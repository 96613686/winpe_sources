# sqlite3_blob_open

- ea: `0x180010ca0`
- end: `0x180011514`
- name: `sqlite3_blob_open`
- size: `2164`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: ``

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005980`
- `0x180010ca0`
- `0x180023dd0`
- `0x180027020`
- `0x180029d80`
- `0x18002aef0`
- `0x18002b2d0`
- `0x180044690`
- `0x18004dba0`
- `0x180071400`
- `0x1800743d0`
- `0x180074530`
- `0x180087d40`
- `0x180088530`
- `0x18008b770`
- `0x1800a3b40`
- `0x1800a3c90`
- `0x1800aead0`
- `0x1800b15b0`
- `0x1800c3f40`
- `0x18010d010`

## string_xrefs

- `0x180011365`: `cannot open virtual table: %s`
- `0x18001135c`: `cannot open table without rowid: %s`
- `0x180011353`: `cannot open view: %s`
- `0x180011312`: `cannot open %s column for writing`

## pseudocode

```c
__int64 __fastcall sqlite3_blob_open(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        __int64 a5,
        int a6,
        unsigned __int64 *a7)
{
  unsigned int v8; // esi
  _QWORD *v9; // r12
  const char *v10; // rbx
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // r13
  unsigned __int64 v14; // rdi
  bool v15; // zf
  __int64 v16; // rax
  __int64 v17; // r13
  char v18; // cl
  int v19; // ecx
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r14
  int v23; // r10d
  __int64 v24; // r11
  const char *v25; // r9
  _BYTE *i; // r8
  __int64 v27; // rax
  const char *v28; // r10
  __int64 j; // r8
  int v30; // r9d
  unsigned int k; // edx
  const char *v32; // rax
  __int64 m; // r9
  int v34; // eax
  int v35; // edx
  __int64 v36; // rdi
  int *v37; // rcx
  int v38; // esi
  __int64 v39; // rdx
  int v40; // r8d
  int v41; // r9d
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rbx
  __int64 v48; // rcx
  __int64 v49; // rax
  unsigned int v50; // eax
  __int64 v51; // rax
  __int64 v52; // rbx
  const char *v53; // r8
  unsigned int v54; // ebx
  BOOL v56; // [rsp+30h] [rbp-D0h]
  unsigned int v57; // [rsp+34h] [rbp-CCh]
  int v58; // [rsp+38h] [rbp-C8h]
  _QWORD *v59; // [rsp+40h] [rbp-C0h] BYREF
  const char *v60; // [rsp+48h] [rbp-B8h]
  __int64 v61; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+58h] [rbp-A8h]
  __int64 v63; // [rsp+60h] [rbp-A0h]
  unsigned __int64 *v64; // [rsp+68h] [rbp-98h]
  __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  __int64 v66[5]; // [rsp+78h] [rbp-88h] BYREF
  int v67; // [rsp+A4h] [rbp-5Ch]
  int v68; // [rsp+A8h] [rbp-58h]
  __int64 v69; // [rsp+170h] [rbp+70h]
  __int128 v70; // [rsp+188h] [rbp+88h]
  __int128 v71; // [rsp+198h] [rbp+98h]
  __int128 v72; // [rsp+1A8h] [rbp+A8h]
  __int128 v73; // [rsp+1B8h] [rbp+B8h]
  __int128 v74; // [rsp+1C8h] [rbp+C8h]
  __int128 v75; // [rsp+1D8h] [rbp+D8h]
  __int128 v76; // [rsp+1E8h] [rbp+E8h]
  __int128 v77; // [rsp+1F8h] [rbp+F8h]
  __int64 v78; // [rsp+208h] [rbp+108h]

  v64 = a7;
  v8 = 0;
  v58 = 0;
  v9 = 0;
  *a7 = 0;
  v10 = a4;
  v57 = 0;
  v11 = *(_QWORD *)(a1 + 24);
  v56 = a6 != 0;
  v12 = a3;
  v60 = a4;
  v13 = a2;
  v62 = a3;
  v63 = a2;
  if ( v11 )
    ((void (*)(void))xmmword_18013C230)();
  v61 = sqlite3DbMallocRawNN(a1, 56);
  v14 = v61;
  if ( v61 )
  {
    *(_OWORD *)v61 = 0;
    *(_OWORD *)(v14 + 16) = 0;
    *(_OWORD *)(v14 + 32) = 0;
    *(_QWORD *)(v14 + 48) = 0;
  }
  while ( 1 )
  {
    memset_0(v66, 0, 0xD8u);
    v65 = a1;
    v15 = *(_BYTE *)(a1 + 103) == 0;
    v78 = 0;
    v69 = *(_QWORD *)(a1 + 352);
    *(_QWORD *)(a1 + 352) = &v65;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v76 = 0;
    v77 = 0;
    if ( !v15 )
      sqlite3ErrorMsg(&v65, "out of memory");
    if ( !v14 )
      goto LABEL_85;
    if ( v9 )
    {
      if ( (unsigned __int64)v9 >= *(_QWORD *)(a1 + 496) )
        goto LABEL_130;
      if ( (unsigned __int64)v9 >= *(_QWORD *)(a1 + 480) )
      {
        *v9 = *(_QWORD *)(a1 + 472);
        *(_QWORD *)(a1 + 472) = v9;
        goto LABEL_17;
      }
      if ( (unsigned __int64)v9 < *(_QWORD *)(a1 + 488) )
      {
LABEL_130:
        if ( *(_QWORD *)(a1 + 776) )
          measureAllocationSize(a1, v9);
        else
          sqlite3_free(v9);
      }
      else
      {
        *v9 = *(_QWORD *)(a1 + 456);
        *(_QWORD *)(a1 + 456) = v9;
      }
    }
LABEL_17:
    v9 = 0;
    v59 = 0;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeEnterAll(a1);
    v16 = sqlite3LocateTable(&v65, 0, v12, v13);
    v17 = v16;
    if ( !v16 )
      goto LABEL_92;
    v18 = *(_BYTE *)(v16 + 63);
    if ( v18 == 1 )
    {
      sqlite3ErrorMsg(&v65, "cannot open virtual table: %s", v12);
      goto LABEL_92;
    }
    if ( *(char *)(v16 + 48) < 0 )
    {
      sqlite3ErrorMsg(&v65, "cannot open table without rowid: %s", v12);
LABEL_92:
      v51 = v66[0];
      if ( !v66[0] )
        goto LABEL_95;
      v66[0] = 0;
LABEL_94:
      v9 = (_QWORD *)v51;
LABEL_95:
      v8 = 1;
      if ( !*(_BYTE *)(a1 + 111) )
        btreeLeaveAll(a1);
      goto LABEL_98;
    }
    if ( v18 == 2 )
    {
      sqlite3ErrorMsg(&v65, "cannot open view: %s", v12);
      goto LABEL_92;
    }
    *(_QWORD *)(v14 + 48) = v16;
    v19 = -32768;
    v20 = *(_QWORD *)(v16 + 96);
    if ( v20 )
    {
      v21 = *(_QWORD *)(a1 + 32);
      v19 = 0;
      if ( *(_QWORD *)(v21 + 24) != v20 )
      {
        do
          ++v19;
        while ( *(_QWORD *)(32LL * v19 + v21 + 24) != v20 );
      }
    }
    v22 = 0;
    *(_QWORD *)(v14 + 40) = *(_QWORD *)(32LL * v19 + *(_QWORD *)(a1 + 32));
    v23 = *(__int16 *)(v16 + 54);
    if ( v23 > 0 )
    {
      v24 = *(_QWORD *)(v16 + 8);
      do
      {
        v25 = v10;
        for ( i = *(_BYTE **)(v24 + 24 * v22); ; ++i )
        {
          while ( 1 )
          {
            v27 = *(unsigned __int8 *)v25;
            if ( (unsigned __int8)*i != (_DWORD)v27 )
              break;
            if ( !*i )
              goto LABEL_36;
            ++i;
            ++v25;
          }
          if ( *((unsigned __int8 *)qword_180114680 + (unsigned __int8)*i) != *((unsigned __int8 *)qword_180114680 + v27) )
            break;
          ++v25;
        }
        v22 = (unsigned int)(v22 + 1);
      }
      while ( (int)v22 < v23 );
    }
    if ( (_DWORD)v22 == v23 )
    {
      v51 = sqlite3MPrintf(a1, "no such column: \"%s\"", v10);
      goto LABEL_94;
    }
LABEL_36:
    if ( a6 )
    {
      v28 = 0;
      if ( (*(_DWORD *)(a1 + 48) & 0x4000LL) != 0 )
      {
        for ( j = *(_QWORD *)(v17 + 72); j; j = *(_QWORD *)(j + 8) )
        {
          v30 = *(_DWORD *)(j + 40);
          for ( k = 0; (int)k < v30; v28 = v32 )
          {
            v32 = "foreign key";
            if ( *(_DWORD *)(j + 16 * (k + 4LL)) != (_DWORD)v22 )
              v32 = v28;
            ++k;
          }
        }
      }
      for ( m = *(_QWORD *)(v17 + 16); m; m = *(_QWORD *)(m + 40) )
      {
        if ( *(_WORD *)(m + 94) )
        {
          v34 = 0;
          do
          {
            v35 = *(__int16 *)(*(_QWORD *)(m + 8) + 2LL * v34);
            if ( v35 == (_DWORD)v22 || (_WORD)v35 == 0xFFFE )
              v28 = "indexed";
            ++v34;
          }
          while ( v34 < *(unsigned __int16 *)(m + 94) );
        }
      }
      if ( v28 )
      {
        v51 = sqlite3MPrintf(a1, "cannot open %s column for writing", v28);
        goto LABEL_94;
      }
    }
    v36 = sqlite3VdbeCreate(&v65);
    *(_QWORD *)(v61 + 24) = v36;
    if ( v36 )
    {
      v37 = *(int **)(v17 + 96);
      v38 = -32768;
      if ( v37 )
      {
        v39 = *(_QWORD *)(a1 + 32);
        v38 = 0;
        if ( *(int **)(v39 + 24) != v37 )
        {
          do
            ++v38;
          while ( *(int **)(32LL * v38 + v39 + 24) != v37 );
        }
      }
      v40 = v37[1];
      v41 = *v37;
      v42 = *(int *)(v36 + 144);
      if ( *(_DWORD *)(v36 + 148) > (int)v42 )
      {
        *(_DWORD *)(v36 + 144) = v42 + 1;
        v43 = 3 * v42;
        v44 = *(_QWORD *)(v36 + 136);
        *(_DWORD *)(v44 + 8 * v43) = 64770;
        *(_DWORD *)(v44 + 8 * v43 + 4) = v38;
        *(_DWORD *)(v44 + 8 * v43 + 12) = v41;
        v45 = v44 + 8 * v43;
        *(_DWORD *)(v45 + 16) = v40;
        *(_DWORD *)(v45 + 8) = v56;
      }
      else
      {
        addOp4IntSlow(v36, 2, v38, v56, v41, v40);
      }
      v46 = *(int *)(v36 + 144);
      if ( (int)v46 > 0 )
        *(_WORD *)(*(_QWORD *)(v36 + 136) + 24 * v46 - 22) = 1;
      if ( *(_DWORD *)(v36 + 144) + 6 > *(_DWORD *)(v36 + 148) && (unsigned int)growOpArray(v36, 6) )
      {
        v47 = 0;
      }
      else
      {
        v48 = 3LL * *(int *)(v36 + 144);
        v49 = *(_QWORD *)(v36 + 136);
        *(_QWORD *)(v49 + 8 * v48) = 169;
        v47 = v49 + 8 * v48;
        *(_QWORD *)(v47 + 8) = 0;
        *(_QWORD *)(v47 + 16) = 0;
        *(_QWORD *)(v47 + 24) = 112;
        *(_QWORD *)(v47 + 32) = 0;
        *(_QWORD *)(v47 + 40) = 0;
        *(_BYTE *)(v47 + 48) = 31;
        *(_DWORD *)(v47 + 52) = 0;
        *(_DWORD *)(v47 + 56) = 5;
        *(_DWORD *)(v47 + 56) = *(_DWORD *)(v36 + 144) + 5;
        *(_DWORD *)(v47 + 60) = 1;
        *(_BYTE *)(v47 + 49) = 0;
        *(_QWORD *)(v47 + 64) = 0;
        *(_WORD *)(v47 + 50) = 0;
        *(_QWORD *)(v47 + 72) = 94;
        *(_DWORD *)(v47 + 80) = 0;
        *(_DWORD *)(v47 + 84) = 1;
        *(_QWORD *)(v47 + 88) = 0;
        *(_DWORD *)(v47 + 96) = 84;
        *(_QWORD *)(v47 + 100) = 1;
        *(_DWORD *)(v47 + 108) = 0;
        *(_QWORD *)(v47 + 112) = 0;
        *(_QWORD *)(v47 + 120) = 70;
        *(_QWORD *)(v47 + 128) = 0;
        *(_QWORD *)(v47 + 136) = 0;
        *(_DWORD *)(v36 + 144) += 6;
      }
      *(_DWORD *)(v36 + 204) |= 1 << v38;
      if ( v38 != 1 && *(_BYTE *)(*(_QWORD *)(32LL * v38 + *(_QWORD *)(*(_QWORD *)v36 + 32LL) + 8) + 17LL) )
        *(_DWORD *)(v36 + 208) |= 1 << v38;
      if ( !*(_BYTE *)(a1 + 103) )
      {
        *(_DWORD *)(v47 + 4) = v38;
        *(_DWORD *)(v47 + 8) = *(_DWORD *)(v17 + 40);
        *(_DWORD *)(v47 + 12) = v56;
        if ( !*(_BYTE *)(*(_QWORD *)v36 + 103LL) )
          vdbeChangeP4Full(v36, *(_QWORD *)(v36 + 136) + 48LL, *(_QWORD *)v17, 0);
        if ( !*(_BYTE *)(a1 + 103) )
        {
          if ( a6 )
            *(_BYTE *)(v47 + 24) = 113;
          *(_DWORD *)(v47 + 32) = *(_DWORD *)(v17 + 40);
          *(_DWORD *)(v47 + 36) = v38;
          *(_BYTE *)(v47 + 25) = -3;
          *(_DWORD *)(v47 + 40) = *(__int16 *)(v17 + 54) + 1;
          *(_DWORD *)(v47 + 80) = *(__int16 *)(v17 + 54);
          LOWORD(v71) = 0;
          v68 = 1;
          v67 = 1;
          sqlite3VdbeMakeReady(v36, &v65);
        }
      }
      v10 = v60;
      v8 = v57;
    }
    v14 = v61;
    *(_WORD *)(v61 + 8) = v22;
    *(_QWORD *)(v14 + 32) = a1;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeLeaveAll(a1);
    if ( *(_BYTE *)(a1 + 103) )
      goto LABEL_85;
    v50 = blobSeekToRow(v14, a5, &v59);
    v8 = v50;
    v57 = v50;
    if ( ++v58 >= 50 || v50 != 17 )
      break;
    sqlite3ParseObjectReset(&v65);
    v9 = v59;
    v12 = v62;
    v13 = v63;
  }
  v9 = v59;
