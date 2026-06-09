# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x1800054d0`
- end: `0x180005afa`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002f8c`

## callees

- `0x180001e5a`
- `0x1800054d0`
- `0x180006058`
- `0x180006994`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800056d1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800056df`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // r15
  __int64 v5; // rbx
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r14
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // r11
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r10
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  __int64 v35; // rax
  void **v36; // rdi
  volatile signed __int32 *v37; // rcx
  volatile signed __int32 *v38; // r14
  void *v39; // rbx
  HANDLE ProcessHeap; // rax
  char *v41; // rbx
  rsize_t v42; // rdx
  char **v43; // r14
  char *v44; // rdi
  _WORD *v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // r12
  char **v48; // r14
  _BYTE *v49; // r8
  __int64 v50; // rax
  __int64 v51; // r12
  char **v52; // r14
  _BYTE *v53; // r8
  __int64 v54; // rax
  __int64 v55; // r12
  char **v56; // r14
  _BYTE *v57; // r8
  __int64 v58; // rax
  __int64 v59; // r12
  char **v60; // r14
  _BYTE *v61; // r8
  __int64 v62; // rax
  __int64 v63; // r12
  char **v64; // r14
  _BYTE *v65; // r8
  __int64 v66; // rax
  __int64 v67; // r12
  char **v68; // r14
  _BYTE *v69; // r8
  __int64 v70; // rax
  __int64 v71; // r12
  char **v72; // r14
  _WORD *v73; // r8
  __int64 v74; // rax
  unsigned __int64 v75; // r12
  char **v76; // r14
  _BYTE *v77; // r8
  __int64 v78; // rax
  __int64 v79; // r12
  char **v80; // rsi
  _WORD *v81; // r8
  rsize_t v82; // r15

  v2 = -1;
  *(_OWORD *)this = *(_OWORD *)a2;
  v5 = 2;
  *((_OWORD *)this + 1) = *((_OWORD *)a2 + 1);
  *((_OWORD *)this + 2) = *((_OWORD *)a2 + 2);
  *((_OWORD *)this + 3) = *((_OWORD *)a2 + 3);
  *((_OWORD *)this + 4) = *((_OWORD *)a2 + 4);
  *((_OWORD *)this + 5) = *((_OWORD *)a2 + 5);
  *((_OWORD *)this + 6) = *((_OWORD *)a2 + 6);
  *((_OWORD *)this + 7) = *((_OWORD *)a2 + 7);
  *((_OWORD *)this + 8) = *((_OWORD *)a2 + 8);
  *((_QWORD *)this + 18) = *((_QWORD *)a2 + 18);
  v6 = *((_QWORD *)a2 + 3);
  if ( v6 )
  {
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    v7 = 2 * v8 + 2;
  }
  else
  {
    v7 = 2;
  }
  v9 = *((_QWORD *)a2 + 5);
  if ( v9 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v9 + v11) );
    v10 = v11 + 1;
  }
  else
  {
    v10 = 1;
  }
  v12 = *((_QWORD *)a2 + 6);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_BYTE *)(v12 + v14) );
    v13 = v14 + 1;
  }
  else
  {
    v13 = 1;
  }
  v15 = *((_QWORD *)a2 + 7);
  if ( v15 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *(_BYTE *)(v15 + v17) );
    v16 = v17 + 1;
  }
  else
  {
    v16 = 1;
  }
  v18 = *((_QWORD *)a2 + 9);
  if ( v18 )
  {
    v20 = -1;
    do
      ++v20;
    while ( *(_BYTE *)(v18 + v20) );
    v19 = v20 + 1;
  }
  else
  {
    v19 = 1;
  }
  v21 = *((_QWORD *)a2 + 16);
  if ( v21 )
  {
    v23 = -1;
    do
      ++v23;
    while ( *(_BYTE *)(v21 + v23) );
    v22 = v23 + 1;
  }
  else
  {
    v22 = 1;
  }
  v24 = *((_QWORD *)a2 + 14);
  if ( v24 )
  {
    v26 = -1;
    do
      ++v26;
    while ( *(_BYTE *)(v24 + v26) );
    v25 = v26 + 1;
  }
  else
  {
    v25 = 1;
  }
  v27 = *((_QWORD *)a2 + 15);
  if ( v27 )
  {
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v27 + 2 * v29) );
    v28 = 2 * v29 + 2;
  }
  else
  {
    v28 = 2;
  }
  v30 = *((_QWORD *)a2 + 11);
  if ( v30 )
  {
    v32 = -1;
    do
      ++v32;
    while ( *(_BYTE *)(v30 + v32) );
    v31 = v32 + 1;
  }
  else
  {
    v31 = 1;
  }
  v33 = *((_QWORD *)a2 + 12);
  if ( v33 )
  {
    v34 = -1;
    do
      ++v34;
    while ( *(_WORD *)(v33 + 2 * v34) );
    v5 = 2 * v34 + 2;
  }
  v35 = v16 + v19 + v22 + v25 + v28 + v5 + v31;
  v36 = (void **)((char *)this + 152);
  v37 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  v38 = (volatile signed __int32 *)(v7 + v10 + v35 + v13);
  if ( !v37 )
    goto LABEL_56;
  if ( *v37 != 1 || *((_QWORD *)this + 20) < (unsigned __int64)v38 )
  {
    if ( _InterlockedExchangeAdd(v37, 0xFFFFFFFF) == 1 )
    {
      v39 = *v36;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v39);
    }
    *v36 = 0;
    *((_QWORD *)this + 20) = 0;
