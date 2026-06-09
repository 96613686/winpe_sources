# Microsoft.ReportingServices.Modeling.EntityRefNode::CloneFor

- ea: `0x1bdd0`
- end: `0x1be2b`
- name: `Microsoft.ReportingServices.Modeling.EntityRefNode::CloneFor`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x139d0`
- `0x16c80`
- `0x1bb20`
- `0x1bdd0`
- `0x24160`

## string_xrefs

- `0x1bdd8`: `EntityRefNode is not compiled`

## pseudocode

```c

```

## disassembly

```asm
0x1bdd0  ldarg.0
0x1bdd1  call     instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x1bdd6  brtrue.s loc_1BDE3
0x1bdd8  ldstr    aEntityrefnodeI// "EntityRefNode is not compiled"
0x1bddd  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1bde2  throw
0x1bde3  ldarg.0
0x1bde4  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.EntityRefNode::m_entity
0x1bde9  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x1bdee  brfalse.s loc_1BE0E
0x1bdf0  ldarg.1
0x1bdf1  ldarg.0
0x1bdf2  ldfld    class Microsoft.ReportingServices.Modeling.IQueryEntityInternal Microsoft.ReportingServices.Modeling.EntityRefNode::m_entity
0x1bdf7  callvirt instance class Microsoft.ReportingServices.Modeling.ModelEntity Microsoft.ReportingServices.Modeling.IQueryEntity::get_ModelEntity()
0x1bdfc  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1be01  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x1be06  isinst   Microsoft.ReportingServices.Modeling.ModelEntity
0x1be0b  stloc.0
0x1be0c  br.s     loc_1BE19
0x1be0e  ldstr    aNullOrUnrecogn_0// "Null or unrecognized IQueryEntity"
0x1be13  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1be18  throw
0x1be19  ldloc.0
0x1be1a  brtrue.s loc_1BE1E
0x1be1c  ldnull
0x1be1d  ret
0x1be1e  ldloc.0
0x1be1f  newobj   instance void Microsoft.ReportingServices.Modeling.EntityRefNode::.ctor(class Microsoft.ReportingServices.Modeling.IQueryEntity entity)
0x1be24  dup
0x1be25  callvirt instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x1be2a  ret
```
