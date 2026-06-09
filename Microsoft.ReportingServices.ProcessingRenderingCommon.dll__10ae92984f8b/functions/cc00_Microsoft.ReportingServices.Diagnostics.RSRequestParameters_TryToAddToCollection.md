# Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection

- ea: `0xcc00`
- end: `0xcc60`
- name: `Microsoft.ReportingServices.Diagnostics.RSRequestParameters::TryToAddToCollection`
- size: `96`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xbd90`
- `0xc340`
- `0xc900`
- `0xca60`

## callees

- `0xc760`
- `0xcc00`

## pseudocode

```c

```

## disassembly

```asm
0xcc00  ldarg.0
0xcc01  ldarg.2
0xcc02  ldloca.s 0
0xcc04  call     bool Microsoft.ReportingServices.Diagnostics.RSRequestParameters::HasPrefix(string name, string prefix, [out] string& unprefixedName)
0xcc09  brtrue.s loc_CC0D
0xcc0b  ldc.i4.0
0xcc0c  ret
0xcc0d  ldarg.3
0xcc0e  brtrue.s loc_CC41
0xcc10  ldarg.1
0xcc11  ldlen
0xcc12  conv.i4
0xcc13  ldc.i4.1
0xcc14  ble.s    loc_CC18
0xcc16  ldc.i4.1
0xcc17  ret
0xcc18  ldarg.s  4
0xcc1a  ldloc.0
0xcc1b  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xcc20  brtrue.s loc_CC2F
0xcc22  ldarg.s  4
0xcc24  ldloc.0
0xcc25  ldarg.1
0xcc26  ldc.i4.0
0xcc27  ldelem.ref
0xcc28  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0xcc2d  ldc.i4.1
0xcc2e  ret
0xcc2f  ldarg.1
0xcc30  ldc.i4.0
0xcc31  ldelem.ref
0xcc32  brtrue.s loc_CC3F
0xcc34  ldarg.s  4
0xcc36  ldloc.0
0xcc37  ldnull
0xcc38  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0xcc3d  ldc.i4.1
0xcc3e  ret
0xcc3f  ldc.i4.1
0xcc40  ret
0xcc41  ldarg.1
0xcc42  stloc.1
0xcc43  ldc.i4.0
0xcc44  stloc.2
0xcc45  br.s     loc_CC58
0xcc47  ldloc.1
0xcc48  ldloc.2
0xcc49  ldelem.ref
0xcc4a  stloc.3
0xcc4b  ldarg.s  4
0xcc4d  ldloc.0
0xcc4e  ldloc.3
0xcc4f  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0xcc54  ldloc.2
0xcc55  ldc.i4.1
0xcc56  add
0xcc57  stloc.2
0xcc58  ldloc.2
0xcc59  ldloc.1
0xcc5a  ldlen
0xcc5b  conv.i4
0xcc5c  blt.s    loc_CC47
0xcc5e  ldc.i4.1
0xcc5f  ret
```
