# _invalid_parameter_noinfo

- ea: `0x18000fcc0`
- end: `0x18000fcde`
- name: `_invalid_parameter_noinfo`
- size: `30`
- prototype: `void __cdecl()`
- caller_count: `54`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f650`
- `0x18000f710`
- `0x180010398`
- `0x18001064c`
- `0x1800150a8`
- `0x180015844`
- `0x1800162e4`
- `0x18001638c`
- `0x180016434`
- `0x180017ddc`
- `0x1800187e4`
- `0x180018880`
- `0x180018924`
- `0x180018b00`
- `0x1800194ac`
- `0x18001b7a0`
- `0x18001c518`
- `0x18001c58c`
- `0x18001c6a4`
- `0x18001c7d0`
- `0x18001c9f4`
- `0x18001ca9c`
- `0x18001cb3c`
- `0x18001d908`
- `0x18001da74`
- `0x18001e228`
- `0x18001e2fc`
- `0x18001e3c8`
- `0x18001e4a0`
- `0x18001e50c`
- `0x18001e574`
- `0x18001f7b8`
- `0x180020610`
- `0x180022330`
- `0x180022e60`
- `0x180024d2c`
- `0x180025928`
- `0x180027cb0`
- `0x180027d40`
- `0x180027dd0`
- `0x180027f10`
- `0x18002a640`
- `0x18002b570`
- `0x18002b77c`
- `0x18002cbb4`
- `0x18002cd0c`
- `0x18002cec0`
- `0x18002d520`
- `0x18002d650`
- `0x18002de50`

## callees

- `0x18000fb6c`

## pseudocode

```c
void __cdecl invalid_parameter_noinfo()
{
  sub_18000FB6C(0, 0, 0, 0, 0);
}

```

## disassembly

```asm
0x18000fcc0  sub     rsp, 38h
0x18000fcc4  and     [rsp+38h+var_18], 0
0x18000fcca  xor     r9d, r9d
0x18000fccd  xor     r8d, r8d
0x18000fcd0  xor     edx, edx
0x18000fcd2  xor     ecx, ecx
0x18000fcd4  call    sub_18000FB6C
0x18000fcd9  add     rsp, 38h
0x18000fcdd  retn
```
