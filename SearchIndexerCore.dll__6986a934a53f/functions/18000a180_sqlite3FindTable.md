# sqlite3FindTable

- ea: `0x18000a180`
- end: `0x18000a6b3`
- name: `sqlite3FindTable`
- size: `1331`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x180009f6c`
- `0x18000a038`
- `0x18001d1c8`
- `0x18001ebb8`
- `0x18001f740`
- `0x180043a80`
- `0x18004ad90`
- `0x1800730ac`
- `0x180073c34`
- `0x18007574c`
- `0x180079640`
- `0x180089d94`
- `0x18008ca10`
- `0x18008d5b0`
- `0x18008d8d0`
- `0x18008f958`
- `0x1800923ec`
- `0x180093bb0`
- `0x180097b90`

## callees

- `0x180009760`
- `0x18000a180`
- `0x18000a710`

## string_xrefs

- `0x18000a5c9`: `sqlite_temp_master`
- `0x18000a61f`: `sqlite_temp_master`

## pseudocode

```c
__int64 __fastcall sqlite3FindTable(__int64 a1, unsigned __int8 *a2, _BYTE *a3)
{
  unsigned int v3; // esi
  unsigned __int8 *v4; // r12
  __int64 v6; // rdi
  __int64 v7; // r9
  __int64 v8; // r10
  __int64 *v9; // r11
  int v10; // r10d
  _BYTE *v11; // rdx
  unsigned __int8 *j; // r8
  __int64 v13; // r9
  __int64 v14; // rax
  __int64 result; // rax
  __int64 v16; // r9
  __int64 v17; // r10
  __int64 *v18; // r11
  int v19; // r10d
  _BYTE *v20; // r8
  unsigned __int8 *m; // rax
  __int64 v22; // r9
  __int64 v23; // rcx
  __int64 v24; // r11
  int v25; // r9d
  int v26; // edi
  __int64 v27; // r14
  __int64 v28; // rcx
  __int64 v29; // r8
  _DWORD *v30; // rbp
  __int64 *v31; // rbx
  int v32; // r10d
  _BYTE *v33; // rdx
  unsigned __int8 *jj; // r8
  __int64 v35; // r9
  __int64 v36; // rax
  int v37; // edx
  const char *v38; // r8
  unsigned __int8 *v39; // r9
  __int64 v40; // rcx
  _BYTE *v41; // rcx
  const char *v42; // rdx
  __int64 v43; // rcx
  unsigned __int8 v44; // al
  unsigned int i; // r8d
  int v46; // ecx
  unsigned __int8 v47; // cl
  unsigned __int8 *k; // r8
  int v49; // edx
  unsigned __int8 v50; // al
  unsigned __int8 *ii; // rdx
  int v52; // ecx
  _BYTE *v53; // rdx
  unsigned __int8 *n; // r10
  __int64 v55; // r11
  __int64 v56; // rax
  int v57; // ebx
  int v58; // edx
  const char *v59; // r8
  unsigned __int8 *v60; // r9
  __int64 v61; // rcx

  v3 = 0;
  v4 = a2;
  if ( !a3 )
  {
    v6 = *(_QWORD *)(a1 + 32);
    v7 = *(_QWORD *)(v6 + 56);
    v8 = *(_QWORD *)(v7 + 24);
    if ( v8 )
    {
      v44 = *a2;
      for ( i = 0; *a2; i = -1640531535 * (i + v46) )
      {
        ++a2;
        v46 = *((unsigned __int8 *)qword_1800B4ED0 + v44);
        v44 = *a2;
      }
      v9 = *(__int64 **)(v8 + 16LL * (i % *(_DWORD *)(v7 + 8)) + 8);
      v10 = *(_DWORD *)(v8 + 16LL * (i % *(_DWORD *)(v7 + 8)));
    }
    else
    {
      v9 = *(__int64 **)(v7 + 16);
      v10 = *(_DWORD *)(v7 + 12);
    }
LABEL_4:
    if ( v10 )
    {
      v11 = (_BYTE *)v9[3];
      for ( j = v4; ; ++j )
      {
        v13 = (unsigned __int8)*v11;
        v14 = *j;
        if ( (_DWORD)v13 == (_DWORD)v14 )
        {
          if ( !*v11 )
            goto LABEL_9;
        }
        else if ( *((unsigned __int8 *)qword_1800B4ED0 + v13) != *((unsigned __int8 *)qword_1800B4ED0 + v14) )
        {
          v9 = (__int64 *)*v9;
          --v10;
          goto LABEL_4;
        }
        ++v11;
      }
    }
    v9 = qword_1800D0DC0;
LABEL_9:
    result = v9[2];
    if ( result )
      return result;
    v16 = *(_QWORD *)(v6 + 24);
    v17 = *(_QWORD *)(v16 + 24);
    if ( v17 )
    {
      v47 = *v4;
      for ( k = v4; *k; v3 = -1640531535 * (v3 + v49) )
      {
        ++k;
        v49 = *((unsigned __int8 *)qword_1800B4ED0 + v47);
        v47 = *k;
      }
      v18 = *(__int64 **)(v17 + 16LL * (v3 % *(_DWORD *)(v16 + 8)) + 8);
      v19 = *(_DWORD *)(v17 + 16LL * (v3 % *(_DWORD *)(v16 + 8)));
    }
    else
    {
      v18 = *(__int64 **)(v16 + 16);
      v19 = *(_DWORD *)(v16 + 12);
    }
LABEL_12:
    if ( v19 )
    {
      v20 = (_BYTE *)v18[3];
      for ( m = v4; ; ++m )
      {
        v22 = (unsigned __int8)*v20;
        v23 = *m;
        if ( (_DWORD)v22 == (_DWORD)v23 )
        {
          if ( !*v20 )
            goto LABEL_18;
        }
        else if ( *((unsigned __int8 *)qword_1800B4ED0 + v22) != *((unsigned __int8 *)qword_1800B4ED0 + v23) )
        {
          v18 = (__int64 *)*v18;
          --v19;
          goto LABEL_12;
        }
        ++v20;
      }
    }
    v18 = qword_1800D0DC0;
LABEL_18:
    v24 = v18[2];
    if ( v24 )
      return v24;
    v57 = 2;
    if ( *(int *)(a1 + 40) > 2 )
    {
      do
      {
        v24 = *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v57 + *(_QWORD *)(a1 + 32) + 24) + 8LL, v4, 0) + 16);
        if ( v24 )
          return v24;
      }
      while ( ++v57 < *(_DWORD *)(a1 + 40) );
    }
    if ( !v4 )
      return v24;
    v58 = 7;
    v59 = "sqlite_";
    v60 = v4;
    while ( 1 )
    {
      v61 = *v60;
      --v58;
      if ( !(_BYTE)v61 || *((_BYTE *)qword_1800B4ED0 + v61) != *((_BYTE *)qword_1800B4ED0 + *(unsigned __int8 *)v59) )
        break;
      ++v60;
      ++v59;
      if ( v58 <= 0 )
      {
        --v58;
        break;
      }
    }
    if ( v58 >= 0
      && *((unsigned __int8 *)qword_1800B4ED0 + *v60) != *((unsigned __int8 *)qword_1800B4ED0 + *(unsigned __int8 *)v59) )
    {
      return v24;
    }
    if ( (unsigned int)sqlite3StrICmp(v4 + 7, "schema") )
    {
      if ( (unsigned int)sqlite3StrICmp(v4 + 7, "temp_schema") )
        return v24;
      v42 = "sqlite_temp_master";
      v43 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 56LL) + 8LL;
    }
    else
    {
      v42 = "sqlite_master";
      v43 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + 24LL) + 8LL;
    }
    return *(_QWORD *)(findElementWithHash(v43, v42, 0) + 16);
  }
  v25 = *(_DWORD *)(a1 + 40);
  v26 = 0;
  if ( v25 <= 0 )
    goto LABEL_26;
  do
  {
    v53 = a3;
    for ( n = *(unsigned __int8 **)(32LL * v26 + *(_QWORD *)(a1 + 32)); ; ++n )
    {
      v55 = (unsigned __int8)*v53;
      v56 = *n;
      if ( (_DWORD)v55 != (_DWORD)v56 )
        break;
      if ( !*v53 )
        goto LABEL_26;
LABEL_63:
      ++v53;
    }
    if ( *((unsigned __int8 *)qword_1800B4ED0 + v55) == *((unsigned __int8 *)qword_1800B4ED0 + v56) )
      goto LABEL_63;
    ++v26;
  }
  while ( v26 < v25 );
