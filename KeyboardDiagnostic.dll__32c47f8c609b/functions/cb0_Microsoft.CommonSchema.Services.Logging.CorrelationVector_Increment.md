# Microsoft.CommonSchema.Services.Logging.CorrelationVector::Increment

- ea: `0xcb0`
- end: `0xce2`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::Increment`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0xc90`
- `0xcb0`
- `0xe60`

## pseudocode

```c

```

## disassembly

```asm
0xcb0  ldarg.0
0xcb1  call     instance bool Microsoft.CommonSchema.Services.Logging.CorrelationVector::CanIncrement()
0xcb6  brtrue.s loc_CBF
0xcb8  ldarg.0
0xcb9  call     instance string Microsoft.CommonSchema.Services.Logging.CorrelationVector::get_Value()
0xcbe  ret
0xcbf  ldarg.0
0xcc0  ldflda   int32 Microsoft.CommonSchema.Services.Logging.CorrelationVector::lastExtension
0xcc5  call     int32 [mscorlib]System.Threading.Interlocked::Increment(int32&)
0xcca  stloc.0
0xccb  ldarg.0
0xccc  ldfld    string Microsoft.CommonSchema.Services.Logging.CorrelationVector::correlationVectorBase
0xcd1  ldstr    asc_11FC// "."
0xcd6  ldloc.0
0xcd7  box      [mscorlib]System.Int32
0xcdc  call     string [mscorlib]System.String::Concat(object, object, object)
0xce1  ret
```
