# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine

- ea: `0x2240`
- end: `0x2268`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::PathCombine`
- size: `40`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x2200`
- `0x2850`
- `0x2950`
- `0x3510`
- `0x37a0`
- `0x3c20`
- `0x5040`
- `0x51f0`
- `0x5390`

## callees

- `0x2240`

## pseudocode

```c

```

## disassembly

```asm
0x2240  ldarg.1
0x2241  ldstr    asc_25576// "/"
0x2246  callvirt instance bool [mscorlib]System.String::EndsWith(string)
0x224b  brfalse.s loc_2258
0x224d  ldarg.1
0x224e  ldarg.2
0x224f  call     string [mscorlib]System.String::Concat(string, string)
0x2254  starg.s  1
0x2256  br.s     loc_2266
0x2258  ldarg.1
0x2259  ldstr    asc_25576// "/"
0x225e  ldarg.2
0x225f  call     string [mscorlib]System.String::Concat(string, string, string)
0x2264  starg.s  1
0x2266  ldarg.1
0x2267  ret
```
