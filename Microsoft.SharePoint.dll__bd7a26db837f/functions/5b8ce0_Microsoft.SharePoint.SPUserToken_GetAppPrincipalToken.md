# Microsoft.SharePoint.SPUserToken::GetAppPrincipalToken

- ea: `0x5b8ce0`
- end: `0x5b908a`
- name: `Microsoft.SharePoint.SPUserToken::GetAppPrincipalToken`
- size: `938`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x268820`
- `0x685b00`

## callees

- `0x1b7de0`
- `0x4a24c0`
- `0x4a2520`
- `0x577070`
- `0x5b8ce0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x5b8cf8`: `The user token's length {0} is less than {1}.`
- `0x5b8d28`: `InvalidUserToken`
- `0x5b8d87`: `InvalidUserToken`
- `0x5b8e1a`: `InvalidUserToken`
- `0x5b8e6e`: `InvalidUserToken`
- `0x5b8edc`: `InvalidUserToken`
- `0x5b8f69`: `InvalidUserToken`
- `0x5b8fde`: `InvalidUserToken`
- `0x5b9071`: `InvalidUserToken`
- `0x5b8d58`: `The length of the token {0} does not match the specified size in the token {1}.`
- `0x5b8dd9`: `The size of the token {0} does not match the specified sizes in the token. cbSide={1}, cbGroups={2}, cbAppPrincipal={3}`
- `0x5b8f4a`: `The app principal and perms token '{0}' is invalid.`
- `0x5b8fbf`: `The app principal and perms token '{0}' is invalid.`
- `0x5b904d`: `The app principal type {0} specified in the token is not valid.`

## pseudocode

```c

```

## disassembly

