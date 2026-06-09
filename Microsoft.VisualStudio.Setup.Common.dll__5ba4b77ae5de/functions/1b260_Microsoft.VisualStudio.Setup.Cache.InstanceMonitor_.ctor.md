# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::.ctor

- ea: `0x1b260`
- end: `0x1b2b2`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::.ctor`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0xc1a0`

## string_xrefs

- `0x1b267`: `services`

## pseudocode

```c

```

## disassembly

```asm
0x1b260  ldarg.0
0x1b261  call     instance void [mscorlib]System.Object::.ctor()
0x1b266  ldarg.1
0x1b267  ldstr    aServices// "services"
0x1b26c  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1b271  ldarg.2
0x1b272  ldstr    aInstance// "instance"
0x1b277  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1b27c  ldarg.0
0x1b27d  ldarg.1
0x1b27e  stfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::services
0x1b283  ldarg.0
0x1b284  ldarg.2
0x1b285  stfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b28a  ldarg.0
0x1b28b  ldarg.1
0x1b28c  ldc.i4.1
0x1b28d  call     T0x2B00003E
0x1b292  stfld    class Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::fileSystem
0x1b297  ldarg.0
0x1b298  ldarg.1
0x1b299  ldc.i4.0
0x1b29a  call     T0x2B00003F
0x1b29f  stfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::logger
0x1b2a4  ldarg.0
0x1b2a5  ldarg.1
0x1b2a6  ldc.i4.0
0x1b2a7  call     T0x2B0000D1
0x1b2ac  stfld    class Microsoft.VisualStudio.Setup.Services.IRestartManager Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::restartManager
0x1b2b1  ret
```
