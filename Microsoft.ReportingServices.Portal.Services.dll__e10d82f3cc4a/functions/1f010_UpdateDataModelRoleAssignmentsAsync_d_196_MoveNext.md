# <UpdateDataModelRoleAssignmentsAsync>d__196::MoveNext

- ea: `0x1f010`
- end: `0x1f63f`
- name: `<UpdateDataModelRoleAssignmentsAsync>d__196::MoveNext`
- size: `1583`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x1a00`
- `0x5ff0`
- `0x71c0`
- `0x7240`
- `0x7290`
- `0x73b0`
- `0x73d0`
- `0x9e80`
- `0x1ccb0`
- `0x1efc0`
- `0x1f010`

## pseudocode

```c

```

## disassembly

```asm
0x1f010  ldarg.0
0x1f011  ldfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f016  stloc.0
0x1f017  ldarg.0
0x1f018  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <UpdateDataModelRoleAssignmentsAsync>d__196::<>4__this
0x1f01d  stloc.1
0x1f01e  ldloc.0
0x1f01f  switch   loc_1F0BC, loc_1F141, loc_1F1C7, loc_1F1C7, loc_1F4B7
0x1f038  ldarg.0
0x1f039  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelRoleAssignmentsAsync>d__196::userPrincipal
0x1f03e  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1f043  stloc.2
0x1f044  ldloc.2
0x1f045  ldarg.0
0x1f046  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::itemId
0x1f04b  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x1f050  stloc.3
0x1f051  ldloc.1
0x1f052  ldloc.2
0x1f053  ldloc.3
0x1f054  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x1f059  ldc.i4.8
0x1f05a  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x1f05f  ldarg.0
0x1f060  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::dataModelRoleAssignments
0x1f065  brfalse  loc_1F610
0x1f06a  ldloc.1
0x1f06b  ldarg.0
0x1f06c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::dataModelRoleAssignments
0x1f071  ldarg.0
0x1f072  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelRoleAssignmentsAsync>d__196::userPrincipal
0x1f077  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateAndNormalizeUsers(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> dataModelRoleAssignments, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal)
0x1f07c  ldloc.1
0x1f07d  ldarg.0
0x1f07e  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::itemId
0x1f083  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetRoleIdMapping(valuetype [mscorlib]System.Guid itemId)
0x1f088  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>>::GetAwaiter()
0x1f08d  stloc.s  6
0x1f08f  ldloca.s 6
0x1f091  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>>::get_IsCompleted()
0x1f096  brtrue.s loc_1F0D9
0x1f098  ldarg.0
0x1f099  ldc.i4.0
0x1f09a  dup
0x1f09b  stloc.0
0x1f09c  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f0a1  ldarg.0
0x1f0a2  ldloc.s  6
0x1f0a4  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__1
0x1f0a9  ldarg.0
0x1f0aa  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelRoleAssignmentsAsync>d__196::<>t__builder
0x1f0af  ldloca.s 6
0x1f0b1  ldarg.0
0x1f0b2  call     T0x2B00011C
0x1f0b7  leave    loc_1F63E
0x1f0bc  ldarg.0
0x1f0bd  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__1
0x1f0c2  stloc.s  6
0x1f0c4  ldarg.0
0x1f0c5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__1
0x1f0ca  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>>
0x1f0d0  ldarg.0
0x1f0d1  ldc.i4.m1
0x1f0d2  dup
0x1f0d3  stloc.0
0x1f0d4  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f0d9  ldloca.s 6
0x1f0db  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>>::GetResult()
0x1f0e0  stloc.s  5
0x1f0e2  ldarg.0
0x1f0e3  ldloc.s  5
0x1f0e5  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64> <UpdateDataModelRoleAssignmentsAsync>d__196::<roleIdMapping>5__2
0x1f0ea  ldloc.1
0x1f0eb  ldarg.0
0x1f0ec  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::dataModelRoleAssignments
0x1f0f1  ldarg.0
0x1f0f2  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64> <UpdateDataModelRoleAssignmentsAsync>d__196::<roleIdMapping>5__2
0x1f0f7  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateDataModelRoleAssignments(class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> dataModelRoleAssignments, class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64> roleIdMapping)
0x1f0fc  ldloc.1
0x1f0fd  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1f102  ldarg.0
0x1f103  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::itemId
0x1f108  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::GetDataModelRoleAssignmentsByItemAsync(valuetype [mscorlib]System.Guid)
0x1f10d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::GetAwaiter()
0x1f112  stloc.s  8
0x1f114  ldloca.s 8
0x1f116  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::get_IsCompleted()
0x1f11b  brtrue.s loc_1F15E
0x1f11d  ldarg.0
0x1f11e  ldc.i4.1
0x1f11f  dup
0x1f120  stloc.0
0x1f121  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f126  ldarg.0
0x1f127  ldloc.s  8
0x1f129  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__2
0x1f12e  ldarg.0
0x1f12f  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelRoleAssignmentsAsync>d__196::<>t__builder
0x1f134  ldloca.s 8
0x1f136  ldarg.0
0x1f137  call     T0x2B00011D
0x1f13c  leave    loc_1F63E
0x1f141  ldarg.0
0x1f142  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__2
0x1f147  stloc.s  8
0x1f149  ldarg.0
0x1f14a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__2
0x1f14f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>
0x1f155  ldarg.0
0x1f156  ldc.i4.m1
0x1f157  dup
0x1f158  stloc.0
0x1f159  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f15e  ldloca.s 8
0x1f160  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::GetResult()
0x1f165  stloc.s  7
0x1f167  ldarg.0
0x1f168  ldloc.s  7
0x1f16a  stfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity> <UpdateDataModelRoleAssignmentsAsync>d__196::<existingDataModelRoleAssignmentEntities>5__3
0x1f16f  ldarg.0
0x1f170  ldarg.0
0x1f171  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity> <UpdateDataModelRoleAssignmentsAsync>d__196::<existingDataModelRoleAssignmentEntities>5__3
0x1f176  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <>c::<>9__196_0
0x1f17b  dup
0x1f17c  brtrue.s loc_1F195
0x1f17e  pop
0x1f17f  ldsfld   class <>c <>c::<>9
0x1f184  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c::<UpdateDataModelRoleAssignmentsAsync>b__196_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity r)
0x1f18a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::.ctor(object, native int)
0x1f18f  dup
0x1f190  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <>c::<>9__196_0
0x1f195  call     T0x2B00011A
0x1f19a  call     T0x2B00011B
0x1f19f  stfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::<existingDataModelRoleAssignments>5__4
0x1f1a4  ldloc.1
0x1f1a5  ldarg.0
0x1f1a6  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::<existingDataModelRoleAssignments>5__4
0x1f1ab  ldarg.0
0x1f1ac  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelRoleAssignmentsAsync>d__196::userPrincipal
0x1f1b1  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateAndNormalizeUsers(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> dataModelRoleAssignments, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal)
0x1f1b6  ldarg.0
0x1f1b7  ldarg.0
0x1f1b8  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::dataModelRoleAssignments
0x1f1bd  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::GetEnumerator()
0x1f1c2  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap4
0x1f1c7  nop
0x1f1c8  ldloc.0
0x1f1c9  ldc.i4.2
0x1f1ca  beq      loc_1F298
0x1f1cf  ldloc.0
0x1f1d0  ldc.i4.3
0x1f1d1  beq      loc_1F368
0x1f1d6  br       loc_1F43A
0x1f1db  newobj   instance void <>c__DisplayClass196_0::.ctor()
0x1f1e0  stloc.s  9
0x1f1e2  ldloc.s  9
0x1f1e4  ldarg.0
0x1f1e5  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap4
0x1f1ea  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::get_Current()
0x1f1ef  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass196_0::dataRoleAssignment
0x1f1f4  ldarg.0
0x1f1f5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <UpdateDataModelRoleAssignmentsAsync>d__196::<existingDataModelRoleAssignments>5__4
0x1f1fa  ldloc.s  9
0x1f1fc  ldftn    instance bool <>c__DisplayClass196_0::<UpdateDataModelRoleAssignmentsAsync>b__1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment a)
0x1f202  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment, bool>::.ctor(object, native int)
0x1f207  call     T0x2B00011E
0x1f20c  stloc.s  0xA
0x1f20e  ldloc.s  0xA
0x1f210  brtrue.s loc_1F21D
0x1f212  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Guid>::.ctor()
0x1f217  stloc.s  0xD
0x1f219  ldloc.s  0xD
0x1f21b  br.s     loc_1F224
0x1f21d  ldloc.s  0xA
0x1f21f  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x1f224  stloc.s  0xB
0x1f226  ldloc.s  9
0x1f228  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass196_0::dataRoleAssignment
0x1f22d  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x1f232  ldloc.s  0xB
0x1f234  call     T0x2B00011F
0x1f239  stloc.s  0xC
0x1f23b  ldarg.0
0x1f23c  ldloc.s  0xB
0x1f23e  ldloc.s  9
0x1f240  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass196_0::dataRoleAssignment
0x1f245  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x1f24a  call     T0x2B00011F
0x1f24f  stfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<rolesToDelete>5__6
0x1f254  ldloc.s  0xC
0x1f256  call     T0x2B000120
0x1f25b  brtrue.s loc_1F26D
0x1f25d  ldarg.0
0x1f25e  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<rolesToDelete>5__6
0x1f263  call     T0x2B000120
0x1f268  brfalse  loc_1F433
0x1f26d  ldarg.0
0x1f26e  ldloc.1
0x1f26f  ldarg.0
0x1f270  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <UpdateDataModelRoleAssignmentsAsync>d__196::userPrincipal
0x1f275  ldloc.s  9
0x1f277  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass196_0::dataRoleAssignment
0x1f27c  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x1f281  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetOrCreateUserId(class [mscorlib]System.Security.Principal.IPrincipal userPrincipal, string groupUserName)
0x1f286  stfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::<userId>5__7
0x1f28b  ldarg.0
0x1f28c  ldloc.s  0xC
0x1f28e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1f293  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f298  nop
0x1f299  ldloc.0
0x1f29a  ldc.i4.2
0x1f29b  beq.s    loc_1F301
0x1f29d  br       loc_1F326
0x1f2a2  ldarg.0
0x1f2a3  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f2a8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1f2ad  stloc.s  0xE
0x1f2af  ldloc.1
0x1f2b0  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1f2b5  ldarg.0
0x1f2b6  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::<userId>5__7
0x1f2bb  ldarg.0
0x1f2bc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64> <UpdateDataModelRoleAssignmentsAsync>d__196::<roleIdMapping>5__2
0x1f2c1  ldloc.s  0xE
0x1f2c3  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>::get_Item(void)
0x1f2c8  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::AddDataModelRoleAssignmentAsync(valuetype [mscorlib]System.Guid, int64)
0x1f2cd  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<int32>::GetAwaiter()
0x1f2d2  stloc.s  0xF
0x1f2d4  ldloca.s 0xF
0x1f2d6  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::get_IsCompleted()
0x1f2db  brtrue.s loc_1F31E
0x1f2dd  ldarg.0
0x1f2de  ldc.i4.2
0x1f2df  dup
0x1f2e0  stloc.0
0x1f2e1  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f2e6  ldarg.0
0x1f2e7  ldloc.s  0xF
0x1f2e9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__3
0x1f2ee  ldarg.0
0x1f2ef  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <UpdateDataModelRoleAssignmentsAsync>d__196::<>t__builder
0x1f2f4  ldloca.s 0xF
0x1f2f6  ldarg.0
0x1f2f7  call     T0x2B000121
0x1f2fc  leave    loc_1F63E
0x1f301  ldarg.0
0x1f302  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__3
0x1f307  stloc.s  0xF
0x1f309  ldarg.0
0x1f30a  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32> <UpdateDataModelRoleAssignmentsAsync>d__196::<>u__3
0x1f30f  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>
0x1f315  ldarg.0
0x1f316  ldc.i4.m1
0x1f317  dup
0x1f318  stloc.0
0x1f319  stfld    int32 <UpdateDataModelRoleAssignmentsAsync>d__196::<>1__state
0x1f31e  ldloca.s 0xF
0x1f320  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<int32>::GetResult()
0x1f325  pop
0x1f326  ldarg.0
0x1f327  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f32c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1f331  brtrue   loc_1F2A2
0x1f336  leave.s  loc_1F350
0x1f338  ldloc.0
0x1f339  ldc.i4.0
0x1f33a  bge.s    loc_1F34F
0x1f33c  ldarg.0
0x1f33d  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f342  brfalse.s loc_1F34F
0x1f344  ldarg.0
0x1f345  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f34a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f34f  endfinally
0x1f350  ldarg.0
0x1f351  ldnull
0x1f352  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f357  ldarg.0
0x1f358  ldarg.0
0x1f359  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<rolesToDelete>5__6
0x1f35e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x1f363  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f368  nop
0x1f369  ldloc.0
0x1f36a  ldc.i4.3
0x1f36b  beq.s    loc_1F3D1
0x1f36d  br       loc_1F3F6
0x1f372  ldarg.0
0x1f373  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid> <UpdateDataModelRoleAssignmentsAsync>d__196::<>7__wrap7
0x1f378  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x1f37d  stloc.s  0x10
0x1f37f  ldloc.1
0x1f380  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1f385  ldarg.0
0x1f386  ldfld    valuetype [mscorlib]System.Guid <UpdateDataModelRoleAssignmentsAsync>d__196::<userId>5__7
0x1f38b  ldarg.0
0x1f38c  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64> <UpdateDataModelRoleAssignmentsAsync>d__196::<roleIdMapping>5__2
0x1f391  ldloc.s  0x10
0x1f393  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>::get_Item(void)
  ... truncated ...
```
