# System.Web.Hosting.ISAPIWorkerRequestInProc::GetServerVariable

- ea: `0x168d50`
- end: `0x169061`
- name: `System.Web.Hosting.ISAPIWorkerRequestInProc::GetServerVariable`
- size: `785`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x32200`
- `0x168c00`
- `0x168d30`
- `0x168d50`

## string_xrefs

- `0x168e09`: `INSTANCE_META_PATH`
- `0x168e93`: `SERVER_PROTOCOL`
- `0x168e7d`: `HTTP_USER_AGENT`

## pseudocode

```c

```

## disassembly

```asm
0x168d50  ldarg.1
0x168d51  brfalse  loc_169059
0x168d56  ldarg.1
0x168d57  callvirt instance int32 [mscorlib]System.String::get_Length()
0x168d5c  stloc.0
0x168d5d  ldloc.0
0x168d5e  ldc.i4.5
0x168d5f  sub
0x168d60  switch   loc_169042, loc_169059, loc_16902B, loc_169059, loc_169015, loc_168FD3, loc_168F1F, loc_168EF0, loc_168EC1, loc_169059, loc_168E7C, loc_169059, loc_168E4D, loc_168E08, loc_168DC3, loc_168DAA
0x168da5  br       loc_169059
0x168daa  ldarg.1
0x168dab  ldstr    aHttpsServerSub// "HTTPS_SERVER_SUBJECT"
0x168db0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168db5  brfalse  loc_169059
0x168dba  ldarg.0
0x168dbb  ldc.i4.s 0x1B
0x168dbd  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168dc2  ret
0x168dc3  ldarg.1
0x168dc4  ldstr    aHttpsSecretkey// "HTTPS_SECRETKEYSIZE"
0x168dc9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168dce  brfalse.s loc_168DD9
0x168dd0  ldarg.0
0x168dd1  ldc.i4.s 0x19
0x168dd3  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168dd8  ret
0x168dd9  ldarg.1
0x168dda  ldstr    aCertServerSubj// "CERT_SERVER_SUBJECT"
0x168ddf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168de4  brfalse.s loc_168DEF
0x168de6  ldarg.0
0x168de7  ldc.i4.s 0x15
0x168de9  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168dee  ret
0x168def  ldarg.1
0x168df0  ldstr    aHttpsServerIss// "HTTPS_SERVER_ISSUER"
0x168df5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168dfa  brfalse  loc_169059
0x168dff  ldarg.0
0x168e00  ldc.i4.s 0x1A
0x168e02  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e07  ret
0x168e08  ldarg.1
0x168e09  ldstr    aInstanceMetaPa// "INSTANCE_META_PATH"
0x168e0e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e13  brfalse.s loc_168E1E
0x168e15  ldarg.0
0x168e16  ldc.i4.s 0x1D
0x168e18  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e1d  ret
0x168e1e  ldarg.1
0x168e1f  ldstr    aCertSecretkeys// "CERT_SECRETKEYSIZE"
0x168e24  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e29  brfalse.s loc_168E34
0x168e2b  ldarg.0
0x168e2c  ldc.i4.s 0x12
0x168e2e  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e33  ret
0x168e34  ldarg.1
0x168e35  ldstr    aCertServerIssu// "CERT_SERVER_ISSUER"
0x168e3a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e3f  brfalse  loc_169059
0x168e44  ldarg.0
0x168e45  ldc.i4.s 0x14
0x168e47  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e4c  ret
0x168e4d  ldarg.1
0x168e4e  ldstr    aCertSerialnumb// "CERT_SERIALNUMBER"
0x168e53  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e58  brfalse.s loc_168E63
0x168e5a  ldarg.0
0x168e5b  ldc.i4.s 0x13
0x168e5d  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e62  ret
0x168e63  ldarg.1
0x168e64  ldstr    aGatewayInterfa// "GATEWAY_INTERFACE"
0x168e69  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e6e  brfalse  loc_169059
0x168e73  ldarg.0
0x168e74  ldc.i4.s 0x17
0x168e76  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168e7b  ret
0x168e7c  ldarg.1
0x168e7d  ldstr    aHttpUserAgent// "HTTP_USER_AGENT"
0x168e82  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e87  brfalse.s loc_168E92
0x168e89  ldarg.0
0x168e8a  ldc.i4.s 0x27
0x168e8c  callvirt instance string System.Web.HttpWorkerRequest::GetKnownRequestHeader(int32 index)
0x168e91  ret
0x168e92  ldarg.1
0x168e93  ldstr    aServerProtocol// "SERVER_PROTOCOL"
0x168e98  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168e9d  brfalse.s loc_168EA8
0x168e9f  ldarg.0
0x168ea0  ldc.i4.s 0x21
0x168ea2  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168ea7  ret
0x168ea8  ldarg.1
0x168ea9  ldstr    aServerSoftware// "SERVER_SOFTWARE"
0x168eae  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168eb3  brfalse  loc_169059
0x168eb8  ldarg.0
0x168eb9  ldc.i4.s 0x22
0x168ebb  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168ec0  ret
0x168ec1  ldarg.1
0x168ec2  ldstr    aAuthPassword// "AUTH_PASSWORD"
0x168ec7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168ecc  brfalse.s loc_168ED7
0x168ece  ldarg.0
0x168ecf  ldc.i4.s 0xD
0x168ed1  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168ed6  ret
0x168ed7  ldarg.1
0x168ed8  ldstr    aHttpsKeysize// "HTTPS_KEYSIZE"
0x168edd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168ee2  brfalse  loc_169059
0x168ee7  ldarg.0
0x168ee8  ldc.i4.s 0x18
0x168eea  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168eef  ret
0x168ef0  ldarg.1
0x168ef1  ldstr    aCertKeysize// "CERT_KEYSIZE"
0x168ef6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168efb  brfalse.s loc_168F06
0x168efd  ldarg.0
0x168efe  ldc.i4.s 0x11
0x168f00  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168f05  ret
0x168f06  ldarg.1
0x168f07  ldstr    aCertSubject// "CERT_SUBJECT"
0x168f0c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f11  brfalse  loc_169059
0x168f16  ldarg.0
0x168f17  ldc.i4.s 0x16
0x168f19  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168f1e  ret
0x168f1f  ldarg.1
0x168f20  ldstr    aServerName// "SERVER_NAME"
0x168f25  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f2a  brfalse.s loc_168F35
0x168f2c  ldarg.0
0x168f2d  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x168f32  ldc.i4.8
0x168f33  ldelem.ref
0x168f34  ret
0x168f35  ldarg.1
0x168f36  ldstr    aServerPort// "SERVER_PORT"
0x168f3b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f40  brfalse.s loc_168F4C
0x168f42  ldarg.0
0x168f43  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x168f48  ldc.i4.s 9
0x168f4a  ldelem.ref
0x168f4b  ret
0x168f4c  ldarg.1
0x168f4d  ldstr    aRemoteHost// "REMOTE_HOST"
0x168f52  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f57  brfalse.s loc_168F62
0x168f59  ldarg.0
0x168f5a  ldc.i4.s 0x1F
0x168f5c  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168f61  ret
0x168f62  ldarg.1
0x168f63  ldstr    aRemotePort// "REMOTE_PORT"
0x168f68  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f6d  brfalse.s loc_168F78
0x168f6f  ldarg.0
0x168f70  ldc.i4.s 0x20
0x168f72  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168f77  ret
0x168f78  ldarg.1
0x168f79  ldstr    aRemoteAddr// "REMOTE_ADDR"
0x168f7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f83  brfalse.s loc_168F8E
0x168f85  ldarg.0
0x168f86  ldc.i4.s 0xC
0x168f88  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168f8d  ret
0x168f8e  ldarg.1
0x168f8f  ldstr    aCertCookie// "CERT_COOKIE"
0x168f94  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168f99  brfalse.s loc_168FA4
0x168f9b  ldarg.0
0x168f9c  ldc.i4.s 0xE
0x168f9e  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168fa3  ret
0x168fa4  ldarg.1
0x168fa5  ldstr    aCertIssuer// "CERT_ISSUER"
0x168faa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168faf  brfalse.s loc_168FBA
0x168fb1  ldarg.0
0x168fb2  ldc.i4.s 0x10
0x168fb4  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168fb9  ret
0x168fba  ldarg.1
0x168fbb  ldstr    aInstanceId// "INSTANCE_ID"
0x168fc0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168fc5  brfalse  loc_169059
0x168fca  ldarg.0
0x168fcb  ldc.i4.s 0x1C
0x168fcd  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168fd2  ret
0x168fd3  ldarg.1
0x168fd4  ldstr    aLogonUser// "LOGON_USER"
0x168fd9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168fde  brfalse.s loc_168FE9
0x168fe0  ldarg.0
0x168fe1  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x168fe6  ldc.i4.0
0x168fe7  ldelem.ref
0x168fe8  ret
0x168fe9  ldarg.1
0x168fea  ldstr    aLocalAddr// "LOCAL_ADDR"
0x168fef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x168ff4  brfalse.s loc_168FFF
0x168ff6  ldarg.0
0x168ff7  ldc.i4.s 0x1E
0x168ff9  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x168ffe  ret
0x168fff  ldarg.1
0x169000  ldstr    aCertFlags// "CERT_FLAGS"
0x169005  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16900a  brfalse.s loc_169059
0x16900c  ldarg.0
0x16900d  ldc.i4.s 0xF
0x16900f  call     instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetAdditionalServerVar(int32 index)
0x169014  ret
0x169015  ldarg.1
0x169016  ldstr    aAuthType// "AUTH_TYPE"
0x16901b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x169020  brfalse.s loc_169059
0x169022  ldarg.0
0x169023  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x169028  ldc.i4.1
0x169029  ldelem.ref
0x16902a  ret
0x16902b  ldarg.1
0x16902c  ldstr    aAllRaw// "ALL_RAW"
0x169031  call     bool [mscorlib]System.String::op_Equality(string, string)
0x169036  brfalse.s loc_169059
0x169038  ldarg.0
0x169039  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x16903e  ldc.i4.s 0xB
0x169040  ldelem.ref
0x169041  ret
0x169042  ldarg.1
0x169043  ldstr    aHttps// "HTTPS"
0x169048  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16904d  brfalse.s loc_169059
0x16904f  ldarg.0
0x169050  ldfld    string[] System.Web.Hosting.ISAPIWorkerRequestInProc::_basicServerVars
0x169055  ldc.i4.s 0xA
0x169057  ldelem.ref
0x169058  ret
0x169059  ldarg.0
0x16905a  ldarg.1
0x16905b  callvirt instance string System.Web.Hosting.ISAPIWorkerRequestInProc::GetServerVariableCore(string name)
0x169060  ret
```
