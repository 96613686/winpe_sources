# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::.ctor

- ea: `0x3530`
- end: `0x35c6`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::.ctor`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd960`

## callees

- `0x3530`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldarg.0
0x3531  call     instance void [mscorlib]System.Object::.ctor()
0x3536  ldarg.2
0x3537  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x353c  stloc.0
0x353d  ldarg.2
0x353e  brfalse.s loc_3550
0x3540  ldloc.0
0x3541  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x3546  brfalse.s loc_3550
0x3548  ldloc.0
0x3549  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x354e  brtrue.s loc_3561
0x3550  ldstr    aCanTWorkWithMi// "Can't work with missing or empty upload"...
0x3555  ldloc.0
0x3556  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x355b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x3560  throw
0x3561  ldarg.1
0x3562  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x3567  stloc.1
0x3568  ldloc.1
0x3569  brfalse.s loc_357B
0x356b  ldloc.1
0x356c  callvirt instance bool [mscorlib]System.IO.FileSystemInfo::get_Exists()
0x3571  brfalse.s loc_357B
0x3573  ldloc.1
0x3574  callvirt instance int64 [mscorlib]System.IO.FileInfo::get_Length()
0x3579  brtrue.s loc_358C
0x357b  ldstr    aCanTWorkWithMi// "Can't work with missing or empty upload"...
0x3580  ldloc.0
0x3581  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3586  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x358b  throw
0x358c  ldarg.0
0x358d  ldloc.1
0x358e  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3593  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::.ctor(string)
0x3598  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::_original
0x359d  ldarg.0
0x359e  ldloc.0
0x359f  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x35a4  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::.ctor(string)
0x35a9  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::_pbix
0x35ae  ldarg.0
0x35af  ldarg.3
0x35b0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x35b5  brtrue.s loc_35BF
0x35b7  ldarg.3
0x35b8  newobj   instance void [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete::.ctor(string)
0x35bd  br.s     loc_35C0
0x35bf  ldnull
0x35c0  stfld    class [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.ScopedFileDelete Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PreShreddedPbixFiles::_model
0x35c5  ret
```
