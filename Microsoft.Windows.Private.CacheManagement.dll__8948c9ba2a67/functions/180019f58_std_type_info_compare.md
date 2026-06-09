# __std_type_info_compare

- ea: `0x180019f58`
- end: `0x180019f6d`
- name: `__std_type_info_compare`
- size: `21`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001bd98`

## callees

- `0x180019f58`
- `0x18001c5d3`

## pseudocode

```c
int __fastcall _std_type_info_compare(__int64 a1, __int64 a2)
{
  if ( a1 == a2 )
    return 0;
  else
    return strcmp_0((const char *)(a1 + 9), (const char *)(a2 + 9));
}

```

## disassembly

```asm
0x180019f58  cmp     rcx, rdx
0x180019f5b  jnz     short loc_180019F60
0x180019f5d  xor     eax, eax
0x180019f5f  retn
0x180019f60  add     rdx, 9; Str2
0x180019f64  add     rcx, 9; Str1
0x180019f68  jmp     strcmp_0
```
