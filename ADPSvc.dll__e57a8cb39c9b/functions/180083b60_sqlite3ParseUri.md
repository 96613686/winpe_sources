# sqlite3ParseUri

- ea: `0x180083b60`
- end: `0x18008408b`
- name: `sqlite3ParseUri`
- size: `1323`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180037680`
- `0x180058b0c`

## callees

- `0x1800034e6`
- `0x1800034f2`
- `0x180083b60`
- `0x1800a9930`
- `0x1800aa490`
- `0x1800aa540`
- `0x1800aea30`

## string_xrefs

- `0x180083c73`: `invalid uri authority: %.*s`
- `0x180083eb2`: `cache`
- `0x180083edc`: `access`

## pseudocode

```c
__int64 __fastcall sqlite3ParseUri(
        const char *a1,
        const char *a2,
        unsigned int *a3,
        __int64 *a4,
        _QWORD *a5,
        __int64 *a6)
{
  unsigned int v6; // r12d
  const char *v8; // r13
  __int64 v9; // rbx
  __int64 v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rdx
  _DWORD *v15; // rdi
  int v16; // r12d
  char *v17; // rdi
  int v18; // ecx
  const char *v19; // r8
  unsigned int v20; // r15d
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // r11
  __int64 v25; // rbx
  __int64 v26; // r10
  char v27; // dl
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  char *v32; // rcx
  __int64 v33; // rdx
  char *v34; // r14
  unsigned int v35; // ebp
  __int64 v36; // rbp
  char **v37; // rsi
  const char *v38; // r12
  int v39; // ebx
  char v40; // al
  int v41; // ecx
  bool v42; // zf
  __int64 v43; // r13
  char *v44; // rdx
  int v45; // eax
  __int64 v46; // rax
  int v47; // ecx
  int v48; // ebx
  __int64 v49; // rax
  __int64 result; // rax
  _DWORD *v51; // rdi
  int v52; // [rsp+20h] [rbp-58h]
  int v53; // [rsp+24h] [rbp-54h]
  const char *v54; // [rsp+80h] [rbp+8h]
  unsigned int v55; // [rsp+88h] [rbp+10h]

  v54 = a1;
  v6 = *a3;
  v8 = a1;
  if ( a2 )
  {
    v10 = -1;
    do
      ++v10;
    while ( a2[v10] );
    v9 = v10 & 0x3FFFFFFF;
  }
  else
  {
    v9 = 0;
  }
  if ( (v6 & 0x40) == 0 && !byte_18010EE56 || (unsigned int)v9 < 5 || *(_DWORD *)a2 != 1701603686 || a2[4] != 58 )
  {
    v51 = (_DWORD *)sqlite3_malloc64((unsigned int)(v9 + 8));
    if ( v51 )
    {
      *v51 = 0;
      v17 = (char *)(v51 + 1);
      if ( (_DWORD)v9 )
        memcpy_0(v17, a2, (unsigned int)v9);
      *(_DWORD *)&v17[v9] = 0;
      v55 = v6 & 0xFFFFFFBF;
      goto LABEL_109;
    }
    return 7;
  }
  v11 = (unsigned int)(v9 + 8);
  v12 = 0;
  do
  {
    v13 = a2[v12] == 38;
    v12 = (unsigned int)(v12 + 1);
    v11 += v13;
  }
  while ( (int)v12 < (int)v9 );
  v15 = (_DWORD *)sqlite3_malloc64(v11);
  if ( !v15 )
    return 7;
  v16 = v6 | 0x40;
  *v15 = 0;
  v17 = (char *)(v15 + 1);
  v55 = v16;
  v18 = 5;
  if ( a2[5] == 47 && a2[6] == 47 )
  {
    v19 = a2 + 7;
    v18 = 7;
    if ( a2[7] )
    {
      do
      {
        if ( a2[v18] == 47 )
          break;
        ++v18;
      }
      while ( a2[v18] );
      if ( v18 != 7 && (v18 != 16 || *(_QWORD *)v19 != 0x736F686C61636F6CLL || a2[15] != 116) )
      {
        v20 = 1;
        v21 = sqlite3_mprintf("invalid uri authority: %.*s", v18 - 7, v19);
        goto LABEL_111;
      }
    }
  }
  v22 = 0;
  v23 = 0;
  LOBYTE(v14) = a2[v18];
  if ( (_BYTE)v14 )
  {
    while ( 1 )
    {
      if ( (_BYTE)v14 == 35 )
      {
LABEL_62:
        v8 = v54;
        if ( (_DWORD)v23 == 1 )
        {
          v29 = (int)v22;
          v22 = (unsigned int)(v22 + 1);
          v17[v29] = 0;
        }
        break;
      }
      v24 = v18++;
      if ( (_BYTE)v14 == 37 )
      {
        v25 = (unsigned __int8)a2[v18];
        if ( (*((_BYTE *)&qword_1800FB500 + v25) & 8) != 0 )
        {
          v26 = (unsigned __int8)a2[v24 + 2];
          if ( (*((_BYTE *)&qword_1800FB500 + v26) & 8) != 0 )
          {
            v18 = v24 + 3;
            v14 = (((_BYTE)v26 - 7 * (((char)v26 >> 6) & 1)) & 0xF)
                + 16 * (((_BYTE)v25 - 7 * (((char)v25 >> 6) & 1)) & 0xFu);
            if ( !(_DWORD)v14 )
            {
              while ( 1 )
              {
                v27 = a2[v18];
                if ( !v27 || v27 == 35 || !(_DWORD)v23 && v27 == 63 )
                  break;
                if ( (_DWORD)v23 == 1 && (v27 == 61 || v27 == 38) || (_DWORD)v23 == 2 && v27 == 38 )
                  break;
                ++v18;
              }
              goto LABEL_61;
            }
            goto LABEL_60;
          }
        }
      }
      if ( (_DWORD)v23 == 1 )
      {
        if ( (_BYTE)v14 != 38 && (_BYTE)v14 != 61 )
          goto LABEL_60;
        if ( !v17[(int)v22 - 1] )
        {
          while ( a2[v18] && a2[v18] != 35 && a2[v18 - 1] != 38 )
            ++v18;
          goto LABEL_61;
        }
        if ( (_BYTE)v14 == 38 )
        {
          v17[(int)v22] = 0;
          LODWORD(v22) = v22 + 1;
        }
        else
        {
          v23 = 2;
        }
      }
      else
      {
        if ( ((_DWORD)v23 || (_BYTE)v14 != 63) && ((_DWORD)v23 != 2 || (_BYTE)v14 != 38) )
          goto LABEL_60;
        v23 = 1;
      }
      LOBYTE(v14) = 0;
LABEL_60:
      v28 = (int)v22;
      v22 = (unsigned int)(v22 + 1);
      v17[v28] = v14;
LABEL_61:
      LOBYTE(v14) = a2[v18];
      if ( !(_BYTE)v14 )
        goto LABEL_62;
    }
  }
  *(_DWORD *)&v17[(int)v22] = 0;
  if ( v17 )
  {
    v31 = -1;
    do
      ++v31;
    while ( v17[v31] );
    v30 = v31 & 0x3FFFFFFF;
  }
  else
  {
    v30 = 0;
  }
  v32 = &v17[v30 + 1];
  if ( !*v32 )
  {
LABEL_109:
    v20 = 0;
    v49 = sqlite3_vfs_find(v8, v14, v22, v23);
    *a4 = v49;
    if ( !v49 )
    {
      v20 = 1;
      v21 = sqlite3_mprintf("no such vfs: %s", v8);
      goto LABEL_111;
    }
    goto LABEL_112;
  }
  v20 = 3;
  while ( 1 )
  {
    v33 = -1;
    do
      ++v33;
    while ( v32[v33] );
    v14 = v33 & 0x3FFFFFFF;
    v34 = &v32[(unsigned int)(v14 + 1)];
    if ( v34 )
    {
      v36 = -1;
      do
        ++v36;
      while ( v34[v36] );
      v35 = v36 & 0x3FFFFFFF;
    }
    else
    {
      v35 = 0;
    }
    if ( (_DWORD)v14 != 3 || *(_WORD *)v32 != 26230 || v32[2] != 115 )
      break;
    v8 = &v32[(unsigned int)(v14 + 1)];
    v54 = v8;
LABEL_108:
    v32 = &v34[v35 + 1];
    if ( !*v32 )
      goto LABEL_109;
  }
  if ( (_DWORD)v14 == 5 )
  {
    v37 = 0;
    v38 = 0;
    v39 = 0;
    if ( *(_DWORD *)v32 == 1751343459 && v32[4] == 101 )
    {
      v39 = 393216;
      v37 = &off_18010E518;
      v38 = "cache";
    }
    goto LABEL_90;
  }
  if ( (_DWORD)v14 != 4 )
  {
    v37 = 0;
    v39 = 0;
    v38 = 0;
LABEL_90:
    v53 = v39;
    if ( v37 )
      goto LABEL_91;
    LOBYTE(v16) = v55;
LABEL_107:
    v8 = v54;
    goto LABEL_108;
  }
  if ( *(_DWORD *)v32 != 1701080941 )
    goto LABEL_107;
  v40 = v16;
  v37 = &off_18010E550;
  v39 = 135;
  v38 = "access";
  v53 = v40 & 0x87;
LABEL_91:
  v41 = 0;
  v42 = *v37 == 0;
  while ( 2 )
  {
    v52 = v41;
    if ( v42 )
      goto LABEL_102;
    v43 = 2LL * v41;
    v44 = v37[2 * v41];
    if ( v44 )
    {
      v46 = -1;
      do
        ++v46;
      while ( v44[v46] );
      v45 = v46 & 0x3FFFFFFF;
    }
    else
    {
      v45 = 0;
    }
    if ( v35 != v45 )
    {
LABEL_100:
      v42 = v37[2 * ++v41] == 0;
      continue;
    }
    break;
  }
  if ( memcmp_0(v34, v44, v35) )
  {
    v41 = v52;
    goto LABEL_100;
  }
  v47 = (int)v37[v43 + 1];
  if ( !v47 )
  {
LABEL_102:
    v20 = 1;
    v21 = sqlite3_mprintf("no such %s mode: %s", v38, v34);
    goto LABEL_111;
  }
  if ( (int)(v47 & 0xFFFFFF7F) <= v53 )
  {
    v48 = ~v39;
    LOBYTE(v16) = v47 | v48 & v55;
    v55 = v47 | v48 & v55;
    goto LABEL_107;
  }
  v21 = sqlite3_mprintf("%s mode not allowed: %s", v38, v34);
LABEL_111:
  *a6 = v21;
  sqlite3_free_filename(v17);
  v17 = 0;
LABEL_112:
  *a3 = v55;
  result = v20;
  *a5 = v17;
  return result;
}

