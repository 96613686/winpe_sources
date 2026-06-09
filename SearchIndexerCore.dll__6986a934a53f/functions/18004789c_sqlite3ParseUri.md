# sqlite3ParseUri

- ea: `0x18004789c`
- end: `0x180047d91`
- name: `sqlite3ParseUri`
- size: `1269`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003182c`
- `0x18007a180`

## callees

- `0x18001eb90`
- `0x1800310a0`
- `0x180031d50`
- `0x180038910`
- `0x18004789c`
- `0x180047da0`
- `0x1800af614`
- `0x1800af620`

## string_xrefs

- `0x180047a2b`: `invalid uri authority: %.*s`
- `0x180047c58`: `cache`
- `0x180047c83`: `access`

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
  unsigned int v6; // r15d
  const char *v7; // rbp
  __int64 *v8; // r13
  unsigned int *v9; // r12
  int v11; // eax
  __int64 v12; // rdx
  size_t v13; // rsi
  unsigned int v14; // r14d
  _DWORD *v15; // rbx
  _BYTE *v16; // rbx
  unsigned int v17; // r15d
  __int64 v18; // rax
  __int64 result; // rax
  int v20; // ecx
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rdx
  _DWORD *v24; // rbx
  int v25; // ecx
  const char *v26; // r8
  __int64 v27; // rdx
  __int64 v28; // rax
  int v29; // r8d
  int v30; // r9d
  int v31; // edx
  __int64 v32; // r11
  __int64 v33; // rsi
  __int64 v34; // r10
  char v35; // dl
  __int64 v36; // rax
  __int64 v37; // rax
  char *i; // rdx
  int v39; // eax
  __int64 v40; // rdx
  const char *v41; // rsi
  unsigned __int16 *v42; // rdx
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  char **v46; // rbp
  const char *v47; // r15
  int v48; // edi
  int v49; // ecx
  char v50; // r12
  int v51; // r12d
  int j; // eax
  __int64 v53; // r13
  char *v54; // rcx
  int v55; // eax
  const void *v56; // rcx
  int v57; // r8d
  int v58; // ecx
  unsigned int v59; // [rsp+20h] [rbp-48h]
  int v60; // [rsp+24h] [rbp-44h]
  int v61; // [rsp+28h] [rbp-40h]
  const char *v62; // [rsp+70h] [rbp+8h]

  v62 = a1;
  v6 = *a3;
  v7 = a1;
  v8 = a4;
  v9 = a3;
  v11 = sqlite3Strlen30(a2);
  v13 = v11;
  v14 = 1;
  if ( ((v6 & 0x40) != 0 || byte_1800D0876) && v11 >= 5 )
  {
    v20 = *(_DWORD *)v12 - 1701603686;
    if ( *(_DWORD *)v12 == 1701603686 )
      v20 = *(unsigned __int8 *)(v12 + 4) - 58;
    if ( !v20 )
    {
      v21 = 0;
      v22 = v11 + 8;
      do
      {
        v23 = a2[v21] == 38;
        v21 = (unsigned int)(v21 + 1);
        v22 += v23;
      }
      while ( (int)v21 < v11 );
      v24 = (_DWORD *)sqlite3_malloc64(v22);
      if ( v24 )
      {
        v17 = v6 | 0x40;
        *v24 = 0;
        v16 = v24 + 1;
        v59 = v17;
        v25 = 5;
        if ( a2[5] == 47 && a2[6] == 47 )
        {
          v26 = a2 + 7;
          v25 = 7;
          if ( a2[7] )
          {
            do
            {
              if ( a2[v25] == 47 )
                break;
              ++v25;
            }
            while ( a2[v25] );
            if ( v25 != 7 )
            {
              if ( v25 != 16 )
                goto LABEL_27;
              v27 = 0x736F686C61636F6CLL - *(_QWORD *)v26;
              if ( *(_QWORD *)v26 == 0x736F686C61636F6CLL )
                v27 = 116LL - *((unsigned __int8 *)a2 + 15);
              if ( v27 )
              {
LABEL_27:
                v28 = sqlite3_mprintf("invalid uri authority: %.*s", v25 - 7, v26);
                goto LABEL_100;
              }
            }
          }
        }
        v29 = 0;
        v30 = 0;
        LOBYTE(v31) = a2[v25];
        if ( (_BYTE)v31 )
        {
          while ( 1 )
          {
            if ( (_BYTE)v31 == 35 )
            {
LABEL_66:
              if ( v30 == 1 )
              {
                v37 = v29++;
                v16[v37] = 0;
              }
              break;
            }
            v32 = v25++;
            if ( (_BYTE)v31 == 37 )
            {
              v33 = (unsigned __int8)a2[v25];
              if ( (*((_BYTE *)&qword_1800B4FF0 + v33) & 8) != 0 )
              {
                v34 = (unsigned __int8)a2[v32 + 2];
                if ( (*((_BYTE *)&qword_1800B4FF0 + v34) & 8) != 0 )
                {
                  v25 = v32 + 3;
                  v31 = (((_BYTE)v34 - 7 * (((char)v34 >> 6) & 1)) & 0xF)
                      + 16 * (((_BYTE)v33 - 7 * (((char)v33 >> 6) & 1)) & 0xF);
                  if ( !v31 )
                  {
                    while ( 1 )
                    {
                      v35 = a2[v25];
                      if ( !v35 || v35 == 35 || !v30 && v35 == 63 )
                        break;
                      if ( v30 == 1 && (v35 == 61 || v35 == 38) || v30 == 2 && v35 == 38 )
                        break;
                      ++v25;
                    }
                    goto LABEL_65;
                  }
                  goto LABEL_64;
                }
              }
            }
            if ( v30 == 1 )
            {
              if ( (_BYTE)v31 != 38 && (_BYTE)v31 != 61 )
                goto LABEL_64;
              if ( !v16[v29 - 1] )
              {
                while ( a2[v25] && a2[v25] != 35 && a2[v25 - 1] != 38 )
                  ++v25;
                goto LABEL_65;
              }
              if ( (_BYTE)v31 == 38 )
                v16[v29++] = 0;
              else
                v30 = 2;
            }
            else
            {
              if ( (v30 || (_BYTE)v31 != 63) && (v30 != 2 || (_BYTE)v31 != 38) )
                goto LABEL_64;
              v30 = 1;
            }
            LOBYTE(v31) = 0;
LABEL_64:
            v36 = v29++;
            v16[v36] = v31;
LABEL_65:
            LOBYTE(v31) = a2[v25];
            if ( !(_BYTE)v31 )
              goto LABEL_66;
          }
        }
        *(_DWORD *)&v16[v29] = 0;
        v14 = 3;
        for ( i = &v16[(int)(sqlite3Strlen30(v16) + 1)]; ; i = (char *)&v41[v60 + 1] )
        {
          if ( !*i )
          {
            v7 = v62;
            v9 = a3;
            v8 = a4;
            goto LABEL_7;
          }
          v39 = sqlite3Strlen30(i);
          v41 = (const char *)(v40 + v39 + 1);
          v60 = sqlite3Strlen30(v41);
          if ( v43 == 3 )
          {
            v44 = *v42;
            v45 = 26230 - v44;
            if ( v44 == 26230 )
              v45 = 115 - *((unsigned __int8 *)v42 + 2);
            if ( !v45 )
            {
              v62 = v41;
              continue;
            }
          }
          if ( v43 == 5 )
            break;
          if ( v43 != 4 )
          {
            v46 = 0;
            v48 = 0;
            v47 = 0;
LABEL_89:
            v51 = v48;
            if ( v46 )
              goto LABEL_83;
            v17 = v59;
            continue;
          }
          if ( *(_DWORD *)v42 == 1701080941 )
          {
            v50 = v17;
            v46 = &off_1800D0690;
            v48 = 135;
            v47 = "access";
            v51 = v50 & 0x87;
LABEL_83:
            for ( j = 0; ; j = v61 + 1 )
            {
              v53 = 2LL * j;
              v61 = j;
              v54 = v46[2 * j];
              if ( !v54 )
                goto LABEL_96;
              v55 = sqlite3Strlen30(v54);
              if ( v57 == v55 && !memcmp_0(v41, v56, v57) )
                break;
            }
            v58 = (int)v46[v53 + 1];
            if ( !v58 )
            {
LABEL_96:
              v14 = 1;
              v28 = sqlite3_mprintf("no such %s mode: %s", v47, v41);
              goto LABEL_97;
            }
            if ( (int)(v58 & 0xFFFFFF7F) <= v51 )
            {
              v17 = v58 | v59 & ~v48;
              v59 = v17;
              continue;
            }
            v28 = sqlite3_mprintf("%s mode not allowed: %s", v47, v41);
LABEL_97:
            v17 = v59;
            v9 = a3;
LABEL_100:
            *a6 = v28;
            sqlite3_free_filename(v16);
            v16 = 0;
            goto LABEL_8;
          }
        }
        v46 = 0;
        v47 = 0;
        v48 = 0;
        v49 = 1751343459 - *(_DWORD *)v42;
        if ( *(_DWORD *)v42 == 1751343459 )
          v49 = 101 - *((unsigned __int8 *)v42 + 4);
        if ( !v49 )
        {
          v48 = 393216;
          v46 = &off_1800D0658;
          v47 = "cache";
        }
        goto LABEL_89;
      }
      return 7;
    }
  }
  v15 = (_DWORD *)sqlite3_malloc64(v11 + 8);
  if ( !v15 )
    return 7;
  *v15 = 0;
  v16 = v15 + 1;
  if ( (_DWORD)v13 )
    memcpy_0(v16, a2, v13);
  *(_DWORD *)&v16[v13] = 0;
  v17 = v6 & 0xFFFFFFBF;
LABEL_7:
  v14 = 0;
  v18 = sqlite3_vfs_find(v7);
  *v8 = v18;
  if ( !v18 )
  {
    v14 = 1;
    v28 = sqlite3_mprintf("no such vfs: %s", v7);
    goto LABEL_100;
  }
LABEL_8:
  result = v14;
  *v9 = v17;
  *a5 = v16;
  return result;
}

```

