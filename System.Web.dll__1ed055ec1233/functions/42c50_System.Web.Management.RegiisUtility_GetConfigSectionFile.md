# System.Web.Management.RegiisUtility::GetConfigSectionFile

- ea: `0x42c50`
- end: `0x42d23`
- name: `System.Web.Management.RegiisUtility::GetConfigSectionFile`
- size: `211`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x42bd0`
- `0x42c10`

## callees

- `0x34f20`
- `0x42c50`
- `0x15ad60`
- `0x15af70`
- `0x15b1c0`
- `0x15b270`
- `0x15c3e0`

## string_xrefs

- `0x42c83`: `Configuration_for_physical_path_not_found`
- `0x42cff`: `Configuration_for_physical_path_not_found`

## pseudocode

```c

```

## disassembly

```asm
0x42c50  ldarg.2
0x42c51  ldstr    asc_1B2EDA// "."
0x42c56  call     bool [mscorlib]System.String::op_Equality(string, string)
0x42c5b  brfalse.s loc_42C66
0x42c5d  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x42c62  starg.s  2
0x42c64  br.s     loc_42C9D
0x42c66  ldarg.2
0x42c67  call     bool [mscorlib]System.IO.Path::IsPathRooted(string)
0x42c6c  brtrue.s loc_42C7B
0x42c6e  call     string [mscorlib]System.Environment::get_CurrentDirectory()
0x42c73  ldarg.2
0x42c74  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x42c79  starg.s  2
0x42c7b  ldarg.2
0x42c7c  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x42c81  brtrue.s loc_42C9D
0x42c83  ldstr    aConfigurationF// "Configuration_for_physical_path_not_fou"...
0x42c88  ldc.i4.1
0x42c89  newarr   [mscorlib]System.Object
0x42c8e  dup
0x42c8f  ldc.i4.0
0x42c90  ldarg.2
0x42c91  stelem.ref
0x42c92  call     string System.Web.SR::GetString(string name, object[] args)
0x42c97  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x42c9c  throw
0x42c9d  newobj   instance void System.Web.Configuration.WebConfigurationFileMap::.ctor()
0x42ca2  stloc.0
0x42ca3  ldarg.2
0x42ca4  ldc.i4.s 0x5C
0x42ca6  ldc.i4.s 0x2F
0x42ca8  callvirt instance string [mscorlib]System.String::Replace(char, char)
0x42cad  stloc.1
0x42cae  ldloc.1
0x42caf  callvirt instance int32 [mscorlib]System.String::get_Length()
0x42cb4  ldc.i4.2
0x42cb5  ble.s    loc_42CCC
0x42cb7  ldloc.1
0x42cb8  ldc.i4.1
0x42cb9  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x42cbe  ldc.i4.s 0x3A
0x42cc0  bne.un.s loc_42CCC
0x42cc2  ldloc.1
0x42cc3  ldc.i4.2
0x42cc4  callvirt instance string [mscorlib]System.String::Substring(int32)
0x42cc9  stloc.1
0x42cca  br.s     loc_42CE0
0x42ccc  ldloc.1
0x42ccd  ldstr    asc_1B7332// "//"
0x42cd2  ldc.i4.4
0x42cd3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x42cd8  brfalse.s loc_42CE0
0x42cda  ldstr    asc_1B2C3C// "/"
0x42cdf  stloc.1
0x42ce0  ldloc.0
0x42ce1  callvirt instance class System.Web.Configuration.VirtualDirectoryMappingCollection System.Web.Configuration.WebConfigurationFileMap::get_VirtualDirectories()
0x42ce6  ldloc.1
0x42ce7  ldarg.2
0x42ce8  ldc.i4.1
0x42ce9  newobj   instance void System.Web.Configuration.VirtualDirectoryMapping::.ctor(string physicalDirectory, bool isAppRoot)
0x42cee  callvirt instance void System.Web.Configuration.VirtualDirectoryMappingCollection::Add(string virtualDirectory, class System.Web.Configuration.VirtualDirectoryMapping mapping)
0x42cf3  ldarg.3
0x42cf4  ldloc.0
0x42cf5  ldloc.1
0x42cf6  call     class [System.Configuration]System.Configuration.Configuration System.Web.Configuration.WebConfigurationManager::OpenMappedWebConfiguration(class System.Web.Configuration.WebConfigurationFileMap fileMap, string path)
0x42cfb  stind.ref
0x42cfc  leave.s  loc_42D1A
0x42cfe  stloc.2
0x42cff  ldstr    aConfigurationF// "Configuration_for_physical_path_not_fou"...
0x42d04  ldc.i4.1
0x42d05  newarr   [mscorlib]System.Object
0x42d0a  dup
0x42d0b  ldc.i4.0
0x42d0c  ldarg.2
0x42d0d  stelem.ref
0x42d0e  call     string System.Web.SR::GetString(string name, object[] args)
0x42d13  ldloc.2
0x42d14  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x42d19  throw
0x42d1a  ldarg.3
0x42d1b  ldind.ref
0x42d1c  ldarg.1
0x42d1d  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x42d22  ret
```
