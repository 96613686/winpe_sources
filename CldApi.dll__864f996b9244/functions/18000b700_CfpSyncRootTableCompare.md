# CfpSyncRootTableCompare

- ea: `0x18000b700`
- end: `0x18000b717`
- name: `CfpSyncRootTableCompare`
- size: `23`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000b700`

## pseudocode

```c
__int64 __fastcall CfpSyncRootTableCompare(struct _RTL_AVL_TABLE *Table, _QWORD *FirstStruct, _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x18000b700  mov     rcx, [r8]
0x18000b703  cmp     [rdx], rcx
0x18000b706  jnz     short loc_18000B70E
0x18000b708  mov     eax, 2
0x18000b70d  retn
0x18000b70e  xor     eax, eax
0x18000b710  cmp     [rdx], rcx
0x18000b713  setnle  al
0x18000b716  retn
```
