# UpdateEncodingVector

- ea: `0x1800396ec`
- end: `0x180039947`
- name: `UpdateEncodingVector`
- size: `603`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18003e878`
- `0x180046500`

## callees

- `0x180001f20`
- `0x180005670`
- `0x18003886c`
- `0x1800396ec`
- `0x180039e10`
- `0x18003a1f4`

## pseudocode

```c
__int64 __fastcall UpdateEncodingVector(_QWORD *a1, __int64 a2, __int64 a3, int a4)
{
  __int64 v7; // rsi
  unsigned __int16 v8; // ax
  _BYTE *v9; // rdx
  __int16 v10; // ax
  __int64 v11; // r8
  unsigned __int16 v12; // r9
  int v13; // edi
  __int64 v14; // rcx
  unsigned int v15; // ecx
  __int64 v16; // r9
  __int64 v17; // rax
  int v18; // r9d
  __int64 v19; // r8
  __int64 v20; // r8
  __int16 v21; // ax
  __int64 v22; // r8
  unsigned int v23; // r8d
  _BYTE *v25; // [rsp+30h] [rbp-58h] BYREF
  char pszDest[16]; // [rsp+38h] [rbp-50h] BYREF

  if ( a4 <= *(_DWORD *)a2 && a4 > 0 )
  {
    v7 = *(_QWORD *)(a1[5] + 168LL);
    v8 = StrmPutBytes(v7, (__int64)"/", 1, 1);
    if ( v8 )
      return v8;
    v9 = (_BYTE *)a1[7];
    v10 = 5;
    if ( v9 )
    {
      if ( !*v9 )
      {
        v12 = 0;
LABEL_10:
        if ( !v12 )
          v12 = StrmPutStringEOL(v7, " findfont /Encoding get");
        v13 = 0;
LABEL_38:
        if ( v12 )
          return v12;
        while ( v13 < a4 )
        {
          if ( *(_BYTE *)a1[5] )
          {
            v14 = *(_QWORD *)(a2 + 16);
            if ( v14 )
            {
              v15 = *(unsigned __int16 *)(v14 + 2LL * v13);
              if ( (*(_BYTE *)(((unsigned __int64)v15 >> 3) + a1[10]) & (unsigned __int8)(1 << (v15 & 7))) != 0 )
                goto LABEL_37;
            }
          }
          v16 = *(_QWORD *)(a2 + 8);
          v25 = 0;
          FindGlyphName((__int64)a1, a2, v13, *(_WORD *)(v16 + 4LL * v13), (__int64 *)&v25);
          v17 = *(_QWORD *)(a2 + 16);
          if ( v17 )
            v18 = *(unsigned __int16 *)(v17 + 2LL * v13);
          else
            v18 = v13;
          StringCchPrintfA(pszDest, 0x10u, "dup %d /", v18);
          if ( pszDest[0] )
          {
            v19 = -1;
            do
              ++v19;
            while ( pszDest[v19] );
            v8 = StrmPutBytes(v7, (__int64)pszDest, v19, 1);
            if ( v8 )
              return v8;
          }
          if ( v25 )
          {
            if ( *v25 )
            {
              v20 = -1;
              do
                ++v20;
              while ( v25[v20] );
              v21 = StrmPutBytes(v7, (__int64)v25, v20, 1);
            }
            else
            {
              v21 = 0;
            }
          }
          else
          {
            v21 = 5;
          }
          if ( v21 )
          {
            v12 = v21;
LABEL_37:
            ++v13;
            goto LABEL_38;
          }
          v12 = StrmPutStringEOL(v7, " put");
          if ( v12 )
            goto LABEL_37;
          v22 = *(_QWORD *)(a2 + 16);
          if ( !v22 )
            goto LABEL_37;
          v23 = *(unsigned __int16 *)(v22 + 2LL * v13);
          *(_BYTE *)(((unsigned __int64)v23 >> 3) + a1[10]) |= 1 << (v23 & 7);
          ++v13;
        }
        return (unsigned __int16)StrmPutStringEOL(v7, "pop");
      }
      v11 = -1;
      do
        ++v11;
      while ( v9[v11] );
      v10 = StrmPutBytes(v7, (__int64)v9, v11, 1);
    }
    v12 = v10;
    goto LABEL_10;
  }
  return 1;
}

