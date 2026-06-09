# <>c__DisplayClass420_0::<GetNativeProductVersion>b__0

- ea: `0x102b0`
- end: `0x1031a`
- name: `<>c__DisplayClass420_0::<GetNativeProductVersion>b__0`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task`

## string_xrefs

- `0x102b6`: `ReportingServicesNativeClient.dll`

## pseudocode

```c

```

## disassembly

```asm
0x102b0  ldarg.0
0x102b1  ldfld    string <>c__DisplayClass420_0::location
0x102b6  ldstr    aReportingservi_0// "ReportingServicesNativeClient.dll"
0x102bb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x102c0  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x102c5  stloc.0
0x102c6  ldarg.0
0x102c7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x102cc  ldstr    a00000100020000// "{0:0000}.{1:000}.{2:0000}.{3:00}"
0x102d1  ldc.i4.4
0x102d2  newarr   [mscorlib]System.Object
0x102d7  dup
0x102d8  ldc.i4.0
0x102d9  ldloc.0
0x102da  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FileMajorPart()
0x102df  box      [mscorlib]System.Int32
0x102e4  stelem.ref
0x102e5  dup
0x102e6  ldc.i4.1
0x102e7  ldloc.0
0x102e8  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FileMinorPart()
0x102ed  box      [mscorlib]System.Int32
0x102f2  stelem.ref
0x102f3  dup
0x102f4  ldc.i4.2
0x102f5  ldloc.0
0x102f6  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FileBuildPart()
0x102fb  box      [mscorlib]System.Int32
0x10300  stelem.ref
0x10301  dup
0x10302  ldc.i4.3
0x10303  ldloc.0
0x10304  callvirt instance int32 [System]System.Diagnostics.FileVersionInfo::get_FilePrivatePart()
0x10309  box      [mscorlib]System.Int32
0x1030e  stelem.ref
0x1030f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x10314  stfld    string <>c__DisplayClass420_0::version
0x10319  ret
```
