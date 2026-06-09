# Microsoft.BIServer.BIService.ProcessBinder::BindInternal

- ea: `0x1ad0`
- end: `0x1aff`
- name: `Microsoft.BIServer.BIService.ProcessBinder::BindInternal`
- size: `47`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ac0`
- `0x1b00`

## callees

- `0x1ad0`
- `0x2660`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldarg.1
0x1ad1  ldarg.0
0x1ad2  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetProcessById(int32)
0x1ad7  callvirt instance native int [System]System.Diagnostics.Process::get_Handle()
0x1adc  call     bool Microsoft.BIServer.BIService.Win32::AssignProcessToJobObject(class [mscorlib]System.Runtime.InteropServices.SafeHandle job, native int process)
0x1ae1  brtrue.s loc_1AFE
0x1ae3  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1ae8  ldstr    aUnableToAssoci// "Unable to associate process {0} with Jo"...
0x1aed  ldarg.0
0x1aee  box      [mscorlib]System.Int32
0x1af3  call     string [mscorlib]System.String::Format(string, object)
0x1af8  newobj   instance void [System]System.ComponentModel.Win32Exception::.ctor(int32, string)
0x1afd  throw
0x1afe  ret
```
