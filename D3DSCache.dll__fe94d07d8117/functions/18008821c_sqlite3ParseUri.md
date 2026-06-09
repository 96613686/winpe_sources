# sqlite3ParseUri

- ea: `0x18008821c`
- end: `0x180088710`
- name: `sqlite3ParseUri`
- size: `1268`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800204f0`
- `0x180053c70`

## callees

- `0x18002b81c`
- `0x180042350`
- `0x18008821c`
- `0x1800964a0`
- `0x180096550`
- `0x180098d40`
- `0x1800a6cfc`
- `0x1800a6d08`

## string_xrefs

- `0x180088333`: `invalid uri authority: %.*s`
- `0x18008855d`: `cache`
- `0x180088588`: `access`

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
  __int64 v13; // r8
  size_t v14; // rsi
  unsigned int v15; // r14d
  int v16; // ecx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rdx
  _DWORD *v21; // rbx
  unsigned int v22; // r15d
  _BYTE *v23; // rbx
  int v24; // ecx
  const char *v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  int v28; // r9d
  __int64 v29; // r11
  __int64 v30; // rsi
  __int64 v31; // r10
  char v32; // dl
  __int64 v33; // rax
  __int64 v34; // rax
  char *i; // rdx
  __int64 v36; // r8
  int v37; // eax
  __int64 v38; // rdx
  const char *v39; // rsi
  __int64 v40; // r8
  unsigned int v41; // eax
  unsigned __int16 *v42; // rdx
  int v43; // r9d
  int v44; // ecx
  char **v45; // rbp
  const char *v46; // r15
  int v47; // edi
  int v48; // ecx
  char v49; // r12
  int v50; // r12d
  int j; // eax
  __int64 v52; // r13
  char *v53; // rcx
  int v54; // eax
  const void *v55; // rcx
  int v56; // ecx
  _DWORD *v57; // rbx
  __int64 result; // rax
  __int64 v59; // rax
  unsigned int v60; // [rsp+20h] [rbp-48h]
  unsigned int v61; // [rsp+24h] [rbp-44h]
  int v62; // [rsp+28h] [rbp-40h]
  const char *v63; // [rsp+70h] [rbp+8h]

  v63 = a1;
  v6 = *a3;
  v7 = a1;
  v8 = a4;
  v9 = a3;
  v11 = sqlite3Strlen30(a2, a2, a3);
  v14 = v11;
  v15 = 1;
  if ( ((v6 & 0x40) != 0 || byte_1800C6976) && v11 >= 5 )
  {
    v16 = *(_DWORD *)v12 - 1701603686;
    if ( *(_DWORD *)v12 == 1701603686 )
      v16 = *(unsigned __int8 *)(v12 + 4) - 58;
    if ( !v16 )
    {
      v17 = 0;
      v18 = v11 + 8;
      do
      {
        v19 = a2[v17] == 38;
        v17 = (unsigned int)(v17 + 1);
        v18 += v19;
      }
      while ( (int)v17 < v11 );
      v21 = (_DWORD *)sqlite3_malloc64(v18, v19, v17);
      if ( v21 )
      {
        v22 = v6 | 0x40;
        *v21 = 0;
        v23 = v21 + 1;
        v60 = v22;
        v24 = 5;
        if ( a2[5] == 47 && a2[6] == 47 )
        {
          v25 = a2 + 7;
          v24 = 7;
          if ( a2[7] )
          {
            do
            {
              if ( a2[v24] == 47 )
                break;
              ++v24;
            }
            while ( a2[v24] );
            if ( v24 != 7 )
            {
              if ( v24 != 16 )
                goto LABEL_20;
              v20 = 0x736F686C61636F6CLL - *(_QWORD *)v25;
              if ( *(_QWORD *)v25 == 0x736F686C61636F6CLL )
                v20 = 116LL - *((unsigned __int8 *)a2 + 15);
              if ( v20 )
              {
LABEL_20:
                v26 = sqlite3_mprintf("invalid uri authority: %.*s", v24 - 7, v25);
                goto LABEL_101;
              }
            }
          }
        }
        v27 = 0;
        v28 = 0;
        LOBYTE(v20) = a2[v24];
        if ( (_BYTE)v20 )
        {
          while ( 1 )
          {
            if ( (_BYTE)v20 == 35 )
            {
LABEL_59:
              if ( v28 == 1 )
              {
                v34 = (int)v27;
                v27 = (unsigned int)(v27 + 1);
                v23[v34] = 0;
              }
              break;
            }
            v29 = v24++;
            if ( (_BYTE)v20 == 37 )
            {
              v30 = (unsigned __int8)a2[v24];
              if ( (*((_BYTE *)&qword_1800ADE90 + v30) & 8) != 0 )
              {
                v31 = (unsigned __int8)a2[v29 + 2];
                if ( (*((_BYTE *)&qword_1800ADE90 + v31) & 8) != 0 )
                {
                  v24 = v29 + 3;
                  v20 = (((_BYTE)v31 - 7 * (((char)v31 >> 6) & 1)) & 0xF)
                      + 16 * (((_BYTE)v30 - 7 * (((char)v30 >> 6) & 1)) & 0xFu);
                  if ( !(_DWORD)v20 )
                  {
                    while ( 1 )
                    {
                      v32 = a2[v24];
                      if ( !v32 || v32 == 35 || !v28 && v32 == 63 )
                        break;
                      if ( v28 == 1 && (v32 == 61 || v32 == 38) || v28 == 2 && v32 == 38 )
                        break;
                      ++v24;
                    }
                    goto LABEL_58;
                  }
                  goto LABEL_57;
                }
              }
            }
            if ( v28 == 1 )
            {
              if ( (_BYTE)v20 != 38 && (_BYTE)v20 != 61 )
                goto LABEL_57;
              if ( !v23[(int)v27 - 1] )
              {
                while ( a2[v24] && a2[v24] != 35 && a2[v24 - 1] != 38 )
                  ++v24;
                goto LABEL_58;
              }
              if ( (_BYTE)v20 == 38 )
              {
                v23[(int)v27] = 0;
                LODWORD(v27) = v27 + 1;
              }
              else
              {
                v28 = 2;
              }
            }
            else
            {
              if ( (v28 || (_BYTE)v20 != 63) && (v28 != 2 || (_BYTE)v20 != 38) )
                goto LABEL_57;
              v28 = 1;
            }
            LOBYTE(v20) = 0;
LABEL_57:
            v33 = (int)v27;
            v27 = (unsigned int)(v27 + 1);
            v23[v33] = v20;
LABEL_58:
            LOBYTE(v20) = a2[v24];
            if ( !(_BYTE)v20 )
              goto LABEL_59;
          }
        }
        *(_DWORD *)&v23[(int)v27] = 0;
        v15 = 3;
        for ( i = &v23[(int)(sqlite3Strlen30(v23, v20, v27) + 1)]; ; i = (char *)&v39[v61 + 1] )
        {
          if ( !*i )
          {
            v7 = v63;
            v9 = a3;
            v8 = a4;
            goto LABEL_99;
          }
          v37 = sqlite3Strlen30(i, i, v36);
          v39 = (const char *)(v38 + v37 + 1);
          v41 = sqlite3Strlen30(v39, v38, v40);
          v61 = v41;
          v36 = v41;
          if ( v43 == 3 )
          {
            v44 = *v42;
            v36 = (unsigned int)(26230 - v44);
            if ( v44 == 26230 )
              v36 = 115 - (unsigned int)*((unsigned __int8 *)v42 + 2);
            if ( !(_DWORD)v36 )
            {
              v63 = v39;
              continue;
            }
            v36 = v41;
          }
          if ( v43 == 5 )
            break;
          if ( v43 != 4 )
          {
            v45 = 0;
            v47 = 0;
            v46 = 0;
LABEL_78:
            v50 = v47;
            if ( v45 )
              goto LABEL_79;
            v22 = v60;
            continue;
          }
          if ( *(_DWORD *)v42 == 1701080941 )
          {
            v49 = v22;
            v45 = &off_1800C65C0;
            v47 = 135;
            v46 = "access";
            v50 = v49 & 0x87;
LABEL_79:
            for ( j = 0; ; j = v62 + 1 )
            {
              v52 = 2LL * j;
              v62 = j;
              v53 = v45[2 * j];
              if ( !v53 )
                goto LABEL_92;
              v54 = sqlite3Strlen30(v53, v42, v36);
              if ( (_DWORD)v36 == v54 )
              {
                if ( !memcmp_0(v39, v55, (int)v36) )
                {
                  v56 = (int)v45[v52 + 1];
                  if ( !v56 )
                  {
LABEL_92:
                    v15 = 1;
                    v26 = sqlite3_mprintf("no such %s mode: %s", v46, v39);
                    goto LABEL_91;
                  }
                  if ( (int)(v56 & 0xFFFFFF7F) <= v50 )
                  {
                    v22 = v56 | v60 & ~v47;
                    v60 = v22;
                    break;
                  }
                  v26 = sqlite3_mprintf("%s mode not allowed: %s", v46, v39);
LABEL_91:
                  v22 = v60;
                  v9 = a3;
LABEL_101:
                  *a6 = v26;
                  sqlite3_free_filename(v23);
                  v23 = 0;
                  goto LABEL_102;
                }
                v36 = v61;
              }
            }
          }
        }
        v45 = 0;
        v46 = 0;
        v47 = 0;
        v48 = 1751343459 - *(_DWORD *)v42;
        if ( *(_DWORD *)v42 == 1751343459 )
          v48 = 101 - *((unsigned __int8 *)v42 + 4);
        if ( !v48 )
        {
          v47 = 393216;
          v45 = &off_1800C6590;
          v46 = "cache";
        }
        goto LABEL_78;
      }
      return 7;
    }
  }
  v57 = (_DWORD *)sqlite3_malloc64(v11 + 8, v12, v13);
  if ( !v57 )
    return 7;
  *v57 = 0;
  v23 = v57 + 1;
  if ( (_DWORD)v14 )
    memcpy_0(v23, a2, v14);
  *(_DWORD *)&v23[v14] = 0;
  v22 = v6 & 0xFFFFFFBF;
LABEL_99:
  v15 = 0;
  v59 = sqlite3_vfs_find(v7);
  *v8 = v59;
  if ( !v59 )
  {
    v15 = 1;
    v26 = sqlite3_mprintf("no such vfs: %s", v7);
    goto LABEL_101;
  }
LABEL_102:
  result = v15;
  *v9 = v22;
  *a5 = v23;
  return result;
}

```

