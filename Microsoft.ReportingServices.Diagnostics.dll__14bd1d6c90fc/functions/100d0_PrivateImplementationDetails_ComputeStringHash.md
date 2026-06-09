# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x100d0`
- end: `0x100fc`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x24b0`
- `0x7390`
- `0x77e0`
- `0x7d20`
- `0x8ac0`
- `0x8c50`
- `0xe140`

## callees

- `0x100d0`

## pseudocode

```c

```

## disassembly

```asm
0x100d0  ldarg.0
0x100d1  brfalse.s loc_100FA
0x100d3  ldc.i4   0x811C9DC5
0x100d8  stloc.0
0x100d9  ldc.i4.0
0x100da  stloc.1
0x100db  br.s     loc_100F1
0x100dd  ldarg.0
0x100de  ldloc.1
0x100df  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x100e4  ldloc.0
0x100e5  xor
0x100e6  ldc.i4   0x1000193
0x100eb  mul
0x100ec  stloc.0
0x100ed  ldloc.1
0x100ee  ldc.i4.1
0x100ef  add
0x100f0  stloc.1
0x100f1  ldloc.1
0x100f2  ldarg.0
0x100f3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x100f8  blt.s    loc_100DD
0x100fa  ldloc.0
0x100fb  ret
```
