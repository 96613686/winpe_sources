# Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_Value

- ea: `0xc90`
- end: `0xcac`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_Value`
- size: `28`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xcb0`
- `0xcf0`
- `0xd00`

## pseudocode

```c

```

## disassembly

```asm
0xc90  ldarg.0
0xc91  ldfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xc96  ldstr    asc_11FC// "."
0xc9b  ldarg.0
0xc9c  ldfld    int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xca1  box      [mscorlib]System.Int32
0xca6  call     string [mscorlib]System.String::Concat(object, object, object)
0xcab  ret
```
