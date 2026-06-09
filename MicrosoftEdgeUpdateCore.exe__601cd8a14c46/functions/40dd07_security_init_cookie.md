# ___security_init_cookie

- ea: `0x40dd07`
- end: `0x40dd52`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40d740`

## callees

- `0x40dcba`
- `0x40dd07`

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
  dword_43D008 = ~v0;
}

```

## disassembly

```asm
0x40dd07  mov     ecx, ___security_cookie
0x40dd0d  push    esi
0x40dd0e  push    edi
0x40dd0f  mov     edi, 0BB40E64Eh
0x40dd14  mov     esi, 0FFFF0000h
0x40dd19  cmp     ecx, edi
0x40dd1b  jz      short loc_40DD21
0x40dd1d  test    esi, ecx
0x40dd1f  jnz     short loc_40DD47
0x40dd21  call    ___get_entropy
0x40dd26  mov     ecx, eax
0x40dd28  cmp     ecx, edi
0x40dd2a  jnz     short loc_40DD33
0x40dd2c  mov     ecx, 0BB40E64Fh
0x40dd31  jmp     short loc_40DD41
0x40dd33  test    esi, ecx
0x40dd35  jnz     short loc_40DD41
0x40dd37  or      eax, 4711h
0x40dd3c  shl     eax, 10h
0x40dd3f  or      ecx, eax
0x40dd41  mov     ___security_cookie, ecx
0x40dd47  not     ecx
0x40dd49  pop     edi
0x40dd4a  mov     dword_43D008, ecx
0x40dd50  pop     esi
0x40dd51  retn
```
