# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CleanPath

- ea: `0x9990`
- end: `0x99ad`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::CleanPath`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x96a0`
- `0x9750`

## pseudocode

```c

```

## disassembly

```asm
0x9990  ldarg.1
0x9991  ldc.i4.1
0x9992  newarr   [mscorlib]System.Char
0x9997  dup
0x9998  ldc.i4.0
0x9999  ldc.i4.s 0x2F
0x999b  stelem.i2
0x999c  callvirt instance string [mscorlib]System.String::Trim(char[])
0x99a1  ldc.i4.0
0x99a2  ldstr    asc_10432// "/"
0x99a7  callvirt instance string [mscorlib]System.String::Insert(int32, string)
0x99ac  ret
```
