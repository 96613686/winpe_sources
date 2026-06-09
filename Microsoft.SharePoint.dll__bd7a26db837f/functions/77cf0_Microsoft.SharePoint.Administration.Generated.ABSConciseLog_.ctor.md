# Microsoft.SharePoint.Administration.Generated.ABSConciseLog::.ctor

- ea: `0x77cf0`
- end: `0x78330`
- name: `Microsoft.SharePoint.Administration.Generated.ABSConciseLog::.ctor`
- size: `1600`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6ddb0`

## callees

- `0x6edf0`
- `0x77800`
- `0x77820`
- `0x77840`
- `0x77860`
- `0x77880`
- `0x778a0`
- `0x778c0`
- `0x778e0`
- `0x77900`
- `0x77920`
- `0x77940`
- `0x77960`
- `0x77980`
- `0x779a0`
- `0x779c0`
- `0x779e0`
- `0x77a00`
- `0x77a20`
- `0x77a40`
- `0x77a60`
- `0x77a80`
- `0x77aa0`
- `0x77ac0`
- `0x77ae0`
- `0x77b00`
- `0x77b20`
- `0x77b40`
- `0x77b60`
- `0x77b80`
- `0x77ba0`
- `0x77bc0`
- `0x77be0`
- `0x77c00`
- `0x77c20`
- `0x77c40`
- `0x77c60`
- `0x77c80`
- `0x77ca0`
- `0x77cc0`
- `0x77ce0`
- `0x77cf0`
- `0x37a4e0`

## string_xrefs

- `0x77d45`: `WriteBlobsElapsedTime`
- `0x77d95`: `WriteBlobsExecutionTime`
- `0x77de5`: `WriteBlobsCPUCycles`
- `0x77efd`: `WriteBlobsCount`
- `0x77f25`: `WriteBlobsSuccessCount`
- `0x77f75`: `WriteBlobsBytesSuccess`
- `0x77f9d`: `TotalCancelledReadCount`
- `0x77fc5`: `CancelledNearReadCount`
- `0x77fed`: `DeleteBlobsElapsedTime`
- `0x78015`: `DeleteBlobsCount`
- `0x7803d`: `DeleteBlobsSuccessCount`
- `0x78065`: `GetDeletedBlobsCount`
- `0x780dd`: `WriteBlobGroupsCount`
- `0x78105`: `WriteBlobGroupsSuccessCount`
- `0x78155`: `ApplySiteKeyForWriteBlobExecutionTime`
- `0x7817d`: `SiteKeyConfigLoadTimeForGetBlob`
- `0x781a5`: `SiteKeyConfigLoadTimeForWriteBlob`
- `0x781cd`: `WriteFarBlobsExecutionTime`
- `0x7821d`: `WriteBlobsAwaitTime`
- `0x7826d`: `WriteBlobsFirstByteTime`
- `0x7830d`: `DeleteBlobScheduledCount`

## pseudocode

```c

