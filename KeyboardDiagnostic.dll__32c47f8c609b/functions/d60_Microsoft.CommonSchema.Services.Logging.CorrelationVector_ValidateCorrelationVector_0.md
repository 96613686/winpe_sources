# Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector_0

- ea: `0xd60`
- end: `0xdf9`
- name: `Microsoft.CommonSchema.Services.Logging.CorrelationVector::ValidateCorrelationVector_0`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xd20`

## callees

- `0xd60`

## pseudocode

```c

```

## disassembly

```asm
0xd60  ldarg.0
0xd61  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xd66  brtrue.s loc_D71
0xd68  ldarg.0
0xd69  callvirt instance int32 [mscorlib]System.String::get_Length()
0xd6e  ldarg.1
0xd6f  ble.s    loc_D8C
0xd71  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xd76  ldstr    aTheCorrelation// "The Correlation vector can not be null "...
0xd7b  ldarg.1
0xd7c  box      [mscorlib]System.Byte
0xd81  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xd86  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xd8b  throw
0xd8c  ldarg.0
0xd8d  ldc.i4.1
0xd8e  newarr   [mscorlib]System.Char
0xd93  dup
0xd94  ldc.i4.0
0xd95  ldc.i4.s 0x2E
0xd97  stelem.i2
0xd98  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xd9d  stloc.0
0xd9e  ldloc.0
0xd9f  ldlen
0xda0  conv.i4
0xda1  ldc.i4.2
0xda2  blt.s    loc_DAF
0xda4  ldloc.0
0xda5  ldc.i4.0
0xda6  ldelem.ref
0xda7  callvirt instance int32 [mscorlib]System.String::get_Length()
0xdac  ldarg.2
0xdad  beq.s    loc_DC5
0xdaf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xdb4  ldstr    aInvalidCorrela// "Invalid correlation vector {0}"
0xdb9  ldarg.0
0xdba  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0xdbf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xdc4  throw
0xdc5  ldc.i4.1
0xdc6  stloc.1
0xdc7  br.s     loc_DF2
0xdc9  ldloc.0
0xdca  ldloc.1
0xdcb  ldelem.ref
0xdcc  ldloca.s 2
0xdce  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0xdd3  brtrue.s loc_DEE
0xdd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0xdda  ldstr    aInvalidCorrela_0// "Invalid correlation vector {0}. Invalid"...
0xddf  ldarg.0
0xde0  ldloc.0
0xde1  ldloc.1
0xde2  ldelem.ref
0xde3  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object, object)
0xde8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xded  throw
0xdee  ldloc.1
0xdef  ldc.i4.1
0xdf0  add
0xdf1  stloc.1
0xdf2  ldloc.1
0xdf3  ldloc.0
0xdf4  ldlen
0xdf5  conv.i4
0xdf6  blt.s    loc_DC9
0xdf8  ret
```