## disassembly

```asm
0x18004789c  mov     rax, rsp
0x18004789f  mov     [rax+10h], rbx
0x1800478a3  mov     [rax+20h], r9
0x1800478a7  mov     [rax+18h], r8
0x1800478ab  mov     [rax+8], rcx
0x1800478af  push    rbp
0x1800478b0  push    rsi
0x1800478b1  push    rdi
0x1800478b2  push    r12
0x1800478b4  push    r13
0x1800478b6  push    r14
0x1800478b8  push    r15
0x1800478ba  sub     rsp, 30h
0x1800478be  mov     r15d, [r8]
0x1800478c1  mov     rbp, rcx
0x1800478c4  mov     rcx, rdx
0x1800478c7  mov     r13, r9
0x1800478ca  mov     r12, r8
0x1800478cd  mov     rdi, rdx
0x1800478d0  call    sqlite3Strlen30
0x1800478d5  movsxd  rsi, eax
0x1800478d8  mov     r14d, 1
0x1800478de  test    r15b, 40h
0x1800478e2  jnz     loc_18004796D
0x1800478e8  cmp     cs:byte_1800D0876, 0
0x1800478ef  jnz     short loc_18004796D
0x1800478f1  lea     eax, [rsi+8]
0x1800478f4  movsxd  rcx, eax
0x1800478f7  call    sqlite3_malloc64
0x1800478fc  mov     rbx, rax
0x1800478ff  test    rax, rax
0x180047902  jz      short loc_180047966
0x180047904  xor     eax, eax
0x180047906  mov     [rbx], eax
0x180047908  add     rbx, 4
0x18004790c  test    esi, esi
0x18004790e  jz      short loc_18004791E
0x180047910  mov     r8, rsi; Size
0x180047913  mov     rdx, rdi; Src
0x180047916  mov     rcx, rbx; void *
0x180047919  call    memcpy_0
0x18004791e  xor     ecx, ecx
0x180047920  mov     [rsi+rbx], ecx
0x180047923  and     r15d, 0FFFFFFBFh
0x180047927  mov     rcx, rbp
0x18004792a  xor     r14d, r14d
0x18004792d  call    sqlite3_vfs_find
0x180047932  mov     [r13+0], rax
0x180047936  test    rax, rax
0x180047939  jz      loc_180047D62
0x18004793f  mov     rcx, [rsp+68h+arg_20]
0x180047947  mov     eax, r14d
0x18004794a  mov     [r12], r15d
0x18004794e  mov     [rcx], rbx
0x180047951  mov     rbx, [rsp+68h+arg_8]
0x180047956  add     rsp, 30h
0x18004795a  pop     r15
0x18004795c  pop     r14
0x18004795e  pop     r13
0x180047960  pop     r12
0x180047962  pop     rdi
0x180047963  pop     rsi
0x180047964  pop     rbp
0x180047965  retn
0x180047966  mov     eax, 7
0x18004796b  jmp     short loc_180047951
0x18004796d  cmp     esi, 5
0x180047970  jl      loc_1800478F1
0x180047976  mov     ecx, [rdx]
0x180047978  sub     ecx, 656C6966h
0x18004797e  jnz     short loc_180047987
0x180047980  movzx   ecx, byte ptr [rdx+4]
0x180047984  sub     ecx, 3Ah ; ':'
0x180047987  test    ecx, ecx
0x180047989  jnz     loc_1800478F1
0x18004798f  lea     eax, [rsi+8]
0x180047992  xor     r8d, r8d
0x180047995  movsxd  rcx, eax
0x180047998  mov     bpl, 26h ; '&'
0x18004799b  xor     edx, edx
0x18004799d  cmp     [r8+rdi], bpl
0x1800479a1  setz    dl
0x1800479a4  add     r8d, r14d
0x1800479a7  add     rcx, rdx
0x1800479aa  cmp     r8d, esi
0x1800479ad  jl      short loc_18004799B
0x1800479af  call    sqlite3_malloc64
0x1800479b4  mov     rbx, rax
0x1800479b7  test    rax, rax
0x1800479ba  jz      short loc_180047966
0x1800479bc  xor     eax, eax
0x1800479be  or      r15d, 40h
0x1800479c2  mov     [rbx], eax
0x1800479c4  mov     dl, 2Fh ; '/'
0x1800479c6  add     rbx, 4
0x1800479ca  mov     [rsp+68h+var_48], r15d
0x1800479cf  lea     ecx, [rax+5]
0x1800479d2  cmp     [rdi+5], dl
0x1800479d5  jnz     short loc_180047A3C
0x1800479d7  cmp     [rdi+6], dl
0x1800479da  jnz     short loc_180047A3C
0x1800479dc  lea     r8, [rdi+7]
0x1800479e0  lea     ecx, [rax+7]
0x1800479e3  cmp     [r8], al
0x1800479e6  jz      short loc_180047A3C
0x1800479e8  movsxd  rax, ecx
0x1800479eb  cmp     [rax+rdi], dl
0x1800479ee  jz      short loc_1800479FC
0x1800479f0  add     ecx, r14d
0x1800479f3  movsxd  rax, ecx
0x1800479f6  cmp     byte ptr [rax+rdi], 0
0x1800479fa  jnz     short loc_1800479E8
0x1800479fc  cmp     ecx, 7
0x1800479ff  jz      short loc_180047A3C
0x180047a01  cmp     ecx, 10h
0x180047a04  jnz     short loc_180047A28
0x180047a06  mov     rdx, 736F686C61636F6Ch
0x180047a10  sub     rdx, [r8]
0x180047a13  jnz     short loc_180047A23
0x180047a15  lea     eax, [rcx+64h]
0x180047a18  movzx   edx, al
0x180047a1b  movzx   eax, byte ptr [r8+8]
0x180047a20  sub     rdx, rax
0x180047a23  test    rdx, rdx
0x180047a26  jz      short loc_180047A3C
0x180047a28  lea     edx, [rcx-7]
0x180047a2b  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x180047a32  call    sqlite3_mprintf
0x180047a37  jmp     loc_180047D77
0x180047a3c  movsxd  rax, ecx
0x180047a3f  xor     r8d, r8d
0x180047a42  xor     r9d, r9d
0x180047a45  mov     dl, [rax+rdi]
0x180047a48  test    dl, dl
0x180047a4a  jz      loc_180047BA8
0x180047a50  mov     r12b, 23h ; '#'
0x180047a53  lea     r13, qword_1800B4FF0
0x180047a5a  cmp     dl, r12b
0x180047a5d  jz      loc_180047B99
0x180047a63  movsxd  r11, ecx
0x180047a66  add     ecx, r14d
0x180047a69  cmp     dl, 25h ; '%'
0x180047a6c  jnz     loc_180047B1B
0x180047a72  movsxd  rax, ecx
0x180047a75  movzx   esi, byte ptr [rax+rdi]
0x180047a79  test    byte ptr [rsi+r13], 8
0x180047a7e  jz      loc_180047B1B
0x180047a84  movzx   r10d, byte ptr [r11+rdi+2]
0x180047a8a  test    byte ptr [r10+r13], 8
0x180047a8f  jz      loc_180047B1B
0x180047a95  mov     al, sil
0x180047a98  mov     dl, sil
0x180047a9b  sar     al, 6
0x180047a9e  and     al, r14b
0x180047aa1  movzx   eax, al
0x180047aa4  imul    ecx, eax, 7
0x180047aa7  mov     al, r10b
0x180047aaa  sar     al, 6
0x180047aad  and     al, r14b
0x180047ab0  movzx   eax, al
0x180047ab3  sub     dl, cl
0x180047ab5  imul    ecx, eax, 7
0x180047ab8  mov     al, r10b
0x180047abb  and     edx, 0Fh
0x180047abe  shl     edx, 4
0x180047ac1  sub     al, cl
0x180047ac3  lea     ecx, [r11+3]
0x180047ac7  and     eax, 0Fh
0x180047aca  add     edx, eax
0x180047acc  jz      short loc_180047B0F
0x180047ace  jmp     loc_180047B82
0x180047ad3  cmp     dl, r12b
0x180047ad6  jz      loc_180047B8B
0x180047adc  test    r9d, r9d
0x180047adf  jnz     short loc_180047AEA
0x180047ae1  cmp     dl, 3Fh ; '?'
0x180047ae4  jz      loc_180047B8B
0x180047aea  cmp     r9d, r14d
0x180047aed  jnz     short loc_180047B01
0x180047aef  cmp     dl, 3Dh ; '='
0x180047af2  jz      loc_180047B8B
0x180047af8  cmp     dl, bpl
0x180047afb  jz      loc_180047B8B
0x180047b01  cmp     r9d, 2
0x180047b05  jnz     short loc_180047B0C
0x180047b07  cmp     dl, bpl
0x180047b0a  jz      short loc_180047B8B
0x180047b0c  add     ecx, r14d
0x180047b0f  movsxd  rax, ecx
0x180047b12  mov     dl, [rax+rdi]
0x180047b15  test    dl, dl
0x180047b17  jnz     short loc_180047AD3
0x180047b19  jmp     short loc_180047B8B
0x180047b1b  cmp     r9d, r14d
0x180047b1e  jnz     short loc_180047B68
0x180047b20  cmp     dl, bpl
0x180047b23  jz      short loc_180047B2A
0x180047b25  cmp     dl, 3Dh ; '='
0x180047b28  jnz     short loc_180047B82
0x180047b2a  movsxd  rax, r8d
0x180047b2d  cmp     byte ptr [rax+rbx-1], 0
0x180047b32  jz      short loc_180047B55
0x180047b34  cmp     dl, bpl
0x180047b37  jnz     short loc_180047B60
0x180047b39  mov     byte ptr [rax+rbx], 0
0x180047b3d  add     r8d, r14d
0x180047b40  jmp     short loc_180047B80
0x180047b42  movsxd  rax, ecx
0x180047b45  cmp     [rax+rdi], r12b
0x180047b49  jz      short loc_180047B8B
0x180047b4b  cmp     [rax+rdi-1], bpl
0x180047b50  jz      short loc_180047B8B
0x180047b52  add     ecx, r14d
0x180047b55  movsxd  rax, ecx
0x180047b58  cmp     byte ptr [rax+rdi], 0
0x180047b5c  jnz     short loc_180047B42
0x180047b5e  jmp     short loc_180047B8B
0x180047b60  mov     r9d, 2
0x180047b66  jmp     short loc_180047B80
0x180047b68  test    r9d, r9d
0x180047b6b  jnz     short loc_180047B72
0x180047b6d  cmp     dl, 3Fh ; '?'
0x180047b70  jz      short loc_180047B7D
0x180047b72  cmp     r9d, 2
0x180047b76  jnz     short loc_180047B82
0x180047b78  cmp     dl, bpl
0x180047b7b  jnz     short loc_180047B82
0x180047b7d  mov     r9d, r14d
0x180047b80  xor     dl, dl
0x180047b82  movsxd  rax, r8d
0x180047b85  add     r8d, r14d
0x180047b88  mov     [rax+rbx], dl
0x180047b8b  movsxd  rax, ecx
0x180047b8e  mov     dl, [rax+rdi]
0x180047b91  test    dl, dl
0x180047b93  jnz     loc_180047A5A
0x180047b99  cmp     r9d, r14d
0x180047b9c  jnz     short loc_180047BA8
0x180047b9e  movsxd  rax, r8d
0x180047ba1  add     r8d, r14d
0x180047ba4  mov     byte ptr [rax+rbx], 0
0x180047ba8  movsxd  rax, r8d
0x180047bab  xor     ecx, ecx
0x180047bad  mov     [rax+rbx], ecx
0x180047bb0  mov     rcx, rbx
0x180047bb3  call    sqlite3Strlen30
0x180047bb8  add     eax, r14d
0x180047bbb  mov     r14d, 3
0x180047bc1  movsxd  rdx, eax
0x180047bc4  add     rdx, rbx
0x180047bc7  cmp     byte ptr [rdx], 0
0x180047bca  jz      loc_180047D48
0x180047bd0  mov     rcx, rdx
0x180047bd3  call    sqlite3Strlen30
0x180047bd8  mov     r9d, eax
0x180047bdb  lea     ecx, [rax+1]
0x180047bde  movsxd  rsi, ecx
0x180047be1  add     rsi, rdx
0x180047be4  mov     rcx, rsi
0x180047be7  call    sqlite3Strlen30
0x180047bec  mov     [rsp+68h+var_44], eax
0x180047bf0  mov     r8d, eax
0x180047bf3  cmp     r9d, r14d
0x180047bf6  jnz     short loc_180047C25
0x180047bf8  movzx   ecx, word ptr [rdx]
0x180047bfb  mov     r8d, 6676h
0x180047c01  sub     r8d, ecx
0x180047c04  jnz     short loc_180047C13
0x180047c06  movzx   ecx, byte ptr [rdx+2]
0x180047c0a  mov     r8d, 73h ; 's'
0x180047c10  sub     r8d, ecx
0x180047c13  test    r8d, r8d
0x180047c16  jnz     short loc_180047C22
0x180047c18  mov     [rsp+68h+arg_0], rsi
0x180047c1d  jmp     loc_180047D07
0x180047c22  mov     r8d, eax
0x180047c25  cmp     r9d, 5
0x180047c29  jnz     short loc_180047C61
0x180047c2b  xor     ebp, ebp
0x180047c2d  xor     r15d, r15d
0x180047c30  xor     edi, edi
0x180047c32  mov     ecx, 68636163h
0x180047c37  sub     ecx, [rdx]
0x180047c39  jnz     short loc_180047C44
0x180047c3b  movzx   eax, byte ptr [rdx+4]
0x180047c3f  lea     ecx, [rbp+65h]
0x180047c42  sub     ecx, eax
0x180047c44  test    ecx, ecx
0x180047c46  jnz     loc_180047CD3
0x180047c4c  mov     edi, 60000h
0x180047c51  lea     rbp, off_1800D0658; "shared"
0x180047c58  lea     r15, aCache; "cache"
0x180047c5f  jmp     short loc_180047CD3
0x180047c61  cmp     r9d, 4
0x180047c65  jnz     short loc_180047CCC
0x180047c67  mov     eax, 65646F6Dh
0x180047c6c  cmp     eax, [rdx]
0x180047c6e  jnz     loc_180047D07
0x180047c74  mov     r12d, r15d
0x180047c77  lea     rbp, off_1800D0690; "ro"
  ... truncated ...
```