## disassembly

```asm
0x18008821c  mov     rax, rsp
0x18008821f  mov     [rax+10h], rbx
0x180088223  mov     [rax+20h], r9
0x180088227  mov     [rax+18h], r8
0x18008822b  mov     [rax+8], rcx
0x18008822f  push    rbp
0x180088230  push    rsi
0x180088231  push    rdi
0x180088232  push    r12
0x180088234  push    r13
0x180088236  push    r14
0x180088238  push    r15
0x18008823a  sub     rsp, 30h
0x18008823e  mov     r15d, [r8]
0x180088241  mov     rbp, rcx
0x180088244  mov     rcx, rdx
0x180088247  mov     r13, r9
0x18008824a  mov     r12, r8
0x18008824d  mov     rdi, rdx
0x180088250  call    sqlite3Strlen30
0x180088255  movsxd  rsi, eax
0x180088258  mov     r14d, 1
0x18008825e  test    r15b, 40h
0x180088262  jnz     short loc_180088271
0x180088264  cmp     cs:byte_1800C6976, 0
0x18008826b  jz      loc_180088656
0x180088271  cmp     esi, 5
0x180088274  jl      loc_180088656
0x18008827a  mov     ecx, [rdx]
0x18008827c  sub     ecx, 656C6966h
0x180088282  jnz     short loc_18008828B
0x180088284  movzx   ecx, byte ptr [rdx+4]
0x180088288  sub     ecx, 3Ah ; ':'
0x18008828b  test    ecx, ecx
0x18008828d  jnz     loc_180088656
0x180088293  lea     eax, [rsi+8]
0x180088296  xor     r8d, r8d
0x180088299  movsxd  rcx, eax
0x18008829c  mov     bpl, 26h ; '&'
0x18008829f  xor     edx, edx
0x1800882a1  cmp     [r8+rdi], bpl
0x1800882a5  setz    dl
0x1800882a8  add     r8d, r14d
0x1800882ab  add     rcx, rdx
0x1800882ae  cmp     r8d, esi
0x1800882b1  jl      short loc_18008829F
0x1800882b3  call    sqlite3_malloc64
0x1800882b8  mov     rbx, rax
0x1800882bb  test    rax, rax
0x1800882be  jz      loc_180088669
0x1800882c4  xor     eax, eax
0x1800882c6  or      r15d, 40h
0x1800882ca  mov     [rbx], eax
0x1800882cc  mov     dl, 2Fh ; '/'
0x1800882ce  add     rbx, 4
0x1800882d2  mov     [rsp+68h+var_48], r15d
0x1800882d7  lea     ecx, [rax+5]
0x1800882da  cmp     [rdi+5], dl
0x1800882dd  jnz     short loc_180088344
0x1800882df  cmp     [rdi+6], dl
0x1800882e2  jnz     short loc_180088344
0x1800882e4  lea     r8, [rdi+7]
0x1800882e8  lea     ecx, [rax+7]
0x1800882eb  cmp     [r8], al
0x1800882ee  jz      short loc_180088344
0x1800882f0  movsxd  rax, ecx
0x1800882f3  cmp     [rax+rdi], dl
0x1800882f6  jz      short loc_180088304
0x1800882f8  add     ecx, r14d
0x1800882fb  movsxd  rax, ecx
0x1800882fe  cmp     byte ptr [rax+rdi], 0
0x180088302  jnz     short loc_1800882F0
0x180088304  cmp     ecx, 7
0x180088307  jz      short loc_180088344
0x180088309  cmp     ecx, 10h
0x18008830c  jnz     short loc_180088330
0x18008830e  mov     rdx, 736F686C61636F6Ch
0x180088318  sub     rdx, [r8]
0x18008831b  jnz     short loc_18008832B
0x18008831d  lea     eax, [rcx+64h]
0x180088320  movzx   edx, al
0x180088323  movzx   eax, byte ptr [r8+8]
0x180088328  sub     rdx, rax
0x18008832b  test    rdx, rdx
0x18008832e  jz      short loc_180088344
0x180088330  lea     edx, [rcx-7]
0x180088333  lea     rcx, aInvalidUriAuth; "invalid uri authority: %.*s"
0x18008833a  call    sqlite3_mprintf
0x18008833f  jmp     loc_1800886D4
0x180088344  movsxd  rax, ecx
0x180088347  xor     r8d, r8d
0x18008834a  xor     r9d, r9d
0x18008834d  mov     dl, [rax+rdi]
0x180088350  test    dl, dl
0x180088352  jz      loc_1800884B1
0x180088358  mov     r12b, 23h ; '#'
0x18008835b  lea     r13, qword_1800ADE90
0x180088362  cmp     dl, r12b
0x180088365  jz      loc_1800884A2
0x18008836b  movsxd  r11, ecx
0x18008836e  add     ecx, r14d
0x180088371  cmp     dl, 25h ; '%'
0x180088374  jnz     loc_180088424
0x18008837a  movsxd  rax, ecx
0x18008837d  movzx   esi, byte ptr [rax+rdi]
0x180088381  test    byte ptr [rsi+r13], 8
0x180088386  jz      loc_180088424
0x18008838c  movzx   r10d, byte ptr [r11+rdi+2]
0x180088392  test    byte ptr [r10+r13], 8
0x180088397  jz      loc_180088424
0x18008839d  mov     al, sil
0x1800883a0  mov     dl, sil
0x1800883a3  sar     al, 6
0x1800883a6  and     al, r14b
0x1800883a9  movzx   eax, al
0x1800883ac  imul    ecx, eax, 7
0x1800883af  mov     al, r10b
0x1800883b2  sar     al, 6
0x1800883b5  and     al, r14b
0x1800883b8  movzx   eax, al
0x1800883bb  sub     dl, cl
0x1800883bd  imul    ecx, eax, 7
0x1800883c0  mov     al, r10b
0x1800883c3  and     edx, 0Fh
0x1800883c6  shl     edx, 4
0x1800883c9  sub     al, cl
0x1800883cb  lea     ecx, [r11+3]
0x1800883cf  and     eax, 0Fh
0x1800883d2  add     edx, eax
0x1800883d4  jnz     loc_18008848B
0x1800883da  jmp     short loc_180088418
0x1800883dc  cmp     dl, r12b
0x1800883df  jz      loc_180088494
0x1800883e5  test    r9d, r9d
0x1800883e8  jnz     short loc_1800883F3
0x1800883ea  cmp     dl, 3Fh ; '?'
0x1800883ed  jz      loc_180088494
0x1800883f3  cmp     r9d, r14d
0x1800883f6  jnz     short loc_18008840A
0x1800883f8  cmp     dl, 3Dh ; '='
0x1800883fb  jz      loc_180088494
0x180088401  cmp     dl, bpl
0x180088404  jz      loc_180088494
0x18008840a  cmp     r9d, 2
0x18008840e  jnz     short loc_180088415
0x180088410  cmp     dl, bpl
0x180088413  jz      short loc_180088494
0x180088415  add     ecx, r14d
0x180088418  movsxd  rax, ecx
0x18008841b  mov     dl, [rax+rdi]
0x18008841e  test    dl, dl
0x180088420  jnz     short loc_1800883DC
0x180088422  jmp     short loc_180088494
0x180088424  cmp     r9d, r14d
0x180088427  jnz     short loc_180088471
0x180088429  cmp     dl, bpl
0x18008842c  jz      short loc_180088433
0x18008842e  cmp     dl, 3Dh ; '='
0x180088431  jnz     short loc_18008848B
0x180088433  movsxd  rax, r8d
0x180088436  cmp     byte ptr [rax+rbx-1], 0
0x18008843b  jz      short loc_18008845E
0x18008843d  cmp     dl, bpl
0x180088440  jnz     short loc_180088469
0x180088442  mov     byte ptr [rax+rbx], 0
0x180088446  add     r8d, r14d
0x180088449  jmp     short loc_180088489
0x18008844b  movsxd  rax, ecx
0x18008844e  cmp     [rax+rdi], r12b
0x180088452  jz      short loc_180088494
0x180088454  cmp     [rax+rdi-1], bpl
0x180088459  jz      short loc_180088494
0x18008845b  add     ecx, r14d
0x18008845e  movsxd  rax, ecx
0x180088461  cmp     byte ptr [rax+rdi], 0
0x180088465  jnz     short loc_18008844B
0x180088467  jmp     short loc_180088494
0x180088469  mov     r9d, 2
0x18008846f  jmp     short loc_180088489
0x180088471  test    r9d, r9d
0x180088474  jnz     short loc_18008847B
0x180088476  cmp     dl, 3Fh ; '?'
0x180088479  jz      short loc_180088486
0x18008847b  cmp     r9d, 2
0x18008847f  jnz     short loc_18008848B
0x180088481  cmp     dl, bpl
0x180088484  jnz     short loc_18008848B
0x180088486  mov     r9d, r14d
0x180088489  xor     dl, dl
0x18008848b  movsxd  rax, r8d
0x18008848e  add     r8d, r14d
0x180088491  mov     [rax+rbx], dl
0x180088494  movsxd  rax, ecx
0x180088497  mov     dl, [rax+rdi]
0x18008849a  test    dl, dl
0x18008849c  jnz     loc_180088362
0x1800884a2  cmp     r9d, r14d
0x1800884a5  jnz     short loc_1800884B1
0x1800884a7  movsxd  rax, r8d
0x1800884aa  add     r8d, r14d
0x1800884ad  mov     byte ptr [rax+rbx], 0
0x1800884b1  movsxd  rax, r8d
0x1800884b4  xor     ecx, ecx
0x1800884b6  mov     [rax+rbx], ecx
0x1800884b9  mov     rcx, rbx
0x1800884bc  call    sqlite3Strlen30
0x1800884c1  add     eax, r14d
0x1800884c4  mov     r14d, 3
0x1800884ca  movsxd  rdx, eax
0x1800884cd  add     rdx, rbx
0x1800884d0  cmp     byte ptr [rdx], 0
0x1800884d3  jz      loc_180088698
0x1800884d9  mov     rcx, rdx
0x1800884dc  call    sqlite3Strlen30
0x1800884e1  mov     r9d, eax
0x1800884e4  lea     ecx, [rax+1]
0x1800884e7  movsxd  rsi, ecx
0x1800884ea  add     rsi, rdx
0x1800884ed  mov     rcx, rsi
0x1800884f0  call    sqlite3Strlen30
0x1800884f5  mov     [rsp+68h+var_44], eax
0x1800884f9  mov     r8d, eax
0x1800884fc  cmp     r9d, r14d
0x1800884ff  jnz     short loc_18008852E
0x180088501  movzx   ecx, word ptr [rdx]
0x180088504  mov     r8d, 6676h
0x18008850a  sub     r8d, ecx
0x18008850d  jnz     short loc_18008851C
0x18008850f  movzx   ecx, byte ptr [rdx+2]
0x180088513  mov     r8d, 73h ; 's'
0x180088519  sub     r8d, ecx
0x18008851c  test    r8d, r8d
0x18008851f  jnz     short loc_18008852B
0x180088521  mov     [rsp+68h+arg_0], rsi
0x180088526  jmp     loc_180088612
0x18008852b  mov     r8d, eax
0x18008852e  cmp     r9d, 5
0x180088532  jnz     short loc_180088566
0x180088534  xor     ebp, ebp
0x180088536  xor     r15d, r15d
0x180088539  xor     edi, edi
0x18008853b  mov     ecx, 68636163h
0x180088540  sub     ecx, [rdx]
0x180088542  jnz     short loc_18008854D
0x180088544  movzx   eax, byte ptr [rdx+4]
0x180088548  lea     ecx, [rbp+65h]
0x18008854b  sub     ecx, eax
0x18008854d  test    ecx, ecx
0x18008854f  jnz     short loc_18008859B
0x180088551  mov     edi, 60000h
0x180088556  lea     rbp, off_1800C6590; "shared"
0x18008855d  lea     r15, aCache; "cache"
0x180088564  jmp     short loc_18008859B
0x180088566  cmp     r9d, 4
0x18008856a  jnz     short loc_180088594
0x18008856c  mov     eax, 65646F6Dh
0x180088571  cmp     eax, [rdx]
0x180088573  jnz     loc_180088612
0x180088579  mov     r12d, r15d
0x18008857c  lea     rbp, off_1800C65C0; "ro"
0x180088583  mov     edi, 87h
0x180088588  lea     r15, aAccess; "access"
0x18008858f  and     r12d, edi
0x180088592  jmp     short loc_1800885A3
0x180088594  xor     ebp, ebp
0x180088596  xor     edi, edi
0x180088598  xor     r15d, r15d
0x18008859b  mov     r12d, edi
0x18008859e  test    rbp, rbp
0x1800885a1  jz      short loc_18008860D
0x1800885a3  xor     eax, eax
0x1800885a5  movsxd  r13, eax
0x1800885a8  add     r13, r13
0x1800885ab  mov     [rsp+68h+var_40], eax
0x1800885af  mov     rcx, [rbp+r13*8+0]
0x1800885b4  test    rcx, rcx
0x1800885b7  jz      loc_180088647
0x1800885bd  call    sqlite3Strlen30
0x1800885c2  cmp     r8d, eax
0x1800885c5  jnz     short loc_1800885DE
0x1800885c7  mov     rdx, rcx; Buf2
0x1800885ca  movsxd  r8, r8d; Size
0x1800885cd  mov     rcx, rsi; Buf1
0x1800885d0  call    memcmp_0
0x1800885d5  test    eax, eax
0x1800885d7  jz      short loc_1800885E6
0x1800885d9  mov     r8d, [rsp+68h+var_44]
0x1800885de  mov     eax, [rsp+68h+var_40]
0x1800885e2  inc     eax
0x1800885e4  jmp     short loc_1800885A5
0x1800885e6  mov     ecx, [rbp+r13*8+8]
0x1800885eb  test    ecx, ecx
0x1800885ed  jz      short loc_180088647
0x1800885ef  mov     eax, ecx
0x1800885f1  btr     eax, 7
0x1800885f5  cmp     eax, r12d
0x1800885f8  jg      short loc_180088623
0x1800885fa  not     edi
0x1800885fc  and     edi, [rsp+68h+var_48]
0x180088600  mov     r15d, edi
  ... truncated ...
```
