# MS.Internal.Printing.Configuration.PrintSchemaShim::SetPageMediaSize

- ea: `0x14ac0`
- end: `0x14bb1`
- name: `MS.Internal.Printing.Configuration.PrintSchemaShim::SetPageMediaSize`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x14250`

## callees

- `0xf650`
- `0xf660`
- `0xf6c0`
- `0xf7c0`
- `0xf7d0`
- `0x14ac0`
- `0x15000`
- `0x15010`
- `0x17ef0`
- `0x3f040`

## pseudocode

```c

```

## disassembly

```asm
0x14ac0  newobj   instance void <>c__DisplayClass35_0::.ctor()
0x14ac5  stloc.0
0x14ac6  ldloc.0
0x14ac7  ldarg.0
0x14ac8  stfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14acd  ldc.i4.0
0x14ace  stloc.1
0x14acf  ldc.r8   0.0
0x14ad8  stloc.2
0x14ad9  ldc.r8   0.0
0x14ae2  stloc.3
0x14ae3  ldarg.1
0x14ae4  ldc.i4.2
0x14ae5  and
0x14ae6  ldc.i4.2
0x14ae7  ceq
0x14ae9  stloc.s  4
0x14aeb  ldc.i4.0
0x14aec  stloc.s  5
0x14aee  ldloc.s  4
0x14af0  brfalse.s loc_14B42
0x14af2  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<int16, valuetype System.Printing.PageMediaSizeName> MS.Internal.Printing.Configuration.PrintSchemaShim::dmPaperSizeToPageMediaSize
0x14af7  ldarg.2
0x14af8  ldloc.0
0x14af9  ldftn    instance void <>c__DisplayClass35_0::<SetPageMediaSize>b__0(valuetype System.Printing.PageMediaSizeName sizeName)
0x14aff  newobj   instance void class [mscorlib]System.Action`1<valuetype System.Printing.PageMediaSizeName>::.ctor(object, native int)
0x14b04  call     T0x2B000009
0x14b09  stloc.s  5
0x14b0b  ldloc.s  5
0x14b0d  brfalse.s loc_14B42
0x14b0f  ldloc.0
0x14b10  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14b15  callvirt instance class MS.Internal.Printing.Configuration.PageMediaSizeSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_PageMediaSize()
0x14b1a  callvirt instance valuetype System.Printing.PageMediaSizeName MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_Value()
0x14b1f  stloc.1
0x14b20  ldloc.0
0x14b21  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14b26  callvirt instance class MS.Internal.Printing.Configuration.PageMediaSizeSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_PageMediaSize()
0x14b2b  callvirt instance float64 MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_MediaSizeWidth()
0x14b30  stloc.2
0x14b31  ldloc.0
0x14b32  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14b37  callvirt instance class MS.Internal.Printing.Configuration.PageMediaSizeSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_PageMediaSize()
0x14b3c  callvirt instance float64 MS.Internal.Printing.Configuration.PageMediaSizeSetting::get_MediaSizeHeight()
0x14b41  stloc.3
0x14b42  ldarg.1
0x14b43  ldc.i4.8
0x14b44  and
0x14b45  ldc.i4.8
0x14b46  ceq
0x14b48  stloc.s  6
0x14b4a  ldarg.1
0x14b4b  ldc.i4.4
0x14b4c  and
0x14b4d  ldc.i4.4
0x14b4e  ceq
0x14b50  stloc.s  7
0x14b52  ldloc.s  6
0x14b54  ldloc.s  7
0x14b56  or
0x14b57  brfalse.s loc_14BB0
0x14b59  ldloc.s  6
0x14b5b  brfalse.s loc_14B6F
0x14b5d  ldarg.3
0x14b5e  ldc.i4.1
0x14b5f  ldc.i4   0x7FFF
0x14b64  call     int16 MS.Internal.Printing.Configuration.PrintSchemaShim::Clamp(int32 value, int16 min, int16 max)
0x14b69  call     float64 MS.Internal.Printing.Configuration.PrintSchemaShim::LengthValueFromTenthOfMillimeterToDIP(int32 tenthOfMillimeterValue)
0x14b6e  stloc.2
0x14b6f  ldloc.s  7
0x14b71  brfalse.s loc_14B86
0x14b73  ldarg.s  4
0x14b75  ldc.i4.1
0x14b76  ldc.i4   0x7FFF
0x14b7b  call     int16 MS.Internal.Printing.Configuration.PrintSchemaShim::Clamp(int32 value, int16 min, int16 max)
0x14b80  call     float64 MS.Internal.Printing.Configuration.PrintSchemaShim::LengthValueFromTenthOfMillimeterToDIP(int32 tenthOfMillimeterValue)
0x14b85  stloc.3
0x14b86  ldloc.s  5
0x14b88  brfalse.s loc_14B9E
0x14b8a  ldloc.0
0x14b8b  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14b90  callvirt instance class MS.Internal.Printing.Configuration.PageMediaSizeSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_PageMediaSize()
0x14b95  ldloc.1
0x14b96  ldloc.2
0x14b97  ldloc.3
0x14b98  callvirt instance void MS.Internal.Printing.Configuration.PageMediaSizeSetting::SetFixedMediaSize(valuetype System.Printing.PageMediaSizeName value, float64 mediaSizeWidth, float64 mediaSizeHeight)
0x14b9d  ret
0x14b9e  ldloc.0
0x14b9f  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket <>c__DisplayClass35_0::ticket
0x14ba4  callvirt instance class MS.Internal.Printing.Configuration.PageMediaSizeSetting MS.Internal.Printing.Configuration.InternalPrintTicket::get_PageMediaSize()
0x14ba9  ldloc.2
0x14baa  ldloc.3
0x14bab  callvirt instance void MS.Internal.Printing.Configuration.PageMediaSizeSetting::SetFixedMediaSize(float64 mediaSizeWidth, float64 mediaSizeHeight)
0x14bb0  ret
```
