# System.Windows.Media.ColorContext::Initialize

- ea: `0x77df0`
- end: `0x77ec4`
- name: `System.Windows.Media.ColorContext::Initialize`
- size: `212`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x77900`
- `0x77910`

## callees

- `0x77df0`
- `0x77f40`
- `0x10b350`
- `0x146e40`
- `0x146e70`

## string_xrefs

- `0x77dfb`: `profileUri`
- `0x77e18`: `profileUri`
- `0x77e0e`: `UriNotAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x77df0  ldc.i4.0
0x77df1  stloc.1
0x77df2  ldarg.1
0x77df3  ldnull
0x77df4  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x77df9  brfalse.s loc_77E06
0x77dfb  ldstr    aProfileuri// "profileUri"
0x77e00  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x77e05  throw
0x77e06  ldarg.1
0x77e07  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x77e0c  brtrue.s loc_77E23
0x77e0e  ldstr    aUrinotabsolute// "UriNotAbsolute"
0x77e13  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x77e18  ldstr    aProfileuri// "profileUri"
0x77e1d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x77e22  throw
0x77e23  ldarg.0
0x77e24  ldarg.1
0x77e25  newobj   instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [System]System.Uri>::.ctor(var<u1>)
0x77e2a  stfld    valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<class [System]System.Uri> System.Windows.Media.ColorContext::_profileUri
0x77e2f  ldarg.0
0x77e30  ldarg.2
0x77e31  newobj   instance void valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<bool>::.ctor(var<u1>)
0x77e36  stfld    valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<bool> System.Windows.Media.ColorContext::_isProfileUriNotFromUser
0x77e3b  ldnull
0x77e3c  stloc.0
0x77e3d  ldarg.1
0x77e3e  call     class [mscorlib]System.IO.Stream MS.Internal.WpfWebRequestHelper::CreateRequestAndGetResponseStream(class [System]System.Uri uri)
0x77e43  stloc.0
0x77e44  leave.s  loc_77E4E
0x77e46  pop
0x77e47  ldarg.2
0x77e48  brfalse.s loc_77E4C
0x77e4a  ldc.i4.1
0x77e4b  stloc.1
0x77e4c  leave.s  loc_77E4E
0x77e4e  ldloc.0
0x77e4f  brtrue.s loc_77EB6
0x77e51  ldloc.1
0x77e52  brfalse.s loc_77E88
0x77e54  ldsfld   string System.Windows.Media.ColorContext::_colorProfileResources
0x77e59  ldtoken  System.Windows.Media.ColorContext
0x77e5e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x77e63  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetAssembly(class [mscorlib]System.Type)
0x77e68  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x77e6d  stloc.3
0x77e6e  ldloc.3
0x77e6f  ldsfld   string System.Windows.Media.ColorContext::_sRGBProfileName
0x77e74  callvirt instance object [mscorlib]System.Resources.ResourceManager::GetObject(string)
0x77e79  castclass unsigned int8[]
0x77e7e  stloc.2
0x77e7f  ldloc.2
0x77e80  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x77e85  stloc.0
0x77e86  br.s     loc_77EB6
0x77e88  ldarg.2
0x77e89  ldc.i4.0
0x77e8a  ceq
0x77e8c  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0x77e91  ldstr    aFilenotfoundex// "FileNotFoundExceptionWithFileName"
0x77e96  ldc.i4.1
0x77e97  newarr   [mscorlib]System.Object
0x77e9c  dup
0x77e9d  ldc.i4.0
0x77e9e  ldarg.1
0x77e9f  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x77ea4  stelem.ref
0x77ea5  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x77eaa  ldarg.1
0x77eab  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x77eb0  newobj   instance void [mscorlib]System.IO.FileNotFoundException::.ctor(string, string)
0x77eb5  throw
0x77eb6  ldarg.0
0x77eb7  ldloc.0
0x77eb8  ldarg.1
0x77eb9  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x77ebe  call     instance void System.Windows.Media.ColorContext::FromStream(class [mscorlib]System.IO.Stream stm, string filename)
0x77ec3  ret
```
