# MS.Internal.Printing.Configuration.FallbackPTProvider::get_OemDriverNamespace

- ea: `0xdc70`
- end: `0xdcfe`
- name: `MS.Internal.Printing.Configuration.FallbackPTProvider::get_OemDriverNamespace`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd8a0`
- `0xddb0`
- `0xdde0`

## callees

- `0xdc70`

## string_xrefs

- `0xdc7d`: `http://schemas.microsoft.com/windows/printing/oemdriverpt/netfx{0}/{1}/v{2}`
- `0xdcbb`: `http://schemas.microsoft.com/windows/printing/oemdriverpt/netfx{0}/{1}/v{2}`

## pseudocode

```c

```

## disassembly

```asm
0xdc70  ldarg.0
0xdc71  ldfld    string MS.Internal.Printing.Configuration.FallbackPTProvider::_printTicketNamespace
0xdc76  brtrue.s loc_DCF7
0xdc78  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdc7d  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/windows/pr"...
0xdc82  ldc.i4.3
0xdc83  newarr   [mscorlib]System.Object
0xdc88  dup
0xdc89  ldc.i4.0
0xdc8a  ldstr    aV0400// "_v0400"
0xdc8f  stelem.ref
0xdc90  dup
0xdc91  ldc.i4.1
0xdc92  ldarg.0
0xdc93  ldfld    string MS.Internal.Printing.Configuration.FallbackPTProvider::_driverName
0xdc98  stelem.ref
0xdc99  dup
0xdc9a  ldc.i4.2
0xdc9b  ldarg.0
0xdc9c  ldfld    unsigned int16 MS.Internal.Printing.Configuration.FallbackPTProvider::_driverVersion
0xdca1  box      [mscorlib]System.UInt16
0xdca6  stelem.ref
0xdca7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdcac  stloc.0
0xdcad  ldloc.0
0xdcae  ldc.i4.1
0xdcaf  call     bool [System]System.Uri::IsWellFormedUriString(string, valuetype [System]System.UriKind)
0xdcb4  brtrue.s loc_DCF0
0xdcb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdcbb  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/windows/pr"...
0xdcc0  ldc.i4.3
0xdcc1  newarr   [mscorlib]System.Object
0xdcc6  dup
0xdcc7  ldc.i4.0
0xdcc8  ldstr    aV0400// "_v0400"
0xdccd  stelem.ref
0xdcce  dup
0xdccf  ldc.i4.1
0xdcd0  ldarg.0
0xdcd1  ldfld    string MS.Internal.Printing.Configuration.FallbackPTProvider::_driverName
0xdcd6  call     string [System]System.Uri::EscapeUriString(string)
0xdcdb  stelem.ref
0xdcdc  dup
0xdcdd  ldc.i4.2
0xdcde  ldarg.0
0xdcdf  ldfld    unsigned int16 MS.Internal.Printing.Configuration.FallbackPTProvider::_driverVersion
0xdce4  box      [mscorlib]System.UInt16
0xdce9  stelem.ref
0xdcea  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdcef  stloc.0
0xdcf0  ldarg.0
0xdcf1  ldloc.0
0xdcf2  stfld    string MS.Internal.Printing.Configuration.FallbackPTProvider::_printTicketNamespace
0xdcf7  ldarg.0
0xdcf8  ldfld    string MS.Internal.Printing.Configuration.FallbackPTProvider::_printTicketNamespace
0xdcfd  ret
```
