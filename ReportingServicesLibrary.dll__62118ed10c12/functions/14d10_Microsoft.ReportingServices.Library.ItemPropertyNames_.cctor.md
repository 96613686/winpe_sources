# Microsoft.ReportingServices.Library.ItemPropertyNames::.cctor

- ea: `0x14d10`
- end: `0x14f03`
- name: `Microsoft.ReportingServices.Library.ItemPropertyNames::.cctor`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14cb0`

## string_xrefs

- `0x14d41`: `CreatedBy`
- `0x14e3f`: `CreatedBy`
- `0x14de0`: `ComponentID`
- `0x14ec4`: `ComponentID`
- `0x14d7d`: `HasScheduleReadyDataSources`
- `0x14e7c`: `HasScheduleReadyDataSources`
- `0x14d98`: `VirtualPath`
- `0x14e85`: `VirtualPath`
- `0x14dc5`: `HasValidReportLink`
- `0x14eb2`: `HasValidReportLink`

## pseudocode

```c

```

## disassembly

```asm
0x14d10  ldc.i4.s 0x1B
0x14d12  newarr   [mscorlib]System.String
0x14d17  dup
0x14d18  ldc.i4.0
0x14d19  ldstr    aName// "Name"
0x14d1e  stelem.ref
0x14d1f  dup
0x14d20  ldc.i4.1
0x14d21  ldstr    aPath_0// "Path"
0x14d26  stelem.ref
0x14d27  dup
0x14d28  ldc.i4.2
0x14d29  ldstr    aType_0// "Type"
0x14d2e  stelem.ref
0x14d2f  dup
0x14d30  ldc.i4.3
0x14d31  ldstr    aSize// "Size"
0x14d36  stelem.ref
0x14d37  dup
0x14d38  ldc.i4.4
0x14d39  ldstr    aId_2// "ID"
0x14d3e  stelem.ref
0x14d3f  dup
0x14d40  ldc.i4.5
0x14d41  ldstr    aCreatedby// "CreatedBy"
0x14d46  stelem.ref
0x14d47  dup
0x14d48  ldc.i4.6
0x14d49  ldstr    aCreationdate_0// "CreationDate"
0x14d4e  stelem.ref
0x14d4f  dup
0x14d50  ldc.i4.7
0x14d51  ldstr    aModifiedby// "ModifiedBy"
0x14d56  stelem.ref
0x14d57  dup
0x14d58  ldc.i4.8
0x14d59  ldstr    aModifieddate_0// "ModifiedDate"
0x14d5e  stelem.ref
0x14d5f  dup
0x14d60  ldc.i4.s 9
0x14d62  ldstr    aMimetype_1// "MIMEType"
0x14d67  stelem.ref
0x14d68  dup
0x14d69  ldc.i4.s 0xA
0x14d6b  ldstr    aCanrununattend// "CanRunUnattended"
0x14d70  stelem.ref
0x14d71  dup
0x14d72  ldc.i4.s 0xB
0x14d74  ldstr    aHasparameterde// "HasParameterDefaultValues"
0x14d79  stelem.ref
0x14d7a  dup
0x14d7b  ldc.i4.s 0xC
0x14d7d  ldstr    aHasschedulerea// "HasScheduleReadyDataSources"
0x14d82  stelem.ref
0x14d83  dup
0x14d84  ldc.i4.s 0xD
0x14d86  ldstr    aHasuserprofile// "HasUserProfileQueryDependencies"
0x14d8b  stelem.ref
0x14d8c  dup
0x14d8d  ldc.i4.s 0xE
0x14d8f  ldstr    aHasuserprofile_0// "HasUserProfileReportDependencies"
0x14d94  stelem.ref
0x14d95  dup
0x14d96  ldc.i4.s 0xF
0x14d98  ldstr    aVirtualpath// "VirtualPath"
0x14d9d  stelem.ref
0x14d9e  dup
0x14d9f  ldc.i4.s 0x10
0x14da1  ldstr    aExecutiondatet_0// "ExecutionDateTime"
0x14da6  stelem.ref
0x14da7  dup
0x14da8  ldc.i4.s 0x11
0x14daa  ldstr    aReserved// "Reserved"
0x14daf  stelem.ref
0x14db0  dup
0x14db1  ldc.i4.s 0x12
0x14db3  ldstr    aLanguage// "Language"
0x14db8  stelem.ref
0x14db9  dup
0x14dba  ldc.i4.s 0x13
0x14dbc  ldstr    aIssnapshotexec// "IsSnapshotExecution"
0x14dc1  stelem.ref
0x14dc2  dup
0x14dc3  ldc.i4.s 0x14
0x14dc5  ldstr    aHasvalidreport// "HasValidReportLink"
0x14dca  stelem.ref
0x14dcb  dup
0x14dcc  ldc.i4.s 0x15
0x14dce  ldstr    aIsgenerated// "IsGenerated"
0x14dd3  stelem.ref
0x14dd4  dup
0x14dd5  ldc.i4.s 0x16
0x14dd7  ldstr    aCangeneratemod// "CanGenerateModel"
0x14ddc  stelem.ref
0x14ddd  dup
0x14dde  ldc.i4.s 0x17
0x14de0  ldstr    aComponentid_0// "ComponentID"
0x14de5  stelem.ref
0x14de6  dup
0x14de7  ldc.i4.s 0x18
0x14de9  ldstr    aHasdatasourcec// "HasDataSourceCredentials"
0x14dee  stelem.ref
0x14def  dup
0x14df0  ldc.i4.s 0x19
0x14df2  ldstr    aHasuserprofile_1// "HasUserProfileDependencies"
0x14df7  stelem.ref
0x14df8  dup
0x14df9  ldc.i4.s 0x1A
0x14dfb  ldstr    aSubtype_0// "Subtype"
0x14e00  stelem.ref
0x14e01  stsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyPropertyNames
0x14e06  ldc.i4.s 0x1A
0x14e08  newarr   [mscorlib]System.String
0x14e0d  dup
0x14e0e  ldc.i4.0
0x14e0f  ldstr    aName// "Name"
0x14e14  stelem.ref
0x14e15  dup
0x14e16  ldc.i4.1
0x14e17  ldstr    aPath_0// "Path"
0x14e1c  stelem.ref
0x14e1d  dup
0x14e1e  ldc.i4.2
0x14e1f  ldstr    aType_0// "Type"
0x14e24  stelem.ref
0x14e25  dup
0x14e26  ldc.i4.3
0x14e27  ldstr    aSize// "Size"
0x14e2c  stelem.ref
0x14e2d  dup
0x14e2e  ldc.i4.4
0x14e2f  ldstr    aId_2// "ID"
0x14e34  stelem.ref
0x14e35  dup
0x14e36  ldc.i4.5
0x14e37  ldstr    aDescription_0// "Description"
0x14e3c  stelem.ref
0x14e3d  dup
0x14e3e  ldc.i4.6
0x14e3f  ldstr    aCreatedby// "CreatedBy"
0x14e44  stelem.ref
0x14e45  dup
0x14e46  ldc.i4.7
0x14e47  ldstr    aCreationdate_0// "CreationDate"
0x14e4c  stelem.ref
0x14e4d  dup
0x14e4e  ldc.i4.8
0x14e4f  ldstr    aModifiedby// "ModifiedBy"
0x14e54  stelem.ref
0x14e55  dup
0x14e56  ldc.i4.s 9
0x14e58  ldstr    aModifieddate_0// "ModifiedDate"
0x14e5d  stelem.ref
0x14e5e  dup
0x14e5f  ldc.i4.s 0xA
0x14e61  ldstr    aMimetype_1// "MIMEType"
0x14e66  stelem.ref
0x14e67  dup
0x14e68  ldc.i4.s 0xB
0x14e6a  ldstr    aCanrununattend// "CanRunUnattended"
0x14e6f  stelem.ref
0x14e70  dup
0x14e71  ldc.i4.s 0xC
0x14e73  ldstr    aHasparameterde// "HasParameterDefaultValues"
0x14e78  stelem.ref
0x14e79  dup
0x14e7a  ldc.i4.s 0xD
0x14e7c  ldstr    aHasschedulerea// "HasScheduleReadyDataSources"
0x14e81  stelem.ref
0x14e82  dup
0x14e83  ldc.i4.s 0xE
0x14e85  ldstr    aVirtualpath// "VirtualPath"
0x14e8a  stelem.ref
0x14e8b  dup
0x14e8c  ldc.i4.s 0xF
0x14e8e  ldstr    aExecutiondatet_0// "ExecutionDateTime"
0x14e93  stelem.ref
0x14e94  dup
0x14e95  ldc.i4.s 0x10
0x14e97  ldstr    aReserved// "Reserved"
0x14e9c  stelem.ref
0x14e9d  dup
0x14e9e  ldc.i4.s 0x11
0x14ea0  ldstr    aHidden_0// "Hidden"
0x14ea5  stelem.ref
0x14ea6  dup
0x14ea7  ldc.i4.s 0x12
0x14ea9  ldstr    aIssnapshotexec// "IsSnapshotExecution"
0x14eae  stelem.ref
0x14eaf  dup
0x14eb0  ldc.i4.s 0x13
0x14eb2  ldstr    aHasvalidreport// "HasValidReportLink"
0x14eb7  stelem.ref
0x14eb8  dup
0x14eb9  ldc.i4.s 0x14
0x14ebb  ldstr    aCangeneratemod// "CanGenerateModel"
0x14ec0  stelem.ref
0x14ec1  dup
0x14ec2  ldc.i4.s 0x15
0x14ec4  ldstr    aComponentid_0// "ComponentID"
0x14ec9  stelem.ref
0x14eca  dup
0x14ecb  ldc.i4.s 0x16
0x14ecd  ldstr    aHasdatasourcec// "HasDataSourceCredentials"
0x14ed2  stelem.ref
0x14ed3  dup
0x14ed4  ldc.i4.s 0x17
0x14ed6  ldstr    aHasuserprofile_1// "HasUserProfileDependencies"
0x14edb  stelem.ref
0x14edc  dup
0x14edd  ldc.i4.s 0x18
0x14edf  ldstr    aSubtype_0// "Subtype"
0x14ee4  stelem.ref
0x14ee5  dup
0x14ee6  ldc.i4.s 0x19
0x14ee8  ldstr    aParentid_0// "ParentID"
0x14eed  stelem.ref
0x14eee  stsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::SpecialPropertyNames
0x14ef3  ldsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyPropertyNames
0x14ef8  call     class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.PropertyHashTable::Create(string[] strings)
0x14efd  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyProperties
0x14f02  ret
```
