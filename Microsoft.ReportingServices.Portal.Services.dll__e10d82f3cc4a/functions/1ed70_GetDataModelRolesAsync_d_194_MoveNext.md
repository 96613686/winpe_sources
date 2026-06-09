# <GetDataModelRolesAsync>d__194::MoveNext

- ea: `0x1ed70`
- end: `0x1ee6a`
- name: `<GetDataModelRolesAsync>d__194::MoveNext`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1a00`
- `0x5ff0`
- `0x9e80`
- `0x1ed70`

## pseudocode

```c

```

## disassembly

```asm
0x1ed70  ldarg.0
0x1ed71  ldfld    int32 <GetDataModelRolesAsync>d__194::<>1__state
0x1ed76  stloc.0
0x1ed77  ldarg.0
0x1ed78  ldfld    class Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository <GetDataModelRolesAsync>d__194::<>4__this
0x1ed7d  stloc.1
0x1ed7e  ldloc.0
0x1ed7f  brfalse.s loc_1EDEC
0x1ed81  ldarg.0
0x1ed82  ldfld    class [mscorlib]System.Security.Principal.IPrincipal <GetDataModelRolesAsync>d__194::userPrincipal
0x1ed87  call     class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Portal.Services.ServicesUtil::CreateRsService(class [mscorlib]System.Security.Principal.IPrincipal principal)
0x1ed8c  stloc.3
0x1ed8d  ldloc.3
0x1ed8e  ldarg.0
0x1ed8f  ldfld    valuetype [mscorlib]System.Guid <GetDataModelRolesAsync>d__194::itemId
0x1ed94  call     string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetCatalogPathFromGuid(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, valuetype [mscorlib]System.Guid key)
0x1ed99  stloc.s  4
0x1ed9b  ldloc.1
0x1ed9c  ldloc.3
0x1ed9d  ldloc.s  4
0x1ed9f  call     instance class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetLibraryCatalogItem(class [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService rsService, string itemPath)
0x1eda4  ldc.i4.7
0x1eda5  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.CatalogItem::ThrowIfNoAccess(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x1edaa  ldloc.1
0x1edab  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x1edb0  ldarg.0
0x1edb1  ldfld    valuetype [mscorlib]System.Guid <GetDataModelRolesAsync>d__194::itemId
0x1edb6  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::GetDataModelRolesByItemAsync(valuetype [mscorlib]System.Guid)
0x1edbb  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<var<u1>> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>>::GetAwaiter()
0x1edc0  stloc.s  5
0x1edc2  ldloca.s 5
0x1edc4  call     instance bool valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>>::get_IsCompleted()
0x1edc9  brtrue.s loc_1EE09
0x1edcb  ldarg.0
0x1edcc  ldc.i4.0
0x1edcd  dup
0x1edce  stloc.0
0x1edcf  stfld    int32 <GetDataModelRolesAsync>d__194::<>1__state
0x1edd4  ldarg.0
0x1edd5  ldloc.s  5
0x1edd7  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>> <GetDataModelRolesAsync>d__194::<>u__1
0x1eddc  ldarg.0
0x1eddd  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRolesAsync>d__194::<>t__builder
0x1ede2  ldloca.s 5
0x1ede4  ldarg.0
0x1ede5  call     T0x2B000118
0x1edea  leave.s  loc_1EE69
0x1edec  ldarg.0
0x1eded  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>> <GetDataModelRolesAsync>d__194::<>u__1
0x1edf2  stloc.s  5
0x1edf4  ldarg.0
0x1edf5  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>> <GetDataModelRolesAsync>d__194::<>u__1
0x1edfa  initobj  valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>>
0x1ee00  ldarg.0
0x1ee01  ldc.i4.m1
0x1ee02  dup
0x1ee03  stloc.0
0x1ee04  stfld    int32 <GetDataModelRolesAsync>d__194::<>1__state
0x1ee09  ldloca.s 5
0x1ee0b  call     instance var<u1> valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>>::GetResult()
0x1ee10  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> <>c::<>9__194_0
0x1ee15  dup
0x1ee16  brtrue.s loc_1EE2F
0x1ee18  pop
0x1ee19  ldsfld   class <>c <>c::<>9
0x1ee1e  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole <>c::<GetDataModelRolesAsync>b__194_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity r)
0x1ee24  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::.ctor(object, native int)
0x1ee29  dup
0x1ee2a  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> <>c::<>9__194_0
0x1ee2f  call     T0x2B00005C
0x1ee34  call     T0x2B00005E
0x1ee39  stloc.2
0x1ee3a  leave.s  loc_1EE55
0x1ee3c  stloc.s  6
0x1ee3e  ldarg.0
0x1ee3f  ldc.i4.s 0xFE
0x1ee41  stfld    int32 <GetDataModelRolesAsync>d__194::<>1__state
0x1ee46  ldarg.0
0x1ee47  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRolesAsync>d__194::<>t__builder
0x1ee4c  ldloc.s  6
0x1ee4e  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>::SetException(class [mscorlib]System.Exception)
0x1ee53  leave.s  loc_1EE69
0x1ee55  ldarg.0
0x1ee56  ldc.i4.s 0xFE
0x1ee58  stfld    int32 <GetDataModelRolesAsync>d__194::<>1__state
0x1ee5d  ldarg.0
0x1ee5e  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>> <GetDataModelRolesAsync>d__194::<>t__builder
0x1ee63  ldloc.2
0x1ee64  call     instance void valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>>::SetResult(var<u1>)
0x1ee69  ret
```
