# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetTablixBasedRdlReport

- ea: `0x3f0`
- end: `0x54d`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetTablixBasedRdlReport`
- size: `349`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x3c0`
- `0x3f0`
- `0x550`

## pseudocode

```c

```

## disassembly

```asm
0x3f0  call     class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetEmptyRdlReport()
0x3f5  stloc.0
0x3f6  ldloc.0
0x3f7  callvirt instance class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Report::get_Body()
0x3fc  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem> [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Body::get_ReportItems()
0x401  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix::.ctor()
0x406  stloc.1
0x407  ldloc.1
0x408  ldstr    aTablix// "Tablix"
0x40d  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName(string itemName)
0x412  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_Name(string)
0x417  ldloc.1
0x418  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixBody::.ctor()
0x41d  stloc.2
0x41e  ldloc.2
0x41f  ldc.i4.1
0x420  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixColumn
0x425  dup
0x426  ldc.i4.0
0x427  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixColumn::.ctor()
0x42c  dup
0x42d  ldc.r8   1.0
0x436  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSize::.ctor(float64)
0x43b  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixColumn::set_Width(valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportSize)
0x440  stelem.ref
0x441  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixBody::set_TablixColumns(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixColumn>)
0x446  ldloc.2
0x447  ldc.i4.1
0x448  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixRow
0x44d  dup
0x44e  ldc.i4.0
0x44f  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixRow::.ctor()
0x454  stloc.3
0x455  ldloc.3
0x456  ldc.i4.1
0x457  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixCell
0x45c  dup
0x45d  ldc.i4.0
0x45e  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixCell::.ctor()
0x463  dup
0x464  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CellContents::.ctor()
0x469  dup
0x46a  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle::.ctor()
0x46f  dup
0x470  ldstr    aRectangle// "Rectangle"
0x475  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRandomizedItemName(string itemName)
0x47a  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem::set_Name(string)
0x47f  dup
0x480  ldc.i4.1
0x481  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Rectangle::set_KeepTogether(bool)
0x486  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CellContents::set_ReportItem(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem)
0x48b  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixCell::set_CellContents(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.CellContents)
0x490  stelem.ref
0x491  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixRow::set_TablixCells(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixCell>)
0x496  ldloc.3
0x497  stelem.ref
0x498  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixBody::set_TablixRows(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixRow>)
0x49d  ldloc.2
0x49e  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix::set_TablixBody(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixBody)
0x4a3  ldloc.1
0x4a4  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy::.ctor()
0x4a9  stloc.s  4
0x4ab  ldloc.s  4
0x4ad  ldc.i4.1
0x4ae  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember
0x4b3  dup
0x4b4  ldc.i4.0
0x4b5  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember::.ctor()
0x4ba  stelem.ref
0x4bb  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy::set_TablixMembers(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember>)
0x4c0  ldloc.s  4
0x4c2  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix::set_TablixColumnHierarchy(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy)
0x4c7  ldloc.1
0x4c8  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy::.ctor()
0x4cd  stloc.s  4
0x4cf  ldloc.s  4
0x4d1  ldc.i4.1
0x4d2  newarr   [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember
0x4d7  dup
0x4d8  ldc.i4.0
0x4d9  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember::.ctor()
0x4de  dup
0x4df  newobj   instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Group::.ctor()
0x4e4  dup
0x4e5  ldstr    aDetails// "Details"
0x4ea  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Group::set_Name(string)
0x4ef  dup
0x4f0  ldarga.s 0
0x4f2  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x4f7  brfalse.s loc_52D
0x4f9  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression>::.ctor()
0x4fe  dup
0x4ff  ldloca.s 5
0x501  initobj  [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression
0x507  ldloca.s 5
0x509  ldstr    aIifRownumberNo// "=IIf(RowNumber(Nothing) <= {0}, RowNumb"...
0x50e  ldarga.s 0
0x510  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x515  box      [mscorlib]System.Int32
0x51a  call     string [mscorlib]System.String::Format(string, object)
0x51f  call     instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression::set_Value(string)
0x524  ldloc.s  5
0x526  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression>::Add(var<u1>)
0x52b  br.s     loc_52E
0x52d  ldnull
0x52e  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Group::set_GroupExpressions(class [mscorlib]System.Collections.Generic.IList`1<valuetype [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportExpression>)
0x533  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.HierarchyMember::set_Group(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Group)
0x538  stelem.ref
0x539  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy::set_TablixMembers(class [mscorlib]System.Collections.Generic.IList`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixMember>)
0x53e  ldloc.s  4
0x540  callvirt instance void [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.Tablix::set_TablixRowHierarchy(class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.TablixHierarchy)
0x545  ldloc.1
0x546  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.ReportItem>::Add(var<u1>)
0x54b  ldloc.0
0x54c  ret
```
