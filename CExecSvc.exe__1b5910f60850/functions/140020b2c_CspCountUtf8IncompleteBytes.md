# CspCountUtf8IncompleteBytes

- ea: `0x140020b2c`
- end: `0x140020ba2`
- name: `CspCountUtf8IncompleteBytes`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140021484`
- `0x1400219e4`

## callees

- `0x140020b2c`

## pseudocode

```c
__int64 __fastcall CspCountUtf8IncompleteBytes(__int64 a1)
{
  unsigned int v1; // edx
  unsigned int v2; // r8d
  char v3; // cl

  v1 = 0;
  v2 = 1;
  if ( (*(_BYTE *)(a1 + 511) & 0xC0) == 0x80 )
  {
    while ( ++v1 <= 3 )
    {
      if ( (*(_BYTE *)(511 - v1 + a1) & 0xC0) != 0x80 )
        goto LABEL_4;
    }
    return 0;
  }
LABEL_4:
  v3 = *(_BYTE *)(511 - v1 + a1);
  if ( v3 < 0 )
  {
    if ( (v3 & 0xE0) != 0xC0 )
    {
      if ( (v3 & 0xF0) == 0xE0 )
      {
        v2 = 2;
      }
      else
      {
        if ( (v3 & 0xF8) != 0xF0 )
          return 0;
        v2 = 3;
      }
    }
    if ( v1 < v2 )
      return v1 + 1;
  }
  return 0;
}

```

## disassembly

```asm
0x140020b2c  mov     al, [rcx+1FFh]
0x140020b32  xor     edx, edx
0x140020b34  mov     r11b, 0C0h
0x140020b37  mov     r10, rcx
0x140020b3a  and     al, r11b
0x140020b3d  mov     r9d, 1FFh
0x140020b43  lea     r8d, [rdx+1]
0x140020b47  cmp     al, 80h
0x140020b49  jnz     short loc_140020B64
0x140020b4b  add     edx, r8d
0x140020b4e  cmp     edx, 3
0x140020b51  ja      short loc_140020B9F
0x140020b53  mov     eax, r9d
0x140020b56  sub     eax, edx
0x140020b58  mov     cl, [rax+r10]
0x140020b5c  and     cl, r11b
0x140020b5f  cmp     cl, 80h
0x140020b62  jz      short loc_140020B4B
0x140020b64  sub     r9d, edx
0x140020b67  mov     cl, [r9+r10]
0x140020b6b  test    cl, cl
0x140020b6d  jns     short loc_140020B9F
0x140020b6f  mov     al, cl
0x140020b71  and     al, 0E0h
0x140020b73  cmp     al, r11b
0x140020b76  jz      short loc_140020B96
0x140020b78  mov     al, cl
0x140020b7a  and     al, 0F0h
0x140020b7c  cmp     al, 0E0h
0x140020b7e  jnz     short loc_140020B88
0x140020b80  mov     r8d, 2
0x140020b86  jmp     short loc_140020B96
0x140020b88  and     cl, 0F8h
0x140020b8b  cmp     cl, 0F0h
0x140020b8e  jnz     short loc_140020B9F
0x140020b90  mov     r8d, 3
0x140020b96  cmp     edx, r8d
0x140020b99  jnb     short loc_140020B9F
0x140020b9b  lea     eax, [rdx+1]
0x140020b9e  retn
0x140020b9f  xor     eax, eax
0x140020ba1  retn
```
