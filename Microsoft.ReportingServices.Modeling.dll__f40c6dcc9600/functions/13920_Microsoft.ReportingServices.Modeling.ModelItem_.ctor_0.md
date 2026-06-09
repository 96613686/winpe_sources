# Microsoft.ReportingServices.Modeling.ModelItem::.ctor_0

- ea: `0x13920`
- end: `0x139ca`
- name: `Microsoft.ReportingServices.Modeling.ModelItem::.ctor_0`
- size: `170`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x12e70`
- `0x13700`
- `0x16480`
- `0x169c0`

## callees

- `0x9610`
- `0x97d0`
- `0x9cf0`
- `0x9d30`
- `0x9e80`
- `0x9eb0`
- `0x9ee0`
- `0x13920`
- `0x13b10`

## string_xrefs

- `0x1396f`: `baseItem.CustomProperties is not read-only`

## pseudocode

```c

```

## disassembly

```asm
0x13920  ldarg.0
0x13921  call     instance void Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::.ctor()
0x13926  ldarg.1
0x13927  brtrue.s loc_13934
0x13929  ldstr    aBaseitem// "baseItem"
0x1392e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x13933  throw
0x13934  ldarg.1
0x13935  callvirt instance class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::get_ParentItem()
0x1393a  brtrue.s loc_1394F
0x1393c  ldarg.1
0x1393d  isinst   Microsoft.ReportingServices.Modeling.SemanticModel
0x13942  brtrue.s loc_1394F
0x13944  ldstr    aBaseitemHasNoP// "baseItem has no ParentItem and is not M"...
0x13949  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x1394e  throw
0x1394f  ldarg.1
0x13950  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingObject::get_IsCompiled()
0x13955  brtrue.s loc_13962
0x13957  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::get_ModelItem_BaseItemMustBeCompiled()
0x1395c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13961  throw
0x13962  ldarg.1
0x13963  callvirt instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x13968  callvirt instance bool class Microsoft.ReportingServices.Modeling.CheckedCollection`1<class Microsoft.ReportingServices.Modeling.CustomProperty>::get_IsReadOnly()
0x1396d  brtrue.s loc_1397A
0x1396f  ldstr    aBaseitemCustom// "baseItem.CustomProperties is not read-o"...
0x13974  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0x13979  throw
0x1397a  ldarg.0
0x1397b  ldarg.1
0x1397c  ldfld    valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x13981  stfld    valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::__id
0x13986  ldarg.0
0x13987  ldarg.1
0x13988  ldfld    string Microsoft.ReportingServices.Modeling.ModelItem::__name
0x1398d  stfld    string Microsoft.ReportingServices.Modeling.ModelItem::__name
0x13992  ldarg.0
0x13993  ldarg.1
0x13994  ldfld    string Microsoft.ReportingServices.Modeling.ModelItem::m_description
0x13999  stfld    string Microsoft.ReportingServices.Modeling.ModelItem::m_description
0x1399e  ldarg.0
0x1399f  ldarg.2
0x139a0  brtrue.s loc_139AA
0x139a2  ldarg.1
0x139a3  ldfld    bool Microsoft.ReportingServices.Modeling.ModelItem::m_hidden
0x139a8  br.s     loc_139AB
0x139aa  ldc.i4.1
0x139ab  stfld    bool Microsoft.ReportingServices.Modeling.ModelItem::m_hidden
0x139b0  ldarg.0
0x139b1  ldarg.1
0x139b2  callvirt instance class Microsoft.ReportingServices.Modeling.CustomPropertyCollection Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::get_CustomProperties()
0x139b7  call     instance void Microsoft.ReportingServices.Modeling.ExtensibleModelingObject::set_CustomProperties(class Microsoft.ReportingServices.Modeling.CustomPropertyCollection value)
0x139bc  ldarg.0
0x139bd  ldarg.1
0x139be  stfld    class Microsoft.ReportingServices.Modeling.ModelItem Microsoft.ReportingServices.Modeling.ModelItem::m_baseItem
0x139c3  ldarg.0
0x139c4  call     instance void Microsoft.ReportingServices.Modeling.ModelingObject::SetCompiledIndicator()
0x139c9  ret
```
