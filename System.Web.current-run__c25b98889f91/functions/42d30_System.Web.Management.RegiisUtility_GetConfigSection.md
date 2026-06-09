# System.Web.Management.RegiisUtility::GetConfigSection

- ea: `0x42d30`
- end: `0x42db9`
- name: `System.Web.Management.RegiisUtility::GetConfigSection`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x42b40`
- `0x42b90`

## callees

- `0x34f20`
- `0x34fa0`
- `0x42d30`
- `0x15c280`
- `0x15c370`

## string_xrefs

- `0x42d6b`: `Configuration_for_machine_config_not_found`
- `0x42d7c`: `Configuration_for_path_not_found`

## pseudocode

```c

```

## disassembly

```asm
0x42d30  ldarg.2
0x42d31  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42d36  brfalse.s loc_42D3B
0x42d38  ldnull
0x42d39  starg.s  2
0x42d3b  ldarg.s  4
0x42d3d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42d42  brfalse.s loc_42D47
0x42d44  ldnull
0x42d45  starg.s  4
0x42d47  nop
0x42d48  ldarg.s  5
0x42d4a  brfalse.s loc_42D58
0x42d4c  ldarg.s  6
0x42d4e  ldarg.s  4
0x42d50  call     class [System.Configuration]System.Configuration.Configuration System.Web.Configuration.WebConfigurationManager::OpenMachineConfiguration(string locationSubPath)
0x42d55  stind.ref
0x42d56  br.s     loc_42D64
0x42d58  ldarg.s  6
0x42d5a  ldarg.2
0x42d5b  ldarg.3
0x42d5c  ldarg.s  4
0x42d5e  call     class [System.Configuration]System.Configuration.Configuration System.Web.Configuration.WebConfigurationManager::OpenWebConfiguration(string path, string site, string locationSubPath)
0x42d63  stind.ref
0x42d64  leave.s  loc_42DAF
0x42d66  stloc.0
0x42d67  ldarg.s  5
0x42d69  brfalse.s loc_42D7C
0x42d6b  ldstr    aConfigurationF_0// "Configuration_for_machine_config_not_fo"...
0x42d70  call     string System.Web.SR::GetString(string name)
0x42d75  ldloc.0
0x42d76  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x42d7b  throw
0x42d7c  ldstr    aConfigurationF_1// "Configuration_for_path_not_found"
0x42d81  ldc.i4.2
0x42d82  newarr   [mscorlib]System.Object
0x42d87  dup
0x42d88  ldc.i4.0
0x42d89  ldarg.2
0x42d8a  stelem.ref
0x42d8b  dup
0x42d8c  ldc.i4.1
0x42d8d  ldarg.3
0x42d8e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x42d93  brtrue.s loc_42D98
0x42d95  ldarg.3
0x42d96  br.s     loc_42DA2
0x42d98  ldstr    aDefaultsitenam// "DefaultSiteName"
0x42d9d  call     string System.Web.SR::GetString(string name)
0x42da2  stelem.ref
0x42da3  call     string System.Web.SR::GetString(string name, object[] args)
0x42da8  ldloc.0
0x42da9  newobj   instance void [mscorlib]System.Exception::.ctor(string, class [mscorlib]System.Exception)
0x42dae  throw
0x42daf  ldarg.s  6
0x42db1  ldind.ref
0x42db2  ldarg.1
0x42db3  callvirt instance class [System.Configuration]System.Configuration.ConfigurationSection [System.Configuration]System.Configuration.Configuration::GetSection(string)
0x42db8  ret
```
