# write_double_translated_unicode_nolock(char const * const,uint)

- ea: `0x4141b1`
- end: `0x414219`
- name: `?write_double_translated_unicode_nolock@@YA?AUwrite_result@?A0x17268360@@QBDI@Z`
- size: `104`
- prototype: `DWORD *__cdecl(DWORD *, unsigned int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x414672`

## callees

- `0x4141b1`
- `0x4168f8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x41420a`
- `KERNEL32!GetLastError` at `0x41420a`

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
0x4141b1  mov     edi, edi
0x4141b3  push    ebp
0x4141b4  mov     ebp, esp
0x4141b6  push    ecx
0x4141b7  push    ebx
0x4141b8  push    esi
0x4141b9  mov     esi, [ebp+arg_0]
0x4141bc  xor     eax, eax
0x4141be  push    edi
0x4141bf  mov     edi, esi
0x4141c1  stosd
0x4141c2  stosd
0x4141c3  stosd
0x4141c4  mov     edi, [ebp+arg_4]
0x4141c7  mov     eax, [ebp+arg_8]
0x4141ca  add     eax, edi
0x4141cc  mov     [ebp+var_4], eax
0x4141cf  cmp     edi, eax
0x4141d1  jnb     short loc_414212
0x4141d3  movzx   ebx, word ptr [edi]
0x4141d6  push    ebx; Character
0x4141d7  call    __putwch_nolock
0x4141dc  pop     ecx
0x4141dd  cmp     ax, bx
0x4141e0  jnz     short loc_41420A
0x4141e2  add     dword ptr [esi+4], 2
0x4141e6  cmp     ebx, 0Ah
0x4141e9  jnz     short loc_414200
0x4141eb  push    0Dh
0x4141ed  pop     ebx
0x4141ee  push    ebx; Character
0x4141ef  call    __putwch_nolock
0x4141f4  pop     ecx
0x4141f5  cmp     ax, bx
0x4141f8  jnz     short loc_41420A
0x4141fa  inc     dword ptr [esi+4]
0x4141fd  inc     dword ptr [esi+8]
0x414200  add     edi, 2
0x414203  cmp     edi, [ebp+var_4]
0x414206  jb      short loc_4141D3
0x414208  jmp     short loc_414212
0x41420a  call    ds:GetLastError
0x414210  mov     [esi], eax
0x414212  pop     edi
0x414213  mov     eax, esi
0x414215  pop     esi
0x414216  pop     ebx
0x414217  leave
0x414218  retn
```
