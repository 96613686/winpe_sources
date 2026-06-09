# Microsoft.Internal.GDIExporter.FontInstallInfo::Uninstall

- ea: `0x22be0`
- end: `0x22c35`
- name: `Microsoft.Internal.GDIExporter.FontInstallInfo::Uninstall`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x22d60`

## callees

- `0x1be10`
- `0x1c2d0`
- `0x22be0`

## string_xrefs

- `0x22c12`: `RemoveFontResourceEx failed`

## pseudocode

```c

```

## disassembly

```asm
0x22be0  ldarg.1
0x22be1  ldnull
0x22be2  bne.un.s loc_22BE7
0x22be4  ldc.i4.0
0x22be5  br.s     loc_22BE8
0x22be7  ldc.i4.1
0x22be8  stloc.3
0x22be9  ldloc.3
0x22bea  call     void [System]System.Diagnostics.Debug::Assert(bool)
0x22bef  ldarg.1
0x22bf0  isinst   [mscorlib]System.String
0x22bf5  stloc.1
0x22bf6  ldloc.1
0x22bf7  ldnull
0x22bf8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22bfd  brfalse.s loc_22C1E
0x22bff  ldloc.1
0x22c00  ldc.i4.s 0x30
0x22c02  ldc.i4.0
0x22c03  conv.i8
0x22c04  call     int32 Microsoft.Internal.GDIExporter.CNativeMethods::RemoveFontResourceExW([hasfieldmarshal] modopt([mscorlib]System.Runtime.CompilerServices.IsConst) string fileName, modopt([mscorlib]System.Runtime.CompilerServices.IsLong) unsigned int32 fl, modopt([mscorlib]System.Runtime.CompilerServices.IsConst) unsigned int8* pdv)
0x22c09  ldc.i4.0
0x22c0a  bne.un.s loc_22C0F
0x22c0c  ldc.i4.0
0x22c0d  br.s     loc_22C10
0x22c0f  ldc.i4.1
0x22c10  stloc.2
0x22c11  ldloc.2
0x22c12  ldstr    aRemovefontreso// "RemoveFontResourceEx failed"
0x22c17  call     void [System]System.Diagnostics.Debug::Assert(bool, string)
0x22c1c  br.s     loc_22C34
0x22c1e  ldarg.1
0x22c1f  isinst   Microsoft.Internal.GDIExporter.GdiFontResourceSafeHandle
0x22c24  stloc.0
0x22c25  ldloc.0
0x22c26  brfalse.s loc_22C34
0x22c28  call     class [mscorlib]System.Collections.ArrayList Microsoft.Internal.GDIExporter.CGDIDevice::get_OldPrivateFonts()
0x22c2d  ldloc.0
0x22c2e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x22c33  pop
0x22c34  ret
```
