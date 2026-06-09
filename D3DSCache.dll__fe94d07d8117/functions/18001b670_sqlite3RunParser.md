# sqlite3RunParser

- ea: `0x18001b670`
- end: `0x18001bc26`
- name: `sqlite3RunParser`
- size: `1462`
- prototype: ``
- caller_count: `4`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x18001a9c0`
- `0x18003cc7c`
- `0x180073744`
- `0x180095340`

## callees

- `0x180012470`
- `0x180014464`
- `0x18001ae70`
- `0x18001b670`
- `0x18001bc30`
- `0x18002d570`
- `0x180034900`
- `0x18003af40`
- `0x18003c8d4`
- `0x180042488`
- `0x180042500`
- `0x1800449f0`
- `0x180045374`
- `0x1800629d0`
- `0x18007e48c`
- `0x18007ed94`
- `0x1800a6638`
- `0x1800a6710`
- `0x1800a6764`
- `0x1800a8010`

## string_xrefs

- `0x18001ba0a`: `incomplete input`
- `0x18001ba58`: `unrecognized token: "%T"`

## pseudocode

```c
__int64 __fastcall sqlite3RunParser(__int64 *a1, _BYTE *a2)
{
  __int64 v2; // r14
  int v5; // edi
  int v6; // esi
  _BYTE *v7; // r13
  int Token; // eax
  int v9; // r12d
  unsigned int v10; // esi
  int v11; // eax
  unsigned __int16 *v12; // rax
  _QWORD *v13; // r13
  unsigned __int16 v14; // di
  __int128 v15; // xmm6
  unsigned __int16 v16; // cx
  __int64 v17; // rdi
  int v18; // r9d
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  __int64 v21; // rdi
  char *v22; // rcx
  _QWORD *v23; // rdi
  char *v24; // rdi
  char *i; // rcx
  __int64 v26; // rdx
  const char *v27; // rax
  __int64 v28; // rcx
  unsigned int v29; // esi
  const char *v30; // rax
  __int64 v31; // rdi
  int v32; // eax
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 result; // rax
  int v36; // [rsp+30h] [rbp-D0h] BYREF
  int v37; // [rsp+34h] [rbp-CCh]
  __int128 v38; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE *v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+58h] [rbp-A8h]
  int v41; // [rsp+5Ch] [rbp-A4h]
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  char *v43; // [rsp+70h] [rbp-90h] BYREF
  _QWORD *v44; // [rsp+78h] [rbp-88h]
  char *v45; // [rsp+80h] [rbp-80h]
  char *v46; // [rsp+88h] [rbp-78h]
  _DWORD v47[594]; // [rsp+90h] [rbp-70h] BYREF
  char v48; // [rsp+9D8h] [rbp+8D8h] BYREF

  v2 = *a1;
  v36 = 0;
  v5 = -1;
  memset_0(&v43, 0, 0x980u);
  v6 = *(_DWORD *)(v2 + 140);
  if ( !*(_DWORD *)(v2 + 216) )
    *(_DWORD *)(v2 + 408) = 0;
  *((_DWORD *)a1 + 6) = 0;
  v46 = (char *)v47;
  v45 = &v48;
  v43 = (char *)v47;
  a1[43] = (__int64)a2;
  v44 = a1;
  v47[0] = 0;
  v7 = *(_BYTE **)(v2 + 352);
  v39 = v7;
  *(_QWORD *)(v2 + 352) = a1;
  while ( 1 )
  {
    Token = sqlite3GetToken(a2, &v36);
    v9 = Token;
    v37 = v6 - Token;
    if ( v6 - Token < 0 )
      break;
    v10 = v36;
    if ( v36 < 164 )
      goto LABEL_32;
    if ( *(_DWORD *)(v2 + 408) )
    {
      *((_DWORD *)a1 + 6) = 9;
      goto LABEL_68;
    }
    v10 = v36;
    if ( v36 == 184 )
    {
      v6 = v37;
      a2 += Token;
    }
    else
    {
      if ( *a2 )
      {
        switch ( v36 )
        {
          case 164:
            *(_QWORD *)&v38 = a2 + 6;
            if ( (unsigned int)getToken(&v38) == 59 )
            {
              v10 = 164;
              if ( (unsigned int)getToken(&v38) != 24 )
                v10 = 59;
            }
            else
            {
              v10 = 59;
            }
            v36 = v10;
            goto LABEL_32;
          case 165:
            *(_QWORD *)&v38 = a2 + 4;
            if ( v5 == 23 )
            {
              v11 = getToken(&v38);
              if ( v11 == 22 || v11 == 59 )
              {
                v10 = 165;
LABEL_30:
                v36 = v10;
                goto LABEL_32;
              }
            }
LABEL_29:
            v10 = 59;
            goto LABEL_30;
          case 166:
            *(_QWORD *)&v38 = a2 + 6;
            if ( v5 == 23 && (unsigned int)getToken(&v38) == 22 )
              goto LABEL_30;
            goto LABEL_29;
        }
        if ( v36 != 183 )
        {
          v41 = 0;
          v39 = a2;
          v40 = Token;
          sqlite3ErrorMsg(a1, "unrecognized token: \"%T\"", &v39);
          goto LABEL_69;
        }
      }
      else
      {
        if ( v5 == 1 )
        {
          v10 = 0;
        }
        else
        {
          if ( !v5 )
            goto LABEL_69;
          v10 = 1;
        }
        v36 = v10;
        v9 = 0;
      }
LABEL_32:
      v12 = (unsigned __int16 *)v43;
      v13 = v44;
      a1[36] = (__int64)a2;
      *((_DWORD *)a1 + 74) = v9;
      v14 = *v12;
      v15 = *((_OWORD *)a1 + 18);
      while ( 1 )
      {
        if ( v14 <= 0x246u )
        {
          v16 = v10;
          v17 = 2LL * v14;
          v18 = *(unsigned __int16 *)((char *)&qword_1800B9DC0[8] + v17);
          while ( 1 )
          {
            v19 = (unsigned int)v16 + v18;
            if ( word_1800B8AF0[v19] == v16 )
            {
              v14 = word_1800B7930[v19];
              goto LABEL_43;
            }
            if ( !word_1800BA290[v16] )
              break;
            v16 = word_1800BA290[v16];
          }
          v20 = (unsigned int)v16 + v18 - (unsigned __int64)v16;
          if ( word_1800B8BBA[v20] == 101 && v16 )
            v14 = word_1800B79FA[v20];
          else
            v14 = *(_WORD *)((char *)qword_1800B6760 + v17);
        }
LABEL_43:
        if ( v14 < 0x4E9u )
          break;
        v21 = (unsigned int)v14 - 1257;
        if ( !*((_BYTE *)qword_1800B6DC0 + v21) && v43 >= v45 && (unsigned int)yyGrowStack(&v43) )
          goto LABEL_52;
        v38 = v15;
        v14 = yy_reduce((__int64 *)&v43, v21, v10, &v38, v13);
      }
      if ( v14 > 0x4E5u )
      {
        if ( v14 == 1255 )
        {
          v43 -= 24;
        }
        else
        {
          v23 = v44;
          v38 = v15;
          v42 = v15;
          if ( *(_BYTE *)v15 )
            sqlite3ErrorMsg(v44, "near \"%T\": syntax error", &v38);
          else
            sqlite3ErrorMsg(v44, "incomplete input");
          v44 = v23;
          yy_destructor(&v43, (unsigned __int16)v10, &v42);
        }
      }
      else
      {
        v22 = v43 + 24;
        v43 = v22;
        if ( v22 > v45 )
        {
          if ( (unsigned int)yyGrowStack(&v43) )
          {
            v43 -= 24;
LABEL_52:
            yyStackOverflow(&v43);
            goto LABEL_63;
          }
          v22 = v43;
        }
        *((_WORD *)v22 + 1) = v10;
        *(_OWORD *)(v22 + 8) = v15;
        if ( v14 > 0x246u )
          v14 += 412;
        *(_WORD *)v22 = v14;
      }
LABEL_63:
      v7 = v39;
      a2 += v9;
      if ( *((_DWORD *)a1 + 6) )
        goto LABEL_69;
      v5 = v36;
      v6 = v37;
    }
  }
  *((_DWORD *)a1 + 6) = 18;
