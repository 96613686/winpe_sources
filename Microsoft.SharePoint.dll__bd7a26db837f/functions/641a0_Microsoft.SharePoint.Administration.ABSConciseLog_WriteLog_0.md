# Microsoft.SharePoint.Administration.ABSConciseLog::WriteLog_0

- ea: `0x641a0`
- end: `0x64479`
- name: `Microsoft.SharePoint.Administration.ABSConciseLog::WriteLog_0`
- size: `729`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x37a3a0`

## string_xrefs

- `0x641c4`: `WriteBlobsElapsedTime`
- `0x641e6`: `WriteBlobsExecutionTime`
- `0x6420a`: `WriteBlobsCPUCycles`
- `0x64288`: `WriteBlobsCount`
- `0x6429a`: `WriteBlobsSuccessCount`
- `0x642be`: `WriteBlobsBytesSuccess`
- `0x642d0`: `TotalCancelledReadCount`
- `0x642e2`: `CancelledNearReadCount`
- `0x642f4`: `DeleteBlobsElapsedTime`
- `0x64306`: `DeleteBlobsCount`
- `0x64318`: `DeleteBlobsSuccessCount`
- `0x6432a`: `GetDeletedBlobsCount`
- `0x64360`: `WriteBlobGroupsCount`
- `0x64372`: `WriteBlobGroupsSuccessCount`
- `0x64396`: `ApplySiteKeyForWriteBlobExecutionTime`
- `0x643a8`: `SiteKeyConfigLoadTimeForGetBlob`
- `0x643ba`: `SiteKeyConfigLoadTimeForWriteBlob`
- `0x643cc`: `WriteFarBlobsExecutionTime`
- `0x643f0`: `WriteBlobsAwaitTime`
- `0x64414`: `WriteBlobsFirstByteTime`
- `0x6445c`: `DeleteBlobScheduledCount`

## pseudocode

```c