LABEL_56:
    wil::details::shared_buffer::create((volatile signed __int32 **)this + 19, v38);
  }
  v41 = (char *)(((unsigned __int64)*v36 + 4) & -(__int64)(*v36 != 0));
  if ( !v41 )
    return;
  v42 = *((_QWORD *)this + 20);
  v43 = (char **)((char *)this + 24);
  v44 = &v41[v42];
  if ( v41 != &v41[v42] && (v45 = (_WORD *)*((_QWORD *)a2 + 3)) != 0 && *v45 )
  {
    v46 = -1;
    do
      ++v46;
    while ( v45[v46] );
    v47 = 2 * v46 + 2;
    if ( v42 < v47 )
    {
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v43 = 0;
      v48 = (char **)((char *)this + 40);
      goto LABEL_73;
    }
    memcpy_s(v41, v42, v45, 2 * v46 + 2);
    if ( this != (wil::StoredFailureInfo *)-24LL )
      *v43 = v41;
    v41 += v47;
  }
  else if ( this != (wil::StoredFailureInfo *)-24LL )
  {
    *v43 = 0;
  }
  v48 = (char **)((char *)this + 40);
  if ( v41 == v44 )
    goto LABEL_84;
LABEL_73:
  v49 = (_BYTE *)*((_QWORD *)a2 + 5);
  if ( !v49 || !*v49 )
  {
LABEL_84:
    if ( v48 )
      *v48 = 0;
    goto LABEL_86;
  }
  v50 = -1;
  do
    ++v50;
  while ( v49[v50] );
  v51 = v50 + 1;
  if ( v44 - v41 < (unsigned __int64)(v50 + 1) )
  {
    if ( v48 )
      *v48 = 0;
    v52 = (char **)((char *)this + 48);
    goto LABEL_87;
  }
  memcpy_s(v41, v44 - v41, v49, v50 + 1);
  if ( v48 )
    *v48 = v41;
  v41 += v51;
LABEL_86:
  v52 = (char **)((char *)this + 48);
  if ( v41 == v44 )
    goto LABEL_98;
LABEL_87:
  v53 = (_BYTE *)*((_QWORD *)a2 + 6);
  if ( !v53 || !*v53 )
  {
LABEL_98:
    if ( v52 )
      *v52 = 0;
    goto LABEL_100;
  }
  v54 = -1;
  do
    ++v54;
  while ( v53[v54] );
  v55 = v54 + 1;
  if ( v44 - v41 < (unsigned __int64)(v54 + 1) )
  {
    if ( v52 )
      *v52 = 0;
    v56 = (char **)((char *)this + 56);
    goto LABEL_101;
  }
  memcpy_s(v41, v44 - v41, v53, v54 + 1);
  if ( v52 )
    *v52 = v41;
  v41 += v55;