```

## disassembly

```asm
0x77cf0  ldarg.0
0x77cf1  ldarg.1
0x77cf2  call     instance void Microsoft.SharePoint.Administration.Generated.BaseSlapiEvent::.ctor(class Microsoft.SharePoint.Administration.SPLogEventUsageEntry entry)
0x77cf7  ldarg.1
0x77cf8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77cfd  ldstr    aPartitionkey// "PartitionKey"
0x77d02  ldloca.s 0
0x77d04  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77d09  brfalse.s loc_77D17
0x77d0b  ldarg.0
0x77d0c  ldloc.0
0x77d0d  isinst   [mscorlib]System.String
0x77d12  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_PartitionKey(string value)
0x77d17  ldarg.1
0x77d18  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77d1d  ldstr    aGetblobselapse// "GetBlobsElapsedTime"
0x77d22  ldloca.s 0
0x77d24  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77d29  brfalse.s loc_77D3F
0x77d2b  ldloc.0
0x77d2c  isinst   [mscorlib]System.Int64
0x77d31  brfalse.s loc_77D3F
0x77d33  ldarg.0
0x77d34  ldloc.0
0x77d35  unbox.any [mscorlib]System.Int64
0x77d3a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsElapsedTime(int64 value)
0x77d3f  ldarg.1
0x77d40  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77d45  ldstr    aWriteblobselap// "WriteBlobsElapsedTime"
0x77d4a  ldloca.s 0
0x77d4c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77d51  brfalse.s loc_77D67
0x77d53  ldloc.0
0x77d54  isinst   [mscorlib]System.Int64
0x77d59  brfalse.s loc_77D67
0x77d5b  ldarg.0
0x77d5c  ldloc.0
0x77d5d  unbox.any [mscorlib]System.Int64
0x77d62  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsElapsedTime(int64 value)
0x77d67  ldarg.1
0x77d68  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77d6d  ldstr    aGetblobsexecut// "GetBlobsExecutionTime"
0x77d72  ldloca.s 0
0x77d74  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77d79  brfalse.s loc_77D8F
0x77d7b  ldloc.0
0x77d7c  isinst   [mscorlib]System.Int64
0x77d81  brfalse.s loc_77D8F
0x77d83  ldarg.0
0x77d84  ldloc.0
0x77d85  unbox.any [mscorlib]System.Int64
0x77d8a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsExecutionTime(int64 value)
0x77d8f  ldarg.1
0x77d90  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77d95  ldstr    aWriteblobsexec// "WriteBlobsExecutionTime"
0x77d9a  ldloca.s 0
0x77d9c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77da1  brfalse.s loc_77DB7
0x77da3  ldloc.0
0x77da4  isinst   [mscorlib]System.Int64
0x77da9  brfalse.s loc_77DB7
0x77dab  ldarg.0
0x77dac  ldloc.0
0x77dad  unbox.any [mscorlib]System.Int64
0x77db2  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsExecutionTime(int64 value)
0x77db7  ldarg.1
0x77db8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77dbd  ldstr    aGetblobscpucyc// "GetBlobsCPUCycles"
0x77dc2  ldloca.s 0
0x77dc4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77dc9  brfalse.s loc_77DDF
0x77dcb  ldloc.0
0x77dcc  isinst   [mscorlib]System.Int64
0x77dd1  brfalse.s loc_77DDF
0x77dd3  ldarg.0
0x77dd4  ldloc.0
0x77dd5  unbox.any [mscorlib]System.Int64
0x77dda  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsCPUCycles(int64 value)
0x77ddf  ldarg.1
0x77de0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77de5  ldstr    aWriteblobscpuc// "WriteBlobsCPUCycles"
0x77dea  ldloca.s 0
0x77dec  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77df1  brfalse.s loc_77E07
0x77df3  ldloc.0
0x77df4  isinst   [mscorlib]System.Int64
0x77df9  brfalse.s loc_77E07
0x77dfb  ldarg.0
0x77dfc  ldloc.0
0x77dfd  unbox.any [mscorlib]System.Int64
0x77e02  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsCPUCycles(int64 value)
0x77e07  ldarg.1
0x77e08  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77e0d  ldstr    aEncryptiontime// "EncryptionTime"
0x77e12  ldloca.s 0
0x77e14  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77e19  brfalse.s loc_77E2F
0x77e1b  ldloc.0
0x77e1c  isinst   [mscorlib]System.Int64
0x77e21  brfalse.s loc_77E2F
0x77e23  ldarg.0
0x77e24  ldloc.0
0x77e25  unbox.any [mscorlib]System.Int64
0x77e2a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_EncryptionTime(int64 value)
0x77e2f  ldarg.1
0x77e30  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77e35  ldstr    aEncryptioncycl// "EncryptionCycles"
0x77e3a  ldloca.s 0
0x77e3c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77e41  brfalse.s loc_77E57
0x77e43  ldloc.0
0x77e44  isinst   [mscorlib]System.Int64
0x77e49  brfalse.s loc_77E57
0x77e4b  ldarg.0
0x77e4c  ldloc.0
0x77e4d  unbox.any [mscorlib]System.Int64
0x77e52  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_EncryptionCycles(int64 value)
0x77e57  ldarg.1
0x77e58  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77e5d  ldstr    aDecryptiontime// "DecryptionTime"
0x77e62  ldloca.s 0
0x77e64  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77e69  brfalse.s loc_77E7F
0x77e6b  ldloc.0
0x77e6c  isinst   [mscorlib]System.Int64
0x77e71  brfalse.s loc_77E7F
0x77e73  ldarg.0
0x77e74  ldloc.0
0x77e75  unbox.any [mscorlib]System.Int64
0x77e7a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_DecryptionTime(int64 value)
0x77e7f  ldarg.1
0x77e80  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77e85  ldstr    aDecryptioncycl// "DecryptionCycles"
0x77e8a  ldloca.s 0
0x77e8c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77e91  brfalse.s loc_77EA7
0x77e93  ldloc.0
0x77e94  isinst   [mscorlib]System.Int64
0x77e99  brfalse.s loc_77EA7
0x77e9b  ldarg.0
0x77e9c  ldloc.0
0x77e9d  unbox.any [mscorlib]System.Int64
0x77ea2  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_DecryptionCycles(int64 value)
0x77ea7  ldarg.1
0x77ea8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77ead  ldstr    aGetblobscount// "GetBlobsCount"
0x77eb2  ldloca.s 0
0x77eb4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77eb9  brfalse.s loc_77ECF
0x77ebb  ldloc.0
0x77ebc  isinst   [mscorlib]System.Int32
0x77ec1  brfalse.s loc_77ECF
0x77ec3  ldarg.0
0x77ec4  ldloc.0
0x77ec5  unbox.any [mscorlib]System.Int32
0x77eca  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsCount(int32 value)
0x77ecf  ldarg.1
0x77ed0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77ed5  ldstr    aGetblobssucces// "GetBlobsSuccessCount"
0x77eda  ldloca.s 0
0x77edc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77ee1  brfalse.s loc_77EF7
0x77ee3  ldloc.0
0x77ee4  isinst   [mscorlib]System.Int32
0x77ee9  brfalse.s loc_77EF7
0x77eeb  ldarg.0
0x77eec  ldloc.0
0x77eed  unbox.any [mscorlib]System.Int32
0x77ef2  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsSuccessCount(int32 value)
0x77ef7  ldarg.1
0x77ef8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77efd  ldstr    aWriteblobscoun// "WriteBlobsCount"
0x77f02  ldloca.s 0
0x77f04  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77f09  brfalse.s loc_77F1F
0x77f0b  ldloc.0
0x77f0c  isinst   [mscorlib]System.Int32
0x77f11  brfalse.s loc_77F1F
0x77f13  ldarg.0
0x77f14  ldloc.0
0x77f15  unbox.any [mscorlib]System.Int32
0x77f1a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsCount(int32 value)
0x77f1f  ldarg.1
0x77f20  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77f25  ldstr    aWriteblobssucc// "WriteBlobsSuccessCount"
0x77f2a  ldloca.s 0
0x77f2c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77f31  brfalse.s loc_77F47
0x77f33  ldloc.0
0x77f34  isinst   [mscorlib]System.Int32
0x77f39  brfalse.s loc_77F47
0x77f3b  ldarg.0
0x77f3c  ldloc.0
0x77f3d  unbox.any [mscorlib]System.Int32
0x77f42  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsSuccessCount(int32 value)
0x77f47  ldarg.1
0x77f48  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77f4d  ldstr    aGetblobsbytess// "GetBlobsBytesSuccess"
0x77f52  ldloca.s 0
0x77f54  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77f59  brfalse.s loc_77F6F
0x77f5b  ldloc.0
0x77f5c  isinst   [mscorlib]System.Int64
0x77f61  brfalse.s loc_77F6F
0x77f63  ldarg.0
0x77f64  ldloc.0
0x77f65  unbox.any [mscorlib]System.Int64
0x77f6a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetBlobsBytesSuccess(int64 value)
0x77f6f  ldarg.1
0x77f70  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77f75  ldstr    aWriteblobsbyte// "WriteBlobsBytesSuccess"
0x77f7a  ldloca.s 0
0x77f7c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77f81  brfalse.s loc_77F97
0x77f83  ldloc.0
0x77f84  isinst   [mscorlib]System.Int64
0x77f89  brfalse.s loc_77F97
0x77f8b  ldarg.0
0x77f8c  ldloc.0
0x77f8d  unbox.any [mscorlib]System.Int64
0x77f92  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_WriteBlobsBytesSuccess(int64 value)
0x77f97  ldarg.1
0x77f98  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77f9d  ldstr    aTotalcancelled// "TotalCancelledReadCount"
0x77fa2  ldloca.s 0
0x77fa4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77fa9  brfalse.s loc_77FBF
0x77fab  ldloc.0
0x77fac  isinst   [mscorlib]System.Int64
0x77fb1  brfalse.s loc_77FBF
0x77fb3  ldarg.0
0x77fb4  ldloc.0
0x77fb5  unbox.any [mscorlib]System.Int64
0x77fba  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_TotalCancelledReadCount(int64 value)
0x77fbf  ldarg.1
0x77fc0  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77fc5  ldstr    aCancellednearr// "CancelledNearReadCount"
0x77fca  ldloca.s 0
0x77fcc  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77fd1  brfalse.s loc_77FE7
0x77fd3  ldloc.0
0x77fd4  isinst   [mscorlib]System.Int64
0x77fd9  brfalse.s loc_77FE7
0x77fdb  ldarg.0
0x77fdc  ldloc.0
0x77fdd  unbox.any [mscorlib]System.Int64
0x77fe2  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_CancelledNearReadCount(int64 value)
0x77fe7  ldarg.1
0x77fe8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x77fed  ldstr    aDeleteblobsela// "DeleteBlobsElapsedTime"
0x77ff2  ldloca.s 0
0x77ff4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x77ff9  brfalse.s loc_7800F
0x77ffb  ldloc.0
0x77ffc  isinst   [mscorlib]System.Int64
0x78001  brfalse.s loc_7800F
0x78003  ldarg.0
0x78004  ldloc.0
0x78005  unbox.any [mscorlib]System.Int64
0x7800a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_DeleteBlobsElapsedTime(int64 value)
0x7800f  ldarg.1
0x78010  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x78015  ldstr    aDeleteblobscou// "DeleteBlobsCount"
0x7801a  ldloca.s 0
0x7801c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x78021  brfalse.s loc_78037
0x78023  ldloc.0
0x78024  isinst   [mscorlib]System.Int64
0x78029  brfalse.s loc_78037
0x7802b  ldarg.0
0x7802c  ldloc.0
0x7802d  unbox.any [mscorlib]System.Int64
0x78032  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_DeleteBlobsCount(int64 value)
0x78037  ldarg.1
0x78038  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x7803d  ldstr    aDeleteblobssuc// "DeleteBlobsSuccessCount"
0x78042  ldloca.s 0
0x78044  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x78049  brfalse.s loc_7805F
0x7804b  ldloc.0
0x7804c  isinst   [mscorlib]System.Int64
0x78051  brfalse.s loc_7805F
0x78053  ldarg.0
0x78054  ldloc.0
0x78055  unbox.any [mscorlib]System.Int64
0x7805a  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_DeleteBlobsSuccessCount(int64 value)
0x7805f  ldarg.1
0x78060  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Administration.SPLogEventUsageEntry::get_CustomProperties()
0x78065  ldstr    aGetdeletedblob// "GetDeletedBlobsCount"
0x7806a  ldloca.s 0
0x7806c  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::TryGetValue(var<u1>, !!T0)
0x78071  brfalse.s loc_78087
0x78073  ldloc.0
0x78074  isinst   [mscorlib]System.Int64
0x78079  brfalse.s loc_78087
0x7807b  ldarg.0
0x7807c  ldloc.0
0x7807d  unbox.any [mscorlib]System.Int64
0x78082  call     instance void Microsoft.SharePoint.Administration.Generated.ABSConciseLog::set_GetDeletedBlobsCount(int64 value)
0x78087  ldarg.1
  ... truncated ...
```
