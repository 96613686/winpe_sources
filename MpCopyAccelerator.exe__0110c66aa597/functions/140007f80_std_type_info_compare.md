# __std_type_info_compare

- ea: `0x140007f80`
- end: `0x140007f95`
- name: `__std_type_info_compare`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b000`

## callees

- `0x140007f80`
- `0x1400257b0`

## pseudocode

```c
int __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  if ( a1 == a2 )
    return 0;
  else
    return strcmp((const char *)(a1 + 9), (const char *)(a2 + 9));
}

```

## disassembly

```asm
0x140007f80  cmp     rcx, rdx
0x140007f83  jnz     short loc_140007F88
0x140007f85  xor     eax, eax
0x140007f87  retn
0x140007f88  add     rdx, 9; Str2
0x140007f8c  add     rcx, 9; Str1
0x140007f90  jmp     strcmp
```
