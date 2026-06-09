# Microsoft.VisualStudio.Setup.Extensions::IsExperimentRoot

- ea: `0x58c0`
- end: `0x58f4`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsExperimentRoot`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x16d00`

## callees

- `0x58c0`
- `0x80d0`
- `0x8300`
- `0x98f0`
- `0xc1a0`

## pseudocode

```c

```

## disassembly

```asm
0x58c0  ldarg.0
0x58c1  ldstr    aPackage// "package"
0x58c6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x58cb  ldarg.0
0x58cc  isinst   Microsoft.VisualStudio.Setup.IRootPackage
0x58d1  stloc.0
0x58d2  ldloc.0
0x58d3  brfalse.s loc_58F2
0x58d5  ldloc.0
0x58d6  callvirt instance bool Microsoft.VisualStudio.Setup.IRootPackage::get_IsRoot()
0x58db  brfalse.s loc_58F2
0x58dd  ldloc.0
0x58de  callvirt instance class Microsoft.VisualStudio.Setup.OriginInfo Microsoft.VisualStudio.Setup.IPackage::get_Origin()
0x58e3  dup
0x58e4  brtrue.s loc_58E9
0x58e6  pop
0x58e7  ldc.i4.0
0x58e8  ret
0x58e9  call     instance valuetype Microsoft.VisualStudio.Setup.PartialManifestType Microsoft.VisualStudio.Setup.OriginInfo::get_ManifestType()
0x58ee  ldc.i4.1
0x58ef  ceq
0x58f1  ret
0x58f2  ldc.i4.0
0x58f3  ret
```
