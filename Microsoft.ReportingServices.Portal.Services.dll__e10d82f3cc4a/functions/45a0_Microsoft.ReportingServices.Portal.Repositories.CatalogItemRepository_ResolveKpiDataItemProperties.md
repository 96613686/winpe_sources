# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties

- ea: `0x45a0`
- end: `0x481a`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveKpiDataItemProperties`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4260`

## callees

- `0x45a0`
- `0x48b0`
- `0xa840`
- `0x12880`

## string_xrefs

- `0x4733`: `{0}.Path`

## pseudocode

```c

```

## disassembly

```asm
0x45a0  ldsfld   string [mscorlib]System.String::Empty
0x45a5  stloc.0
0x45a6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x45ab  stloc.1
0x45ac  ldsfld   string [mscorlib]System.String::Empty
0x45b1  stloc.2
0x45b2  ldsfld   string [mscorlib]System.String::Empty
0x45b7  stloc.3
0x45b8  ldsfld   string [mscorlib]System.String::Empty
0x45bd  stloc.s  4
0x45bf  ldsfld   string [mscorlib]System.String::Empty
0x45c4  stloc.s  5
0x45c6  ldsfld   string [mscorlib]System.String::Empty
0x45cb  stloc.s  6
0x45cd  ldarg.2
0x45ce  brfalse.s loc_45F1
0x45d0  ldarg.2
0x45d1  isinst   valuetype [mscorlib]System.Nullable`1<float64>[]
0x45d6  brtrue.s loc_45E5
0x45d8  ldarg.2
0x45d9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x45de  call     string [mscorlib]System.Convert::ToString(object, class [mscorlib]System.IFormatProvider)
0x45e3  br.s     loc_45F0
0x45e5  ldarg.2
0x45e6  isinst   valuetype [mscorlib]System.Nullable`1<float64>[]
0x45eb  call     string [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::SerializeObject(object)
0x45f0  stloc.0
0x45f1  ldarg.1
0x45f2  brfalse  loc_46C8
0x45f7  ldarg.1
0x45f8  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0x45fd  stloc.s  7
0x45ff  ldloca.s 7
0x4601  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4606  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x460b  stloc.s  4
0x460d  ldarg.1
0x460e  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItemType [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiDataItem::get_Type()
0x4613  ldc.i4.1
0x4614  bne.un   loc_46B7
0x4619  ldarg.1
0x461a  isinst   [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem
0x461f  stloc.s  8
0x4621  ldarg.3
0x4622  ldloc.s  8
0x4624  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Id()
0x4629  ldloc.s  8
0x462b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Path()
0x4630  ldc.i4.8
0x4631  ldc.i4.1
0x4632  ldloca.s 1
0x4634  ldloca.s 2
0x4636  callvirt instance void Microsoft.ReportingServices.Portal.Services.Extensions.ResolveCatalogItem::Invoke(valuetype [mscorlib]System.Guid id, string path, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.ItemType itemType, bool throwIfNotExists, [out] valuetype [mscorlib]System.Guid& actualId, [out] string& actualPath)
0x463b  ldarg.s  5
0x463d  ldarg.0
0x463e  ldloc.2
0x463f  ldloc.1
0x4640  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo::.ctor(string, string, valuetype [mscorlib]System.Guid)
0x4645  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfoCollection::Add(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSetInfo)
0x464a  ldloc.s  8
0x464c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Column()
0x4651  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x4656  brtrue.s loc_4665
0x4658  ldloc.s  8
0x465a  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Column()
0x465f  callvirt instance string [mscorlib]System.String::Trim()
0x4664  stloc.3
0x4665  ldarg.0
0x4666  ldstr    aTrendset// "TrendSet"
0x466b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4670  brfalse.s loc_4680
0x4672  ldc.i4.0
0x4673  stloc.s  7
0x4675  ldloca.s 7
0x4677  call     instance string [mscorlib]System.Int32::ToString()
0x467c  stloc.s  5
0x467e  br.s     loc_46A9
0x4680  ldloc.s  8
0x4682  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Aggregation()
0x4687  brtrue.s loc_4697
0x4689  ldc.i4.1
0x468a  stloc.s  7
0x468c  ldloca.s 7
0x468e  call     instance string [mscorlib]System.Int32::ToString()
0x4693  stloc.s  5
0x4695  br.s     loc_46A9
0x4697  ldloc.s  8
0x4699  callvirt instance valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItemAggregation [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Aggregation()
0x469e  stloc.s  7
0x46a0  ldloca.s 7
0x46a2  call     instance string [mscorlib]System.Int32::ToString()
0x46a7  stloc.s  5
0x46a9  ldloc.s  8
0x46ab  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> [Microsoft.ReportingServices.Portal.Interfaces]Model.KpiSharedDataItem::get_Parameters()
0x46b0  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ResolveDataSetParameters(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSetParameter> parameters)
0x46b5  stloc.s  6
0x46b7  leave.s  loc_46C8
0x46b9  stloc.s  9
0x46bb  call     string Microsoft.ReportingServices.Portal.Services.SR::get_Error_CatalogItemPropertyInvalid()
0x46c0  ldloc.s  9
0x46c2  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Microsoft.ReportingServices.Portal.Interfaces.Exceptions.CatalogItemPropertyInvalidException::.ctor(string, class [mscorlib]System.Exception)
0x46c7  throw
0x46c8  ldarg.s  4
0x46ca  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x46cf  dup
0x46d0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x46d5  ldstr    a0Value// "{0}.Value"
0x46da  ldarg.0
0x46db  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x46e0  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x46e5  dup
0x46e6  ldloc.s  4
0x46e8  brtrue.s loc_46F1
0x46ea  ldsfld   string [mscorlib]System.String::Empty
0x46ef  br.s     loc_46F2
0x46f1  ldloc.0
0x46f2  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x46f7  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x46fc  ldarg.s  4
0x46fe  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4703  dup
0x4704  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4709  ldstr    a0Type// "{0}.Type"
0x470e  ldarg.0
0x470f  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4714  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4719  dup
0x471a  ldloc.s  4
0x471c  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4721  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4726  ldarg.s  4
0x4728  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x472d  dup
0x472e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4733  ldstr    a0Path// "{0}.Path"
0x4738  ldarg.0
0x4739  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x473e  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x4743  dup
0x4744  ldloc.2
0x4745  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x474a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x474f  ldarg.s  4
0x4751  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x4756  dup
0x4757  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x475c  ldstr    a0Id// "{0}.Id"
0x4761  ldarg.0
0x4762  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4767  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x476c  dup
0x476d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4772  stloc.s  0xA
0x4774  ldloca.s 0xA
0x4776  ldloc.1
0x4777  call     instance bool [mscorlib]System.Guid::Equals(valuetype [mscorlib]System.Guid)
0x477c  brtrue.s loc_478D
0x477e  ldloca.s 1
0x4780  constrained. [mscorlib]System.Guid
0x4786  callvirt instance string [mscorlib]System.Object::ToString()
0x478b  br.s     loc_4792
0x478d  ldsfld   string [mscorlib]System.String::Empty
0x4792  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4797  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x479c  ldarg.s  4
0x479e  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x47a3  dup
0x47a4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47a9  ldstr    a0Column// "{0}.Column"
0x47ae  ldarg.0
0x47af  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x47b4  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x47b9  dup
0x47ba  ldloc.3
0x47bb  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x47c0  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x47c5  ldarg.s  4
0x47c7  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x47cc  dup
0x47cd  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47d2  ldstr    a0Aggregation// "{0}.Aggregation"
0x47d7  ldarg.0
0x47d8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x47dd  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x47e2  dup
0x47e3  ldloc.s  5
0x47e5  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x47ea  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x47ef  ldarg.s  4
0x47f1  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::.ctor()
0x47f6  dup
0x47f7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x47fc  ldstr    a0Parameters// "{0}.Parameters"
0x4801  ldarg.0
0x4802  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x4807  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Name
0x480c  dup
0x480d  ldloc.s  6
0x480f  stfld    string [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property::Value
0x4814  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.Soap.Property>::Add(var<u1>)
0x4819  ret
```
