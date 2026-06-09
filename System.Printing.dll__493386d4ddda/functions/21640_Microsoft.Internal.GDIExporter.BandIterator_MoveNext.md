# Microsoft.Internal.GDIExporter.BandIterator::MoveNext

- ea: `0x21640`
- end: `0x2178b`
- name: `Microsoft.Internal.GDIExporter.BandIterator::MoveNext`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1e470`

## callees

- `0x21640`

## pseudocode

```c

```

## disassembly

```asm
0x21640  ldarg.0
0x21641  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_index
0x21646  stloc.s  6
0x21648  ldloc.s  6
0x2164a  ldarg.0
0x2164b  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_count
0x21650  bge.s    loc_2165C
0x21652  ldloc.s  6
0x21654  ldc.i4.m1
0x21655  blt.s    loc_2165C
0x21657  ldc.i4.1
0x21658  stloc.s  5
0x2165a  br.s     loc_2165F
0x2165c  ldc.i4.0
0x2165d  stloc.s  5
0x2165f  ldloc.s  5
0x21661  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x21666  ldarg.0
0x21667  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_index
0x2166c  ldc.i4.1
0x2166d  add
0x2166e  stloc.s  4
0x21670  ldarg.0
0x21671  ldloc.s  4
0x21673  stfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_index
0x21678  ldarg.0
0x21679  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_count
0x2167e  stloc.3
0x2167f  ldloc.s  4
0x21681  ldloc.3
0x21682  bge      loc_21789
0x21687  ldloc.3
0x21688  stloc.2
0x21689  ldarg.0
0x2168a  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_rect
0x2168f  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Height()
0x21694  ldarg.0
0x21695  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_index
0x2169a  mul
0x2169b  stloc.s  9
0x2169d  ldarg.0
0x2169e  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x216a3  ldarg.0
0x216a4  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_rect
0x216a9  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x216ae  ldloc.s  9
0x216b0  ldloc.2
0x216b1  add
0x216b2  ldc.i4.1
0x216b3  sub
0x216b4  ldloc.2
0x216b5  div
0x216b6  add
0x216b7  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Y(int32)
0x216bc  ldarg.0
0x216bd  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_count
0x216c2  stloc.1
0x216c3  ldarg.0
0x216c4  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_rect
0x216c9  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Height()
0x216ce  stloc.s  8
0x216d0  ldarg.0
0x216d1  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x216d6  ldloc.s  8
0x216d8  ldloc.1
0x216d9  add
0x216da  ldc.i4.1
0x216db  sub
0x216dc  ldloc.1
0x216dd  div
0x216de  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Height(int32)
0x216e3  ldarg.0
0x216e4  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x216e9  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x216ee  ldarg.0
0x216ef  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_prevBottom
0x216f4  sub
0x216f5  stloc.0
0x216f6  ldarg.0
0x216f7  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x216fc  ldarg.0
0x216fd  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x21702  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x21707  ldloc.0
0x21708  sub
0x21709  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Y(int32)
0x2170e  ldarg.0
0x2170f  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_index
0x21714  ldarg.0
0x21715  ldfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_count
0x2171a  ldc.i4.1
0x2171b  sub
0x2171c  bne.un.s loc_21752
0x2171e  ldarg.0
0x2171f  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_rect
0x21724  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Height()
0x21729  ldarg.0
0x2172a  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x2172f  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x21734  sub
0x21735  stloc.s  7
0x21737  ldarg.0
0x21738  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x2173d  ldarg.0
0x2173e  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_rect
0x21743  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x21748  ldloc.s  7
0x2174a  add
0x2174b  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Height(int32)
0x21750  br.s     loc_2176A
0x21752  ldarg.0
0x21753  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x21758  ldarg.0
0x21759  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x2175e  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Height()
0x21763  ldloc.0
0x21764  add
0x21765  call     instance void [WindowsBase]System.Windows.Int32Rect::set_Height(int32)
0x2176a  ldarg.0
0x2176b  dup
0x2176c  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x21771  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Y()
0x21776  ldarg.0
0x21777  ldflda   valuetype [WindowsBase]System.Windows.Int32Rect Microsoft.Internal.GDIExporter.BandIterator::_band
0x2177c  call     instance int32 [WindowsBase]System.Windows.Int32Rect::get_Height()
0x21781  add
0x21782  stfld    int32 Microsoft.Internal.GDIExporter.BandIterator::_prevBottom
0x21787  ldc.i4.1
0x21788  ret
0x21789  ldc.i4.0
0x2178a  ret
```
