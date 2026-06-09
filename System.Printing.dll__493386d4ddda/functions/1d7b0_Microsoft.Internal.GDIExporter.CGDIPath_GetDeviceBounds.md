# Microsoft.Internal.GDIExporter.CGDIPath::GetDeviceBounds

- ea: `0x1d7b0`
- end: `0x1d871`
- name: `Microsoft.Internal.GDIExporter.CGDIPath::GetDeviceBounds`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d880`
- `0x1d920`

## callees

- `0x1d7b0`

## pseudocode

```c

```

## disassembly

```asm
0x1d7b0  ldarg.2
0x1d7b1  ldc.i4.1
0x1d7b2  bge.s    loc_1D7B7
0x1d7b4  ldc.i4.0
0x1d7b5  br.s     loc_1D7B8
0x1d7b7  ldc.i4.1
0x1d7b8  stloc.s  7
0x1d7ba  ldloc.s  7
0x1d7bc  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x1d7c1  ldarg.1
0x1d7c2  ldc.i4.0
0x1d7c3  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d7c8  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d7cd  stloc.2
0x1d7ce  ldloc.2
0x1d7cf  stloc.s  6
0x1d7d1  ldarg.1
0x1d7d2  ldc.i4.0
0x1d7d3  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d7d8  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d7dd  stloc.1
0x1d7de  ldloc.1
0x1d7df  stloc.s  5
0x1d7e1  ldc.i4.1
0x1d7e2  stloc.0
0x1d7e3  ldc.i4.1
0x1d7e4  ldarg.2
0x1d7e5  bge.s    loc_1D834
0x1d7e7  ldarg.1
0x1d7e8  ldloc.0
0x1d7e9  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d7ee  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::x
0x1d7f3  stloc.s  4
0x1d7f5  ldloc.s  4
0x1d7f7  ldloc.s  6
0x1d7f9  bge.s    loc_1D801
0x1d7fb  ldloc.s  4
0x1d7fd  stloc.s  6
0x1d7ff  br.s     loc_1D80C
0x1d801  ldloc.s  4
0x1d803  ldloc.2
0x1d804  bgt.s    loc_1D809
0x1d806  ldloc.2
0x1d807  br.s     loc_1D80B
0x1d809  ldloc.s  4
0x1d80b  stloc.2
0x1d80c  ldarg.1
0x1d80d  ldloc.0
0x1d80e  ldelema  Microsoft.Internal.GDIExporter.PointI
0x1d813  ldfld    int32 Microsoft.Internal.GDIExporter.PointI::y
0x1d818  stloc.3
0x1d819  ldloc.3
0x1d81a  ldloc.s  5
0x1d81c  bge.s    loc_1D823
0x1d81e  ldloc.3
0x1d81f  stloc.s  5
0x1d821  br.s     loc_1D82C
0x1d823  ldloc.3
0x1d824  ldloc.1
0x1d825  bgt.s    loc_1D82A
0x1d827  ldloc.1
0x1d828  br.s     loc_1D82B
0x1d82a  ldloc.3
0x1d82b  stloc.1
0x1d82c  ldloc.0
0x1d82d  ldc.i4.1
0x1d82e  add
0x1d82f  stloc.0
0x1d830  ldloc.0
0x1d831  ldarg.2
0x1d832  blt.s    loc_1D7E7
0x1d834  ldarg.0
0x1d835  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1d83a  ldloc.s  6
0x1d83c  call     instance void [WindowsBase]System.Windows.Int32Rect::set_X(int32)
0x1d841  ldarg.0
0x1d842  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1d847  ldloc.s  5
0x1d849  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Y(int32)
0x1d84e  ldarg.0
0x1d84f  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1d854  ldloc.2
0x1d855  ldloc.s  6
0x1d857  sub
0x1d858  ldc.i4.1
0x1d859  add
0x1d85a  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Width(int32)
0x1d85f  ldarg.0
0x1d860  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.CGDIPath::m_DeviceBounds
0x1d865  ldloc.1
0x1d866  ldloc.s  5
0x1d868  sub
0x1d869  ldc.i4.1
0x1d86a  add
0x1d86b  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Height(int32)
0x1d870  ret
```