LABEL_100:
  v56 = (char **)((char *)this + 56);
  if ( v41 == v44 )
    goto LABEL_112;
LABEL_101:
  v57 = (_BYTE *)*((_QWORD *)a2 + 7);
  if ( !v57 || !*v57 )
  {
LABEL_112:
    if ( v56 )
      *v56 = 0;
    goto LABEL_114;
  }
  v58 = -1;
  do
    ++v58;
  while ( v57[v58] );
  v59 = v58 + 1;
  if ( v44 - v41 < (unsigned __int64)(v58 + 1) )
  {
    if ( v56 )
      *v56 = 0;
    v60 = (char **)((char *)this + 72);
    goto LABEL_115;
  }
  memcpy_s(v41, v44 - v41, v57, v58 + 1);
  if ( v56 )
    *v56 = v41;
  v41 += v59;
LABEL_114:
  v60 = (char **)((char *)this + 72);
  if ( v41 == v44 )
    goto LABEL_126;
LABEL_115:
  v61 = (_BYTE *)*((_QWORD *)a2 + 9);
  if ( !v61 || !*v61 )
  {
LABEL_126:
    if ( v60 )
      *v60 = 0;
    goto LABEL_128;
  }
  v62 = -1;
  do
    ++v62;
  while ( v61[v62] );
  v63 = v62 + 1;
  if ( v44 - v41 < (unsigned __int64)(v62 + 1) )
  {
    if ( v60 )
      *v60 = 0;
    v64 = (char **)((char *)this + 128);
    goto LABEL_129;
  }
  memcpy_s(v41, v44 - v41, v61, v62 + 1);
  if ( v60 )
    *v60 = v41;
  v41 += v63;
LABEL_128:
  v64 = (char **)((char *)this + 128);
  if ( v41 == v44 )
    goto LABEL_140;
LABEL_129:
  v65 = (_BYTE *)*((_QWORD *)a2 + 16);
  if ( !v65 || !*v65 )
  {
LABEL_140:
    if ( v64 )
      *v64 = 0;
    goto LABEL_142;
  }
  v66 = -1;
  do
    ++v66;
  while ( v65[v66] );
  v67 = v66 + 1;
  if ( v44 - v41 < (unsigned __int64)(v66 + 1) )
  {
    if ( v64 )
      *v64 = 0;
    v68 = (char **)((char *)this + 112);
    goto LABEL_143;
  }
  memcpy_s(v41, v44 - v41, v65, v66 + 1);
  if ( v64 )
    *v64 = v41;
  v41 += v67;
LABEL_142:
  v68 = (char **)((char *)this + 112);
  if ( v41 == v44 )
    goto LABEL_154;
LABEL_143:
  v69 = (_BYTE *)*((_QWORD *)a2 + 14);
  if ( !v69 || !*v69 )
  {
LABEL_154:
    if ( v68 )
      *v68 = 0;
    goto LABEL_156;
  }
  v70 = -1;
  do
    ++v70;
  while ( v69[v70] );
  v71 = v70 + 1;
  if ( v44 - v41 < (unsigned __int64)(v70 + 1) )
  {
    if ( v68 )
      *v68 = 0;
    v72 = (char **)((char *)this + 120);
    goto LABEL_157;
  }
  memcpy_s(v41, v44 - v41, v69, v70 + 1);
  if ( v68 )
    *v68 = v41;
  v41 += v71;
LABEL_156:
  v72 = (char **)((char *)this + 120);
  if ( v41 == v44 )
    goto LABEL_168;
LABEL_157:
  v73 = (_WORD *)*((_QWORD *)a2 + 15);
  if ( !v73 || !*v73 )
  {
LABEL_168:
    if ( v72 )
      *v72 = 0;
    goto LABEL_170;
  }
  v74 = -1;
  do
    ++v74;
  while ( v73[v74] );
  v75 = 2 * v74 + 2;
  if ( v44 - v41 < v75 )
  {
    if ( v72 )
      *v72 = 0;
    v76 = (char **)((char *)this + 88);
    goto LABEL_171;
  }
  memcpy_s(v41, v44 - v41, v73, 2 * v74 + 2);
  if ( v72 )
    *v72 = v41;
  v41 += v75;
