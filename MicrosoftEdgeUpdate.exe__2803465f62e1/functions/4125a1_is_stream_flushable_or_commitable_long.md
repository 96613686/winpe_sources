# is_stream_flushable_or_commitable(long)

- ea: `0x4125a1`
- end: `0x4125c6`
- name: `?is_stream_flushable_or_commitable@@YA_NJ@Z`
- size: `37`
- prototype: `bool __cdecl(__int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x41256e`

## callees

- `0x4125a1`

## pseudocode

```c
bool __cdecl is_stream_flushable_or_commitable(__int16 a1)
{
  return (a1 & 3) == 2 && (a1 & 0xC0) != 0 || (a1 & 0x800) != 0;
}

```

## disassembly

```asm
0x4125a1  mov     edi, edi
0x4125a3  push    ebp
0x4125a4  mov     ebp, esp
0x4125a6  mov     eax, [ebp+arg_0]
0x4125a9  and     al, 3
0x4125ab  cmp     al, 2
0x4125ad  jnz     short loc_4125B5
0x4125af  test    byte ptr [ebp+arg_0], 0C0h
0x4125b3  jnz     short loc_4125BE
0x4125b5  test    [ebp+arg_0], 800h
0x4125bc  jz      short loc_4125C2
0x4125be  mov     al, 1
0x4125c0  pop     ebp
0x4125c1  retn
0x4125c2  xor     al, al
0x4125c4  pop     ebp
0x4125c5  retn
```