LABEL_68:
  ++*((_DWORD *)a1 + 12);
LABEL_69:
  v24 = v43;
  for ( i = v46; v24 > i; v24 -= 24 )
  {
    v26 = *((unsigned __int16 *)v24 + 1);
    if ( (unsigned __int16)v26 >= 0xCDu )
    {
      yy_destructor(&v43, v26, v24 + 8);
      i = v46;
    }
  }
  if ( i != (char *)v47 )
    sqlite3_free(i);
  if ( *(_BYTE *)(v2 + 103) )
    *((_DWORD *)a1 + 6) = 7;
  v27 = (const char *)a1[1];
  if ( v27 )
  {
LABEL_81:
    sqlite3_log(*((unsigned int *)a1 + 6), "%s in \"%s\"", v27, (const char *)a1[43]);
    v29 = 1;
  }
  else
  {
    v28 = *((unsigned int *)a1 + 6);
    v29 = 0;
    if ( (_DWORD)v28 && (_DWORD)v28 != 101 )
    {
      v30 = (const char *)sqlite3ErrStr(v28);
      v27 = (const char *)sqlite3MPrintf(v2, "%s", v30);
      a1[1] = (__int64)v27;
      goto LABEL_81;
    }
  }
  v31 = a1[50];
  a1[43] = (__int64)a2;
  if ( v31 )
  {
    if ( dword_1800C6970 )
    {
      sqlite3_mutex_enter(xmmword_1800C78A0);
      v32 = ((__int64 (__fastcall *)(__int64))xmmword_1800C69A8)(v31);
      --qword_1800C7958;
      qword_1800C7910 -= v32;
      ((void (__fastcall *)(__int64))xmmword_1800C6998)(v31);
      sqlite3_mutex_leave(xmmword_1800C78A0);
    }
    else
    {
      ((void (__fastcall *)(__int64))xmmword_1800C6998)(v31);
    }
  }
  v33 = a1[44];
  if ( v33 && !*((_BYTE *)a1 + 308) )
    sqlite3DeleteTable(v2, v33);
  v34 = a1[46];
  if ( v34 && *((_BYTE *)a1 + 308) < 2u )
    sqlite3DeleteTrigger(v2, v34);
  if ( a1[41] )
    sqlite3DbNNFreeNN(v2);
  result = v29;
  *(_QWORD *)(v2 + 352) = v7;
  return result;
}

