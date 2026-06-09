# Microsoft.ReportingServices.Library.Security::InnerRoleToOperations

- ea: `0x4b490`
- end: `0x4b77b`
- name: `Microsoft.ReportingServices.Library.Security::InnerRoleToOperations`
- size: `747`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x4b3a0`

## callees

- `0x4b490`
- `0x8b340`
- `0x8b350`
- `0x8b360`

## string_xrefs

- `0x4b4c7`: `Wrong number of tasks found for role`
- `0x4b55d`: `Wrong number of tasks found for role`
- `0x4b6e4`: `Wrong number of tasks found for role`
- `0x4b770`: `Unknown security scope`

## pseudocode

```c

```

## disassembly

```asm
0x4b490  ldarg.1
0x4b491  callvirt instance string SecurityRole::get_TaskMask()
0x4b496  stloc.0
0x4b497  ldarg.1
0x4b498  callvirt instance valuetype SecurityScope SecurityRole::get_Scope()
0x4b49d  stloc.1
0x4b49e  ldloc.1
0x4b49f  switch   loc_4B54B, loc_4B4B5, loc_4B6D2
0x4b4b0  br       loc_4B770
0x4b4b5  ldloc.0
0x4b4b6  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b4bb  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_CatalogTaskMap
0x4b4c0  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x4b4c5  beq.s    loc_4B4DD
0x4b4c7  ldstr    aWrongNumberOfT// "Wrong number of tasks found for role"
0x4b4cc  ldarg.1
0x4b4cd  callvirt instance string SecurityRole::get_RoleName()
0x4b4d2  call     string [mscorlib]System.String::Concat(string, string)
0x4b4d7  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4b4dc  throw
0x4b4dd  ldc.i4.0
0x4b4de  stloc.2
0x4b4df  br.s     loc_4B541
0x4b4e1  ldloc.0
0x4b4e2  ldloc.2
0x4b4e3  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4b4e8  ldc.i4.s 0x31
0x4b4ea  bne.un.s loc_4B53D
0x4b4ec  ldloc.2
0x4b4ed  stloc.3
0x4b4ee  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_CatalogTaskMap
0x4b4f3  ldloc.3
0x4b4f4  box      CatalogTaskEnum
0x4b4f9  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4b4fe  castclass TaskOperationMap
0x4b503  stloc.s  4
0x4b505  ldloc.s  4
0x4b507  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation[] TaskOperationMap::m_CatOper
0x4b50c  brfalse.s loc_4B53D
0x4b50e  ldc.i4.0
0x4b50f  stloc.s  5
0x4b511  br.s     loc_4B530
0x4b513  ldarg.2
0x4b514  ldind.ref
0x4b515  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::CatalogOperations
0x4b51a  ldloc.s  4
0x4b51c  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation[] TaskOperationMap::m_CatOper
0x4b521  ldloc.s  5
0x4b523  ldelem.i4
0x4b524  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation)
0x4b529  pop
0x4b52a  ldloc.s  5
0x4b52c  ldc.i4.1
0x4b52d  add
0x4b52e  stloc.s  5
0x4b530  ldloc.s  5
0x4b532  ldloc.s  4
0x4b534  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CatalogOperation[] TaskOperationMap::m_CatOper
0x4b539  ldlen
0x4b53a  conv.i4
0x4b53b  blt.s    loc_4B513
0x4b53d  ldloc.2
0x4b53e  ldc.i4.1
0x4b53f  add
0x4b540  stloc.2
0x4b541  ldloc.2
0x4b542  ldloc.0
0x4b543  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b548  blt.s    loc_4B4E1
0x4b54a  ret
0x4b54b  ldloc.0
0x4b54c  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b551  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTaskMap
0x4b556  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x4b55b  beq.s    loc_4B573
0x4b55d  ldstr    aWrongNumberOfT// "Wrong number of tasks found for role"
0x4b562  ldarg.1
0x4b563  callvirt instance string SecurityRole::get_RoleName()
0x4b568  call     string [mscorlib]System.String::Concat(string, string)
0x4b56d  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4b572  throw
0x4b573  ldc.i4.0
0x4b574  stloc.s  6
0x4b576  br       loc_4B6C4
0x4b57b  ldloc.0
0x4b57c  ldloc.s  6
0x4b57e  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4b583  ldc.i4.s 0x31
0x4b585  bne.un   loc_4B6BE
0x4b58a  ldloc.s  6
0x4b58c  stloc.s  7
0x4b58e  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_CatalogItemTaskMap
0x4b593  ldloc.s  7
0x4b595  box      CatalogItemTaskEnum
0x4b59a  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4b59f  castclass TaskOperationMap
0x4b5a4  stloc.s  8
0x4b5a6  ldloc.s  8
0x4b5a8  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperation[] TaskOperationMap::m_DSOper
0x4b5ad  brfalse.s loc_4B5DE
0x4b5af  ldc.i4.0
0x4b5b0  stloc.s  9
0x4b5b2  br.s     loc_4B5D1
0x4b5b4  ldarg.2
0x4b5b5  ldind.ref
0x4b5b6  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::DatasourceOperations
0x4b5bb  ldloc.s  8
0x4b5bd  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperation[] TaskOperationMap::m_DSOper
0x4b5c2  ldloc.s  9
0x4b5c4  ldelem.i4
0x4b5c5  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperation)
0x4b5ca  pop
0x4b5cb  ldloc.s  9
0x4b5cd  ldc.i4.1
0x4b5ce  add
0x4b5cf  stloc.s  9
0x4b5d1  ldloc.s  9
0x4b5d3  ldloc.s  8
0x4b5d5  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.DatasourceOperation[] TaskOperationMap::m_DSOper
0x4b5da  ldlen
0x4b5db  conv.i4
0x4b5dc  blt.s    loc_4B5B4
0x4b5de  ldloc.s  8
0x4b5e0  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperation[] TaskOperationMap::m_ResOper
0x4b5e5  brfalse.s loc_4B616
0x4b5e7  ldc.i4.0
0x4b5e8  stloc.s  0xA
0x4b5ea  br.s     loc_4B609
0x4b5ec  ldarg.2
0x4b5ed  ldind.ref
0x4b5ee  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::ResourceOperations
0x4b5f3  ldloc.s  8
0x4b5f5  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperation[] TaskOperationMap::m_ResOper
0x4b5fa  ldloc.s  0xA
0x4b5fc  ldelem.i4
0x4b5fd  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperation)
0x4b602  pop
0x4b603  ldloc.s  0xA
0x4b605  ldc.i4.1
0x4b606  add
0x4b607  stloc.s  0xA
0x4b609  ldloc.s  0xA
0x4b60b  ldloc.s  8
0x4b60d  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ResourceOperation[] TaskOperationMap::m_ResOper
0x4b612  ldlen
0x4b613  conv.i4
0x4b614  blt.s    loc_4B5EC
0x4b616  ldloc.s  8
0x4b618  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation[] TaskOperationMap::m_RptOper
0x4b61d  brfalse.s loc_4B64E
0x4b61f  ldc.i4.0
0x4b620  stloc.s  0xB
0x4b622  br.s     loc_4B641
0x4b624  ldarg.2
0x4b625  ldind.ref
0x4b626  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::ReportOperations
0x4b62b  ldloc.s  8
0x4b62d  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation[] TaskOperationMap::m_RptOper
0x4b632  ldloc.s  0xB
0x4b634  ldelem.i4
0x4b635  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation)
0x4b63a  pop
0x4b63b  ldloc.s  0xB
0x4b63d  ldc.i4.1
0x4b63e  add
0x4b63f  stloc.s  0xB
0x4b641  ldloc.s  0xB
0x4b643  ldloc.s  8
0x4b645  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ReportOperation[] TaskOperationMap::m_RptOper
0x4b64a  ldlen
0x4b64b  conv.i4
0x4b64c  blt.s    loc_4B624
0x4b64e  ldloc.s  8
0x4b650  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation[] TaskOperationMap::m_FldOper
0x4b655  brfalse.s loc_4B686
0x4b657  ldc.i4.0
0x4b658  stloc.s  0xC
0x4b65a  br.s     loc_4B679
0x4b65c  ldarg.2
0x4b65d  ldind.ref
0x4b65e  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::FolderOperations
0x4b663  ldloc.s  8
0x4b665  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation[] TaskOperationMap::m_FldOper
0x4b66a  ldloc.s  0xC
0x4b66c  ldelem.i4
0x4b66d  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation)
0x4b672  pop
0x4b673  ldloc.s  0xC
0x4b675  ldc.i4.1
0x4b676  add
0x4b677  stloc.s  0xC
0x4b679  ldloc.s  0xC
0x4b67b  ldloc.s  8
0x4b67d  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.FolderOperation[] TaskOperationMap::m_FldOper
0x4b682  ldlen
0x4b683  conv.i4
0x4b684  blt.s    loc_4B65C
0x4b686  ldloc.s  8
0x4b688  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation[] TaskOperationMap::m_ModelOper
0x4b68d  brfalse.s loc_4B6BE
0x4b68f  ldc.i4.0
0x4b690  stloc.s  0xD
0x4b692  br.s     loc_4B6B1
0x4b694  ldarg.2
0x4b695  ldind.ref
0x4b696  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::ModelOperations
0x4b69b  ldloc.s  8
0x4b69d  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation[] TaskOperationMap::m_ModelOper
0x4b6a2  ldloc.s  0xD
0x4b6a4  ldelem.i4
0x4b6a5  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation)
0x4b6aa  pop
0x4b6ab  ldloc.s  0xD
0x4b6ad  ldc.i4.1
0x4b6ae  add
0x4b6af  stloc.s  0xD
0x4b6b1  ldloc.s  0xD
0x4b6b3  ldloc.s  8
0x4b6b5  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelOperation[] TaskOperationMap::m_ModelOper
0x4b6ba  ldlen
0x4b6bb  conv.i4
0x4b6bc  blt.s    loc_4B694
0x4b6be  ldloc.s  6
0x4b6c0  ldc.i4.1
0x4b6c1  add
0x4b6c2  stloc.s  6
0x4b6c4  ldloc.s  6
0x4b6c6  ldloc.0
0x4b6c7  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b6cc  blt      loc_4B57B
0x4b6d1  ret
0x4b6d2  ldloc.0
0x4b6d3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b6d8  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_ModelItemTaskMap
0x4b6dd  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x4b6e2  beq.s    loc_4B6FA
0x4b6e4  ldstr    aWrongNumberOfT// "Wrong number of tasks found for role"
0x4b6e9  ldarg.1
0x4b6ea  callvirt instance string SecurityRole::get_RoleName()
0x4b6ef  call     string [mscorlib]System.String::Concat(string, string)
0x4b6f4  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4b6f9  throw
0x4b6fa  ldc.i4.0
0x4b6fb  stloc.s  0xE
0x4b6fd  br.s     loc_4B765
0x4b6ff  ldloc.0
0x4b700  ldloc.s  0xE
0x4b702  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x4b707  ldc.i4.s 0x31
0x4b709  bne.un.s loc_4B75F
0x4b70b  ldloc.s  0xE
0x4b70d  stloc.s  0xF
0x4b70f  ldsfld   class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Library.AuthzData::m_ModelItemTaskMap
0x4b714  ldloc.s  0xF
0x4b716  box      ModelItemTaskEnum
0x4b71b  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x4b720  castclass TaskOperationMap
0x4b725  stloc.s  0x10
0x4b727  ldloc.s  0x10
0x4b729  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperation[] TaskOperationMap::m_ModelItemOper
0x4b72e  brfalse.s loc_4B75F
0x4b730  ldc.i4.0
0x4b731  stloc.s  0x11
0x4b733  br.s     loc_4B752
0x4b735  ldarg.2
0x4b736  ldind.ref
0x4b737  ldfld    class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AceStruct::ModelItemOperations
0x4b73c  ldloc.s  0x10
0x4b73e  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperation[] TaskOperationMap::m_ModelItemOper
0x4b743  ldloc.s  0x11
0x4b745  ldelem.i4
0x4b746  callvirt instance int32 [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperationsCollection::Add(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperation)
0x4b74b  pop
0x4b74c  ldloc.s  0x11
0x4b74e  ldc.i4.1
0x4b74f  add
0x4b750  stloc.s  0x11
0x4b752  ldloc.s  0x11
0x4b754  ldloc.s  0x10
0x4b756  ldfld    valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ModelItemOperation[] TaskOperationMap::m_ModelItemOper
0x4b75b  ldlen
0x4b75c  conv.i4
0x4b75d  blt.s    loc_4B735
0x4b75f  ldloc.s  0xE
0x4b761  ldc.i4.1
0x4b762  add
0x4b763  stloc.s  0xE
0x4b765  ldloc.s  0xE
0x4b767  ldloc.0
0x4b768  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4b76d  blt.s    loc_4B6FF
0x4b76f  ret
0x4b770  ldstr    aUnknownSecurit_0// "Unknown security scope"
0x4b775  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x4b77a  throw
```
