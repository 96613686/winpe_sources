# System.Windows.Threading.DispatcherOperation::InvokeCompletions

- ea: `0x3dad0`
- end: `0x3db25`
- name: `System.Windows.Threading.DispatcherOperation::InvokeCompletions`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x3c2b0`

## callees

- `0xd6a0`
- `0x3dad0`
- `0x3dd70`
- `0x3dd80`
- `0x3dd90`

## string_xrefs

- `0x3db1a`: `Operation should be either Aborted or Completed!`

## pseudocode

```c

```

## disassembly

```asm
0x3dad0  ldarg.0
0x3dad1  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3dad6  stloc.0
0x3dad7  ldloc.0
0x3dad8  ldc.i4.1
0x3dad9  beq.s    loc_3DAE1
0x3dadb  ldloc.0
0x3dadc  ldc.i4.2
0x3dadd  beq.s    loc_3DAED
0x3dadf  br.s     loc_3DB19
0x3dae1  ldarg.0
0x3dae2  ldfld    class System.Windows.Threading.DispatcherOperationTaskSource System.Windows.Threading.DispatcherOperation::_taskSource
0x3dae7  callvirt instance void System.Windows.Threading.DispatcherOperationTaskSource::SetCanceled()
0x3daec  ret
0x3daed  ldarg.0
0x3daee  ldfld    class [mscorlib]System.Exception System.Windows.Threading.DispatcherOperation::_exception
0x3daf3  brfalse.s loc_3DB07
0x3daf5  ldarg.0
0x3daf6  ldfld    class System.Windows.Threading.DispatcherOperationTaskSource System.Windows.Threading.DispatcherOperation::_taskSource
0x3dafb  ldarg.0
0x3dafc  ldfld    class [mscorlib]System.Exception System.Windows.Threading.DispatcherOperation::_exception
0x3db01  callvirt instance void System.Windows.Threading.DispatcherOperationTaskSource::SetException(class [mscorlib]System.Exception exception)
0x3db06  ret
0x3db07  ldarg.0
0x3db08  ldfld    class System.Windows.Threading.DispatcherOperationTaskSource System.Windows.Threading.DispatcherOperation::_taskSource
0x3db0d  ldarg.0
0x3db0e  ldfld    object System.Windows.Threading.DispatcherOperation::_result
0x3db13  callvirt instance void System.Windows.Threading.DispatcherOperationTaskSource::SetResult(object result)
0x3db18  ret
0x3db19  ldc.i4.0
0x3db1a  ldstr    aOperationShoul// "Operation should be either Aborted or C"...
0x3db1f  call     void MS.Internal.Invariant::Assert(bool condition, string invariantMessage)
0x3db24  ret
```
