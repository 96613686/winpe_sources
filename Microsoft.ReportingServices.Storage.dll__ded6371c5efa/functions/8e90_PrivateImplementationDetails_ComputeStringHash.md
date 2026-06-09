# <PrivateImplementationDetails>::ComputeStringHash

- ea: `0x8e90`
- end: `0x8ebc`
- name: `<PrivateImplementationDetails>::ComputeStringHash`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2990`

## callees

- `0x8e90`

## pseudocode

```c

```

## disassembly

```asm
0x8e90  ldarg.0
0x8e91  brfalse.s loc_8EBA
0x8e93  ldc.i4   0x811C9DC5
0x8e98  stloc.0
0x8e99  ldc.i4.0
0x8e9a  stloc.1
0x8e9b  br.s     loc_8EB1
0x8e9d  ldarg.0
0x8e9e  ldloc.1
0x8e9f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x8ea4  ldloc.0
0x8ea5  xor
0x8ea6  ldc.i4   0x1000193
0x8eab  mul
0x8eac  stloc.0
0x8ead  ldloc.1
0x8eae  ldc.i4.1
0x8eaf  add
0x8eb0  stloc.1
0x8eb1  ldloc.1
0x8eb2  ldarg.0
0x8eb3  callvirt instance int32 [mscorlib]System.String::get_Length()
0x8eb8  blt.s    loc_8E9D
0x8eba  ldloc.0
0x8ebb  ret
```
