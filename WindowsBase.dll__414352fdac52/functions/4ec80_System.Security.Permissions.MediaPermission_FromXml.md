# System.Security.Permissions.MediaPermission::FromXml

- ea: `0x4ec80`
- end: `0x4edd0`
- name: `System.Security.Permissions.MediaPermission::FromXml`
- size: `336`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2c130`
- `0x4ec80`
- `0x4ee60`

## string_xrefs

- `0x4ec83`: `securityElement`
- `0x4ecb2`: `securityElement`
- `0x4ed1c`: `BadXml`
- `0x4ed66`: `BadXml`
- `0x4edb2`: `BadXml`

## pseudocode

```c

```

## disassembly

```asm
0x4ec80  ldarg.1
0x4ec81  brtrue.s loc_4EC8E
0x4ec83  ldstr    aSecurityelemen// "securityElement"
0x4ec88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4ec8d  throw
0x4ec8e  ldarg.1
0x4ec8f  ldstr    aClass// "class"
0x4ec94  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4ec99  stloc.0
0x4ec9a  ldloc.0
0x4ec9b  brfalse.s loc_4ECB2
0x4ec9d  ldloc.0
0x4ec9e  ldarg.0
0x4ec9f  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x4eca4  callvirt instance string [mscorlib]System.Type::get_FullName()
0x4eca9  ldc.i4.4
0x4ecaa  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x4ecaf  ldc.i4.m1
0x4ecb0  bne.un.s loc_4ECBD
0x4ecb2  ldstr    aSecurityelemen// "securityElement"
0x4ecb7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4ecbc  throw
0x4ecbd  ldarg.1
0x4ecbe  ldstr    aUnrestricted// "Unrestricted"
0x4ecc3  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4ecc8  stloc.1
0x4ecc9  ldloc.1
0x4ecca  brfalse.s loc_4ECEA
0x4eccc  ldloc.1
0x4eccd  call     bool [mscorlib]System.Boolean::Parse(string)
0x4ecd2  brfalse.s loc_4ECEA
0x4ecd4  ldarg.0
0x4ecd5  ldc.i4.3
0x4ecd6  stfld    valuetype System.Security.Permissions.MediaPermissionAudio System.Security.Permissions.MediaPermission::_mediaPermissionAudio
0x4ecdb  ldarg.0
0x4ecdc  ldc.i4.3
0x4ecdd  stfld    valuetype System.Security.Permissions.MediaPermissionVideo System.Security.Permissions.MediaPermission::_mediaPermissionVideo
0x4ece2  ldarg.0
0x4ece3  ldc.i4.3
0x4ece4  stfld    valuetype System.Security.Permissions.MediaPermissionImage System.Security.Permissions.MediaPermission::_mediaPermissionImage
0x4ece9  ret
0x4ecea  ldarg.0
0x4eceb  call     instance void System.Security.Permissions.MediaPermission::InitDefaults()
0x4ecf0  ldarg.1
0x4ecf1  ldstr    aAudio// "Audio"
0x4ecf6  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4ecfb  stloc.2
0x4ecfc  ldloc.2
0x4ecfd  brfalse.s loc_4ED1C
0x4ecff  ldarg.0
0x4ed00  ldtoken  System.Security.Permissions.MediaPermissionAudio
0x4ed05  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ed0a  ldloc.2
0x4ed0b  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4ed10  unbox.any System.Security.Permissions.MediaPermissionAudio
0x4ed15  stfld    valuetype System.Security.Permissions.MediaPermissionAudio System.Security.Permissions.MediaPermission::_mediaPermissionAudio
0x4ed1a  br.s     loc_4ED3A
0x4ed1c  ldstr    aBadxml// "BadXml"
0x4ed21  ldc.i4.1
0x4ed22  newarr   [mscorlib]System.Object
0x4ed27  dup
0x4ed28  ldc.i4.0
0x4ed29  ldstr    aAudio_0// "audio"
0x4ed2e  stelem.ref
0x4ed2f  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4ed34  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ed39  throw
0x4ed3a  ldarg.1
0x4ed3b  ldstr    aVideo// "Video"
0x4ed40  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4ed45  stloc.3
0x4ed46  ldloc.3
0x4ed47  brfalse.s loc_4ED66
0x4ed49  ldarg.0
0x4ed4a  ldtoken  System.Security.Permissions.MediaPermissionVideo
0x4ed4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4ed54  ldloc.3
0x4ed55  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4ed5a  unbox.any System.Security.Permissions.MediaPermissionVideo
0x4ed5f  stfld    valuetype System.Security.Permissions.MediaPermissionVideo System.Security.Permissions.MediaPermission::_mediaPermissionVideo
0x4ed64  br.s     loc_4ED84
0x4ed66  ldstr    aBadxml// "BadXml"
0x4ed6b  ldc.i4.1
0x4ed6c  newarr   [mscorlib]System.Object
0x4ed71  dup
0x4ed72  ldc.i4.0
0x4ed73  ldstr    aVideo_0// "video"
0x4ed78  stelem.ref
0x4ed79  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4ed7e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4ed83  throw
0x4ed84  ldarg.1
0x4ed85  ldstr    aImage// "Image"
0x4ed8a  callvirt instance string [mscorlib]System.Security.SecurityElement::Attribute(string)
0x4ed8f  stloc.s  4
0x4ed91  ldloc.s  4
0x4ed93  brfalse.s loc_4EDB2
0x4ed95  ldarg.0
0x4ed96  ldtoken  System.Security.Permissions.MediaPermissionImage
0x4ed9b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x4eda0  ldloc.s  4
0x4eda2  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x4eda7  unbox.any System.Security.Permissions.MediaPermissionImage
0x4edac  stfld    valuetype System.Security.Permissions.MediaPermissionImage System.Security.Permissions.MediaPermission::_mediaPermissionImage
0x4edb1  ret
0x4edb2  ldstr    aBadxml// "BadXml"
0x4edb7  ldc.i4.1
0x4edb8  newarr   [mscorlib]System.Object
0x4edbd  dup
0x4edbe  ldc.i4.0
0x4edbf  ldstr    aImage_0// "image"
0x4edc4  stelem.ref
0x4edc5  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x4edca  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x4edcf  throw
```
