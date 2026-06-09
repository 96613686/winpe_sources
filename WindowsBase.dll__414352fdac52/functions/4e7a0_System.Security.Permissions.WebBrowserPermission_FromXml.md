# System.Security.Permissions.WebBrowserPermission::FromXml

- ea: `0x4e7a0`
- end: `0x4e84c`
- name: `System.Security.Permissions.WebBrowserPermission::FromXml`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2c130`
- `0x4e7a0`

## string_xrefs

- `0x4e7a3`: `securityElement`
- `0x4e7d2`: `securityElement`
- `0x4e82e`: `BadXml`

## pseudocode

```c

```

## disassembly

```asm
0x4e7a0  ldarg.1
0x4e7a1  brtrue.s loc_4E7AE
0x4e7a3  ldstr    aSecurityelemen// "securityElement"
0x4e7a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4e7ad  throw
0x4e7ae  ldarg.1
0x4e7af  ldstr    aClass// "class"
0x4e7b4  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4e7b9  stloc.0
0x4e7ba  ldloc.0
0x4e7bb  brfalse.s loc_4E7D2
0x4e7bd  ldloc.0
0x4e7be  ldarg.0
0x4e7bf  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4e7c4  callvirt instance string [mscorlib]System.Type::get_FullName()
0x4e7c9  ldc.i4.4
0x4e7ca  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4e7cf  ldc.i4.m1
0x4e7d0  bne.un.s loc_4E7DD
0x4e7d2  ldstr    aSecurityelemen// "securityElement"
0x4e7d7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4e7dc  throw
0x4e7dd  ldarg.1
0x4e7de  ldstr    aUnrestricted// "Unrestricted"
0x4e7e3  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4e7e8  stloc.1
0x4e7e9  ldloc.1
0x4e7ea  brfalse.s loc_4E7FC
0x4e7ec  ldloc.1
0x4e7ed  call     bool [mscorlib]System.Boolean::Parse(string)
0x4e7f2  brfalse.s loc_4E7FC
0x4e7f4  ldarg.0
0x4e7f5  ldc.i4.2
0x4e7f6  stfld    valuetype System.Security.Permissions.WebBrowserPermissionLevel System.Security.Permissions.WebBrowserPermission::_webBrowserPermissionLevel
0x4e7fb  ret
0x4e7fc  ldarg.0
0x4e7fd  ldc.i4.0
0x4e7fe  stfld    valuetype System.Security.Permissions.WebBrowserPermissionLevel System.Security.Permissions.WebBrowserPermission::_webBrowserPermissionLevel
0x4e803  ldarg.1
0x4e804  ldstr    aLevel// "Level"
0x4e809  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4e80e  stloc.2
0x4e80f  ldloc.2
0x4e810  brfalse.s loc_4E82E
0x4e812  ldarg.0
0x4e813  ldtoken  System.Security.Permissions.WebBrowserPermissionLevel
0x4e818  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4e81d  ldloc.2
0x4e81e  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4e823  unbox.any System.Security.Permissions.WebBrowserPermissionLevel
0x4e828  stfld    valuetype System.Security.Permissions.WebBrowserPermissionLevel System.Security.Permissions.WebBrowserPermission::_webBrowserPermissionLevel
0x4e82d  ret
0x4e82e  ldstr    aBadxml// "BadXml"
0x4e833  ldc.i4.1
0x4e834  newarr   [mscorlib]System.Object
0x4e839  dup
0x4e83a  ldc.i4.0
0x4e83b  ldstr    aLevel_0// "level"
0x4e840  stelem.ref
0x4e841  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4e846  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4e84b  throw
```
