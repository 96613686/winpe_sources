# SnapInHostingOptions::ReadBoolSetting

- ea: `0x26c0`
- end: `0x2706`
- name: `SnapInHostingOptions::ReadBoolSetting`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2560`

## callees

- `0xa0`
- `0x2680`
- `0x26c0`

## string_xrefs

- `0x26e5`: `mmc.exe.config: Key {0} with value {1} is not a valid int`

## pseudocode

```c

```

## disassembly

```asm
0x26c0  ldarg.1
0x26c1  stloc.0
0x26c2  ldarg.0
0x26c3  call     string SnapInHostingOptions::ReadStringSetting(string settingKey)
0x26c8  stloc.1
0x26c9  ldloc.1
0x26ca  brfalse.s loc_2704
0x26cc  ldc.i4.0
0x26cd  stloc.2
0x26ce  ldloc.1
0x26cf  ldc.i4.0
0x26d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x26d5  ldloca.s 2
0x26d7  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x26dc  brtrue.s loc_26FF
0x26de  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x26e3  ldc.i4.4
0x26e4  ldc.i4.0
0x26e5  ldstr    aMmcExeConfigKe_0// "mmc.exe.config: Key {0} with value {1} "...
0x26ea  ldc.i4.2
0x26eb  newarr   [mscorlib]System.Object
0x26f0  stloc.3
0x26f1  ldloc.3
0x26f2  ldc.i4.0
0x26f3  ldarg.0
0x26f4  stelem.ref
0x26f5  ldloc.3
0x26f6  ldc.i4.1
0x26f7  ldloc.1
0x26f8  stelem.ref
0x26f9  ldloc.3
0x26fa  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x26ff  ldloc.2
0x2700  ldc.i4.0
0x2701  cgt
0x2703  stloc.0
0x2704  ldloc.0
0x2705  ret
```
