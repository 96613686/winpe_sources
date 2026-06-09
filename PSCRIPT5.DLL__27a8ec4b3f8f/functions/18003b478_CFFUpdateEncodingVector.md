# CFFUpdateEncodingVector

- ea: `0x18003b478`
- end: `0x18003b6e5`
- name: `CFFUpdateEncodingVector`
- size: `621`
- prototype: `__int64 __fastcall(__int64, int, __int64, unsigned __int16 *)`
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
- `0x18003b478`
- `0x180049c04`

## pseudocode

```c
__int64 __fastcall CFFUpdateEncodingVector(__int64 a1, int a2, _DWORD *a3, unsigned __int16 *a4)
{
  int v4; // r12d
  unsigned __int16 *v5; // rdi
  _DWORD *v6; // rbp
  __int64 *v9; // r13
  int i; // r8d
  __int64 v11; // r15
  unsigned __int16 v12; // bx
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 v15; // r8
  __int64 v16; // rcx
  unsigned __int64 v17; // rdx
  int v18; // eax
  char pszDest[256]; // [rsp+30h] [rbp-148h] BYREF

  v4 = 0;
  v5 = a4;
  v6 = a3;
  if ( a2 )
  {
    v9 = *(__int64 **)(*(_QWORD *)(a1 + 48) + 8LL);
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
              v14 = -1;
              do
                ++v14;
              while ( pszDest[v14] );
              v12 = StrmPutBytes(v11, (__int64)pszDest, v14, 1);
              if ( v12 )
                goto LABEL_29;
              v12 = 0;
            }
            if ( (unsigned int)XCF_GlyphIDsToCharNames(*v9, v13, v6, (__int64)pszDest) )
            {
              v12 = 4097;
            }
            else
            {
              if ( pszDest[0] )
              {
                v15 = -1;
                do
                  ++v15;
                while ( pszDest[v15] );
                v12 = StrmPutBytes(v11, (__int64)pszDest, v15, 1);
              }
              if ( !v12 )
              {
                v12 = StrmPutStringEOL(v11, " put");
                if ( !v12 )
                {
                  v16 = *(_QWORD *)(a1 + 80);
                  v17 = (unsigned __int64)*v5 >> 3;
                  v18 = *(unsigned __int8 *)(v17 + v16);
                  _bittestandset(&v18, *v5 & 7);
                  *(_BYTE *)(v17 + v16) = v18;
                }
              }
            }
          }
LABEL_29:
          ++v4;
          ++v5;
          ++v6;
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003b478  mov     [rsp+arg_8], rbx
0x18003b47d  push    rbp
0x18003b47e  push    rsi
0x18003b47f  push    rdi
0x18003b480  push    r12
0x18003b482  push    r13
0x18003b484  push    r14
0x18003b486  push    r15
0x18003b488  sub     rsp, 140h
0x18003b48f  mov     rax, cs:__security_cookie
0x18003b496  xor     rax, rsp
0x18003b499  mov     [rsp+178h+var_48], rax
0x18003b4a1  xor     r12d, r12d
0x18003b4a4  mov     rdi, r9
0x18003b4a7  mov     rbp, r8
0x18003b4aa  mov     esi, edx
0x18003b4ac  mov     r14, rcx
0x18003b4af  test    edx, edx
0x18003b4b1  jz      loc_18003B6B6
0x18003b4b7  mov     rax, [rcx+30h]
0x18003b4bb  mov     r13, [rax+8]
0x18003b4bf  test    r13, r13
0x18003b4c2  jz      loc_18003B6AF
0x18003b4c8  test    r9, r9
0x18003b4cb  jz      loc_18003B6AF
0x18003b4d1  test    r8, r8
0x18003b4d4  jz      loc_18003B6AF
0x18003b4da  test    edx, edx
0x18003b4dc  jle     loc_18003B6B6
0x18003b4e2  mov     r8d, r12d
0x18003b4e5  lea     r11d, [r12+1]
0x18003b4ea  mov     ecx, 0FEh
0x18003b4ef  movzx   r10d, word ptr [r9]
0x18003b4f3  movzx   eax, r10w
0x18003b4f7  sub     ax, r11w
0x18003b4fb  cmp     ax, cx
0x18003b4fe  ja      short loc_18003B521
0x18003b500  mov     rax, [r14+50h]
0x18003b504  mov     ecx, r10d
0x18003b507  and     ecx, 7
0x18003b50a  mov     edx, r11d
0x18003b50d  shl     edx, cl
0x18003b50f  movzx   ecx, r10w
0x18003b513  shr     rcx, 3
0x18003b517  test    [rcx+rax], dl
0x18003b51a  jz      short loc_18003B52D
0x18003b51c  mov     ecx, 0FEh
0x18003b521  add     r8d, r11d
0x18003b524  add     r9, 2
0x18003b528  cmp     r8d, esi
0x18003b52b  jl      short loc_18003B4EF
0x18003b52d  cmp     esi, r8d
0x18003b530  jle     loc_18003B6B6
0x18003b536  mov     rax, [r14+28h]
0x18003b53a  lea     r8, aSFindfontEncod; "/%s findfont /Encoding get"
0x18003b541  mov     r9, [r14+38h]
0x18003b545  lea     rcx, [rsp+178h+pszDest]; pszDest
0x18003b54a  mov     edx, 100h; cchDest
0x18003b54f  mov     r15, [rax+0A8h]
0x18003b556  call    StringCchPrintfA
0x18003b55b  lea     rdx, [rsp+178h+pszDest]
0x18003b560  mov     rcx, r15
0x18003b563  call    StrmPutStringEOL
0x18003b568  movzx   ebx, ax
0x18003b56b  jmp     loc_18003B692
0x18003b570  cmp     r12d, esi
0x18003b573  jge     loc_18003B69B
0x18003b579  movzx   eax, word ptr [rdi]
0x18003b57c  mov     edx, 1
0x18003b581  sub     ax, dx
0x18003b584  mov     ecx, 0FEh
0x18003b589  cmp     ax, cx
0x18003b58c  ja      loc_18003B687
0x18003b592  movzx   r9d, word ptr [rdi]
0x18003b596  mov     rax, [r14+50h]
0x18003b59a  mov     ecx, r9d
0x18003b59d  and     ecx, 7
0x18003b5a0  shl     edx, cl
0x18003b5a2  movzx   ecx, word ptr [rdi]
0x18003b5a5  shr     rcx, 3
0x18003b5a9  test    [rcx+rax], dl
0x18003b5ac  jnz     loc_18003B687
0x18003b5b2  lea     r8, aDupD; "dup %d /"
0x18003b5b9  mov     edx, 100h; cchDest
0x18003b5be  lea     rcx, [rsp+178h+pszDest]; pszDest
0x18003b5c3  call    StringCchPrintfA
0x18003b5c8  xor     ebx, ebx
0x18003b5ca  cmp     [rsp+178h+pszDest], bl
0x18003b5ce  jz      short loc_18003B602
0x18003b5d0  lea     rax, [rsp+178h+pszDest]
0x18003b5d5  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b5d9  inc     r8
0x18003b5dc  cmp     [rax+r8], bl
0x18003b5e0  jnz     short loc_18003B5D9
0x18003b5e2  mov     r9b, 1
0x18003b5e5  lea     rdx, [rsp+178h+pszDest]
0x18003b5ea  mov     rcx, r15
0x18003b5ed  call    StrmPutBytes
0x18003b5f2  movzx   ebx, ax
0x18003b5f5  xor     eax, eax
0x18003b5f7  cmp     ax, bx
0x18003b5fa  jnz     loc_18003B687
0x18003b600  xor     ebx, ebx
0x18003b602  mov     rcx, [r13+0]
0x18003b606  lea     r9, [rsp+178h+pszDest]
0x18003b60b  mov     r8, rbp
0x18003b60e  call    XCF_GlyphIDsToCharNames
0x18003b613  test    eax, eax
0x18003b615  jnz     short loc_18003B682
0x18003b617  cmp     [rsp+178h+pszDest], bl
0x18003b61b  jz      short loc_18003B642
0x18003b61d  lea     rax, [rsp+178h+pszDest]
0x18003b622  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003b626  inc     r8
0x18003b629  cmp     [rax+r8], bl
0x18003b62d  jnz     short loc_18003B626
0x18003b62f  mov     r9b, 1
0x18003b632  lea     rdx, [rsp+178h+pszDest]
0x18003b637  mov     rcx, r15
0x18003b63a  call    StrmPutBytes
0x18003b63f  movzx   ebx, ax
0x18003b642  xor     eax, eax
0x18003b644  cmp     ax, bx
0x18003b647  jnz     short loc_18003B687
0x18003b649  lea     rdx, aPut_1; " put"
0x18003b650  mov     rcx, r15
0x18003b653  call    StrmPutStringEOL
0x18003b658  movzx   ebx, ax
0x18003b65b  xor     eax, eax
0x18003b65d  cmp     ax, bx
0x18003b660  jnz     short loc_18003B687
0x18003b662  movzx   r8d, word ptr [rdi]
0x18003b666  mov     rcx, [r14+50h]
0x18003b66a  mov     edx, r8d
0x18003b66d  shr     rdx, 3
0x18003b671  and     r8d, 7
0x18003b675  movzx   eax, byte ptr [rdx+rcx]
0x18003b679  bts     eax, r8d
0x18003b67d  mov     [rdx+rcx], al
0x18003b680  jmp     short loc_18003B687
0x18003b682  mov     ebx, 1001h
0x18003b687  inc     r12d
0x18003b68a  add     rdi, 2
0x18003b68e  add     rbp, 4
0x18003b692  test    bx, bx
0x18003b695  jz      loc_18003B570
0x18003b69b  lea     rdx, aPop; "pop"
0x18003b6a2  mov     rcx, r15
0x18003b6a5  call    StrmPutStringEOL
0x18003b6aa  movzx   eax, bx
0x18003b6ad  jmp     short loc_18003B6B9
0x18003b6af  mov     eax, 5
0x18003b6b4  jmp     short loc_18003B6B9
0x18003b6b6  mov     eax, r12d
0x18003b6b9  mov     rcx, [rsp+178h+var_48]
0x18003b6c1  xor     rcx, rsp; StackCookie
0x18003b6c4  call    __security_check_cookie
0x18003b6c9  mov     rbx, [rsp+178h+arg_8]
0x18003b6d1  add     rsp, 140h
0x18003b6d8  pop     r15
0x18003b6da  pop     r14
0x18003b6dc  pop     r13
0x18003b6de  pop     r12
0x18003b6e0  pop     rdi
0x18003b6e1  pop     rsi
0x18003b6e2  pop     rbp
0x18003b6e3  retn
```
