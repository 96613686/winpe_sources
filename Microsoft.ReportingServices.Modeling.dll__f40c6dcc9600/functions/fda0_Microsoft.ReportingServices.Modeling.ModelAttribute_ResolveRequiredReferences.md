# Microsoft.ReportingServices.Modeling.ModelAttribute::ResolveRequiredReferences

- ea: `0xfda0`
- end: `0xfde4`
- name: `Microsoft.ReportingServices.Modeling.ModelAttribute::ResolveRequiredReferences`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0xeeb0`
- `0xf2a0`
- `0xfda0`
- `0x14530`
- `0x19480`

## string_xrefs

- `0xfdb3`: `ResolveRequiredReferences: expression already initialized on ModelAttribute`

## pseudocode

```c

```

## disassembly

```asm
0xfda0  ldarg.0
0xfda1  ldarg.1
0xfda2  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::ResolveRequiredReferences(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0xfda7  brtrue.s loc_FDAB
0xfda9  ldc.i4.0
0xfdaa  ret
0xfdab  ldarg.0
0xfdac  ldfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xfdb1  brfalse.s loc_FDBE
0xfdb3  ldstr    aResolverequire// "ResolveRequiredReferences: expression a"...
0xfdb8  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xfdbd  throw
0xfdbe  ldarg.0
0xfdbf  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_BaseItem()
0xfdc4  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::get_Expression()
0xfdc9  brfalse.s loc_FDE2
0xfdcb  ldarg.0
0xfdcc  ldarg.0
0xfdcd  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.ModelAttribute::get_BaseItem()
0xfdd2  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::get_Expression()
0xfdd7  ldarg.1
0xfdd8  callvirt instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.Expression::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0xfddd  stfld    class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.ModelAttribute::m_expression
0xfde2  ldc.i4.1
0xfde3  ret
```
