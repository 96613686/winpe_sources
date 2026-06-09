# System.Windows.SystemParameters::InvalidateCache_0

- ea: `0x27f60`
- end: `0x28ba9`
- name: `System.Windows.SystemParameters::InvalidateCache_0`
- size: `3145`
- prototype: ``
- caller_count: `2`
- callee_count: `52`
- tags: `broker_com_uri`

## callers

- `0x27c40`
- `0x2bb80`

## callees

- `0x23ef0`
- `0x23f00`
- `0x241b0`
- `0x241e0`
- `0x25af0`
- `0x25b40`
- `0x25b90`
- `0x25be0`
- `0x25c30`
- `0x25c80`
- `0x25d70`
- `0x25dc0`
- `0x25e10`
- `0x25e60`
- `0x25f70`
- `0x25fc0`
- `0x26010`
- `0x26060`
- `0x260b0`
- `0x26100`
- `0x26150`
- `0x26260`
- `0x262c0`
- `0x26320`
- `0x26370`
- `0x263c0`
- `0x26410`
- `0x26460`
- `0x264c0`
- `0x26520`
- `0x26580`
- `0x265e0`
- `0x26630`
- `0x26680`
- `0x266e0`
- `0x267e0`
- `0x26840`
- `0x26890`
- `0x268e0`
- `0x26930`
- `0x26980`
- `0x269d0`
- `0x26a20`
- `0x26b30`
- `0x26b80`
- `0x26bd0`
- `0x26c90`
- `0x26cf0`
- `0x26e00`
- `0x27ce0`

## string_xrefs

- `0x2839e`: `ComboBoxAnimation`

## pseudocode

```c

```

## disassembly

