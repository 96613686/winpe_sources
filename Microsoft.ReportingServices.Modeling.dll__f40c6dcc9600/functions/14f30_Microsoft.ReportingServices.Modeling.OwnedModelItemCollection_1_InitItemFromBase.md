# Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1::InitItemFromBase

- ea: `0x14f30`
- end: `0x14f55`
- name: `Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1::InitItemFromBase`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x13b10`
- `0x145e0`
- `0x14f30`

## string_xrefs

- `0x14f3d`: `Item.ParentItem should already be set on lazy cloned item`

## pseudocode

```c

```

## disassembly

```asm
0x14f30  ldarg.1
0x14f31  box      var<u1>
0x14f36  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::get_ParentItem()
0x14f3b  brtrue.s loc_14F48
0x14f3d  ldstr    aItemParentitem// "Item.ParentItem should already be set o"...
0x14f42  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14f47  throw
0x14f48  ldarg.1
0x14f49  box      var<u1>
0x14f4e  ldarg.0
0x14f4f  callvirt instance void Microsoft.ReportingServices.Modeling.ModelItem::SetOwnerCollection(class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection newOwnerCollection)
0x14f54  ret
```
