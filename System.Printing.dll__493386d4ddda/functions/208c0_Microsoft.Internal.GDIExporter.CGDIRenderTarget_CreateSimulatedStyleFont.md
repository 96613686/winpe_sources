# Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateSimulatedStyleFont

- ea: `0x208c0`
- end: `0x20a74`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateSimulatedStyleFont`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1ffe0`

## callees

- `0x207b0`
- `0x208c0`
- `0x20a80`
- `0x20b00`
- `0x20b60`
- `0x21310`

## string_xrefs

- `0x2094e`: `CreateUnstyledFont failed`
- `0x20a35`: `CreateFontCached failed`

## pseudocode

```c

```

## disassembly

```asm
0x208c0  ldnull
0x208c1  stloc.0
0x208c2  ldarg.1
0x208c3  ldc.i4.s 0x10
0x208c5  conv.i8
0x208c6  add
0x208c7  ldind.i4
0x208c8  ldc.i4   0x2BC
0x208cd  bne.un.s loc_208DF
0x208cf  ldarg.2
0x208d0  ldc.i4.1
0x208d1  and
0x208d2  brfalse.s loc_208DF
0x208d4  ldarg.1
0x208d5  ldc.i4.s 0x10
0x208d7  conv.i8
0x208d8  add
0x208d9  ldc.i4   0x258
0x208de  stind.i4
0x208df  ldarg.1
0x208e0  ldc.i4.s 0x1C
0x208e2  conv.i8
0x208e3  add
0x208e4  stloc.s  8
0x208e6  ldloc.s  8
0x208e8  newobj   instance void [mscorlib]System.String::.ctor(char*)
0x208ed  stloc.s  6
0x208ef  ldloc.s  6
0x208f1  ldarg.1
0x208f2  ldc.i4.s 0x10
0x208f4  conv.i8
0x208f5  add
0x208f6  ldind.i4
0x208f7  ldarg.1
0x208f8  ldc.i4.s 0x14
0x208fa  conv.i8
0x208fb  add
0x208fc  ldind.u1
0x208fd  newobj   instance void FontSimulatedStyleKey::.ctor(string faceName, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) int32 lfWeight, unsigned int8 lfItalic)
0x20902  stloc.s  4
0x20904  ldarg.0
0x20905  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_cachedUnstyledFontCharsets
0x2090a  ldloc.s  4
0x2090c  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x20911  brfalse.s loc_20938
0x20913  ldarg.0
0x20914  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_cachedUnstyledFontCharsets
0x20919  ldloc.s  4
0x2091b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x20920  unbox    [mscorlib]System.Byte
0x20925  ldind.u1
0x20926  stloc.s  7
0x20928  ldarg.1
0x20929  ldc.i4.s 0x17
0x2092b  conv.i8
0x2092c  add
0x2092d  ldloc.s  7
0x2092f  stind.i1
0x20930  ldarg.0
0x20931  ldarg.1
0x20932  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv)
0x20937  stloc.0
0x20938  ldloc.0
0x20939  brtrue   loc_20A72
0x2093e  ldnull
0x2093f  stloc.3
0x20940  ldarg.0
0x20941  ldarg.1
0x20942  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateUnstyledFont(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv)
0x20947  stloc.s  5
0x20949  ldloc.s  5
0x2094b  brtrue.s loc_2095A
0x2094d  ldc.i4.0
0x2094e  ldstr    aCreateunstyled// "CreateUnstyledFont failed"
0x20953  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20958  br.s     loc_20963
0x2095a  ldarg.0
0x2095b  ldloc.s  5
0x2095d  call     instance string Microsoft.Internal.GDIExporter.CGDIRenderTarget::GetFontStyle(class Microsoft.Internal.GDIExporter.GdiSafeHandle font)
0x20962  stloc.3
0x20963  ldloc.3
0x20964  ldnull
0x20965  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2096a  brfalse  loc_20A72
0x2096f  ldloca.s 9
0x20971  ldc.i4   0xB2
0x20976  stind.i1
0x20977  ldloca.s 9
0x20979  ldc.i4.1
0x2097a  add
0x2097b  ldc.i4   0xB1
0x20980  stind.i1
0x20981  ldloca.s 9
0x20983  ldc.i4.2
0x20984  add
0x20985  ldc.i4   0xDE
0x2098a  stind.i1
0x2098b  ldloca.s 9
0x2098d  ldc.i4.3
0x2098e  add
0x2098f  ldc.i4   0xBA
0x20994  stind.i1
0x20995  ldloca.s 9
0x20997  ldc.i4.4
0x20998  add
0x20999  ldc.i4   0x88
0x2099e  stind.i1
0x2099f  ldloca.s 9
0x209a1  ldc.i4.5
0x209a2  add
0x209a3  ldc.i4   0xEE
0x209a8  stind.i1
0x209a9  ldloca.s 9
0x209ab  ldc.i4.6
0x209ac  add
0x209ad  ldc.i4   0x86
0x209b2  stind.i1
0x209b3  ldloca.s 9
0x209b5  ldc.i4.7
0x209b6  add
0x209b7  ldc.i4   0xA1
0x209bc  stind.i1
0x209bd  ldloca.s 9
0x209bf  ldc.i4.8
0x209c0  add
0x209c1  ldc.i4   0x81
0x209c6  stind.i1
0x209c7  ldloca.s 9
0x209c9  ldc.i4.s 9
0x209cb  add
0x209cc  ldc.i4.s 0x4D
0x209ce  stind.i1
0x209cf  ldloca.s 9
0x209d1  ldc.i4.s 0xA
0x209d3  add
0x209d4  ldc.i4   0xFF
0x209d9  stind.i1
0x209da  ldloca.s 9
0x209dc  ldc.i4.s 0xB
0x209de  add
0x209df  ldc.i4   0xCC
0x209e4  stind.i1
0x209e5  ldloca.s 9
0x209e7  ldc.i4.s 0xC
0x209e9  add
0x209ea  ldc.i4   0x80
0x209ef  stind.i1
0x209f0  ldloca.s 9
0x209f2  ldc.i4.s 0xD
0x209f4  add
0x209f5  ldc.i4.2
0x209f6  stind.i1
0x209f7  ldloca.s 9
0x209f9  ldc.i4.s 0xE
0x209fb  add
0x209fc  ldc.i4   0xA2
0x20a01  stind.i1
0x20a02  ldloca.s 9
0x20a04  ldc.i4.s 0xF
0x20a06  add
0x20a07  ldc.i4   0xA3
0x20a0c  stind.i1
0x20a0d  ldloca.s 9
0x20a0f  ldc.i4.s 0x10
0x20a11  add
0x20a12  ldc.i4   0x82
0x20a17  stind.i1
0x20a18  ldc.i4.0
0x20a19  conv.i8
0x20a1a  stloc.1
0x20a1b  ldloc.0
0x20a1c  brtrue.s loc_20A72
0x20a1e  ldarg.1
0x20a1f  ldc.i4.s 0x17
0x20a21  conv.i8
0x20a22  add
0x20a23  ldloc.1
0x20a24  ldloca.s 9
0x20a26  add
0x20a27  ldind.u1
0x20a28  stind.i1
0x20a29  ldarg.0
0x20a2a  ldarg.1
0x20a2b  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached(modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& logfontdv)
0x20a30  stloc.2
0x20a31  ldloc.2
0x20a32  brtrue.s loc_20A41
0x20a34  ldc.i4.0
0x20a35  ldstr    aCreatefontcach_2// "CreateFontCached failed"
0x20a3a  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20a3f  br.s     loc_20A67
0x20a41  ldarg.0
0x20a42  ldloc.2
0x20a43  ldloc.s  6
0x20a45  ldloc.3
0x20a46  call     instance bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::CheckFontFaceAndStyle([hasfieldmarshal] class Microsoft.Internal.GDIExporter.GdiSafeHandle value, string font, string fontFace)
0x20a4b  brfalse.s loc_20A67
0x20a4d  ldloc.2
0x20a4e  stloc.0
0x20a4f  ldarg.0
0x20a50  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_cachedUnstyledFontCharsets
0x20a55  ldloc.s  4
0x20a57  ldarg.1
0x20a58  ldc.i4.s 0x17
0x20a5a  conv.i8
0x20a5b  add
0x20a5c  ldind.u1
0x20a5d  box      [mscorlib]System.Byte
0x20a62  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x20a67  ldloc.1
0x20a68  ldc.i4.1
0x20a69  conv.i8
0x20a6a  add
0x20a6b  stloc.1
0x20a6c  ldloc.1
0x20a6d  ldc.i4.s 0x11
0x20a6f  conv.i8
0x20a70  blt.s    loc_20A1B
0x20a72  ldloc.0
0x20a73  ret
```
