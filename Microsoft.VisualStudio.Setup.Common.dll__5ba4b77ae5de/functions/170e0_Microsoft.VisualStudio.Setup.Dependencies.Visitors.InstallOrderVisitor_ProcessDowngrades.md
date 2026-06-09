# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ProcessDowngrades

- ea: `0x170e0`
- end: `0x1725a`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ProcessDowngrades`
- size: `378`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16ba0`

## callees

- `0x5fd0`
- `0x61d0`
- `0x7f40`
- `0x8260`
- `0x11b00`
- `0x16690`
- `0x166c0`
- `0x16b40`
- `0x16b50`
- `0x16b70`
- `0x170e0`
- `0x17290`
- `0x172e0`

## pseudocode

```c

```

## disassembly

```asm
0x170e0  ldloca.s 0
0x170e2  ldarg.0
0x170e3  stfld    class Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor <>c__DisplayClass29_0::<>4__this
0x170e8  ldloca.s 0
0x170ea  ldarg.0
0x170eb  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_VisitedOrder()
0x170f0  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Count()
0x170f5  ldc.i4.s 0x32
0x170f7  add
0x170f8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::.ctor(int32)
0x170fd  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x17102  newobj   instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::.ctor()
0x17107  stloc.1
0x17108  ldarg.0
0x17109  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_VisitedOrder()
0x1710e  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x17113  stloc.2
0x17114  br.s     loc_1717E
0x17116  ldloc.2
0x17117  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x1711c  stloc.3
0x1711d  ldloc.3
0x1711e  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x17123  stloc.s  4
0x17125  ldloc.s  4
0x17127  brfalse.s loc_17172
0x17129  ldloc.s  4
0x1712b  call     string Microsoft.VisualStudio.Setup.Extensions::GetManifestId(class Microsoft.VisualStudio.Setup.IPackage package)
0x17130  stloc.s  5
0x17132  ldloc.s  5
0x17134  call     bool Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty(string source)
0x17139  brtrue.s loc_1714A
0x1713b  ldarg.0
0x1713c  call     instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_CatalogsToUninstall()
0x17141  ldloc.s  5
0x17143  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0x17148  br.s     loc_1714B
0x1714a  ldc.i4.0
0x1714b  brtrue.s loc_17157
0x1714d  ldloc.s  4
0x1714f  callvirt instance valuetype Microsoft.VisualStudio.Setup.RequestedState Microsoft.VisualStudio.Setup.IPackage::get_RequestedState()
0x17154  ldc.i4.4
0x17155  bne.un.s loc_17163
0x17157  ldarg.0
0x17158  ldloc.3
0x17159  ldc.i4.0
0x1715a  ldloca.s 0
0x1715c  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__processDowngrade|29_1(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] bool inPlaceInsertion, [opt] valuetype <>c__DisplayClass29_0& services)
0x17161  br.s     loc_17172
0x17163  ldloc.3
0x17164  call     bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__isAbsentNodeRequiredToDowngrade|29_0(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode x)
0x17169  brfalse.s loc_17172
0x1716b  ldloc.1
0x1716c  ldloc.3
0x1716d  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Enqueue(var<u1>)
0x17172  ldloc.0
0x17173  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x17178  ldloc.3
0x17179  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Add(var<u1>)
0x1717e  ldloc.2
0x1717f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17184  brtrue.s loc_17116
0x17186  leave    loc_17241
0x1718b  ldloc.2
0x1718c  brfalse.s loc_17194
0x1718e  ldloc.2
0x1718f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17194  endfinally
0x17195  ldloc.1
0x17196  callvirt instance var<u1> class [System]System.Collections.Generic.Queue`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Dequeue()
0x1719b  stloc.s  6
0x1719d  ldarg.0
0x1719e  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::logger
0x171a3  dup
0x171a4  brtrue.s loc_171A9
0x171a6  pop
0x171a7  br.s     loc_171CE
0x171a9  ldstr    aPackage_1// "Package '"
0x171ae  ldloc.s  6
0x171b0  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x171b5  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x171ba  ldstr    aDetectedAsRequ// "' detected as requesting absent but req"...
0x171bf  call     string [mscorlib]System.String::Concat(string, string, string)
0x171c4  call     T0x2B000016
0x171c9  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x171ce  ldarg.0
0x171cf  ldloc.s  6
0x171d1  ldc.i4.1
0x171d2  ldloca.s 0
0x171d4  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__processDowngrade|29_1(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node, [opt] bool inPlaceInsertion, [opt] valuetype <>c__DisplayClass29_0& services)
0x171d9  ldloc.s  6
0x171db  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Children()
0x171e0  ldsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c::<>9__29_3
0x171e5  dup
0x171e6  brtrue.s loc_171FF
0x171e8  pop
0x171e9  ldsfld   class <>c <>c::<>9
0x171ee  ldftn    instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode <>c::<ProcessDowngrades>b__29_3(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc x)
0x171f4  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::.ctor(object, native int)
0x171f9  dup
0x171fa  stsfld   class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyArc, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c::<>9__29_3
0x171ff  call     T0x2B000082
0x17204  ldnull
0x17205  ldftn    bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__isAbsentNodeRequiredToDowngrade|29_0(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode x)
0x1720b  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode, bool>::.ctor(object, native int)
0x17210  call     T0x2B000099
0x17215  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::GetEnumerator()
0x1721a  stloc.2
0x1721b  br.s     loc_1722D
0x1721d  ldloc.2
0x1721e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Current()
0x17223  stloc.s  7
0x17225  ldloc.1
0x17226  ldloc.s  7
0x17228  callvirt instance void class [System]System.Collections.Generic.Queue`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Enqueue(var<u1>)
0x1722d  ldloc.2
0x1722e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x17233  brtrue.s loc_1721D
0x17235  leave.s  loc_17241
0x17237  ldloc.2
0x17238  brfalse.s loc_17240
0x1723a  ldloc.2
0x1723b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17240  endfinally
0x17241  ldloc.1
0x17242  callvirt instance int32 class [System]System.Collections.Generic.Queue`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::get_Count()
0x17247  ldc.i4.0
0x17248  bgt      loc_17195
0x1724d  ldarg.0
0x1724e  ldloc.0
0x1724f  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x17254  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::set_VisitedOrder(class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> value)
0x17259  ret
```