```asm
0x27f60  ldarg.0
0x27f61  ldc.i4.s 0x45
0x27f63  bgt      loc_27FF3
0x27f68  ldarg.0
0x27f69  ldc.i4.s 0x21
0x27f6b  bgt.s    loc_27FA3
0x27f6d  ldarg.0
0x27f6e  ldc.i4.s 0xB
0x27f70  bgt.s    loc_27F86
0x27f72  ldarg.0
0x27f73  ldc.i4.6
0x27f74  beq      loc_2846C
0x27f79  ldarg.0
0x27f7a  ldc.i4.s 0xB
0x27f7c  beq      loc_282E7
0x27f81  br       loc_28BA7
0x27f86  ldarg.0
0x27f87  ldc.i4.s 0x17
0x27f89  beq      loc_282CD
0x27f8e  ldarg.0
0x27f8f  ldc.i4.s 0x1C
0x27f91  beq      loc_28335
0x27f96  ldarg.0
0x27f97  ldc.i4.s 0x21
0x27f99  beq      loc_28B9A
0x27f9e  br       loc_28BA7
0x27fa3  ldarg.0
0x27fa4  ldc.i4.s 0x31
0x27fa6  bgt.s    loc_27FD6
0x27fa8  ldarg.0
0x27fa9  ldc.i4.s 0x25
0x27fab  beq      loc_2845F
0x27fb0  ldarg.0
0x27fb1  ldc.i4.s 0x2A
0x27fb3  beq      loc_2846C
0x27fb8  ldarg.0
0x27fb9  ldc.i4.s 0x2E
0x27fbb  sub
0x27fbc  switch   loc_281F3, loc_281ED, loc_28BA7, loc_28B80
0x27fd1  br       loc_28BA7
0x27fd6  ldarg.0
0x27fd7  ldc.i4.s 0x39
0x27fd9  beq      loc_28B8D
0x27fde  ldarg.0
0x27fdf  ldc.i4.s 0x43
0x27fe1  beq      loc_281BD
0x27fe6  ldarg.0
0x27fe7  ldc.i4.s 0x45
0x27fe9  beq      loc_282DA
0x27fee  br       loc_28BA7
0x27ff3  ldarg.0
0x27ff4  ldc.i4   0x1025
0x27ff9  bgt      loc_280EF
0x27ffe  ldarg.0
0x27fff  ldc.i4.s 0x6B
0x28001  bgt.s    loc_2805A
0x28003  ldarg.0
0x28004  ldc.i4.s 0x49
0x28006  sub
0x28007  switch   loc_28438, loc_28BA7, loc_28BA7, loc_28B66, loc_28B73
0x28020  ldarg.0
0x28021  ldc.i4.s 0x60
0x28023  beq      loc_282F4
0x28028  ldarg.0
0x28029  ldc.i4.s 0x63
0x2802b  sub
0x2802c  switch   loc_28328, loc_28BA7, loc_2831B, loc_28BA7, loc_2830E, loc_28BA7, loc_28301, loc_28BA7, loc_2838F
0x28055  br       loc_28BA7
0x2805a  ldarg.0
0x2805b  ldc.i4   0x1003
0x28060  sub
0x28061  switch   loc_283EA, loc_28BA7, loc_2839C, loc_28BA7, loc_283DD, loc_28BA7, loc_283C3, loc_28BA7, loc_282C0
0x2808a  ldarg.0
0x2808b  ldc.i4   0x100F
0x28090  sub
0x28091  switch   loc_283D0, loc_28BA7, loc_28404, loc_28BA7, loc_28382, loc_28BA7, loc_283F7, loc_28BA7, loc_28411, loc_28BA7, loc_2841E, loc_28BA7, loc_283B6
0x280ca  ldarg.0
0x280cb  ldc.i4   0x1021
0x280d0  sub
0x280d1  switch   loc_281C9, loc_28BA7, loc_281E1, loc_28BA7, loc_281D5
0x280ea  br       loc_28BA7
0x280ef  ldarg.0
0x280f0  ldc.i4   0x2005
0x280f5  bgt.s    loc_2811D
0x280f7  ldarg.0
0x280f8  ldc.i4   0x103F
0x280fd  beq      loc_2842B
0x28102  ldarg.0
0x28103  ldc.i4   0x1043
0x28108  beq      loc_283A9
0x2810d  ldarg.0
0x2810e  ldc.i4   0x2005
0x28113  beq      loc_28452
0x28118  br       loc_28BA7
0x2811d  ldarg.0
0x2811e  ldc.i4   0x2007
0x28123  beq      loc_28445
0x28128  ldarg.0
0x28129  ldc.i4   0x200F
0x2812e  beq.s    loc_2813D
0x28130  ldarg.0
0x28131  ldc.i4   0x2011
0x28136  beq.s    loc_281B1
0x28138  br       loc_28BA7
0x2813d  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x28142  ldc.i4.1
0x28143  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28148  stloc.0
0x28149  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2814e  ldc.i4.s 0x32
0x28150  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28155  brfalse.s loc_28169
0x28157  ldloc.0
0x28158  ldsfld   float64 System.Windows.SystemParameters::_focusHorizontalBorderHeight
0x2815d  call     float64 System.Windows.SystemParameters::get_FocusHorizontalBorderHeight()
0x28162  ceq
0x28164  ldc.i4.0
0x28165  ceq
0x28167  or
0x28168  stloc.0
0x28169  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2816e  ldc.i4.s 0x33
0x28170  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28175  brfalse.s loc_28189
0x28177  ldloc.0
0x28178  ldsfld   float64 System.Windows.SystemParameters::_focusVerticalBorderWidth
0x2817d  call     float64 System.Windows.SystemParameters::get_FocusVerticalBorderWidth()
0x28182  ceq
0x28184  ldc.i4.0
0x28185  ceq
0x28187  or
0x28188  stloc.0
0x28189  ldloc.0
0x2818a  brfalse.s loc_281AF
0x2818c  ldc.i4.3
0x2818d  newarr   [mscorlib]System.String
0x28192  dup
0x28193  ldc.i4.0
0x28194  ldstr    aFocusborderwid// "FocusBorderWidth"
0x28199  stelem.ref
0x2819a  dup
0x2819b  ldc.i4.1
0x2819c  ldstr    aFocushorizonta// "FocusHorizontalBorderHeight"
0x281a1  stelem.ref
0x281a2  dup
0x281a3  ldc.i4.2
0x281a4  ldstr    aFocusverticalb// "FocusVerticalBorderWidth"
0x281a9  stelem.ref
0x281aa  call     void System.Windows.SystemParameters::OnPropertiesChanged(string[] propertyNames)
0x281af  ldloc.0
0x281b0  ret
0x281b1  ldc.i4.2
0x281b2  ldstr    aFocusborderhei// "FocusBorderHeight"
0x281b7  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x281bc  ret
0x281bd  ldc.i4.3
0x281be  ldstr    aHighcontrast// "HighContrast"
0x281c3  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x281c8  ret
0x281c9  ldc.i4.4
0x281ca  ldstr    aMousevanish// "MouseVanish"
0x281cf  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x281d4  ret
0x281d5  ldc.i4.5
0x281d6  ldstr    aDropshadow// "DropShadow"
0x281db  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x281e0  ret
0x281e1  ldc.i4.6
0x281e2  ldstr    aFlatmenu// "FlatMenu"
0x281e7  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x281ec  ret
0x281ed  call     bool System.Windows.SystemParameters::InvalidateDisplayDependentCache()
0x281f2  ret
0x281f3  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x281f8  ldc.i4.s 9
0x281fa  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x281ff  stloc.1
0x28200  ldloc.1
0x28201  brfalse.s loc_28208
0x28203  call     void System.Windows.SystemFonts::InvalidateIconMetrics()
0x28208  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2820d  ldc.i4.s 0x39
0x2820f  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28214  brfalse.s loc_28228
0x28216  ldloc.1
0x28217  ldsfld   float64 System.Windows.SystemParameters::_iconWidth
0x2821c  call     float64 System.Windows.SystemParameters::get_IconWidth()
0x28221  ceq
0x28223  ldc.i4.0
0x28224  ceq
0x28226  or
0x28227  stloc.1
0x28228  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2822d  ldc.i4.s 0x3A
0x2822f  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28234  brfalse.s loc_28248
0x28236  ldloc.1
0x28237  ldsfld   float64 System.Windows.SystemParameters::_iconHeight
0x2823c  call     float64 System.Windows.SystemParameters::get_IconHeight()
0x28241  ceq
0x28243  ldc.i4.0
0x28244  ceq
0x28246  or
0x28247  stloc.1
0x28248  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2824d  ldc.i4.s 0x3B
0x2824f  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28254  brfalse.s loc_28268
0x28256  ldloc.1
0x28257  ldsfld   float64 System.Windows.SystemParameters::_iconGridWidth
0x2825c  call     float64 System.Windows.SystemParameters::get_IconGridWidth()
0x28261  ceq
0x28263  ldc.i4.0
0x28264  ceq
0x28266  or
0x28267  stloc.1
0x28268  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2826d  ldc.i4.s 0x3C
0x2826f  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28274  brfalse.s loc_28288
0x28276  ldloc.1
0x28277  ldsfld   float64 System.Windows.SystemParameters::_iconGridHeight
0x2827c  call     float64 System.Windows.SystemParameters::get_IconGridHeight()
0x28281  ceq
0x28283  ldc.i4.0
0x28284  ceq
0x28286  or
0x28287  stloc.1
0x28288  ldloc.1
0x28289  brfalse.s loc_282BE
0x2828b  ldc.i4.5
0x2828c  newarr   [mscorlib]System.String
0x28291  dup
0x28292  ldc.i4.0
0x28293  ldstr    aIconmetrics// "IconMetrics"
0x28298  stelem.ref
0x28299  dup
0x2829a  ldc.i4.1
0x2829b  ldstr    aIconwidth// "IconWidth"
0x282a0  stelem.ref
0x282a1  dup
0x282a2  ldc.i4.2
0x282a3  ldstr    aIconheight// "IconHeight"
0x282a8  stelem.ref
0x282a9  dup
0x282aa  ldc.i4.3
0x282ab  ldstr    aIcongridwidth// "IconGridWidth"
0x282b0  stelem.ref
0x282b1  dup
0x282b2  ldc.i4.4
0x282b3  ldstr    aIcongridheight// "IconGridHeight"
0x282b8  stelem.ref
0x282b9  call     void System.Windows.SystemParameters::OnPropertiesChanged(string[] propertyNames)
0x282be  ldloc.1
0x282bf  ret
0x282c0  ldc.i4.s 0xA
0x282c2  ldstr    aKeyboardcues// "KeyboardCues"
0x282c7  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x282cc  ret
0x282cd  ldc.i4.s 0xB
0x282cf  ldstr    aKeyboarddelay// "KeyboardDelay"
0x282d4  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x282d9  ret
0x282da  ldc.i4.s 0xC
0x282dc  ldstr    aKeyboardprefer// "KeyboardPreference"
0x282e1  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x282e6  ret
0x282e7  ldc.i4.s 0xD
0x282e9  ldstr    aKeyboardspeed// "KeyboardSpeed"
0x282ee  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x282f3  ret
0x282f4  ldc.i4.s 0xE
0x282f6  ldstr    aSnaptodefaultb// "SnapToDefaultButton"
0x282fb  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x28300  ret
0x28301  ldc.i4.s 0xF
0x28303  ldstr    aWheelscrolllin// "WheelScrollLines"
0x28308  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x2830d  ret
0x2830e  ldc.i4.s 0x10
0x28310  ldstr    aMousehovertime// "MouseHoverTime"
0x28315  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x2831a  ret
0x2831b  ldc.i4.s 0x11
0x2831d  ldstr    aMousehoverheig// "MouseHoverHeight"
0x28322  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x28327  ret
0x28328  ldc.i4.s 0x12
0x2832a  ldstr    aMousehoverwidt// "MouseHoverWidth"
0x2832f  call     bool System.Windows.SystemParameters::InvalidateProperty(int32 slot, string name)
0x28334  ret
0x28335  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x2833a  ldc.i4.s 0x13
0x2833c  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x28341  stloc.2
0x28342  ldsfld   class [mscorlib]System.Collections.BitArray System.Windows.SystemParameters::_cacheValid
0x28347  ldc.i4.s 0x61
0x28349  call     bool System.Windows.SystemResources::ClearSlot(class [mscorlib]System.Collections.BitArray cacheValid, int32 slot)
0x2834e  brfalse.s loc_28362
0x28350  ldloc.2
  ... truncated ...
```
