# System.Web.FileChangesMonitor::CreateFileMonitoringException

- ea: `0xd220`
- end: `0xd2dc`
- name: `System.Web.FileChangesMonitor::CreateFileMonitoringException`
- size: `188`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0xc560`
- `0xc920`
- `0xd2e0`
- `0xd4b0`
- `0xd640`
- `0xd7b0`
- `0xdf50`

## callees

- `0xd220`
- `0x189b0`
- `0x241d0`
- `0x24660`
- `0x30d70`
- `0x34f20`

## string_xrefs

- `0xd250`: `Directory_does_not_exist_for_monitoring`
- `0xd258`: `Access_denied_for_monitoring`
- `0xd26a`: `NetBios_command_limit_reached`
- `0xd297`: `App_Virtual_Path`

## pseudocode

```c

```

## disassembly

```asm
0xd220  ldc.i4.0
0xd221  stloc.1
0xd222  ldarg.0
0xd223  ldc.i4   0x80070005
0xd228  bgt.s    loc_D23E
0xd22a  ldarg.0
0xd22b  ldc.i4   0x80070002
0xd230  sub
0xd231  ldc.i4.1
0xd232  ble.un.s loc_D250
0xd234  ldarg.0
0xd235  ldc.i4   0x80070005
0xd23a  beq.s    loc_D258
0xd23c  br.s     loc_D274
0xd23e  ldarg.0
0xd23f  ldc.i4   0x80070038
0xd244  beq.s    loc_D26A
0xd246  ldarg.0
0xd247  ldc.i4   0x80070057
0xd24c  beq.s    loc_D262
0xd24e  br.s     loc_D274
0xd250  ldstr    aDirectoryDoesN// "Directory_does_not_exist_for_monitoring"
0xd255  stloc.0
0xd256  br.s     loc_D27A
0xd258  ldstr    aAccessDeniedFo// "Access_denied_for_monitoring"
0xd25d  stloc.0
0xd25e  ldc.i4.1
0xd25f  stloc.1
0xd260  br.s     loc_D27A
0xd262  ldstr    aInvalidFileNam// "Invalid_file_name_for_monitoring"
0xd267  stloc.0
0xd268  br.s     loc_D27A
0xd26a  ldstr    aNetbiosCommand// "NetBios_command_limit_reached"
0xd26f  stloc.0
0xd270  ldc.i4.1
0xd271  stloc.1
0xd272  br.s     loc_D27A
0xd274  ldstr    aFailedToStartM// "Failed_to_start_monitoring"
0xd279  stloc.0
0xd27a  ldloc.1
0xd27b  brfalse.s loc_D2C0
0xd27d  ldloc.0
0xd27e  ldc.i4.1
0xd27f  newarr   [mscorlib]System.Object
0xd284  dup
0xd285  ldc.i4.0
0xd286  ldarg.1
0xd287  call     string System.Web.HttpRuntime::GetSafePath(string path)
0xd28c  stelem.ref
0xd28d  call     string System.Web.SR::GetString(string name, object[] args)
0xd292  ldstr    asc_1B3DC2// "\n\r"
0xd297  ldstr    aAppVirtualPath// "App_Virtual_Path"
0xd29c  ldc.i4.1
0xd29d  newarr   [mscorlib]System.Object
0xd2a2  dup
0xd2a3  ldc.i4.0
0xd2a4  call     string System.Web.HttpRuntime::get_AppDomainAppVirtualPath()
0xd2a9  stelem.ref
0xd2aa  call     string System.Web.SR::GetString(string name, object[] args)
0xd2af  call     string [mscorlib]System.String::Concat(string, string, string)
0xd2b4  ldarg.1
0xd2b5  call     string System.Web.HttpRuntime::get_AppDomainAppVirtualPath()
0xd2ba  ldarg.0
0xd2bb  call     void System.Web.UnsafeNativeMethods::RaiseFileMonitoringEventlogEvent(string eventInfo, string path, string appVirtualPath, int32 hr)
0xd2c0  ldloc.0
0xd2c1  ldc.i4.1
0xd2c2  newarr   [mscorlib]System.Object
0xd2c7  dup
0xd2c8  ldc.i4.0
0xd2c9  ldarg.1
0xd2ca  call     string System.Web.HttpRuntime::GetSafePath(string path)
0xd2cf  stelem.ref
0xd2d0  call     string System.Web.SR::GetString(string name, object[] args)
0xd2d5  ldarg.0
0xd2d6  newobj   instance void System.Web.HttpException::.ctor(string message, int32 hr)
0xd2db  ret
```
