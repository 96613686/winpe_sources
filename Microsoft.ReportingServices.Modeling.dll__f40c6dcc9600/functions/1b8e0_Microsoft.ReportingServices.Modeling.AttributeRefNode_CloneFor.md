# Microsoft.ReportingServices.Modeling.AttributeRefNode::CloneFor

- ea: `0x1b8e0`
- end: `0x1b944`
- name: `Microsoft.ReportingServices.Modeling.AttributeRefNode::CloneFor`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x139d0`
- `0x16c80`
- `0x1b290`
- `0x1b300`
- `0x1b310`
- `0x1b8e0`

## string_xrefs

- `0x1b8e8`: `AttributeRefNode is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x1b8e0  ldarg.0
0x1b8e1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1b8e6  brtrue.s loc_1B8F3
0x1b8e8  ldstr    aAttributerefno_1// "AttributeRefNode is not compiled"
0x1b8ed  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b8f2  throw
0x1b8f3  ldarg.0
0x1b8f4  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeRefNode::get_ModelAttribute()
0x1b8f9  brfalse.s loc_1B914
0x1b8fb  ldarg.1
0x1b8fc  ldarg.0
0x1b8fd  call     instance class Microsoft.ReportingServices.Modeling.ModelAttribute Microsoft.ReportingServices.Modeling.AttributeRefNode::get_ModelAttribute()
0x1b902  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1b907  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x1b90c  isinst   Microsoft.ReportingServices.Modeling.ModelAttribute
0x1b911  stloc.0
0x1b912  br.s     loc_1B932
0x1b914  ldarg.0
0x1b915  call     instance class Microsoft.ReportingServices.Modeling.Expression Microsoft.ReportingServices.Modeling.AttributeRefNode::get_CalculatedAttribute()
0x1b91a  brfalse.s loc_1B927
0x1b91c  ldstr    aUnexpectedCalc// "Unexpected CalculatedAttribute referenc"...
0x1b921  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b926  throw
0x1b927  ldstr    aNullOrUnrecogn// "Null or unrecognized IQueryAttribute"
0x1b92c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1b931  throw
0x1b932  ldloc.0
0x1b933  brtrue.s loc_1B937
0x1b935  ldnull
0x1b936  ret
0x1b937  ldloc.0
0x1b938  newobj   instance void Microsoft.ReportingServices.Modeling.AttributeRefNode::.ctor(class Microsoft.ReportingServices.Modeling.IQueryAttribute attribute)
0x1b93d  dup
0x1b93e  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x1b943  ret
```
