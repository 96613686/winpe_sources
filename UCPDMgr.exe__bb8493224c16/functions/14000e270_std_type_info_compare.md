# __std_type_info_compare

- ea: `0x14000e270`
- end: `0x14000e285`
- name: `__std_type_info_compare`
- size: `21`
- prototype: `int __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000dd64`

## callees

- `0x14000e270`
- `0x14000e376`

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
0x14000e270  cmp     rcx, rdx
0x14000e273  jnz     short loc_14000E278
0x14000e275  xor     eax, eax
0x14000e277  retn
0x14000e278  add     rdx, 9; Str2
0x14000e27c  add     rcx, 9; Str1
0x14000e280  jmp     strcmp_0
```
