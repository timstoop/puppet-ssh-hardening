
source 'https://rubygems.org'

puppetversion = ENV['PUPPET_VERSION']
if puppetversion
  gem 'puppet', puppetversion, :require => false
else
  gem 'puppet', :require => false
end

group :test do
  gem 'rake'
  # bugfix for ruby 1.8, puppet+rspec interplay
  # https://github.com/rspec/rspec-core/issues/1864
  gem 'rspec', '~> 3.1.0', :require => false if RUBY_VERSION.start_with? '1.8'
  gem 'rspec-puppet'
  # avoid NoMethodError: private method `clone' called for #<RuboCop::Cop::CopStore:0x00000104e286c8>
  gem 'puppet-lint'
  gem 'puppetlabs_spec_helper', :git => 'https://github.com/ehaselwanter/puppetlabs_spec_helper'
  gem 'rubocop', '~> 0.31' if RUBY_VERSION > '1.9.2'
end

group :development do
  gem 'guard-rake'
end

group :integration do
  gem 'kitchen-puppet'
  gem 'kitchen-sharedtests', '~> 0.2.0'
  gem 'kitchen-vagrant'
  gem 'librarian-puppet'
  gem 'test-kitchen'
end

group :openstack do
  gem 'kitchen-openstack'
end
