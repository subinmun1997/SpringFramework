# SpringFramework

## 스프링

<br>

#### Dispatcher-Servlet

>  서블릿 컨테이너에서 HTTP 프로토콜을 통해 들어오는 모든 요청을 제일 앞에서 처리해주는 프론트 컨트롤러를 말함
>
> 따라서 서버가 받기 전에, 공통처리 작업을 디스패처 서블릿이 처리해주고 적절한 세부 컨트롤러로 작업을 위임해줍니다.
>
> 디스패처 서블릿이 처리하는 url 패턴을 지정해줘야 하는데, 일반적으로는 .mvc와 같은 패턴으로 처리하라고 미리 지정해줍니다.
>
> 
> 디스패처 서블릿으로 인해 web.xml이 가진 역할이 상당히 축소되었습니다. 기존에는 모든 서블릿을 url 매핑 활용을 위해 모두 web.xml에 등록해 주었지만, 디스패처 서블릿은 그 전에 모든 요청을 핸들링해주면서 작업을 편리하게 할 수 있도록 도와줍니다. 또한 이 서블릿을 통해 MVC를 사용할 수 있기 때문에 웹 개발 시 큰 장점을 가져다 줍니다.

<br>

#### DI(Dependency Injection)

> 스프링이 다른 프레임워크와 차별화되어 제공하는 의존 관계 주입 기능으로, 객체를 직접 생성하는 게 아니라 외부에서 생성한 후 주입 시켜주는 방식입니다.
>
> 의존성 주입을 통해서 모듈 간의 결합도가 낮아지고 유연성이 높아집니다.
>
> 스프링 컨테이너가 지원하는 핵심 개념 중 하나로, 설정 파일을 통해 객체간의 의존관계를 설정하는 역할을 합니다.
>
> 각 클래스 사이에 필요로 하는 의존관계를 Bean 설정 정보 바탕으로 컨테이너가 자동으로 연결합니다.
>
> 객체는 직접 의존하고 있는 객체를 생성하거나 검색할 필요가 없으므로 코드 관리가 쉬워지는 장점이 있습니다.

<br>

#### IoC(Inversion of Control)

> 제어의 역전이라는 의미로, 말 그대로 메소드나 객체의 호출작업을 개발자가 결정하는 것이 아니라, 외부에서 결정되는 것을 의미합니다.
>
> 제어의 역전이라고 말하며, 간단히 말해 "제어의 흐름을 바꾼다"라고 합니다.
>
> 객체의 의존성을 역전시켜 객체 간의 결합도를 줄이고 유연한 코드를 작성할 수 있게 하여 가독성 및 코드 중복, 유지 보수를 편하게 할 수 있습니다.
>
> 스프링이 실행될 때 모든 의존성 객체를 만들어주고 필요한 곳에 주입시켜줌으로써 Bean들은 싱글턴 패턴의 특징을 가지며, 제어의 흐름을 사용자가 아닌 스프링에게 맡겨 작업을 처리합니다.

<br>

#### AOP(Aspect Oriented Programming)

> 공통의 관심 사항을 적용해서 발생하는 의존 관계의 복잡성과 코드 중복을 해소해줍니다.
>
> 각 클래스에서 공통 관심 사항을 구현한 모듈에 대한 의존관계를 갖기 보단, Aspect를 이용해 핵심 로직을 구현한 각 클래스에 공통 기능을 적용합니다.
>
> 간단한 설정만으로도 공통 기능을 여러 클래스에 적용할 수 있는 장점이 있으며 핵심 로직 코드를 수정하지 않고도 웹 애플리케이션의 보안, 로깅, 트랜잭션과 같은 공통 관심 사항을 AOP를 이용해 간단하게 적용할 수 있습니다.

<br>

#### AOP 용어

> Advice : 언제 공통 관심기능을 핵심 로직에 적용할지 정의
>
> Joinpoint : Advice를 적용이 가능한 지점을 의미 (before, after 등등)
>
> Pointcut : Joinpoint의 부분집합으로, 실제로 Advice가 적용되는 Joinpoint를 나타냄
>
> Weaving : Advice를 핵심 로직코드에 적용하는 것
>
> Aspect : 여러 객체에 공통으로 적용되는 공통 관심 사항을 말함. 트랜잭션이나 보안 등이 Aspect의 좋은 예

<br>

#### DAO(Data Access Object)

> DB에 데이터를 조회하거나 조작하는 기능들을 전담합니다.
>
> Mybatis를 이용할 때는, mapper.xml에 쿼리문을 작성하고 이를 mapper 클래스에서 받아와 DAO에게 넘겨주는 식으로 구현합니다.

<br>

#### Annotation

> 소스코드에 @어노테이션의 형태로 표현하며 클래스, 필드, 메소드의 선언부에 적용할 수 있는 특정기능이 부여된 표현법을 말합니다.
>
> 애플리케이션 규모가 커질수록, xml 환경설정이 매우 복잡해지는데 이러한 어려움을 개선시키기 위해 자바 파일에 어노테이션을 적용해서 개발자가 설정 파일 작업을 할 때 발생시키는 오류를 최소화해주는 역할을 합니다.
>
> 어노테이션 사용으로 소스 코드에 메타데이터를 보관할 수 있고, 컴파일 타임의 체크뿐 아니라 어노테이션 API를 사용해 코드 가독성도 높여줍니다.

- @Controller : dispatcher-servlet.xml에서 bean 태그로 정의하는 것과 같음.
- @RequestMapping : 특정 메소드에서 요청되는 URL과 매칭시키는 어노테이션
- @Autowired : 자동으로 의존성 주입하기 위한 어노테이션
- @Service : 비즈니스 로직 처리하는 서비스 클래스에 등록
- @Repository : DAO에 등록

<br>

#### Spring JDBC

> 데이터베이스 테이블과, 자바 객체 사이의 단순한 매핑을 간단한 설정을 통해 처리하는 것
>
> 기존의 JDBC에서는 구현하고 싶은 로직마다 필요한 SQL문이 모두 달랐고, 이에 필요한 Connection, PrepareStatement, ResultSet 등을 생성하고 Exception 처리도 모두 해야하는 번거러움이 존재했습니다.
>
> Spring에서는 JDBC와 ORM 프레임워크를 직접 지원하기 때문에 따로 작성하지 않아도 모두 다 처리해주는 장점이 있습니다.

<br>

#### MyBatis

> 객체, 데이터베이스, Mapper 자체를 독립적으로 작성하고, DTO에 해당하는 부분과 SQL 실행결과를 매핑해서 사용할 수 있도록 지원함
>
> 기존에는 DAO에 모두 SQL문이 자바 소스상에 위치했으나, MyBatis를 통해 SQL은 XML 설정 파일로 관리합니다.
>
> 설정파일로 분리하면, 수정할 때 설정파일만 건드리면 되므로 유지보수에 매우 좋습니다. 또한 매개변수나 리턴 타입으로 매핑되는 모든 DTO에 관련된 부분도 모두 설정파일에서 작업할 수 있는 장점이 있습니다.

<br>

<br>

<br>
