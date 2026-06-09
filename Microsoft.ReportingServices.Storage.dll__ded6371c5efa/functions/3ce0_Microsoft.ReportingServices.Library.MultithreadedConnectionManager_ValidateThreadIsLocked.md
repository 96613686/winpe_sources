# Microsoft.ReportingServices.Library.MultithreadedConnectionManager::ValidateThreadIsLocked

- ea: `0x3ce0`
- end: `0x3d1c`
- name: `Microsoft.ReportingServices.Library.MultithreadedConnectionManager::ValidateThreadIsLocked`
- size: `60`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x3bd0`
- `0x3cc0`

## string_xrefs

- `0x3d11`: `currentThreadId`

## pseudocode

```c

```

## disassembly

```asm
0x3ce0  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x3ce5  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x3cea  stloc.0
0x3ceb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3cf0  ldarg.0
0x3cf1  ldfld    int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockDepth
0x3cf6  ldc.i4.0
0x3cf7  cgt
0x3cf9  ldstr    aLockdepth// "_lockDepth"
0x3cfe  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3d03  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x3d08  ldloc.0
0x3d09  ldarg.0
0x3d0a  ldfld    int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockedThreadId
0x3d0f  ceq
0x3d11  ldstr    aCurrentthreadi// "currentThreadId"
0x3d16  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x3d1b  ret
```
