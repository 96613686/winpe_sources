# ReadMrLine

- ea: `0x18000c1a4`
- end: `0x18000c656`
- name: `ReadMrLine`
- size: `1202`
- prototype: `__int64 __fastcall(_DWORD **, unsigned __int8 *, unsigned __int16 *, __int64, unsigned __int64, int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180009c84`
- `0x18000b604`
- `0x18000cab0`
- `0x18000d4b0`

## callees

- `0x180009bd0`
- `0x18000c1a4`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c3db`
- `KERNEL32!SetLastError` at `0x18000c3db`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadMrLine(
        _DWORD **a1,
        unsigned __int8 *a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int64 a5,
        int a6,
        unsigned int a7)
{
  unsigned __int16 v7; // bp
  _DWORD *v8; // rdi
  unsigned __int16 *v9; // r12
  unsigned __int8 v10; // si
  unsigned __int16 v11; // r11
  unsigned int v12; // r14d
  char v13; // r13
  unsigned int v14; // ebx
  int v15; // r15d
  unsigned __int16 v16; // r8
  int v17; // edx
  char v18; // al
  char v19; // r9
  int v20; // ecx
  __int64 v21; // rax
  unsigned __int8 v22; // cl
  int v23; // r12d
  __int64 *v24; // r9
  int v25; // edx
  _BYTE *v26; // rdx
  _BYTE *v27; // r10
  int v28; // r9d
  _BYTE *v29; // r15
  unsigned int v30; // ecx
  int v32; // eax
  unsigned __int8 v33; // dl
  unsigned __int8 v34; // cl
  bool v35; // zf
  unsigned __int8 v36; // dl
  unsigned __int64 v37; // rax
  unsigned __int8 v38; // [rsp+30h] [rbp-58h]
  char v39; // [rsp+31h] [rbp-57h]
  int v40; // [rsp+34h] [rbp-54h]
  int v41; // [rsp+38h] [rbp-50h]

  v7 = *a3;
  v8 = *a1;
  v9 = a3;
  v10 = *a2;
  v11 = 0;
  v12 = a7;
  v13 = 0;
  v14 = 1;
  v40 = 0;
  v15 = 0;
  v38 = 0;
  v16 = 0;
  while ( 1 )
  {
    v17 = *v8 >> v10;
    if ( v10 > 0x19u )
      LOBYTE(v17) = (v8[1] << (32 - v10)) + v17;
    v18 = *((_BYTE *)gc_PrefTable + (v17 & 0x7F));
    v19 = v18 & 0xF;
    v20 = v18 >> 4;
    if ( (__int16)v20 < 4 )
    {
      if ( v16 >= v7 && v16 )
      {
        while ( ++v11 < 0x6C3u )
        {
          v7 = v9[v11];
          if ( v7 > v16 )
          {
            v13 = v11 & 1;
            goto LABEL_10;
          }
        }
        goto LABEL_79;
      }
LABEL_10:
      if ( v38 == v13 || v7 == v12 )
        LOWORD(v20) = v7 + v20;
      else
        LOWORD(v20) = v9[v11 + 1] + v20;
      if ( (unsigned __int16)v20 <= v16 && v16 || (unsigned __int16)v20 > v12 )
        goto LABEL_32;
      v21 = (unsigned __int16)v15;
      LOWORD(v15) = v15 + 1;
      *(_WORD *)(a4 + 2 * v21) = v20;
      if ( (unsigned __int16)v15 >= 0x6C3u )
        goto LABEL_79;
      v40 = v15;
      v38 = 1 - v38;
      goto LABEL_71;
    }
    if ( (_WORD)v20 == 4 )
    {
      v22 = v10 + v19;
      v23 = 1;
      v41 = v38;
      v24 = GlobTableBlack;
      if ( v22 > 0x1Fu )
        ++v8;
      v39 = 0;
      v10 = v22 - 32;
      if ( v22 <= 0x1Fu )
        v10 = v22;
      if ( !v38 )
        v24 = gc_GlobTableWhite;
      while ( 1 )
      {
        v25 = *v8 >> v10;
        if ( v10 > 0x11u )
          LOWORD(v25) = (v8[1] << (32 - v10)) + v25;
        v26 = (char *)v24 + 5 * (v25 & 0x7FFFu);
        v27 = v26;
        v28 = 0;
        v29 = v26 + 4;
        while ( 1 )
        {
          v30 = *v26 & 0x3F;
          if ( (char)*v26 >= 0 )
          {
            v16 += v30;
            if ( v16 > v12 )
              goto LABEL_32;
            *(_WORD *)(a4 + 2LL * (unsigned __int16)v40) = v16;
            HIWORD(v32) = HIWORD(v40);
            v12 = a7;
            if ( (unsigned __int16)(v40 + 1) >= 0x6C3u )
              goto LABEL_79;
            LOWORD(v32) = v40 + 1;
            v40 = v32;
            v41 = 1 - v41;
            if ( (unsigned __int8)++v39 >= 2u )
            {
              v35 = v23 == 0;
              v9 = a3;
              if ( v35 )
                v19 = ((*v27 >> 3) & 8) + ((v27[1] >> 4) & 4) + ((v27[2] >> 5) & 2) + ((v27[3] & 0x40) != 0);
              else
                v19 = *v29 >> 4;
              v15 = v32;
              goto LABEL_72;
            }
            goto LABEL_41;
          }
          if ( v30 > 0x28 )
            break;
          v16 += (_WORD)v30 << 6;
          if ( v16 > v12 )
            goto LABEL_32;
LABEL_41:
          ++v26;
          if ( (unsigned int)++v28 >= 4 )
            goto LABEL_44;
        }
        if ( v30 != 53 )
          goto LABEL_32;
LABEL_44:
        v24 = GlobTableBlack;
        if ( v41 != v38 )
          v23 = 0;
        if ( !v41 )
          v24 = gc_GlobTableWhite;
        v33 = v10 + (*v29 & 0xF);
        if ( v33 > 0x1Fu )
          ++v8;
        v34 = v33 - 32;
        if ( v33 <= 0x1Fu )
          v34 = v10 + (*v29 & 0xF);
        v10 = v34;
        if ( (unsigned __int64)v8 > a5 )
        {
LABEL_53:
          v14 = 2;
          goto LABEL_32;
        }
      }
    }
    if ( v20 != 5 )
      break;
    if ( v16 >= v7 && v16 )
    {
      while ( ++v11 < 0x6C3u )
      {
        v7 = v9[v11];
        if ( v7 > v16 )
          goto LABEL_63;
      }
LABEL_79:
      v14 = 3;
      goto LABEL_32;
    }
LABEL_63:
    v13 = v11 & 1;
    if ( v7 == v12 )
    {
      LOWORD(v20) = v12;
    }
    else
    {
      v20 = v9[v11 + 1];
      if ( v20 != v12 && 1 - v13 == v38 )
        LOWORD(v20) = v9[v11 + 2];
    }
    if ( (unsigned __int16)v20 <= v16 && v16 || (unsigned __int16)v20 > v12 )
    {
LABEL_32:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids, v14, v16);
      }
      SetLastError(0x570u);
      goto LABEL_37;
    }
LABEL_71:
    v16 = v20;
LABEL_72:
    v36 = v10 + v19 - 32;
    v37 = (unsigned __int64)(v8 + 1);
    if ( (unsigned __int8)(v10 + v19) <= 0x1Fu )
    {
      v37 = (unsigned __int64)v8;
      v36 = v10 + v19;
    }
    v8 = (_DWORD *)v37;
    if ( a6 && v16 == v12 && v16 )
    {
      v14 = 0;
      v10 = v36;
      goto LABEL_37;
    }
    v10 = v36;
    if ( v37 > a5 )
      goto LABEL_53;
  }
  if ( v20 != 6 )
    goto LABEL_32;
  if ( a6 )
  {
    v14 = 4;
  }
  else
  {
    if ( v16 != v12 )
      goto LABEL_32;
    v14 = 0;
  }
LABEL_37:
  *a2 = v10;
  *a1 = v8;
  return v14;
}

```

