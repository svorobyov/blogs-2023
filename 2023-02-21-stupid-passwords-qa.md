# 2023-02-21

# Stupid Questions and Answers About Passwords

## Q: Are passwords dead?

## A:
Really stupid question.

## Q: But nevertheless?

## A:
Passwords are being declared dead for decades, but they 
stupidly survive nevertheless.

## Q: Is it stupid to reuse the same password for all your logins/websites?

Depends on: 1) how strong your password is and 2) how you 
authenticate with the password  on websites. 
While 1) is clear to resist brute-force attacks, 2) 
is less obvious. Let me explain. First off, it is the stupidiest thing 
to send your password to the website (Like Facebook) to register/sign 
up/login. They leak personal information all the time. Neverthless,
people continue to send their passwords in clear (over HTTPS,
hopefully).

Normally, even if the password is stored in hashed/salted form
only, it is still sent in clear every time the user registers,
changes their password, or logs in. So if the intruder captures 
your register/login session with a cleartext password, your 
password is compromised for all websites you use it for.

Therefore, they constantly repeat like a dogma: use different 
passwords for different passwords. Sounds like a clever advice? 
Not necessarily.

Let me give you a simple clue. You know that the ubiquitous 
`Ssh` protocol
allows you to authenticate with a remote server that knows your
public key only, without ever getting your private key. 
Similar magic happens with TLS client/server authentications 
in electronic banking, commerce, website browsing,
where parties never reveal their private keys (passwords).
This magic was unknown/unthinkable 45-50 yesrs ago.

You may use a single key pair to communicate with many websites,
you never send away your private key. Nothing to be compromised 
by Facebook and similar. The only inconvenience is the length 
of your private key (to remember), especially if you want to use 
it on many devices.

Meanwhile, the feasibility is clear. It is possible to 
authenticate with a remote site withiout ever giving it 
your password! Therefore, you may reuse your single 
strong password on any number of websites. None of then learns,
nor can leak your password.

Some more details.



## Appendix

1. In security, we also call this defense in depth, 
which is the act of layering imperfect defenses 
in hope that an attacker will not defeat all of those layers. 
This is what real-world cryptography is also about.

2. Even if the password is stored after password hashing it, 
   it is still sent in clear every time the user registers, 
   changes their password, or logs in.

3. Cryptographic protocols called asymmetric (or augmented) 
   password-authenticated key exchanges (PAKEs) attempt 
   to provide user authentication without having users 
   ever communicate their passwords directly to the server. 
   This contrasts with symmetric or bal- anced PAKEs protocols, 
   where both sides know the password.