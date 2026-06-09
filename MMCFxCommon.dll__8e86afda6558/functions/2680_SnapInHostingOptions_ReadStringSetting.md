# SnapInHostingOptions::ReadStringSetting

- ea: `0x2680`
- end: `0x26b5`
- name: `SnapInHostingOptions::ReadStringSetting`
- size: `53`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x26c0`
- `0x2710`

## callees

- `0xa0`
- `0x2680`
- `0x27d0`

## string_xrefs

- `0x269d`: `mmc.exe.config: Key {0} not defined for section <appSettings>`

## pseudocode

```c

```

## disassembly

```asm
0x2680  ldnull
0x2681  stloc.0
0x2682  call     class [System]System.Collections.Specialized.NameValueCollection SnapInHostingOptions::GetSection()
0x2687  stloc.1
0x2688  ldloc.1
0x2689  brfalse.s loc_26B3
0x268b  ldloc.1
0x268c  ldarg.0
0x268d  callvirt instance string [System]System.Collections.Specialized.NameValueCollection::get_Item(string)
0x2692  stloc.0
0x2693  ldloc.0
0x2694  brtrue.s loc_26B3
0x2696  call     class [System]System.Diagnostics.TraceSource Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x269b  ldc.i4.8
0x269c  ldc.i4.0
0x269d  ldstr    aMmcExeConfigKe// "mmc.exe.config: Key {0} not defined for"...
0x26a2  ldc.i4.1
0x26a3  newarr   [mscorlib]System.Object
0x26a8  stloc.2
0x26a9  ldloc.2
0x26aa  ldc.i4.0
0x26ab  ldarg.0
0x26ac  stelem.ref
0x26ad  ldloc.2
0x26ae  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string, object[])
0x26b3  ldloc.0
0x26b4  ret
```
