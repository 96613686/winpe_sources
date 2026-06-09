# Microsoft.ReportingServices.Library.ItemPropertyNames::.cctor

- ea: `0x4400`
- end: `0x45f3`
- name: `Microsoft.ReportingServices.Library.ItemPropertyNames::.cctor`
- size: `499`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x43a0`

## string_xrefs

- `0x4431`: `CreatedBy`
- `0x452f`: `CreatedBy`
- `0x446d`: `HasScheduleReadyDataSources`
- `0x456c`: `HasScheduleReadyDataSources`
- `0x4488`: `VirtualPath`
- `0x4575`: `VirtualPath`
- `0x44b5`: `HasValidReportLink`
- `0x45a2`: `HasValidReportLink`
- `0x44d0`: `ComponentID`
- `0x45b4`: `ComponentID`

## pseudocode

```c

```

## disassembly

```asm
0x4400  ldc.i4.s 0x1B
0x4402  newarr   [mscorlib]System.String
0x4407  dup
0x4408  ldc.i4.0
0x4409  ldstr    aName_0// "Name"
0x440e  stelem.ref
0x440f  dup
0x4410  ldc.i4.1
0x4411  ldstr    aPath// "Path"
0x4416  stelem.ref
0x4417  dup
0x4418  ldc.i4.2
0x4419  ldstr    aType// "Type"
0x441e  stelem.ref
0x441f  dup
0x4420  ldc.i4.3
0x4421  ldstr    aSize// "Size"
0x4426  stelem.ref
0x4427  dup
0x4428  ldc.i4.4
0x4429  ldstr    aId_0// "ID"
0x442e  stelem.ref
0x442f  dup
0x4430  ldc.i4.5
0x4431  ldstr    aCreatedby// "CreatedBy"
0x4436  stelem.ref
0x4437  dup
0x4438  ldc.i4.6
0x4439  ldstr    aCreationdate// "CreationDate"
0x443e  stelem.ref
0x443f  dup
0x4440  ldc.i4.7
0x4441  ldstr    aModifiedby// "ModifiedBy"
0x4446  stelem.ref
0x4447  dup
0x4448  ldc.i4.8
0x4449  ldstr    aModifieddate// "ModifiedDate"
0x444e  stelem.ref
0x444f  dup
0x4450  ldc.i4.s 9
0x4452  ldstr    aMimetype// "MIMEType"
0x4457  stelem.ref
0x4458  dup
0x4459  ldc.i4.s 0xA
0x445b  ldstr    aCanrununattend// "CanRunUnattended"
0x4460  stelem.ref
0x4461  dup
0x4462  ldc.i4.s 0xB
0x4464  ldstr    aHasparameterde// "HasParameterDefaultValues"
0x4469  stelem.ref
0x446a  dup
0x446b  ldc.i4.s 0xC
0x446d  ldstr    aHasschedulerea// "HasScheduleReadyDataSources"
0x4472  stelem.ref
0x4473  dup
0x4474  ldc.i4.s 0xD
0x4476  ldstr    aHasuserprofile// "HasUserProfileQueryDependencies"
0x447b  stelem.ref
0x447c  dup
0x447d  ldc.i4.s 0xE
0x447f  ldstr    aHasuserprofile_0// "HasUserProfileReportDependencies"
0x4484  stelem.ref
0x4485  dup
0x4486  ldc.i4.s 0xF
0x4488  ldstr    aVirtualpath// "VirtualPath"
0x448d  stelem.ref
0x448e  dup
0x448f  ldc.i4.s 0x10
0x4491  ldstr    aExecutiondatet// "ExecutionDateTime"
0x4496  stelem.ref
0x4497  dup
0x4498  ldc.i4.s 0x11
0x449a  ldstr    aReserved// "Reserved"
0x449f  stelem.ref
0x44a0  dup
0x44a1  ldc.i4.s 0x12
0x44a3  ldstr    aLanguage// "Language"
0x44a8  stelem.ref
0x44a9  dup
0x44aa  ldc.i4.s 0x13
0x44ac  ldstr    aIssnapshotexec// "IsSnapshotExecution"
0x44b1  stelem.ref
0x44b2  dup
0x44b3  ldc.i4.s 0x14
0x44b5  ldstr    aHasvalidreport// "HasValidReportLink"
0x44ba  stelem.ref
0x44bb  dup
0x44bc  ldc.i4.s 0x15
0x44be  ldstr    aIsgenerated// "IsGenerated"
0x44c3  stelem.ref
0x44c4  dup
0x44c5  ldc.i4.s 0x16
0x44c7  ldstr    aCangeneratemod// "CanGenerateModel"
0x44cc  stelem.ref
0x44cd  dup
0x44ce  ldc.i4.s 0x17
0x44d0  ldstr    aComponentid// "ComponentID"
0x44d5  stelem.ref
0x44d6  dup
0x44d7  ldc.i4.s 0x18
0x44d9  ldstr    aHasdatasourcec// "HasDataSourceCredentials"
0x44de  stelem.ref
0x44df  dup
0x44e0  ldc.i4.s 0x19
0x44e2  ldstr    aHasuserprofile_1// "HasUserProfileDependencies"
0x44e7  stelem.ref
0x44e8  dup
0x44e9  ldc.i4.s 0x1A
0x44eb  ldstr    aSubtype// "Subtype"
0x44f0  stelem.ref
0x44f1  stsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyPropertyNames
0x44f6  ldc.i4.s 0x1A
0x44f8  newarr   [mscorlib]System.String
0x44fd  dup
0x44fe  ldc.i4.0
0x44ff  ldstr    aName_0// "Name"
0x4504  stelem.ref
0x4505  dup
0x4506  ldc.i4.1
0x4507  ldstr    aPath// "Path"
0x450c  stelem.ref
0x450d  dup
0x450e  ldc.i4.2
0x450f  ldstr    aType// "Type"
0x4514  stelem.ref
0x4515  dup
0x4516  ldc.i4.3
0x4517  ldstr    aSize// "Size"
0x451c  stelem.ref
0x451d  dup
0x451e  ldc.i4.4
0x451f  ldstr    aId_0// "ID"
0x4524  stelem.ref
0x4525  dup
0x4526  ldc.i4.5
0x4527  ldstr    aDescription// "Description"
0x452c  stelem.ref
0x452d  dup
0x452e  ldc.i4.6
0x452f  ldstr    aCreatedby// "CreatedBy"
0x4534  stelem.ref
0x4535  dup
0x4536  ldc.i4.7
0x4537  ldstr    aCreationdate// "CreationDate"
0x453c  stelem.ref
0x453d  dup
0x453e  ldc.i4.8
0x453f  ldstr    aModifiedby// "ModifiedBy"
0x4544  stelem.ref
0x4545  dup
0x4546  ldc.i4.s 9
0x4548  ldstr    aModifieddate// "ModifiedDate"
0x454d  stelem.ref
0x454e  dup
0x454f  ldc.i4.s 0xA
0x4551  ldstr    aMimetype// "MIMEType"
0x4556  stelem.ref
0x4557  dup
0x4558  ldc.i4.s 0xB
0x455a  ldstr    aCanrununattend// "CanRunUnattended"
0x455f  stelem.ref
0x4560  dup
0x4561  ldc.i4.s 0xC
0x4563  ldstr    aHasparameterde// "HasParameterDefaultValues"
0x4568  stelem.ref
0x4569  dup
0x456a  ldc.i4.s 0xD
0x456c  ldstr    aHasschedulerea// "HasScheduleReadyDataSources"
0x4571  stelem.ref
0x4572  dup
0x4573  ldc.i4.s 0xE
0x4575  ldstr    aVirtualpath// "VirtualPath"
0x457a  stelem.ref
0x457b  dup
0x457c  ldc.i4.s 0xF
0x457e  ldstr    aExecutiondatet// "ExecutionDateTime"
0x4583  stelem.ref
0x4584  dup
0x4585  ldc.i4.s 0x10
0x4587  ldstr    aReserved// "Reserved"
0x458c  stelem.ref
0x458d  dup
0x458e  ldc.i4.s 0x11
0x4590  ldstr    aHidden// "Hidden"
0x4595  stelem.ref
0x4596  dup
0x4597  ldc.i4.s 0x12
0x4599  ldstr    aIssnapshotexec// "IsSnapshotExecution"
0x459e  stelem.ref
0x459f  dup
0x45a0  ldc.i4.s 0x13
0x45a2  ldstr    aHasvalidreport// "HasValidReportLink"
0x45a7  stelem.ref
0x45a8  dup
0x45a9  ldc.i4.s 0x14
0x45ab  ldstr    aCangeneratemod// "CanGenerateModel"
0x45b0  stelem.ref
0x45b1  dup
0x45b2  ldc.i4.s 0x15
0x45b4  ldstr    aComponentid// "ComponentID"
0x45b9  stelem.ref
0x45ba  dup
0x45bb  ldc.i4.s 0x16
0x45bd  ldstr    aHasdatasourcec// "HasDataSourceCredentials"
0x45c2  stelem.ref
0x45c3  dup
0x45c4  ldc.i4.s 0x17
0x45c6  ldstr    aHasuserprofile_1// "HasUserProfileDependencies"
0x45cb  stelem.ref
0x45cc  dup
0x45cd  ldc.i4.s 0x18
0x45cf  ldstr    aSubtype// "Subtype"
0x45d4  stelem.ref
0x45d5  dup
0x45d6  ldc.i4.s 0x19
0x45d8  ldstr    aParentid// "ParentID"
0x45dd  stelem.ref
0x45de  stsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::SpecialPropertyNames
0x45e3  ldsfld   string[] Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyPropertyNames
0x45e8  call     class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.PropertyHashTable::Create(string[] strings)
0x45ed  stsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.ItemPropertyNames::ItemReadOnlyProperties
0x45f2  ret
```