LABEL_85:
  if ( !v8 && !*(_BYTE *)(a1 + 103) )
  {
    *v64 = v14;
    goto LABEL_110;
  }
  if ( !v14 )
    goto LABEL_110;
LABEL_98:
  v52 = *(_QWORD *)(v14 + 24);
  if ( v52 )
  {
    if ( *(_BYTE *)(v52 + 199) )
      sqlite3VdbeReset(*(_QWORD *)(v14 + 24));
    sqlite3VdbeDelete(v52);
  }
  if ( v14 >= *(_QWORD *)(a1 + 496) )
    goto LABEL_131;
  if ( v14 >= *(_QWORD *)(a1 + 480) )
  {
    *(_QWORD *)v14 = *(_QWORD *)(a1 + 472);
    *(_QWORD *)(a1 + 472) = v14;
    goto LABEL_110;
  }
  if ( v14 < *(_QWORD *)(a1 + 488) )
  {
LABEL_131:
    if ( *(_QWORD *)(a1 + 776) )
      measureAllocationSize(a1, v14);
    else
      sqlite3_free(v14);
  }
  else
  {
    *(_QWORD *)v14 = *(_QWORD *)(a1 + 456);
    *(_QWORD *)(a1 + 456) = v14;
  }
LABEL_110:
  v53 = 0;
  if ( v9 )
    v53 = "%s";
  sqlite3ErrorWithMsg(a1, v8, v53, v9);
  if ( v9 )
  {
    if ( (unsigned __int64)v9 < *(_QWORD *)(a1 + 496) )
    {
      if ( (unsigned __int64)v9 >= *(_QWORD *)(a1 + 480) )
      {
        *v9 = *(_QWORD *)(a1 + 472);
        *(_QWORD *)(a1 + 472) = v9;
        goto LABEL_121;
      }
      if ( (unsigned __int64)v9 >= *(_QWORD *)(a1 + 488) )
      {
        *v9 = *(_QWORD *)(a1 + 456);
        *(_QWORD *)(a1 + 456) = v9;
        goto LABEL_121;
      }
    }
    if ( *(_QWORD *)(a1 + 776) )
      measureAllocationSize(a1, v9);
    else
      sqlite3_free(v9);
  }
