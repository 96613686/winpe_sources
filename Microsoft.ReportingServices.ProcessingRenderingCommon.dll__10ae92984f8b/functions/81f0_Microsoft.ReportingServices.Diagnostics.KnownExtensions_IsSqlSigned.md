# Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsSqlSigned

- ea: `0x81f0`
- end: `0x820b`
- name: `Microsoft.ReportingServices.Diagnostics.KnownExtensions::IsSqlSigned`
- size: `27`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x8000`

## callees

- `0x81f0`

## string_xrefs

- `0x81f1`: `PublicKeyToken=89845dcd8080cc91`
- `0x81fe`: `PublicKeyToken=ba138330840163b5`

## pseudocode

```c

```

## disassembly

```asm
0x81f0  ldarg.0
0x81f1  ldstr    aPublickeytoken// "PublicKeyToken=89845dcd8080cc91"
0x81f6  callvirt instance bool [mscorlib]System.String::Contains(string)
0x81fb  brtrue.s loc_8209
0x81fd  ldarg.0
0x81fe  ldstr    aPublickeytoken_0// "PublicKeyToken=ba138330840163b5"
0x8203  callvirt instance bool [mscorlib]System.String::Contains(string)
0x8208  ret
0x8209  ldc.i4.1
0x820a  ret
```