```asm
0x5b8ce0  ldarg.0
0x5b8ce1  brtrue.s loc_5B8CE5
0x5b8ce3  ldnull
0x5b8ce4  ret
0x5b8ce5  ldarg.0
0x5b8ce6  ldlen
0x5b8ce7  conv.i4
0x5b8ce8  ldc.i4.s 0x28
0x5b8cea  bge.s    loc_5B8D3E
0x5b8cec  ldc.i4   0xC73C2
0x5b8cf1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8cf6  ldc.i4.s 0x14
0x5b8cf8  ldstr    aTheUserTokenSL// "The user token's length {0} is less tha"...
0x5b8cfd  ldc.i4.2
0x5b8cfe  newarr   [mscorlib]System.Object
0x5b8d03  stloc.s  0xA
0x5b8d05  ldloc.s  0xA
0x5b8d07  ldc.i4.0
0x5b8d08  ldarg.0
0x5b8d09  ldlen
0x5b8d0a  conv.i4
0x5b8d0b  box      [mscorlib]System.Int32
0x5b8d10  stelem.ref
0x5b8d11  ldloc.s  0xA
0x5b8d13  ldc.i4.1
0x5b8d14  ldc.i4.s 0x28
0x5b8d16  box      [mscorlib]System.Int32
0x5b8d1b  stelem.ref
0x5b8d1c  ldloc.s  0xA
0x5b8d1e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8d23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8d28  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8d2d  ldc.i4.0
0x5b8d2e  newarr   [mscorlib]System.Object
0x5b8d33  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8d38  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8d3d  throw
0x5b8d3e  ldarg.0
0x5b8d3f  ldc.i4.8
0x5b8d40  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x5b8d45  stloc.0
0x5b8d46  ldloc.0
0x5b8d47  ldarg.0
0x5b8d48  ldlen
0x5b8d49  conv.i4
0x5b8d4a  beq.s    loc_5B8D9D
0x5b8d4c  ldc.i4   0xC73C3
0x5b8d51  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8d56  ldc.i4.s 0x14
0x5b8d58  ldstr    aTheLengthOfThe// "The length of the token {0} does not ma"...
0x5b8d5d  ldc.i4.2
0x5b8d5e  newarr   [mscorlib]System.Object
0x5b8d63  stloc.s  0xB
0x5b8d65  ldloc.s  0xB
0x5b8d67  ldc.i4.0
0x5b8d68  ldarg.0
0x5b8d69  ldlen
0x5b8d6a  conv.i4
0x5b8d6b  box      [mscorlib]System.Int32
0x5b8d70  stelem.ref
0x5b8d71  ldloc.s  0xB
0x5b8d73  ldc.i4.1
0x5b8d74  ldloc.0
0x5b8d75  box      [mscorlib]System.Int32
0x5b8d7a  stelem.ref
0x5b8d7b  ldloc.s  0xB
0x5b8d7d  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8d82  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8d87  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8d8c  ldc.i4.0
0x5b8d8d  newarr   [mscorlib]System.Object
0x5b8d92  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8d97  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8d9c  throw
0x5b8d9d  ldarg.0
0x5b8d9e  ldc.i4.s 0x14
0x5b8da0  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x5b8da5  stloc.1
0x5b8da6  ldarg.0
0x5b8da7  ldc.i4.s 0x18
0x5b8da9  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x5b8dae  stloc.2
0x5b8daf  ldarg.0
0x5b8db0  ldc.i4.s 0x24
0x5b8db2  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x5b8db7  stloc.3
0x5b8db8  ldarg.0
0x5b8db9  ldc.i4.s 0x20
0x5b8dbb  call     int32 [mscorlib]System.BitConverter::ToInt32(unsigned int8[], int32)
0x5b8dc0  stloc.s  4
0x5b8dc2  ldloc.0
0x5b8dc3  ldloc.1
0x5b8dc4  ldloc.2
0x5b8dc5  add
0x5b8dc6  ldloc.3
0x5b8dc7  add
0x5b8dc8  ldc.i4.s 0x28
0x5b8dca  add
0x5b8dcb  beq.s    loc_5B8E30
0x5b8dcd  ldc.i4   0xC73C4
0x5b8dd2  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8dd7  ldc.i4.s 0x14
0x5b8dd9  ldstr    aTheSizeOfTheTo// "The size of the token {0} does not matc"...
0x5b8dde  ldc.i4.4
0x5b8ddf  newarr   [mscorlib]System.Object
0x5b8de4  stloc.s  0xC
0x5b8de6  ldloc.s  0xC
0x5b8de8  ldc.i4.0
0x5b8de9  ldloc.0
0x5b8dea  box      [mscorlib]System.Int32
0x5b8def  stelem.ref
0x5b8df0  ldloc.s  0xC
0x5b8df2  ldc.i4.1
0x5b8df3  ldloc.1
0x5b8df4  box      [mscorlib]System.Int32
0x5b8df9  stelem.ref
0x5b8dfa  ldloc.s  0xC
0x5b8dfc  ldc.i4.2
0x5b8dfd  ldloc.2
0x5b8dfe  box      [mscorlib]System.Int32
0x5b8e03  stelem.ref
0x5b8e04  ldloc.s  0xC
0x5b8e06  ldc.i4.3
0x5b8e07  ldloc.3
0x5b8e08  box      [mscorlib]System.Int32
0x5b8e0d  stelem.ref
0x5b8e0e  ldloc.s  0xC
0x5b8e10  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8e15  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8e1a  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8e1f  ldc.i4.0
0x5b8e20  newarr   [mscorlib]System.Object
0x5b8e25  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8e2a  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8e2f  throw
0x5b8e30  ldloc.s  4
0x5b8e32  brfalse.s loc_5B8E39
0x5b8e34  ldloc.s  4
0x5b8e36  ldc.i4.1
0x5b8e37  bne.un.s loc_5B8E3B
0x5b8e39  ldnull
0x5b8e3a  ret
0x5b8e3b  ldloc.3
0x5b8e3c  brtrue.s loc_5B8E84
0x5b8e3e  ldc.i4   0xC73C5
0x5b8e43  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8e48  ldc.i4.s 0x14
0x5b8e4a  ldstr    aTheAppPrincipa_5// "The app principal type is {0} but the s"...
0x5b8e4f  ldc.i4.1
0x5b8e50  newarr   [mscorlib]System.Object
0x5b8e55  stloc.s  0xD
0x5b8e57  ldloc.s  0xD
0x5b8e59  ldc.i4.0
0x5b8e5a  ldloc.s  4
0x5b8e5c  box      [mscorlib]System.Int32
0x5b8e61  stelem.ref
0x5b8e62  ldloc.s  0xD
0x5b8e64  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8e69  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8e6e  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8e73  ldc.i4.0
0x5b8e74  newarr   [mscorlib]System.Object
0x5b8e79  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8e7e  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8e83  throw
0x5b8e84  call     class [mscorlib]System.Text.Encoding [mscorlib]System.Text.Encoding::get_Unicode()
0x5b8e89  ldarg.0
0x5b8e8a  ldloc.1
0x5b8e8b  ldloc.2
0x5b8e8c  add
0x5b8e8d  ldc.i4.s 0x28
0x5b8e8f  add
0x5b8e90  ldloc.3
0x5b8e91  callvirt instance string [mscorlib]System.Text.Encoding::GetString(unsigned int8[], int32, int32)
0x5b8e96  stloc.s  5
0x5b8e98  ldloc.s  5
0x5b8e9a  stloc.s  6
0x5b8e9c  ldsfld   string [mscorlib]System.String::Empty
0x5b8ea1  stloc.s  7
0x5b8ea3  ldloc.s  5
0x5b8ea5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5b8eaa  brfalse.s loc_5B8EF2
0x5b8eac  ldc.i4   0x48B391
0x5b8eb1  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8eb6  ldc.i4.s 0x14
0x5b8eb8  ldstr    aTheAppPrincipa_6// "The app principal type is {0} but the v"...
0x5b8ebd  ldc.i4.1
0x5b8ebe  newarr   [mscorlib]System.Object
0x5b8ec3  stloc.s  0xE
0x5b8ec5  ldloc.s  0xE
0x5b8ec7  ldc.i4.0
0x5b8ec8  ldloc.s  4
0x5b8eca  box      [mscorlib]System.Int32
0x5b8ecf  stelem.ref
0x5b8ed0  ldloc.s  0xE
0x5b8ed2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8ed7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8edc  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8ee1  ldc.i4.0
0x5b8ee2  newarr   [mscorlib]System.Object
0x5b8ee7  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8eec  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8ef1  throw
0x5b8ef2  ldloc.s  5
0x5b8ef4  ldsfld   char[] Microsoft.SharePoint.SPUserToken::s_AppPrincipalNamePermissionsSeperators
0x5b8ef9  ldc.i4.0
0x5b8efa  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0x5b8eff  stloc.s  8
0x5b8f01  ldloc.s  8
0x5b8f03  ldlen
0x5b8f04  conv.i4
0x5b8f05  stloc.s  0xF
0x5b8f07  ldloc.s  0xF
0x5b8f09  ldc.i4.1
0x5b8f0a  sub
0x5b8f0b  switch   loc_5B8F1D, loc_5B8F28
0x5b8f18  br       loc_5B8FB3
0x5b8f1d  ldloc.s  8
0x5b8f1f  ldc.i4.0
0x5b8f20  ldelem.ref
0x5b8f21  stloc.s  6
0x5b8f23  br       loc_5B8FF4
0x5b8f28  ldloc.s  8
0x5b8f2a  ldc.i4.0
0x5b8f2b  ldelem.ref
0x5b8f2c  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5b8f31  brfalse.s loc_5B8F7F
0x5b8f33  ldloc.s  8
0x5b8f35  ldc.i4.1
0x5b8f36  ldelem.ref
0x5b8f37  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x5b8f3c  brfalse.s loc_5B8F7F
0x5b8f3e  ldc.i4   0x48B392
0x5b8f43  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8f48  ldc.i4.s 0x14
0x5b8f4a  ldstr    aTheAppPrincipa_7// "The app principal and perms token '{0}'"...
0x5b8f4f  ldc.i4.1
0x5b8f50  newarr   [mscorlib]System.Object
0x5b8f55  stloc.s  0x10
0x5b8f57  ldloc.s  0x10
0x5b8f59  ldc.i4.0
0x5b8f5a  ldloc.s  6
0x5b8f5c  stelem.ref
0x5b8f5d  ldloc.s  0x10
0x5b8f5f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8f64  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8f69  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8f6e  ldc.i4.0
0x5b8f6f  newarr   [mscorlib]System.Object
0x5b8f74  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8f79  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8f7e  throw
0x5b8f7f  ldloc.s  8
0x5b8f81  ldc.i4.0
0x5b8f82  ldelem.ref
0x5b8f83  stloc.s  6
0x5b8f85  ldloc.s  8
0x5b8f87  ldc.i4.1
0x5b8f88  ldelem.ref
0x5b8f89  stloc.s  7
0x5b8f8b  ldc.i4   0x48B393
0x5b8f90  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8f95  ldc.i4.s 0x64
0x5b8f97  ldstr    aTheAppPrincipa_8// "The app principal perms are {0}."
0x5b8f9c  ldc.i4.1
0x5b8f9d  newarr   [mscorlib]System.Object
0x5b8fa2  stloc.s  0x11
0x5b8fa4  ldloc.s  0x11
0x5b8fa6  ldc.i4.0
0x5b8fa7  ldloc.s  7
0x5b8fa9  stelem.ref
0x5b8faa  ldloc.s  0x11
0x5b8fac  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8fb1  br.s     loc_5B8FF4
0x5b8fb3  ldc.i4   0x48B394
0x5b8fb8  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8fbd  ldc.i4.s 0x14
0x5b8fbf  ldstr    aTheAppPrincipa_7// "The app principal and perms token '{0}'"...
0x5b8fc4  ldc.i4.1
0x5b8fc5  newarr   [mscorlib]System.Object
0x5b8fca  stloc.s  0x12
0x5b8fcc  ldloc.s  0x12
0x5b8fce  ldc.i4.0
0x5b8fcf  ldloc.s  6
0x5b8fd1  stelem.ref
0x5b8fd2  ldloc.s  0x12
0x5b8fd4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x5b8fd9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5b8fde  ldstr    aInvalidusertok// "InvalidUserToken"
0x5b8fe3  ldc.i4.0
0x5b8fe4  newarr   [mscorlib]System.Object
0x5b8fe9  call     string Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo culture, string name, object[] values)
0x5b8fee  newobj   instance void Microsoft.SharePoint.SPException::.ctor(string strMessage)
0x5b8ff3  throw
0x5b8ff4  ldc.i4   0x48B395
0x5b8ff9  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x5b8ffe  ldc.i4.s 0x64
0x5b9000  ldstr    aTheAppPrincipa_9// "The app principal name is {0}."
0x5b9005  ldc.i4.1
0x5b9006  newarr   [mscorlib]System.Object
  ... truncated ...
```
