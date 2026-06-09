# Microsoft.VisualStudio.Setup.Extensions::AdjustVersionRangeForPriorTarget

- ea: `0x6640`
- end: `0x6663`
- name: `Microsoft.VisualStudio.Setup.Extensions::AdjustVersionRangeForPriorTarget`
- size: `35`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x142e0`

## callees

- `0x6670`
- `0xc410`
- `0xc4b0`
- `0xc4d0`
- `0xc4f0`
- `0xc510`

## pseudocode

```c

```

## disassembly

```asm
0x6640  ldarg.0
0x6641  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.VersionRange::get_Minimum()
0x6646  ldarg.0
0x6647  callvirt instance bool Microsoft.VisualStudio.Setup.VersionRange::get_IsMinimumInclusive()
0x664c  ldarg.0
0x664d  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.VersionRange::get_Maximum()
0x6652  call     class [mscorlib]System.Version Microsoft.VisualStudio.Setup.Extensions::GetAdjustedMaxVersion(class [mscorlib]System.Version maxVersion)
0x6657  ldarg.0
0x6658  callvirt instance bool Microsoft.VisualStudio.Setup.VersionRange::get_IsMaximumInclusive()
0x665d  newobj   instance void Microsoft.VisualStudio.Setup.VersionRange::.ctor(class [mscorlib]System.Version minimum, bool isMinimumInclusive, class [mscorlib]System.Version maximum, bool isMaximumInclusive)
0x6662  ret
```
