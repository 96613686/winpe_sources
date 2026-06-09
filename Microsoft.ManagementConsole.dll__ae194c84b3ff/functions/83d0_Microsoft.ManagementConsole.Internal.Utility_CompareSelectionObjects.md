# Microsoft.ManagementConsole.Internal.Utility::CompareSelectionObjects

- ea: `0x83d0`
- end: `0x840e`
- name: `Microsoft.ManagementConsole.Internal.Utility::CompareSelectionObjects`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xdc90`
- `0xe9b0`

## callees

- `0x83d0`

## pseudocode

```c

```

## disassembly

```asm
0x83d0  ldc.i4.0
0x83d1  stloc.0
0x83d2  ldarg.0
0x83d3  isinst   [mscorlib]System.IComparable
0x83d8  brfalse.s loc_83EC
0x83da  ldarg.0
0x83db  castclass [mscorlib]System.IComparable
0x83e0  ldarg.1
0x83e1  callvirt instance int32 [mscorlib]System.IComparable::CompareTo(object)
0x83e6  brtrue.s loc_840C
0x83e8  ldc.i4.1
0x83e9  stloc.0
0x83ea  br.s     loc_840C
0x83ec  ldarg.1
0x83ed  isinst   [mscorlib]System.IComparable
0x83f2  brfalse.s loc_8406
0x83f4  ldarg.1
0x83f5  castclass [mscorlib]System.IComparable
0x83fa  ldarg.0
0x83fb  callvirt instance int32 [mscorlib]System.IComparable::CompareTo(object)
0x8400  brtrue.s loc_840C
0x8402  ldc.i4.1
0x8403  stloc.0
0x8404  br.s     loc_840C
0x8406  ldarg.0
0x8407  ldarg.1
0x8408  bne.un.s loc_840C
0x840a  ldc.i4.1
0x840b  stloc.0
0x840c  ldloc.0
0x840d  ret
```
