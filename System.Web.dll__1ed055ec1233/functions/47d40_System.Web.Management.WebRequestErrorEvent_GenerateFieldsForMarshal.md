# System.Web.Management.WebRequestErrorEvent::GenerateFieldsForMarshal

- ea: `0x47d40`
- end: `0x47eb7`
- name: `System.Web.Management.WebRequestErrorEvent::GenerateFieldsForMarshal`
- size: `375`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x45fc0`
- `0x47830`
- `0x47c70`
- `0x47ca0`
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

- `0x47d64`: `RequestPath`
- `0x47e16`: `RequestThreadAccountName`
- `0x47e32`: `ThreadID`
- `0x47e5b`: `ThreadAccountName`
- `0x47e93`: `IsImpersonating`

## pseudocode

```c

```

## disassembly

```asm
0x47d40  ldarg.0
0x47d41  ldarg.1
0x47d42  call     instance void System.Web.Management.WebBaseErrorEvent::GenerateFieldsForMarshal(class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData> fields)
0x47d47  ldarg.1
0x47d48  ldstr    aRequesturl_0// "RequestUrl"
0x47d4d  ldarg.0
0x47d4e  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47d53  callvirt instance string System.Web.Management.WebRequestInformation::get_RequestUrl()
0x47d58  ldc.i4.0
0x47d59  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47d5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47d63  ldarg.1
0x47d64  ldstr    aRequestpath// "RequestPath"
0x47d69  ldarg.0
0x47d6a  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47d6f  callvirt instance string System.Web.Management.WebRequestInformation::get_RequestPath()
0x47d74  ldc.i4.0
0x47d75  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47d7a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47d7f  ldarg.1
0x47d80  ldstr    aUserhostaddres// "UserHostAddress"
0x47d85  ldarg.0
0x47d86  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47d8b  callvirt instance string System.Web.Management.WebRequestInformation::get_UserHostAddress()
0x47d90  ldc.i4.0
0x47d91  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47d96  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47d9b  ldarg.1
0x47d9c  ldstr    aUsername// "UserName"
0x47da1  ldarg.0
0x47da2  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47da7  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47dac  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47db1  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x47db6  ldc.i4.0
0x47db7  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47dbc  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47dc1  ldarg.1
0x47dc2  ldstr    aUserauthentica// "UserAuthenticated"
0x47dc7  ldarg.0
0x47dc8  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47dcd  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47dd2  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47dd7  callvirt instance bool [mscorlib]System.Security.Principal.IIdentity::get_IsAuthenticated()
0x47ddc  stloc.0
0x47ddd  ldloca.s 0
0x47ddf  call     instance string [mscorlib]System.Boolean::ToString()
0x47de4  ldc.i4.2
0x47de5  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47dea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47def  ldarg.1
0x47df0  ldstr    aUserauthentica_0// "UserAuthenticationType"
0x47df5  ldarg.0
0x47df6  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47dfb  callvirt instance class [mscorlib]System.Security.Principal.IPrincipal System.Web.Management.WebRequestInformation::get_Principal()
0x47e00  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x47e05  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_AuthenticationType()
0x47e0a  ldc.i4.0
0x47e0b  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47e10  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47e15  ldarg.1
0x47e16  ldstr    aRequestthreada// "RequestThreadAccountName"
0x47e1b  ldarg.0
0x47e1c  call     instance class System.Web.Management.WebRequestInformation System.Web.Management.WebRequestErrorEvent::get_RequestInformation()
0x47e21  callvirt instance string System.Web.Management.WebRequestInformation::get_ThreadAccountName()
0x47e26  ldc.i4.0
0x47e27  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47e2c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47e31  ldarg.1
0x47e32  ldstr    aThreadid_0// "ThreadID"
0x47e37  ldarg.0
0x47e38  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebRequestErrorEvent::get_ThreadInformation()
0x47e3d  callvirt instance int32 System.Web.Management.WebThreadInformation::get_ThreadID()
0x47e42  stloc.1
0x47e43  ldloca.s 1
0x47e45  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InstalledUICulture()
0x47e4a  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x47e4f  ldc.i4.1
0x47e50  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47e55  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47e5a  ldarg.1
0x47e5b  ldstr    aThreadaccountn// "ThreadAccountName"
0x47e60  ldarg.0
0x47e61  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebRequestErrorEvent::get_ThreadInformation()
0x47e66  callvirt instance string System.Web.Management.WebThreadInformation::get_ThreadAccountName()
0x47e6b  ldc.i4.0
0x47e6c  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47e71  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47e76  ldarg.1
0x47e77  ldstr    aStacktrace// "StackTrace"
0x47e7c  ldarg.0
0x47e7d  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebRequestErrorEvent::get_ThreadInformation()
0x47e82  callvirt instance string System.Web.Management.WebThreadInformation::get_StackTrace()
0x47e87  ldc.i4.0
0x47e88  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47e8d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47e92  ldarg.1
0x47e93  ldstr    aIsimpersonatin// "IsImpersonating"
0x47e98  ldarg.0
0x47e99  call     instance class System.Web.Management.WebThreadInformation System.Web.Management.WebRequestErrorEvent::get_ThreadInformation()
0x47e9e  callvirt instance bool System.Web.Management.WebThreadInformation::get_IsImpersonating()
0x47ea3  stloc.0
0x47ea4  ldloca.s 0
0x47ea6  call     instance string [mscorlib]System.Boolean::ToString()
0x47eab  ldc.i4.2
0x47eac  newobj   instance void System.Web.Management.WebEventFieldData::.ctor(string name, string data, valuetype System.Web.Management.WebEventFieldType type)
0x47eb1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class System.Web.Management.WebEventFieldData>::Add(var<u1>)
0x47eb6  ret
```