## disassembly

```asm
0x18000c1a4  mov     rax, rsp
0x18000c1a7  mov     [rax+20h], r9
0x18000c1ab  mov     [rax+18h], r8
0x18000c1af  mov     [rax+10h], rdx
0x18000c1b3  mov     [rax+8], rcx
0x18000c1b7  push    rbx
0x18000c1b8  push    rbp
0x18000c1b9  push    rsi
0x18000c1ba  push    rdi
0x18000c1bb  push    r12
0x18000c1bd  push    r13
0x18000c1bf  push    r14
0x18000c1c1  push    r15
0x18000c1c3  sub     rsp, 48h
0x18000c1c7  movzx   ebp, word ptr [r8]
0x18000c1cb  xor     r9d, r9d
0x18000c1ce  mov     rdi, [rcx]
0x18000c1d1  mov     r12, r8
0x18000c1d4  mov     sil, [rdx]
0x18000c1d7  mov     r11d, r9d
0x18000c1da  mov     r14d, [rsp+88h+arg_30]
0x18000c1e2  mov     r13b, r9b
0x18000c1e5  lea     ebx, [r9+1]
0x18000c1e9  mov     [rsp+88h+var_54], r9d
0x18000c1ee  mov     r15d, r9d
0x18000c1f1  mov     [rsp+88h+var_58], r9b
0x18000c1f6  mov     r8d, r9d
0x18000c1f9  mov     edx, [rdi]
0x18000c1fb  lea     r10, [rdi+4]
0x18000c1ff  movzx   eax, sil
0x18000c203  mov     ecx, eax
0x18000c205  shr     edx, cl
0x18000c207  cmp     sil, 19h
0x18000c20b  jbe     short loc_18000C21B
0x18000c20d  mov     ecx, 20h ; ' '
0x18000c212  sub     ecx, eax
0x18000c214  mov     eax, [r10]
0x18000c217  shl     eax, cl
0x18000c219  add     edx, eax
0x18000c21b  mov     eax, edx
0x18000c21d  lea     r9, gc_PrefTable
0x18000c224  and     eax, 7Fh
0x18000c227  mov     r9b, [rax+r9]
0x18000c22b  mov     al, r9b
0x18000c22e  and     r9b, 0Fh
0x18000c232  sar     al, 4
0x18000c235  movsx   ecx, al
0x18000c238  mov     eax, 4
0x18000c23d  cmp     cx, ax
0x18000c240  jge     loc_18000C2EC
0x18000c246  cmp     r8w, bp
0x18000c24a  jb      short loc_18000C27A
0x18000c24c  test    r8w, r8w
0x18000c250  jz      short loc_18000C27A
0x18000c252  add     r11w, bx
0x18000c256  mov     eax, 6C3h
0x18000c25b  cmp     r11w, ax
0x18000c25f  jnb     loc_18000C612
0x18000c265  movzx   eax, r11w
0x18000c269  movzx   ebp, word ptr [r12+rax*2]
0x18000c26e  cmp     bp, r8w
0x18000c272  jbe     short loc_18000C252
0x18000c274  mov     r13b, r11b
0x18000c277  and     r13b, bl
0x18000c27a  mov     dl, [rsp+88h+var_58]
0x18000c27e  cmp     dl, r13b
0x18000c281  jz      short loc_18000C28B
0x18000c283  movzx   eax, bp
0x18000c286  cmp     eax, r14d
0x18000c289  jnz     short loc_18000C290
0x18000c28b  add     cx, bp
0x18000c28e  jmp     short loc_18000C29A
0x18000c290  movzx   eax, r11w
0x18000c294  add     cx, [r12+rax*2+2]
0x18000c29a  cmp     cx, r8w
0x18000c29e  ja      short loc_18000C2AA
0x18000c2a0  test    r8w, r8w
0x18000c2a4  jnz     loc_18000C396
0x18000c2aa  movzx   eax, cx
0x18000c2ad  cmp     eax, r14d
0x18000c2b0  ja      loc_18000C396
0x18000c2b6  mov     r10, [rsp+88h+arg_18]
0x18000c2be  movzx   eax, r15w
0x18000c2c2  add     r15w, bx
0x18000c2c6  mov     [r10+rax*2], cx
0x18000c2cb  mov     eax, 6C3h
0x18000c2d0  cmp     r15w, ax
0x18000c2d4  jnb     loc_18000C612
0x18000c2da  mov     eax, ebx
0x18000c2dc  mov     [rsp+88h+var_54], r15d
0x18000c2e1  sub     al, dl
0x18000c2e3  mov     [rsp+88h+var_58], al
0x18000c2e7  jmp     loc_18000C5BE
0x18000c2ec  jnz     loc_18000C537
0x18000c2f2  movzx   edx, [rsp+88h+var_58]
0x18000c2f7  add     r9b, sil
0x18000c2fa  movzx   ecx, r9b
0x18000c2fe  mov     r12d, ebx
0x18000c301  cmp     cl, 1Fh
0x18000c304  mov     [rsp+88h+var_50], edx
0x18000c308  lea     r9, GlobTableBlack
0x18000c30f  cmova   rdi, r10
0x18000c313  xor     r10d, r10d
0x18000c316  lea     eax, [rcx-20h]
0x18000c319  mov     [rsp+88h+var_57], r10b
0x18000c31e  cmp     cl, 1Fh
0x18000c321  movzx   esi, al
0x18000c324  lea     rax, gc_GlobTableWhite
0x18000c32b  cmovbe  esi, ecx
0x18000c32e  test    dl, dl
0x18000c330  cmovz   r9, rax
0x18000c334  mov     edx, [rdi]
0x18000c336  movzx   eax, sil
0x18000c33a  mov     ecx, eax
0x18000c33c  shr     edx, cl
0x18000c33e  cmp     sil, 11h
0x18000c342  jbe     short loc_18000C352
0x18000c344  mov     ecx, 20h ; ' '
0x18000c349  sub     ecx, eax
0x18000c34b  mov     eax, [rdi+4]
0x18000c34e  shl     eax, cl
0x18000c350  add     edx, eax
0x18000c352  and     edx, 7FFFh
0x18000c358  lea     edx, [rdx+rdx*4]
0x18000c35b  add     rdx, r9
0x18000c35e  mov     r10, rdx
0x18000c361  xor     r9d, r9d
0x18000c364  lea     r15, [rdx+4]
0x18000c368  mov     al, [rdx]
0x18000c36a  and     al, 3Fh
0x18000c36c  cmp     byte ptr [rdx], 0
0x18000c36f  movzx   ecx, al
0x18000c372  jge     loc_18000C40A
0x18000c378  cmp     ecx, 28h ; '('
0x18000c37b  ja      loc_18000C478
0x18000c381  shl     cx, 6
0x18000c385  add     r8w, cx
0x18000c389  movzx   eax, r8w
0x18000c38d  cmp     eax, r14d
0x18000c390  jbe     loc_18000C466
0x18000c396  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c39d  lea     rax, WPP_GLOBAL_Control
0x18000c3a4  cmp     rcx, rax
0x18000c3a7  jz      short loc_18000C3D6
0x18000c3a9  test    byte ptr [rcx+1Ch], 2
0x18000c3ad  jz      short loc_18000C3D6
0x18000c3af  cmp     byte ptr [rcx+19h], 3
0x18000c3b3  jb      short loc_18000C3D6
0x18000c3b5  mov     rcx, [rcx+10h]
0x18000c3b9  mov     edx, 0Bh
0x18000c3be  movzx   r8d, r8w
0x18000c3c2  mov     r9d, ebx
0x18000c3c5  mov     [rsp+88h+var_68], r8d
0x18000c3ca  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000c3d1  call    WPP_SF_dd
0x18000c3d6  mov     ecx, 570h; dwErrCode
0x18000c3db  call    cs:__imp_SetLastError
0x18000c3e1  mov     rax, [rsp+88h+arg_8]
0x18000c3e9  mov     [rax], sil
0x18000c3ec  mov     rax, [rsp+88h+arg_0]
0x18000c3f4  mov     [rax], rdi
0x18000c3f7  mov     eax, ebx
0x18000c3f9  add     rsp, 48h
0x18000c3fd  pop     r15
0x18000c3ff  pop     r14
0x18000c401  pop     r13
0x18000c403  pop     r12
0x18000c405  pop     rdi
0x18000c406  pop     rsi
0x18000c407  pop     rbp
0x18000c408  pop     rbx
0x18000c409  retn
0x18000c40a  add     r8w, cx
0x18000c40e  movzx   ecx, r8w
0x18000c412  cmp     ecx, r14d
0x18000c415  ja      loc_18000C396
0x18000c41b  movzx   eax, word ptr [rsp+88h+var_54]
0x18000c420  mov     r14, [rsp+88h+arg_18]
0x18000c428  mov     [r14+rax*2], cx
0x18000c42d  mov     ecx, 6C3h
0x18000c432  mov     eax, [rsp+88h+var_54]
0x18000c436  mov     r14d, [rsp+88h+arg_30]
0x18000c43e  add     ax, bx
0x18000c441  cmp     ax, cx
0x18000c444  jnb     loc_18000C612
0x18000c44a  mov     [rsp+88h+var_54], eax
0x18000c44e  mov     eax, ebx
0x18000c450  sub     eax, [rsp+88h+var_50]
0x18000c454  mov     [rsp+88h+var_50], eax
0x18000c458  mov     al, [rsp+88h+var_57]
0x18000c45c  add     al, bl
0x18000c45e  mov     [rsp+88h+var_57], al
0x18000c462  cmp     al, 2
0x18000c464  jnb     short loc_18000C4E5
0x18000c466  add     rdx, rbx
0x18000c469  add     r9d, ebx
0x18000c46c  cmp     r9d, 4
0x18000c470  jb      loc_18000C368
0x18000c476  jmp     short loc_18000C481
0x18000c478  cmp     ecx, 35h ; '5'
0x18000c47b  jnz     loc_18000C396
0x18000c481  movzx   edx, [rsp+88h+var_58]
0x18000c486  lea     r9, GlobTableBlack
0x18000c48d  mov     r10d, [rsp+88h+var_50]
0x18000c492  xor     eax, eax
0x18000c494  cmp     r10d, edx
0x18000c497  mov     dl, [r15]
0x18000c49a  cmovnz  r12d, eax
0x18000c49e  test    r10d, r10d
0x18000c4a1  lea     rax, gc_GlobTableWhite
0x18000c4a8  cmovz   r9, rax
0x18000c4ac  and     dl, 0Fh
0x18000c4af  add     dl, sil
0x18000c4b2  cmp     dl, 1Fh
0x18000c4b5  jbe     short loc_18000C4BB
0x18000c4b7  add     rdi, 4
0x18000c4bb  lea     eax, [rdx-20h]
0x18000c4be  cmp     dl, 1Fh
0x18000c4c1  movzx   ecx, al
0x18000c4c4  movzx   eax, dl
0x18000c4c7  cmovbe  ecx, eax
0x18000c4ca  mov     sil, cl
0x18000c4cd  cmp     rdi, [rsp+88h+arg_20]
0x18000c4d5  jbe     loc_18000C334
0x18000c4db  mov     ebx, 2
0x18000c4e0  jmp     loc_18000C396
0x18000c4e5  test    r12d, r12d
0x18000c4e8  mov     r12, [rsp+88h+arg_10]
0x18000c4f0  jz      short loc_18000C4FB
0x18000c4f2  mov     r9b, [r15]
0x18000c4f5  shr     r9b, 4
0x18000c4f9  jmp     short loc_18000C52D
0x18000c4fb  mov     dl, [r10]
0x18000c4fe  add     r10, rbx
0x18000c501  shr     dl, 3
0x18000c504  and     dl, 8
0x18000c507  mov     r9b, [r10+rbx+1]
0x18000c50c  mov     al, [r10+rbx]
0x18000c510  shr     al, 5
0x18000c513  and     al, 2
0x18000c515  shr     r9b, 6
0x18000c519  and     r9b, bl
0x18000c51c  add     r9b, al
0x18000c51f  mov     al, [r10]
0x18000c522  shr     al, 4
0x18000c525  and     al, 4
0x18000c527  add     r9b, al
0x18000c52a  add     r9b, dl
0x18000c52d  mov     r15d, [rsp+88h+var_54]
0x18000c532  jmp     loc_18000C5C2
0x18000c537  cmp     ecx, 5
0x18000c53a  jnz     loc_18000C627
0x18000c540  cmp     r8w, bp
0x18000c544  jb      short loc_18000C56E
0x18000c546  test    r8w, r8w
0x18000c54a  jz      short loc_18000C56E
0x18000c54c  add     r11w, bx
0x18000c550  mov     eax, 6C3h
0x18000c555  cmp     r11w, ax
0x18000c559  jnb     loc_18000C612
0x18000c55f  movzx   eax, r11w
0x18000c563  movzx   ebp, word ptr [r12+rax*2]
0x18000c568  cmp     bp, r8w
0x18000c56c  jbe     short loc_18000C54C
0x18000c56e  mov     r13b, r11b
0x18000c571  movzx   eax, bp
0x18000c574  and     r13b, bl
0x18000c577  cmp     eax, r14d
0x18000c57a  jz      short loc_18000C59E
0x18000c57c  movzx   edx, r11w
0x18000c580  movzx   ecx, word ptr [r12+rdx*2+2]
0x18000c586  cmp     ecx, r14d
0x18000c589  jz      short loc_18000C5A2
0x18000c58b  mov     eax, ebx
0x18000c58d  sub     al, r13b
0x18000c590  cmp     al, [rsp+88h+var_58]
0x18000c594  jnz     short loc_18000C5A2
0x18000c596  movzx   ecx, word ptr [r12+rdx*2+4]
0x18000c59c  jmp     short loc_18000C5A2
0x18000c59e  movzx   ecx, r14w
0x18000c5a2  cmp     cx, r8w
0x18000c5a6  ja      short loc_18000C5B2
0x18000c5a8  test    r8w, r8w
0x18000c5ac  jnz     loc_18000C396
0x18000c5b2  movzx   eax, cx
0x18000c5b5  cmp     eax, r14d
0x18000c5b8  ja      loc_18000C396
0x18000c5be  movzx   r8d, cx
0x18000c5c2  add     r9b, sil
0x18000c5c5  movzx   ecx, r9b
0x18000c5c9  cmp     cl, 1Fh
0x18000c5cc  lea     eax, [rcx-20h]
0x18000c5cf  movzx   edx, al
0x18000c5d2  lea     rax, [rdi+4]
0x18000c5d6  cmovbe  rax, rdi
0x18000c5da  cmovbe  edx, ecx
0x18000c5dd  xor     r9d, r9d
0x18000c5e0  mov     rdi, rax
0x18000c5e3  cmp     [rsp+88h+arg_28], r9d
0x18000c5eb  jz      short loc_18000C5FC
  ... truncated ...
```
