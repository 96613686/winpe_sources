# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::CommitSelection

- ea: `0x151d0`
- end: `0x15243`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::CommitSelection`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7f50`
- `0x8330`
- `0x8350`
- `0x8370`
- `0x8380`
- `0x14850`
- `0x151d0`
- `0x16690`
- `0x166e0`

## pseudocode

```c

```

## disassembly

```asm
0x151d0  ldarg.0
0x151d1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::get_InstallOrder()
0x151d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x151db  stloc.0
0x151dc  br.s     loc_1522E
0x151de  ldloc.0
0x151df  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x151e4  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x151e9  stloc.1
0x151ea  ldarg.1
0x151eb  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> Microsoft.VisualStudio.Setup.Dependencies.ISelectionPlan::get_UpdatedSelections()
0x151f0  ldloc.1
0x151f1  ldloca.s 2
0x151f3  callvirt instance bool class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState>::TryGetValue(var<u1>, !!T0)
0x151f8  brfalse.s loc_1522E
0x151fa  ldloc.1
0x151fb  isinst   Microsoft.VisualStudio.Setup.ISelectablePackage
0x15200  stloc.3
0x15201  ldloc.3
0x15202  brfalse.s loc_1522E
0x15204  ldloc.3
0x15205  ldloc.2
0x15206  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x1520b  brtrue.s loc_15210
0x1520d  ldc.i4.1
0x1520e  br.s     loc_15211
0x15210  ldc.i4.3
0x15211  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x15216  ldloc.3
0x15217  ldloc.2
0x15218  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectionState::get_SelectedState()
0x1521d  callvirt instance void Microsoft.VisualStudio.Setup.ISelectablePackage::set_SelectedState(valuetype Microsoft.VisualStudio.Setup.SelectedState value)
0x15222  ldloc.3
0x15223  ldloc.2
0x15224  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectionState::get_UserSelectedState()
0x15229  callvirt instance void Microsoft.VisualStudio.Setup.ISelectablePackage::set_UserSelectedState(valuetype Microsoft.VisualStudio.Setup.UserSelectedState value)
0x1522e  ldloc.0
0x1522f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x15234  brtrue.s loc_151DE
0x15236  leave.s  loc_15242
0x15238  ldloc.0
0x15239  brfalse.s loc_15241
0x1523b  ldloc.0
0x1523c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x15241  endfinally
0x15242  ret
```
