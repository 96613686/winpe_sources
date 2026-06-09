# Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandContentValidator::.ctor

- ea: `0xbe30`
- end: `0xbe54`
- name: `Microsoft.ReportingServices.Portal.Services.SystemResources.UniversalBrandContentValidator::.ctor`
- size: `36`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xd4a0`

## string_xrefs

- `0xbe3e`: `application/json`
- `0xbe43`: `.json`

## pseudocode

```c

```

## disassembly

```asm
0xbe30  ldarg.0
0xbe31  ldc.i4.1
0xbe32  newarr   [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem
0xbe37  dup
0xbe38  ldc.i4.0
0xbe39  ldstr    aColors// "colors"
0xbe3e  ldstr    aApplicationJso// "application/json"
0xbe43  ldstr    aJson// ".json"
0xbe48  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem::.ctor(string, string, string)
0xbe4d  stelem.ref
0xbe4e  call     instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourcePackageContentRequiredValidator::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.SystemResourcePackageContentValidationItem>)
0xbe53  ret
```
