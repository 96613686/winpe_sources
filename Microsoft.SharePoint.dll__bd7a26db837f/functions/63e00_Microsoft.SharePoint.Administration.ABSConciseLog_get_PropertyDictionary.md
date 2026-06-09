# Microsoft.SharePoint.Administration.ABSConciseLog::get_PropertyDictionary

- ea: `0x63e00`
- end: `0x64173`
- name: `Microsoft.SharePoint.Administration.ABSConciseLog::get_PropertyDictionary`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x64180`

## string_xrefs

- `0x63e2e`: `WriteBlobsElapsedTime`
- `0x63e5a`: `WriteBlobsExecutionTime`
- `0x63e86`: `WriteBlobsCPUCycles`
- `0x63f20`: `WriteBlobsCount`
- `0x63f36`: `WriteBlobsSuccessCount`
- `0x63f62`: `WriteBlobsBytesSuccess`
- `0x63f78`: `TotalCancelledReadCount`
- `0x63f8e`: `CancelledNearReadCount`
- `0x63fa4`: `DeleteBlobsElapsedTime`
- `0x63fba`: `DeleteBlobsCount`
- `0x63fd0`: `DeleteBlobsSuccessCount`
- `0x63fe6`: `GetDeletedBlobsCount`
- `0x64028`: `WriteBlobGroupsCount`
- `0x6403e`: `WriteBlobGroupsSuccessCount`
- `0x6406a`: `ApplySiteKeyForWriteBlobExecutionTime`
- `0x64080`: `SiteKeyConfigLoadTimeForGetBlob`
- `0x64096`: `SiteKeyConfigLoadTimeForWriteBlob`
- `0x640ac`: `WriteFarBlobsExecutionTime`
- `0x640d8`: `WriteBlobsAwaitTime`
- `0x64104`: `WriteBlobsFirstByteTime`
- `0x6415c`: `DeleteBlobScheduledCount`

## pseudocode

```c

