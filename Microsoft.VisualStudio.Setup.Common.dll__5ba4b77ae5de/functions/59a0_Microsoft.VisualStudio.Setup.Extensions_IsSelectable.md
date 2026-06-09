# Microsoft.VisualStudio.Setup.Extensions::IsSelectable

- ea: `0x59a0`
- end: `0x59c9`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsSelectable`
- size: `41`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5a40`
- `0x152f0`
- `0x15460`
- `0x173e0`
- `0x1d170`
- `0x1d200`

## callees

- `0x59a0`
- `0x7ee0`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x59a0  ldarg.0
0x59a1  ldstr    aPackage// "package"
0x59a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x59ab  ldarg.0
0x59ac  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x59b1  ldc.i4.6
0x59b2  beq.s    loc_59C7
0x59b4  ldarg.0
0x59b5  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x59ba  ldc.i4.7
0x59bb  beq.s    loc_59C7
0x59bd  ldarg.0
0x59be  callvirt instance valuetype Microsoft.VisualStudio.Setup.PackageType Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x59c3  ldc.i4.8
0x59c4  ceq
0x59c6  ret
0x59c7  ldc.i4.1
0x59c8  ret
```
