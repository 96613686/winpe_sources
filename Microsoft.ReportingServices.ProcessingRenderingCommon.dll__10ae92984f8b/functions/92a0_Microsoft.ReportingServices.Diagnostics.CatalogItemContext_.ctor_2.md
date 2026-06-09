# Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor_2

- ea: `0x92a0`
- end: `0x92e1`
- name: `Microsoft.ReportingServices.Diagnostics.CatalogItemContext::.ctor_2`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x9290`

## callees

- `0x92a0`
- `0x92f0`
- `0x9330`

## string_xrefs

- `0x92b9`: `pathTranslator`

## pseudocode

```c

```

## disassembly

```asm
0x92a0  ldarg.0
0x92a1  call     instance void class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::.ctor()
0x92a6  ldarg.2
0x92a7  brtrue.s loc_92B0
0x92a9  ldarg.3
0x92aa  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.MissingParameterException::.ctor(string)
0x92af  throw
0x92b0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x92b5  ldarg.1
0x92b6  ldnull
0x92b7  cgt.un
0x92b9  ldstr    aPathtranslator// "pathTranslator"
0x92be  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x92c3  ldarg.0
0x92c4  ldarg.1
0x92c5  stfld    class Microsoft.ReportingServices.Diagnostics.IPathTranslator class Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::m_PathTranslator
0x92ca  ldarg.0
0x92cb  call     instance void Microsoft.ReportingServices.Diagnostics.CatalogItemContext::Init()
0x92d0  ldarg.0
0x92d1  ldarg.2
0x92d2  call     instance bool Microsoft.ReportingServices.Diagnostics.CatalogItemContext::SetPath(string path)
0x92d7  brtrue.s loc_92E0
0x92d9  ldarg.2
0x92da  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidItemPathException::.ctor(string)
0x92df  throw
0x92e0  ret
```
