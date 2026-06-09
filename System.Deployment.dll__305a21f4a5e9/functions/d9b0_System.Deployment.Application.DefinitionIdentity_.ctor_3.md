# System.Deployment.Application.DefinitionIdentity::.ctor_3

- ea: `0xd9b0`
- end: `0xda2b`
- name: `System.Deployment.Application.DefinitionIdentity::.ctor_3`
- size: `123`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x20c0`
- `0x34c0`
- `0xd9b0`
- `0xda40`
- `0x22ed0`

## string_xrefs

- `0xda1a`: `publicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0xd9b0  ldarg.0
0xd9b1  call     instance void [mscorlib]System.Object::.ctor()
0xd9b6  ldarg.0
0xd9b7  call     class System.Deployment.Internal.Isolation.IIdentityAuthority System.Deployment.Internal.Isolation.IsolationInterop::get_IdentityAuthority()
0xd9bc  callvirt instance class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Internal.Isolation.IIdentityAuthority::CreateDefinition()
0xd9c1  stfld    class System.Deployment.Internal.Isolation.IDefinitionIdentity System.Deployment.Application.DefinitionIdentity::_idComPtr
0xd9c6  ldarg.0
0xd9c7  ldstr    aName// "name"
0xd9cc  ldarg.1
0xd9cd  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0xd9d2  call     instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xd9d7  ldarg.0
0xd9d8  ldstr    aVersion_0// "version"
0xd9dd  ldarg.1
0xd9de  callvirt instance class [mscorlib]System.Version [mscorlib]System.Reflection.AssemblyName::get_Version()
0xd9e3  callvirt instance string [mscorlib]System.Object::ToString()
0xd9e8  call     instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xd9ed  ldarg.1
0xd9ee  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Reflection.AssemblyName::get_CultureInfo()
0xd9f3  brfalse.s loc_DA0B
0xd9f5  ldarg.0
0xd9f6  ldstr    aCulture// "culture"
0xd9fb  ldarg.1
0xd9fc  callvirt instance class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Reflection.AssemblyName::get_CultureInfo()
0xda01  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0xda06  call     instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xda0b  ldarg.1
0xda0c  callvirt instance unsigned int8[] [mscorlib]System.Reflection.AssemblyName::GetPublicKeyToken()
0xda11  stloc.0
0xda12  ldloc.0
0xda13  brfalse.s loc_DA2A
0xda15  ldloc.0
0xda16  ldlen
0xda17  brfalse.s loc_DA2A
0xda19  ldarg.0
0xda1a  ldstr    aPublickeytoken// "publicKeyToken"
0xda1f  ldloc.0
0xda20  call     string System.Deployment.Application.HexString::FromBytes(unsigned int8[] bytes)
0xda25  call     instance void System.Deployment.Application.DefinitionIdentity::set_Item(string name, string value)
0xda2a  ret
```
