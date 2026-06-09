# System.Web.Management.WebErrorEvent::GenerateFieldsForMarshal

- ea: `0x47a20`
- end: `0x47b97`
- name: `System.Web.Management.WebErrorEvent::GenerateFieldsForMarshal`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x45fc0`
- `0x47830`
- `0x47950`
- `0x47980`
- `0x48840`
- `0x48850`
- `0x48860`
- `0x48870`
- `0x48880`
- `0x48d10`
- `0x48d20`
- `0x48d30`
- `0x48d40`

## string_xrefs

- `0x47a44`: `RequestPath`
- `0x47af6`: `RequestThreadAccountName`
- `0x47b12`: `ThreadID`
- `0x47b3b`: `ThreadAccountName`
- `0x47b73`: `IsImpersonating`

## pseudocode

```c

```

## disassembly

```asm
0x47a20  ldarg.0
0x47a21  ldarg.1
0x47a22  call     instance void System.Web.Management.WebBaseErrorEvent::GenerateFieldsForMarshal(class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData> fields)
0x47a27  ldarg.1
0x47a28  ldstr    aRequesturl_0// "RequestUrl"
0x47a2d  ldarg.0
0x47a2e  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47a33  callvirt instance string System.Web.Management.WebRequestInformation::get_RequestUrl()
0x47a38  ldc.i4.0
0x47a39  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47a3e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47a43  ldarg.1
0x47a44  ldstr    aRequestpath// "RequestPath"
0x47a49  ldarg.0
0x47a4a  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47a4f  callvirt instance string System.Web.Management.WebRequestInformation::get_RequestPath()
0x47a54  ldc.i4.0
0x47a55  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47a5a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47a5f  ldarg.1
0x47a60  ldstr    aUserhostaddres// "UserHostAddress"
0x47a65  ldarg.0
0x47a66  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47a6b  callvirt instance string System.Web.Management.WebRequestInformation::get_UserHostAddress()
0x47a70  ldc.i4.0
0x47a71  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47a76  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47a7b  ldarg.1
0x47a7c  ldstr    aUsername// "UserName"
0x47a81  ldarg.0
0x47a82  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47a87  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47a8c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47a91  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x47a96  ldc.i4.0
0x47a97  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47a9c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47aa1  ldarg.1
0x47aa2  ldstr    aUserauthentica// "UserAuthenticated"
0x47aa7  ldarg.0
0x47aa8  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47aad  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47ab2  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47ab7  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x47abc  stloc.0
0x47abd  ldloca.s 0
0x47abf  call     instance string [mscorlib]System.Boolean::ToString()
0x47ac4  ldc.i4.2
0x47ac5  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47aca  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47acf  ldarg.1
0x47ad0  ldstr    aUserauthentica_0// "UserAuthenticationType"
0x47ad5  ldarg.0
0x47ad6  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47adb  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47ae0  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47ae5  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_AuthenticationType()
0x47aea  ldc.i4.0
0x47aeb  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47af0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47af5  ldarg.1
0x47af6  ldstr    aRequestthreada// "RequestThreadAccountName"
0x47afb  ldarg.0
0x47afc  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebErrorEvent::get_RequestInformation()
0x47b01  callvirt instance string System.Web.Management.WebRequestInformation::get_ThreadAccountName()
0x47b06  ldc.i4.0
0x47b07  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47b0c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47b11  ldarg.1
0x47b12  ldstr    aThreadid_0// "ThreadID"
0x47b17  ldarg.0
0x47b18  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebErrorEvent::get_ThreadInformation()
0x47b1d  callvirt instance int32 System.Web.Management.WebThreadInformation::get_ThreadID()
0x47b22  stloc.1
0x47b23  ldloca.s 1
0x47b25  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InstalledUICulture()
0x47b2a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x47b2f  ldc.i4.1
0x47b30  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47b35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47b3a  ldarg.1
0x47b3b  ldstr    aThreadaccountn// "ThreadAccountName"
0x47b40  ldarg.0
0x47b41  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebErrorEvent::get_ThreadInformation()
0x47b46  callvirt instance string System.Web.Management.WebThreadInformation::get_ThreadAccountName()
0x47b4b  ldc.i4.0
0x47b4c  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47b51  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47b56  ldarg.1
0x47b57  ldstr    aStacktrace// "StackTrace"
0x47b5c  ldarg.0
0x47b5d  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebErrorEvent::get_ThreadInformation()
0x47b62  callvirt instance string System.Web.Management.WebThreadInformation::get_StackTrace()
0x47b67  ldc.i4.0
0x47b68  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47b6d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47b72  ldarg.1
0x47b73  ldstr    aIsimpersonatin// "IsImpersonating"
0x47b78  ldarg.0
0x47b79  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebErrorEvent::get_ThreadInformation()
0x47b7e  callvirt instance bool System.Web.Management.WebThreadInformation::get_IsImpersonating()
0x47b83  stloc.0
0x47b84  ldloca.s 0
0x47b86  call     instance string [mscorlib]System.Boolean::ToString()
0x47b8b  ldc.i4.2
0x47b8c  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47b91  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47b96  ret
```
