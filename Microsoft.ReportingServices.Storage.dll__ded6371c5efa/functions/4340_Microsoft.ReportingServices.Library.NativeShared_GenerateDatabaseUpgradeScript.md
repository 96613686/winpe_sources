# Microsoft.ReportingServices.Library.NativeShared::GenerateDatabaseUpgradeScript

- ea: `0x4340`
- end: `0x4374`
- name: `Microsoft.ReportingServices.Library.NativeShared::GenerateDatabaseUpgradeScript`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x4320`
- `0x4330`
- `0x4340`

## string_xrefs

- `0x4356`: `ReportingServicesWMIProvider.DLL`

## pseudocode

```c

```

## disassembly

```asm
0x4340  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x4345  ldsfld   native int Microsoft.ReportingServices.Library.NativeShared::libraryHandle
0x434a  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x434f  brfalse.s loc_436A
0x4351  call     string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::get_SqlSharedCodeDirectory()
0x4356  ldstr    aReportingservi// "ReportingServicesWMIProvider.DLL"
0x435b  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x4360  call     native int Microsoft.ReportingServices.Library.NativeShared::NativeLoadLibrary(string libname)
0x4365  stsfld   native int Microsoft.ReportingServices.Library.NativeShared::libraryHandle
0x436a  ldarg.0
0x436b  ldarg.1
0x436c  ldarg.2
0x436d  ldarg.3
0x436e  call     int32 Microsoft.ReportingServices.Library.NativeShared::__GenerateDatabaseAnyUpgradeScript(string dbCurrentVersion, string dbDesiredVersion, string dbName, [out] string& upgradeScript)
0x4373  ret
```
