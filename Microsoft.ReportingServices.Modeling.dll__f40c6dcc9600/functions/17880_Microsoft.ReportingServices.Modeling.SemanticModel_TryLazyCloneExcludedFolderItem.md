# Microsoft.ReportingServices.Modeling.SemanticModel::TryLazyCloneExcludedFolderItem

- ea: `0x17880`
- end: `0x178f8`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::TryLazyCloneExcludedFolderItem`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x176e0`

## callees

- `0x97d0`
- `0x139d0`
- `0x148b0`
- `0x16c80`
- `0x17880`

## string_xrefs

- `0x178d2`: `Failed to copy folder model item after one of its children has been successfully copied.`

## pseudocode

```c

```

## disassembly

```asm
0x17880  ldarg.1
0x17881  callvirt instance class Microsoft.ReportingServices.Modeling.IOwnedModelItemCollection Microsoft.ReportingServices.Modeling.IFolderItem::get_Items()
0x17886  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.ReportingServices.Modeling.ModelItem>::GetEnumerator()
0x1788b  stloc.0
0x1788c  br.s     loc_178E0
0x1788e  ldloc.0
0x1788f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.ReportingServices.Modeling.ModelItem>::get_Current()
0x17894  stloc.1
0x17895  ldarg.0
0x17896  ldfld    class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_itemInPerspective
0x1789b  brfalse.s loc_178AB
0x1789d  ldarg.0
0x1789e  ldfld    class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_itemInPerspective
0x178a3  ldloc.1
0x178a4  callvirt instance bool class [mscorlib]System.Predicate`1<class Microsoft.ReportingServices.Modeling.ModelItem>::Invoke(var<u1>)
0x178a9  brfalse.s loc_178E0
0x178ab  ldarg.0
0x178ac  ldloc.1
0x178ad  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x178b2  call     instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.SemanticModel::LookupItemByID(valuetype Microsoft.ReportingServices.Modeling.QName id)
0x178b7  brfalse.s loc_178E0
0x178b9  ldarg.0
0x178ba  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem> Microsoft.ReportingServices.Modeling.SemanticModel::m_allItems
0x178bf  ldarg.1
0x178c0  castclass Microsoft.ReportingServices.Modeling.ModelItem
0x178c5  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0x178ca  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.ReportingServices.Modeling.QName, class Microsoft.ReportingServices.Modeling.ModelItem>::get_Item(void)
0x178cf  dup
0x178d0  brtrue.s loc_178DD
0x178d2  ldstr    aFailedToCopyFo// "Failed to copy folder model item after "...
0x178d7  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x178dc  throw
0x178dd  stloc.2
0x178de  leave.s  loc_178F6
0x178e0  ldloc.0
0x178e1  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x178e6  brtrue.s loc_1788E
0x178e8  leave.s  loc_178F4
0x178ea  ldloc.0
0x178eb  brfalse.s loc_178F3
0x178ed  ldloc.0
0x178ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x178f3  endfinally
0x178f4  ldnull
0x178f5  ret
0x178f6  ldloc.2
0x178f7  ret
```
