# Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached

- ea: `0x207b0`
- end: `0x208bb`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::CreateFontCached`
- size: `267`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1ffe0`
- `0x208c0`
- `0x20a80`

## callees

- `0x1b990`
- `0x1bd70`
- `0x1cb20`
- `0x1cb60`
- `0x207b0`
- `0x20ac0`
- `0x21190`

## string_xrefs

- `0x207f6`: `CreateFontIndirectEx failed`
- `0x20876`: `CreateFontCached must never return a closed handle`
- `0x2088d`: `CreateFontCached must never return an invalide handle`
- `0x208af`: `CreateFontCached must never return null`

## pseudocode

```c

```

## disassembly

```asm
0x207b0  ldarg.0
0x207b1  ldarg.1
0x207b2  ldc.i4   0x1A4
0x207b7  call     instance class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CGDIDevice::CacheMatch(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size)
0x207bc  stloc.0
0x207bd  ldnull
0x207be  stloc.2
0x207bf  ldloc.0
0x207c0  brfalse.s loc_207C4
0x207c2  ldloc.0
0x207c3  ret
0x207c4  ldarg.1
0x207c5  ldc.i4.s 0x1C
0x207c7  conv.i8
0x207c8  add
0x207c9  stloc.s  0xB
0x207cb  ldloc.s  0xB
0x207cd  newobj   instance void [mscorlib]System.String::.ctor(char*)
0x207d2  stloc.s  6
0x207d4  ldloca.s 0xC
0x207d6  ldarg.1
0x207d7  ldc.i4   0x1A4
0x207dc  unaligned. 4
0x207df  cpblk
0x207e1  ldc.i4.0
0x207e2  stloc.3
0x207e3  ldarg.1
0x207e4  call     class Microsoft.Internal.GDIExporter.GdiSafeHandle Microsoft.Internal.GDIExporter.CNativeMethods::CreateFontIndirectExW(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) valuetype tagENUMLOGFONTEXDVW* penumlfex)
0x207e9  stloc.1
0x207ea  ldloc.1
0x207eb  ldnull
0x207ec  bne.un.s loc_207F1
0x207ee  ldc.i4.0
0x207ef  br.s     loc_207F2
0x207f1  ldc.i4.1
0x207f2  stloc.s  0xA
0x207f4  ldloc.s  0xA
0x207f6  ldstr    aCreatefontindi// "CreateFontIndirectEx failed"
0x207fb  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20800  ldloc.1
0x20801  brfalse.s loc_20841
0x20803  ldloc.2
0x20804  brtrue.s loc_20808
0x20806  ldloc.1
0x20807  stloc.2
0x20808  ldloc.s  6
0x2080a  ldnull
0x2080b  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20810  brfalse.s loc_20834
0x20812  ldarg.0
0x20813  ldloc.1
0x20814  call     instance string Microsoft.Internal.GDIExporter.CGDIRenderTarget::GetFontFace(class Microsoft.Internal.GDIExporter.GdiSafeHandle font)
0x20819  stloc.s  5
0x2081b  ldloc.s  5
0x2081d  ldnull
0x2081e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x20823  brfalse.s loc_20834
0x20825  ldc.i4.0
0x20826  ldloc.s  6
0x20828  ldloc.s  5
0x2082a  ldc.i4.5
0x2082b  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x20830  bne.un.s loc_20834
0x20832  ldloc.1
0x20833  stloc.0
0x20834  ldloc.0
0x20835  brtrue.s loc_20855
0x20837  ldloc.1
0x20838  ldloc.2
0x20839  beq.s    loc_20841
0x2083b  ldloc.1
0x2083c  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x20841  ldloc.3
0x20842  stloc.s  9
0x20844  ldloc.3
0x20845  ldc.i4.1
0x20846  add
0x20847  stloc.3
0x20848  ldarg.0
0x20849  ldarg.1
0x2084a  ldloc.s  9
0x2084c  call     instance bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::SetLOGFONT([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) valuetype tagENUMLOGFONTEXDVW& value, int32 logfontdv)
0x20851  brfalse.s loc_20864
0x20853  br.s     loc_207E3
0x20855  ldloc.0
0x20856  ldloc.2
0x20857  beq.s    loc_20866
0x20859  ldloc.2
0x2085a  brfalse.s loc_20866
0x2085c  ldloc.2
0x2085d  call     instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Close()
0x20862  br.s     loc_20866
0x20864  ldloc.2
0x20865  stloc.0
0x20866  ldloc.0
0x20867  brfalse.s loc_208AA
0x20869  ldloc.0
0x2086a  call     instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsClosed()
0x2086f  ldc.i4.0
0x20870  ceq
0x20872  stloc.s  8
0x20874  ldloc.s  8
0x20876  ldstr    aCreatefontcach// "CreateFontCached must never return a cl"...
0x2087b  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20880  ldloc.0
0x20881  callvirt instance bool Microsoft.Internal.GDIExporter.GdiSafeHandle::get_IsInvalid()
0x20886  ldc.i4.0
0x20887  ceq
0x20889  stloc.s  7
0x2088b  ldloc.s  7
0x2088d  ldstr    aCreatefontcach_0// "CreateFontCached must never return an i"...
0x20892  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x20897  ldarg.0
0x20898  ldloca.s 0xC
0x2089a  ldc.i4   0x1A4
0x2089f  ldloc.0
0x208a0  call     instance void Microsoft.Internal.GDIExporter.CGDIDevice::CacheObject(modopt([mscorlib]System.Runtime.CompilerServices.IsConst) modopt([mscorlib]System.Runtime.CompilerServices.IsExplicitlyDereferenced) unsigned int8& pData, int32 size, class Microsoft.Internal.GDIExporter.GdiSafeHandle handle)
0x208a5  ldc.i4.1
0x208a6  stloc.s  4
0x208a8  br.s     loc_208AD
0x208aa  ldc.i4.0
0x208ab  stloc.s  4
0x208ad  ldloc.s  4
0x208af  ldstr    aCreatefontcach_1// "CreateFontCached must never return null"
0x208b4  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x208b9  ldloc.0
0x208ba  ret
```
