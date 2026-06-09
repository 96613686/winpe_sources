# CFFUpdateEncodingVector1

- ea: `0x18003b6ec`
- end: `0x18003b891`
- name: `CFFUpdateEncodingVector1`
- size: `421`
- prototype: `__int64 __fastcall(__int64, __int64, int, _DWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003b20c`

## callees

- `0x180001f20`
- `0x180005670`
- `0x180039e10`
- `0x18003a1f4`
- `0x18003b6ec`
- `0x180049c04`

## pseudocode

```c
__int64 __fastcall CFFUpdateEncodingVector1(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  _DWORD *v4; // rdi
  __int64 *v7; // r14
  __int64 v8; // rbp
  unsigned __int16 v9; // bx
  int i; // esi
  __int64 v11; // rdx
  __int64 v12; // r8
  __int64 v13; // r8
  char pszDest[256]; // [rsp+30h] [rbp-138h] BYREF

  v4 = a4;
  if ( !a3 )
    return 0;
  v7 = *(__int64 **)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( !v7 || !a4 )
    return 5;
  v8 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 168LL);
  StringCchPrintfA(pszDest, 0x100u, "/%s findfont /Encoding get", *(const char **)(a1 + 56));
  v9 = StrmPutStringEOL(v8, pszDest);
  for ( i = 0; !v9; ++v4 )
  {
    if ( i >= a3 || !*v4 )
      break;
    StringCchPrintfA(pszDest, 0x100u, "dup %d /", i);
    if ( !pszDest[0] )
      goto LABEL_12;
    v12 = -1;
    do
      ++v12;
    while ( pszDest[v12] );
    v9 = StrmPutBytes(v8, (__int64)pszDest, v12, 1);
    if ( !v9 )
    {
LABEL_12:
      XCF_GlyphIDsToCharNames(*v7, v11, v4, (__int64)pszDest);
      if ( pszDest[0] )
      {
        v13 = -1;
        do
          ++v13;
        while ( pszDest[v13] );
        v9 = StrmPutBytes(v8, (__int64)pszDest, v13, 1);
      }
      else
      {
        v9 = 0;
      }
      if ( !v9 )
        v9 = StrmPutStringEOL(v8, " put");
    }
    ++i;
  }
  StrmPutStringEOL(v8, "pop");
  return v9;
}

```

## disassembly

