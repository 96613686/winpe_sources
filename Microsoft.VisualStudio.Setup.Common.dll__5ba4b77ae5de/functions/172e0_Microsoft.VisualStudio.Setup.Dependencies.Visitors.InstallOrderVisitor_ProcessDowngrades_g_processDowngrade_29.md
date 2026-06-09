# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__processDowngrade|29_1

- ea: `0x172e0`
- end: `0x173ae`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::<ProcessDowngrades>g__processDowngrade|29_1`
- size: `206`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x170e0`

## callees

- `0x5ec0`
- `0x7f50`
- `0x8260`
- `0x11b00`
- `0x16690`
- `0x16e70`
- `0x172e0`

## pseudocode

```c

```

## disassembly

```asm
0x172e0  ldarg.1
0x172e1  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x172e6  stloc.0
0x172e7  ldloc.0
0x172e8  call     bool Microsoft.VisualStudio.Setup.Extensions::IsDowngradable(class Microsoft.VisualStudio.Setup.IPackage package)
0x172ed  brfalse  loc_1737C
0x172f2  ldloc.0
0x172f3  ldc.i4.4
0x172f4  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x172f9  ldarg.0
0x172fa  ldarg.1
0x172fb  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::DowngradeNode(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x17300  stloc.1
0x17301  ldarg.2
0x17302  brtrue.s loc_17312
0x17304  ldarg.3
0x17305  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x1730a  ldloc.1
0x1730b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Add(var<u1>)
0x17310  br.s     loc_1732C
0x17312  ldarg.3
0x17313  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x17318  ldarg.3
0x17319  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> <>c__DisplayClass29_0::nodes
0x1731e  ldarg.1
0x1731f  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::IndexOf(var<u1>)
0x17324  ldc.i4.1
0x17325  add
0x17326  ldloc.1
0x17327  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode>::Insert(int32, var<u1>)
0x1732c  ldarg.0
0x1732d  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::logger
0x17332  dup
0x17333  brtrue.s loc_17337
0x17335  pop
0x17336  ret
0x17337  ldc.i4.5
0x17338  newarr   [mscorlib]System.String
0x1733d  dup
0x1733e  ldc.i4.0
0x1733f  ldstr    aPackage_1// "Package '"
0x17344  stelem.ref
0x17345  dup
0x17346  ldc.i4.1
0x17347  ldloc.0
0x17348  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x1734d  stelem.ref
0x1734e  dup
0x1734f  ldc.i4.2
0x17350  ldstr    aWillRequestADo// "' will request a downgrade to '"
0x17355  stelem.ref
0x17356  dup
0x17357  ldc.i4.3
0x17358  ldloc.1
0x17359  callvirt instance class Microsoft.VisualStudio.Setup.IPackage Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_Package()
0x1735e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x17363  stelem.ref
0x17364  dup
0x17365  ldc.i4.4
0x17366  ldstr    asc_21DE4// "'."
0x1736b  stelem.ref
0x1736c  call     string [mscorlib]System.String::Concat(string[])
0x17371  call     T0x2B000016
0x17376  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x1737b  ret
0x1737c  ldloc.0
0x1737d  ldc.i4.1
0x1737e  callvirt instance void Microsoft.VisualStudio.Setup.IPackage::set_RequestedState(valuetype Microsoft.VisualStudio.Setup.RequestedState value)
0x17383  ldarg.0
0x17384  ldfld    class Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::logger
0x17389  dup
0x1738a  brtrue.s loc_1738E
0x1738c  pop
0x1738d  ret
0x1738e  ldstr    aPackage_1// "Package '"
0x17393  ldloc.0
0x17394  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x17399  ldstr    aWillRequestRem// "' will request removal: no previous ver"...
0x1739e  call     string [mscorlib]System.String::Concat(string, string, string)
0x173a3  call     T0x2B000016
0x173a8  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x173ad  ret
```