LABEL_26:
  if ( v26 < v25 )
    goto LABEL_27;
  if ( (unsigned int)sqlite3StrICmp(a3, "main") )
    return 0;
  v26 = 0;
LABEL_27:
  v27 = *(_QWORD *)(a1 + 32);
  v28 = *(_QWORD *)(32LL * v26 + v27 + 24);
  v29 = *(_QWORD *)(v28 + 24);
  v30 = (_DWORD *)(v28 + 8);
  if ( v29 )
  {
    v50 = *v4;
    for ( ii = v4; *ii; v3 = -1640531535 * (v3 + v52) )
    {
      ++ii;
      v52 = *((unsigned __int8 *)qword_1800B4ED0 + v50);
      v50 = *ii;
    }
    v31 = *(__int64 **)(v29 + 16LL * (v3 % *v30) + 8);
    v32 = *(_DWORD *)(v29 + 16LL * (v3 % *v30));
  }
  else
  {
    v31 = *(__int64 **)(v28 + 16);
    v32 = *(_DWORD *)(v28 + 12);
  }
LABEL_29:
  if ( v32 )
  {
    v33 = (_BYTE *)v31[3];
    for ( jj = v4; ; ++jj )
    {
      v35 = (unsigned __int8)*v33;
      v36 = *jj;
      if ( (_DWORD)v35 == (_DWORD)v36 )
      {
        if ( !*v33 )
          goto LABEL_35;
      }
      else if ( *((unsigned __int8 *)qword_1800B4ED0 + v35) != *((unsigned __int8 *)qword_1800B4ED0 + v36) )
      {
        v31 = (__int64 *)*v31;
        --v32;
        goto LABEL_29;
      }
      ++v33;
    }
  }
  v31 = qword_1800D0DC0;
