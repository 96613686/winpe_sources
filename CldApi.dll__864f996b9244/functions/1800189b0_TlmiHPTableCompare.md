# TlmiHPTableCompare

- ea: `0x1800189b0`
- end: `0x1800189c7`
- name: `TlmiHPTableCompare`
- size: `23`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800189b0`

## pseudocode

```c
__int64 __fastcall TlmiHPTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x1800189b0  mov     rcx, [rdx]
0x1800189b3  cmp     rcx, [r8]
0x1800189b6  jnz     short loc_1800189BE
0x1800189b8  mov     eax, 2
0x1800189bd  retn
0x1800189be  xor     eax, eax
0x1800189c0  cmp     rcx, [r8]
0x1800189c3  setnle  al
0x1800189c6  retn
```
