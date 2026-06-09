# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__isAbsentNodeRequiredToDowngrade|29_0

- ea: `0x17290`
- end: `0x172d8`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__isAbsentNodeRequiredToDowngrade|29_0`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x170e0`

## callees

- `0x5ed0`
- `0x7f40`
- `0x16690`
- `0x166b0`
- `0x17290`

## pseudocode

```c

```

## disassembly

```asm
0x17290  ldarg.0
0x17291  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17296  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x1729b  ldc.i4.1
0x1729c  bne.un.s loc_172D6
0x1729e  ldarg.0
0x1729f  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x172a4  call     bool Microsoft.VisualStudio.Setup.Extensions::IsInstanceDowngradableType(class Microsoft.VisualStudio.Setup.IPackage package)
0x172a9  brfalse.s loc_172D6
0x172ab  ldarg.0
0x172ac  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Parents()
0x172b1  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, bool> <>c::<>9__29_2
0x172b6  dup
0x172b7  brtrue.s loc_172D0
0x172b9  pop
0x172ba  ldsfld   class <>c <>c::<>9
0x172bf  ldftn    instance bool <>c::<ProcessDowngrades>b__29_2(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc y)
0x172c5  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, bool>::.ctor(object, native int)
0x172ca  dup
0x172cb  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, bool> <>c::<>9__29_2
0x172d0  call     T0x2B000081
0x172d5  ret
0x172d6  ldc.i4.0
0x172d7  ret
```
