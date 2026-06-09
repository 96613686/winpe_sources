# Microsoft.ReportingServices.Diagnostics.SqlInstallation::get_SqlSharedCodeDirectory

- ea: `0xa00`
- end: `0xa53`
- name: `Microsoft.ReportingServices.Diagnostics.SqlInstallation::get_SqlSharedCodeDirectory`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x10aa0`

## callees

- `0xa00`
- `0x10150`

## string_xrefs

- `0xa14`: `Installation Error: Could not find `
- `0xa1a`: ` registry key.`
- `0xa42`: ` registry key.`
- `0xa3c`: `Installation Error: Could not find SharedCode on `

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0xa05  stloc.0
0xa06  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0xa0b  ldloc.0
0xa0c  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0xa11  dup
0xa12  brtrue.s loc_A2A
0xa14  ldstr    aInstallationEr// "Installation Error: Could not find "
0xa19  ldloc.0
0xa1a  ldstr    aRegistryKey// " registry key."
0xa1f  call     string [mscorlib]System.String::Concat(string, string, string)
0xa24  newobj   instance void ConfigurationErrorException::.ctor(string message)
0xa29  throw
0xa2a  ldstr    aSharedcode// "SharedCode"
0xa2f  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0xa34  castclass [mscorlib]System.String
0xa39  dup
0xa3a  brtrue.s loc_A52
0xa3c  ldstr    aInstallationEr_0// "Installation Error: Could not find Shar"...
0xa41  ldloc.0
0xa42  ldstr    aRegistryKey// " registry key."
0xa47  call     string [mscorlib]System.String::Concat(string, string, string)
0xa4c  newobj   instance void ConfigurationErrorException::.ctor(string message)
0xa51  throw
0xa52  ret
```