```

## disassembly

```asm
0x1800396ec  mov     [rsp+arg_10], rbx
0x1800396f1  push    rbp
0x1800396f2  push    rsi
0x1800396f3  push    rdi
0x1800396f4  push    r12
0x1800396f6  push    r13
0x1800396f8  push    r14
0x1800396fa  push    r15
0x1800396fc  sub     rsp, 50h
0x180039700  mov     rax, cs:__security_cookie
0x180039707  xor     rax, rsp
0x18003970a  mov     [rsp+88h+var_40], rax
0x18003970f  mov     r12d, r9d
0x180039712  mov     r14, rdx
0x180039715  mov     rbp, rcx
0x180039718  cmp     r9d, [rdx]
0x18003971b  jg      loc_18003991C
0x180039721  xor     r13d, r13d
0x180039724  test    r9d, r9d
0x180039727  jle     loc_18003991C
0x18003972d  mov     rax, [rcx+28h]
0x180039731  lea     ebx, [r13+1]
0x180039735  mov     r9b, bl
0x180039738  lea     rdx, asc_1800667DC; "/"
0x18003973f  mov     r8d, ebx
0x180039742  mov     rsi, [rax+0A8h]
0x180039749  mov     rcx, rsi
0x18003974c  call    StrmPutBytes
0x180039751  cmp     r13w, ax
0x180039755  jnz     loc_180039912
0x18003975b  mov     rdx, [rbp+38h]
0x18003975f  lea     eax, [rbx+4]
0x180039762  test    rdx, rdx
0x180039765  jz      short loc_180039784
0x180039767  cmp     [rdx], r13b
0x18003976a  jz      short loc_1800397A9
0x18003976c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039770  inc     r8
0x180039773  cmp     [rdx+r8], r13b
0x180039777  jnz     short loc_180039770
0x180039779  mov     r9b, bl
0x18003977c  mov     rcx, rsi
0x18003977f  call    StrmPutBytes
0x180039784  movzx   r9d, ax
0x180039788  cmp     r13w, r9w
0x18003978c  jnz     short loc_1800397A1
0x18003978e  lea     rdx, aFindfontEncodi; " findfont /Encoding get"
0x180039795  mov     rcx, rsi
0x180039798  call    StrmPutStringEOL
0x18003979d  movzx   r9d, ax
0x1800397a1  mov     edi, r13d
0x1800397a4  jmp     loc_1800398F7
0x1800397a9  mov     r9d, r13d
0x1800397ac  jmp     short loc_180039788
0x1800397ae  cmp     edi, r12d
0x1800397b1  jge     loc_180039903
0x1800397b7  mov     rax, [rbp+28h]
0x1800397bb  cmp     [rax], r13b
0x1800397be  jz      short loc_1800397EE
0x1800397c0  mov     rcx, [r14+10h]
0x1800397c4  test    rcx, rcx
0x1800397c7  jz      short loc_1800397EE
0x1800397c9  movsxd  rax, edi
0x1800397cc  movzx   ecx, word ptr [rcx+rax*2]
0x1800397d0  mov     rax, [rbp+50h]
0x1800397d4  mov     edx, ecx
0x1800397d6  shr     rdx, 3
0x1800397da  and     ecx, 7
0x1800397dd  mov     r8b, [rdx+rax]
0x1800397e1  mov     eax, ebx
0x1800397e3  shl     eax, cl
0x1800397e5  test    al, r8b
0x1800397e8  jnz     loc_1800398F5
0x1800397ee  mov     r9, [r14+8]
0x1800397f2  lea     rax, [rsp+88h+var_58]
0x1800397f7  movsxd  r15, edi
0x1800397fa  mov     r8d, edi
0x1800397fd  mov     rdx, r14
0x180039800  mov     [rsp+88h+var_58], r13
0x180039805  mov     rcx, rbp
0x180039808  mov     [rsp+88h+var_68], rax
0x18003980d  movzx   r9d, word ptr [r9+r15*4]
0x180039812  call    FindGlyphName
0x180039817  mov     rax, [r14+10h]
0x18003981b  test    rax, rax
0x18003981e  jz      short loc_180039827
0x180039820  movzx   r9d, word ptr [rax+r15*2]
0x180039825  jmp     short loc_18003982A
0x180039827  mov     r9d, edi
0x18003982a  lea     r8, aDupD; "dup %d /"
0x180039831  mov     edx, 10h; cchDest
0x180039836  lea     rcx, [rsp+88h+pszDest]; pszDest
0x18003983b  call    StringCchPrintfA
0x180039840  cmp     [rsp+88h+pszDest], r13b
0x180039845  jz      short loc_180039872
0x180039847  lea     rax, [rsp+88h+pszDest]
0x18003984c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039850  inc     r8
0x180039853  cmp     [rax+r8], r13b
0x180039857  jnz     short loc_180039850
0x180039859  mov     r9b, bl
0x18003985c  lea     rdx, [rsp+88h+pszDest]
0x180039861  mov     rcx, rsi
0x180039864  call    StrmPutBytes
0x180039869  test    ax, ax
0x18003986c  jnz     loc_180039912
0x180039872  mov     rdx, [rsp+88h+var_58]
0x180039877  test    rdx, rdx
0x18003987a  jz      short loc_1800398A0
0x18003987c  cmp     [rdx], r13b
0x18003987f  jz      short loc_18003989B
0x180039881  or      r8, 0FFFFFFFFFFFFFFFFh
0x180039885  inc     r8
0x180039888  cmp     [rdx+r8], r13b
0x18003988c  jnz     short loc_180039885
0x18003988e  mov     r9b, bl
0x180039891  mov     rcx, rsi
0x180039894  call    StrmPutBytes
0x180039899  jmp     short loc_1800398A5
0x18003989b  mov     eax, r13d
0x18003989e  jmp     short loc_1800398A5
0x1800398a0  mov     eax, 5
0x1800398a5  test    ax, ax
0x1800398a8  jnz     short loc_1800398F1
0x1800398aa  lea     rdx, aPut_1; " put"
0x1800398b1  mov     rcx, rsi
0x1800398b4  call    StrmPutStringEOL
0x1800398b9  movzx   r9d, ax
0x1800398bd  test    ax, ax
0x1800398c0  jnz     short loc_1800398F5
0x1800398c2  mov     r8, [r14+10h]
0x1800398c6  test    r8, r8
0x1800398c9  jz      short loc_1800398F5
0x1800398cb  movzx   r8d, word ptr [r8+r15*2]
0x1800398d0  mov     rcx, [rbp+50h]
0x1800398d4  mov     edx, r8d
0x1800398d7  shr     rdx, 3
0x1800398db  and     r8d, 7
0x1800398df  movzx   eax, byte ptr [rdx+rcx]
0x1800398e3  bts     eax, r8d
0x1800398e7  mov     [rdx+rcx], al
0x1800398ea  add     edi, ebx
0x1800398ec  jmp     loc_1800397AE
0x1800398f1  movzx   r9d, ax
0x1800398f5  add     edi, ebx
0x1800398f7  test    r9w, r9w
0x1800398fb  jz      loc_1800397AE
0x180039901  jmp     short loc_180039916
0x180039903  lea     rdx, aPop_0; "pop"
0x18003990a  mov     rcx, rsi
0x18003990d  call    StrmPutStringEOL
0x180039912  movzx   r9d, ax
0x180039916  movzx   eax, r9w
0x18003991a  jmp     short loc_180039921
0x18003991c  mov     eax, 1
0x180039921  mov     rcx, [rsp+88h+var_40]
0x180039926  xor     rcx, rsp; StackCookie
0x180039929  call    __security_check_cookie
0x18003992e  mov     rbx, [rsp+88h+arg_10]
0x180039936  add     rsp, 50h
0x18003993a  pop     r15
0x18003993c  pop     r14
0x18003993e  pop     r13
0x180039940  pop     r12
0x180039942  pop     rdi
0x180039943  pop     rsi
0x180039944  pop     rbp
0x180039945  retn
```
