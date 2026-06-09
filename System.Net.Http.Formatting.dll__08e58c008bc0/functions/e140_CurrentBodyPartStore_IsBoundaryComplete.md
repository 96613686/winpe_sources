# CurrentBodyPartStore::IsBoundaryComplete

- ea: `0xe140`
- end: `0xe17f`
- name: `CurrentBodyPartStore::IsBoundaryComplete`
- size: `63`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xabb0`

## callees

- `0xe0b0`
- `0xe140`

## pseudocode

```c

```

## disassembly

```asm
0xe140  ldarg.0
0xe141  call     instance bool CurrentBodyPartStore::IsBoundaryValid()
0xe146  brtrue.s loc_E14A
0xe148  ldc.i4.0
0xe149  ret
0xe14a  ldarg.0
0xe14b  ldfld    int32 CurrentBodyPartStore::_boundaryLength
0xe150  ldarg.0
0xe151  ldfld    int32 CurrentBodyPartStore::_referenceBoundaryLength
0xe156  bge.s    loc_E15A
0xe158  ldc.i4.0
0xe159  ret
0xe15a  ldarg.0
0xe15b  ldfld    int32 CurrentBodyPartStore::_boundaryLength
0xe160  ldarg.0
0xe161  ldfld    int32 CurrentBodyPartStore::_referenceBoundaryLength
0xe166  ldc.i4.1
0xe167  add
0xe168  bne.un.s loc_E17D
0xe16a  ldarg.0
0xe16b  ldfld    unsigned int8[] CurrentBodyPartStore::_boundary
0xe170  ldarg.0
0xe171  ldfld    int32 CurrentBodyPartStore::_referenceBoundaryLength
0xe176  ldelem.u1
0xe177  ldc.i4.s 0x2D
0xe179  bne.un.s loc_E17D
0xe17b  ldc.i4.0
0xe17c  ret
0xe17d  ldc.i4.1
0xe17e  ret
```
