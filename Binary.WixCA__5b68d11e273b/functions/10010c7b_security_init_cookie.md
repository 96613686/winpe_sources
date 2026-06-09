# ___security_init_cookie

- ea: `0x10010c7b`
- end: `0x10010cc6`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x10010a51`

## callees

- `0x10010c2e`
- `0x10010c7b`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // ecx
  unsigned int entropy; // eax

  v0 = __security_cookie;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    entropy = __get_entropy();
    v0 = entropy;
    if ( entropy == -1153374642 )
    {
      v0 = -1153374641;
    }
    else if ( (entropy & 0xFFFF0000) == 0 )
    {
      v0 = ((entropy | 0x4711) << 16) | entropy;
    }
    __security_cookie = v0;
  }
  dword_10033040 = ~v0;
}

```

## disassembly

```asm
0x10010c7b  mov     ecx, ___security_cookie
0x10010c81  push    esi
0x10010c82  push    edi
0x10010c83  mov     edi, 0BB40E64Eh
0x10010c88  mov     esi, 0FFFF0000h
0x10010c8d  cmp     ecx, edi
0x10010c8f  jz      short loc_10010C95
0x10010c91  test    esi, ecx
0x10010c93  jnz     short loc_10010CBB
0x10010c95  call    ___get_entropy
0x10010c9a  mov     ecx, eax
0x10010c9c  cmp     ecx, edi
0x10010c9e  jnz     short loc_10010CA7
0x10010ca0  mov     ecx, 0BB40E64Fh
0x10010ca5  jmp     short loc_10010CB5
0x10010ca7  test    esi, ecx
0x10010ca9  jnz     short loc_10010CB5
0x10010cab  or      eax, 4711h
0x10010cb0  shl     eax, 10h
0x10010cb3  or      ecx, eax
0x10010cb5  mov     ___security_cookie, ecx
0x10010cbb  not     ecx
0x10010cbd  pop     edi
0x10010cbe  mov     dword_10033040, ecx
0x10010cc4  pop     esi
0x10010cc5  retn
```
