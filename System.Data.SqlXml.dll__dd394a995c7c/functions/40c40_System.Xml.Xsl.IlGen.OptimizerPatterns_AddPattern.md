# System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern

- ea: `0x40c40`
- end: `0x40c54`
- name: `System.Xml.Xsl.IlGen.OptimizerPatterns::AddPattern`
- size: `20`
- prototype: ``
- caller_count: `37`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x409c0`
- `0x40a90`
- `0x40af0`
- `0x410a0`
- `0x42b90`
- `0x42c40`
- `0x43020`
- `0x43860`
- `0x43b00`
- `0x43cf0`
- `0x44b30`
- `0x44e60`
- `0x455f0`
- `0x45890`
- `0x45ac0`
- `0x45cf0`
- `0x46190`
- `0x468e0`
- `0x471d0`
- `0x479d0`
- `0x47db0`
- `0x47e50`
- `0x47f30`
- `0x47fd0`
- `0x48070`
- `0x48100`
- `0x48190`
- `0x48210`
- `0x48290`
- `0x48310`
- `0x483b0`
- `0x48440`
- `0x48ad0`
- `0x492f0`
- `0x49380`
- `0x49400`
- `0x4a170`

## pseudocode

```c

```

## disassembly

```asm
0x40c40  ldarg.0
0x40c41  ldarg.0
0x40c42  ldfld    int32 System.Xml.Xsl.IlGen.OptimizerPatterns::patterns
0x40c47  ldc.i4.1
0x40c48  ldarg.1
0x40c49  ldc.i4.s 0x1F
0x40c4b  and
0x40c4c  shl
0x40c4d  or
0x40c4e  stfld    int32 System.Xml.Xsl.IlGen.OptimizerPatterns::patterns
0x40c53  ret
```
