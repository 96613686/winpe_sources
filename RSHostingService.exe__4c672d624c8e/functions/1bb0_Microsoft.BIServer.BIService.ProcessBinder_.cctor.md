# Microsoft.BIServer.BIService.ProcessBinder::.cctor

- ea: `0x1bb0`
- end: `0x1bbb`
- name: `Microsoft.BIServer.BIService.ProcessBinder::.cctor`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1b00`

## pseudocode

```c

```

## disassembly

```asm
0x1bb0  call     class [mscorlib]System.Runtime.InteropServices.SafeHandle Microsoft.BIServer.BIService.ProcessBinder::GetJobObject()
0x1bb5  stsfld   class [mscorlib]System.Runtime.InteropServices.SafeHandle Microsoft.BIServer.BIService.ProcessBinder::_jobObject
0x1bba  ret
```
