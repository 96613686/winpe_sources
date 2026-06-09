# Microsoft.VisualStudio.Setup.Extensions::Clone

- ea: `0x63a0`
- end: `0x63e6`
- name: `Microsoft.VisualStudio.Setup.Extensions::Clone`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0x14720`
- `0x14740`
- `0x14760`
- `0x14780`
- `0x14790`
- `0x164f0`
- `0x16500`
- `0x16510`
- `0x16520`

## pseudocode

```c

```

## disassembly

```asm
0x63a0  ldarg.0
0x63a1  ldstr    aSeed// "seed"
0x63a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x63ab  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::.ctor()
0x63b0  dup
0x63b1  ldarg.0
0x63b2  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Branch()
0x63b7  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::set_Branch(string value)
0x63bc  dup
0x63bd  ldarg.0
0x63be  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Chip()
0x63c3  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::set_Chip(string value)
0x63c8  dup
0x63c9  ldarg.0
0x63ca  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_MachineArch()
0x63cf  callvirt instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::set_MachineArch(string value)
0x63d4  dup
0x63d5  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::get_Languages()
0x63da  ldarg.0
0x63db  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Languages()
0x63e0  call     T0x2B00002E
0x63e5  ret
```
