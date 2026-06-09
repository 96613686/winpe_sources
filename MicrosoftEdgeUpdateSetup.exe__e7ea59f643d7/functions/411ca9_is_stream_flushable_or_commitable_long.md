# is_stream_flushable_or_commitable(long)

- ea: `0x411ca9`
- end: `0x411cce`
- name: `?is_stream_flushable_or_commitable@@YA_NJ@Z`
- size: `37`
- prototype: `bool __cdecl(__int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x411c76`

## callees

- `0x411ca9`

## pseudocode

```c
bool __cdecl is_stream_flushable_or_commitable(__int16 a1)
{
  return (a1 & 3) == 2 && (a1 & 0xC0) != 0 || (a1 & 0x800) != 0;
}

```

## disassembly

```asm
0x411ca9  mov     edi, edi
0x411cab  push    ebp
0x411cac  mov     ebp, esp
0x411cae  mov     eax, [ebp+arg_0]
0x411cb1  and     al, 3
0x411cb3  cmp     al, 2
0x411cb5  jnz     short loc_411CBD
0x411cb7  test    byte ptr [ebp+arg_0], 0C0h
0x411cbb  jnz     short loc_411CC6
0x411cbd  test    [ebp+arg_0], 800h
0x411cc4  jz      short loc_411CCA
0x411cc6  mov     al, 1
0x411cc8  pop     ebp
0x411cc9  retn
0x411cca  xor     al, al
0x411ccc  pop     ebp
0x411ccd  retn
```
