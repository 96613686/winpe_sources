# Microsoft.SharePoint.Upgrade.RemoveAllMyWorkInOncePlace::RemoveWorkManagementService

- ea: `0xa6b770`
- end: `0xa6bc0e`
- name: `Microsoft.SharePoint.Upgrade.RemoveAllMyWorkInOncePlace::RemoveWorkManagementService`
- size: `1182`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0xa6b510`

## callees

- `0x1c8480`
- `0x1c8540`
- `0x1c8e40`
- `0x1c8ef0`
- `0x2229e0`
- `0x2229f0`
- `0x29d1e0`
- `0x29d200`
- `0x3122a0`
- `0x312d10`
- `0x336990`
- `0xa45800`
- `0xa4f180`
- `0xa4f1f0`
- `0xa4f220`
- `0xa4f290`
- `0xa69b50`
- `0xa6b770`

## string_xrefs

- `0xa6b77b`: `Start removing AWIOP Work Management Service.`
- `0xa6b7ae`: `Microsoft.Office.Server.WorkManagement.WorkManagementServiceProxy`
- `0xa6b7c5`: `ServiceProxy found, removing. [FullName={0}][Id={1}]`
- `0xa6b829`: `RemoveWorkManagementService - done unprovisioning ServiceProxies. [serviceProxyMatchCount={0}]`
- `0xa6b87a`: `Microsoft.Office.Server.WorkManagement.WorkManagementService`
- `0xa6b894`: `Service found, removing. [FullName={0}][Id={1}]`
- `0xa6b901`: `Service Instance found, kicking off unprovision timer job.  [FullName={0}][Id={1}]`
- `0xa6b9cf`: `Finished waiting for service instances to unprovision.  [WaitHandle.Count={0}]`
- `0xa6ba1c`: `Delete of the SPServiceInstanceJobDefinition failed, but it is probably benign. [JobName={0}]`
- `0xa6ba61`: `Finished explicitly deleting SPServiceInstanceJobDefinition timer jobs.`
- `0xa6ba8f`: `Service Instance found, deleting.  [FullName={0}][Id={1}]`
- `0xa6bb05`: `Service Application found, removing. [FullName={0}][Id={1}]`
- `0xa6bb95`: `RemoveWorkManagementService - done unprovisioning Services, Service Applications and Service Instances. [webServiceMatchCount={0}][serviceAppMatchCount={1}][serviceInstanceMatchCount={2}]`
- `0xa6bbd3`: `Finished removing AWIOP Work Management Service.`

## pseudocode

```c

