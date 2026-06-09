# CfpOplockCompletionKeyTableCompare

- ea: `0x1800046d0`
- end: `0x1800046e7`
- name: `CfpOplockCompletionKeyTableCompare`
- size: `23`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800046d0`

## pseudocode

```c
__int64 __fastcall CfpOplockCompletionKeyTableCompare(
        struct _RTL_AVL_TABLE *Table,
        _QWORD *FirstStruct,
        _QWORD *SecondStruct)
{
  if ( *FirstStruct == *SecondStruct )
    return 2;
  else
    return *FirstStruct > *SecondStruct;
}

```

## disassembly

```asm
0x1800046d0  mov     rcx, [r8]
0x1800046d3  cmp     [rdx], rcx
0x1800046d6  jnz     short loc_1800046DE
0x1800046d8  mov     eax, 2
0x1800046dd  retn
0x1800046de  xor     eax, eax
0x1800046e0  cmp     [rdx], rcx
0x1800046e3  setnbe  al
0x1800046e6  retn
```
