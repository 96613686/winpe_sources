# <GetDataModelRoleAssignmentsAsync>d__195::MoveNext

- ea: `0x1ee90`
- end: `0x1ef9f`
- name: `<GetDataModelRoleAssignmentsAsync>d__195::MoveNext`
- size: `271`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1a00`
- `0x5ff0`
- `0x71c0`
- `0x9e80`
- `0x1ee90`

## pseudocode

```c

```

## disassembly

```asm
0x1ee90  ldarg.0
0x1ee91  ldfld    int32 <GetDataModelRoleAssignmentsAsync>d__195::<>1__state
0x1ee96  stloc.0
0x1ee97  ldarg.0
0x1ee98  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <GetDataModelRoleAssignmentsAsync>d__195::<>4__this
0x1ee9d  stloc.1
0x1ee9e  ldloc.0
0x1ee9f  brfalse.s loc_1EF0F
0x1eea1  ldarg.0
0x1eea2  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <GetDataModelRoleAssignmentsAsync>d__195::userPrincipal
0x1eea7  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1eeac  stloc.3
0x1eead  ldloc.3
0x1eeae  ldarg.0
0x1eeaf  ldfld    valuetype [mscorlib]System.Guid <GetDataModelRoleAssignmentsAsync>d__195::itemId
0x1eeb4  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x1eeb9  stloc.s  4
0x1eebb  ldloc.1
0x1eebc  ldloc.3
0x1eebd  ldloc.s  4
0x1eebf  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x1eec4  ldc.i4.7
0x1eec5  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x1eeca  ldloc.1
0x1eecb  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1eed0  ldarg.0
0x1eed1  ldfld    valuetype [mscorlib]System.Guid <GetDataModelRoleAssignmentsAsync>d__195::itemId
0x1eed6  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::GetDataModelRoleAssignmentsByItemAsync(valuetype [mscorlib]System.Guid)
0x1eedb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::GetAwaiter()
0x1eee0  stloc.s  6
0x1eee2  ldloca.s 6
0x1eee4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::get_IsCompleted()
0x1eee9  brtrue.s loc_1EF2C
0x1eeeb  ldarg.0
0x1eeec  ldc.i4.0
0x1eeed  dup
0x1eeee  stloc.0
0x1eeef  stfld    int32 <GetDataModelRoleAssignmentsAsync>d__195::<>1__state
0x1eef4  ldarg.0
0x1eef5  ldloc.s  6
0x1eef7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <GetDataModelRoleAssignmentsAsync>d__195::<>u__1
0x1eefc  ldarg.0
0x1eefd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignmentsAsync>d__195::<>t__builder
0x1ef02  ldloca.s 6
0x1ef04  ldarg.0
0x1ef05  call     T0x2B000119
0x1ef0a  leave    loc_1EF9E
0x1ef0f  ldarg.0
0x1ef10  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <GetDataModelRoleAssignmentsAsync>d__195::<>u__1
0x1ef15  stloc.s  6
0x1ef17  ldarg.0
0x1ef18  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>> <GetDataModelRoleAssignmentsAsync>d__195::<>u__1
0x1ef1d  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>
0x1ef23  ldarg.0
0x1ef24  ldc.i4.m1
0x1ef25  dup
0x1ef26  stloc.0
0x1ef27  stfld    int32 <GetDataModelRoleAssignmentsAsync>d__195::<>1__state
0x1ef2c  ldloca.s 6
0x1ef2e  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity>>::GetResult()
0x1ef33  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <>c::<>9__195_0
0x1ef38  dup
0x1ef39  brtrue.s loc_1EF52
0x1ef3b  pop
0x1ef3c  ldsfld   class <>c <>c::<>9
0x1ef41  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c::<GetDataModelRoleAssignmentsAsync>b__195_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity r)
0x1ef47  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::.ctor(object, native int)
0x1ef4c  dup
0x1ef4d  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleAssignmentEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> <>c::<>9__195_0
0x1ef52  call     T0x2B00011A
0x1ef57  call     T0x2B00011B
0x1ef5c  stloc.s  5
0x1ef5e  ldloc.1
0x1ef5f  ldloc.s  5
0x1ef61  ldarg.0
0x1ef62  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <GetDataModelRoleAssignmentsAsync>d__195::userPrincipal
0x1ef67  call     instance void Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateAndNormalizeUsers(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment> dataModelRoleAssignments, class [mscorlib]System.Security.Principal.IPrincipal userPrincipal)
0x1ef6c  ldloc.s  5
0x1ef6e  stloc.2
0x1ef6f  leave.s  loc_1EF8A
0x1ef71  stloc.s  7
0x1ef73  ldarg.0
0x1ef74  ldc.i4.s 0xFE
0x1ef76  stfld    int32 <GetDataModelRoleAssignmentsAsync>d__195::<>1__state
0x1ef7b  ldarg.0
0x1ef7c  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignmentsAsync>d__195::<>t__builder
0x1ef81  ldloc.s  7
0x1ef83  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>::SetException(class [mscorlib]System.Exception)
0x1ef88  leave.s  loc_1EF9E
0x1ef8a  ldarg.0
0x1ef8b  ldc.i4.s 0xFE
0x1ef8d  stfld    int32 <GetDataModelRoleAssignmentsAsync>d__195::<>1__state
0x1ef92  ldarg.0
0x1ef93  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>> <GetDataModelRoleAssignmentsAsync>d__195::<>t__builder
0x1ef98  ldloc.2
0x1ef99  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>>::SetResult(var<u1>)
0x1ef9e  ret
```
