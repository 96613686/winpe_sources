# Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Visit

- ea: `0x16ba0`
- end: `0x16bd5`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::Visit`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14f50`
- `0x15540`
- `0x155e0`

## callees

- `0x16b40`
- `0x16b80`
- `0x16ba0`
- `0x16be0`
- `0x16d00`
- `0x170e0`

## pseudocode

```c

```

## disassembly

```asm
0x16ba0  ldarg.0
0x16ba1  call     instance class [mscorlib]System.Collections.Generic.IList`1<class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode> Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_VisitedOrder()
0x16ba6  call     T0x2B000093
0x16bab  brfalse.s loc_16BAE
0x16bad  ret
0x16bae  ldarg.0
0x16baf  ldarg.0
0x16bb0  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::rootNode
0x16bb5  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::VisitHelper(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode node)
0x16bba  ldarg.0
0x16bbb  ldarg.0
0x16bbc  ldfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::rootNode
0x16bc1  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::PostRootVisit(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode root)
0x16bc6  ldarg.0
0x16bc7  call     instance bool Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::get_ShouldDowngrade()
0x16bcc  brfalse.s loc_16BD4
0x16bce  ldarg.0
0x16bcf  call     instance void Microsoft.VisualStudio.Setup.Dependencies.Visitors.InstallOrderVisitor::ProcessDowngrades()
0x16bd4  ret
```
