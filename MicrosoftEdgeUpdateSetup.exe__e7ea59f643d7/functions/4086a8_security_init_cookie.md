# ___security_init_cookie

- ea: `0x4086a8`
- end: `0x4086f3`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x408400`

## callees

- `0x40865b`
- `0x4086a8`

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
  dword_426014 = ~v0;
}

```

## disassembly

```asm
0x4086a8  mov     ecx, ___security_cookie
0x4086ae  push    esi
0x4086af  push    edi
0x4086b0  mov     edi, 0BB40E64Eh
0x4086b5  mov     esi, 0FFFF0000h
0x4086ba  cmp     ecx, edi
0x4086bc  jz      short loc_4086C2
0x4086be  test    esi, ecx
0x4086c0  jnz     short loc_4086E8
0x4086c2  call    ___get_entropy
0x4086c7  mov     ecx, eax
0x4086c9  cmp     ecx, edi
0x4086cb  jnz     short loc_4086D4
0x4086cd  mov     ecx, 0BB40E64Fh
0x4086d2  jmp     short loc_4086E2
0x4086d4  test    esi, ecx
0x4086d6  jnz     short loc_4086E2
0x4086d8  or      eax, 4711h
0x4086dd  shl     eax, 10h
0x4086e0  or      ecx, eax
0x4086e2  mov     ___security_cookie, ecx
0x4086e8  not     ecx
0x4086ea  pop     edi
0x4086eb  mov     dword_426014, ecx
0x4086f1  pop     esi
0x4086f2  retn
```
