# NGenTask.TaskExecutive::TryParseDouble

- ea: `0x25a0`
- end: `0x25c0`
- name: `NGenTask.TaskExecutive::TryParseDouble`
- size: `32`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x2540`
- `0x25a0`

## pseudocode

```c

```

## disassembly

```asm
0x25a0  ldarg.0
0x25a1  ldloca.s 0
0x25a3  call     bool [mscorlib]System.Double::TryParse(string, float64&)
0x25a8  brtrue.s loc_25BE
0x25aa  ldstr    aInvalidValue0P// "Invalid value \"{0}\" (Parse as double "...
0x25af  ldc.i4.1
0x25b0  newarr   [mscorlib]System.Object
0x25b5  dup
0x25b6  ldc.i4.0
0x25b7  ldarg.0
0x25b8  stelem.ref
0x25b9  call     void NGenTask.TaskExecutive::UsageError(string format, object[] args)
0x25be  ldloc.0
0x25bf  ret
```
