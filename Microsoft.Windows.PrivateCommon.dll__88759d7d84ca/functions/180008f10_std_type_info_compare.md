# __std_type_info_compare

- ea: `0x180008f10`
- end: `0x180008f25`
- name: `__std_type_info_compare`
- size: `21`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000adb8`

## callees

- `0x180008f10`
- `0x18000b616`

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
0x180008f10  cmp     rcx, rdx
0x180008f13  jnz     short loc_180008F18
0x180008f15  xor     eax, eax
0x180008f17  retn
0x180008f18  add     rdx, 9; Str2
0x180008f1c  add     rcx, 9; Str1
0x180008f20  jmp     strcmp_0
```
