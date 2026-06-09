# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelRolesTrusted

- ea: `0x6f30`
- end: `0x70bc`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::SetDataModelRolesTrusted`
- size: `396`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x38d0`
- `0x1d7f0`

## callees

- `0x6f30`
- `0x73d0`
- `0x1cc50`
- `0x1ed30`

## pseudocode

```c

```

## disassembly

```asm
0x6f30  ldarg.2
0x6f31  stloc.0
0x6f32  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::.ctor()
0x6f37  stloc.1
0x6f38  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::.ctor()
0x6f3d  stloc.2
0x6f3e  ldarg.2
0x6f3f  brfalse  loc_70BB
0x6f44  ldarg.0
0x6f45  ldarg.1
0x6f46  call     instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>> Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetRoleIdMapping(valuetype [mscorlib]System.Guid itemId)
0x6f4b  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>>::get_Result()
0x6f50  stloc.3
0x6f51  ldarg.3
0x6f52  brfalse.s loc_6FBF
0x6f54  ldarg.0
0x6f55  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x6f5a  ldarg.1
0x6f5b  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::GetDataModelRolesByItemAsync(valuetype [mscorlib]System.Guid)
0x6f60  callvirt instance var<u1> class [mscorlib]System.Threading.Tasks.Task`1<class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity>>::get_Result()
0x6f65  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> <>c::<>9__192_0
0x6f6a  dup
0x6f6b  brtrue.s loc_6F84
0x6f6d  pop
0x6f6e  ldsfld   class <>c <>c::<>9
0x6f73  ldftn    instance class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole <>c::<SetDataModelRolesTrusted>b__192_0(class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity r)
0x6f79  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::.ctor(object, native int)
0x6f7e  dup
0x6f7f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.DataAccessObject.DataModelRoleEntity, class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole> <>c::<>9__192_0
0x6f84  call     T0x2B00005C
0x6f89  stloc.s  4
0x6f8b  ldarg.2
0x6f8c  ldloc.s  4
0x6f8e  newobj   instance void DataModelRoleComparer::.ctor()
0x6f93  call     T0x2B00005D
0x6f98  stloc.0
0x6f99  ldloc.s  4
0x6f9b  ldarg.2
0x6f9c  newobj   instance void DataModelRoleComparer::.ctor()
0x6fa1  call     T0x2B00005D
0x6fa6  call     T0x2B00005E
0x6fab  stloc.1
0x6fac  ldloc.s  4
0x6fae  ldarg.2
0x6faf  newobj   instance void DataModelRoleComparer::.ctor()
0x6fb4  call     T0x2B00005F
0x6fb9  call     T0x2B00005E
0x6fbe  stloc.2
0x6fbf  ldloc.0
0x6fc0  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::GetEnumerator()
0x6fc5  stloc.s  5
0x6fc7  br.s     loc_6FED
0x6fc9  ldloc.s  5
0x6fcb  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::get_Current()
0x6fd0  stloc.s  6
0x6fd2  ldarg.0
0x6fd3  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x6fd8  ldarg.1
0x6fd9  ldloc.s  6
0x6fdb  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole::get_ModelRoleId()
0x6fe0  ldloc.s  6
0x6fe2  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole::get_ModelRoleName()
0x6fe7  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::AddDataModelRoleAsync(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string)
0x6fec  pop
0x6fed  ldloc.s  5
0x6fef  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6ff4  brtrue.s loc_6FC9
0x6ff6  leave.s  loc_7004
0x6ff8  ldloc.s  5
0x6ffa  brfalse.s loc_7003
0x6ffc  ldloc.s  5
0x6ffe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7003  endfinally
0x7004  ldloc.1
0x7005  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::GetEnumerator()
0x700a  stloc.s  7
0x700c  br.s     loc_7030
0x700e  ldloca.s 7
0x7010  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::get_Current()
0x7015  stloc.s  8
0x7017  ldarg.0
0x7018  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x701d  ldloc.3
0x701e  ldloc.s  8
0x7020  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole::get_ModelRoleId()
0x7025  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>::get_Item(void)
0x702a  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::DeleteDataModelRoleByIdAsync(int64)
0x702f  pop
0x7030  ldloca.s 7
0x7032  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::MoveNext()
0x7037  brtrue.s loc_700E
0x7039  leave.s  loc_7049
0x703b  ldloca.s 7
0x703d  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>
0x7043  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7048  endfinally
0x7049  ldloc.2
0x704a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::GetEnumerator()
0x704f  stloc.s  7
0x7051  br.s     loc_70A2
0x7053  newobj   instance void <>c__DisplayClass192_0::.ctor()
0x7058  stloc.s  9
0x705a  ldloc.s  9
0x705c  ldloca.s 7
0x705e  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::get_Current()
0x7063  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole <>c__DisplayClass192_0::dataModelRoleToUpdate
0x7068  ldarg.2
0x7069  ldloc.s  9
0x706b  ldftn    instance bool <>c__DisplayClass192_0::<SetDataModelRolesTrusted>b__1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole r)
0x7071  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole, bool>::.ctor(object, native int)
0x7076  call     T0x2B000060
0x707b  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole::get_ModelRoleName()
0x7080  stloc.s  0xA
0x7082  ldarg.0
0x7083  ldfld    class [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::_dataModelRoleAccessor
0x7088  ldloc.3
0x7089  ldloc.s  9
0x708b  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole <>c__DisplayClass192_0::dataModelRoleToUpdate
0x7090  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole::get_ModelRoleId()
0x7095  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>::get_Item(void)
0x709a  ldloc.s  0xA
0x709c  callvirt instance class [mscorlib]System.Threading.Tasks.Task`1<int32> [Microsoft.ReportingServices.CatalogAccessInterfaces]Microsoft.ReportingServices.CatalogAccess.ICatalogDataModelRoleAccessor::UpdateDataModelRoleAsync(int64, string)
0x70a1  pop
0x70a2  ldloca.s 7
0x70a4  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>::MoveNext()
0x70a9  brtrue.s loc_7053
0x70ab  leave.s  loc_70BB
0x70ad  ldloca.s 7
0x70af  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRole>
0x70b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x70ba  endfinally
0x70bb  ret
```