LABEL_121:
  sqlite3ParseObjectReset(&v65);
  if ( *(_BYTE *)(a1 + 103) || v8 )
    v54 = apiHandleError(a1, v8);
  else
    v54 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_18013C240)();
  return v54;
}

```

## disassembly

```asm
0x180010ca0  push    rbp
0x180010ca2  push    rbx
0x180010ca3  push    rsi
0x180010ca4  push    rdi
0x180010ca5  push    r12
0x180010ca7  push    r13
0x180010ca9  push    r14
0x180010cab  push    r15
0x180010cad  lea     rbp, [rsp-128h]
0x180010cb5  sub     rsp, 228h
0x180010cbc  mov     rax, cs:__security_cookie
0x180010cc3  xor     rax, rsp
0x180010cc6  mov     [rbp+160h+var_50], rax
0x180010ccd  mov     rax, [rbp+160h+arg_30]
0x180010cd4  mov     r15, rcx
0x180010cd7  xor     ecx, ecx
0x180010cd9  mov     [rsp+260h+var_1F8], rax
0x180010cde  cmp     [rbp+160h+arg_28], ecx
0x180010ce4  mov     esi, ecx
0x180010ce6  mov     [rsp+260h+var_228], ecx
0x180010cea  mov     r12d, ecx
0x180010ced  mov     [rax], rcx
0x180010cf0  mov     rbx, r9
0x180010cf3  mov     eax, ecx
0x180010cf5  mov     [rsp+260h+var_22C], ecx
0x180010cf9  mov     rcx, [r15+18h]
0x180010cfd  setnz   al
0x180010d00  mov     [rsp+260h+var_230], eax
0x180010d04  mov     r14, r8
0x180010d07  mov     [rsp+260h+var_218], rbx
0x180010d0c  mov     r13, rdx
0x180010d0f  mov     [rsp+260h+var_208], r8
0x180010d14  mov     [rsp+260h+var_200], rdx
0x180010d19  test    rcx, rcx
0x180010d1c  jz      short loc_180010D2A
0x180010d1e  mov     rax, qword ptr cs:xmmword_18013C230
0x180010d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d2a  mov     edx, 38h ; '8'
0x180010d2f  mov     rcx, r15
0x180010d32  call    sqlite3DbMallocRawNN
0x180010d37  mov     [rsp+260h+var_210], rax
0x180010d3c  mov     rdi, rax
0x180010d3f  test    rax, rax
0x180010d42  jz      short loc_180010D60
0x180010d44  xorps   xmm0, xmm0
0x180010d47  xor     eax, eax
0x180010d49  movups  xmmword ptr [rdi], xmm0
0x180010d4c  movups  xmmword ptr [rdi+10h], xmm0
0x180010d50  movups  xmmword ptr [rdi+20h], xmm0
0x180010d54  mov     [rdi+30h], rax
0x180010d58  nop     dword ptr [rax+rax+00000000h]
0x180010d60  xor     edx, edx; Val
0x180010d62  lea     rcx, [rsp+260h+var_1E8]; void *
0x180010d67  mov     r8d, 0D8h; Size
0x180010d6d  call    memset_0
0x180010d72  xorps   xmm0, xmm0
0x180010d75  mov     [rsp+260h+var_1F0], r15
0x180010d7a  xor     eax, eax
0x180010d7c  cmp     byte ptr [r15+67h], 0
0x180010d81  mov     [rbp+160h+var_58], rax
0x180010d88  mov     rax, [r15+160h]
0x180010d8f  mov     [rbp+160h+var_F0], rax
0x180010d93  lea     rax, [rsp+260h+var_1F0]
0x180010d98  mov     [r15+160h], rax
0x180010d9f  movups  [rbp+160h+var_D8], xmm0
0x180010da6  movups  [rbp+160h+var_C8], xmm0
0x180010dad  movups  [rbp+160h+var_B8], xmm0
0x180010db4  movups  [rbp+160h+var_A8], xmm0
0x180010dbb  movups  [rbp+160h+var_98], xmm0
0x180010dc2  movups  [rbp+160h+var_88], xmm0
0x180010dc9  movups  [rbp+160h+var_78], xmm0
0x180010dd0  movups  [rbp+160h+var_68], xmm0
0x180010dd7  jz      short loc_180010DEA
0x180010dd9  lea     rdx, aOutOfMemory; "out of memory"
0x180010de0  lea     rcx, [rsp+260h+var_1F0]
0x180010de5  call    sqlite3ErrorMsg
0x180010dea  test    rdi, rdi
0x180010ded  jz      loc_180011328
0x180010df3  test    r12, r12
0x180010df6  jz      short loc_180010E5A
0x180010df8  cmp     r12, [r15+1F0h]
0x180010dff  jnb     short loc_180010E3B
0x180010e01  cmp     r12, [r15+1E0h]
0x180010e08  jb      short loc_180010E1E
0x180010e0a  mov     rax, [r15+1D8h]
0x180010e11  mov     [r12], rax
0x180010e15  mov     [r15+1D8h], r12
0x180010e1c  jmp     short loc_180010E5A
0x180010e1e  cmp     r12, [r15+1E8h]
0x180010e25  jb      short loc_180010E3B
0x180010e27  mov     rax, [r15+1C8h]
0x180010e2e  mov     [r12], rax
0x180010e32  mov     [r15+1C8h], r12
0x180010e39  jmp     short loc_180010E5A
0x180010e3b  cmp     qword ptr [r15+308h], 0
0x180010e43  jz      short loc_180010E52
0x180010e45  mov     rdx, r12
0x180010e48  mov     rcx, r15
0x180010e4b  call    measureAllocationSize
0x180010e50  jmp     short loc_180010E5A
0x180010e52  mov     rcx, r12
0x180010e55  call    sqlite3_free
0x180010e5a  xor     r12d, r12d
0x180010e5d  mov     [rsp+260h+var_220], r12
0x180010e62  cmp     [r15+6Fh], r12b
0x180010e66  jnz     short loc_180010E70
0x180010e68  mov     rcx, r15
0x180010e6b  call    btreeEnterAll
0x180010e70  mov     r9, r13
0x180010e73  lea     rcx, [rsp+260h+var_1F0]
0x180010e78  mov     r8, r14
0x180010e7b  xor     edx, edx
0x180010e7d  call    sqlite3LocateTable
0x180010e82  mov     r13, rax
0x180010e85  test    rax, rax
0x180010e88  jz      loc_180011379
0x180010e8e  movzx   ecx, byte ptr [rax+3Fh]
0x180010e92  cmp     cl, 1
0x180010e95  jz      loc_180011365
0x180010e9b  test    byte ptr [rax+30h], 80h
0x180010e9f  jnz     loc_18001135C
0x180010ea5  cmp     cl, 2
0x180010ea8  jz      loc_180011353
0x180010eae  mov     [rdi+30h], rax
0x180010eb2  mov     ecx, 0FFFF8000h
0x180010eb7  mov     rdx, [rax+60h]
0x180010ebb  test    rdx, rdx
0x180010ebe  jz      short loc_180010EE0
0x180010ec0  mov     r8, [r15+20h]
0x180010ec4  xor     ecx, ecx
0x180010ec6  cmp     [r8+18h], rdx
0x180010eca  jz      short loc_180010EE0
0x180010ecc  nop     dword ptr [rax+00h]
0x180010ed0  inc     ecx
0x180010ed2  movsxd  rax, ecx
0x180010ed5  shl     rax, 5
0x180010ed9  cmp     [rax+r8+18h], rdx
0x180010ede  jnz     short loc_180010ED0
0x180010ee0  mov     rax, [r15+20h]
0x180010ee4  xor     r14d, r14d
0x180010ee7  movsxd  rcx, ecx
0x180010eea  shl     rcx, 5
0x180010eee  mov     rcx, [rcx+rax]
0x180010ef2  mov     [rdi+28h], rcx
0x180010ef6  movsx   r10d, word ptr [r13+36h]
0x180010efb  test    r10d, r10d
0x180010efe  jle     short loc_180010F65
0x180010f00  mov     r11, [r13+8]
0x180010f04  nop     dword ptr [rax+00h]
0x180010f08  nop     dword ptr [rax+rax+00000000h]
0x180010f10  lea     rcx, [r14+r14*2]
0x180010f14  mov     r9, rbx
0x180010f17  mov     r8, [r11+rcx*8]
0x180010f1b  nop     dword ptr [rax+rax+00h]
0x180010f20  movzx   edx, byte ptr [r8]
0x180010f24  movzx   eax, byte ptr [r9]
0x180010f28  cmp     edx, eax
0x180010f2a  jnz     short loc_180010F38
0x180010f2c  test    edx, edx
0x180010f2e  jz      short loc_180010F6E
0x180010f30  inc     r8
0x180010f33  inc     r9
0x180010f36  jmp     short loc_180010F20
0x180010f38  lea     rcx, qword_180114680
0x180010f3f  movzx   ecx, byte ptr [rax+rcx]
0x180010f43  mov     rax, rdx
0x180010f46  lea     rdx, qword_180114680
0x180010f4d  movzx   eax, byte ptr [rax+rdx]
0x180010f51  cmp     eax, ecx
0x180010f53  jnz     short loc_180010F5D
0x180010f55  inc     r8
0x180010f58  inc     r9
0x180010f5b  jmp     short loc_180010F20
0x180010f5d  inc     r14d
0x180010f60  cmp     r14d, r10d
0x180010f63  jl      short loc_180010F10
0x180010f65  cmp     r14d, r10d
0x180010f68  jz      loc_18001133F
0x180010f6e  cmp     [rbp+160h+arg_28], r12d
0x180010f75  jz      loc_180011023
0x180010f7b  mov     eax, [r15+30h]
0x180010f7f  xor     r10d, r10d
0x180010f82  bt      rax, 0Eh
0x180010f87  jnb     short loc_180010FCB
0x180010f89  mov     r8, [r13+48h]
0x180010f8d  test    r8, r8
0x180010f90  jz      short loc_180010FCB
0x180010f92  mov     r9d, [r8+28h]
0x180010f96  xor     edx, edx
0x180010f98  test    r9d, r9d
0x180010f9b  jle     short loc_180010FC2
0x180010f9d  nop     dword ptr [rax]
0x180010fa0  mov     ecx, edx
0x180010fa2  lea     rax, aForeignKey; "foreign key"
0x180010fa9  add     rcx, 4
0x180010fad  add     rcx, rcx
0x180010fb0  cmp     [r8+rcx*8], r14d
0x180010fb4  cmovnz  rax, r10
0x180010fb8  inc     edx
0x180010fba  mov     r10, rax
0x180010fbd  cmp     edx, r9d
0x180010fc0  jl      short loc_180010FA0
0x180010fc2  mov     r8, [r8+8]
0x180010fc6  test    r8, r8
0x180010fc9  jnz     short loc_180010F92
0x180010fcb  mov     r9, [r13+10h]
0x180010fcf  test    r9, r9
0x180010fd2  jz      short loc_18001101A
0x180010fd4  movzx   r8d, word ptr [r9+5Eh]
0x180010fd9  test    r8d, r8d
0x180010fdc  jz      short loc_180011011
0x180010fde  mov     r11, [r9+8]
0x180010fe2  xor     eax, eax
0x180010fe4  nop     dword ptr [rax+00h]
0x180010fe8  nop     dword ptr [rax+rax+00000000h]
0x180010ff0  movsxd  rcx, eax
0x180010ff3  movsx   edx, word ptr [r11+rcx*2]
0x180010ff8  cmp     edx, r14d
0x180010ffb  jz      short loc_180011003
0x180010ffd  cmp     dx, 0FFFEh
0x180011001  jnz     short loc_18001100A
0x180011003  lea     r10, aIndexed; "indexed"
0x18001100a  inc     eax
0x18001100c  cmp     eax, r8d
0x18001100f  jl      short loc_180010FF0
0x180011011  mov     r9, [r9+28h]
0x180011015  test    r9, r9
0x180011018  jnz     short loc_180010FD4
0x18001101a  test    r10, r10
0x18001101d  jnz     loc_18001130F
0x180011023  lea     rcx, [rsp+260h+var_1F0]
0x180011028  call    sqlite3VdbeCreate
0x18001102d  mov     rdi, rax
0x180011030  mov     rax, [rsp+260h+var_210]
0x180011035  mov     [rax+18h], rdi
0x180011039  test    rdi, rdi
0x18001103c  jz      loc_18001129D
0x180011042  mov     rcx, [r13+60h]
0x180011046  mov     esi, 0FFFF8000h
0x18001104b  test    rcx, rcx
0x18001104e  jz      short loc_180011070
0x180011050  mov     rdx, [r15+20h]
0x180011054  xor     esi, esi
0x180011056  cmp     [rdx+18h], rcx
0x18001105a  jz      short loc_180011070
0x18001105c  nop     dword ptr [rax+00h]
0x180011060  inc     esi
0x180011062  movsxd  rax, esi
0x180011065  shl     rax, 5
0x180011069  cmp     [rax+rdx+18h], rcx
0x18001106e  jnz     short loc_180011060
0x180011070  mov     r8d, [rcx+4]
0x180011074  mov     r9d, [rcx]
0x180011077  movsxd  rcx, dword ptr [rdi+90h]
0x18001107e  cmp     [rdi+94h], ecx
0x180011084  jg      short loc_1800110A7
0x180011086  mov     [rsp+260h+var_238], r8d
0x18001108b  mov     edx, 2
0x180011090  mov     [rsp+260h+var_240], r9d
0x180011095  mov     r8d, esi
0x180011098  mov     r9d, [rsp+260h+var_230]
0x18001109d  mov     rcx, rdi
0x1800110a0  call    addOp4IntSlow
0x1800110a5  jmp     short loc_1800110DA
0x1800110a7  lea     eax, [rcx+1]
0x1800110aa  mov     [rdi+90h], eax
0x1800110b0  lea     rcx, [rcx+rcx*2]
0x1800110b4  mov     rax, [rdi+88h]
0x1800110bb  mov     dword ptr [rax+rcx*8], 0FD02h
0x1800110c2  mov     [rax+rcx*8+4], esi
0x1800110c6  mov     [rax+rcx*8+0Ch], r9d
0x1800110cb  lea     rdx, [rax+rcx*8]
0x1800110cf  mov     eax, [rsp+260h+var_230]
0x1800110d3  mov     [rdx+10h], r8d
0x1800110d7  mov     [rdx+8], eax
0x1800110da  movsxd  rax, dword ptr [rdi+90h]
0x1800110e1  test    eax, eax
0x1800110e3  jle     short loc_1800110F7
0x1800110e5  lea     rcx, [rax+rax*2]
0x1800110e9  mov     rax, [rdi+88h]
0x1800110f0  mov     word ptr [rax+rcx*8-16h], 1
0x1800110f7  mov     eax, [rdi+90h]
0x1800110fd  add     eax, 6
0x180011100  cmp     eax, [rdi+94h]
0x180011106  jle     short loc_180011120
0x180011108  mov     edx, 6
0x18001110d  mov     rcx, rdi
0x180011110  call    growOpArray
0x180011115  test    eax, eax
0x180011117  jz      short loc_180011120
0x180011119  xor     ebx, ebx
0x18001111b  jmp     loc_1800111C6
0x180011120  movsxd  rax, dword ptr [rdi+90h]
0x180011127  mov     edx, 1
0x18001112c  lea     rcx, [rax+rax*2]
0x180011130  mov     rax, [rdi+88h]
0x180011137  mov     qword ptr [rax+rcx*8], 0A9h
0x18001113f  lea     rbx, [rax+rcx*8]
0x180011143  xor     ecx, ecx
0x180011145  mov     [rbx+8], rcx
  ... truncated ...
```
