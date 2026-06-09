# Microsoft.ReportingServices.Modeling.AttributeReference::CloneFor

- ea: `0x11a60`
- end: `0x11ab0`
- name: `Microsoft.ReportingServices.Modeling.AttributeReference::CloneFor`
- size: `80`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x10860`
- `0x11ab0`
- `0x120d0`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x11730`
- `0x11a60`
- `0x139d0`
- `0x16c80`
- `0x1e590`

## string_xrefs

- `0x11a68`: `AttributeReference is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x11a60  ldarg.0
0x11a61  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x11a66  brtrue.s loc_11A73
0x11a68  ldstr    aAttributerefer_1// "AttributeReference is not compiled"
0x11a6d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x11a72  throw
0x11a73  ldarg.0
0x11a74  ldfld    class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.AttributeReference::m_path
0x11a79  ldarg.1
0x11a7a  callvirt instance class Microsoft.ReportingServices.Modeling.ExpressionPath Microsoft.ReportingServices.Modeling.ExpressionPath::CloneFor(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x11a7f  stloc.0
0x11a80  ldloc.0
0x11a81  brtrue.s loc_11A85
0x11a83  ldnull
0x11a84  ret
0x11a85  ldarg.1
0x11a86  ldarg.0
0x11a87  ldfld    class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeReference::m_attribute
0x11a8c  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x11a91  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x11a96  isinst   Microsoft.ReportingServices.Modeling.ModelAttribute
0x11a9b  stloc.1
0x11a9c  ldloc.1
0x11a9d  brtrue.s loc_11AA1
0x11a9f  ldnull
0x11aa0  ret
0x11aa1  ldloc.1
0x11aa2  ldloc.0
0x11aa3  ldc.i4.0
0x11aa4  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeReference::.ctor(class Microsoft.ReportingServices.Modeling.ModelAttribute attribute, class Microsoft.ReportingServices.Modeling.ExpressionPath path, bool clonePath)
0x11aa9  dup
0x11aaa  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x11aaf  ret
```
