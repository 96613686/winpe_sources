# write_double_translated_unicode_nolock(char const * const,uint)

- ea: `0x418b76`
- end: `0x418bde`
- name: `?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z`
- size: `104`
- prototype: `DWORD *__cdecl(DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x419037`

## callees

- `0x418b76`
- `0x41b258`

## import_xrefs

- `KERNEL32!GetLastError` at `0x418bcf`
- `KERNEL32!GetLastError` at `0x418bcf`

## pseudocode

```c
DWORD *__cdecl write_double_translated_unicode_nolock(DWORD *a1, unsigned int a2, int a3)
{
  wchar_t *v3; // edi
  int v4; // ebx

  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v3 = (wchar_t *)a2;
  if ( a2 < a2 + a3 )
  {
    while ( 1 )
    {
      v4 = *v3;
      if ( _putwch_nolock(*v3) != (_WORD)v4 )
        break;
      a1[1] += 2;
      if ( v4 == 10 )
      {
        if ( _putwch_nolock(0xDu) != 13 )
          break;
        ++a1[1];
        ++a1[2];
      }
      if ( (unsigned int)++v3 >= a2 + a3 )
        return a1;
    }
    *a1 = GetLastError();
  }
  return a1;
}

```

## disassembly

```asm
0x418b76  mov     edi, edi
0x418b78  push    ebp
0x418b79  mov     ebp, esp
0x418b7b  push    ecx
0x418b7c  push    ebx
0x418b7d  push    esi
0x418b7e  mov     esi, [ebp+arg_0]
0x418b81  xor     eax, eax
0x418b83  push    edi
0x418b84  mov     edi, esi
0x418b86  stosd
0x418b87  stosd
0x418b88  stosd
0x418b89  mov     edi, [ebp+arg_4]
0x418b8c  mov     eax, [ebp+arg_8]
0x418b8f  add     eax, edi
0x418b91  mov     [ebp+var_4], eax
0x418b94  cmp     edi, eax
0x418b96  jnb     short loc_418BD7
0x418b98  movzx   ebx, word ptr [edi]
0x418b9b  push    ebx; Character
0x418b9c  call    __putwch_nolock
0x418ba1  pop     ecx
0x418ba2  cmp     ax, bx
0x418ba5  jnz     short loc_418BCF
0x418ba7  add     dword ptr [esi+4], 2
0x418bab  cmp     ebx, 0Ah
0x418bae  jnz     short loc_418BC5
0x418bb0  push    0Dh
0x418bb2  pop     ebx
0x418bb3  push    ebx; Character
0x418bb4  call    __putwch_nolock
0x418bb9  pop     ecx
0x418bba  cmp     ax, bx
0x418bbd  jnz     short loc_418BCF
0x418bbf  inc     dword ptr [esi+4]
0x418bc2  inc     dword ptr [esi+8]
0x418bc5  add     edi, 2
0x418bc8  cmp     edi, [ebp+var_4]
0x418bcb  jb      short loc_418B98
0x418bcd  jmp     short loc_418BD7
0x418bcf  call    ds:GetLastError
0x418bd5  mov     [esi], eax
0x418bd7  pop     edi
0x418bd8  mov     eax, esi
0x418bda  pop     esi
0x418bdb  pop     ebx
0x418bdc  leave
0x418bdd  retn
```