```

## disassembly

```asm
0x18001b670  mov     [rsp-8+arg_10], rbx
0x18001b675  push    rbp
0x18001b676  push    rsi
0x18001b677  push    rdi
0x18001b678  push    r12
0x18001b67a  push    r13
0x18001b67c  push    r14
0x18001b67e  push    r15
0x18001b680  lea     rbp, [rsp-910h]
0x18001b688  sub     rsp, 0A10h
0x18001b68f  movaps  [rsp+0A40h+var_40], xmm6
0x18001b697  mov     rax, cs:__security_cookie
0x18001b69e  xor     rax, rsp
0x18001b6a1  mov     [rbp+940h+var_50], rax
0x18001b6a8  mov     r14, [rcx]
0x18001b6ab  mov     r15, rdx
0x18001b6ae  mov     rbx, rcx
0x18001b6b1  xor     r12d, r12d
0x18001b6b4  xor     edx, edx; Val
0x18001b6b6  mov     [rsp+0A40h+var_A10], r12d
0x18001b6bb  lea     rcx, [rsp+0A40h+var_9D0]; void *
0x18001b6c0  mov     r8d, 980h; Size
0x18001b6c6  mov     edi, 0FFFFFFFFh
0x18001b6cb  call    memset_0
0x18001b6d0  mov     esi, [r14+8Ch]
0x18001b6d7  cmp     [r14+0D8h], r12d
0x18001b6de  jnz     short loc_18001B6E7
0x18001b6e0  mov     [r14+198h], r12d
0x18001b6e7  lea     rax, [rbp+940h+var_9B0]
0x18001b6eb  mov     [rbx+18h], r12d
0x18001b6ef  mov     [rbp+940h+var_9B8], rax
0x18001b6f3  lea     rax, [rbp+940h+var_68]
0x18001b6fa  mov     [rbp+940h+var_9C0], rax
0x18001b6fe  lea     rax, [rbp+940h+var_9B0]
0x18001b702  mov     [rsp+0A40h+var_9D0], rax
0x18001b707  mov     [rbx+158h], r15
0x18001b70e  mov     [rsp+0A40h+var_9C8], rbx
0x18001b713  mov     [rbp+940h+var_9B0], r12d
0x18001b717  mov     r13, [r14+160h]
0x18001b71e  mov     [rsp+0A40h+var_9F0], r13
0x18001b723  mov     [r14+160h], rbx
0x18001b72a  lea     rdx, [rsp+0A40h+var_A10]
0x18001b72f  mov     rcx, r15
0x18001b732  call    sqlite3GetToken
0x18001b737  movsxd  r12, eax
0x18001b73a  sub     esi, r12d
0x18001b73d  mov     [rsp+0A40h+var_A0C], esi
0x18001b741  js      loc_18001BA7C
0x18001b747  mov     esi, [rsp+0A40h+var_A10]
0x18001b74b  cmp     esi, 0A4h
0x18001b751  jl      loc_18001B857
0x18001b757  mov     ecx, [r14+198h]
0x18001b75e  test    ecx, ecx
0x18001b760  jnz     loc_18001BA73
0x18001b766  mov     esi, [rsp+0A40h+var_A10]
0x18001b76a  cmp     esi, 0B8h
0x18001b770  jnz     short loc_18001B77B
0x18001b772  mov     esi, [rsp+0A40h+var_A0C]
0x18001b776  add     r15, r12
0x18001b779  jmp     short loc_18001B72A
0x18001b77b  cmp     byte ptr [r15], 0
0x18001b77f  jnz     short loc_18001B7A3
0x18001b781  cmp     edi, 1
0x18001b784  jnz     short loc_18001B78A
0x18001b786  xor     esi, esi
0x18001b788  jmp     short loc_18001B797
0x18001b78a  test    edi, edi
0x18001b78c  jz      loc_18001BA86
0x18001b792  mov     esi, 1
0x18001b797  mov     [rsp+0A40h+var_A10], esi
0x18001b79b  xor     r12d, r12d
0x18001b79e  jmp     loc_18001B857
0x18001b7a3  cmp     esi, 0A4h
0x18001b7a9  jnz     short loc_18001B7EA
0x18001b7ab  lea     rax, [r15+6]
0x18001b7af  lea     rcx, [rsp+0A40h+var_A00]
0x18001b7b4  mov     qword ptr [rsp+0A40h+var_A00], rax
0x18001b7b9  call    getToken
0x18001b7be  cmp     eax, 3Bh ; ';'
0x18001b7c1  jz      short loc_18001B7CA
0x18001b7c3  mov     esi, 3Bh ; ';'
0x18001b7c8  jmp     short loc_18001B7E4
0x18001b7ca  lea     rcx, [rsp+0A40h+var_A00]
0x18001b7cf  call    getToken
0x18001b7d4  cmp     eax, 18h
0x18001b7d7  mov     esi, 0A4h
0x18001b7dc  mov     eax, 3Bh ; ';'
0x18001b7e1  cmovnz  esi, eax
0x18001b7e4  mov     [rsp+0A40h+var_A10], esi
0x18001b7e8  jmp     short loc_18001B857
0x18001b7ea  cmp     esi, 0A5h
0x18001b7f0  jnz     short loc_18001B81B
0x18001b7f2  lea     rax, [r15+4]
0x18001b7f6  mov     qword ptr [rsp+0A40h+var_A00], rax
0x18001b7fb  cmp     edi, 17h
0x18001b7fe  jnz     short loc_18001B840
0x18001b800  lea     rcx, [rsp+0A40h+var_A00]
0x18001b805  call    getToken
0x18001b80a  cmp     eax, 16h
0x18001b80d  jz      short loc_18001B814
0x18001b80f  cmp     eax, 3Bh ; ';'
0x18001b812  jnz     short loc_18001B840
0x18001b814  mov     esi, 0A5h
0x18001b819  jmp     short loc_18001B845
0x18001b81b  cmp     esi, 0A6h
0x18001b821  jnz     short loc_18001B84B
0x18001b823  lea     rax, [r15+6]
0x18001b827  mov     qword ptr [rsp+0A40h+var_A00], rax
0x18001b82c  cmp     edi, 17h
0x18001b82f  jnz     short loc_18001B840
0x18001b831  lea     rcx, [rsp+0A40h+var_A00]
0x18001b836  call    getToken
0x18001b83b  cmp     eax, 16h
0x18001b83e  jz      short loc_18001B845
0x18001b840  mov     esi, 3Bh ; ';'
0x18001b845  mov     [rsp+0A40h+var_A10], esi
0x18001b849  jmp     short loc_18001B857
0x18001b84b  cmp     esi, 0B7h
0x18001b851  jnz     loc_18001BA4B
0x18001b857  mov     rax, [rsp+0A40h+var_9D0]
0x18001b85c  mov     r13, [rsp+0A40h+var_9C8]
0x18001b861  mov     [rbx+120h], r15
0x18001b868  mov     [rbx+128h], r12d
0x18001b86f  movzx   edi, word ptr [rax]
0x18001b872  movups  xmm6, xmmword ptr [rbx+120h]
0x18001b879  mov     eax, 246h
0x18001b87e  cmp     di, ax
0x18001b881  ja      short loc_18001B8FD
0x18001b883  movzx   eax, di
0x18001b886  lea     r11, __ImageBase
0x18001b88d  movzx   ecx, si
0x18001b890  lea     rdi, [rax+rax]
0x18001b894  movzx   r9d, word ptr [rdi+r11+0B9E00h]
0x18001b89d  movzx   r8d, cx
0x18001b8a1  lea     eax, [r8+r9]
0x18001b8a5  mov     edx, eax
0x18001b8a7  cmp     ds:rva word_1800B8AF0[r11+rax*2], cx
0x18001b8b0  jz      short loc_18001B8F4
0x18001b8b2  movzx   eax, cx
0x18001b8b5  movzx   r10d, ds:rva word_1800BA290[r11+rax*2]
0x18001b8be  test    r10w, r10w
0x18001b8c2  jz      short loc_18001B8CA
0x18001b8c4  movzx   ecx, r10w
0x18001b8c8  jmp     short loc_18001B89D
0x18001b8ca  sub     rdx, r8
0x18001b8cd  cmp     ds:rva word_1800B8BBA[r11+rdx*2], 65h ; 'e'
0x18001b8d7  jnz     short loc_18001B8E9
0x18001b8d9  test    cx, cx
0x18001b8dc  jz      short loc_18001B8E9
0x18001b8de  movzx   edi, ds:rva word_1800B79FA[r11+rdx*2]
0x18001b8e7  jmp     short loc_18001B8FD
0x18001b8e9  movzx   edi, word ptr [rdi+r11+0B6760h]
0x18001b8f2  jmp     short loc_18001B8FD
0x18001b8f4  movzx   edi, ds:rva word_1800B7930[r11+rax*2]
0x18001b8fd  mov     eax, 4E9h
0x18001b902  cmp     di, ax
0x18001b905  jb      short loc_18001B961
0x18001b907  movzx   edi, di
0x18001b90a  lea     rcx, __ImageBase
0x18001b911  add     edi, 0FFFFFB17h
0x18001b917  cmp     byte ptr [rdi+rcx+0B6DC0h], 0
0x18001b91f  jnz     short loc_18001B93A
0x18001b921  mov     rax, [rbp+940h+var_9C0]
0x18001b925  cmp     [rsp+0A40h+var_9D0], rax
0x18001b92a  jb      short loc_18001B93A
0x18001b92c  lea     rcx, [rsp+0A40h+var_9D0]
0x18001b931  call    yyGrowStack
0x18001b936  test    eax, eax
0x18001b938  jnz     short loc_18001B993
0x18001b93a  lea     r9, [rsp+0A40h+var_A00]
0x18001b93f  movdqa  [rsp+0A40h+var_A00], xmm6
0x18001b945  mov     r8d, esi
0x18001b948  mov     [rsp+0A40h+var_A20], r13
0x18001b94d  mov     edx, edi
0x18001b94f  lea     rcx, [rsp+0A40h+var_9D0]
0x18001b954  call    yy_reduce
0x18001b959  movzx   edi, ax
0x18001b95c  jmp     loc_18001B879
0x18001b961  mov     eax, 4E5h
0x18001b966  cmp     di, ax
0x18001b969  ja      short loc_18001B9C7
0x18001b96b  mov     rcx, [rsp+0A40h+var_9D0]
0x18001b970  add     rcx, 18h
0x18001b974  mov     [rsp+0A40h+var_9D0], rcx
0x18001b979  cmp     rcx, [rbp+940h+var_9C0]
0x18001b97d  jbe     short loc_18001B9A7
0x18001b97f  lea     rcx, [rsp+0A40h+var_9D0]
0x18001b984  call    yyGrowStack
0x18001b989  test    eax, eax
0x18001b98b  jz      short loc_18001B9A2
0x18001b98d  sub     [rsp+0A40h+var_9D0], 18h
0x18001b993  lea     rcx, [rsp+0A40h+var_9D0]
0x18001b998  call    yyStackOverflow
0x18001b99d  jmp     loc_18001BA2D
0x18001b9a2  mov     rcx, [rsp+0A40h+var_9D0]
0x18001b9a7  mov     eax, 19Ch
0x18001b9ac  mov     [rcx+2], si
0x18001b9b0  add     eax, edi
0x18001b9b2  mov     edx, 246h
0x18001b9b7  cmp     di, dx
0x18001b9ba  movups  xmmword ptr [rcx+8], xmm6
0x18001b9be  cmova   di, ax
0x18001b9c2  mov     [rcx], di
0x18001b9c5  jmp     short loc_18001BA2D
0x18001b9c7  mov     eax, 4E7h
0x18001b9cc  cmp     di, ax
0x18001b9cf  jnz     short loc_18001B9D9
0x18001b9d1  sub     [rsp+0A40h+var_9D0], 18h
0x18001b9d7  jmp     short loc_18001BA2D
0x18001b9d9  mov     rdi, [rsp+0A40h+var_9C8]
0x18001b9de  movq    rax, xmm6
0x18001b9e3  movdqa  [rsp+0A40h+var_A00], xmm6
0x18001b9e9  mov     rcx, rdi
0x18001b9ec  movdqa  [rsp+0A40h+var_9E0], xmm6
0x18001b9f2  cmp     byte ptr [rax], 0
0x18001b9f5  jz      short loc_18001BA0A
0x18001b9f7  lea     r8, [rsp+0A40h+var_A00]
0x18001b9fc  lea     rdx, aNearTSyntaxErr; "near \"%T\": syntax error"
0x18001ba03  call    sqlite3ErrorMsg
0x18001ba08  jmp     short loc_18001BA16
0x18001ba0a  lea     rdx, aIncompleteInpu; "incomplete input"
0x18001ba11  call    sqlite3ErrorMsg
0x18001ba16  lea     r8, [rsp+0A40h+var_9E0]
0x18001ba1b  mov     [rsp+0A40h+var_9C8], rdi
0x18001ba20  movzx   edx, si
0x18001ba23  lea     rcx, [rsp+0A40h+var_9D0]
0x18001ba28  call    yy_destructor
0x18001ba2d  mov     r13, [rsp+0A40h+var_9F0]
0x18001ba32  movsxd  rax, r12d
0x18001ba35  add     r15, rax
0x18001ba38  cmp     dword ptr [rbx+18h], 0
0x18001ba3c  jnz     short loc_18001BA86
0x18001ba3e  mov     edi, [rsp+0A40h+var_A10]
0x18001ba42  mov     esi, [rsp+0A40h+var_A0C]
0x18001ba46  jmp     loc_18001B72A
0x18001ba4b  lea     r8, [rsp+0A40h+var_9F0]
0x18001ba50  mov     [rsp+0A40h+var_9E4], 0
0x18001ba58  lea     rdx, aUnrecognizedTo_0; "unrecognized token: \"%T\""
0x18001ba5f  mov     [rsp+0A40h+var_9F0], r15
0x18001ba64  mov     rcx, rbx
0x18001ba67  mov     [rsp+0A40h+var_9E8], r12d
0x18001ba6c  call    sqlite3ErrorMsg
0x18001ba71  jmp     short loc_18001BA86
0x18001ba73  mov     dword ptr [rbx+18h], 9
0x18001ba7a  jmp     short loc_18001BA83
0x18001ba7c  mov     dword ptr [rbx+18h], 12h
0x18001ba83  inc     dword ptr [rbx+30h]
0x18001ba86  mov     rdi, [rsp+0A40h+var_9D0]
0x18001ba8b  mov     rcx, [rbp+940h+var_9B8]
0x18001ba8f  cmp     rdi, rcx
0x18001ba92  jbe     short loc_18001BABD
0x18001ba94  mov     esi, 0CDh
0x18001ba99  movzx   edx, word ptr [rdi+2]
0x18001ba9d  cmp     dx, si
0x18001baa0  jb      short loc_18001BAB4
0x18001baa2  lea     r8, [rdi+8]
0x18001baa6  lea     rcx, [rsp+0A40h+var_9D0]
0x18001baab  call    yy_destructor
0x18001bab0  mov     rcx, [rbp+940h+var_9B8]
0x18001bab4  sub     rdi, 18h
0x18001bab8  cmp     rdi, rcx
0x18001babb  ja      short loc_18001BA99
0x18001babd  lea     rax, [rbp+940h+var_9B0]
0x18001bac1  cmp     rcx, rax
0x18001bac4  jz      short loc_18001BACB
0x18001bac6  call    sqlite3_free
0x18001bacb  cmp     byte ptr [r14+67h], 0
0x18001bad0  jz      short loc_18001BAD9
0x18001bad2  mov     dword ptr [rbx+18h], 7
0x18001bad9  mov     rax, [rbx+8]
0x18001badd  test    rax, rax
0x18001bae0  jnz     short loc_18001BB0B
0x18001bae2  mov     ecx, [rbx+18h]
0x18001bae5  xor     esi, esi
0x18001bae7  test    ecx, ecx
0x18001bae9  jz      short loc_18001BB29
0x18001baeb  cmp     ecx, 65h ; 'e'
0x18001baee  jz      short loc_18001BB29
0x18001baf0  call    sqlite3ErrStr
0x18001baf5  mov     r8, rax
0x18001baf8  lea     rdx, aS_10; "%s"
0x18001baff  mov     rcx, r14
0x18001bb02  call    sqlite3MPrintf
0x18001bb07  mov     [rbx+8], rax
0x18001bb0b  mov     r9, [rbx+158h]
0x18001bb12  lea     rdx, aSInS; "%s in \"%s\""
0x18001bb19  mov     ecx, [rbx+18h]
0x18001bb1c  mov     r8, rax
0x18001bb1f  call    sqlite3_log
0x18001bb24  mov     esi, 1
0x18001bb29  mov     rdi, [rbx+190h]
0x18001bb30  mov     [rbx+158h], r15
0x18001bb37  test    rdi, rdi
0x18001bb3a  jz      short loc_18001BB9D
0x18001bb3c  cmp     cs:dword_1800C6970, 0
0x18001bb43  jz      short loc_18001BB8E
0x18001bb45  mov     rcx, qword ptr cs:xmmword_1800C78A0
0x18001bb4c  call    sqlite3_mutex_enter
0x18001bb51  mov     rax, qword ptr cs:xmmword_1800C69A8
0x18001bb58  mov     rcx, rdi
  ... truncated ...
```
