# Microsoft.BIServer.BIService.ProcessBinder::Bind

- ea: `0x1ac0`
- end: `0x1acc`
- name: `Microsoft.BIServer.BIService.ProcessBinder::Bind`
- size: `12`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2a50`
- `0x2b00`

## callees

- `0x1ad0`

## pseudocode

```c

```

## disassembly

```asm
0x1ac0  ldarg.0
0x1ac1  ldsfld   class [mscorlib]System.Runtime.InteropServices.SafeHandle Microsoft.BIServer.BIService.ProcessBinder::_jobObject
0x1ac6  call     void Microsoft.BIServer.BIService.ProcessBinder::BindInternal(int32 processId, class [mscorlib]System.Runtime.InteropServices.SafeHandle jobObject)
0x1acb  ret
```