LABEL_170:
  v76 = (char **)((char *)this + 88);
  if ( v41 == v44 )
    goto LABEL_182;
LABEL_171:
  v77 = (_BYTE *)*((_QWORD *)a2 + 11);
  if ( !v77 || !*v77 )
  {
LABEL_182:
    if ( v76 )
      *v76 = 0;
    goto LABEL_184;
  }
  v78 = -1;
  do
    ++v78;
  while ( v77[v78] );
  v79 = v78 + 1;
  if ( v44 - v41 < (unsigned __int64)(v78 + 1) )
  {
    if ( v76 )
      *v76 = 0;
    v80 = (char **)((char *)this + 96);
    goto LABEL_185;
  }
  memcpy_s(v41, v44 - v41, v77, v78 + 1);
  if ( v76 )
    *v76 = v41;
  v41 += v79;
LABEL_184:
  v80 = (char **)((char *)this + 96);
  if ( v41 == v44 )
    goto LABEL_192;
LABEL_185:
  v81 = (_WORD *)*((_QWORD *)a2 + 12);
  if ( !v81 || !*v81 )
    goto LABEL_192;
  do
    ++v2;
  while ( v81[v2] );
  v82 = 2 * v2 + 2;
  if ( v44 - v41 < v82 )
  {
LABEL_192:
    if ( v80 )
      *v80 = 0;
    goto LABEL_194;
  }
  memcpy_s(v41, v44 - v41, v81, v82);
  if ( v80 )
    *v80 = v41;
  v41 += v82;
LABEL_194:
  memset_0(v41, 0, v44 - v41);
}

