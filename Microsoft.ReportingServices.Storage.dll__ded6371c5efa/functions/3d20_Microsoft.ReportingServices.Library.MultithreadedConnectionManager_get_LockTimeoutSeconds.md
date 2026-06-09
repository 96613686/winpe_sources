# Microsoft.ReportingServices.Library.MultithreadedConnectionManager::get_LockTimeoutSeconds

- ea: `0x3d20`
- end: `0x3d56`
- name: `Microsoft.ReportingServices.Library.MultithreadedConnectionManager::get_LockTimeoutSeconds`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x3bf0`

## callees

- `0x280`
- `0x2ff0`
- `0x3000`
- `0x3d20`

## pseudocode

```c

```

## disassembly

```asm
0x3d20  ldsfld   int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockTimeoutSeconds
0x3d25  ldc.i4.0
0x3d26  bge.s    loc_3D50
0x3d28  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCleanupTimeoutSeconds()
0x3d2d  call     int32 Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x3d32  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x3d37  stloc.0
0x3d38  ldloc.0
0x3d39  call     int32 Microsoft.ReportingServices.Library.CachedSystemProperties::get_SessionAccessTimeout()
0x3d3e  call     int32 [mscorlib]System.Math::Max(int32, int32)
0x3d43  stloc.0
0x3d44  ldsflda  int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockTimeoutSeconds
0x3d49  ldloc.0
0x3d4a  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0x3d4f  pop
0x3d50  ldsfld   int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockTimeoutSeconds
0x3d55  ret
```