```

## disassembly

```asm
0x180083b60  mov     [rsp+arg_18], r9
0x180083b65  mov     [rsp+arg_10], r8
0x180083b6a  mov     [rsp+arg_0], rcx
0x180083b6f  push    rbx
0x180083b70  push    rbp
0x180083b71  push    rsi
0x180083b72  push    rdi
0x180083b73  push    r12
0x180083b75  push    r13
0x180083b77  push    r14
0x180083b79  push    r15
0x180083b7b  sub     rsp, 38h
0x180083b7f  mov     r12d, [r8]
0x180083b82  mov     rsi, rdx
0x180083b85  mov     r13, rcx
0x180083b88  test    rdx, rdx
0x180083b8b  jnz     short loc_180083B91
0x180083b8d  xor     ebx, ebx
0x180083b8f  jmp     short loc_180083BA4
0x180083b91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180083b95  inc     rbx
0x180083b98  cmp     byte ptr [rdx+rbx], 0
0x180083b9c  jnz     short loc_180083B95
0x180083b9e  and     ebx, 3FFFFFFFh
0x180083ba4  mov     ebp, 1
0x180083ba9  test    r12b, 40h
0x180083bad  jnz     short loc_180083BBC
0x180083baf  cmp     cs:byte_18010EE56, 0
0x180083bb6  jz      loc_180084044
0x180083bbc  cmp     ebx, 5
0x180083bbf  jb      loc_180084044
0x180083bc5  cmp     dword ptr [rdx], 656C6966h
0x180083bcb  jnz     loc_180084044
0x180083bd1  cmp     byte ptr [rdx+4], 3Ah ; ':'
0x180083bd5  jnz     loc_180084044
0x180083bdb  lea     ecx, [rbx+8]
0x180083bde  xor     r8d, r8d
0x180083be1  mov     r14b, 26h ; '&'
0x180083be4  xor     edx, edx
0x180083be6  cmp     [r8+rsi], r14b
0x180083bea  setz    dl
0x180083bed  add     r8d, ebp
0x180083bf0  add     rcx, rdx
0x180083bf3  cmp     r8d, ebx
0x180083bf6  jl      short loc_180083BE4
0x180083bf8  call    sqlite3_malloc64
0x180083bfd  mov     rdi, rax
0x180083c00  test    rax, rax
0x180083c03  jz      loc_180084054
0x180083c09  xor     eax, eax
0x180083c0b  or      r12d, 40h
0x180083c0f  mov     [rdi], eax
0x180083c11  mov     dl, 2Fh ; '/'
0x180083c13  add     rdi, 4
0x180083c17  mov     [rsp+78h+arg_8], r12d
0x180083c1f  lea     ecx, [rax+5]
0x180083c22  cmp     [rsi+5], dl
0x180083c25  jnz     short loc_180083C84
0x180083c27  cmp     [rsi+6], dl
0x180083c2a  jnz     short loc_180083C84
0x180083c2c  lea     r8, [rsi+7]
0x180083c30  lea     ecx, [rax+7]
0x180083c33  cmp     [r8], al
0x180083c36  jz      short loc_180083C84
0x180083c38  movsxd  rax, ecx
0x180083c3b  cmp     [rax+rsi], dl
0x180083c3e  jz      short loc_180083C4B
0x180083c40  add     ecx, ebp
0x180083c42  movsxd  rax, ecx
0x180083c45  cmp     byte ptr [rax+rsi], 0
0x180083c49  jnz     short loc_180083C38
0x180083c4b  cmp     ecx, 7
0x180083c4e  jz      short loc_180083C84
0x180083c50  cmp     ecx, 10h
0x180083c53  jnz     short loc_180083C6D
0x180083c55  mov     rax, 736F686C61636F6Ch
0x180083c5f  cmp     rax, [r8]
0x180083c62  jnz     short loc_180083C6D
0x180083c64  lea     eax, [rcx+64h]
0x180083c67  cmp     al, [r8+8]
0x180083c6b  jz      short loc_180083C84
0x180083c6d  lea     edx, [rcx-7]
0x180083c70  mov     r15d, ebp
0x180083c73  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x180083c7a  call    sqlite3_mprintf
0x180083c7f  jmp     loc_180083FEB
0x180083c84  movsxd  rax, ecx
0x180083c87  xor     r8d, r8d
0x180083c8a  xor     r9d, r9d
0x180083c8d  mov     dl, [rax+rsi]
0x180083c90  test    dl, dl
0x180083c92  jz      loc_180083DF4
0x180083c98  mov     r15b, 23h ; '#'
0x180083c9b  lea     r13, qword_1800FB500
0x180083ca2  cmp     dl, r15b
0x180083ca5  jz      loc_180083DDD
0x180083cab  movsxd  r11, ecx
0x180083cae  add     ecx, ebp
0x180083cb0  cmp     dl, 25h ; '%'
0x180083cb3  jnz     loc_180083D60
0x180083cb9  movsxd  rax, ecx
0x180083cbc  movzx   ebx, byte ptr [rax+rsi]
0x180083cc0  test    byte ptr [rbx+r13], 8
0x180083cc5  jz      loc_180083D60
0x180083ccb  movzx   r10d, byte ptr [r11+rsi+2]
0x180083cd1  test    byte ptr [r10+r13], 8
0x180083cd6  jz      loc_180083D60
0x180083cdc  mov     al, bl
0x180083cde  mov     dl, bl
0x180083ce0  sar     al, 6
0x180083ce3  and     al, bpl
0x180083ce6  movzx   eax, al
0x180083ce9  imul    ecx, eax, 7
0x180083cec  mov     al, r10b
0x180083cef  sar     al, 6
0x180083cf2  and     al, bpl
0x180083cf5  movzx   eax, al
0x180083cf8  sub     dl, cl
0x180083cfa  imul    ecx, eax, 7
0x180083cfd  mov     al, r10b
0x180083d00  and     edx, 0Fh
0x180083d03  shl     edx, 4
0x180083d06  sub     al, cl
0x180083d08  lea     ecx, [r11+3]
0x180083d0c  and     eax, 0Fh
0x180083d0f  add     edx, eax
0x180083d11  jnz     loc_180083DC6
0x180083d17  jmp     short loc_180083D54
0x180083d19  cmp     dl, r15b
0x180083d1c  jz      loc_180083DCF
0x180083d22  test    r9d, r9d
0x180083d25  jnz     short loc_180083D30
0x180083d27  cmp     dl, 3Fh ; '?'
0x180083d2a  jz      loc_180083DCF
0x180083d30  cmp     r9d, ebp
0x180083d33  jnz     short loc_180083D47
0x180083d35  cmp     dl, 3Dh ; '='
0x180083d38  jz      loc_180083DCF
0x180083d3e  cmp     dl, r14b
0x180083d41  jz      loc_180083DCF
0x180083d47  cmp     r9d, 2
0x180083d4b  jnz     short loc_180083D52
0x180083d4d  cmp     dl, r14b
0x180083d50  jz      short loc_180083DCF
0x180083d52  add     ecx, ebp
0x180083d54  movsxd  rax, ecx
0x180083d57  mov     dl, [rax+rsi]
0x180083d5a  test    dl, dl
0x180083d5c  jnz     short loc_180083D19
0x180083d5e  jmp     short loc_180083DCF
0x180083d60  cmp     r9d, ebp
0x180083d63  jnz     short loc_180083DAC
0x180083d65  cmp     dl, r14b
0x180083d68  jz      short loc_180083D6F
0x180083d6a  cmp     dl, 3Dh ; '='
0x180083d6d  jnz     short loc_180083DC6
0x180083d6f  movsxd  rax, r8d
0x180083d72  cmp     byte ptr [rax+rdi-1], 0
0x180083d77  jz      short loc_180083D99
0x180083d79  cmp     dl, r14b
0x180083d7c  jnz     short loc_180083DA4
0x180083d7e  mov     byte ptr [rax+rdi], 0
0x180083d82  add     r8d, ebp
0x180083d85  jmp     short loc_180083DC4
0x180083d87  movsxd  rax, ecx
0x180083d8a  cmp     [rax+rsi], r15b
0x180083d8e  jz      short loc_180083DCF
0x180083d90  cmp     [rax+rsi-1], r14b
0x180083d95  jz      short loc_180083DCF
0x180083d97  add     ecx, ebp
0x180083d99  movsxd  rax, ecx
0x180083d9c  cmp     byte ptr [rax+rsi], 0
0x180083da0  jnz     short loc_180083D87
0x180083da2  jmp     short loc_180083DCF
0x180083da4  mov     r9d, 2
0x180083daa  jmp     short loc_180083DC4
0x180083dac  test    r9d, r9d
0x180083daf  jnz     short loc_180083DB6
0x180083db1  cmp     dl, 3Fh ; '?'
0x180083db4  jz      short loc_180083DC1
0x180083db6  cmp     r9d, 2
0x180083dba  jnz     short loc_180083DC6
0x180083dbc  cmp     dl, r14b
0x180083dbf  jnz     short loc_180083DC6
0x180083dc1  mov     r9d, ebp
0x180083dc4  xor     dl, dl
0x180083dc6  movsxd  rax, r8d
0x180083dc9  add     r8d, ebp
0x180083dcc  mov     [rax+rdi], dl
0x180083dcf  movsxd  rax, ecx
0x180083dd2  mov     dl, [rax+rsi]
0x180083dd5  test    dl, dl
0x180083dd7  jnz     loc_180083CA2
0x180083ddd  mov     r13, [rsp+78h+arg_0]
0x180083de5  cmp     r9d, ebp
0x180083de8  jnz     short loc_180083DF4
0x180083dea  movsxd  rax, r8d
0x180083ded  add     r8d, ebp
0x180083df0  mov     byte ptr [rax+rdi], 0
0x180083df4  xor     ecx, ecx
0x180083df6  movsxd  rax, r8d
0x180083df9  mov     [rax+rdi], ecx
0x180083dfc  test    rdi, rdi
0x180083dff  jnz     short loc_180083E05
0x180083e01  xor     eax, eax
0x180083e03  jmp     short loc_180083E16
0x180083e05  or      rax, 0FFFFFFFFFFFFFFFFh
0x180083e09  inc     rax
0x180083e0c  cmp     [rdi+rax], cl
0x180083e0f  jnz     short loc_180083E09
0x180083e11  and     eax, 3FFFFFFFh
0x180083e16  lea     rcx, [rax+1]
0x180083e1a  add     rcx, rdi
0x180083e1d  cmp     byte ptr [rcx], 0
0x180083e20  jz      loc_180083FBE
0x180083e26  mov     r15d, 3
0x180083e2c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180083e30  inc     rdx
0x180083e33  cmp     byte ptr [rcx+rdx], 0
0x180083e37  jnz     short loc_180083E30
0x180083e39  and     edx, 3FFFFFFFh
0x180083e3f  lea     r14d, [rdx+1]
0x180083e43  add     r14, rcx
0x180083e46  jnz     short loc_180083E4C
0x180083e48  xor     ebp, ebp
0x180083e4a  jmp     short loc_180083E60
0x180083e4c  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180083e50  inc     rbp
0x180083e53  cmp     byte ptr [r14+rbp], 0
0x180083e58  jnz     short loc_180083E50
0x180083e5a  and     ebp, 3FFFFFFFh
0x180083e60  cmp     edx, r15d
0x180083e63  jnz     short loc_180083E89
0x180083e65  mov     eax, 6676h
0x180083e6a  cmp     ax, [rcx]
0x180083e6d  jnz     short loc_180083E89
0x180083e6f  mov     eax, 73h ; 's'
0x180083e74  cmp     al, [rcx+2]
0x180083e77  jnz     short loc_180083E89
0x180083e79  mov     r13, r14
0x180083e7c  mov     [rsp+78h+arg_0], r14
0x180083e84  jmp     loc_180083FAA
0x180083e89  cmp     edx, 5
0x180083e8c  jnz     short loc_180083EBB
0x180083e8e  xor     esi, esi
0x180083e90  xor     r12d, r12d
0x180083e93  xor     ebx, ebx
0x180083e95  mov     eax, 68636163h
0x180083e9a  cmp     eax, [rcx]
0x180083e9c  jnz     short loc_180083EF2
0x180083e9e  lea     eax, [rdx+60h]
0x180083ea1  cmp     al, [rcx+4]
0x180083ea4  jnz     short loc_180083EF2
0x180083ea6  mov     ebx, 60000h
0x180083eab  lea     rsi, off_18010E518; "shared"
0x180083eb2  lea     r12, aCache; "cache"
0x180083eb9  jmp     short loc_180083EF2
0x180083ebb  cmp     edx, 4
0x180083ebe  jnz     short loc_180083EEB
0x180083ec0  mov     eax, 65646F6Dh
0x180083ec5  cmp     eax, [rcx]
0x180083ec7  jnz     loc_180083FA2
0x180083ecd  mov     eax, r12d
0x180083ed0  lea     rsi, off_18010E550; "ro"
0x180083ed7  mov     ebx, 87h
0x180083edc  lea     r12, aAccess; "access"
0x180083ee3  and     eax, ebx
0x180083ee5  mov     [rsp+78h+var_54], eax
0x180083ee9  jmp     short loc_180083EFF
0x180083eeb  xor     esi, esi
0x180083eed  xor     ebx, ebx
0x180083eef  xor     r12d, r12d
0x180083ef2  mov     [rsp+78h+var_54], ebx
0x180083ef6  test    rsi, rsi
0x180083ef9  jz      loc_180083F9A
0x180083eff  xor     ecx, ecx
0x180083f01  cmp     [rsi], rcx
0x180083f04  jmp     short loc_180083F4F
0x180083f06  movsxd  r13, ecx
0x180083f09  add     r13, r13
0x180083f0c  mov     rdx, [rsi+r13*8]; Buf2
0x180083f10  test    rdx, rdx
0x180083f13  jnz     short loc_180083F19
0x180083f15  xor     eax, eax
0x180083f17  jmp     short loc_180083F2B
0x180083f19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180083f1d  inc     rax
0x180083f20  cmp     byte ptr [rdx+rax], 0
0x180083f24  jnz     short loc_180083F1D
0x180083f26  and     eax, 3FFFFFFFh
0x180083f2b  cmp     ebp, eax
0x180083f2d  jnz     short loc_180083F42
0x180083f2f  mov     r8d, ebp; Size
0x180083f32  mov     rcx, r14; Buf1
0x180083f35  call    memcmp_0
0x180083f3a  test    eax, eax
0x180083f3c  jz      short loc_180083F67
0x180083f3e  mov     ecx, [rsp+78h+var_58]
0x180083f42  inc     ecx
0x180083f44  movsxd  rax, ecx
  ... truncated ...
```