```asm
0x18003b6ec  mov     [rsp+arg_8], rbx
0x18003b6f1  mov     [rsp+arg_10], rbp
0x18003b6f6  push    rsi
0x18003b6f7  push    rdi
0x18003b6f8  push    r12
0x18003b6fa  push    r14
0x18003b6fc  push    r15
0x18003b6fe  sub     rsp, 140h
0x18003b705  mov     rax, cs:__security_cookie
0x18003b70c  xor     rax, rsp
0x18003b70f  mov     [rsp+168h+var_38], rax
0x18003b717  xor     r12d, r12d
0x18003b71a  mov     rdi, r9
0x18003b71d  mov     r15d, r8d
0x18003b720  test    r8d, r8d
0x18003b723  jnz     short loc_18003B72D
0x18003b725  mov     eax, r12d
0x18003b728  jmp     loc_18003B864
0x18003b72d  mov     rax, [rcx+30h]
0x18003b731  mov     r14, [rax+8]
0x18003b735  test    r14, r14
0x18003b738  jz      loc_18003B85F
0x18003b73e  test    r9, r9
0x18003b741  jz      loc_18003B85F
0x18003b747  mov     rax, [rcx+28h]
0x18003b74b  lea     r8, aSFindfontEncod; "/%s findfont /Encoding get"
0x18003b752  mov     r9, [rcx+38h]
0x18003b756  mov     edx, 100h; cchDest
0x18003b75b  lea     rcx, [rsp+168h+pszDest]; pszDest
0x18003b760  mov     rbp, [rax+0A8h]
0x18003b767  call    StringCchPrintfA
0x18003b76c  lea     rdx, [rsp+168h+pszDest]
0x18003b771  mov     rcx, rbp
0x18003b774  call    StrmPutStringEOL
0x18003b779  movzx   ebx, ax
0x18003b77c  mov     esi, r12d
0x18003b77f  test    ax, ax
0x18003b782  jnz     loc_18003B84B
0x18003b788  cmp     esi, r15d
0x18003b78b  jge     loc_18003B84B
0x18003b791  cmp     [rdi], r12d
0x18003b794  jz      loc_18003B84B
0x18003b79a  mov     r9d, esi
0x18003b79d  lea     r8, aDupD; "dup %d /"
0x18003b7a4  mov     edx, 100h; cchDest
0x18003b7a9  lea     rcx, [rsp+168h+pszDest]; pszDest
0x18003b7ae  call    StringCchPrintfA
0x18003b7b3  cmp     [rsp+168h+pszDest], r12b
0x18003b7b8  jz      short loc_18003B7E4
0x18003b7ba  lea     rax, [rsp+168h+pszDest]
0x18003b7bf  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b7c3  inc     r8
0x18003b7c6  cmp     [rax+r8], r12b
0x18003b7ca  jnz     short loc_18003B7C3
0x18003b7cc  mov     r9b, 1
0x18003b7cf  lea     rdx, [rsp+168h+pszDest]
0x18003b7d4  mov     rcx, rbp
0x18003b7d7  call    StrmPutBytes
0x18003b7dc  movzx   ebx, ax
0x18003b7df  test    ax, ax
0x18003b7e2  jnz     short loc_18003B83C
0x18003b7e4  mov     rcx, [r14]
0x18003b7e7  lea     r9, [rsp+168h+pszDest]
0x18003b7ec  mov     r8, rdi
0x18003b7ef  call    XCF_GlyphIDsToCharNames
0x18003b7f4  cmp     [rsp+168h+pszDest], r12b
0x18003b7f9  jz      short loc_18003B822
0x18003b7fb  lea     rax, [rsp+168h+pszDest]
0x18003b800  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b804  inc     r8
0x18003b807  cmp     [rax+r8], r12b
0x18003b80b  jnz     short loc_18003B804
0x18003b80d  mov     r9b, 1
0x18003b810  lea     rdx, [rsp+168h+pszDest]
0x18003b815  mov     rcx, rbp
0x18003b818  call    StrmPutBytes
0x18003b81d  movzx   ebx, ax
0x18003b820  jmp     short loc_18003B825
0x18003b822  mov     ebx, r12d
0x18003b825  test    bx, bx
0x18003b828  jnz     short loc_18003B83C
0x18003b82a  lea     rdx, aPut_1; " put"
0x18003b831  mov     rcx, rbp
0x18003b834  call    StrmPutStringEOL
0x18003b839  movzx   ebx, ax
0x18003b83c  inc     esi
0x18003b83e  add     rdi, 4
0x18003b842  test    bx, bx
0x18003b845  jz      loc_18003B788
0x18003b84b  lea     rdx, aPop; "pop"
0x18003b852  mov     rcx, rbp
0x18003b855  call    StrmPutStringEOL
0x18003b85a  movzx   eax, bx
0x18003b85d  jmp     short loc_18003B864
0x18003b85f  mov     eax, 5
0x18003b864  mov     rcx, [rsp+168h+var_38]
0x18003b86c  xor     rcx, rsp; StackCookie
0x18003b86f  call    __security_check_cookie
0x18003b874  lea     r11, [rsp+168h+var_28]
0x18003b87c  mov     rbx, [r11+38h]
0x18003b880  mov     rbp, [r11+40h]
0x18003b884  mov     rsp, r11
0x18003b887  pop     r15
0x18003b889  pop     r14
0x18003b88b  pop     r12
0x18003b88d  pop     rdi
0x18003b88e  pop     rsi
0x18003b88f  retn
```
