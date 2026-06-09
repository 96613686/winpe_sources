# Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken

- ea: `0x10900`
- end: `0x10929`
- name: `Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken`
- size: `41`
- prototype: ``
- caller_count: `10`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x4970`
- `0xa570`
- `0xa800`
- `0xa980`
- `0xac00`
- `0xd570`
- `0xe810`
- `0x142e0`
- `0x14650`
- `0x16040`

## callees

- `0x10900`

## pseudocode

```c

```

## disassembly

```asm
0x10900  ldarg.0
0x10901  brtrue.s loc_10905
0x10903  ldnull
0x10904  ret
0x10905  ldsfld   string[] Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MatchAnythingTokens
0x1090a  stloc.0
0x1090b  ldc.i4.0
0x1090c  stloc.1
0x1090d  br.s     loc_10921
0x1090f  ldloc.0
0x10910  ldloc.1
0x10911  ldelem.ref
0x10912  ldarg.0
0x10913  ldc.i4.5
0x10914  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x10919  brfalse.s loc_1091D
0x1091b  ldnull
0x1091c  ret
0x1091d  ldloc.1
0x1091e  ldc.i4.1
0x1091f  add
0x10920  stloc.1
0x10921  ldloc.1
0x10922  ldloc.0
0x10923  ldlen
0x10924  conv.i4
0x10925  blt.s    loc_1090F
0x10927  ldarg.0
0x10928  ret
```
