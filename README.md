# MySQL
Configurando o banco de dados relacional MySQL

package com.demo.mvc.config;

//imports necessários

@Configuration 

public class DataConfiguration {

	@Bean
	public DataSource dataSource() {
		DriverManagerDataSource data = new DriverManagerDataSource();
		data.setUrl("jdbc:mysql://localhost:3306/nome_do_seu_banco");
		data.setUsername("root");
		data.setPassword("");
		return data;
	}
	
	@Bean
	public JpaVendorAdapter jpaVendorAdapter() {
		HibernateJpaVendorAdapter adapter = new HibernateJpaVendorAdapter();
		adapter.setDatabase(Database.MYSQL);
		adapter.setShowSql(true);
		adapter.setGenerateDdl(true);
		adapter.setDatabasePlatform("org.hibernate.dialect.MySQLDialect");
		adapter.setPrepareConnection(true);
		return adapter;
	}
	
}