```

## disassembly

```asm
0xa6b770  ldarg.0
0xa6b771  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b776  ldc.i4   0x104F593
0xa6b77b  ldstr    aStartRemovingA_0// "Start removing AWIOP Work Management Se"...
0xa6b780  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::DebugTag(unsigned int32 tagID, string output)
0xa6b785  ldc.i4.0
0xa6b786  stloc.0
0xa6b787  ldarg.0
0xa6b788  call     instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Upgrade.SPFarmAction::get_Farm()
0xa6b78d  callvirt instance class Microsoft.SharePoint.Administration.SPServiceProxyCollection Microsoft.SharePoint.Administration.SPFarm::get_ServiceProxies()
0xa6b792  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceProxy>::GetEnumerator()
0xa6b797  stloc.s  0x10
0xa6b799  br.s     loc_A6B807
0xa6b79b  ldloc.s  0x10
0xa6b79d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServiceProxy>::get_Current()
0xa6b7a2  stloc.1
0xa6b7a3  ldloc.1
0xa6b7a4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6b7a9  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6b7ae  ldstr    aMicrosoftOffic_179// "Microsoft.Office.Server.WorkManagement."...
0xa6b7b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6b7b8  brfalse.s loc_A6B807
0xa6b7ba  ldarg.0
0xa6b7bb  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b7c0  ldc.i4   0x104F594
0xa6b7c5  ldstr    aServiceproxyFo// "ServiceProxy found, removing. [FullName"...
0xa6b7ca  ldc.i4.2
0xa6b7cb  newarr   [mscorlib]System.Object
0xa6b7d0  stloc.s  0x11
0xa6b7d2  ldloc.s  0x11
0xa6b7d4  ldc.i4.0
0xa6b7d5  ldloc.1
0xa6b7d6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6b7db  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6b7e0  stelem.ref
0xa6b7e1  ldloc.s  0x11
0xa6b7e3  ldc.i4.1
0xa6b7e4  ldloc.1
0xa6b7e5  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0xa6b7ea  box      [mscorlib]System.Guid
0xa6b7ef  stelem.ref
0xa6b7f0  ldloc.s  0x11
0xa6b7f2  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6b7f7  ldloc.0
0xa6b7f8  ldc.i4.1
0xa6b7f9  add
0xa6b7fa  stloc.0
0xa6b7fb  ldloc.1
0xa6b7fc  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Unprovision()
0xa6b801  ldloc.1
0xa6b802  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0xa6b807  ldloc.s  0x10
0xa6b809  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa6b80e  brtrue.s loc_A6B79B
0xa6b810  leave.s  loc_A6B81E
0xa6b812  ldloc.s  0x10
0xa6b814  brfalse.s loc_A6B81D
0xa6b816  ldloc.s  0x10
0xa6b818  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6b81d  endfinally
0xa6b81e  ldarg.0
0xa6b81f  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b824  ldc.i4   0x104F595
0xa6b829  ldstr    aRemoveworkmana// "RemoveWorkManagementService - done unpr"...
0xa6b82e  ldc.i4.1
0xa6b82f  newarr   [mscorlib]System.Object
0xa6b834  stloc.s  0x12
0xa6b836  ldloc.s  0x12
0xa6b838  ldc.i4.0
0xa6b839  ldloc.0
0xa6b83a  box      [mscorlib]System.Int32
0xa6b83f  stelem.ref
0xa6b840  ldloc.s  0x12
0xa6b842  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6b847  ldc.i4.0
0xa6b848  stloc.2
0xa6b849  ldc.i4.0
0xa6b84a  stloc.3
0xa6b84b  ldc.i4.0
0xa6b84c  stloc.s  4
0xa6b84e  ldarg.0
0xa6b84f  call     instance class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Upgrade.SPFarmAction::get_Farm()
0xa6b854  callvirt instance class Microsoft.SharePoint.Administration.SPServiceCollection Microsoft.SharePoint.Administration.SPFarm::get_Services()
0xa6b859  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPService>::GetEnumerator()
0xa6b85e  stloc.s  0x13
0xa6b860  br       loc_A6BB70
0xa6b865  ldloc.s  0x13
0xa6b867  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPService>::get_Current()
0xa6b86c  stloc.s  5
0xa6b86e  ldloc.s  5
0xa6b870  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6b875  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6b87a  ldstr    aMicrosoftOffic_180// "Microsoft.Office.Server.WorkManagement."...
0xa6b87f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa6b884  brfalse  loc_A6BB70
0xa6b889  ldarg.0
0xa6b88a  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b88f  ldc.i4   0x104F596
0xa6b894  ldstr    aServiceFoundRe// "Service found, removing. [FullName={0}]"...
0xa6b899  ldc.i4.2
0xa6b89a  newarr   [mscorlib]System.Object
0xa6b89f  stloc.s  0x14
0xa6b8a1  ldloc.s  0x14
0xa6b8a3  ldc.i4.0
0xa6b8a4  ldloc.s  5
0xa6b8a6  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6b8ab  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6b8b0  stelem.ref
0xa6b8b1  ldloc.s  0x14
0xa6b8b3  ldc.i4.1
0xa6b8b4  ldloc.s  5
0xa6b8b6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0xa6b8bb  box      [mscorlib]System.Guid
0xa6b8c0  stelem.ref
0xa6b8c1  ldloc.s  0x14
0xa6b8c3  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6b8c8  ldloc.2
0xa6b8c9  ldc.i4.1
0xa6b8ca  add
0xa6b8cb  stloc.2
0xa6b8cc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>::.ctor()
0xa6b8d1  stloc.s  6
0xa6b8d3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::.ctor()
0xa6b8d8  stloc.s  7
0xa6b8da  ldloc.s  5
0xa6b8dc  callvirt instance class Microsoft.SharePoint.Administration.SPServiceInstanceDependencyCollection Microsoft.SharePoint.Administration.SPService::get_Instances()
0xa6b8e1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::GetEnumerator()
0xa6b8e6  stloc.s  0x15
0xa6b8e8  br       loc_A6B975
0xa6b8ed  ldloc.s  0x15
0xa6b8ef  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::get_Current()
0xa6b8f4  stloc.s  8
0xa6b8f6  ldarg.0
0xa6b8f7  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b8fc  ldc.i4   0x104F597
0xa6b901  ldstr    aServiceInstanc_2// "Service Instance found, kicking off unp"...
0xa6b906  ldc.i4.2
0xa6b907  newarr   [mscorlib]System.Object
0xa6b90c  stloc.s  0x16
0xa6b90e  ldloc.s  0x16
0xa6b910  ldc.i4.0
0xa6b911  ldloc.s  8
0xa6b913  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6b918  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6b91d  stelem.ref
0xa6b91e  ldloc.s  0x16
0xa6b920  ldc.i4.1
0xa6b921  ldloc.s  8
0xa6b923  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0xa6b928  box      [mscorlib]System.Guid
0xa6b92d  stelem.ref
0xa6b92e  ldloc.s  0x16
0xa6b930  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6b935  ldloc.s  4
0xa6b937  ldc.i4.1
0xa6b938  add
0xa6b939  stloc.s  4
0xa6b93b  ldloc.s  8
0xa6b93d  ldc.i4.0
0xa6b93e  newobj   instance void Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition::.ctor(class Microsoft.SharePoint.Administration.SPServiceInstance serviceInstance, bool provision)
0xa6b943  stloc.s  9
0xa6b945  ldloc.s  9
0xa6b947  ldc.r8   5.0
0xa6b950  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xa6b955  ldnull
0xa6b956  ldnull
0xa6b957  call     class Microsoft.SharePoint.Administration.SPTimerJobAsyncResult Microsoft.SharePoint.Administration.SPTimerJobUtility::RunOneTimeJob(class Microsoft.SharePoint.Administration.SPJobDefinition jobDefinition, valuetype [mscorlib]System.TimeSpan timeout, class [mscorlib]System.AsyncCallback callback, object state)
0xa6b95c  stloc.s  0xA
0xa6b95e  ldloc.s  7
0xa6b960  ldloc.s  0xA
0xa6b962  callvirt instance class [mscorlib]System.Threading.WaitHandle Microsoft.SharePoint.Administration.SPTimerJobAsyncResult::get_AsyncWaitHandle()
0xa6b967  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::Add(var<u1>)
0xa6b96c  ldloc.s  6
0xa6b96e  ldloc.s  9
0xa6b970  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>::Add(var<u1>)
0xa6b975  ldloc.s  0x15
0xa6b977  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa6b97c  brtrue   loc_A6B8ED
0xa6b981  leave.s  loc_A6B98F
0xa6b983  ldloc.s  0x15
0xa6b985  brfalse.s loc_A6B98E
0xa6b987  ldloc.s  0x15
0xa6b989  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6b98e  endfinally
0xa6b98f  ldloc.s  7
0xa6b991  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::GetEnumerator()
0xa6b996  stloc.s  0x17
0xa6b998  br.s     loc_A6B9AB
0xa6b99a  ldloca.s 0x17
0xa6b99c  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.WaitHandle>::get_Current()
0xa6b9a1  stloc.s  0xB
0xa6b9a3  ldloc.s  0xB
0xa6b9a5  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0xa6b9aa  pop
0xa6b9ab  ldloca.s 0x17
0xa6b9ad  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.WaitHandle>::MoveNext()
0xa6b9b2  brtrue.s loc_A6B99A
0xa6b9b4  leave.s  loc_A6B9C4
0xa6b9b6  ldloca.s 0x17
0xa6b9b8  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Threading.WaitHandle>
0xa6b9be  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6b9c3  endfinally
0xa6b9c4  ldarg.0
0xa6b9c5  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6b9ca  ldc.i4   0x104F598
0xa6b9cf  ldstr    aFinishedWaitin_2// "Finished waiting for service instances "...
0xa6b9d4  ldc.i4.1
0xa6b9d5  newarr   [mscorlib]System.Object
0xa6b9da  stloc.s  0x18
0xa6b9dc  ldloc.s  0x18
0xa6b9de  ldc.i4.0
0xa6b9df  ldloc.s  7
0xa6b9e1  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Threading.WaitHandle>::get_Count()
0xa6b9e6  box      [mscorlib]System.Int32
0xa6b9eb  stelem.ref
0xa6b9ec  ldloc.s  0x18
0xa6b9ee  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6b9f3  ldloc.s  6
0xa6b9f5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>::GetEnumerator()
0xa6b9fa  stloc.s  0x19
0xa6b9fc  br.s     loc_A6BA3D
0xa6b9fe  ldloca.s 0x19
0xa6ba00  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>::get_Current()
0xa6ba05  stloc.s  0xC
0xa6ba07  ldloc.s  0xC
0xa6ba09  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0xa6ba0e  leave.s  loc_A6BA3D
0xa6ba10  pop
0xa6ba11  ldarg.0
0xa6ba12  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6ba17  ldc.i4   0x104F599
0xa6ba1c  ldstr    aDeleteOfTheSps// "Delete of the SPServiceInstanceJobDefin"...
0xa6ba21  ldc.i4.1
0xa6ba22  newarr   [mscorlib]System.Object
0xa6ba27  stloc.s  0x1A
0xa6ba29  ldloc.s  0x1A
0xa6ba2b  ldc.i4.0
0xa6ba2c  ldloc.s  0xC
0xa6ba2e  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0xa6ba33  stelem.ref
0xa6ba34  ldloc.s  0x1A
0xa6ba36  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6ba3b  leave.s  loc_A6BA3D
0xa6ba3d  ldloca.s 0x19
0xa6ba3f  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>::MoveNext()
0xa6ba44  brtrue.s loc_A6B9FE
0xa6ba46  leave.s  loc_A6BA56
0xa6ba48  ldloca.s 0x19
0xa6ba4a  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Administration.SPServiceInstanceJobDefinition>
0xa6ba50  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6ba55  endfinally
0xa6ba56  ldarg.0
0xa6ba57  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6ba5c  ldc.i4   0x104F59A
0xa6ba61  ldstr    aFinishedExplic// "Finished explicitly deleting SPServiceI"...
0xa6ba66  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa6ba6b  ldloc.s  5
0xa6ba6d  callvirt instance class Microsoft.SharePoint.Administration.SPServiceInstanceDependencyCollection Microsoft.SharePoint.Administration.SPService::get_Instances()
0xa6ba72  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::GetEnumerator()
0xa6ba77  stloc.s  0x1B
0xa6ba79  br.s     loc_A6BACA
0xa6ba7b  ldloc.s  0x1B
0xa6ba7d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Administration.SPServiceInstance>::get_Current()
0xa6ba82  stloc.s  0xD
0xa6ba84  ldarg.0
0xa6ba85  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa6ba8a  ldc.i4   0x104F59B
0xa6ba8f  ldstr    aServiceInstanc_3// "Service Instance found, deleting.  [Ful"...
0xa6ba94  ldc.i4.2
0xa6ba95  newarr   [mscorlib]System.Object
0xa6ba9a  stloc.s  0x1C
0xa6ba9c  ldloc.s  0x1C
0xa6ba9e  ldc.i4.0
0xa6ba9f  ldloc.s  0xD
0xa6baa1  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xa6baa6  callvirt instance string [mscorlib]System.Type::get_FullName()
0xa6baab  stelem.ref
0xa6baac  ldloc.s  0x1C
0xa6baae  ldc.i4.1
0xa6baaf  ldloc.s  0xD
0xa6bab1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0xa6bab6  box      [mscorlib]System.Guid
0xa6babb  stelem.ref
0xa6babc  ldloc.s  0x1C
0xa6babe  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string format, object[] args)
0xa6bac3  ldloc.s  0xD
0xa6bac5  callvirt instance void Microsoft.SharePoint.Administration.SPPersistedObject::Delete()
0xa6baca  ldloc.s  0x1B
0xa6bacc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xa6bad1  brtrue.s loc_A6BA7B
0xa6bad3  leave.s  loc_A6BAE1
0xa6bad5  ldloc.s  0x1B
0xa6bad7  brfalse.s loc_A6BAE0
0xa6bad9  ldloc.s  0x1B
0xa6badb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xa6bae0  endfinally
0xa6bae1  ldloc.s  5
0xa6bae3  callvirt instance class Microsoft.SharePoint.Administration.SPServiceApplicationCollection Microsoft.SharePoint.Administration.SPService::get_Applications()
0xa6bae8  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.Administration.SPServiceApplication>::GetEnumerator()
0xa6baed  stloc.s  0x1D
  ... truncated ...
```
