# System.Web.Compilation.WCFModel.MetadataFile::GetDefaultFileName

- ea: `0x2980`
- end: `0x2a0b`
- name: `System.Web.Compilation.WCFModel.MetadataFile::GetDefaultFileName`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x2880`
- `0x2920`
- `0x2980`

## string_xrefs

- `0x2a05`: `service`

## pseudocode

```c

```

## disassembly

```asm
0x2980  ldarg.0
0x2981  call     instance string System.Web.Compilation.WCFModel.MetadataFile::get_TargetNamespace()
0x2986  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x298b  brtrue.s loc_2A05
0x298d  ldarg.0
0x298e  call     instance string System.Web.Compilation.WCFModel.MetadataFile::get_TargetNamespace()
0x2993  stloc.0
0x2994  ldloc.0
0x2995  ldstr    asc_3D26E// "/"
0x299a  ldc.i4.4
0x299b  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x29a0  brtrue.s loc_2A05
0x29a2  ldloc.0
0x29a3  call     char[] [mscorlib]System.IO.Path::GetInvalidFileNameChars()
0x29a8  callvirt instance int32 [mscorlib]System.String::LastIndexOfAny(char[])
0x29ad  stloc.1
0x29ae  ldloc.1
0x29af  ldc.i4.0
0x29b0  blt.s    loc_29BC
0x29b2  ldloc.0
0x29b3  ldloc.1
0x29b4  ldc.i4.1
0x29b5  add
0x29b6  callvirt instance string [mscorlib]System.String::Substring(int32)
0x29bb  stloc.0
0x29bc  ldstr    asc_3D206// "."
0x29c1  ldarg.0
0x29c2  call     instance string System.Web.Compilation.WCFModel.MetadataFile::GetDefaultExtension()
0x29c7  call     string [mscorlib]System.String::Concat(string, string)
0x29cc  stloc.2
0x29cd  ldloc.0
0x29ce  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29d3  ldloc.2
0x29d4  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29d9  ble.s    loc_29FA
0x29db  ldloc.0
0x29dc  ldloc.2
0x29dd  ldc.i4.5
0x29de  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x29e3  brfalse.s loc_29FA
0x29e5  ldloc.0
0x29e6  ldc.i4.0
0x29e7  ldloc.0
0x29e8  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29ed  ldloc.2
0x29ee  callvirt instance int32 [mscorlib]System.String::get_Length()
0x29f3  sub
0x29f4  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x29f9  stloc.0
0x29fa  ldloc.0
0x29fb  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2a00  ldc.i4.0
0x2a01  ble.s    loc_2A05
0x2a03  ldloc.0
0x2a04  ret
0x2a05  ldstr    aService// "service"
0x2a0a  ret
```
