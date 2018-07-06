

# secure_django_usermanagement
some tips for having a secure user management


this project is about some tips for having a secure user management in django.


# Header verification
#1.
url = "http://%s/users/new_password?token=%s" % (request.get_host(), token)
here in reseting password we need to send a link with respective token to user, so we used this line of code but here we have a
security vulnerability, that is if we did not defined allowed host in django setting, hackers can change the header and send page back
with their own website and use token for reseting password.
