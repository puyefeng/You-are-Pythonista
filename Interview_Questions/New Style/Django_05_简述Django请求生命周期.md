# Django_05_简述Django请求生命周期

## Question

简述Django请求生命周期

1.____ ,请求封装后交给web框架（Flask，Django)

2.____，对请求进行校验或在请求对象中添加其他相关数据，例如：csrf,request.session

3.路由匹配,根据浏览器发送的不同url去匹配不同的视图函数

4.视图函数，在视图函数中进行业务逻辑的处理，可能涉及到：orm，templates

5.____，对响应的数据进行处理

6.____，将响应的内容发送给浏览器

%!A. uwsgi, 中间件,,中间件,uwsgi!%

%!B. wsgi, 中间件,中间件,wsgi!%

%!C. wsgi, 数据库,数据库,wsgi!%

%!D. uwsgi, 数据库,数据库,uwsgi!%

------

## Answer

@!B!@

------

## Analysis

一般是用户通过浏览器向我们的服务器发起一个请求(request),这个请求会去访问视图函数，如果不涉及到数据调用，那么这个时候视图函数返回一个模板也就是一个网页给用户, 视图函数调用模型去数据库查找数据，然后逐级返回，视图函数把返回的数据填充到模板空格中，最后返回网页给用户。

1.wsgi ,请求封装后交给web框架（Flask，Django)

2.中间件，对请求进行校验或在请求对象中添加其他相关数据，例如：csrf,request.session

3.路由匹配,根据浏览器发送的不同url去匹配不同的视图函数

4.视图函数，在视图函数中进行业务逻辑的处理，可能涉及到：orm，templates

5.中间件，对响应的数据进行处理

6.wsgi，将响应的内容发送给浏览器