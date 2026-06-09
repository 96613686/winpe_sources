# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180004980`
- end: `0x180004faa`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800028a0`

## callees

- `0x180001f4a`
- `0x180004980`
- `0x180005518`
- `0x180005718`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b8f`

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
0x180004980  push    rbx
0x180004982  push    rbp
0x180004983  push    rsi
0x180004984  push    rdi
0x180004985  push    r12
0x180004987  push    r13
0x180004989  push    r14
0x18000498b  push    r15
0x18000498d  sub     rsp, 28h
0x180004991  movups  xmm0, xmmword ptr [rdx]
0x180004994  or      r15, 0FFFFFFFFFFFFFFFFh
0x180004998  mov     rsi, rcx
0x18000499b  mov     rbp, rdx
0x18000499e  movups  xmmword ptr [rcx], xmm0
0x1800049a1  movups  xmm1, xmmword ptr [rdx+10h]
0x1800049a5  lea     ebx, [r15+3]
0x1800049a9  movups  xmmword ptr [rcx+10h], xmm1
0x1800049ad  movups  xmm0, xmmword ptr [rdx+20h]
0x1800049b1  movups  xmmword ptr [rcx+20h], xmm0
0x1800049b5  movups  xmm1, xmmword ptr [rdx+30h]
0x1800049b9  movups  xmmword ptr [rcx+30h], xmm1
0x1800049bd  movups  xmm0, xmmword ptr [rdx+40h]
0x1800049c1  movups  xmmword ptr [rcx+40h], xmm0
0x1800049c5  movups  xmm1, xmmword ptr [rdx+50h]
0x1800049c9  movups  xmmword ptr [rcx+50h], xmm1
0x1800049cd  movups  xmm0, xmmword ptr [rdx+60h]
0x1800049d1  movups  xmmword ptr [rcx+60h], xmm0
0x1800049d5  movups  xmm1, xmmword ptr [rdx+70h]
0x1800049d9  movups  xmmword ptr [rcx+70h], xmm1
0x1800049dd  movups  xmm0, xmmword ptr [rdx+80h]
0x1800049e4  movups  xmmword ptr [rcx+80h], xmm0
0x1800049eb  mov     rax, [rdx+90h]
0x1800049f2  mov     [rcx+90h], rax
0x1800049f9  mov     rcx, [rdx+18h]
0x1800049fd  xor     edx, edx
0x1800049ff  test    rcx, rcx
0x180004a02  jnz     short loc_180004A09
0x180004a04  mov     r13d, ebx
0x180004a07  jmp     short loc_180004A1D
0x180004a09  mov     rax, r15
0x180004a0c  inc     rax
0x180004a0f  cmp     [rcx+rax*2], dx
0x180004a13  jnz     short loc_180004A0C
0x180004a15  lea     r13, ds:2[rax*2]
0x180004a1d  mov     rcx, [rbp+28h]
0x180004a21  test    rcx, rcx
0x180004a24  jnz     short loc_180004A2C
0x180004a26  lea     r12d, [rcx+1]
0x180004a2a  jmp     short loc_180004A3B
0x180004a2c  mov     rax, r15
0x180004a2f  inc     rax
0x180004a32  cmp     [rcx+rax], dl
0x180004a35  jnz     short loc_180004A2F
0x180004a37  lea     r12, [rax+1]
0x180004a3b  mov     rcx, [rbp+30h]
0x180004a3f  test    rcx, rcx
0x180004a42  jnz     short loc_180004A4A
0x180004a44  lea     r14d, [rcx+1]
0x180004a48  jmp     short loc_180004A59
0x180004a4a  mov     rax, r15
0x180004a4d  inc     rax
0x180004a50  cmp     [rcx+rax], dl
0x180004a53  jnz     short loc_180004A4D
0x180004a55  lea     r14, [rax+1]
0x180004a59  mov     rcx, [rbp+38h]
0x180004a5d  test    rcx, rcx
0x180004a60  jnz     short loc_180004A67
0x180004a62  lea     edi, [rcx+1]
0x180004a65  jmp     short loc_180004A76
0x180004a67  mov     rax, r15
0x180004a6a  inc     rax
0x180004a6d  cmp     [rcx+rax], dl
0x180004a70  jnz     short loc_180004A6A
0x180004a72  lea     rdi, [rax+1]
0x180004a76  mov     rcx, [rbp+48h]
0x180004a7a  test    rcx, rcx
0x180004a7d  jnz     short loc_180004A85
0x180004a7f  lea     r11d, [rcx+1]
0x180004a83  jmp     short loc_180004A94
0x180004a85  mov     rax, r15
0x180004a88  inc     rax
0x180004a8b  cmp     [rcx+rax], dl
0x180004a8e  jnz     short loc_180004A88
0x180004a90  lea     r11, [rax+1]
0x180004a94  mov     rcx, [rbp+80h]
0x180004a9b  test    rcx, rcx
0x180004a9e  jnz     short loc_180004AA6
0x180004aa0  lea     r10d, [rcx+1]
0x180004aa4  jmp     short loc_180004AB5
0x180004aa6  mov     rax, r15
0x180004aa9  inc     rax
0x180004aac  cmp     [rcx+rax], dl
0x180004aaf  jnz     short loc_180004AA9
0x180004ab1  lea     r10, [rax+1]
0x180004ab5  mov     rcx, [rbp+70h]
0x180004ab9  test    rcx, rcx
0x180004abc  jnz     short loc_180004AC4
0x180004abe  lea     r9d, [rcx+1]
0x180004ac2  jmp     short loc_180004AD3
0x180004ac4  mov     rax, r15
0x180004ac7  inc     rax
0x180004aca  cmp     [rcx+rax], dl
0x180004acd  jnz     short loc_180004AC7
0x180004acf  lea     r9, [rax+1]
0x180004ad3  mov     rcx, [rbp+78h]
0x180004ad7  test    rcx, rcx
0x180004ada  jnz     short loc_180004AE1
0x180004adc  mov     r8, rbx
0x180004adf  jmp     short loc_180004AF5
0x180004ae1  mov     rax, r15
0x180004ae4  inc     rax
0x180004ae7  cmp     [rcx+rax*2], dx
0x180004aeb  jnz     short loc_180004AE4
0x180004aed  lea     r8, ds:2[rax*2]
0x180004af5  mov     rcx, [rbp+58h]
0x180004af9  test    rcx, rcx
0x180004afc  jnz     short loc_180004B03
0x180004afe  lea     edx, [rcx+1]
0x180004b01  jmp     short loc_180004B12
0x180004b03  mov     rax, r15
0x180004b06  inc     rax
0x180004b09  cmp     [rcx+rax], dl
0x180004b0c  jnz     short loc_180004B06
0x180004b0e  lea     rdx, [rax+1]
0x180004b12  mov     rcx, [rbp+60h]
0x180004b16  test    rcx, rcx
0x180004b19  jz      short loc_180004B31
0x180004b1b  mov     rax, r15
0x180004b1e  xor     ebx, ebx
0x180004b20  inc     rax
0x180004b23  cmp     [rcx+rax*2], bx
0x180004b27  jnz     short loc_180004B20
0x180004b29  lea     rbx, ds:2[rax*2]
0x180004b31  lea     rax, [rbx+rdx]
0x180004b35  add     rax, r8
0x180004b38  add     rax, r9
0x180004b3b  add     rax, r10
0x180004b3e  add     rax, r11
0x180004b41  add     rax, rdi
0x180004b44  lea     rdi, [rsi+98h]
0x180004b4b  mov     rcx, [rdi]
0x180004b4e  add     r14, rax
0x180004b51  add     r14, r12
0x180004b54  add     r14, r13
0x180004b57  xor     r13d, r13d
0x180004b5a  test    rcx, rcx
0x180004b5d  jz      short loc_180004B9C
0x180004b5f  cmp     dword ptr [rcx], 1
0x180004b62  jnz     short loc_180004B72
0x180004b64  cmp     [rsi+0A0h], r14
0x180004b6b  jnb     short loc_180004BA7
0x180004b6d  test    rcx, rcx
0x180004b70  jz      short loc_180004B9C
0x180004b72  mov     eax, r15d
0x180004b75  lock xadd [rcx], eax
0x180004b79  add     eax, r15d
0x180004b7c  jnz     short loc_180004B95
0x180004b7e  mov     rbx, [rdi]
0x180004b81  call    cs:__imp_GetProcessHeap
0x180004b87  mov     r8, rbx; lpMem
0x180004b8a  xor     edx, edx; dwFlags
0x180004b8c  mov     rcx, rax; hHeap
0x180004b8f  call    cs:__imp_HeapFree
0x180004b95  mov     [rdi], r13
0x180004b98  mov     [rdi+8], r13
0x180004b9c  mov     rdx, r14; unsigned __int64
0x180004b9f  mov     rcx, rdi; this
0x180004ba2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x180004ba7  mov     rax, [rdi]
0x180004baa  lea     rcx, [rax+4]
0x180004bae  neg     rax
0x180004bb1  sbb     rbx, rbx
0x180004bb4  and     rbx, rcx
0x180004bb7  jz      loc_180004F99
0x180004bbd  mov     rdx, [rdi+8]; DestinationSize
0x180004bc1  lea     r14, [rsi+18h]
0x180004bc5  lea     rdi, [rbx+rdx]
0x180004bc9  cmp     rbx, rdi
0x180004bcc  jz      short loc_180004C1D
0x180004bce  mov     r8, [rbp+18h]; Source
0x180004bd2  test    r8, r8
0x180004bd5  jz      short loc_180004C1D
0x180004bd7  cmp     [r8], r13w
0x180004bdb  jz      short loc_180004C1D
0x180004bdd  mov     rax, r15
0x180004be0  inc     rax
0x180004be3  cmp     [r8+rax*2], r13w
0x180004be8  jnz     short loc_180004BE0
0x180004bea  lea     r12, ds:2[rax*2]
0x180004bf2  cmp     rdx, r12
0x180004bf5  jnb     short loc_180004C05
0x180004bf7  test    r14, r14
0x180004bfa  jz      short loc_180004BFF
0x180004bfc  mov     [r14], r13
0x180004bff  lea     r14, [rsi+28h]
0x180004c03  jmp     short loc_180004C2E
0x180004c05  mov     r9, r12; SourceSize
0x180004c08  mov     rcx, rbx; Destination
0x180004c0b  call    memcpy_s
0x180004c10  test    r14, r14
0x180004c13  jz      short loc_180004C18
0x180004c15  mov     [r14], rbx
0x180004c18  add     rbx, r12
0x180004c1b  jmp     short loc_180004C25
0x180004c1d  test    r14, r14
0x180004c20  jz      short loc_180004C25
0x180004c22  mov     [r14], r13
0x180004c25  lea     r14, [rsi+28h]
0x180004c29  cmp     rbx, rdi
0x180004c2c  jz      short loc_180004C7D
0x180004c2e  mov     r8, [rbp+28h]; Source
0x180004c32  test    r8, r8
0x180004c35  jz      short loc_180004C7D
0x180004c37  cmp     [r8], r13b
0x180004c3a  jz      short loc_180004C7D
0x180004c3c  mov     rax, r15
0x180004c3f  inc     rax
0x180004c42  cmp     [r8+rax], r13b
0x180004c46  jnz     short loc_180004C3F
0x180004c48  mov     rdx, rdi
0x180004c4b  lea     r12, [rax+1]
0x180004c4f  sub     rdx, rbx; DestinationSize
0x180004c52  cmp     rdx, r12
0x180004c55  jnb     short loc_180004C65
0x180004c57  test    r14, r14
0x180004c5a  jz      short loc_180004C5F
0x180004c5c  mov     [r14], r13
0x180004c5f  lea     r14, [rsi+30h]
0x180004c63  jmp     short loc_180004C8E
0x180004c65  mov     r9, r12; SourceSize
0x180004c68  mov     rcx, rbx; Destination
0x180004c6b  call    memcpy_s
0x180004c70  test    r14, r14
0x180004c73  jz      short loc_180004C78
0x180004c75  mov     [r14], rbx
0x180004c78  add     rbx, r12
0x180004c7b  jmp     short loc_180004C85
0x180004c7d  test    r14, r14
0x180004c80  jz      short loc_180004C85
0x180004c82  mov     [r14], r13
0x180004c85  lea     r14, [rsi+30h]
0x180004c89  cmp     rbx, rdi
0x180004c8c  jz      short loc_180004CDD
0x180004c8e  mov     r8, [rbp+30h]; Source
0x180004c92  test    r8, r8
0x180004c95  jz      short loc_180004CDD
0x180004c97  cmp     [r8], r13b
0x180004c9a  jz      short loc_180004CDD
0x180004c9c  mov     rax, r15
0x180004c9f  inc     rax
0x180004ca2  cmp     [r8+rax], r13b
0x180004ca6  jnz     short loc_180004C9F
0x180004ca8  mov     rdx, rdi
0x180004cab  lea     r12, [rax+1]
0x180004caf  sub     rdx, rbx; DestinationSize
0x180004cb2  cmp     rdx, r12
0x180004cb5  jnb     short loc_180004CC5
0x180004cb7  test    r14, r14
0x180004cba  jz      short loc_180004CBF
0x180004cbc  mov     [r14], r13
0x180004cbf  lea     r14, [rsi+38h]
0x180004cc3  jmp     short loc_180004CEE
0x180004cc5  mov     r9, r12; SourceSize
0x180004cc8  mov     rcx, rbx; Destination
0x180004ccb  call    memcpy_s
0x180004cd0  test    r14, r14
0x180004cd3  jz      short loc_180004CD8
0x180004cd5  mov     [r14], rbx
0x180004cd8  add     rbx, r12
0x180004cdb  jmp     short loc_180004CE5
0x180004cdd  test    r14, r14
0x180004ce0  jz      short loc_180004CE5
0x180004ce2  mov     [r14], r13
0x180004ce5  lea     r14, [rsi+38h]
0x180004ce9  cmp     rbx, rdi
0x180004cec  jz      short loc_180004D3D
0x180004cee  mov     r8, [rbp+38h]; Source
0x180004cf2  test    r8, r8
0x180004cf5  jz      short loc_180004D3D
0x180004cf7  cmp     [r8], r13b
0x180004cfa  jz      short loc_180004D3D
0x180004cfc  mov     rax, r15
0x180004cff  inc     rax
0x180004d02  cmp     [r8+rax], r13b
0x180004d06  jnz     short loc_180004CFF
0x180004d08  mov     rdx, rdi
0x180004d0b  lea     r12, [rax+1]
0x180004d0f  sub     rdx, rbx; DestinationSize
0x180004d12  cmp     rdx, r12
0x180004d15  jnb     short loc_180004D25
0x180004d17  test    r14, r14
0x180004d1a  jz      short loc_180004D1F
0x180004d1c  mov     [r14], r13
0x180004d1f  lea     r14, [rsi+48h]
0x180004d23  jmp     short loc_180004D4E
0x180004d25  mov     r9, r12; SourceSize
0x180004d28  mov     rcx, rbx; Destination
0x180004d2b  call    memcpy_s
0x180004d30  test    r14, r14
0x180004d33  jz      short loc_180004D38
  ... truncated ...
```
