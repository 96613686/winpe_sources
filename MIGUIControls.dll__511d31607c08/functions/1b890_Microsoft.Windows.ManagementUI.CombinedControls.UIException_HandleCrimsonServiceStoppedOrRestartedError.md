# Microsoft.Windows.ManagementUI.CombinedControls.UIException::HandleCrimsonServiceStoppedOrRestartedError

- ea: `0x1b890`
- end: `0x1b8d9`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.UIException::HandleCrimsonServiceStoppedOrRestartedError`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x47000`
- `0x47150`

## callees

- `0x12ed0`
- `0x1b6a0`
- `0x1b7f0`
- `0x1b850`
- `0x1b890`
- `0x32920`

## string_xrefs

- `0x1b898`: `CrimsonServiceNotRunning`
- `0x1b8be`: `CrimsonServiceRestarted`

## pseudocode

```c

```

## disassembly

```asm
0x1b890  ldarg.0
0x1b891  call     bool Microsoft.Windows.ManagementUI.CombinedControls.UIException::ServiceNotAvailableError(int32 error)
0x1b896  brfalse.s loc_1B8D8
0x1b898  ldstr    aCrimsonservice// "CrimsonServiceNotRunning"
0x1b89d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x1b8a2  ldc.i4.1
0x1b8a3  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(string message, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction initialAction)
0x1b8a8  stloc.0
0x1b8a9  ldloc.0
0x1b8aa  ldarg.0
0x1b8ab  callvirt instance void [mscorlib]System.Exception::set_HResult(int32)
0x1b8b0  ldloc.0
0x1b8b1  ldc.i4.1
0x1b8b2  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::set_RefreshConsole(bool value)
0x1b8b7  call     bool Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::CheckIfWindowsEventingServiceIsRunning()
0x1b8bc  brfalse.s loc_1B8D6
0x1b8be  ldstr    aCrimsonservice_0// "CrimsonServiceRestarted"
0x1b8c3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x1b8c8  ldc.i4.2
0x1b8c9  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::.ctor(string message, valuetype Microsoft.Windows.ManagementUI.CombinedControls.ExceptionAction initialAction)
0x1b8ce  stloc.0
0x1b8cf  ldloc.0
0x1b8d0  ldc.i4.1
0x1b8d1  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.UIException::set_RefreshConsole(bool value)
0x1b8d6  ldloc.0
0x1b8d7  throw
0x1b8d8  ret
```
