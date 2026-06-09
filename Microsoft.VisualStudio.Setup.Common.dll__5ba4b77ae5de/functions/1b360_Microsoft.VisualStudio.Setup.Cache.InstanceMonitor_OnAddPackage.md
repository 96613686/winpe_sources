# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::OnAddPackage

- ea: `0x1b360`
- end: `0x1b39e`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::OnAddPackage`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7ee0`
- `0xc1a0`
- `0x1a990`
- `0x1a9a0`
- `0x1b360`
- `0x1b4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b360  ldarg.1
0x1b361  ldstr    aPackage// "package"
0x1b366  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1b36b  ldarg.0
0x1b36c  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b371  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b376  ldc.i4.1
0x1b377  and
0x1b378  ldc.i4.1
0x1b379  beq.s    loc_1B381
0x1b37b  ldarg.0
0x1b37c  call     instance void Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::SetLocalState()
0x1b381  ldarg.1
0x1b382  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x1b387  ldc.i4.6
0x1b388  bne.un.s loc_1B39D
0x1b38a  ldarg.0
0x1b38b  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b390  dup
0x1b391  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b396  ldc.i4.2
0x1b397  or
0x1b398  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b39d  ret
```
