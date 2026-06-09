# Microsoft.ManagementConsole.View::CreateSharedDataObjectUpdate

- ea: `0xa500`
- end: `0xa5cc`
- name: `Microsoft.ManagementConsole.View::CreateSharedDataObjectUpdate`
- size: `204`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0xa050`
- `0xa0c0`

## callees

- `0x5200`
- `0xa480`
- `0xa500`

## pseudocode

```c

```

## disassembly

```asm
0xa500  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::.ctor()
0xa505  stloc.0
0xa506  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa50b  stloc.1
0xa50c  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa511  stloc.2
0xa512  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa517  stloc.3
0xa518  ldarg.0
0xa519  ldarg.1
0xa51a  ldloc.2
0xa51b  ldloc.1
0xa51c  call     instance void Microsoft.ManagementConsole.View::ParseSharedDataItems(class Microsoft.ManagementConsole.WritableSharedDataItem[] items, class [mscorlib]System.Collections.ArrayList formats, class [mscorlib]System.Collections.ArrayList dataUpdate)
0xa521  ldloc.0
0xa522  ldloc.2
0xa523  ldtoken  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xa528  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa52d  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xa532  castclass valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration[]
0xa537  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetAddedFormats(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration[])
0xa53c  ldarg.0
0xa53d  ldarg.2
0xa53e  ldloc.3
0xa53f  ldloc.1
0xa540  call     instance void Microsoft.ManagementConsole.View::ParseSharedDataItems(class Microsoft.ManagementConsole.WritableSharedDataItem[] items, class [mscorlib]System.Collections.ArrayList formats, class [mscorlib]System.Collections.ArrayList dataUpdate)
0xa545  ldloc.0
0xa546  ldloc.3
0xa547  ldtoken  [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration
0xa54c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa551  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xa556  castclass valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration[]
0xa55b  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetChangedFormats(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.DataFormatConfiguration[])
0xa560  ldloc.0
0xa561  ldloc.1
0xa562  ldtoken  [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData
0xa567  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa56c  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xa571  castclass valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData[]
0xa576  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetUpdatedData(valuetype [MMCFxCommon]Microsoft.ManagementConsole.Internal.ClipboardData[])
0xa57b  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0xa580  stloc.s  4
0xa582  ldarg.3
0xa583  stloc.s  6
0xa585  ldc.i4.0
0xa586  stloc.s  7
0xa588  br.s     loc_A5A6
0xa58a  ldloc.s  6
0xa58c  ldloc.s  7
0xa58e  ldelem.ref
0xa58f  stloc.s  5
0xa591  ldloc.s  4
0xa593  ldloc.s  5
0xa595  callvirt instance string Microsoft.ManagementConsole.SharedDataItemBase::get_ClipboardFormatId()
0xa59a  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0xa59f  pop
0xa5a0  ldloc.s  7
0xa5a2  ldc.i4.1
0xa5a3  add
0xa5a4  stloc.s  7
0xa5a6  ldloc.s  7
0xa5a8  ldloc.s  6
0xa5aa  ldlen
0xa5ab  conv.i4
0xa5ac  blt.s    loc_A58A
0xa5ae  ldloc.0
0xa5af  ldloc.s  4
0xa5b1  ldtoken  [mscorlib]System.String
0xa5b6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xa5bb  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0xa5c0  castclass string[]
0xa5c5  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.SharedDataObjectUpdate::SetRemovedClipboardFormatIds(string[])
0xa5ca  ldloc.0
0xa5cb  ret
```
