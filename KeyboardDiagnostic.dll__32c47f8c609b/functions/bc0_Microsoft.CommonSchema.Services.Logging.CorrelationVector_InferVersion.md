# Microsoft.CommonSchema.Services.Logging.CorrelationVector::InferVersion

- ea: `0xbc0`
- end: `0xbed`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::InferVersion`
- size: `45`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xb60`
- `0xba0`

## callees

- `0xbc0`

## pseudocode

```c

```

## disassembly

```asm
0xbc0  ldarg.0
0xbc1  ldc.i4.s 0x2E
0xbc3  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0xbc8  stloc.0
0xbc9  ldc.i4.s 0x10
0xbcb  ldloc.0
0xbcc  bne.un.s loc_BD0
0xbce  ldc.i4.0
0xbcf  ret
0xbd0  ldc.i4.s 0x16
0xbd2  ldloc.0
0xbd3  bne.un.s loc_BD7
0xbd5  ldc.i4.1
0xbd6  ret
0xbd7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xbdc  ldstr    aInvalidCorrela// "Invalid correlation vector {0}"
0xbe1  ldarg.0
0xbe2  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xbe7  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xbec  throw
```
