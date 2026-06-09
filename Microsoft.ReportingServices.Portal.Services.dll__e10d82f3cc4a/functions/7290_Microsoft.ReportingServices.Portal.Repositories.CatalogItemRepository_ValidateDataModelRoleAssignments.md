# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateDataModelRoleAssignments

- ea: `0x7290`
- end: `0x73b0`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::ValidateDataModelRoleAssignments`
- size: `288`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f010`

## callees

- `0x7290`
- `0x1f660`
- `0x1f6a0`

## pseudocode

```c

```

## disassembly

```asm
0x7290  ldarg.1
0x7291  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::GetEnumerator()
0x7296  stloc.0
0x7297  br       loc_7393
0x729c  newobj   instance void <>c__DisplayClass199_0::.ctor()
0x72a1  stloc.1
0x72a2  ldloc.1
0x72a3  ldloca.s 0
0x72a5  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::get_Current()
0x72aa  stfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x72af  ldarg.1
0x72b0  ldloc.1
0x72b1  ldftn    instance bool <>c__DisplayClass199_0::<ValidateDataModelRoleAssignments>b__0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment a)
0x72b7  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment, bool>::.ctor(object, native int)
0x72bc  call     T0x2B000064
0x72c1  ldc.i4.1
0x72c2  ble.s    loc_72D5
0x72c4  ldloc.1
0x72c5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x72ca  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x72cf  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidPolicyDefinitionException::.ctor(string)
0x72d4  throw
0x72d5  ldloc.1
0x72d6  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x72db  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x72e0  brfalse.s loc_72F4
0x72e2  ldloc.1
0x72e3  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x72e8  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x72ed  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Guid>::get_Count()
0x72f2  brtrue.s loc_7305
0x72f4  ldloc.1
0x72f5  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x72fa  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x72ff  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidPolicyDefinitionException::.ctor(string)
0x7304  throw
0x7305  ldloc.1
0x7306  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x730b  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x7310  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid>::GetEnumerator()
0x7315  stloc.2
0x7316  br.s     loc_737F
0x7318  newobj   instance void <>c__DisplayClass199_1::.ctor()
0x731d  stloc.3
0x731e  ldloc.3
0x731f  ldloc.2
0x7320  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Guid>::get_Current()
0x7325  stfld    valuetype [mscorlib]System.Guid <>c__DisplayClass199_1::roleId
0x732a  ldarg.2
0x732b  ldloc.3
0x732c  ldfld    valuetype [mscorlib]System.Guid <>c__DisplayClass199_1::roleId
0x7331  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, int64>::ContainsKey(var<u1>)
0x7336  brtrue.s loc_734F
0x7338  ldloc.3
0x7339  ldflda   valuetype [mscorlib]System.Guid <>c__DisplayClass199_1::roleId
0x733e  constrained. [mscorlib]System.Guid
0x7344  callvirt instance string [mscorlib]System.Object::ToString()
0x7349  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RoleNotFoundException::.ctor(string)
0x734e  throw
0x734f  ldloc.1
0x7350  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x7355  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [mscorlib]System.Guid> [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_DataModelRoles()
0x735a  ldloc.3
0x735b  ldftn    instance bool <>c__DisplayClass199_1::<ValidateDataModelRoleAssignments>b__1(valuetype [mscorlib]System.Guid r)
0x7361  newobj   instance void class [mscorlib]System.Func`2<valuetype [mscorlib]System.Guid, bool>::.ctor(object, native int)
0x7366  call     T0x2B000065
0x736b  ldc.i4.1
0x736c  ble.s    loc_737F
0x736e  ldloc.1
0x736f  ldfld    class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment <>c__DisplayClass199_0::dataRoleAssignment
0x7374  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment::get_GroupUserName()
0x7379  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InvalidPolicyDefinitionException::.ctor(string)
0x737e  throw
0x737f  ldloc.2
0x7380  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x7385  brtrue.s loc_7318
0x7387  leave.s  loc_7393
0x7389  ldloc.2
0x738a  brfalse.s loc_7392
0x738c  ldloc.2
0x738d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x7392  endfinally
0x7393  ldloca.s 0
0x7395  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>::MoveNext()
0x739a  brtrue   loc_729C
0x739f  leave.s  loc_73AF
0x73a1  ldloca.s 0
0x73a3  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelRoleAssignment>
0x73a9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x73ae  endfinally
0x73af  ret
```
