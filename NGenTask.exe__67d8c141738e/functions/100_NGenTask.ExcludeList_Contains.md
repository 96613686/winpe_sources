# NGenTask.ExcludeList::Contains

- ea: `0x100`
- end: `0x10d`
- name: `NGenTask.ExcludeList::Contains`
- size: `13`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x3c10`

## pseudocode

```c

```

## disassembly

```asm
0x100  ldarg.0
0x101  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0x106  ldarg.1
0x107  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::ContainsKey(var<u1>)
0x10c  ret
```
