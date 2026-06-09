# Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontW

- ea: `0x1ffe0`
- end: `0x201bc`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontW`
- size: `476`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x20530`

## callees

- `0x1620`
- `0x1ce80`
- `0x1ffe0`
- `0x207b0`
- `0x208c0`

## pseudocode

```c

```

## disassembly

```asm
0x1ffe0  ldarg.1
0x1ffe1  call     instance class [PresentationCore]System.Windows.Media.GlyphTypeface [PresentationCore]System.Windows.Media.GlyphRun::get_GlyphTypeface()
0x1ffe6  stloc.0
0x1ffe7  ldstr    aEnUs// "en-US"
0x1ffec  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::GetCultureInfo(string)
0x1fff1  stloc.s  5
0x1fff3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InstalledUICulture()
0x1fff8  stloc.s  6
0x1fffa  ldloc.0
0x1fffb  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string> [PresentationCore]System.Windows.Media.GlyphTypeface::get_Win32FamilyNames()
0x20000  ldloc.s  6
0x20002  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string>::get_Item(void)
0x20007  stloc.1
0x20008  ldloc.1
0x20009  ldnull
0x2000a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2000f  brfalse.s loc_2001F
0x20011  ldloc.0
0x20012  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string> [PresentationCore]System.Windows.Media.GlyphTypeface::get_Win32FamilyNames()
0x20017  ldloc.s  5
0x20019  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string>::get_Item(void)
0x2001e  stloc.1
0x2001f  ldloc.0
0x20020  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string> [PresentationCore]System.Windows.Media.GlyphTypeface::get_Win32FaceNames()
0x20025  ldloc.s  6
0x20027  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string>::get_Item(void)
0x2002c  stloc.s  4
0x2002e  ldloc.s  4
0x20030  ldnull
0x20031  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20036  brfalse.s loc_20047
0x20038  ldloc.0
0x20039  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string> [PresentationCore]System.Windows.Media.GlyphTypeface::get_Win32FaceNames()
0x2003e  ldloc.s  5
0x20040  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string>::get_Item(void)
0x20045  stloc.s  4
0x20047  ldloc.0
0x20048  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string> [PresentationCore]System.Windows.Media.GlyphTypeface::get_Win32FaceNames()
0x2004d  ldloc.s  5
0x2004f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<class [mscorlib]System.Globalization.CultureInfo, string>::get_Item(void)
0x20054  ldstr    aRegular// "Regular"
0x20059  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2005e  brfalse.s loc_20075
0x20060  ldloc.1
0x20061  ldstr    asc_261BA// " "
0x20066  call     string [mscorlib]System.String::Concat(string, string)
0x2006b  ldloc.s  4
0x2006d  call     string [mscorlib]System.String::Concat(string, string)
0x20072  stloc.3
0x20073  br.s     loc_20077
0x20075  ldloc.1
0x20076  stloc.3
0x20077  ldarg.0
0x20078  ldloc.0
0x20079  ldloc.3
0x2007a  ldarg.s  4
0x2007c  call     instance string Microsoft.Internal.GDIExporter.CGDIDevice::CheckFont(class [PresentationCore]System.Windows.Media.GlyphTypeface typeface, string name, [out] bool& isPrivateFont)
0x20081  stloc.2
0x20082  ldloc.2
0x20083  ldnull
0x20084  call     bool [mscorlib]System.String::op_Equality(string, string)
0x20089  brfalse.s loc_2008D
0x2008b  ldnull
0x2008c  ret
0x2008d  ldloc.2
0x2008e  ldloc.3
0x2008f  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20094  brfalse.s loc_20098
0x20096  ldloc.2
0x20097  stloc.1
0x20098  ldloca.s 0xA
0x2009a  ldc.i4.0
0x2009b  ldc.i4   0x1A4
0x200a0  conv.i8
0x200a1  unaligned. 4
0x200a4  initblk
0x200a6  ldloca.s 0xA
0x200a8  ldc.i4.s 0x1A
0x200aa  add
0x200ab  ldc.i4.2
0x200ac  stind.i1
0x200ad  ldloca.s 0xA
0x200af  ldc.i4.s 0x1B
0x200b1  add
0x200b2  ldc.i4.0
0x200b3  stind.i1
0x200b4  ldloc.0
0x200b5  call     instance bool [PresentationCore]System.Windows.Media.GlyphTypeface::get_Symbol()
0x200ba  brfalse.s loc_200CC
0x200bc  ldloca.s 0xA
0x200be  ldc.i4.s 0x17
0x200c0  add
0x200c1  ldc.i4.2
0x200c2  stind.i1
0x200c3  ldloca.s 0xA
0x200c5  ldc.i4.s 0x18
0x200c7  add
0x200c8  ldc.i4.8
0x200c9  stind.i1
0x200ca  br.s     loc_200DA
0x200cc  ldloca.s 0xA
0x200ce  ldc.i4.s 0x17
0x200d0  add
0x200d1  ldc.i4.1
0x200d2  stind.i1
0x200d3  ldloca.s 0xA
0x200d5  ldc.i4.s 0x18
0x200d7  add
0x200d8  ldc.i4.4
0x200d9  stind.i1
0x200da  call     valuetype [PresentationCore]System.Windows.FontStyle [PresentationCore]System.Windows.FontStyles::get_Normal()
0x200df  stloc.s  8
0x200e1  ldloc.0
0x200e2  call     instance valuetype [PresentationCore]System.Windows.FontStyle [PresentationCore]System.Windows.Media.GlyphTypeface::get_Style()
0x200e7  stloc.s  7
0x200e9  ldloca.s 0xA
0x200eb  ldc.i4.s 0x14
0x200ed  add
0x200ee  ldloc.s  7
0x200f0  ldloc.s  8
0x200f2  call     bool [PresentationCore]System.Windows.FontStyle::op_Inequality(valuetype [PresentationCore]System.Windows.FontStyle, valuetype [PresentationCore]System.Windows.FontStyle)
0x200f7  ldc.i4.0
0x200f8  bne.un.s loc_20102
0x200fa  ldloca.s 0xA
0x200fc  ldc.i4.s 0x14
0x200fe  add
0x200ff  ldind.u1
0x20100  br.s     loc_20103
0x20102  ldc.i4.1
0x20103  stind.i1
0x20104  ldloca.s 0xA
0x20106  ldc.i4.s 0xC
0x20108  add
0x20109  ldarg.1
0x2010a  call     instance bool [PresentationCore]System.Windows.Media.GlyphRun::get_IsSideways()
0x2010f  ldc.i4.0
0x20110  bne.un.s loc_2011A
0x20112  ldloca.s 0xA
0x20114  ldc.i4.s 0xC
0x20116  add
0x20117  ldind.i4
0x20118  br.s     loc_2011F
0x2011a  ldc.i4   0x384
0x2011f  stind.i4
0x20120  ldloc.0
0x20121  call     instance valuetype [PresentationCore]System.Windows.FontWeight [PresentationCore]System.Windows.Media.GlyphTypeface::get_Weight()
0x20126  stloc.s  9
0x20128  ldloca.s 0xA
0x2012a  ldc.i4.s 0x10
0x2012c  add
0x2012d  ldloca.s 9
0x2012f  call     instance int32 [PresentationCore]System.Windows.FontWeight::ToOpenTypeWeight()
0x20134  stind.i4
0x20135  ldloca.s 0xA
0x20137  ldarg.2
0x20138  ldarg.3
0x20139  mul
0x2013a  call     float64 [mscorlib]System.Math::Round(float64)
0x2013f  conv.i4
0x20140  neg
0x20141  stind.i4
0x20142  ldloc.0
0x20143  callvirt instance valuetype [PresentationCore]System.Windows.Media.StyleSimulations [PresentationCore]System.Windows.Media.GlyphTypeface::get_StyleSimulations()
0x20148  ldc.i4.2
0x20149  and
0x2014a  brfalse.s loc_2015D
0x2014c  ldloca.s 0xA
0x2014e  ldc.i4.s 0x14
0x20150  add
0x20151  ldind.u1
0x20152  brfalse.s loc_20156
0x20154  ldnull
0x20155  ret
0x20156  ldloca.s 0xA
0x20158  ldc.i4.s 0x14
0x2015a  add
0x2015b  ldc.i4.1
0x2015c  stind.i1
0x2015d  ldloc.0
0x2015e  callvirt instance valuetype [PresentationCore]System.Windows.Media.StyleSimulations [PresentationCore]System.Windows.Media.GlyphTypeface::get_StyleSimulations()
0x20163  ldc.i4.1
0x20164  and
0x20165  brfalse.s loc_20188
0x20167  ldloca.s 0xA
0x20169  ldc.i4.s 0x10
0x2016b  add
0x2016c  ldloca.s 0xA
0x2016e  ldc.i4.s 0x10
0x20170  add
0x20171  ldind.i4
0x20172  ldc.i4   0x12C
0x20177  add
0x20178  stind.i4
0x20179  ldloca.s 0xA
0x2017b  ldc.i4.s 0x10
0x2017d  add
0x2017e  ldind.i4
0x2017f  ldc.i4   0x384
0x20184  ble.s    loc_20188
0x20186  ldnull
0x20187  ret
0x20188  ldloca.s 0xA
0x2018a  ldc.i4.s 0x1C
0x2018c  add
0x2018d  ldc.i4.s 0x1F
0x2018f  ldloc.1
0x20190  call     void Microsoft.Internal.GDIExporter.CopyTo(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int16& buffer, int32 len, string s)
0x20195  ldloc.0
0x20196  callvirt instance valuetype [PresentationCore]System.Windows.Media.StyleSimulations [PresentationCore]System.Windows.Media.GlyphTypeface::get_StyleSimulations()
0x2019b  brtrue.s loc_201A7
0x2019d  ldarg.0
0x2019e  ldloca.s 0xA
0x201a0  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv)
0x201a5  br.s     loc_201B5
0x201a7  ldarg.0
0x201a8  ldloca.s 0xA
0x201aa  ldloc.0
0x201ab  callvirt instance valuetype [PresentationCore]System.Windows.Media.StyleSimulations [PresentationCore]System.Windows.Media.GlyphTypeface::get_StyleSimulations()
0x201b0  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateSimulatedStyleFont(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv, valuetype [PresentationCore]System.Windows.Media.StyleSimulations styleSimulations)
0x201b5  ldarg.0
0x201b6  call     void [mscorlib]System.GC::KeepAlive(object)
0x201bb  ret
```
