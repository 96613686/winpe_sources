# FullTextLine::DrawTextLine

- ea: `0x156e10`
- end: `0x156f52`
- name: `FullTextLine::DrawTextLine`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: ``

## callers

- `0x156d70`
- `0x156fc0`

## callees

- `0xef6d0`
- `0xef700`
- `0xef720`
- `0xef730`
- `0xef990`
- `0x11b6d0`
- `0x11dea0`
- `0x11dec0`
- `0x11e220`
- `0x124f60`
- `0x146e70`
- `0x156e10`
- `0x156f60`
- `0x158c20`

## string_xrefs

- `0x156ed4`: `CreateLineFailure`

## pseudocode

```c

```

## disassembly

```asm
0x156e10  call     valuetype [WindowsBase]System.Windows.Rect [WindowsBase]System.Windows.Rect::get_Empty()
0x156e15  stloc.s  5
0x156e17  ldarg.0
0x156e18  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> FullTextLine::_ploline
0x156e1d  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0x156e22  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x156e27  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x156e2c  brfalse  loc_156EF9
0x156e31  ldc.i4.0
0x156e32  stloc.1
0x156e33  ldloca.s 8
0x156e35  ldc.i4.0
0x156e36  ldc.i4.0
0x156e37  ldarg.0
0x156e38  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156e3d  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_textWidthAtTrailing
0x156e42  ldarg.0
0x156e43  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156e48  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_height
0x156e4d  call     instance void MS.Internal.TextFormatting.LSRECT::.ctor(int32 x1, int32 y1, int32 x2, int32 y2)
0x156e52  ldarg.1
0x156e53  ldarg.2
0x156e54  ldarg.3
0x156e55  ldarg.0
0x156e56  newobj   instance void MS.Internal.TextFormatting.DrawingState::.ctor(class System.Windows.Media.DrawingContext drawingContext, valuetype [WindowsBase]System.Windows.Point lineOrigin, class System.Windows.Media.MatrixTransform antiInversion, class FullTextLine currentLine)
0x156e5b  stloc.2
0x156e5c  ldarg.0
0x156e5d  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156e62  ldfld    class MS.Internal.TextFormatting.TextFormatterImp MS.Internal.TextFormatting.TextMetrics::_formatter
0x156e67  ldloc.2
0x156e68  ldarg.0
0x156e69  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> FullTextLine::_ploc
0x156e6e  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0x156e73  callvirt instance class System.Windows.Media.TextFormatting.TextFormatterContext MS.Internal.TextFormatting.TextFormatterImp::AcquireContext(object owner, native int ploc)
0x156e78  stloc.0
0x156e79  ldloc.0
0x156e7a  callvirt instance void System.Windows.Media.TextFormatting.TextFormatterContext::EmptyBoundingBox()
0x156e7f  ldloca.s 7
0x156e81  ldc.i4.0
0x156e82  ldarg.0
0x156e83  ldflda   valuetype MS.Internal.TextFormatting.TextMetrics FullTextLine::_metrics
0x156e88  ldfld    int32 MS.Internal.TextFormatting.TextMetrics::_baselineOffset
0x156e8d  call     instance void MS.Internal.TextFormatting.LSPOINT::.ctor(int32 horizontalPosition, int32 verticalPosition)
0x156e92  ldarg.0
0x156e93  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int> FullTextLine::_ploline
0x156e98  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalDataForSet`1<native int>::get_Value()
0x156e9d  ldloca.s 7
0x156e9f  ldc.i4.1
0x156ea0  ldloca.s 8
0x156ea2  call     valuetype MS.Internal.TextFormatting.LsErr MS.Internal.TextFormatting.UnsafeNativeMethods::LoDisplayLine(native int ploline, valuetype MS.Internal.TextFormatting.LSPOINT& pt, unsigned int32 displayMode, valuetype MS.Internal.TextFormatting.LSRECT& clipRect)
0x156ea7  stloc.1
0x156ea8  leave.s  loc_156EB4
0x156eaa  ldloc.2
0x156eab  brfalse.s loc_156EB3
0x156ead  ldloc.2
0x156eae  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x156eb3  endfinally
0x156eb4  ldloc.0
0x156eb5  callvirt instance valuetype [WindowsBase]System.Windows.Rect System.Windows.Media.TextFormatting.TextFormatterContext::get_BoundingBox()
0x156eba  stloc.s  5
0x156ebc  ldloc.0
0x156ebd  callvirt instance class [mscorlib]System.Exception System.Windows.Media.TextFormatting.TextFormatterContext::get_CallbackException()
0x156ec2  stloc.s  4
0x156ec4  ldloc.0
0x156ec5  callvirt instance void System.Windows.Media.TextFormatting.TextFormatterContext::Release()
0x156eca  ldloc.1
0x156ecb  brfalse.s loc_156EF3
0x156ecd  ldloc.s  4
0x156ecf  brfalse.s loc_156ED4
0x156ed1  ldloc.s  4
0x156ed3  throw
0x156ed4  ldstr    aCreatelinefail// "CreateLineFailure"
0x156ed9  ldc.i4.1
0x156eda  newarr   [mscorlib]System.Object
0x156edf  dup
0x156ee0  ldc.i4.0
0x156ee1  ldloc.1
0x156ee2  box      MS.Internal.TextFormatting.LsErr
0x156ee7  stelem.ref
0x156ee8  call     string MS.Internal.PresentationCore.SR::Get(string id, object[] args)
0x156eed  ldloc.1
0x156eee  call     void System.Windows.Media.TextFormatting.TextFormatterContext::ThrowExceptionFromLsError(string message, valuetype MS.Internal.TextFormatting.LsErr lserr)
0x156ef3  ldloc.0
0x156ef4  call     void [mscorlib]System.GC::KeepAlive(object)
0x156ef9  ldarg.0
0x156efa  ldfld    class MS.Internal.TextFormatting.FormattedTextSymbols FullTextLine::_collapsingSymbol
0x156eff  brfalse.s loc_156F3A
0x156f01  ldloca.s 3
0x156f03  initobj  [WindowsBase]System.Windows.Point
0x156f09  ldarg.3
0x156f0a  brfalse.s loc_156F2A
0x156f0c  ldarg.2
0x156f0d  stloc.3
0x156f0e  ldarga.s 2
0x156f10  ldarga.s 2
0x156f12  ldc.r8   0.0
0x156f1b  dup
0x156f1c  stloc.s  6
0x156f1e  call     instance void [WindowsBase]System.Windows.Point::set_Y(float64)
0x156f23  ldloc.s  6
0x156f25  call     instance void [WindowsBase]System.Windows.Point::set_X(float64)
0x156f2a  ldloca.s 5
0x156f2c  ldarg.0
0x156f2d  ldarg.1
0x156f2e  ldarg.2
0x156f2f  ldloc.3
0x156f30  call     instance valuetype [WindowsBase]System.Windows.Rect FullTextLine::DrawCollapsingSymbol(class System.Windows.Media.DrawingContext drawingContext, valuetype [WindowsBase]System.Windows.Point lineOrigin, valuetype [WindowsBase]System.Windows.Point vectorToLineOrigin)
0x156f35  call     instance void [WindowsBase]System.Windows.Rect::Union(valuetype [WindowsBase]System.Windows.Rect)
0x156f3a  ldarg.0
0x156f3b  ldarg.2
0x156f3c  ldloc.s  5
0x156f3e  call     instance void FullTextLine::BuildOverhang(valuetype [WindowsBase]System.Windows.Point origin, valuetype [WindowsBase]System.Windows.Rect boundingBox)
0x156f43  ldarg.0
0x156f44  ldarg.0
0x156f45  ldfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156f4a  ldc.i4.4
0x156f4b  or
0x156f4c  stfld    valuetype StatusFlags FullTextLine::_statusFlags
0x156f51  ret
```
