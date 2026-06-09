# Microsoft.ReportingServices.Modeling.SemanticModel::UnlinkSingleItem

- ea: `0x17440`
- end: `0x17493`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::UnlinkSingleItem`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x173c0`

## callees

- `0x97d0`
- `0x139d0`
- `0x13af0`
- `0x17440`

## string_xrefs

- `0x17475`: `item not linked`

## pseudocode

```c

```

## disassembly

```asm
0x17440  ldarg.1
0x17441  brtrue.s loc_1744E
0x17443  ldstr    aItemIsNull// "item is null"
0x17448  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1744d  throw
0x1744e  ldarg.1
0x1744f  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x17454  ldarg.0
0x17455  beq.s    loc_17462
0x17457  ldstr    aItemModelMisma// "item.Model mismatch"
0x1745c  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x17461  throw
0x17462  ldarg.0
0x17463  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_allItems
0x17468  ldarg.1
0x17469  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1746e  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem>::ContainsKey(var<u1>)
0x17473  brtrue.s loc_17480
0x17475  ldstr    aItemNotLinked// "item not linked"
0x1747a  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1747f  throw
0x17480  ldarg.0
0x17481  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_allItems
0x17486  ldarg.1
0x17487  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x1748c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem>::Remove(var<u1>)
0x17491  pop
0x17492  ret
```
