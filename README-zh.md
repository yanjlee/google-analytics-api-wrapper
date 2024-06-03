 # google-analytics-api-wrapper
=======
Google Analytics API包装器是一个方便的工具，可以通过API从GA提取数据。当用户拥有多个GA配置文件/网站属性时，它特别有用。
### 安装
```
$ pip install google-api-python-client pandas
$ python setup.py install
```
    
### 使用方法
##### 授权
请访问 https://console.developers.google.com 开始一个API项目。确保您已启用分析API。 
创建一个新的OAuth客户端ID并将其下载到您的工作目录中。 
授权您的API访问权限。
 
```python
from analytics_query import analytics_query as aq
aq.authorize()
```
然后使用可以访问您GA帐户的Google帐户对应用程序进行授权。 
控制台将在工作目录中名为"analytics.dat"的文件中存储您的刷新令牌和访问令牌。 
现在您可以进行API调用。
 
##### 查询GA
get_api_query方法将获取从GA API获取数据的参数，并作为pandas DataFrame返回。 
```python
from analytics_query import analytics_query as aq
df = aq.get_api_query(start_date='7 days ago',
                 end_date='yesterday',
                 metrics='ga:date',
                 dimensions='ga:sessions')
df.head()
```