```

## disassembly

```asm
0x641a0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x641a5  stloc.0
0x641a6  ldloc.0
0x641a7  ldstr    aPartitionkey// "PartitionKey"
0x641ac  ldarg.0
0x641ad  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x641b2  ldloc.0
0x641b3  ldstr    aGetblobselapse// "GetBlobsElapsedTime"
0x641b8  ldarg.1
0x641b9  box      [mscorlib]System.Int64
0x641be  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x641c3  ldloc.0
0x641c4  ldstr    aWriteblobselap// "WriteBlobsElapsedTime"
0x641c9  ldarg.2
0x641ca  box      [mscorlib]System.Int64
0x641cf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x641d4  ldloc.0
0x641d5  ldstr    aGetblobsexecut// "GetBlobsExecutionTime"
0x641da  ldarg.3
0x641db  box      [mscorlib]System.Int64
0x641e0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x641e5  ldloc.0
0x641e6  ldstr    aWriteblobsexec// "WriteBlobsExecutionTime"
0x641eb  ldarg.s  4
0x641ed  box      [mscorlib]System.Int64
0x641f2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x641f7  ldloc.0
0x641f8  ldstr    aGetblobscpucyc// "GetBlobsCPUCycles"
0x641fd  ldarg.s  5
0x641ff  box      [mscorlib]System.Int64
0x64204  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64209  ldloc.0
0x6420a  ldstr    aWriteblobscpuc// "WriteBlobsCPUCycles"
0x6420f  ldarg.s  6
0x64211  box      [mscorlib]System.Int64
0x64216  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6421b  ldloc.0
0x6421c  ldstr    aEncryptiontime// "EncryptionTime"
0x64221  ldarg.s  7
0x64223  box      [mscorlib]System.Int64
0x64228  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6422d  ldloc.0
0x6422e  ldstr    aEncryptioncycl// "EncryptionCycles"
0x64233  ldarg.s  8
0x64235  box      [mscorlib]System.Int64
0x6423a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6423f  ldloc.0
0x64240  ldstr    aDecryptiontime// "DecryptionTime"
0x64245  ldarg.s  9
0x64247  box      [mscorlib]System.Int64
0x6424c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64251  ldloc.0
0x64252  ldstr    aDecryptioncycl// "DecryptionCycles"
0x64257  ldarg.s  0xA
0x64259  box      [mscorlib]System.Int64
0x6425e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64263  ldloc.0
0x64264  ldstr    aGetblobscount// "GetBlobsCount"
0x64269  ldarg.s  0xB
0x6426b  box      [mscorlib]System.Int32
0x64270  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64275  ldloc.0
0x64276  ldstr    aGetblobssucces// "GetBlobsSuccessCount"
0x6427b  ldarg.s  0xC
0x6427d  box      [mscorlib]System.Int32
0x64282  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64287  ldloc.0
0x64288  ldstr    aWriteblobscoun// "WriteBlobsCount"
0x6428d  ldarg.s  0xD
0x6428f  box      [mscorlib]System.Int32
0x64294  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64299  ldloc.0
0x6429a  ldstr    aWriteblobssucc// "WriteBlobsSuccessCount"
0x6429f  ldarg.s  0xE
0x642a1  box      [mscorlib]System.Int32
0x642a6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x642ab  ldloc.0
0x642ac  ldstr    aGetblobsbytess// "GetBlobsBytesSuccess"
0x642b1  ldarg.s  0xF
0x642b3  box      [mscorlib]System.Int64
0x642b8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x642bd  ldloc.0
0x642be  ldstr    aWriteblobsbyte// "WriteBlobsBytesSuccess"
0x642c3  ldarg.s  0x10
0x642c5  box      [mscorlib]System.Int64
0x642ca  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x642cf  ldloc.0
0x642d0  ldstr    aTotalcancelled// "TotalCancelledReadCount"
0x642d5  ldarg.s  0x11
0x642d7  box      [mscorlib]System.Int64
0x642dc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x642e1  ldloc.0
0x642e2  ldstr    aCancellednearr// "CancelledNearReadCount"
0x642e7  ldarg.s  0x12
0x642e9  box      [mscorlib]System.Int64
0x642ee  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x642f3  ldloc.0
0x642f4  ldstr    aDeleteblobsela// "DeleteBlobsElapsedTime"
0x642f9  ldarg.s  0x13
0x642fb  box      [mscorlib]System.Int64
0x64300  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64305  ldloc.0
0x64306  ldstr    aDeleteblobscou// "DeleteBlobsCount"
0x6430b  ldarg.s  0x14
0x6430d  box      [mscorlib]System.Int64
0x64312  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64317  ldloc.0
0x64318  ldstr    aDeleteblobssuc// "DeleteBlobsSuccessCount"
0x6431d  ldarg.s  0x15
0x6431f  box      [mscorlib]System.Int64
0x64324  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64329  ldloc.0
0x6432a  ldstr    aGetdeletedblob// "GetDeletedBlobsCount"
0x6432f  ldarg.s  0x16
0x64331  box      [mscorlib]System.Int64
0x64336  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6433b  ldloc.0
0x6433c  ldstr    aGetblobgroupsc// "GetBlobGroupsCount"
0x64341  ldarg.s  0x17
0x64343  box      [mscorlib]System.Int32
0x64348  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6434d  ldloc.0
0x6434e  ldstr    aGetblobgroupss// "GetBlobGroupsSuccessCount"
0x64353  ldarg.s  0x18
0x64355  box      [mscorlib]System.Int32
0x6435a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6435f  ldloc.0
0x64360  ldstr    aWriteblobgroup// "WriteBlobGroupsCount"
0x64365  ldarg.s  0x19
0x64367  box      [mscorlib]System.Int32
0x6436c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64371  ldloc.0
0x64372  ldstr    aWriteblobgroup_0// "WriteBlobGroupsSuccessCount"
0x64377  ldarg.s  0x1A
0x64379  box      [mscorlib]System.Int32
0x6437e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64383  ldloc.0
0x64384  ldstr    aApplysitekeyfo// "ApplySiteKeyForGetBlobExecutionTime"
0x64389  ldarg.s  0x1B
0x6438b  box      [mscorlib]System.Int64
0x64390  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64395  ldloc.0
0x64396  ldstr    aApplysitekeyfo_0// "ApplySiteKeyForWriteBlobExecutionTime"
0x6439b  ldarg.s  0x1C
0x6439d  box      [mscorlib]System.Int64
0x643a2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x643a7  ldloc.0
0x643a8  ldstr    aSitekeyconfigl// "SiteKeyConfigLoadTimeForGetBlob"
0x643ad  ldarg.s  0x1D
0x643af  box      [mscorlib]System.Int64
0x643b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x643b9  ldloc.0
0x643ba  ldstr    aSitekeyconfigl_0// "SiteKeyConfigLoadTimeForWriteBlob"
0x643bf  ldarg.s  0x1E
0x643c1  box      [mscorlib]System.Int64
0x643c6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x643cb  ldloc.0
0x643cc  ldstr    aWritefarblobse// "WriteFarBlobsExecutionTime"
0x643d1  ldarg.s  0x1F
0x643d3  box      [mscorlib]System.Int64
0x643d8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x643dd  ldloc.0
0x643de  ldstr    aGetblobsawaitt// "GetBlobsAwaitTime"
0x643e3  ldarg.s  0x20
0x643e5  box      [mscorlib]System.Int64
0x643ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x643ef  ldloc.0
0x643f0  ldstr    aWriteblobsawai// "WriteBlobsAwaitTime"
0x643f5  ldarg.s  0x21
0x643f7  box      [mscorlib]System.Int64
0x643fc  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64401  ldloc.0
0x64402  ldstr    aGetblobsfirstb// "GetBlobsFirstByteTime"
0x64407  ldarg.s  0x22
0x64409  box      [mscorlib]System.Int64
0x6440e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64413  ldloc.0
0x64414  ldstr    aWriteblobsfirs// "WriteBlobsFirstByteTime"
0x64419  ldarg.s  0x23
0x6441b  box      [mscorlib]System.Int64
0x64420  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64425  ldloc.0
0x64426  ldstr    aValidateblobgr// "ValidateBlobGroupsCount"
0x6442b  ldarg.s  0x24
0x6442d  box      [mscorlib]System.Int32
0x64432  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64437  ldloc.0
0x64438  ldstr    aValidateblobgr_0// "ValidateBlobGroupsSuccessCount"
0x6443d  ldarg.s  0x25
0x6443f  box      [mscorlib]System.Int32
0x64444  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x64449  ldloc.0
0x6444a  ldstr    aValidateblobse// "ValidateBlobsElapsedTime"
0x6444f  ldarg.s  0x26
0x64451  box      [mscorlib]System.Int64
0x64456  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6445b  ldloc.0
0x6445c  ldstr    aDeleteblobsche// "DeleteBlobScheduledCount"
0x64461  ldarg.s  0x27
0x64463  box      [mscorlib]System.Int64
0x64468  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x6446d  ldstr    aAbsconciselog// "ABSConciseLog"
0x64472  ldloc.0
0x64473  call     void Microsoft.SharePoint.Administration.SPSimpleUsageEventLog::WriteLog(string eventName, class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> customProperties)
0x64478  ret
```
