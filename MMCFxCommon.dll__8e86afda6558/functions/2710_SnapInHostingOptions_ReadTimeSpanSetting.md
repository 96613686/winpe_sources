# SnapInHostingOptions::ReadTimeSpanSetting

- ea: `0x2710`
- end: `0x27cb`
- name: `SnapInHostingOptions::ReadTimeSpanSetting`
- size: `187`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x2570`
- `0x25a0`
- `0x25c0`
- `0x25f0`
- `0x2620`
- `0x2650`

## callees

- `0xa0`
- `0x2680`
- `0x2710`

## string_xrefs

- `0x2738`: `mmc.exe.config: Key {0} with value {1} is not a valid int`
- `0x2779`: `mmc.exe.config: Key {0} with value {1} must be >= {2} and <= {3}`

## pseudocode

```c

```

## disassembly

```asm
0x2710  ldarg.1
0x2711  stloc.0
0x2712  ldarg.0
0x2713  call     string SnapInHostingOptions::ReadStringSetting(string settingKey)
0x2718  stloc.1
0x2719  ldloc.1
0x271a  brfalse  loc_27C9
0x271f  ldc.i4.0
0x2720  stloc.2
0x2721  ldloc.1
0x2722  ldc.i4.0
0x2723  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x2728  ldloca.s 2
0x272a  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0x272f  brtrue.s loc_2758
0x2731  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x2736  ldc.i4.4
0x2737  ldc.i4.0
0x2738  ldstr    aMmcExeConfigKe_0// "mmc.exe.config: Key {0} with value {1} "...
0x273d  ldc.i4.2
0x273e  newarr   [mscorlib]System.Object
0x2743  stloc.s  4
0x2745  ldloc.s  4
0x2747  ldc.i4.0
0x2748  ldarg.0
0x2749  stelem.ref
0x274a  ldloc.s  4
0x274c  ldc.i4.1
0x274d  ldloc.1
0x274e  stelem.ref
0x274f  ldloc.s  4
0x2751  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x2756  br.s     loc_27C9
0x2758  ldloc.2
0x2759  conv.r8
0x275a  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x275f  stloc.3
0x2760  ldloc.3
0x2761  ldarg.2
0x2762  call     bool [mscorlib]System.TimeSpan::op_LessThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x2767  brtrue.s loc_2772
0x2769  ldloc.3
0x276a  ldarg.3
0x276b  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x2770  brfalse.s loc_27C7
0x2772  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x2777  ldc.i4.4
0x2778  ldc.i4.0
0x2779  ldstr    aMmcExeConfigKe_1// "mmc.exe.config: Key {0} with value {1} "...
0x277e  ldc.i4.4
0x277f  newarr   [mscorlib]System.Object
0x2784  stloc.s  5
0x2786  ldloc.s  5
0x2788  ldc.i4.0
0x2789  ldarg.0
0x278a  stelem.ref
0x278b  ldloc.s  5
0x278d  ldc.i4.1
0x278e  ldloca.s 3
0x2790  constrained. [mscorlib]System.TimeSpan
0x2796  callvirt instance string [mscorlib]System.Object::ToString()
0x279b  stelem.ref
0x279c  ldloc.s  5
0x279e  ldc.i4.2
0x279f  ldarga.s 2
0x27a1  constrained. [mscorlib]System.TimeSpan
0x27a7  callvirt instance string [mscorlib]System.Object::ToString()
0x27ac  stelem.ref
0x27ad  ldloc.s  5
0x27af  ldc.i4.3
0x27b0  ldarga.s 3
0x27b2  constrained. [mscorlib]System.TimeSpan
0x27b8  callvirt instance string [mscorlib]System.Object::ToString()
0x27bd  stelem.ref
0x27be  ldloc.s  5
0x27c0  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x27c5  br.s     loc_27C9
0x27c7  ldloc.3
0x27c8  stloc.0
0x27c9  ldloc.0
0x27ca  ret
```
