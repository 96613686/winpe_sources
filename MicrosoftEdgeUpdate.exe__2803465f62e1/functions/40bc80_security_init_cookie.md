# ___security_init_cookie

- ea: `0x40bc80`
- end: `0x40bccb`
- name: `___security_init_cookie`
- size: `75`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x40b880`

## callees

- `0x40bc33`
- `0x40bc80`

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
  dword_417000 = ~v0;
}

```

## disassembly

```asm
0x40bc80  mov     ecx, ___security_cookie
0x40bc86  push    esi
0x40bc87  push    edi
0x40bc88  mov     edi, 0BB40E64Eh
0x40bc8d  mov     esi, 0FFFF0000h
0x40bc92  cmp     ecx, edi
0x40bc94  jz      short loc_40BC9A
0x40bc96  test    esi, ecx
0x40bc98  jnz     short loc_40BCC0
0x40bc9a  call    ___get_entropy
0x40bc9f  mov     ecx, eax
0x40bca1  cmp     ecx, edi
0x40bca3  jnz     short loc_40BCAC
0x40bca5  mov     ecx, 0BB40E64Fh
0x40bcaa  jmp     short loc_40BCBA
0x40bcac  test    esi, ecx
0x40bcae  jnz     short loc_40BCBA
0x40bcb0  or      eax, 4711h
0x40bcb5  shl     eax, 10h
0x40bcb8  or      ecx, eax
0x40bcba  mov     ___security_cookie, ecx
0x40bcc0  not     ecx
0x40bcc2  pop     edi
0x40bcc3  mov     dword_417000, ecx
0x40bcc9  pop     esi
0x40bcca  retn
```
