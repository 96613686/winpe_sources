# Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetUpdatedSelectedState

- ea: `0x152f0`
- end: `0x153e2`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::GetUpdatedSelectedState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14fb0`

## callees

- `0x59a0`
- `0x5a40`
- `0x81e0`
- `0x8320`
- `0x8340`
- `0xbaa0`
- `0x152f0`
- `0x153f0`
- `0x15420`
- `0x15460`
- `0x16690`

## pseudocode

```c

```

## disassembly

```asm
0x152f0  ldarg.1
0x152f1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x152f6  call     bool Microsoft.VisualStudio.Setup.Extensions::IsSelectable(class Microsoft.VisualStudio.Setup.IPackage package)
0x152fb  brfalse.s loc_1530C
0x152fd  ldarg.1
0x152fe  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x15303  isinst   Microsoft.VisualStudio.Setup.ISelectablePackage
0x15308  stloc.0
0x15309  ldloc.0
0x1530a  brtrue.s loc_1532C
0x1530c  ldstr    aPackage_0// "Package "
0x15311  ldarg.1
0x15312  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x15317  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x1531c  ldstr    aIsNotSelectabl// " is not selectable"
0x15321  call     string [mscorlib]System.String::Concat(string, string, string)
0x15326  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1532b  throw
0x1532c  ldc.i4.0
0x1532d  stloc.1
0x1532e  ldarg.2
0x1532f  brtrue.s loc_15393
0x15331  ldarg.3
0x15332  ldc.i4.2
0x15333  bne.un.s loc_1533C
0x15335  ldc.i4.1
0x15336  stloc.1
0x15337  br       loc_153C5
0x1533c  ldarg.0
0x1533d  ldarg.1
0x1533e  ldarg.s  4
0x15340  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::AreDependenciesMet(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> updatedSelections)
0x15345  brtrue.s loc_15353
0x15347  ldloc.0
0x15348  call     valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.Extensions::GetSelectedState(class Microsoft.VisualStudio.Setup.IPackage package)
0x1534d  brfalse.s loc_15353
0x1534f  ldc.i4.1
0x15350  stloc.1
0x15351  br.s     loc_153C5
0x15353  ldloc.0
0x15354  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_UserSelectedState()
0x15359  ldc.i4.1
0x1535a  bne.un.s loc_1536D
0x1535c  ldarg.0
0x1535d  ldarg.1
0x1535e  ldarg.s  4
0x15360  ldarg.s  5
0x15362  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::HasSelectedParentOnDeselection(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> updatedSelections, bool useReducedSet)
0x15367  brtrue.s loc_153C5
0x15369  ldc.i4.1
0x1536a  stloc.1
0x1536b  br.s     loc_153C5
0x1536d  ldloc.0
0x1536e  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_UserSelectedState()
0x15373  ldc.i4.2
0x15374  bne.un.s loc_153C5
0x15376  ldarg.0
0x15377  ldarg.1
0x15378  ldarg.s  4
0x1537a  ldarg.s  5
0x1537c  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::HasSelectedParentOnDeselection(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> updatedSelections, bool useReducedSet)
0x15381  brtrue.s loc_153C5
0x15383  ldloc.0
0x15384  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x15389  brfalse.s loc_153C5
0x1538b  ldc.i4.1
0x1538c  ldc.i4.2
0x1538d  newobj   instance void Microsoft.VisualStudio.Setup.SelectionState::.ctor(valuetype Microsoft.VisualStudio.Setup.SelectedState selectedState, valuetype Microsoft.VisualStudio.Setup.UserSelectedState userSelectedState)
0x15392  ret
0x15393  ldarg.3
0x15394  ldc.i4.2
0x15395  bne.un.s loc_1539B
0x15397  ldc.i4.1
0x15398  stloc.1
0x15399  br.s     loc_153C5
0x1539b  ldloc.0
0x1539c  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_UserSelectedState()
0x153a1  ldc.i4.2
0x153a2  bne.un.s loc_153BB
0x153a4  ldarg.0
0x153a5  ldarg.1
0x153a6  ldarg.s  4
0x153a8  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.DependencyGraph::HasSelectedRequiredParent(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<class Microsoft.VisualStudio.Setup.IPackageIdentity, class Microsoft.VisualStudio.Setup.ISelectionState> updatedSelections)
0x153ad  brfalse.s loc_153C5
0x153af  ldloc.0
0x153b0  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x153b5  brtrue.s loc_153C5
0x153b7  ldc.i4.1
0x153b8  stloc.1
0x153b9  br.s     loc_153C5
0x153bb  ldloc.0
0x153bc  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x153c1  brtrue.s loc_153C5
0x153c3  ldc.i4.1
0x153c4  stloc.1
0x153c5  ldloc.1
0x153c6  brtrue.s loc_153DA
0x153c8  ldloc.0
0x153c9  callvirt instance valuetype Microsoft.VisualStudio.Setup.SelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_SelectedState()
0x153ce  ldloc.0
0x153cf  callvirt instance valuetype Microsoft.VisualStudio.Setup.UserSelectedState Microsoft.VisualStudio.Setup.ISelectablePackage::get_UserSelectedState()
0x153d4  newobj   instance void Microsoft.VisualStudio.Setup.SelectionState::.ctor(valuetype Microsoft.VisualStudio.Setup.SelectedState selectedState, valuetype Microsoft.VisualStudio.Setup.UserSelectedState userSelectedState)
0x153d9  ret
0x153da  ldarg.2
0x153db  ldarg.3
0x153dc  newobj   instance void Microsoft.VisualStudio.Setup.SelectionState::.ctor(valuetype Microsoft.VisualStudio.Setup.SelectedState selectedState, valuetype Microsoft.VisualStudio.Setup.UserSelectedState userSelectedState)
0x153e1  ret
```
