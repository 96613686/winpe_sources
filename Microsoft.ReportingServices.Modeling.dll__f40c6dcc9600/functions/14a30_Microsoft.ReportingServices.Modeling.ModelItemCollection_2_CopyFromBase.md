# Microsoft.ReportingServices.Modeling.ModelItemCollection`2::CopyFromBase

- ea: `0x14a30`
- end: `0x14b14`
- name: `Microsoft.ReportingServices.Modeling.ModelItemCollection`2::CopyFromBase`
- size: `228`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x97d0`
- `0x139d0`
- `0x13af0`
- `0x14a30`
- `0x16c80`

## string_xrefs

- `0x14a84`: `ParentItem has no Model, items' ParentItem has no Model, or Models match; copy only allowed between different models`

## pseudocode

```c

```

## disassembly

```asm
0x14a30  ldarg.1
0x14a31  brtrue.s loc_14A3E
0x14a33  ldstr    aItemsIsNull// "items is null"
0x14a38  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14a3d  throw
0x14a3e  ldarg.0
0x14a3f  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::get_ParentItem()
0x14a44  box      var<u1>
0x14a49  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x14a4e  brfalse.s loc_14A84
0x14a50  ldarg.1
0x14a51  callvirt instance var<u1> class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::get_ParentItem()
0x14a56  box      var<u1>
0x14a5b  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x14a60  brfalse.s loc_14A84
0x14a62  ldarg.0
0x14a63  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::get_ParentItem()
0x14a68  box      var<u1>
0x14a6d  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x14a72  ldarg.1
0x14a73  callvirt instance var<u1> class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::get_ParentItem()
0x14a78  box      var<u1>
0x14a7d  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x14a82  bne.un.s loc_14A8F
0x14a84  ldstr    aParentitemHasN// "ParentItem has no Model, items' ParentI"...
0x14a89  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14a8e  throw
0x14a8f  ldarg.0
0x14a90  call     instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<var<u1>>::get_Count()
0x14a95  ldc.i4.0
0x14a96  ble.s    loc_14AA3
0x14a98  ldstr    aCollectionIsNo// "Collection is not empty"
0x14a9d  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x14aa2  throw
0x14aa3  ldarg.1
0x14aa4  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<var<u1>>::GetEnumerator()
0x14aa9  stloc.0
0x14aaa  br.s     loc_14AFA
0x14aac  ldloca.s 0
0x14aae  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::get_Current()
0x14ab3  stloc.1
0x14ab4  ldarg.0
0x14ab5  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::get_ParentItem()
0x14aba  box      var<u1>
0x14abf  callvirt instance class Microsoft.ReportingServices.Modeling.SemanticModel Microsoft.ReportingServices.Modeling.ModelItem::get_Model()
0x14ac4  ldloc.1
0x14ac5  box      var<u1>
0x14aca  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x14acf  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x14ad4  isinst   var<u1>
0x14ad9  unbox.any var<u1>
0x14ade  stloc.2
0x14adf  ldloc.2
0x14ae0  box      var<u1>
0x14ae5  brfalse.s loc_14AFA
0x14ae7  ldarg.0
0x14ae8  call     instance class [mscorlib]System.Collections.Generic.List`1<var<u1>> class Microsoft.ReportingServices.Modeling.CheckedCollection`1<var<u1>>::get_Items()
0x14aed  ldloc.2
0x14aee  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<var<u1>>::Add(var<u1>)
0x14af3  ldarg.0
0x14af4  ldloc.2
0x14af5  callvirt instance void class Microsoft.ReportingServices.Modeling.ModelItemCollection`2<var<u1>, !!T0>::InitItemFromBase(var<u1>)
0x14afa  ldloca.s 0
0x14afc  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>::MoveNext()
0x14b01  brtrue.s loc_14AAC
0x14b03  leave.s  loc_14B13
0x14b05  ldloca.s 0
0x14b07  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>>
0x14b0d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x14b12  endfinally
0x14b13  ret
```
