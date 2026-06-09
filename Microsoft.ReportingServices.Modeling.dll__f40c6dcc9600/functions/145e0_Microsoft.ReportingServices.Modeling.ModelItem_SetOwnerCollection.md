# Microsoft.ReportingServices.Modeling.ModelItem::SetOwnerCollection

- ea: `0x145e0`
- end: `0x1462b`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::SetOwnerCollection`
- size: `75`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14f30`
- `0x14f60`
- `0x14fb0`

## callees

- `0x97d0`
- `0x145e0`
- `0x14c70`
- `0x14c80`

## string_xrefs

- `0x14618`: `item already has an OwnerCollection`

## pseudocode

```c

```

## disassembly

```asm
0x145e0  ldarg.1
0x145e1  brfalse.s loc_14623
0x145e3  ldarg.0
0x145e4  ldfld    class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::m_parentItem
0x145e9  ldarg.1
0x145ea  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection::get_ParentItem()
0x145ef  beq.s    loc_145FC
0x145f1  ldstr    aMParentitemDoe// "m_parentItem does not match newOwnerCol"...
0x145f6  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x145fb  throw
0x145fc  ldarg.1
0x145fd  ldarg.0
0x145fe  callvirt instance bool Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection::CanContain(class Microsoft.ReportingServices.Modeling.ModelItem item)
0x14603  brtrue.s loc_14610
0x14605  ldstr    aItemCannotBeCo// "item cannot be contained by newOwnerCol"...
0x1460a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1460f  throw
0x14610  ldarg.0
0x14611  ldfld    class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::m_ownerCollection
0x14616  brfalse.s loc_14623
0x14618  ldstr    aItemAlreadyHas// "item already has an OwnerCollection"
0x1461d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14622  throw
0x14623  ldarg.0
0x14624  ldarg.1
0x14625  stfld    class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.ModelItem::m_ownerCollection
0x1462a  ret
```
