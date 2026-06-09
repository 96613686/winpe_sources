# Microsoft.ReportingServices.Modeling.ModelRole::ResolveRequiredReferences

- ea: `0x15e40`
- end: `0x15e96`
- name: `Microsoft.ReportingServices.Modeling.ModelRole::ResolveRequiredReferences`
- size: `86`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x139d0`
- `0x14530`
- `0x15390`
- `0x15560`
- `0x15e40`
- `0x16c80`

## string_xrefs

- `0x15e53`: `Related role already set on ModelRole.`

## pseudocode

```c

```

## disassembly

```asm
0x15e40  ldarg.0
0x15e41  ldarg.1
0x15e42  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::ResolveRequiredReferences(class Microsoft.ReportingServices.Modeling.SemanticModel newModel)
0x15e47  brtrue.s loc_15E4B
0x15e49  ldc.i4.0
0x15e4a  ret
0x15e4b  ldarg.0
0x15e4c  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15e51  brfalse.s loc_15E5E
0x15e53  ldstr    aRelatedRoleAlr// "Related role already set on ModelRole."
0x15e58  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x15e5d  throw
0x15e5e  ldarg.0
0x15e5f  call     instance class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::get_BaseItem()
0x15e64  callvirt instance class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedRole()
0x15e69  brfalse.s loc_15E8C
0x15e6b  ldarg.0
0x15e6c  ldarg.1
0x15e6d  ldarg.0
0x15e6e  call     instance class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::get_BaseItem()
0x15e73  callvirt instance class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::get_RelatedRole()
0x15e78  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x15e7d  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x15e82  isinst   Microsoft.ReportingServices.Modeling.ModelRole
0x15e87  stfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15e8c  ldarg.0
0x15e8d  ldfld    class Microsoft.ReportingServices.Modeling.ModelRole Microsoft.ReportingServices.Modeling.ModelRole::m_relatedRole
0x15e92  ldnull
0x15e93  cgt.un
0x15e95  ret
```
