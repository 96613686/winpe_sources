# Microsoft.SharePoint.Utilities.Mime.BufferedWrite::EnsureBuffer

- ea: `0x2c8a0`
- end: `0x2c91a`
- name: `Microsoft.SharePoint.Utilities.Mime.BufferedWrite::EnsureBuffer`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2c960`
- `0x2c9a0`

## callees

- `0x29cd0`
- `0x2c8a0`
- `0x2ca50`

## string_xrefs

- `0x2c8be`: `WriteBufferOverflow`

## pseudocode

```c

```

## disassembly

```asm
0x2c8a0  ldarg.0
0x2c8a1  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.BufferedWrite::buffer
0x2c8a6  ldlen
0x2c8a7  conv.i4
0x2c8a8  stloc.0
0x2c8a9  ldarg.1
0x2c8aa  ldloc.0
0x2c8ab  ldarg.0
0x2c8ac  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.BufferedWrite::offset
0x2c8b1  sub
0x2c8b2  ble.s    loc_2C919
0x2c8b4  ldloc.0
0x2c8b5  stloc.1
0x2c8b6  ldloc.1
0x2c8b7  ldc.i4   0x7FFFFFFF
0x2c8bc  bne.un.s loc_2C8D9
0x2c8be  ldstr    aWritebufferove// "WriteBufferOverflow"
0x2c8c3  ldc.i4.0
0x2c8c4  newarr   [mscorlib]System.Object
0x2c8c9  call     string Microsoft.SharePoint.Utilities.Mime.SR::GetString(string resourceId, object[] args)
0x2c8ce  newobj   instance void [System.Xml]System.Xml.XmlException::.ctor(string)
0x2c8d3  call     class [mscorlib]System.Exception ExceptionUtility::ThrowHelperError(class [mscorlib]System.Exception ex)
0x2c8d8  throw
0x2c8d9  ldloc.1
0x2c8da  ldc.i4   0x3FFFFFFF
0x2c8df  blt.s    loc_2C8E8
0x2c8e1  ldc.i4   0x7FFFFFFF
0x2c8e6  br.s     loc_2C8EB
0x2c8e8  ldloc.1
0x2c8e9  ldc.i4.2
0x2c8ea  mul
0x2c8eb  stloc.1
0x2c8ec  ldarg.1
0x2c8ed  ldloc.1
0x2c8ee  ldarg.0
0x2c8ef  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.BufferedWrite::offset
0x2c8f4  sub
0x2c8f5  bgt.s    loc_2C8B6
0x2c8f7  ldloc.1
0x2c8f8  newarr   [mscorlib]System.Byte
0x2c8fd  stloc.2
0x2c8fe  ldarg.0
0x2c8ff  ldfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.BufferedWrite::buffer
0x2c904  ldc.i4.0
0x2c905  ldloc.2
0x2c906  ldc.i4.0
0x2c907  ldarg.0
0x2c908  ldfld    int32 Microsoft.SharePoint.Utilities.Mime.BufferedWrite::offset
0x2c90d  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0x2c912  ldarg.0
0x2c913  ldloc.2
0x2c914  stfld    unsigned int8[] Microsoft.SharePoint.Utilities.Mime.BufferedWrite::buffer
0x2c919  ret
```
