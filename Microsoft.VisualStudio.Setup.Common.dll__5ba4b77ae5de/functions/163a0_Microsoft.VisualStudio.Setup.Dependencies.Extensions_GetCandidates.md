# Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetCandidates

- ea: `0x163a0`
- end: `0x163c1`
- name: `Microsoft.VisualStudio.Setup.Dependencies.Extensions::GetCandidates`
- size: `33`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x16c00`
- `0x175f0`
- `0x17660`
- `0x17890`

## callees

- `0xc1a0`
- `0x163a0`
- `0x166a0`

## pseudocode

```c

```

## disassembly

```asm
0x163a0  ldarg.0
0x163a1  ldstr    aNode// "node"
0x163a6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x163ab  ldarg.0
0x163ac  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyList`1<class Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Dependencies.IDependencyNode::get_CandidatePackageIds()
0x163b1  stloc.0
0x163b2  ldarg.1
0x163b3  brtrue.s loc_163B9
0x163b5  ldloc.0
0x163b6  stloc.1
0x163b7  ldloc.1
0x163b8  ret
0x163b9  ldloc.0
0x163ba  ldarg.1
0x163bb  call     T0x2B000013
0x163c0  ret
```
