# CFFUpdateEncodingVector1

- ea: `0x180039e5c`
- end: `0x18003a000`
- name: `CFFUpdateEncodingVector1`
- size: `420`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003997c`

## callees

- `0x180001ee0`
- `0x1800055e0`
- `0x18003858c`
- `0x180038968`
- `0x180039e5c`
- `0x180048394`

## pseudocode

```c
__int64 __fastcall CFFUpdateEncodingVector1(__int64 a1, __int64 a2, int a3, _DWORD *a4)
{
  _DWORD *v4; // rdi
  _QWORD *v7; // r14
  __int64 v8; // rbp
  unsigned __int16 v9; // bx
  int i; // esi
  __int64 v11; // rdx
  __int64 v12; // r9
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  char pszDest[256]; // [rsp+30h] [rbp-138h] BYREF

  v4 = a4;
  if ( !a3 )
    return 0;
  v7 = *(_QWORD **)(*(_QWORD *)(a1 + 48) + 8LL);
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
    v13 = -1;
    do
      ++v13;
    while ( pszDest[v13] );
    LOBYTE(v12) = 1;
    v9 = StrmPutBytes(v8, pszDest, v13, v12);
    if ( !v9 )
    {
LABEL_12:
      XCF_GlyphIDsToCharNames(*v7, v11, v4, pszDest);
      if ( pszDest[0] )
      {
        v15 = -1;
        do
          ++v15;
        while ( pszDest[v15] );
        LOBYTE(v14) = 1;
        v9 = StrmPutBytes(v8, pszDest, v15, v14);
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
0x180039e5c  mov     [rsp+arg_8], rbx
0x180039e61  mov     [rsp+arg_10], rbp
0x180039e66  push    rsi
0x180039e67  push    rdi
0x180039e68  push    r12
0x180039e6a  push    r14
0x180039e6c  push    r15
0x180039e6e  sub     rsp, 140h
0x180039e75  mov     rax, cs:__security_cookie
0x180039e7c  xor     rax, rsp
0x180039e7f  mov     [rsp+168h+var_38], rax
0x180039e87  xor     r12d, r12d
0x180039e8a  mov     rdi, r9
0x180039e8d  mov     r15d, r8d
0x180039e90  test    r8d, r8d
0x180039e93  jnz     short loc_180039E9D
0x180039e95  mov     eax, r12d
0x180039e98  jmp     loc_180039FD4
0x180039e9d  mov     rax, [rcx+30h]
0x180039ea1  mov     r14, [rax+8]
0x180039ea5  test    r14, r14
0x180039ea8  jz      loc_180039FCF
0x180039eae  test    r9, r9
0x180039eb1  jz      loc_180039FCF
0x180039eb7  mov     rax, [rcx+28h]
0x180039ebb  lea     r8, aSFindfontEncod; "/%s findfont /Encoding get"
0x180039ec2  mov     r9, [rcx+38h]
0x180039ec6  mov     edx, 100h; cchDest
0x180039ecb  lea     rcx, [rsp+168h+pszDest]; pszDest
0x180039ed0  mov     rbp, [rax+0A8h]
0x180039ed7  call    StringCchPrintfA
0x180039edc  lea     rdx, [rsp+168h+pszDest]
0x180039ee1  mov     rcx, rbp
0x180039ee4  call    StrmPutStringEOL
0x180039ee9  movzx   ebx, ax
0x180039eec  mov     esi, r12d
0x180039eef  test    ax, ax
0x180039ef2  jnz     loc_180039FBB
0x180039ef8  cmp     esi, r15d
0x180039efb  jge     loc_180039FBB
0x180039f01  cmp     [rdi], r12d
0x180039f04  jz      loc_180039FBB
0x180039f0a  mov     r9d, esi
0x180039f0d  lea     r8, aDupD; "dup %d /"
0x180039f14  mov     edx, 100h; cchDest
0x180039f19  lea     rcx, [rsp+168h+pszDest]; pszDest
0x180039f1e  call    StringCchPrintfA
0x180039f23  cmp     [rsp+168h+pszDest], r12b
0x180039f28  jz      short loc_180039F54
0x180039f2a  lea     rax, [rsp+168h+pszDest]
0x180039f2f  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039f33  inc     r8
0x180039f36  cmp     [rax+r8], r12b
0x180039f3a  jnz     short loc_180039F33
0x180039f3c  mov     r9b, 1
0x180039f3f  lea     rdx, [rsp+168h+pszDest]
0x180039f44  mov     rcx, rbp
0x180039f47  call    StrmPutBytes
0x180039f4c  movzx   ebx, ax
0x180039f4f  test    ax, ax
0x180039f52  jnz     short loc_180039FAC
0x180039f54  mov     rcx, [r14]
0x180039f57  lea     r9, [rsp+168h+pszDest]
0x180039f5c  mov     r8, rdi
0x180039f5f  call    XCF_GlyphIDsToCharNames
0x180039f64  cmp     [rsp+168h+pszDest], r12b
0x180039f69  jz      short loc_180039F92
0x180039f6b  lea     rax, [rsp+168h+pszDest]
0x180039f70  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039f74  inc     r8
0x180039f77  cmp     [rax+r8], r12b
0x180039f7b  jnz     short loc_180039F74
0x180039f7d  mov     r9b, 1
0x180039f80  lea     rdx, [rsp+168h+pszDest]
0x180039f85  mov     rcx, rbp
0x180039f88  call    StrmPutBytes
0x180039f8d  movzx   ebx, ax
0x180039f90  jmp     short loc_180039F95
0x180039f92  mov     ebx, r12d
0x180039f95  test    bx, bx
0x180039f98  jnz     short loc_180039FAC
0x180039f9a  lea     rdx, aPut_1; " put"
0x180039fa1  mov     rcx, rbp
0x180039fa4  call    StrmPutStringEOL
0x180039fa9  movzx   ebx, ax
0x180039fac  inc     esi
0x180039fae  add     rdi, 4
0x180039fb2  test    bx, bx
0x180039fb5  jz      loc_180039EF8
0x180039fbb  lea     rdx, aPop; "pop"
0x180039fc2  mov     rcx, rbp
0x180039fc5  call    StrmPutStringEOL
0x180039fca  movzx   eax, bx
0x180039fcd  jmp     short loc_180039FD4
0x180039fcf  mov     eax, 5
0x180039fd4  mov     rcx, [rsp+168h+var_38]
0x180039fdc  xor     rcx, rsp; StackCookie
0x180039fdf  call    __security_check_cookie
0x180039fe4  lea     r11, [rsp+168h+var_28]
0x180039fec  mov     rbx, [r11+38h]
0x180039ff0  mov     rbp, [r11+40h]
0x180039ff4  mov     rsp, r11
0x180039ff7  pop     r15
0x180039ff9  pop     r14
0x180039ffb  pop     r12
0x180039ffd  pop     rdi
0x180039ffe  pop     rsi
0x180039fff  retn
```
