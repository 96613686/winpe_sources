# Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::OnRemovePackage

- ea: `0x1b3a0`
- end: `0x1b3e7`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::OnRemovePackage`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x7ee0`
- `0xc1a0`
- `0x1a990`
- `0x1a9a0`
- `0x1b3a0`
- `0x1b3f0`
- `0x1b4b0`

## pseudocode

```c

```

## disassembly

```asm
0x1b3a0  ldarg.1
0x1b3a1  ldstr    aPackage// "package"
0x1b3a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1b3ab  ldarg.0
0x1b3ac  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b3b1  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b3b6  ldc.i4.1
0x1b3b7  and
0x1b3b8  ldc.i4.1
0x1b3b9  bne.un.s loc_1B3C1
0x1b3bb  ldarg.0
0x1b3bc  call     instance void Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::SetLocalState()
0x1b3c1  ldarg.1
0x1b3c2  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x1b3c7  ldc.i4.6
0x1b3c8  bne.un.s loc_1B3E6
0x1b3ca  ldarg.0
0x1b3cb  call     instance bool Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::HasProduct()
0x1b3d0  brtrue.s loc_1B3E6
0x1b3d2  ldarg.0
0x1b3d3  ldfld    class Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceMonitor::instance
0x1b3d8  dup
0x1b3d9  callvirt instance valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState Microsoft.VisualStudio.Setup.Cache.Instance::get_State()
0x1b3de  ldc.i4.s 0xFD
0x1b3e0  and
0x1b3e1  callvirt instance void Microsoft.VisualStudio.Setup.Cache.Instance::set_State(valuetype Microsoft.VisualStudio.Setup.Cache.InstanceState value)
0x1b3e6  ret
```
