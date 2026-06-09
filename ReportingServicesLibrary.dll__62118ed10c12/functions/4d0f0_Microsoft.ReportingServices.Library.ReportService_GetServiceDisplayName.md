# Microsoft.ReportingServices.Library.ReportService::GetServiceDisplayName

- ea: `0x4d0f0`
- end: `0x4d1a6`
- name: `Microsoft.ReportingServices.Library.ReportService::GetServiceDisplayName`
- size: `182`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4cdb0`

## callees

- `0x4d0f0`

## string_xrefs

- `0x4d105`: `SYSTEM\CurrentControlSet\Services`
- `0x4d12c`: `ImagePath`
- `0x4d19d`: `SQL Server Reporting Services`

## pseudocode

```c

```

## disassembly

```asm
0x4d0f0  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0x4d0f5  callvirt instance class [System]System.Diagnostics.ProcessModule [System]System.Diagnostics.Process::get_MainModule()
0x4d0fa  callvirt instance string [System]System.Diagnostics.ProcessModule::get_FileName()
0x4d0ff  stloc.0
0x4d100  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x4d105  ldstr    aSystemCurrentc// "SYSTEM\\CurrentControlSet\\Services"
0x4d10a  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4d10f  stloc.1
0x4d110  ldloc.1
0x4d111  callvirt instance string[] [mscorlib]Microsoft.Win32.RegistryKey::GetSubKeyNames()
0x4d116  stloc.2
0x4d117  ldc.i4.0
0x4d118  stloc.3
0x4d119  br.s     loc_4D186
0x4d11b  ldloc.2
0x4d11c  ldloc.3
0x4d11d  ldelem.ref
0x4d11e  stloc.s  4
0x4d120  ldloc.1
0x4d121  ldloc.s  4
0x4d123  callvirt instance class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.RegistryKey::OpenSubKey(string)
0x4d128  stloc.s  5
0x4d12a  ldloc.s  5
0x4d12c  ldstr    aImagepath// "ImagePath"
0x4d131  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x4d136  stloc.s  6
0x4d138  ldloc.s  6
0x4d13a  brfalse.s loc_4D174
0x4d13c  ldloc.s  6
0x4d13e  isinst   [mscorlib]System.String
0x4d143  stloc.s  7
0x4d145  ldloc.s  7
0x4d147  brfalse.s loc_4D174
0x4d149  ldloc.s  7
0x4d14b  ldloc.0
0x4d14c  callvirt instance bool [mscorlib]System.String::Contains(string)
0x4d151  brfalse.s loc_4D174
0x4d153  ldloc.s  5
0x4d155  ldstr    aDisplayname// "DisplayName"
0x4d15a  callvirt instance object [mscorlib]Microsoft.Win32.RegistryKey::GetValue(string)
0x4d15f  castclass [mscorlib]System.String
0x4d164  stloc.s  8
0x4d166  ldloc.s  8
0x4d168  brtrue.s loc_4D16E
0x4d16a  ldloc.s  4
0x4d16c  stloc.s  8
0x4d16e  ldloc.s  8
0x4d170  stloc.s  9
0x4d172  leave.s  loc_4D1A3
0x4d174  leave.s  loc_4D182
0x4d176  ldloc.s  5
0x4d178  brfalse.s loc_4D181
0x4d17a  ldloc.s  5
0x4d17c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d181  endfinally
0x4d182  ldloc.3
0x4d183  ldc.i4.1
0x4d184  add
0x4d185  stloc.3
0x4d186  ldloc.3
0x4d187  ldloc.2
0x4d188  ldlen
0x4d189  conv.i4
0x4d18a  blt.s    loc_4D11B
0x4d18c  leave.s  loc_4D198
0x4d18e  ldloc.1
0x4d18f  brfalse.s loc_4D197
0x4d191  ldloc.1
0x4d192  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d197  endfinally
0x4d198  leave.s  loc_4D19D
0x4d19a  pop
0x4d19b  leave.s  loc_4D19D
0x4d19d  ldstr    aSqlServerRepor// "SQL Server Reporting Services"
0x4d1a2  ret
0x4d1a3  ldloc.s  9
0x4d1a5  ret
```