```

## disassembly

```asm
0x63e00  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x63e05  stloc.0
0x63e06  ldloc.0
0x63e07  ldstr    aPartitionkey// "PartitionKey"
0x63e0c  ldarg.0
0x63e0d  ldfld    string Microsoft.SharePoint.Administration.ABSConciseLog::PartitionKey
0x63e12  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e17  ldloc.0
0x63e18  ldstr    aGetblobselapse// "GetBlobsElapsedTime"
0x63e1d  ldarg.0
0x63e1e  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsElapsedTime
0x63e23  box      [mscorlib]System.Int64
0x63e28  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e2d  ldloc.0
0x63e2e  ldstr    aWriteblobselap// "WriteBlobsElapsedTime"
0x63e33  ldarg.0
0x63e34  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsElapsedTime
0x63e39  box      [mscorlib]System.Int64
0x63e3e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e43  ldloc.0
0x63e44  ldstr    aGetblobsexecut// "GetBlobsExecutionTime"
0x63e49  ldarg.0
0x63e4a  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsExecutionTime
0x63e4f  box      [mscorlib]System.Int64
0x63e54  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e59  ldloc.0
0x63e5a  ldstr    aWriteblobsexec// "WriteBlobsExecutionTime"
0x63e5f  ldarg.0
0x63e60  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsExecutionTime
0x63e65  box      [mscorlib]System.Int64
0x63e6a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e6f  ldloc.0
0x63e70  ldstr    aGetblobscpucyc// "GetBlobsCPUCycles"
0x63e75  ldarg.0
0x63e76  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsCPUCycles
0x63e7b  box      [mscorlib]System.Int64
0x63e80  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e85  ldloc.0
0x63e86  ldstr    aWriteblobscpuc// "WriteBlobsCPUCycles"
0x63e8b  ldarg.0
0x63e8c  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsCPUCycles
0x63e91  box      [mscorlib]System.Int64
0x63e96  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63e9b  ldloc.0
0x63e9c  ldstr    aEncryptiontime// "EncryptionTime"
0x63ea1  ldarg.0
0x63ea2  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::EncryptionTime
0x63ea7  box      [mscorlib]System.Int64
0x63eac  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63eb1  ldloc.0
0x63eb2  ldstr    aEncryptioncycl// "EncryptionCycles"
0x63eb7  ldarg.0
0x63eb8  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::EncryptionCycles
0x63ebd  box      [mscorlib]System.Int64
0x63ec2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63ec7  ldloc.0
0x63ec8  ldstr    aDecryptiontime// "DecryptionTime"
0x63ecd  ldarg.0
0x63ece  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DecryptionTime
0x63ed3  box      [mscorlib]System.Int64
0x63ed8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63edd  ldloc.0
0x63ede  ldstr    aDecryptioncycl// "DecryptionCycles"
0x63ee3  ldarg.0
0x63ee4  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DecryptionCycles
0x63ee9  box      [mscorlib]System.Int64
0x63eee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63ef3  ldloc.0
0x63ef4  ldstr    aGetblobscount// "GetBlobsCount"
0x63ef9  ldarg.0
0x63efa  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsCount
0x63eff  box      [mscorlib]System.Int32
0x63f04  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f09  ldloc.0
0x63f0a  ldstr    aGetblobssucces// "GetBlobsSuccessCount"
0x63f0f  ldarg.0
0x63f10  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsSuccessCount
0x63f15  box      [mscorlib]System.Int32
0x63f1a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f1f  ldloc.0
0x63f20  ldstr    aWriteblobscoun// "WriteBlobsCount"
0x63f25  ldarg.0
0x63f26  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsCount
0x63f2b  box      [mscorlib]System.Int32
0x63f30  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f35  ldloc.0
0x63f36  ldstr    aWriteblobssucc// "WriteBlobsSuccessCount"
0x63f3b  ldarg.0
0x63f3c  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsSuccessCount
0x63f41  box      [mscorlib]System.Int32
0x63f46  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f4b  ldloc.0
0x63f4c  ldstr    aGetblobsbytess// "GetBlobsBytesSuccess"
0x63f51  ldarg.0
0x63f52  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsBytesSuccess
0x63f57  box      [mscorlib]System.Int64
0x63f5c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f61  ldloc.0
0x63f62  ldstr    aWriteblobsbyte// "WriteBlobsBytesSuccess"
0x63f67  ldarg.0
0x63f68  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsBytesSuccess
0x63f6d  box      [mscorlib]System.Int64
0x63f72  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f77  ldloc.0
0x63f78  ldstr    aTotalcancelled// "TotalCancelledReadCount"
0x63f7d  ldarg.0
0x63f7e  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::TotalCancelledReadCount
0x63f83  box      [mscorlib]System.Int64
0x63f88  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63f8d  ldloc.0
0x63f8e  ldstr    aCancellednearr// "CancelledNearReadCount"
0x63f93  ldarg.0
0x63f94  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::CancelledNearReadCount
0x63f99  box      [mscorlib]System.Int64
0x63f9e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63fa3  ldloc.0
0x63fa4  ldstr    aDeleteblobsela// "DeleteBlobsElapsedTime"
0x63fa9  ldarg.0
0x63faa  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DeleteBlobsElapsedTime
0x63faf  box      [mscorlib]System.Int64
0x63fb4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63fb9  ldloc.0
0x63fba  ldstr    aDeleteblobscou// "DeleteBlobsCount"
0x63fbf  ldarg.0
0x63fc0  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DeleteBlobsCount
0x63fc5  box      [mscorlib]System.Int64
0x63fca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63fcf  ldloc.0
0x63fd0  ldstr    aDeleteblobssuc// "DeleteBlobsSuccessCount"
0x63fd5  ldarg.0
0x63fd6  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DeleteBlobsSuccessCount
0x63fdb  box      [mscorlib]System.Int64
0x63fe0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63fe5  ldloc.0
0x63fe6  ldstr    aGetdeletedblob// "GetDeletedBlobsCount"
0x63feb  ldarg.0
0x63fec  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetDeletedBlobsCount
0x63ff1  box      [mscorlib]System.Int64
0x63ff6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x63ffb  ldloc.0
0x63ffc  ldstr    aGetblobgroupsc// "GetBlobGroupsCount"
0x64001  ldarg.0
0x64002  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobGroupsCount
0x64007  box      [mscorlib]System.Int32
0x6400c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64011  ldloc.0
0x64012  ldstr    aGetblobgroupss// "GetBlobGroupsSuccessCount"
0x64017  ldarg.0
0x64018  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobGroupsSuccessCount
0x6401d  box      [mscorlib]System.Int32
0x64022  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64027  ldloc.0
0x64028  ldstr    aWriteblobgroup// "WriteBlobGroupsCount"
0x6402d  ldarg.0
0x6402e  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobGroupsCount
0x64033  box      [mscorlib]System.Int32
0x64038  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6403d  ldloc.0
0x6403e  ldstr    aWriteblobgroup_0// "WriteBlobGroupsSuccessCount"
0x64043  ldarg.0
0x64044  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobGroupsSuccessCount
0x64049  box      [mscorlib]System.Int32
0x6404e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64053  ldloc.0
0x64054  ldstr    aApplysitekeyfo// "ApplySiteKeyForGetBlobExecutionTime"
0x64059  ldarg.0
0x6405a  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::ApplySiteKeyForGetBlobExecutionTime
0x6405f  box      [mscorlib]System.Int64
0x64064  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64069  ldloc.0
0x6406a  ldstr    aApplysitekeyfo_0// "ApplySiteKeyForWriteBlobExecutionTime"
0x6406f  ldarg.0
0x64070  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::ApplySiteKeyForWriteBlobExecutionTime
0x64075  box      [mscorlib]System.Int64
0x6407a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6407f  ldloc.0
0x64080  ldstr    aSitekeyconfigl// "SiteKeyConfigLoadTimeForGetBlob"
0x64085  ldarg.0
0x64086  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::SiteKeyConfigLoadTimeForGetBlob
0x6408b  box      [mscorlib]System.Int64
0x64090  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64095  ldloc.0
0x64096  ldstr    aSitekeyconfigl_0// "SiteKeyConfigLoadTimeForWriteBlob"
0x6409b  ldarg.0
0x6409c  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::SiteKeyConfigLoadTimeForWriteBlob
0x640a1  box      [mscorlib]System.Int64
0x640a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x640ab  ldloc.0
0x640ac  ldstr    aWritefarblobse// "WriteFarBlobsExecutionTime"
0x640b1  ldarg.0
0x640b2  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteFarBlobsExecutionTime
0x640b7  box      [mscorlib]System.Int64
0x640bc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x640c1  ldloc.0
0x640c2  ldstr    aGetblobsawaitt// "GetBlobsAwaitTime"
0x640c7  ldarg.0
0x640c8  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsAwaitTime
0x640cd  box      [mscorlib]System.Int64
0x640d2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x640d7  ldloc.0
0x640d8  ldstr    aWriteblobsawai// "WriteBlobsAwaitTime"
0x640dd  ldarg.0
0x640de  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsAwaitTime
0x640e3  box      [mscorlib]System.Int64
0x640e8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x640ed  ldloc.0
0x640ee  ldstr    aGetblobsfirstb// "GetBlobsFirstByteTime"
0x640f3  ldarg.0
0x640f4  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::GetBlobsFirstByteTime
0x640f9  box      [mscorlib]System.Int64
0x640fe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64103  ldloc.0
0x64104  ldstr    aWriteblobsfirs// "WriteBlobsFirstByteTime"
0x64109  ldarg.0
0x6410a  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::WriteBlobsFirstByteTime
0x6410f  box      [mscorlib]System.Int64
0x64114  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64119  ldloc.0
0x6411a  ldstr    aValidateblobgr// "ValidateBlobGroupsCount"
0x6411f  ldarg.0
0x64120  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::ValidateBlobGroupsCount
0x64125  box      [mscorlib]System.Int32
0x6412a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6412f  ldloc.0
0x64130  ldstr    aValidateblobgr_0// "ValidateBlobGroupsSuccessCount"
0x64135  ldarg.0
0x64136  ldfld    int32 Microsoft.SharePoint.Administration.ABSConciseLog::ValidateBlobGroupsSuccessCount
0x6413b  box      [mscorlib]System.Int32
0x64140  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64145  ldloc.0
0x64146  ldstr    aValidateblobse// "ValidateBlobsElapsedTime"
0x6414b  ldarg.0
0x6414c  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::ValidateBlobsElapsedTime
0x64151  box      [mscorlib]System.Int64
0x64156  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6415b  ldloc.0
0x6415c  ldstr    aDeleteblobsche// "DeleteBlobScheduledCount"
0x64161  ldarg.0
0x64162  ldfld    int64 Microsoft.SharePoint.Administration.ABSConciseLog::DeleteBlobScheduledCount
0x64167  box      [mscorlib]System.Int64
0x6416c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64171  ldloc.0
0x64172  ret
```
