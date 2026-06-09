# Microsoft.VisualStudio.Setup.InstallSize::.ctor_1

- ea: `0x79e0`
- end: `0x7a43`
- name: `Microsoft.VisualStudio.Setup.InstallSize::.ctor_1`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x79a0`
- `0x79c0`
- `0x14920`

## callees

- `0x7a60`
- `0x7a80`
- `0x7aa0`
- `0x7ac0`

## string_xrefs

- `0x7a24`: `cache`

## pseudocode

```c

```

## disassembly

```asm
0x79e0  ldarg.0
0x79e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::.ctor()
0x79e6  ldarg.0
0x79e7  ldarg.1
0x79e8  call     instance void Microsoft.VisualStudio.Setup.InstallSize::set_TargetDrive(int64 value)
0x79ed  ldarg.0
0x79ee  ldarg.2
0x79ef  call     instance void Microsoft.VisualStudio.Setup.InstallSize::set_SystemDrive(int64 value)
0x79f4  ldarg.0
0x79f5  ldarg.3
0x79f6  call     instance void Microsoft.VisualStudio.Setup.InstallSize::set_SharedDrive(int64 value)
0x79fb  ldarg.0
0x79fc  ldarg.s  4
0x79fe  call     instance void Microsoft.VisualStudio.Setup.InstallSize::set_CacheSize(int64 value)
0x7a03  ldarg.0
0x7a04  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::.ctor()
0x7a09  dup
0x7a0a  ldstr    aShareddrive// "sharedDrive"
0x7a0f  ldarg.s  7
0x7a11  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::Add(var<u1>, !!T0)
0x7a16  dup
0x7a17  ldstr    aSystemdrive// "systemDrive"
0x7a1c  ldarg.s  6
0x7a1e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::Add(var<u1>, !!T0)
0x7a23  dup
0x7a24  ldstr    aCache// "cache"
0x7a29  ldarg.s  8
0x7a2b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::Add(var<u1>, !!T0)
0x7a30  dup
0x7a31  ldstr    aTargetdrive// "targetDrive"
0x7a36  ldarg.s  5
0x7a38  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::Add(var<u1>, !!T0)
0x7a3d  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> Microsoft.VisualStudio.Setup.InstallSize::<RequestedSizes>k__BackingField
0x7a42  ret
```
