# __std_type_info_compare

- ea: `0x1800146e0`
- end: `0x1800146f5`
- name: `__std_type_info_compare`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800141dc`

## callees

- `0x1800146e0`
- `0x180015108`

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
0x1800146e0  cmp     rcx, rdx
0x1800146e3  jnz     short loc_1800146E8
0x1800146e5  xor     eax, eax
0x1800146e7  retn
0x1800146e8  add     rdx, 9; Str2
0x1800146ec  add     rcx, 9; Str1
0x1800146f0  jmp     strcmp_0
```
