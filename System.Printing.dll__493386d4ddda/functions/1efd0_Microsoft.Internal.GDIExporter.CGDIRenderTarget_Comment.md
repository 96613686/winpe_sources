# Microsoft.Internal.GDIExporter.CGDIRenderTarget::Comment

- ea: `0x1efd0`
- end: `0x1f02d`
- name: `Microsoft.Internal.GDIExporter.CGDIRenderTarget::Comment`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1bdd0`
- `0x1cf70`
- `0x1efd0`

## string_xrefs

- `0x1efde`: `StartPage has not been called yet (Comment).`
- `0x1f019`: `GdiComment failed`

## pseudocode

```c

```

## disassembly

```asm
0x1efd0  ldarg.0
0x1efd1  call     instance bool Microsoft.Internal.GDIExporter.CGDIDevice::get_HasDC()
0x1efd6  brfalse.s loc_1F02C
0x1efd8  ldarg.0
0x1efd9  ldfld    bool Microsoft.Internal.GDIExporter.CGDIRenderTarget::m_startPage
0x1efde  ldstr    aStartpageHasNo_6// "StartPage has not been called yet (Comm"...
0x1efe3  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1efe8  ldarg.1
0x1efe9  ldnull
0x1efea  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x1efef  brfalse.s loc_1F02C
0x1eff1  ldarg.1
0x1eff2  call     native int [mscorlib]System.Runtime.InteropServices.Marshal::StringToCoTaskMemAnsi(string)
0x1eff7  stloc.1
0x1eff8  ldarg.0
0x1eff9  ldfld    class Microsoft.Internal.GDIExporter.GdiSafeDCHandle Microsoft.Internal.GDIExporter.CGDIDevice::m_hDC
0x1effe  ldarg.1
0x1efff  call     instance int32 [mscorlib]System.String::get_Length()
0x1f004  ldloca.s 1
0x1f006  call     instance void* [mscorlib]System.IntPtr::ToPointer()
0x1f00b  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::GdiComment(class Microsoft.Internal.GDIExporter.GdiSafeDCHandle hdc, unsigned int32 nSize, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int8* pData)
0x1f010  ldc.i4.0
0x1f011  bne.un.s loc_1F016
0x1f013  ldc.i4.0
0x1f014  br.s     loc_1F017
0x1f016  ldc.i4.1
0x1f017  stloc.0
0x1f018  ldloc.0
0x1f019  ldstr    aGdicommentFail// "GdiComment failed"
0x1f01e  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x1f023  leave.s  loc_1F02C
0x1f025  ldloc.1
0x1f026  call     void [mscorlib]System.Runtime.InteropServices.Marshal::FreeCoTaskMem(native int)
0x1f02b  endfinally
0x1f02c  ret
```
