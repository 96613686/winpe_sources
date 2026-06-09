# CFFUpdateEncodingVector

- ea: `0x180039be8`
- end: `0x180039e54`
- name: `CFFUpdateEncodingVector`
- size: `620`
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
- `0x180039be8`
- `0x180048394`

## pseudocode

```c
__int64 __fastcall CFFUpdateEncodingVector(__int64 a1, int a2, __int64 a3, unsigned __int16 *a4)
{
  int v4; // r12d
  unsigned __int16 *v5; // rdi
  __int64 v6; // rbp
  _QWORD *v9; // r13
  int i; // r8d
  __int64 v11; // r15
  unsigned __int16 v12; // bx
  __int64 v13; // rdx
  __int64 v14; // r9
  __int64 v15; // r8
  __int64 v16; // r9
  __int64 v17; // r8
  __int64 v18; // rcx
  unsigned __int64 v19; // rdx
  int v20; // eax
  char pszDest[256]; // [rsp+30h] [rbp-148h] BYREF

  v4 = 0;
  v5 = a4;
  v6 = a3;
  if ( a2 )
  {
    v9 = *(_QWORD **)(*(_QWORD *)(a1 + 48) + 8LL);
    if ( !v9 || !a4 || !a3 )
      return 5;
    if ( a2 > 0 )
    {
      for ( i = 0; i < a2; ++i )
      {
        if ( (unsigned __int16)(*a4 - 1) <= 0xFEu
          && ((unsigned __int8)(1 << (*a4 & 7)) & *(_BYTE *)(((unsigned __int64)*a4 >> 3) + *(_QWORD *)(a1 + 80))) == 0 )
        {
          break;
        }
        ++a4;
      }
      if ( a2 > i )
      {
        v11 = *(_QWORD *)(*(_QWORD *)(a1 + 40) + 168LL);
        StringCchPrintfA(pszDest, 0x100u, "/%s findfont /Encoding get", *(const char **)(a1 + 56));
        v12 = StrmPutStringEOL(v11, pszDest);
        while ( 1 )
        {
          if ( v12 || v4 >= a2 )
          {
            StrmPutStringEOL(v11, "pop");
            return v12;
          }
          if ( (unsigned __int16)(*v5 - 1) <= 0xFEu
            && ((unsigned __int8)(1 << (*v5 & 7)) & *(_BYTE *)(((unsigned __int64)*v5 >> 3) + *(_QWORD *)(a1 + 80))) == 0 )
          {
            StringCchPrintfA(pszDest, 0x100u, "dup %d /", *v5);
            v12 = 0;
            if ( pszDest[0] )
            {
              v15 = -1;
              do
                ++v15;
              while ( pszDest[v15] );
              LOBYTE(v14) = 1;
              v12 = StrmPutBytes(v11, pszDest, v15, v14);
              if ( v12 )
                goto LABEL_29;
              v12 = 0;
            }
            if ( (unsigned int)XCF_GlyphIDsToCharNames(*v9, v13, v6, pszDest) )
            {
              v12 = 4097;
            }
            else
            {
              if ( pszDest[0] )
              {
                v17 = -1;
                do
                  ++v17;
                while ( pszDest[v17] );
                LOBYTE(v16) = 1;
                v12 = StrmPutBytes(v11, pszDest, v17, v16);
              }
              if ( !v12 )
              {
                v12 = StrmPutStringEOL(v11, " put");
                if ( !v12 )
                {
                  v18 = *(_QWORD *)(a1 + 80);
                  v19 = (unsigned __int64)*v5 >> 3;
                  v20 = *(unsigned __int8 *)(v19 + v18);
                  _bittestandset(&v20, *v5 & 7);
                  *(_BYTE *)(v19 + v18) = v20;
                }
              }
            }
          }
LABEL_29:
          ++v4;
          ++v5;
          v6 += 4;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180039be8  mov     [rsp+arg_8], rbx
0x180039bed  push    rbp
0x180039bee  push    rsi
0x180039bef  push    rdi
0x180039bf0  push    r12
0x180039bf2  push    r13
0x180039bf4  push    r14
0x180039bf6  push    r15
0x180039bf8  sub     rsp, 140h
0x180039bff  mov     rax, cs:__security_cookie
0x180039c06  xor     rax, rsp
0x180039c09  mov     [rsp+178h+var_48], rax
0x180039c11  xor     r12d, r12d
0x180039c14  mov     rdi, r9
0x180039c17  mov     rbp, r8
0x180039c1a  mov     esi, edx
0x180039c1c  mov     r14, rcx
0x180039c1f  test    edx, edx
0x180039c21  jz      loc_180039E26
0x180039c27  mov     rax, [rcx+30h]
0x180039c2b  mov     r13, [rax+8]
0x180039c2f  test    r13, r13
0x180039c32  jz      loc_180039E1F
0x180039c38  test    r9, r9
0x180039c3b  jz      loc_180039E1F
0x180039c41  test    r8, r8
0x180039c44  jz      loc_180039E1F
0x180039c4a  test    edx, edx
0x180039c4c  jle     loc_180039E26
0x180039c52  mov     r8d, r12d
0x180039c55  lea     r11d, [r12+1]
0x180039c5a  mov     ecx, 0FEh
0x180039c5f  movzx   r10d, word ptr [r9]
0x180039c63  movzx   eax, r10w
0x180039c67  sub     ax, r11w
0x180039c6b  cmp     ax, cx
0x180039c6e  ja      short loc_180039C91
0x180039c70  mov     rax, [r14+50h]
0x180039c74  mov     ecx, r10d
0x180039c77  and     ecx, 7
0x180039c7a  mov     edx, r11d
0x180039c7d  shl     edx, cl
0x180039c7f  movzx   ecx, r10w
0x180039c83  shr     rcx, 3
0x180039c87  test    [rcx+rax], dl
0x180039c8a  jz      short loc_180039C9D
0x180039c8c  mov     ecx, 0FEh
0x180039c91  add     r8d, r11d
0x180039c94  add     r9, 2
0x180039c98  cmp     r8d, esi
0x180039c9b  jl      short loc_180039C5F
0x180039c9d  cmp     esi, r8d
0x180039ca0  jle     loc_180039E26
0x180039ca6  mov     rax, [r14+28h]
0x180039caa  lea     r8, aSFindfontEncod; "/%s findfont /Encoding get"
0x180039cb1  mov     r9, [r14+38h]
0x180039cb5  lea     rcx, [rsp+178h+pszDest]; pszDest
0x180039cba  mov     edx, 100h; cchDest
0x180039cbf  mov     r15, [rax+0A8h]
0x180039cc6  call    StringCchPrintfA
0x180039ccb  lea     rdx, [rsp+178h+pszDest]
0x180039cd0  mov     rcx, r15
0x180039cd3  call    StrmPutStringEOL
0x180039cd8  movzx   ebx, ax
0x180039cdb  jmp     loc_180039E02
0x180039ce0  cmp     r12d, esi
0x180039ce3  jge     loc_180039E0B
0x180039ce9  movzx   eax, word ptr [rdi]
0x180039cec  mov     edx, 1
0x180039cf1  sub     ax, dx
0x180039cf4  mov     ecx, 0FEh
0x180039cf9  cmp     ax, cx
0x180039cfc  ja      loc_180039DF7
0x180039d02  movzx   r9d, word ptr [rdi]
0x180039d06  mov     rax, [r14+50h]
0x180039d0a  mov     ecx, r9d
0x180039d0d  and     ecx, 7
0x180039d10  shl     edx, cl
0x180039d12  movzx   ecx, word ptr [rdi]
0x180039d15  shr     rcx, 3
0x180039d19  test    [rcx+rax], dl
0x180039d1c  jnz     loc_180039DF7
0x180039d22  lea     r8, aDupD; "dup %d /"
0x180039d29  mov     edx, 100h; cchDest
0x180039d2e  lea     rcx, [rsp+178h+pszDest]; pszDest
0x180039d33  call    StringCchPrintfA
0x180039d38  xor     ebx, ebx
0x180039d3a  cmp     [rsp+178h+pszDest], bl
0x180039d3e  jz      short loc_180039D72
0x180039d40  lea     rax, [rsp+178h+pszDest]
0x180039d45  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039d49  inc     r8
0x180039d4c  cmp     [rax+r8], bl
0x180039d50  jnz     short loc_180039D49
0x180039d52  mov     r9b, 1
0x180039d55  lea     rdx, [rsp+178h+pszDest]
0x180039d5a  mov     rcx, r15
0x180039d5d  call    StrmPutBytes
0x180039d62  movzx   ebx, ax
0x180039d65  xor     eax, eax
0x180039d67  cmp     ax, bx
0x180039d6a  jnz     loc_180039DF7
0x180039d70  xor     ebx, ebx
0x180039d72  mov     rcx, [r13+0]
0x180039d76  lea     r9, [rsp+178h+pszDest]
0x180039d7b  mov     r8, rbp
0x180039d7e  call    XCF_GlyphIDsToCharNames
0x180039d83  test    eax, eax
0x180039d85  jnz     short loc_180039DF2
0x180039d87  cmp     [rsp+178h+pszDest], bl
0x180039d8b  jz      short loc_180039DB2
0x180039d8d  lea     rax, [rsp+178h+pszDest]
0x180039d92  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039d96  inc     r8
0x180039d99  cmp     [rax+r8], bl
0x180039d9d  jnz     short loc_180039D96
0x180039d9f  mov     r9b, 1
0x180039da2  lea     rdx, [rsp+178h+pszDest]
0x180039da7  mov     rcx, r15
0x180039daa  call    StrmPutBytes
0x180039daf  movzx   ebx, ax
0x180039db2  xor     eax, eax
0x180039db4  cmp     ax, bx
0x180039db7  jnz     short loc_180039DF7
0x180039db9  lea     rdx, aPut_1; " put"
0x180039dc0  mov     rcx, r15
0x180039dc3  call    StrmPutStringEOL
0x180039dc8  movzx   ebx, ax
0x180039dcb  xor     eax, eax
0x180039dcd  cmp     ax, bx
0x180039dd0  jnz     short loc_180039DF7
0x180039dd2  movzx   r8d, word ptr [rdi]
0x180039dd6  mov     rcx, [r14+50h]
0x180039dda  mov     edx, r8d
0x180039ddd  shr     rdx, 3
0x180039de1  and     r8d, 7
0x180039de5  movzx   eax, byte ptr [rdx+rcx]
0x180039de9  bts     eax, r8d
0x180039ded  mov     [rdx+rcx], al
0x180039df0  jmp     short loc_180039DF7
0x180039df2  mov     ebx, 1001h
0x180039df7  inc     r12d
0x180039dfa  add     rdi, 2
0x180039dfe  add     rbp, 4
0x180039e02  test    bx, bx
0x180039e05  jz      loc_180039CE0
0x180039e0b  lea     rdx, aPop; "pop"
0x180039e12  mov     rcx, r15
0x180039e15  call    StrmPutStringEOL
0x180039e1a  movzx   eax, bx
0x180039e1d  jmp     short loc_180039E29
0x180039e1f  mov     eax, 5
0x180039e24  jmp     short loc_180039E29
0x180039e26  mov     eax, r12d
0x180039e29  mov     rcx, [rsp+178h+var_48]
0x180039e31  xor     rcx, rsp; StackCookie
0x180039e34  call    __security_check_cookie
0x180039e39  mov     rbx, [rsp+178h+arg_8]
0x180039e41  add     rsp, 140h
0x180039e48  pop     r15
0x180039e4a  pop     r14
0x180039e4c  pop     r13
0x180039e4e  pop     r12
0x180039e50  pop     rdi
0x180039e51  pop     rsi
0x180039e52  pop     rbp
0x180039e53  retn
```
