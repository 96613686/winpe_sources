# Microsoft.ManagementConsole.NodeSyncManager::RemoveNodes

- ea: `0x1350`
- end: `0x1454`
- name: `Microsoft.ManagementConsole.NodeSyncManager::RemoveNodes`
- size: `260`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0xa40`
- `0x41a0`
- `0x66d0`

## callees

- `0x2c0`
- `0x670`
- `0x840`
- `0x870`
- `0x11f0`
- `0x1350`
- `0x15f0`
- `0x1ea0`
- `0x2000`
- `0x2040`
- `0x5c80`
- `0x5cb0`
- `0x8440`

## string_xrefs

- `0x13c3`: `NodeSyncManager.RemoveNodes() failed`

## pseudocode

```c

```

## disassembly

```asm
0x1350  ldarg.0
0x1351  ldfld    bool Microsoft.ManagementConsole.NodeSyncManager::_initialized
0x1356  brtrue.s loc_1368
0x1358  call     string Microsoft.ManagementConsole.Internal.Strings::get_NodeSyncManagerNotInitialized()
0x135d  call     string Microsoft.ManagementConsole.Internal.Utility::LoadResourceString(string resourceName)
0x1362  newobj   instance void [mscorlib]System.Exception::.ctor(string)
0x1367  throw
0x1368  ldarg.1
0x1369  ldlen
0x136a  conv.i4
0x136b  brtrue.s loc_136E
0x136d  ret
0x136e  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.ScopeNode>::.ctor()
0x1373  stloc.0
0x1374  ldarg.1
0x1375  ldlen
0x1376  conv.i4
0x1377  newarr   [mscorlib]System.Int32
0x137c  stloc.1
0x137d  ldc.i4.0
0x137e  stloc.2
0x137f  br.s     loc_1390
0x1381  ldloc.1
0x1382  ldloc.2
0x1383  ldarg.1
0x1384  ldloc.2
0x1385  ldelem.ref
0x1386  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x138b  stelem.i4
0x138c  ldloc.2
0x138d  ldc.i4.1
0x138e  add
0x138f  stloc.2
0x1390  ldloc.2
0x1391  ldarg.1
0x1392  ldlen
0x1393  conv.i4
0x1394  blt.s    loc_1381
0x1396  ldarg.0
0x1397  ldloc.0
0x1398  ldarg.1
0x1399  call     instance void Microsoft.ManagementConsole.NodeSyncManager::AddTreeToDeletionList(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.ScopeNode> nodeList, class Microsoft.ManagementConsole.ScopeNode[] nodes)
0x139e  newobj   instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DeleteScopeNodesCommand::.ctor()
0x13a3  stloc.3
0x13a4  ldloc.3
0x13a5  ldloc.1
0x13a6  callvirt instance void [MMCFxCommon]Microsoft.ManagementConsole.Internal.DeleteScopeNodesCommand::SetIds(int32[])
0x13ab  ldarg.0
0x13ac  ldfld    class [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform Microsoft.ManagementConsole.NodeSyncManager::_snapInPlatform
0x13b1  ldloc.3
0x13b2  callvirt instance class [MMCFxCommon]Microsoft.ManagementConsole.Internal.CommandResult [MMCFxCommon]Microsoft.ManagementConsole.Internal.ISnapInPlatform::ProcessCommand(class [MMCFxCommon]Microsoft.ManagementConsole.Internal.Command)
0x13b7  pop
0x13b8  leave.s  loc_13CF
0x13ba  pop
0x13bb  call     class [System]System.Diagnostics.TraceSource [MMCFxCommon]Microsoft.ManagementConsole.TraceSources::get_ExecutiveSource()
0x13c0  ldc.i4.4
0x13c1  ldc.i4.s 0xC
0x13c3  ldstr    aNodesyncmanage_6// "NodeSyncManager.RemoveNodes() failed"
0x13c8  callvirt instance void [System]System.Diagnostics.TraceSource::TraceEvent(valuetype [System]System.Diagnostics.TraceEventType, int32, string)
0x13cd  rethrow
0x13cf  ldloc.0
0x13d0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ManagementConsole.ScopeNode>::GetEnumerator()
0x13d5  stloc.s  5
0x13d7  br.s     loc_143A
0x13d9  ldloca.s 5
0x13db  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.ScopeNode>::get_Current()
0x13e0  stloc.s  4
0x13e2  ldloc.s  4
0x13e4  callvirt instance class Microsoft.ManagementConsole.ScopeNodeCollection Microsoft.ManagementConsole.ScopeNode::get_Children()
0x13e9  ldarg.0
0x13ea  ldftn    instance void Microsoft.ManagementConsole.NodeSyncManager::OnNodesChanged(object sender, class Microsoft.ManagementConsole.ScopeNodeCollectionEventArgs e)
0x13f0  newobj   instance void ScopeNodeCollectionEventHandler::.ctor(object object, native int method)
0x13f5  callvirt instance void Microsoft.ManagementConsole.ScopeNodeCollection::remove_ItemsChanged(class ScopeNodeCollectionEventHandler value)
0x13fa  ldloc.s  4
0x13fc  ldarg.0
0x13fd  ldftn    instance void Microsoft.ManagementConsole.NodeSyncManager::OnNodeChanged(object sender, class Microsoft.ManagementConsole.NodeChangedEventArgs e)
0x1403  newobj   instance void NodeChangedEventHandler::.ctor(object object, native int method)
0x1408  callvirt instance void Microsoft.ManagementConsole.Node::remove_Changed(class NodeChangedEventHandler value)
0x140d  ldloc.s  4
0x140f  ldarg.0
0x1410  ldftn    instance void Microsoft.ManagementConsole.NodeSyncManager::OnNodeSharedDataChanged(object sender, class Microsoft.ManagementConsole.WritableSharedDataChangedEventArgs e)
0x1416  newobj   instance void SharedDataChangedEventHandler::.ctor(object object, native int method)
0x141b  callvirt instance void Microsoft.ManagementConsole.ScopeNode::remove_SharedDataChanged(class SharedDataChangedEventHandler value)
0x1420  ldarg.0
0x1421  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.ScopeNode> Microsoft.ManagementConsole.NodeSyncManager::_nodes
0x1426  ldloc.s  4
0x1428  callvirt instance int32 Microsoft.ManagementConsole.Node::get_Id()
0x142d  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ManagementConsole.ScopeNode>::Remove(var<u1>)
0x1432  pop
0x1433  ldloc.s  4
0x1435  callvirt instance void Microsoft.ManagementConsole.ScopeNode::OnNodeSyncManagerRemove()
0x143a  ldloca.s 5
0x143c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.ScopeNode>::MoveNext()
0x1441  brtrue.s loc_13D9
0x1443  leave.s  loc_1453
0x1445  ldloca.s 5
0x1447  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ManagementConsole.ScopeNode>
0x144d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1452  endfinally
0x1453  ret
```