LABEL_35:
  v24 = v31[2];
  if ( v24 || !v4 )
    return v24;
  v37 = 7;
  v38 = "sqlite_";
  v39 = v4;
  while ( 1 )
  {
    v40 = *v39;
    --v37;
    if ( !(_BYTE)v40 || *((_BYTE *)qword_1800B4ED0 + v40) != *((_BYTE *)qword_1800B4ED0 + *(unsigned __int8 *)v38) )
      break;
    ++v39;
    ++v38;
    if ( v37 <= 0 )
    {
      --v37;
      break;
    }
  }
  if ( v37 >= 0
    && *((unsigned __int8 *)qword_1800B4ED0 + *v39) != *((unsigned __int8 *)qword_1800B4ED0 + *(unsigned __int8 *)v38) )
  {
    return v24;
  }
  v41 = v4 + 7;
  if ( v26 == 1 )
  {
    if ( (unsigned int)sqlite3StrICmp(v41, "temp_schema")
      && (unsigned int)sqlite3StrICmp(v4 + 7, "schema")
      && (unsigned int)sqlite3StrICmp(v4 + 7, "master") )
    {
      return v24;
    }
    v42 = "sqlite_temp_master";
    v43 = *(_QWORD *)(v27 + 56) + 8LL;
    return *(_QWORD *)(findElementWithHash(v43, v42, 0) + 16);
  }
  if ( !(unsigned int)sqlite3StrICmp(v41, "schema") )
  {
    v42 = "sqlite_master";
    v43 = (__int64)v30;
    return *(_QWORD *)(findElementWithHash(v43, v42, 0) + 16);
  }
  return v24;
}

