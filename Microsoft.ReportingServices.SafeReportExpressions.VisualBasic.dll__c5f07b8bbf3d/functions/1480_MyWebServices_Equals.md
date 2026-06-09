# MyWebServices::Equals

- ea: `0x1480`
- end: `0x148d`
- name: `MyWebServices::Equals`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c

```

## disassembly

```asm
0x1480  ldarg.0
0x1481  ldarg.1
0x1482  call     object [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::GetObjectValue(object)
0x1487  call     instance bool [mscorlib]System.Object::Equals(object)
0x148c  ret
```