```

## disassembly

```asm
0x1800054d0  push    rbx
0x1800054d2  push    rbp
0x1800054d3  push    rsi
0x1800054d4  push    rdi
0x1800054d5  push    r12
0x1800054d7  push    r13
0x1800054d9  push    r14
0x1800054db  push    r15
0x1800054dd  sub     rsp, 28h
0x1800054e1  movups  xmm0, xmmword ptr [rdx]
0x1800054e4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800054e8  mov     rsi, rcx
0x1800054eb  mov     rbp, rdx
0x1800054ee  movups  xmmword ptr [rcx], xmm0
0x1800054f1  movups  xmm1, xmmword ptr [rdx+10h]
0x1800054f5  lea     ebx, [r15+3]
0x1800054f9  movups  xmmword ptr [rcx+10h], xmm1
0x1800054fd  movups  xmm0, xmmword ptr [rdx+20h]
0x180005501  movups  xmmword ptr [rcx+20h], xmm0
0x180005505  movups  xmm1, xmmword ptr [rdx+30h]
0x180005509  movups  xmmword ptr [rcx+30h], xmm1
0x18000550d  movups  xmm0, xmmword ptr [rdx+40h]
0x180005511  movups  xmmword ptr [rcx+40h], xmm0
0x180005515  movups  xmm1, xmmword ptr [rdx+50h]
0x180005519  movups  xmmword ptr [rcx+50h], xmm1
0x18000551d  movups  xmm0, xmmword ptr [rdx+60h]
0x180005521  movups  xmmword ptr [rcx+60h], xmm0
0x180005525  movups  xmm1, xmmword ptr [rdx+70h]
0x180005529  movups  xmmword ptr [rcx+70h], xmm1
0x18000552d  movups  xmm0, xmmword ptr [rdx+80h]
0x180005534  movups  xmmword ptr [rcx+80h], xmm0
0x18000553b  mov     rax, [rdx+90h]
0x180005542  mov     [rcx+90h], rax
0x180005549  mov     rcx, [rdx+18h]
0x18000554d  xor     edx, edx
0x18000554f  test    rcx, rcx
0x180005552  jnz     short loc_180005559
0x180005554  mov     r13d, ebx
0x180005557  jmp     short loc_18000556D
0x180005559  mov     rax, r15
0x18000555c  inc     rax
0x18000555f  cmp     [rcx+rax*2], dx
0x180005563  jnz     short loc_18000555C
0x180005565  lea     r13, ds:2[rax*2]
0x18000556d  mov     rcx, [rbp+28h]
0x180005571  test    rcx, rcx
0x180005574  jnz     short loc_18000557C
0x180005576  lea     r12d, [rcx+1]
0x18000557a  jmp     short loc_18000558B
0x18000557c  mov     rax, r15
0x18000557f  inc     rax
0x180005582  cmp     [rcx+rax], dl
0x180005585  jnz     short loc_18000557F
0x180005587  lea     r12, [rax+1]
0x18000558b  mov     rcx, [rbp+30h]
0x18000558f  test    rcx, rcx
0x180005592  jnz     short loc_18000559A
0x180005594  lea     r14d, [rcx+1]
0x180005598  jmp     short loc_1800055A9
0x18000559a  mov     rax, r15
0x18000559d  inc     rax
0x1800055a0  cmp     [rcx+rax], dl
0x1800055a3  jnz     short loc_18000559D
0x1800055a5  lea     r14, [rax+1]
0x1800055a9  mov     rcx, [rbp+38h]
0x1800055ad  test    rcx, rcx
0x1800055b0  jnz     short loc_1800055B7
0x1800055b2  lea     edi, [rcx+1]
0x1800055b5  jmp     short loc_1800055C6
0x1800055b7  mov     rax, r15
0x1800055ba  inc     rax
0x1800055bd  cmp     [rcx+rax], dl
0x1800055c0  jnz     short loc_1800055BA
0x1800055c2  lea     rdi, [rax+1]
0x1800055c6  mov     rcx, [rbp+48h]
0x1800055ca  test    rcx, rcx
0x1800055cd  jnz     short loc_1800055D5
0x1800055cf  lea     r11d, [rcx+1]
0x1800055d3  jmp     short loc_1800055E4
0x1800055d5  mov     rax, r15
0x1800055d8  inc     rax
0x1800055db  cmp     [rcx+rax], dl
0x1800055de  jnz     short loc_1800055D8
0x1800055e0  lea     r11, [rax+1]
0x1800055e4  mov     rcx, [rbp+80h]
0x1800055eb  test    rcx, rcx
0x1800055ee  jnz     short loc_1800055F6
0x1800055f0  lea     r10d, [rcx+1]
0x1800055f4  jmp     short loc_180005605
0x1800055f6  mov     rax, r15
0x1800055f9  inc     rax
0x1800055fc  cmp     [rcx+rax], dl
0x1800055ff  jnz     short loc_1800055F9
0x180005601  lea     r10, [rax+1]
0x180005605  mov     rcx, [rbp+70h]
0x180005609  test    rcx, rcx
0x18000560c  jnz     short loc_180005614
0x18000560e  lea     r9d, [rcx+1]
0x180005612  jmp     short loc_180005623
0x180005614  mov     rax, r15
0x180005617  inc     rax
0x18000561a  cmp     [rcx+rax], dl
0x18000561d  jnz     short loc_180005617
0x18000561f  lea     r9, [rax+1]
0x180005623  mov     rcx, [rbp+78h]
0x180005627  test    rcx, rcx
0x18000562a  jnz     short loc_180005631
0x18000562c  mov     r8, rbx
0x18000562f  jmp     short loc_180005645
0x180005631  mov     rax, r15
0x180005634  inc     rax
0x180005637  cmp     [rcx+rax*2], dx
0x18000563b  jnz     short loc_180005634
0x18000563d  lea     r8, ds:2[rax*2]
0x180005645  mov     rcx, [rbp+58h]
0x180005649  test    rcx, rcx
0x18000564c  jnz     short loc_180005653
0x18000564e  lea     edx, [rcx+1]
0x180005651  jmp     short loc_180005662
0x180005653  mov     rax, r15
0x180005656  inc     rax
0x180005659  cmp     [rcx+rax], dl
0x18000565c  jnz     short loc_180005656
0x18000565e  lea     rdx, [rax+1]
0x180005662  mov     rcx, [rbp+60h]
0x180005666  test    rcx, rcx
0x180005669  jz      short loc_180005681
0x18000566b  mov     rax, r15
0x18000566e  xor     ebx, ebx
0x180005670  inc     rax
0x180005673  cmp     [rcx+rax*2], bx
0x180005677  jnz     short loc_180005670
0x180005679  lea     rbx, ds:2[rax*2]
0x180005681  lea     rax, [rbx+rdx]
0x180005685  add     rax, r8
0x180005688  add     rax, r9
0x18000568b  add     rax, r10
0x18000568e  add     rax, r11
0x180005691  add     rax, rdi
0x180005694  lea     rdi, [rsi+98h]
0x18000569b  mov     rcx, [rdi]
0x18000569e  add     r14, rax
0x1800056a1  add     r14, r12
0x1800056a4  add     r14, r13
0x1800056a7  xor     r13d, r13d
0x1800056aa  test    rcx, rcx
0x1800056ad  jz      short loc_1800056EC
0x1800056af  cmp     dword ptr [rcx], 1
0x1800056b2  jnz     short loc_1800056C2
0x1800056b4  cmp     [rsi+0A0h], r14
0x1800056bb  jnb     short loc_1800056F7
0x1800056bd  test    rcx, rcx
0x1800056c0  jz      short loc_1800056EC
0x1800056c2  mov     eax, r15d
0x1800056c5  lock xadd [rcx], eax
0x1800056c9  add     eax, r15d
0x1800056cc  jnz     short loc_1800056E5
0x1800056ce  mov     rbx, [rdi]
0x1800056d1  call    cs:__imp_GetProcessHeap
0x1800056d7  mov     r8, rbx; lpMem
0x1800056da  xor     edx, edx; dwFlags
0x1800056dc  mov     rcx, rax; hHeap
0x1800056df  call    cs:__imp_HeapFree
0x1800056e5  mov     [rdi], r13
0x1800056e8  mov     [rdi+8], r13
0x1800056ec  mov     rdx, r14; unsigned __int64
0x1800056ef  mov     rcx, rdi; this
0x1800056f2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x1800056f7  mov     rax, [rdi]
0x1800056fa  lea     rcx, [rax+4]
0x1800056fe  neg     rax
0x180005701  sbb     rbx, rbx
0x180005704  and     rbx, rcx
0x180005707  jz      loc_180005AE9
0x18000570d  mov     rdx, [rdi+8]; DestinationSize
0x180005711  lea     r14, [rsi+18h]
0x180005715  lea     rdi, [rbx+rdx]
0x180005719  cmp     rbx, rdi
0x18000571c  jz      short loc_18000576D
0x18000571e  mov     r8, [rbp+18h]; Source
0x180005722  test    r8, r8
0x180005725  jz      short loc_18000576D
0x180005727  cmp     [r8], r13w
0x18000572b  jz      short loc_18000576D
0x18000572d  mov     rax, r15
0x180005730  inc     rax
0x180005733  cmp     [r8+rax*2], r13w
0x180005738  jnz     short loc_180005730
0x18000573a  lea     r12, ds:2[rax*2]
0x180005742  cmp     rdx, r12
0x180005745  jnb     short loc_180005755
0x180005747  test    r14, r14
0x18000574a  jz      short loc_18000574F
0x18000574c  mov     [r14], r13
0x18000574f  lea     r14, [rsi+28h]
0x180005753  jmp     short loc_18000577E
0x180005755  mov     r9, r12; SourceSize
0x180005758  mov     rcx, rbx; Destination
0x18000575b  call    memcpy_s
0x180005760  test    r14, r14
0x180005763  jz      short loc_180005768
0x180005765  mov     [r14], rbx
0x180005768  add     rbx, r12
0x18000576b  jmp     short loc_180005775
0x18000576d  test    r14, r14
0x180005770  jz      short loc_180005775
0x180005772  mov     [r14], r13
0x180005775  lea     r14, [rsi+28h]
0x180005779  cmp     rbx, rdi
0x18000577c  jz      short loc_1800057CD
0x18000577e  mov     r8, [rbp+28h]; Source
0x180005782  test    r8, r8
0x180005785  jz      short loc_1800057CD
0x180005787  cmp     [r8], r13b
0x18000578a  jz      short loc_1800057CD
0x18000578c  mov     rax, r15
0x18000578f  inc     rax
0x180005792  cmp     [r8+rax], r13b
0x180005796  jnz     short loc_18000578F
0x180005798  mov     rdx, rdi
0x18000579b  lea     r12, [rax+1]
0x18000579f  sub     rdx, rbx; DestinationSize
0x1800057a2  cmp     rdx, r12
0x1800057a5  jnb     short loc_1800057B5
0x1800057a7  test    r14, r14
0x1800057aa  jz      short loc_1800057AF
0x1800057ac  mov     [r14], r13
0x1800057af  lea     r14, [rsi+30h]
0x1800057b3  jmp     short loc_1800057DE
0x1800057b5  mov     r9, r12; SourceSize
0x1800057b8  mov     rcx, rbx; Destination
0x1800057bb  call    memcpy_s
0x1800057c0  test    r14, r14
0x1800057c3  jz      short loc_1800057C8
0x1800057c5  mov     [r14], rbx
0x1800057c8  add     rbx, r12
0x1800057cb  jmp     short loc_1800057D5
0x1800057cd  test    r14, r14
0x1800057d0  jz      short loc_1800057D5
0x1800057d2  mov     [r14], r13
0x1800057d5  lea     r14, [rsi+30h]
0x1800057d9  cmp     rbx, rdi
0x1800057dc  jz      short loc_18000582D
0x1800057de  mov     r8, [rbp+30h]; Source
0x1800057e2  test    r8, r8
0x1800057e5  jz      short loc_18000582D
0x1800057e7  cmp     [r8], r13b
0x1800057ea  jz      short loc_18000582D
0x1800057ec  mov     rax, r15
0x1800057ef  inc     rax
0x1800057f2  cmp     [r8+rax], r13b
0x1800057f6  jnz     short loc_1800057EF
0x1800057f8  mov     rdx, rdi
0x1800057fb  lea     r12, [rax+1]
0x1800057ff  sub     rdx, rbx; DestinationSize
0x180005802  cmp     rdx, r12
0x180005805  jnb     short loc_180005815
0x180005807  test    r14, r14
0x18000580a  jz      short loc_18000580F
0x18000580c  mov     [r14], r13
0x18000580f  lea     r14, [rsi+38h]
0x180005813  jmp     short loc_18000583E
0x180005815  mov     r9, r12; SourceSize
0x180005818  mov     rcx, rbx; Destination
0x18000581b  call    memcpy_s
0x180005820  test    r14, r14
0x180005823  jz      short loc_180005828
0x180005825  mov     [r14], rbx
0x180005828  add     rbx, r12
0x18000582b  jmp     short loc_180005835
0x18000582d  test    r14, r14
0x180005830  jz      short loc_180005835
0x180005832  mov     [r14], r13
0x180005835  lea     r14, [rsi+38h]
0x180005839  cmp     rbx, rdi
0x18000583c  jz      short loc_18000588D
0x18000583e  mov     r8, [rbp+38h]; Source
0x180005842  test    r8, r8
0x180005845  jz      short loc_18000588D
0x180005847  cmp     [r8], r13b
0x18000584a  jz      short loc_18000588D
0x18000584c  mov     rax, r15
0x18000584f  inc     rax
0x180005852  cmp     [r8+rax], r13b
0x180005856  jnz     short loc_18000584F
0x180005858  mov     rdx, rdi
0x18000585b  lea     r12, [rax+1]
0x18000585f  sub     rdx, rbx; DestinationSize
0x180005862  cmp     rdx, r12
0x180005865  jnb     short loc_180005875
0x180005867  test    r14, r14
0x18000586a  jz      short loc_18000586F
0x18000586c  mov     [r14], r13
0x18000586f  lea     r14, [rsi+48h]
0x180005873  jmp     short loc_18000589E
0x180005875  mov     r9, r12; SourceSize
0x180005878  mov     rcx, rbx; Destination
0x18000587b  call    memcpy_s
0x180005880  test    r14, r14
0x180005883  jz      short loc_180005888
  ... truncated ...
```
