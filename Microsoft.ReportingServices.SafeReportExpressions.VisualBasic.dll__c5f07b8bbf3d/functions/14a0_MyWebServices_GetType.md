# MyWebServices::GetType

- ea: `0x14a0`
- end: `0x14ab`
- name: `MyWebServices::GetType`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0x14a0  ldtoken  MyWebServices
0x14a5  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x14aa  ret
```
