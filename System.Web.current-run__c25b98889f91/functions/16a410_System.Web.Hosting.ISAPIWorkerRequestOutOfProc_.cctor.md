# System.Web.Hosting.ISAPIWorkerRequestOutOfProc::.cctor

- ea: `0x16a410`
- end: `0x16a534`
- name: `System.Web.Hosting.ISAPIWorkerRequestOutOfProc::.cctor`
- size: `292`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x16a419`: `APPL_MD_PATH`
- `0x16a4d7`: `INSTANCE_META_PATH`
- `0x16a516`: `SERVER_PROTOCOL`
- `0x16a498`: `HTTP_USER_AGENT`

## pseudocode

```c

```

## disassembly

```asm
0x16a410  ldc.i4.s 0x20
0x16a412  newarr   [mscorlib]System.String
0x16a417  dup
0x16a418  ldc.i4.0
0x16a419  ldstr    aApplMdPath// "APPL_MD_PATH"
0x16a41e  stelem.ref
0x16a41f  dup
0x16a420  ldc.i4.1
0x16a421  ldstr    aAllRaw// "ALL_RAW"
0x16a426  stelem.ref
0x16a427  dup
0x16a428  ldc.i4.2
0x16a429  ldstr    aAuthPassword// "AUTH_PASSWORD"
0x16a42e  stelem.ref
0x16a42f  dup
0x16a430  ldc.i4.3
0x16a431  ldstr    aAuthType// "AUTH_TYPE"
0x16a436  stelem.ref
0x16a437  dup
0x16a438  ldc.i4.4
0x16a439  ldstr    aCertCookie// "CERT_COOKIE"
0x16a43e  stelem.ref
0x16a43f  dup
0x16a440  ldc.i4.5
0x16a441  ldstr    aCertFlags// "CERT_FLAGS"
0x16a446  stelem.ref
0x16a447  dup
0x16a448  ldc.i4.6
0x16a449  ldstr    aCertIssuer// "CERT_ISSUER"
0x16a44e  stelem.ref
0x16a44f  dup
0x16a450  ldc.i4.7
0x16a451  ldstr    aCertKeysize// "CERT_KEYSIZE"
0x16a456  stelem.ref
0x16a457  dup
0x16a458  ldc.i4.8
0x16a459  ldstr    aCertSecretkeys// "CERT_SECRETKEYSIZE"
0x16a45e  stelem.ref
0x16a45f  dup
0x16a460  ldc.i4.s 9
0x16a462  ldstr    aCertSerialnumb// "CERT_SERIALNUMBER"
0x16a467  stelem.ref
0x16a468  dup
0x16a469  ldc.i4.s 0xA
0x16a46b  ldstr    aCertServerIssu// "CERT_SERVER_ISSUER"
0x16a470  stelem.ref
0x16a471  dup
0x16a472  ldc.i4.s 0xB
0x16a474  ldstr    aCertServerSubj// "CERT_SERVER_SUBJECT"
0x16a479  stelem.ref
0x16a47a  dup
0x16a47b  ldc.i4.s 0xC
0x16a47d  ldstr    aCertSubject// "CERT_SUBJECT"
0x16a482  stelem.ref
0x16a483  dup
0x16a484  ldc.i4.s 0xD
0x16a486  ldstr    aGatewayInterfa// "GATEWAY_INTERFACE"
0x16a48b  stelem.ref
0x16a48c  dup
0x16a48d  ldc.i4.s 0xE
0x16a48f  ldstr    aHttpCookie// "HTTP_COOKIE"
0x16a494  stelem.ref
0x16a495  dup
0x16a496  ldc.i4.s 0xF
0x16a498  ldstr    aHttpUserAgent// "HTTP_USER_AGENT"
0x16a49d  stelem.ref
0x16a49e  dup
0x16a49f  ldc.i4.s 0x10
0x16a4a1  ldstr    aHttps// "HTTPS"
0x16a4a6  stelem.ref
0x16a4a7  dup
0x16a4a8  ldc.i4.s 0x11
0x16a4aa  ldstr    aHttpsKeysize// "HTTPS_KEYSIZE"
0x16a4af  stelem.ref
0x16a4b0  dup
0x16a4b1  ldc.i4.s 0x12
0x16a4b3  ldstr    aHttpsSecretkey// "HTTPS_SECRETKEYSIZE"
0x16a4b8  stelem.ref
0x16a4b9  dup
0x16a4ba  ldc.i4.s 0x13
0x16a4bc  ldstr    aHttpsServerIss// "HTTPS_SERVER_ISSUER"
0x16a4c1  stelem.ref
0x16a4c2  dup
0x16a4c3  ldc.i4.s 0x14
0x16a4c5  ldstr    aHttpsServerSub// "HTTPS_SERVER_SUBJECT"
0x16a4ca  stelem.ref
0x16a4cb  dup
0x16a4cc  ldc.i4.s 0x15
0x16a4ce  ldstr    aInstanceId// "INSTANCE_ID"
0x16a4d3  stelem.ref
0x16a4d4  dup
0x16a4d5  ldc.i4.s 0x16
0x16a4d7  ldstr    aInstanceMetaPa// "INSTANCE_META_PATH"
0x16a4dc  stelem.ref
0x16a4dd  dup
0x16a4de  ldc.i4.s 0x17
0x16a4e0  ldstr    aLocalAddr// "LOCAL_ADDR"
0x16a4e5  stelem.ref
0x16a4e6  dup
0x16a4e7  ldc.i4.s 0x18
0x16a4e9  ldstr    aLogonUser// "LOGON_USER"
0x16a4ee  stelem.ref
0x16a4ef  dup
0x16a4f0  ldc.i4.s 0x19
0x16a4f2  ldstr    aRemoteAddr// "REMOTE_ADDR"
0x16a4f7  stelem.ref
0x16a4f8  dup
0x16a4f9  ldc.i4.s 0x1A
0x16a4fb  ldstr    aRemoteHost// "REMOTE_HOST"
0x16a500  stelem.ref
0x16a501  dup
0x16a502  ldc.i4.s 0x1B
0x16a504  ldstr    aServerName// "SERVER_NAME"
0x16a509  stelem.ref
0x16a50a  dup
0x16a50b  ldc.i4.s 0x1C
0x16a50d  ldstr    aServerPort// "SERVER_PORT"
0x16a512  stelem.ref
0x16a513  dup
0x16a514  ldc.i4.s 0x1D
0x16a516  ldstr    aServerProtocol// "SERVER_PROTOCOL"
0x16a51b  stelem.ref
0x16a51c  dup
0x16a51d  ldc.i4.s 0x1E
0x16a51f  ldstr    aServerSoftware// "SERVER_SOFTWARE"
0x16a524  stelem.ref
0x16a525  dup
0x16a526  ldc.i4.s 0x1F
0x16a528  ldstr    aRemotePort// "REMOTE_PORT"
0x16a52d  stelem.ref
0x16a52e  stsfld   string[] System.Web.Hosting.ISAPIWorkerRequestOutOfProc::_serverVarNames
0x16a533  ret
```
