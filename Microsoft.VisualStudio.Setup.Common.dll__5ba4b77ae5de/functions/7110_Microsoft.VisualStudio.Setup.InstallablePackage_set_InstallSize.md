# Microsoft.VisualStudio.Setup.InstallablePackage::set_InstallSize

- ea: `0x7110`
- end: `0x7160`
- name: `Microsoft.VisualStudio.Setup.InstallablePackage::set_InstallSize`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callees

- `0x70e0`
- `0x70f0`
- `0x7110`
- `0x79c0`
- `0x7a50`
- `0x7a60`
- `0x7a70`
- `0x7a80`
- `0x9a90`

## pseudocode

```c

```

## disassembly

```asm
0x7110  ldarg.0
0x7111  call     instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.InstallablePackage::get_InstallSizes()
0x7116  brtrue.s loc_7123
0x7118  ldarg.0
0x7119  newobj   instance void Microsoft.VisualStudio.Setup.InstallSize::.ctor()
0x711e  call     instance void Microsoft.VisualStudio.Setup.InstallablePackage::set_InstallSizes(class Microsoft.VisualStudio.Setup.InstallSize value)
0x7123  ldarg.0
0x7124  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.Package::get_Type()
0x7129  ldc.i4.1
0x712a  bne.un.s loc_7146
0x712c  ldarg.0
0x712d  call     instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.InstallablePackage::get_InstallSizes()
0x7132  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_TargetDrive()
0x7137  brtrue.s loc_715F
0x7139  ldarg.0
0x713a  call     instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.InstallablePackage::get_InstallSizes()
0x713f  ldarg.1
0x7140  callvirt instance void Microsoft.VisualStudio.Setup.InstallSize::set_TargetDrive(int64 value)
0x7145  ret
0x7146  ldarg.0
0x7147  call     instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.InstallablePackage::get_InstallSizes()
0x714c  callvirt instance int64 Microsoft.VisualStudio.Setup.InstallSize::get_SystemDrive()
0x7151  brtrue.s loc_715F
0x7153  ldarg.0
0x7154  call     instance class Microsoft.VisualStudio.Setup.InstallSize Microsoft.VisualStudio.Setup.InstallablePackage::get_InstallSizes()
0x7159  ldarg.1
0x715a  callvirt instance void Microsoft.VisualStudio.Setup.InstallSize::set_SystemDrive(int64 value)
0x715f  ret
```
