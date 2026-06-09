# <>c::<RecordUpdateInformation>b__2_1

- ea: `0x5ba0`
- end: `0x5bb8`
- name: `<>c::<RecordUpdateInformation>b__2_1`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x5ba0`

## pseudocode

```c

```

## disassembly

```asm
0x5ba0  ldarg.1
0x5ba1  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x5ba6  ldc.i4.6
0x5ba7  bne.un.s loc_5BB6
0x5ba9  ldarg.1
0x5baa  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_CurrentState()
0x5baf  ldc.i4.2
0x5bb0  ceq
0x5bb2  ldc.i4.0
0x5bb3  ceq
0x5bb5  ret
0x5bb6  ldc.i4.0
0x5bb7  ret
```
