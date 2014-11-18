# Omniauth::Weixin::Oauth2

TODO: Write a gem description

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'omniauth-weixin-oauth2'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install omniauth-weixin-oauth2

## Usage

1 Gemfile中增加gem 'omniauth-weixin-oauth2', :git => 'https://github.com/xuxiaohu/omniauth-weixin-oauth2.git'
2 bundle install
3 config/initializers/omniauth.rb中
  Rails.application.config.middleware.use OmniAuth::Builder do
    provider :weixin, 'appid', 'secret'
  end
4 返回结果
<OmniAuth::AuthHash credentials=#<OmniAuth::AuthHash expires=true expires_at=1416308714 refresh_token="" token=""> extra=#<OmniAuth::AuthHash raw_info=#<OmniAuth::AuthHash city="" country="" headimgurl="" language="zh_CN" nickname="" openid="" privilege=[] province="" sex=1 unionid="">> info=#<OmniAuth::AuthHash::InfoHash city="" country="CN" image="" nickname="" openid="" province="Jiangsu" sex=1> provider="weixin" uid="">

5 callback action中使用
  request.env['omniauth.auth']['info']
  request.env['omniauth.auth']['credentials']

6 补充
  数据格式不一定符合要求，大家自己去 lib/strategies/weinxin.rb该。okay！

## Contributing

1. Fork it ( https://github.com/xuxiaohu/omniauth-weixin-oauth2/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request
