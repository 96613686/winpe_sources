# Microsoft.Internal.GDIExporter.CGDIDevice::ConvertPen

- ea: `0x1cc10`
- end: `0x1cdf0`
- name: `Microsoft.Internal.GDIExporter.CGDIDevice::ConvertPen`
- size: `480`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1f740`

## callees

- `0x420`
- `0x8f0`
- `0xac0`
- `0xc50`
- `0x1bd60`
- `0x1c660`
- `0x1cb20`
- `0x1cb60`
- `0x1cc10`
- `0x1d4a0`
- `0x1d5a0`

## string_xrefs

- `0x1cdd6`: `ExtCreatePen failed`

## pseudocode

```c

```

## disassembly

```asm
0x1cc10  ldnull
0x1cc11  stloc.3
0x1cc12  ldarg.1
0x1cc13  ldarg.3
0x1cc14  ldarg.s  5
0x1cc16  call     bool Microsoft.Internal.GDIExporter.PenSupported([hasfieldmarshal] class [PresentationCore]System.Windows.Media.Pen value, valuetype [WindowsBase]System.Windows.Media.Matrix pPen, unsigned int32 matrix)
0x1cc1b  brtrue.s loc_1CC25
0x1cc1d  ldarg.0
0x1cc1e  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cc23  ldnull
0x1cc24  ret
0x1cc25  ldarg.1
0x1cc26  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_Thickness()
0x1cc2b  ldc.r8   0.0
0x1cc34  beq.s    loc_1CC3B
0x1cc36  ldc.i4.1
0x1cc37  stloc.s  9
0x1cc39  br.s     loc_1CC3E
0x1cc3b  ldc.i4.0
0x1cc3c  stloc.s  9
0x1cc3e  ldloc.s  9
0x1cc40  ldstr    aGdiDoesnTSuppo// "GDI doesn't support 0-width pens"
0x1cc45  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1cc4a  ldarg.1
0x1cc4b  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_Thickness()
0x1cc50  ldarga.s 3
0x1cc52  call     float64 Microsoft.Internal.GDIExporter.GetScaleX(valuetype [WindowsBase]System.Windows.Media.Matrix& matrix)
0x1cc57  mul
0x1cc58  stloc.s  0xC
0x1cc5a  ldarg.s  4
0x1cc5c  call     instance int32 Microsoft.Internal.GDIExporter.CGDIPath::GetResolutionScale()
0x1cc61  conv.r8
0x1cc62  ldloc.s  0xC
0x1cc64  mul
0x1cc65  stloc.s  8
0x1cc67  ldloc.s  8
0x1cc69  ldc.r8   0.0
0x1cc72  bgt.un.s loc_1CC7C
0x1cc74  ldarg.0
0x1cc75  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cc7a  ldnull
0x1cc7b  ret
0x1cc7c  ldloc.s  8
0x1cc7e  call     float64 [mscorlib]System.Math::Round(float64)
0x1cc83  conv.i4
0x1cc84  stloc.2
0x1cc85  ldc.i4.1
0x1cc86  stloc.s  6
0x1cc88  ldloc.2
0x1cc89  ldc.i4.1
0x1cc8a  bgt.s    loc_1CC91
0x1cc8c  ldc.i4.1
0x1cc8d  stloc.2
0x1cc8e  ldc.i4.0
0x1cc8f  stloc.s  6
0x1cc91  ldnull
0x1cc92  stloc.3
0x1cc93  ldarg.1
0x1cc94  ldloc.s  6
0x1cc96  ldloca.s 3
0x1cc98  call     int32 Microsoft.Internal.GDIExporter.GetStyle(class [PresentationCore]System.Windows.Media.Pen pen, [hasfieldmarshal] bool thick, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32[]& dashes)
0x1cc9d  stloc.0
0x1cc9e  ldloc.0
0x1cc9f  ldc.i4.0
0x1cca0  bge.s    loc_1CCAA
0x1cca2  ldarg.0
0x1cca3  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cca8  ldnull
0x1cca9  ret
0x1ccaa  ldloc.s  6
0x1ccac  brfalse  loc_1CD3C
0x1ccb1  ldarg.1
0x1ccb2  call     instance valuetype [PresentationCore]System.Windows.Media.PenLineJoin [PresentationCore]System.Windows.Media.Pen::get_LineJoin()
0x1ccb7  stloc.s  5
0x1ccb9  ldloc.s  5
0x1ccbb  brtrue.s loc_1CCFE
0x1ccbd  ldarg.s  4
0x1ccbf  brfalse.s loc_1CD1A
0x1ccc1  ldarg.s  4
0x1ccc3  call     instance float64 Microsoft.Internal.GDIExporter.CGDIPath::MaxCos()
0x1ccc8  stloc.s  0xB
0x1ccca  ldarg.1
0x1cccb  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_MiterLimit()
0x1ccd0  stloc.s  4
0x1ccd2  ldloc.s  4
0x1ccd4  ldc.r8   0.5
0x1ccdd  ble.un.s loc_1CD1A
0x1ccdf  ldloc.s  0xB
0x1cce1  ldc.r8   1.0
0x1ccea  ldc.r8   2.0
0x1ccf3  ldloc.s  4
0x1ccf5  div
0x1ccf6  ldloc.s  4
0x1ccf8  div
0x1ccf9  sub
0x1ccfa  bge.un.s loc_1CD1A
0x1ccfc  br.s     loc_1CD26
0x1ccfe  ldloc.s  5
0x1cd00  ldc.i4.1
0x1cd01  beq.s    loc_1CD10
0x1cd03  ldloc.s  5
0x1cd05  ldc.i4.2
0x1cd06  beq.s    loc_1CD3C
0x1cd08  ldarg.0
0x1cd09  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cd0e  ldnull
0x1cd0f  ret
0x1cd10  ldloc.0
0x1cd11  ldc.i4   0x1000
0x1cd16  or
0x1cd17  stloc.0
0x1cd18  br.s     loc_1CD3C
0x1cd1a  ldloc.2
0x1cd1b  ldc.i4.1
0x1cd1c  ble.s    loc_1CD26
0x1cd1e  ldarg.0
0x1cd1f  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cd24  ldnull
0x1cd25  ret
0x1cd26  ldloc.0
0x1cd27  ldc.i4   0x2000
0x1cd2c  or
0x1cd2d  stloc.0
0x1cd2e  ldarg.0
0x1cd2f  ldarg.1
0x1cd30  call     instance float64 [PresentationCore]System.Windows.Media.Pen::get_MiterLimit()
0x1cd35  conv.r4
0x1cd36  call     instance modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 Microsoft.Internal.GDIExporter.CGDIDevice::SetMiterLimit(float32 eNewLimit)
0x1cd3b  pop
0x1cd3c  ldarg.2
0x1cd3d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1cd42  ldtoken  [PresentationCore]System.Windows.Media.SolidColorBrush
0x1cd47  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1cd4c  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1cd51  brfalse  loc_1CDE8
0x1cd56  ldarg.2
0x1cd57  castclass [PresentationCore]System.Windows.Media.SolidColorBrush
0x1cd5c  stloc.s  0xA
0x1cd5e  ldloca.s 0xD
0x1cd60  ldc.i4.0
0x1cd61  stind.i4
0x1cd62  ldloca.s 0xD
0x1cd64  ldc.i4.4
0x1cd65  add
0x1cd66  ldloc.s  0xA
0x1cd68  call     modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 Microsoft.Internal.GDIExporter.ToCOLORREF(class [PresentationCore]System.Windows.Media.SolidColorBrush pBrush)
0x1cd6d  stind.i4
0x1cd6e  ldloca.s 0xD
0x1cd70  ldc.i4.8
0x1cd71  add
0x1cd72  ldc.i4.0
0x1cd73  conv.i8
0x1cd74  stind.i8
0x1cd75  ldloca.s 0xD
0x1cd77  ldc.i4.s 0x10
0x1cd79  add
0x1cd7a  ldloc.0
0x1cd7b  stind.i4
0x1cd7c  ldloca.s 0xD
0x1cd7e  ldc.i4.s 0x14
0x1cd80  add
0x1cd81  ldloc.2
0x1cd82  stind.i4
0x1cd83  ldarg.0
0x1cd84  ldloca.s 0xD
0x1cd86  ldc.i4.s 0x18
0x1cd88  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::CacheMatch(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size)
0x1cd8d  stloc.1
0x1cd8e  ldloc.1
0x1cd8f  brtrue.s loc_1CDE0
0x1cd91  ldloc.3
0x1cd92  brfalse.s loc_1CD9A
0x1cd94  ldloc.3
0x1cd95  ldlen
0x1cd96  stloc.s  7
0x1cd98  br.s     loc_1CD9D
0x1cd9a  ldc.i4.0
0x1cd9b  stloc.s  7
0x1cd9d  ldloca.s 0xD
0x1cd9f  ldc.i4.s 0x10
0x1cda1  add
0x1cda2  ldind.i4
0x1cda3  ldc.i4   loc_10000
0x1cda8  or
0x1cda9  ldloca.s 0xD
0x1cdab  ldc.i4.s 0x14
0x1cdad  add
0x1cdae  ldind.i4
0x1cdaf  ldloca.s 0xD
0x1cdb1  ldloc.s  7
0x1cdb3  ldloc.3
0x1cdb4  call     class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CNativeMethods::ExtCreatePen(modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 dwPenStyle, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 dwWidth, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype tagLOGBRUSH* plb, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 dwStyleCount, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32[] pStyle)
0x1cdb9  stloc.1
0x1cdba  ldloc.1
0x1cdbb  brfalse.s loc_1CDD5
0x1cdbd  ldloca.s 0xD
0x1cdbf  ldc.i4.s 0x10
0x1cdc1  add
0x1cdc2  ldind.i4
0x1cdc3  ldc.i4.7
0x1cdc4  and
0x1cdc5  ldc.i4.7
0x1cdc6  beq.s    loc_1CDE0
0x1cdc8  ldarg.0
0x1cdc9  ldloca.s 0xD
0x1cdcb  ldc.i4.s 0x18
0x1cdcd  ldloc.1
0x1cdce  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::CacheObject(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size, class Microsoft.Internal.GDIExporter.GdiSafeHandle handle)
0x1cdd3  br.s     loc_1CDE0
0x1cdd5  ldc.i4.0
0x1cdd6  ldstr    aExtcreatepenFa// "ExtCreatePen failed"
0x1cddb  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1cde0  ldarg.0
0x1cde1  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cde6  ldloc.1
0x1cde7  ret
0x1cde8  ldarg.0
0x1cde9  call     void [mscorlib]System.GC::KeepAlive(object)
0x1cdee  ldnull
0x1cdef  ret
```
