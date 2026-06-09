# Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetStandardizedPathName

- ea: `0xa90`
- end: `0xab1`
- name: `Microsoft.ReportingServices.Portal.WebHost.Services.Impl.CatalogContainer::GetStandardizedPathName`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xa00`
- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldarg.0
0xa91  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0xa96  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa9b  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xaa0  ldc.i4.1
0xaa1  newarr   [mscorlib]System.Char
0xaa6  dup
0xaa7  ldc.i4.0
0xaa8  ldc.i4.s 0x5C
0xaaa  stelem.i2
0xaab  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0xab0  ret
```