```

## disassembly

```asm
0x18000a180  push    rbx
0x18000a182  push    rbp
0x18000a183  push    rsi
0x18000a184  push    rdi
0x18000a185  push    r12
0x18000a187  push    r14
0x18000a189  push    r15
0x18000a18b  sub     rsp, 20h
0x18000a18f  xor     esi, esi
0x18000a191  lea     r15, qword_1800B4ED0
0x18000a198  mov     r12, rdx
0x18000a19b  mov     rbp, rcx
0x18000a19e  test    r8, r8
0x18000a1a1  jnz     loc_18000A29E
0x18000a1a7  mov     rdi, [rcx+20h]
0x18000a1ab  mov     r9, [rdi+38h]
0x18000a1af  mov     r10, [r9+18h]
0x18000a1b3  test    r10, r10
0x18000a1b6  jnz     loc_18000A3EC
0x18000a1bc  mov     r11, [r9+10h]
0x18000a1c0  mov     r10d, [r9+0Ch]
0x18000a1c4  test    r10d, r10d
0x18000a1c7  jz      loc_18000A3DD
0x18000a1cd  mov     rdx, [r11+18h]
0x18000a1d1  mov     r8, r12
0x18000a1d4  nop     dword ptr [rax+00h]
0x18000a1d8  nop     dword ptr [rax+rax+00000000h]
0x18000a1e0  movzx   r9d, byte ptr [rdx]
0x18000a1e4  movzx   eax, byte ptr [r8]
0x18000a1e8  cmp     r9d, eax
0x18000a1eb  jnz     short loc_18000A26B
0x18000a1ed  test    r9d, r9d
0x18000a1f0  jz      short loc_18000A1FA
0x18000a1f2  inc     rdx
0x18000a1f5  inc     r8
0x18000a1f8  jmp     short loc_18000A1E0
0x18000a1fa  lea     rbx, qword_1800D0DC0
0x18000a201  mov     rax, [r11+10h]
0x18000a205  test    rax, rax
0x18000a208  jnz     short loc_18000A25C
0x18000a20a  mov     r9, [rdi+18h]
0x18000a20e  mov     r10, [r9+18h]
0x18000a212  test    r10, r10
0x18000a215  jnz     loc_18000A439
0x18000a21b  mov     r11, [r9+10h]
0x18000a21f  mov     r10d, [r9+0Ch]
0x18000a223  test    r10d, r10d
0x18000a226  jz      short loc_18000A249
0x18000a228  mov     r8, [r11+18h]
0x18000a22c  mov     rax, r12
0x18000a22f  nop
0x18000a230  movzx   r9d, byte ptr [r8]
0x18000a234  movzx   ecx, byte ptr [rax]
0x18000a237  cmp     r9d, ecx
0x18000a23a  jnz     short loc_18000A288
0x18000a23c  test    r9d, r9d
0x18000a23f  jz      short loc_18000A24C
0x18000a241  inc     r8
0x18000a244  inc     rax
0x18000a247  jmp     short loc_18000A230
0x18000a249  mov     r11, rbx
0x18000a24c  mov     r11, [r11+10h]
0x18000a250  test    r11, r11
0x18000a253  jz      loc_18000A528
0x18000a259  mov     rax, r11
0x18000a25c  add     rsp, 20h
0x18000a260  pop     r15
0x18000a262  pop     r14
0x18000a264  pop     r12
0x18000a266  pop     rdi
0x18000a267  pop     rsi
0x18000a268  pop     rbp
0x18000a269  pop     rbx
0x18000a26a  retn
0x18000a26b  movzx   ecx, byte ptr [rax+r15]
0x18000a270  movzx   eax, byte ptr [r9+r15]
0x18000a275  cmp     eax, ecx
0x18000a277  jz      loc_18000A1F2
0x18000a27d  mov     r11, [r11]
0x18000a280  dec     r10d
0x18000a283  jmp     loc_18000A1C4
0x18000a288  movzx   edx, byte ptr [rcx+r15]
0x18000a28d  movzx   ecx, byte ptr [r9+r15]
0x18000a292  cmp     ecx, edx
0x18000a294  jz      short loc_18000A241
0x18000a296  mov     r11, [r11]
0x18000a299  dec     r10d
0x18000a29c  jmp     short loc_18000A223
0x18000a29e  mov     r9d, [rcx+28h]
0x18000a2a2  mov     edi, esi
0x18000a2a4  test    r9d, r9d
0x18000a2a7  jg      loc_18000A4D5
0x18000a2ad  cmp     edi, r9d
0x18000a2b0  jge     loc_18000A688
0x18000a2b6  mov     r14, [rbp+20h]
0x18000a2ba  movsxd  rax, edi
0x18000a2bd  shl     rax, 5
0x18000a2c1  mov     rcx, [rax+r14+18h]
0x18000a2c6  mov     r8, [rcx+18h]
0x18000a2ca  lea     rbp, [rcx+8]
0x18000a2ce  test    r8, r8
0x18000a2d1  jnz     loc_18000A487
0x18000a2d7  mov     rbx, [rcx+10h]
0x18000a2db  mov     r10d, [rcx+0Ch]
0x18000a2df  nop
0x18000a2e0  test    r10d, r10d
0x18000a2e3  jz      short loc_18000A30E
0x18000a2e5  mov     rdx, [rbx+18h]
0x18000a2e9  mov     r8, r12
0x18000a2ec  nop     dword ptr [rax+00h]
0x18000a2f0  movzx   r9d, byte ptr [rdx]
0x18000a2f4  movzx   eax, byte ptr [r8]
0x18000a2f8  cmp     r9d, eax
0x18000a2fb  jnz     loc_18000A3C0
0x18000a301  test    r9d, r9d
0x18000a304  jz      short loc_18000A315
0x18000a306  inc     rdx
0x18000a309  inc     r8
0x18000a30c  jmp     short loc_18000A2F0
0x18000a30e  lea     rbx, qword_1800D0DC0
0x18000a315  mov     r11, [rbx+10h]
0x18000a319  test    r11, r11
0x18000a31c  jnz     loc_18000A259
0x18000a322  test    r12, r12
0x18000a325  jz      loc_18000A259
0x18000a32b  mov     edx, 7
0x18000a330  lea     r8, aSqlite_0; "sqlite_"
0x18000a337  mov     r9, r12
0x18000a33a  nop     word ptr [rax+rax+00h]
0x18000a340  movzx   ecx, byte ptr [r9]
0x18000a344  dec     edx
0x18000a346  test    cl, cl
0x18000a348  jz      short loc_18000A365
0x18000a34a  movzx   eax, byte ptr [r8]
0x18000a34e  movzx   eax, byte ptr [rax+r15]
0x18000a353  cmp     [rcx+r15], al
0x18000a357  jnz     short loc_18000A365
0x18000a359  inc     r9
0x18000a35c  inc     r8
0x18000a35f  test    edx, edx
0x18000a361  jg      short loc_18000A340
0x18000a363  dec     edx
0x18000a365  test    edx, edx
0x18000a367  js      short loc_18000A383
0x18000a369  movzx   eax, byte ptr [r8]
0x18000a36d  movzx   ecx, byte ptr [rax+r15]
0x18000a372  movzx   eax, byte ptr [r9]
0x18000a376  movzx   eax, byte ptr [rax+r15]
0x18000a37b  cmp     eax, ecx
0x18000a37d  jnz     loc_18000A259
0x18000a383  lea     rcx, [r12+7]
0x18000a388  cmp     edi, 1
0x18000a38b  jz      loc_18000A5DD
0x18000a391  lea     rdx, aSqliteSchema+7; "schema"
0x18000a398  call    sqlite3StrICmp
0x18000a39d  test    eax, eax
0x18000a39f  jnz     loc_18000A259
0x18000a3a5  lea     rdx, aSqliteMaster; "sqlite_master"
0x18000a3ac  mov     rcx, rbp
0x18000a3af  xor     r8d, r8d
0x18000a3b2  call    findElementWithHash
0x18000a3b7  mov     r11, [rax+10h]
0x18000a3bb  jmp     loc_18000A259
0x18000a3c0  movzx   ecx, byte ptr [rax+r15]
0x18000a3c5  movzx   eax, byte ptr [r9+r15]
0x18000a3ca  cmp     eax, ecx
0x18000a3cc  jz      loc_18000A306
0x18000a3d2  mov     rbx, [rbx]
0x18000a3d5  dec     r10d
0x18000a3d8  jmp     loc_18000A2E0
0x18000a3dd  lea     rbx, qword_1800D0DC0
0x18000a3e4  mov     r11, rbx
0x18000a3e7  jmp     loc_18000A201
0x18000a3ec  movzx   eax, byte ptr [rdx]
0x18000a3ef  mov     r8d, esi
0x18000a3f2  test    al, al
0x18000a3f4  jz      short loc_18000A41D
0x18000a3f6  nop     word ptr [rax+rax+00000000h]
0x18000a400  movzx   eax, al
0x18000a403  lea     rdx, [rdx+1]
0x18000a407  movzx   ecx, byte ptr [rax+r15]
0x18000a40c  movzx   eax, byte ptr [rdx]
0x18000a40f  add     ecx, r8d
0x18000a412  imul    r8d, ecx, 9E3779B1h
0x18000a419  test    al, al
0x18000a41b  jnz     short loc_18000A400
0x18000a41d  xor     edx, edx
0x18000a41f  mov     eax, r8d
0x18000a422  div     dword ptr [r9+8]
0x18000a426  mov     ecx, edx
0x18000a428  add     rcx, rcx
0x18000a42b  mov     r11, [r10+rcx*8+8]
0x18000a430  mov     r10d, [r10+rcx*8]
0x18000a434  jmp     loc_18000A1C4
0x18000a439  movzx   ecx, byte ptr [r12]
0x18000a43e  mov     r8, r12
0x18000a441  test    cl, cl
0x18000a443  jz      short loc_18000A46C
0x18000a445  nop     word ptr [rax+rax+00000000h]
0x18000a450  movzx   ecx, cl
0x18000a453  lea     r8, [r8+1]
0x18000a457  movzx   edx, byte ptr [rcx+r15]
0x18000a45c  movzx   ecx, byte ptr [r8]
0x18000a460  add     edx, esi
0x18000a462  imul    esi, edx, 9E3779B1h
0x18000a468  test    cl, cl
0x18000a46a  jnz     short loc_18000A450
0x18000a46c  xor     edx, edx
0x18000a46e  mov     eax, esi
0x18000a470  div     dword ptr [r9+8]
0x18000a474  mov     ecx, edx
0x18000a476  add     rcx, rcx
0x18000a479  mov     r11, [r10+rcx*8+8]
0x18000a47e  mov     r10d, [r10+rcx*8]
0x18000a482  jmp     loc_18000A223
0x18000a487  movzx   eax, byte ptr [r12]
0x18000a48c  mov     rdx, r12
0x18000a48f  test    al, al
0x18000a491  jz      short loc_18000A4BB
0x18000a493  nop     dword ptr [rax+00h]
0x18000a497  nop     word ptr [rax+rax+00000000h]
0x18000a4a0  movzx   eax, al
0x18000a4a3  lea     rdx, [rdx+1]
0x18000a4a7  movzx   ecx, byte ptr [rax+r15]
0x18000a4ac  movzx   eax, byte ptr [rdx]
0x18000a4af  add     ecx, esi
0x18000a4b1  imul    esi, ecx, 9E3779B1h
0x18000a4b7  test    al, al
0x18000a4b9  jnz     short loc_18000A4A0
0x18000a4bb  xor     edx, edx
0x18000a4bd  mov     eax, esi
0x18000a4bf  div     dword ptr [rbp+0]
0x18000a4c2  mov     ecx, edx
0x18000a4c4  add     rcx, rcx
0x18000a4c7  mov     rbx, [r8+rcx*8+8]
0x18000a4cc  mov     r10d, [r8+rcx*8]
0x18000a4d0  jmp     loc_18000A2E0
0x18000a4d5  mov     rbx, [rcx+20h]
0x18000a4d9  movsxd  rax, edi
0x18000a4dc  mov     rdx, r8
0x18000a4df  shl     rax, 5
0x18000a4e3  mov     r10, [rax+rbx]
0x18000a4e7  nop     word ptr [rax+rax+00000000h]
0x18000a4f0  movzx   r11d, byte ptr [rdx]
0x18000a4f4  movzx   eax, byte ptr [r10]
0x18000a4f8  cmp     r11d, eax
0x18000a4fb  jnz     short loc_18000A50E
0x18000a4fd  test    r11d, r11d
0x18000a500  jz      loc_18000A2AD
0x18000a506  inc     rdx
0x18000a509  inc     r10
0x18000a50c  jmp     short loc_18000A4F0
0x18000a50e  movzx   ecx, byte ptr [rax+r15]
0x18000a513  movzx   eax, byte ptr [r11+r15]
0x18000a518  cmp     eax, ecx
0x18000a51a  jz      short loc_18000A506
0x18000a51c  inc     edi
0x18000a51e  cmp     edi, r9d
0x18000a521  jl      short loc_18000A4D9
0x18000a523  jmp     loc_18000A2AD
0x18000a528  mov     ebx, 2
0x18000a52d  cmp     [rbp+28h], ebx
0x18000a530  jg      loc_18000A650
0x18000a536  test    r12, r12
0x18000a539  jz      loc_18000A259
0x18000a53f  mov     edx, 7
0x18000a544  lea     r8, aSqlite_0; "sqlite_"
0x18000a54b  mov     r9, r12
0x18000a54e  xchg    ax, ax
0x18000a550  movzx   ecx, byte ptr [r9]
0x18000a554  dec     edx
0x18000a556  test    cl, cl
0x18000a558  jz      short loc_18000A575
0x18000a55a  movzx   eax, byte ptr [r8]
0x18000a55e  movzx   eax, byte ptr [rax+r15]
0x18000a563  cmp     [rcx+r15], al
0x18000a567  jnz     short loc_18000A575
0x18000a569  inc     r9
0x18000a56c  inc     r8
0x18000a56f  test    edx, edx
0x18000a571  jg      short loc_18000A550
0x18000a573  dec     edx
0x18000a575  test    edx, edx
0x18000a577  js      short loc_18000A593
0x18000a579  movzx   eax, byte ptr [r8]
0x18000a57d  movzx   ecx, byte ptr [rax+r15]
0x18000a582  movzx   eax, byte ptr [r9]
0x18000a586  movzx   eax, byte ptr [rax+r15]
0x18000a58b  cmp     eax, ecx
0x18000a58d  jnz     loc_18000A259
0x18000a593  lea     rdx, aSqliteSchema+7; "schema"
0x18000a59a  lea     rcx, [r12+7]
0x18000a59f  call    sqlite3StrICmp
0x18000a5a4  test    eax, eax
0x18000a5a6  jz      loc_18000A62F
0x18000a5ac  lea     rdx, aSqliteTempSche+7; "temp_schema"
0x18000a5b3  lea     rcx, [r12+7]
0x18000a5b8  call    sqlite3StrICmp
0x18000a5bd  test    eax, eax
0x18000a5bf  jnz     loc_18000A259
  ... truncated ...
```
