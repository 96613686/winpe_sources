# Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight

- ea: `0x1d640`
- end: `0x1d665`
- name: `Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight`
- size: `37`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x22c70`

## callees

- `0x1d640`

## string_xrefs

- `0x1d646`: `application/json`

## pseudocode

```c

```

## disassembly

```asm
0x1d640  ldarg.0
0x1d641  brtrue.s loc_1D645
0x1d643  ldc.i4.0
0x1d644  ret
0x1d645  ldarg.0
0x1d646  ldstr    aApplicationJso_0// "application/json"
0x1d64b  ldc.i4.5
0x1d64c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x1d651  brfalse.s loc_1D663
0x1d653  ldarg.0
0x1d654  ldstr    aVerbose// "verbose"
0x1d659  ldc.i4.5
0x1d65a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1d65f  ldc.i4.m1
0x1d660  ceq
0x1d662  ret
0x1d663  ldc.i4.0
0x1d664  ret
```
