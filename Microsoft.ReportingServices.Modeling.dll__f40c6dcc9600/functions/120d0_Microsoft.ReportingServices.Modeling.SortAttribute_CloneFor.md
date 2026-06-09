# Microsoft.ReportingServices.Modeling.SortAttribute::CloneFor

- ea: `0x120d0`
- end: `0x12108`
- name: `Microsoft.ReportingServices.Modeling.SortAttribute::CloneFor`
- size: `56`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x12110`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x11a60`
- `0x11f60`
- `0x120d0`

## string_xrefs

- `0x120d8`: `SortAttribute is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x120d0  ldarg.0
0x120d1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x120d6  brtrue.s loc_120E3
0x120d8  ldstr    aSortattributeI// "SortAttribute is not compiled"
0x120dd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x120e2  throw
0x120e3  ldarg.0
0x120e4  ldfld    class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.SortAttribute::m_attributeReference
0x120e9  ldarg.1
0x120ea  callvirt instance class Microsoft.ReportingServices.Modeling.AttributeReference Microsoft.ReportingServices.Modeling.AttributeReference::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x120ef  stloc.0
0x120f0  ldloc.0
0x120f1  brtrue.s loc_120F5
0x120f3  ldnull
0x120f4  ret
0x120f5  ldloc.0
0x120f6  ldarg.0
0x120f7  ldfld    valuetype Microsoft.ReportingServices.Modeling.SortAttributeDirection Microsoft.ReportingServices.Modeling.SortAttribute::m_sortDirection
0x120fc  newobj   instance void Microsoft.ReportingServices.Modeling.SortAttribute::.ctor(class Microsoft.ReportingServices.Modeling.AttributeReference attributeReference, valuetype Microsoft.ReportingServices.Modeling.SortAttributeDirection sortDirection)
0x12101  dup
0x12102  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x12107  ret
```
