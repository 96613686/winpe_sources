# is_stream_flushable_or_commitable(long)

- ea: `0x415a2b`
- end: `0x415a50`
- name: `?is_stream_flushable_or_commitable@@YA_NJ@Z`
- size: `37`
- prototype: `bool __cdecl(__int16)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4159f8`

## callees

- `0x415a2b`

## pseudocode

```c
bool __cdecl is_stream_flushable_or_commitable(__int16 a1)
{
  return (a1 & 3) == 2 && (a1 & 0xC0) != 0 || (a1 & 0x800) != 0;
}

```

## disassembly

```asm
0x415a2b  mov     edi, edi
0x415a2d  push    ebp
0x415a2e  mov     ebp, esp
0x415a30  mov     eax, [ebp+arg_0]
0x415a33  and     al, 3
0x415a35  cmp     al, 2
0x415a37  jnz     short loc_415A3F
0x415a39  test    byte ptr [ebp+arg_0], 0C0h
0x415a3d  jnz     short loc_415A48
0x415a3f  test    [ebp+arg_0], 800h
0x415a46  jz      short loc_415A4C
0x415a48  mov     al, 1
0x415a4a  pop     ebp
0x415a4b  retn
0x415a4c  xor     al, al
0x415a4e  pop     ebp
0x415a4f  retn
```
