# System.Printing.IndexedProperties.PrintThreadPriorityProperty::get_Value

- ea: `0x154e0`
- end: `0x154ec`
- name: `System.Printing.IndexedProperties.PrintThreadPriorityProperty::get_Value`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x15580`
- `0x15590`
- `0x155a0`

## pseudocode

```c

```

## disassembly

```asm
0x154e0  ldarg.0
0x154e1  ldfld    valuetype [mscorlib]System.Threading.ThreadPriority System.Printing.IndexedProperties.PrintThreadPriorityProperty::value
0x154e6  box      [mscorlib]System.Threading.ThreadPriority
0x154eb  ret
```
