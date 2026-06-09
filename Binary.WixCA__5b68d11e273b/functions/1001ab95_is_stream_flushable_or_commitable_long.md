# is_stream_flushable_or_commitable(long)

- ea: `0x1001ab95`
- end: `0x1001abba`
- name: `?is_stream_flushable_or_commitable@@YA_NJ@Z`
- size: `37`
- prototype: `bool __cdecl(int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1001ab62`

## callees

- `0x1001ab95`

## pseudocode

```c
bool __cdecl is_stream_flushable_or_commitable(__int16 a1)
{
  return (a1 & 3) == 2 && (a1 & 0xC0) != 0 || (a1 & 0x800) != 0;
}

```

## disassembly

```asm
0x1001ab95  mov     edi, edi
0x1001ab97  push    ebp
0x1001ab98  mov     ebp, esp
0x1001ab9a  mov     eax, [ebp+arg_0]
0x1001ab9d  and     al, 3
0x1001ab9f  cmp     al, 2
0x1001aba1  jnz     short loc_1001ABA9
0x1001aba3  test    byte ptr [ebp+arg_0], 0C0h
0x1001aba7  jnz     short loc_1001ABB2
0x1001aba9  test    [ebp+arg_0], 800h
0x1001abb0  jz      short loc_1001ABB6
0x1001abb2  mov     al, 1
0x1001abb4  pop     ebp
0x1001abb5  retn
0x1001abb6  xor     al, al
0x1001abb8  pop     ebp
0x1001abb9  retn
```
