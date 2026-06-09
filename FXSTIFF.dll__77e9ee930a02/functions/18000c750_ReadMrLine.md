# ReadMrLine

- ea: `0x18000c750`
- end: `0x18000cc09`
- name: `ReadMrLine`
- size: `1209`
- prototype: `__int64 __fastcall(_DWORD **, unsigned __int8 *, unsigned __int16 *, __int64, unsigned __int64, int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a130`
- `0x18000bb50`
- `0x18000d060`
- `0x18000da70`

## callees

- `0x18000a070`
- `0x18000c750`

## import_xrefs

- `KERNEL32!SetLastError` at `0x18000c987`
- `KERNEL32!SetLastError` at `0x18000c987`

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
0x18000c750  mov     rax, rsp
0x18000c753  mov     [rax+20h], r9
0x18000c757  mov     [rax+18h], r8
0x18000c75b  mov     [rax+10h], rdx
0x18000c75f  mov     [rax+8], rcx
0x18000c763  push    rbx
0x18000c764  push    rbp
0x18000c765  push    rsi
0x18000c766  push    rdi
0x18000c767  push    r12
0x18000c769  push    r13
0x18000c76b  push    r14
0x18000c76d  push    r15
0x18000c76f  sub     rsp, 48h
0x18000c773  movzx   ebp, word ptr [r8]
0x18000c777  xor     r9d, r9d
0x18000c77a  mov     rdi, [rcx]
0x18000c77d  mov     r12, r8
0x18000c780  mov     sil, [rdx]
0x18000c783  mov     r11d, r9d
0x18000c786  mov     r14d, [rsp+88h+arg_30]
0x18000c78e  mov     r13b, r9b
0x18000c791  lea     ebx, [r9+1]
0x18000c795  mov     [rsp+88h+var_54], r9d
0x18000c79a  mov     r15d, r9d
0x18000c79d  mov     [rsp+88h+var_58], r9b
0x18000c7a2  mov     r8d, r9d
0x18000c7a5  mov     edx, [rdi]
0x18000c7a7  lea     r10, [rdi+4]
0x18000c7ab  movzx   eax, sil
0x18000c7af  mov     ecx, eax
0x18000c7b1  shr     edx, cl
0x18000c7b3  cmp     sil, 19h
0x18000c7b7  jbe     short loc_18000C7C7
0x18000c7b9  mov     ecx, 20h ; ' '
0x18000c7be  sub     ecx, eax
0x18000c7c0  mov     eax, [r10]
0x18000c7c3  shl     eax, cl
0x18000c7c5  add     edx, eax
0x18000c7c7  mov     eax, edx
0x18000c7c9  lea     r9, gc_PrefTable
0x18000c7d0  and     eax, 7Fh
0x18000c7d3  mov     r9b, [rax+r9]
0x18000c7d7  mov     al, r9b
0x18000c7da  and     r9b, 0Fh
0x18000c7de  sar     al, 4
0x18000c7e1  movsx   ecx, al
0x18000c7e4  mov     eax, 4
0x18000c7e9  cmp     cx, ax
0x18000c7ec  jge     loc_18000C898
0x18000c7f2  cmp     r8w, bp
0x18000c7f6  jb      short loc_18000C826
0x18000c7f8  test    r8w, r8w
0x18000c7fc  jz      short loc_18000C826
0x18000c7fe  add     r11w, bx
0x18000c802  mov     eax, 6C3h
0x18000c807  cmp     r11w, ax
0x18000c80b  jnb     loc_18000CBC5
0x18000c811  movzx   eax, r11w
0x18000c815  movzx   ebp, word ptr [r12+rax*2]
0x18000c81a  cmp     bp, r8w
0x18000c81e  jbe     short loc_18000C7FE
0x18000c820  mov     r13b, r11b
0x18000c823  and     r13b, bl
0x18000c826  mov     dl, [rsp+88h+var_58]
0x18000c82a  cmp     dl, r13b
0x18000c82d  jz      short loc_18000C837
0x18000c82f  movzx   eax, bp
0x18000c832  cmp     eax, r14d
0x18000c835  jnz     short loc_18000C83C
0x18000c837  add     cx, bp
0x18000c83a  jmp     short loc_18000C846
0x18000c83c  movzx   eax, r11w
0x18000c840  add     cx, [r12+rax*2+2]
0x18000c846  cmp     cx, r8w
0x18000c84a  ja      short loc_18000C856
0x18000c84c  test    r8w, r8w
0x18000c850  jnz     loc_18000C942
0x18000c856  movzx   eax, cx
0x18000c859  cmp     eax, r14d
0x18000c85c  ja      loc_18000C942
0x18000c862  mov     r10, [rsp+88h+arg_18]
0x18000c86a  movzx   eax, r15w
0x18000c86e  add     r15w, bx
0x18000c872  mov     [r10+rax*2], cx
0x18000c877  mov     eax, 6C3h
0x18000c87c  cmp     r15w, ax
0x18000c880  jnb     loc_18000CBC5
0x18000c886  mov     eax, ebx
0x18000c888  mov     [rsp+88h+var_54], r15d
0x18000c88d  sub     al, dl
0x18000c88f  mov     [rsp+88h+var_58], al
0x18000c893  jmp     loc_18000CB71
0x18000c898  jnz     loc_18000CAEA
0x18000c89e  movzx   edx, [rsp+88h+var_58]
0x18000c8a3  add     r9b, sil
0x18000c8a6  movzx   ecx, r9b
0x18000c8aa  mov     r12d, ebx
0x18000c8ad  cmp     cl, 1Fh
0x18000c8b0  mov     [rsp+88h+var_50], edx
0x18000c8b4  lea     r9, GlobTableBlack
0x18000c8bb  cmova   rdi, r10
0x18000c8bf  xor     r10d, r10d
0x18000c8c2  lea     eax, [rcx-20h]
0x18000c8c5  mov     [rsp+88h+var_57], r10b
0x18000c8ca  cmp     cl, 1Fh
0x18000c8cd  movzx   esi, al
0x18000c8d0  lea     rax, gc_GlobTableWhite
0x18000c8d7  cmovbe  esi, ecx
0x18000c8da  test    dl, dl
0x18000c8dc  cmovz   r9, rax
0x18000c8e0  mov     edx, [rdi]
0x18000c8e2  movzx   eax, sil
0x18000c8e6  mov     ecx, eax
0x18000c8e8  shr     edx, cl
0x18000c8ea  cmp     sil, 11h
0x18000c8ee  jbe     short loc_18000C8FE
0x18000c8f0  mov     ecx, 20h ; ' '
0x18000c8f5  sub     ecx, eax
0x18000c8f7  mov     eax, [rdi+4]
0x18000c8fa  shl     eax, cl
0x18000c8fc  add     edx, eax
0x18000c8fe  and     edx, 7FFFh
0x18000c904  lea     edx, [rdx+rdx*4]
0x18000c907  add     rdx, r9
0x18000c90a  mov     r10, rdx
0x18000c90d  xor     r9d, r9d
0x18000c910  lea     r15, [rdx+4]
0x18000c914  mov     al, [rdx]
0x18000c916  and     al, 3Fh
0x18000c918  cmp     byte ptr [rdx], 0
0x18000c91b  movzx   ecx, al
0x18000c91e  jge     loc_18000C9BD
0x18000c924  cmp     ecx, 28h ; '('
0x18000c927  ja      loc_18000CA2B
0x18000c92d  shl     cx, 6
0x18000c931  add     r8w, cx
0x18000c935  movzx   eax, r8w
0x18000c939  cmp     eax, r14d
0x18000c93c  jbe     loc_18000CA19
0x18000c942  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c949  lea     rax, WPP_GLOBAL_Control
0x18000c950  cmp     rcx, rax
0x18000c953  jz      short loc_18000C982
0x18000c955  test    byte ptr [rcx+1Ch], 2
0x18000c959  jz      short loc_18000C982
0x18000c95b  cmp     byte ptr [rcx+19h], 3
0x18000c95f  jb      short loc_18000C982
0x18000c961  mov     rcx, [rcx+10h]
0x18000c965  mov     edx, 0Bh
0x18000c96a  movzx   r8d, r8w
0x18000c96e  mov     r9d, ebx
0x18000c971  mov     [rsp+88h+var_68], r8d
0x18000c976  lea     r8, WPP_111dc5fed54a36c06a62ddb32e537446_Traceguids
0x18000c97d  call    WPP_SF_dd
0x18000c982  mov     ecx, 570h; dwErrCode
0x18000c987  call    cs:__imp_SetLastError
0x18000c98e  nop     dword ptr [rax+rax+00h]
0x18000c993  mov     rax, [rsp+88h+arg_8]
0x18000c99b  mov     [rax], sil
0x18000c99e  mov     rax, [rsp+88h+arg_0]
0x18000c9a6  mov     [rax], rdi
0x18000c9a9  mov     eax, ebx
0x18000c9ab  add     rsp, 48h
0x18000c9af  pop     r15
0x18000c9b1  pop     r14
0x18000c9b3  pop     r13
0x18000c9b5  pop     r12
0x18000c9b7  pop     rdi
0x18000c9b8  pop     rsi
0x18000c9b9  pop     rbp
0x18000c9ba  pop     rbx
0x18000c9bb  retn
0x18000c9bd  add     r8w, cx
0x18000c9c1  movzx   ecx, r8w
0x18000c9c5  cmp     ecx, r14d
0x18000c9c8  ja      loc_18000C942
0x18000c9ce  movzx   eax, word ptr [rsp+88h+var_54]
0x18000c9d3  mov     r14, [rsp+88h+arg_18]
0x18000c9db  mov     [r14+rax*2], cx
0x18000c9e0  mov     ecx, 6C3h
0x18000c9e5  mov     eax, [rsp+88h+var_54]
0x18000c9e9  mov     r14d, [rsp+88h+arg_30]
0x18000c9f1  add     ax, bx
0x18000c9f4  cmp     ax, cx
0x18000c9f7  jnb     loc_18000CBC5
0x18000c9fd  mov     [rsp+88h+var_54], eax
0x18000ca01  mov     eax, ebx
0x18000ca03  sub     eax, [rsp+88h+var_50]
0x18000ca07  mov     [rsp+88h+var_50], eax
0x18000ca0b  mov     al, [rsp+88h+var_57]
0x18000ca0f  add     al, bl
0x18000ca11  mov     [rsp+88h+var_57], al
0x18000ca15  cmp     al, 2
0x18000ca17  jnb     short loc_18000CA98
0x18000ca19  add     rdx, rbx
0x18000ca1c  add     r9d, ebx
0x18000ca1f  cmp     r9d, 4
0x18000ca23  jb      loc_18000C914
0x18000ca29  jmp     short loc_18000CA34
0x18000ca2b  cmp     ecx, 35h ; '5'
0x18000ca2e  jnz     loc_18000C942
0x18000ca34  movzx   edx, [rsp+88h+var_58]
0x18000ca39  lea     r9, GlobTableBlack
0x18000ca40  mov     r10d, [rsp+88h+var_50]
0x18000ca45  xor     eax, eax
0x18000ca47  cmp     r10d, edx
0x18000ca4a  mov     dl, [r15]
0x18000ca4d  cmovnz  r12d, eax
0x18000ca51  test    r10d, r10d
0x18000ca54  lea     rax, gc_GlobTableWhite
0x18000ca5b  cmovz   r9, rax
0x18000ca5f  and     dl, 0Fh
0x18000ca62  add     dl, sil
0x18000ca65  cmp     dl, 1Fh
0x18000ca68  jbe     short loc_18000CA6E
0x18000ca6a  add     rdi, 4
0x18000ca6e  lea     eax, [rdx-20h]
0x18000ca71  cmp     dl, 1Fh
0x18000ca74  movzx   ecx, al
0x18000ca77  movzx   eax, dl
0x18000ca7a  cmovbe  ecx, eax
0x18000ca7d  mov     sil, cl
0x18000ca80  cmp     rdi, [rsp+88h+arg_20]
0x18000ca88  jbe     loc_18000C8E0
0x18000ca8e  mov     ebx, 2
0x18000ca93  jmp     loc_18000C942
0x18000ca98  test    r12d, r12d
0x18000ca9b  mov     r12, [rsp+88h+arg_10]
0x18000caa3  jz      short loc_18000CAAE
0x18000caa5  mov     r9b, [r15]
0x18000caa8  shr     r9b, 4
0x18000caac  jmp     short loc_18000CAE0
0x18000caae  mov     dl, [r10]
0x18000cab1  add     r10, rbx
0x18000cab4  shr     dl, 3
0x18000cab7  and     dl, 8
0x18000caba  mov     r9b, [r10+rbx+1]
0x18000cabf  mov     al, [r10+rbx]
0x18000cac3  shr     al, 5
0x18000cac6  and     al, 2
0x18000cac8  shr     r9b, 6
0x18000cacc  and     r9b, bl
0x18000cacf  add     r9b, al
0x18000cad2  mov     al, [r10]
0x18000cad5  shr     al, 4
0x18000cad8  and     al, 4
0x18000cada  add     r9b, al
0x18000cadd  add     r9b, dl
0x18000cae0  mov     r15d, [rsp+88h+var_54]
0x18000cae5  jmp     loc_18000CB75
0x18000caea  cmp     ecx, 5
0x18000caed  jnz     loc_18000CBDA
0x18000caf3  cmp     r8w, bp
0x18000caf7  jb      short loc_18000CB21
0x18000caf9  test    r8w, r8w
0x18000cafd  jz      short loc_18000CB21
0x18000caff  add     r11w, bx
0x18000cb03  mov     eax, 6C3h
0x18000cb08  cmp     r11w, ax
0x18000cb0c  jnb     loc_18000CBC5
0x18000cb12  movzx   eax, r11w
0x18000cb16  movzx   ebp, word ptr [r12+rax*2]
0x18000cb1b  cmp     bp, r8w
0x18000cb1f  jbe     short loc_18000CAFF
0x18000cb21  mov     r13b, r11b
0x18000cb24  movzx   eax, bp
0x18000cb27  and     r13b, bl
0x18000cb2a  cmp     eax, r14d
0x18000cb2d  jz      short loc_18000CB51
0x18000cb2f  movzx   edx, r11w
0x18000cb33  movzx   ecx, word ptr [r12+rdx*2+2]
0x18000cb39  cmp     ecx, r14d
0x18000cb3c  jz      short loc_18000CB55
0x18000cb3e  mov     eax, ebx
0x18000cb40  sub     al, r13b
0x18000cb43  cmp     al, [rsp+88h+var_58]
0x18000cb47  jnz     short loc_18000CB55
0x18000cb49  movzx   ecx, word ptr [r12+rdx*2+4]
0x18000cb4f  jmp     short loc_18000CB55
0x18000cb51  movzx   ecx, r14w
0x18000cb55  cmp     cx, r8w
0x18000cb59  ja      short loc_18000CB65
0x18000cb5b  test    r8w, r8w
0x18000cb5f  jnz     loc_18000C942
0x18000cb65  movzx   eax, cx
0x18000cb68  cmp     eax, r14d
0x18000cb6b  ja      loc_18000C942
0x18000cb71  movzx   r8d, cx
0x18000cb75  add     r9b, sil
0x18000cb78  movzx   ecx, r9b
0x18000cb7c  cmp     cl, 1Fh
0x18000cb7f  lea     eax, [rcx-20h]
0x18000cb82  movzx   edx, al
0x18000cb85  lea     rax, [rdi+4]
0x18000cb89  cmovbe  rax, rdi
0x18000cb8d  cmovbe  edx, ecx
0x18000cb90  xor     r9d, r9d
0x18000cb93  mov     rdi, rax
0x18000cb96  cmp     [rsp+88h+arg_28], r9d
  ... truncated ...
```
