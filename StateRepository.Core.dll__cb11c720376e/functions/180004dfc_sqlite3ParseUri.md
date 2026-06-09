# sqlite3ParseUri

- ea: `0x180004dfc`
- end: `0x1800052f3`
- name: `sqlite3ParseUri`
- size: `1271`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180001fbc`
- `0x180069970`

## callees

- `0x180001110`
- `0x180004dfc`
- `0x180005810`
- `0x180005b90`
- `0x180005bc0`
- `0x180068380`
- `0x180099808`
- `0x180099814`

## string_xrefs

- `0x180004f8d`: `invalid uri authority: %.*s`
- `0x1800051ba`: `cache`
- `0x1800051e5`: `access`

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
  if ( ((v6 & 0x40) != 0 || byte_1800B5636) && v11 >= 5 )
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
              if ( (*((_BYTE *)&qword_18009E630 + v33) & 8) != 0 )
              {
                v34 = (unsigned __int8)a2[v32 + 2];
                if ( (*((_BYTE *)&qword_18009E630 + v34) & 8) != 0 )
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
            v46 = &off_1800B54F0;
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
          v46 = &off_1800B54C0;
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
0x180004dfc  mov     rax, rsp
0x180004dff  mov     [rax+10h], rbx
0x180004e03  mov     [rax+20h], r9
0x180004e07  mov     [rax+18h], r8
0x180004e0b  mov     [rax+8], rcx
0x180004e0f  push    rbp
0x180004e10  push    rsi
0x180004e11  push    rdi
0x180004e12  push    r12
0x180004e14  push    r13
0x180004e16  push    r14
0x180004e18  push    r15
0x180004e1a  sub     rsp, 30h
0x180004e1e  mov     r15d, [r8]
0x180004e21  mov     rbp, rcx
0x180004e24  mov     rcx, rdx
0x180004e27  mov     r13, r9
0x180004e2a  mov     r12, r8
0x180004e2d  mov     rdi, rdx
0x180004e30  call    sqlite3Strlen30
0x180004e35  movsxd  rsi, eax
0x180004e38  mov     r14d, 1
0x180004e3e  test    r15b, 40h
0x180004e42  jnz     loc_180004ECF
0x180004e48  cmp     cs:byte_1800B5636, 0
0x180004e4f  jnz     short loc_180004ECF
0x180004e51  lea     eax, [rsi+8]
0x180004e54  movsxd  rcx, eax
0x180004e57  call    sqlite3_malloc64
0x180004e5c  mov     rbx, rax
0x180004e5f  test    rax, rax
0x180004e62  jz      short loc_180004EC8
0x180004e64  xor     eax, eax
0x180004e66  mov     [rbx], eax
0x180004e68  add     rbx, 4
0x180004e6c  test    esi, esi
0x180004e6e  jnz     short loc_180004EB8
0x180004e70  xor     ecx, ecx
0x180004e72  mov     [rsi+rbx], ecx
0x180004e75  and     r15d, 0FFFFFFBFh
0x180004e79  mov     rcx, rbp
0x180004e7c  xor     r14d, r14d
0x180004e7f  call    sqlite3_vfs_find
0x180004e84  mov     [r13+0], rax
0x180004e88  test    rax, rax
0x180004e8b  jz      loc_1800052C4
0x180004e91  mov     rcx, [rsp+68h+arg_20]
0x180004e99  mov     eax, r14d
0x180004e9c  mov     [r12], r15d
0x180004ea0  mov     [rcx], rbx
0x180004ea3  mov     rbx, [rsp+68h+arg_8]
0x180004ea8  add     rsp, 30h
0x180004eac  pop     r15
0x180004eae  pop     r14
0x180004eb0  pop     r13
0x180004eb2  pop     r12
0x180004eb4  pop     rdi
0x180004eb5  pop     rsi
0x180004eb6  pop     rbp
0x180004eb7  retn
0x180004eb8  mov     r8, rsi; Size
0x180004ebb  mov     rdx, rdi; Src
0x180004ebe  mov     rcx, rbx; void *
0x180004ec1  call    memcpy_0
0x180004ec6  jmp     short loc_180004E70
0x180004ec8  mov     eax, 7
0x180004ecd  jmp     short loc_180004EA3
0x180004ecf  cmp     esi, 5
0x180004ed2  jl      loc_180004E51
0x180004ed8  mov     ecx, [rdx]
0x180004eda  sub     ecx, 656C6966h
0x180004ee0  jnz     short loc_180004EE9
0x180004ee2  movzx   ecx, byte ptr [rdx+4]
0x180004ee6  sub     ecx, 3Ah ; ':'
0x180004ee9  test    ecx, ecx
0x180004eeb  jnz     loc_180004E51
0x180004ef1  lea     eax, [rsi+8]
0x180004ef4  xor     r8d, r8d
0x180004ef7  movsxd  rcx, eax
0x180004efa  mov     bpl, 26h ; '&'
0x180004efd  xor     edx, edx
0x180004eff  cmp     [r8+rdi], bpl
0x180004f03  setz    dl
0x180004f06  add     r8d, r14d
0x180004f09  add     rcx, rdx
0x180004f0c  cmp     r8d, esi
0x180004f0f  jl      short loc_180004EFD
0x180004f11  call    sqlite3_malloc64
0x180004f16  mov     rbx, rax
0x180004f19  test    rax, rax
0x180004f1c  jz      short loc_180004EC8
0x180004f1e  xor     eax, eax
0x180004f20  or      r15d, 40h
0x180004f24  mov     [rbx], eax
0x180004f26  mov     dl, 2Fh ; '/'
0x180004f28  add     rbx, 4
0x180004f2c  mov     [rsp+68h+var_48], r15d
0x180004f31  lea     ecx, [rax+5]
0x180004f34  cmp     [rdi+5], dl
0x180004f37  jnz     short loc_180004F9E
0x180004f39  cmp     [rdi+6], dl
0x180004f3c  jnz     short loc_180004F9E
0x180004f3e  lea     r8, [rdi+7]
0x180004f42  lea     ecx, [rax+7]
0x180004f45  cmp     [r8], al
0x180004f48  jz      short loc_180004F9E
0x180004f4a  movsxd  rax, ecx
0x180004f4d  cmp     [rax+rdi], dl
0x180004f50  jz      short loc_180004F5E
0x180004f52  add     ecx, r14d
0x180004f55  movsxd  rax, ecx
0x180004f58  cmp     byte ptr [rax+rdi], 0
0x180004f5c  jnz     short loc_180004F4A
0x180004f5e  cmp     ecx, 7
0x180004f61  jz      short loc_180004F9E
0x180004f63  cmp     ecx, 10h
0x180004f66  jnz     short loc_180004F8A
0x180004f68  mov     rdx, 736F686C61636F6Ch
0x180004f72  sub     rdx, [r8]
0x180004f75  jnz     short loc_180004F85
0x180004f77  lea     eax, [rcx+64h]
0x180004f7a  movzx   edx, al
0x180004f7d  movzx   eax, byte ptr [r8+8]
0x180004f82  sub     rdx, rax
0x180004f85  test    rdx, rdx
0x180004f88  jz      short loc_180004F9E
0x180004f8a  lea     edx, [rcx-7]
0x180004f8d  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x180004f94  call    sqlite3_mprintf
0x180004f99  jmp     loc_1800052D9
0x180004f9e  movsxd  rax, ecx
0x180004fa1  xor     r8d, r8d
0x180004fa4  xor     r9d, r9d
0x180004fa7  mov     dl, [rax+rdi]
0x180004faa  test    dl, dl
0x180004fac  jz      loc_18000510A
0x180004fb2  mov     r12b, 23h ; '#'
0x180004fb5  lea     r13, qword_18009E630
0x180004fbc  cmp     dl, r12b
0x180004fbf  jz      loc_1800050FB
0x180004fc5  movsxd  r11, ecx
0x180004fc8  add     ecx, r14d
0x180004fcb  cmp     dl, 25h ; '%'
0x180004fce  jnz     loc_18000507D
0x180004fd4  movsxd  rax, ecx
0x180004fd7  movzx   esi, byte ptr [rax+rdi]
0x180004fdb  test    byte ptr [rsi+r13], 8
0x180004fe0  jz      loc_18000507D
0x180004fe6  movzx   r10d, byte ptr [r11+rdi+2]
0x180004fec  test    byte ptr [r10+r13], 8
0x180004ff1  jz      loc_18000507D
0x180004ff7  mov     al, sil
0x180004ffa  mov     dl, sil
0x180004ffd  sar     al, 6
0x180005000  and     al, r14b
0x180005003  movzx   eax, al
0x180005006  imul    ecx, eax, 7
0x180005009  mov     al, r10b
0x18000500c  sar     al, 6
0x18000500f  and     al, r14b
0x180005012  movzx   eax, al
0x180005015  sub     dl, cl
0x180005017  imul    ecx, eax, 7
0x18000501a  mov     al, r10b
0x18000501d  and     edx, 0Fh
0x180005020  shl     edx, 4
0x180005023  sub     al, cl
0x180005025  lea     ecx, [r11+3]
0x180005029  and     eax, 0Fh
0x18000502c  add     edx, eax
0x18000502e  jz      short loc_180005071
0x180005030  jmp     loc_1800050E4
0x180005035  cmp     dl, r12b
0x180005038  jz      loc_1800050ED
0x18000503e  test    r9d, r9d
0x180005041  jnz     short loc_18000504C
0x180005043  cmp     dl, 3Fh ; '?'
0x180005046  jz      loc_1800050ED
0x18000504c  cmp     r9d, r14d
0x18000504f  jnz     short loc_180005063
0x180005051  cmp     dl, 3Dh ; '='
0x180005054  jz      loc_1800050ED
0x18000505a  cmp     dl, bpl
0x18000505d  jz      loc_1800050ED
0x180005063  cmp     r9d, 2
0x180005067  jnz     short loc_18000506E
0x180005069  cmp     dl, bpl
0x18000506c  jz      short loc_1800050ED
0x18000506e  add     ecx, r14d
0x180005071  movsxd  rax, ecx
0x180005074  mov     dl, [rax+rdi]
0x180005077  test    dl, dl
0x180005079  jnz     short loc_180005035
0x18000507b  jmp     short loc_1800050ED
0x18000507d  cmp     r9d, r14d
0x180005080  jnz     short loc_1800050CA
0x180005082  cmp     dl, bpl
0x180005085  jz      short loc_18000508C
0x180005087  cmp     dl, 3Dh ; '='
0x18000508a  jnz     short loc_1800050E4
0x18000508c  movsxd  rax, r8d
0x18000508f  cmp     byte ptr [rax+rbx-1], 0
0x180005094  jz      short loc_1800050B7
0x180005096  cmp     dl, bpl
0x180005099  jnz     short loc_1800050C2
0x18000509b  mov     byte ptr [rax+rbx], 0
0x18000509f  add     r8d, r14d
0x1800050a2  jmp     short loc_1800050E2
0x1800050a4  movsxd  rax, ecx
0x1800050a7  cmp     [rax+rdi], r12b
0x1800050ab  jz      short loc_1800050ED
0x1800050ad  cmp     [rax+rdi-1], bpl
0x1800050b2  jz      short loc_1800050ED
0x1800050b4  add     ecx, r14d
0x1800050b7  movsxd  rax, ecx
0x1800050ba  cmp     byte ptr [rax+rdi], 0
0x1800050be  jnz     short loc_1800050A4
0x1800050c0  jmp     short loc_1800050ED
0x1800050c2  mov     r9d, 2
0x1800050c8  jmp     short loc_1800050E2
0x1800050ca  test    r9d, r9d
0x1800050cd  jnz     short loc_1800050D4
0x1800050cf  cmp     dl, 3Fh ; '?'
0x1800050d2  jz      short loc_1800050DF
0x1800050d4  cmp     r9d, 2
0x1800050d8  jnz     short loc_1800050E4
0x1800050da  cmp     dl, bpl
0x1800050dd  jnz     short loc_1800050E4
0x1800050df  mov     r9d, r14d
0x1800050e2  xor     dl, dl
0x1800050e4  movsxd  rax, r8d
0x1800050e7  add     r8d, r14d
0x1800050ea  mov     [rax+rbx], dl
0x1800050ed  movsxd  rax, ecx
0x1800050f0  mov     dl, [rax+rdi]
0x1800050f3  test    dl, dl
0x1800050f5  jnz     loc_180004FBC
0x1800050fb  cmp     r9d, r14d
0x1800050fe  jnz     short loc_18000510A
0x180005100  movsxd  rax, r8d
0x180005103  add     r8d, r14d
0x180005106  mov     byte ptr [rax+rbx], 0
0x18000510a  movsxd  rax, r8d
0x18000510d  xor     ecx, ecx
0x18000510f  mov     [rax+rbx], ecx
0x180005112  mov     rcx, rbx
0x180005115  call    sqlite3Strlen30
0x18000511a  add     eax, r14d
0x18000511d  mov     r14d, 3
0x180005123  movsxd  rdx, eax
0x180005126  add     rdx, rbx
0x180005129  cmp     byte ptr [rdx], 0
0x18000512c  jz      loc_1800052AA
0x180005132  mov     rcx, rdx
0x180005135  call    sqlite3Strlen30
0x18000513a  mov     r9d, eax
0x18000513d  lea     ecx, [rax+1]
0x180005140  movsxd  rsi, ecx
0x180005143  add     rsi, rdx
0x180005146  mov     rcx, rsi
0x180005149  call    sqlite3Strlen30
0x18000514e  mov     [rsp+68h+var_44], eax
0x180005152  mov     r8d, eax
0x180005155  cmp     r9d, r14d
0x180005158  jnz     short loc_180005187
0x18000515a  movzx   ecx, word ptr [rdx]
0x18000515d  mov     r8d, 6676h
0x180005163  sub     r8d, ecx
0x180005166  jnz     short loc_180005175
0x180005168  movzx   ecx, byte ptr [rdx+2]
0x18000516c  mov     r8d, 73h ; 's'
0x180005172  sub     r8d, ecx
0x180005175  test    r8d, r8d
0x180005178  jnz     short loc_180005184
0x18000517a  mov     [rsp+68h+arg_0], rsi
0x18000517f  jmp     loc_180005269
0x180005184  mov     r8d, eax
0x180005187  cmp     r9d, 5
0x18000518b  jnz     short loc_1800051C3
0x18000518d  xor     ebp, ebp
0x18000518f  xor     r15d, r15d
0x180005192  xor     edi, edi
0x180005194  mov     ecx, 68636163h
0x180005199  sub     ecx, [rdx]
0x18000519b  jnz     short loc_1800051A6
0x18000519d  movzx   eax, byte ptr [rdx+4]
0x1800051a1  lea     ecx, [rbp+65h]
0x1800051a4  sub     ecx, eax
0x1800051a6  test    ecx, ecx
0x1800051a8  jnz     loc_180005235
0x1800051ae  mov     edi, 60000h
0x1800051b3  lea     rbp, off_1800B54C0; "shared"
0x1800051ba  lea     r15, aCache; "cache"
0x1800051c1  jmp     short loc_180005235
0x1800051c3  cmp     r9d, 4
0x1800051c7  jnz     short loc_18000522E
0x1800051c9  mov     eax, 65646F6Dh
0x1800051ce  cmp     eax, [rdx]
0x1800051d0  jnz     loc_180005269
0x1800051d6  mov     r12d, r15d
  ... truncated ...
```
