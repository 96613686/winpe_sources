# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x140004b90`
- end: `0x1400051ba`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400028b4`

## callees

- `0x140001e7e`
- `0x140004b90`
- `0x140005758`
- `0x140005958`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004d9f`
- `KERNEL32!HeapFree` at `0x140004d9f`
- `KERNEL32!GetProcessHeap` at `0x140004d91`
- `KERNEL32!GetProcessHeap` at `0x140004d91`

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
0x140004b90  push    rbx
0x140004b92  push    rbp
0x140004b93  push    rsi
0x140004b94  push    rdi
0x140004b95  push    r12
0x140004b97  push    r13
0x140004b99  push    r14
0x140004b9b  push    r15
0x140004b9d  sub     rsp, 28h
0x140004ba1  movups  xmm0, xmmword ptr [rdx]
0x140004ba4  or      r15, 0FFFFFFFFFFFFFFFFh
0x140004ba8  mov     rsi, rcx
0x140004bab  mov     rbp, rdx
0x140004bae  movups  xmmword ptr [rcx], xmm0
0x140004bb1  movups  xmm1, xmmword ptr [rdx+10h]
0x140004bb5  lea     ebx, [r15+3]
0x140004bb9  movups  xmmword ptr [rcx+10h], xmm1
0x140004bbd  movups  xmm0, xmmword ptr [rdx+20h]
0x140004bc1  movups  xmmword ptr [rcx+20h], xmm0
0x140004bc5  movups  xmm1, xmmword ptr [rdx+30h]
0x140004bc9  movups  xmmword ptr [rcx+30h], xmm1
0x140004bcd  movups  xmm0, xmmword ptr [rdx+40h]
0x140004bd1  movups  xmmword ptr [rcx+40h], xmm0
0x140004bd5  movups  xmm1, xmmword ptr [rdx+50h]
0x140004bd9  movups  xmmword ptr [rcx+50h], xmm1
0x140004bdd  movups  xmm0, xmmword ptr [rdx+60h]
0x140004be1  movups  xmmword ptr [rcx+60h], xmm0
0x140004be5  movups  xmm1, xmmword ptr [rdx+70h]
0x140004be9  movups  xmmword ptr [rcx+70h], xmm1
0x140004bed  movups  xmm0, xmmword ptr [rdx+80h]
0x140004bf4  movups  xmmword ptr [rcx+80h], xmm0
0x140004bfb  mov     rax, [rdx+90h]
0x140004c02  mov     [rcx+90h], rax
0x140004c09  mov     rcx, [rdx+18h]
0x140004c0d  xor     edx, edx
0x140004c0f  test    rcx, rcx
0x140004c12  jnz     short loc_140004C19
0x140004c14  mov     r13d, ebx
0x140004c17  jmp     short loc_140004C2D
0x140004c19  mov     rax, r15
0x140004c1c  inc     rax
0x140004c1f  cmp     [rcx+rax*2], dx
0x140004c23  jnz     short loc_140004C1C
0x140004c25  lea     r13, ds:2[rax*2]
0x140004c2d  mov     rcx, [rbp+28h]
0x140004c31  test    rcx, rcx
0x140004c34  jnz     short loc_140004C3C
0x140004c36  lea     r12d, [rcx+1]
0x140004c3a  jmp     short loc_140004C4B
0x140004c3c  mov     rax, r15
0x140004c3f  inc     rax
0x140004c42  cmp     [rcx+rax], dl
0x140004c45  jnz     short loc_140004C3F
0x140004c47  lea     r12, [rax+1]
0x140004c4b  mov     rcx, [rbp+30h]
0x140004c4f  test    rcx, rcx
0x140004c52  jnz     short loc_140004C5A
0x140004c54  lea     r14d, [rcx+1]
0x140004c58  jmp     short loc_140004C69
0x140004c5a  mov     rax, r15
0x140004c5d  inc     rax
0x140004c60  cmp     [rcx+rax], dl
0x140004c63  jnz     short loc_140004C5D
0x140004c65  lea     r14, [rax+1]
0x140004c69  mov     rcx, [rbp+38h]
0x140004c6d  test    rcx, rcx
0x140004c70  jnz     short loc_140004C77
0x140004c72  lea     edi, [rcx+1]
0x140004c75  jmp     short loc_140004C86
0x140004c77  mov     rax, r15
0x140004c7a  inc     rax
0x140004c7d  cmp     [rcx+rax], dl
0x140004c80  jnz     short loc_140004C7A
0x140004c82  lea     rdi, [rax+1]
0x140004c86  mov     rcx, [rbp+48h]
0x140004c8a  test    rcx, rcx
0x140004c8d  jnz     short loc_140004C95
0x140004c8f  lea     r11d, [rcx+1]
0x140004c93  jmp     short loc_140004CA4
0x140004c95  mov     rax, r15
0x140004c98  inc     rax
0x140004c9b  cmp     [rcx+rax], dl
0x140004c9e  jnz     short loc_140004C98
0x140004ca0  lea     r11, [rax+1]
0x140004ca4  mov     rcx, [rbp+80h]
0x140004cab  test    rcx, rcx
0x140004cae  jnz     short loc_140004CB6
0x140004cb0  lea     r10d, [rcx+1]
0x140004cb4  jmp     short loc_140004CC5
0x140004cb6  mov     rax, r15
0x140004cb9  inc     rax
0x140004cbc  cmp     [rcx+rax], dl
0x140004cbf  jnz     short loc_140004CB9
0x140004cc1  lea     r10, [rax+1]
0x140004cc5  mov     rcx, [rbp+70h]
0x140004cc9  test    rcx, rcx
0x140004ccc  jnz     short loc_140004CD4
0x140004cce  lea     r9d, [rcx+1]
0x140004cd2  jmp     short loc_140004CE3
0x140004cd4  mov     rax, r15
0x140004cd7  inc     rax
0x140004cda  cmp     [rcx+rax], dl
0x140004cdd  jnz     short loc_140004CD7
0x140004cdf  lea     r9, [rax+1]
0x140004ce3  mov     rcx, [rbp+78h]
0x140004ce7  test    rcx, rcx
0x140004cea  jnz     short loc_140004CF1
0x140004cec  mov     r8, rbx
0x140004cef  jmp     short loc_140004D05
0x140004cf1  mov     rax, r15
0x140004cf4  inc     rax
0x140004cf7  cmp     [rcx+rax*2], dx
0x140004cfb  jnz     short loc_140004CF4
0x140004cfd  lea     r8, ds:2[rax*2]
0x140004d05  mov     rcx, [rbp+58h]
0x140004d09  test    rcx, rcx
0x140004d0c  jnz     short loc_140004D13
0x140004d0e  lea     edx, [rcx+1]
0x140004d11  jmp     short loc_140004D22
0x140004d13  mov     rax, r15
0x140004d16  inc     rax
0x140004d19  cmp     [rcx+rax], dl
0x140004d1c  jnz     short loc_140004D16
0x140004d1e  lea     rdx, [rax+1]
0x140004d22  mov     rcx, [rbp+60h]
0x140004d26  test    rcx, rcx
0x140004d29  jz      short loc_140004D41
0x140004d2b  mov     rax, r15
0x140004d2e  xor     ebx, ebx
0x140004d30  inc     rax
0x140004d33  cmp     [rcx+rax*2], bx
0x140004d37  jnz     short loc_140004D30
0x140004d39  lea     rbx, ds:2[rax*2]
0x140004d41  lea     rax, [rbx+rdx]
0x140004d45  add     rax, r8
0x140004d48  add     rax, r9
0x140004d4b  add     rax, r10
0x140004d4e  add     rax, r11
0x140004d51  add     rax, rdi
0x140004d54  lea     rdi, [rsi+98h]
0x140004d5b  mov     rcx, [rdi]
0x140004d5e  add     r14, rax
0x140004d61  add     r14, r12
0x140004d64  add     r14, r13
0x140004d67  xor     r13d, r13d
0x140004d6a  test    rcx, rcx
0x140004d6d  jz      short loc_140004DAC
0x140004d6f  cmp     dword ptr [rcx], 1
0x140004d72  jnz     short loc_140004D82
0x140004d74  cmp     [rsi+0A0h], r14
0x140004d7b  jnb     short loc_140004DB7
0x140004d7d  test    rcx, rcx
0x140004d80  jz      short loc_140004DAC
0x140004d82  mov     eax, r15d
0x140004d85  lock xadd [rcx], eax
0x140004d89  add     eax, r15d
0x140004d8c  jnz     short loc_140004DA5
0x140004d8e  mov     rbx, [rdi]
0x140004d91  call    cs:__imp_GetProcessHeap
0x140004d97  mov     r8, rbx; lpMem
0x140004d9a  xor     edx, edx; dwFlags
0x140004d9c  mov     rcx, rax; hHeap
0x140004d9f  call    cs:__imp_HeapFree
0x140004da5  mov     [rdi], r13
0x140004da8  mov     [rdi+8], r13
0x140004dac  mov     rdx, r14; unsigned __int64
0x140004daf  mov     rcx, rdi; this
0x140004db2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x140004db7  mov     rax, [rdi]
0x140004dba  lea     rcx, [rax+4]
0x140004dbe  neg     rax
0x140004dc1  sbb     rbx, rbx
0x140004dc4  and     rbx, rcx
0x140004dc7  jz      loc_1400051A9
0x140004dcd  mov     rdx, [rdi+8]; DestinationSize
0x140004dd1  lea     r14, [rsi+18h]
0x140004dd5  lea     rdi, [rbx+rdx]
0x140004dd9  cmp     rbx, rdi
0x140004ddc  jz      short loc_140004E2D
0x140004dde  mov     r8, [rbp+18h]; Source
0x140004de2  test    r8, r8
0x140004de5  jz      short loc_140004E2D
0x140004de7  cmp     [r8], r13w
0x140004deb  jz      short loc_140004E2D
0x140004ded  mov     rax, r15
0x140004df0  inc     rax
0x140004df3  cmp     [r8+rax*2], r13w
0x140004df8  jnz     short loc_140004DF0
0x140004dfa  lea     r12, ds:2[rax*2]
0x140004e02  cmp     rdx, r12
0x140004e05  jnb     short loc_140004E15
0x140004e07  test    r14, r14
0x140004e0a  jz      short loc_140004E0F
0x140004e0c  mov     [r14], r13
0x140004e0f  lea     r14, [rsi+28h]
0x140004e13  jmp     short loc_140004E3E
0x140004e15  mov     r9, r12; SourceSize
0x140004e18  mov     rcx, rbx; Destination
0x140004e1b  call    memcpy_s
0x140004e20  test    r14, r14
0x140004e23  jz      short loc_140004E28
0x140004e25  mov     [r14], rbx
0x140004e28  add     rbx, r12
0x140004e2b  jmp     short loc_140004E35
0x140004e2d  test    r14, r14
0x140004e30  jz      short loc_140004E35
0x140004e32  mov     [r14], r13
0x140004e35  lea     r14, [rsi+28h]
0x140004e39  cmp     rbx, rdi
0x140004e3c  jz      short loc_140004E8D
0x140004e3e  mov     r8, [rbp+28h]; Source
0x140004e42  test    r8, r8
0x140004e45  jz      short loc_140004E8D
0x140004e47  cmp     [r8], r13b
0x140004e4a  jz      short loc_140004E8D
0x140004e4c  mov     rax, r15
0x140004e4f  inc     rax
0x140004e52  cmp     [r8+rax], r13b
0x140004e56  jnz     short loc_140004E4F
0x140004e58  mov     rdx, rdi
0x140004e5b  lea     r12, [rax+1]
0x140004e5f  sub     rdx, rbx; DestinationSize
0x140004e62  cmp     rdx, r12
0x140004e65  jnb     short loc_140004E75
0x140004e67  test    r14, r14
0x140004e6a  jz      short loc_140004E6F
0x140004e6c  mov     [r14], r13
0x140004e6f  lea     r14, [rsi+30h]
0x140004e73  jmp     short loc_140004E9E
0x140004e75  mov     r9, r12; SourceSize
0x140004e78  mov     rcx, rbx; Destination
0x140004e7b  call    memcpy_s
0x140004e80  test    r14, r14
0x140004e83  jz      short loc_140004E88
0x140004e85  mov     [r14], rbx
0x140004e88  add     rbx, r12
0x140004e8b  jmp     short loc_140004E95
0x140004e8d  test    r14, r14
0x140004e90  jz      short loc_140004E95
0x140004e92  mov     [r14], r13
0x140004e95  lea     r14, [rsi+30h]
0x140004e99  cmp     rbx, rdi
0x140004e9c  jz      short loc_140004EED
0x140004e9e  mov     r8, [rbp+30h]; Source
0x140004ea2  test    r8, r8
0x140004ea5  jz      short loc_140004EED
0x140004ea7  cmp     [r8], r13b
0x140004eaa  jz      short loc_140004EED
0x140004eac  mov     rax, r15
0x140004eaf  inc     rax
0x140004eb2  cmp     [r8+rax], r13b
0x140004eb6  jnz     short loc_140004EAF
0x140004eb8  mov     rdx, rdi
0x140004ebb  lea     r12, [rax+1]
0x140004ebf  sub     rdx, rbx; DestinationSize
0x140004ec2  cmp     rdx, r12
0x140004ec5  jnb     short loc_140004ED5
0x140004ec7  test    r14, r14
0x140004eca  jz      short loc_140004ECF
0x140004ecc  mov     [r14], r13
0x140004ecf  lea     r14, [rsi+38h]
0x140004ed3  jmp     short loc_140004EFE
0x140004ed5  mov     r9, r12; SourceSize
0x140004ed8  mov     rcx, rbx; Destination
0x140004edb  call    memcpy_s
0x140004ee0  test    r14, r14
0x140004ee3  jz      short loc_140004EE8
0x140004ee5  mov     [r14], rbx
0x140004ee8  add     rbx, r12
0x140004eeb  jmp     short loc_140004EF5
0x140004eed  test    r14, r14
0x140004ef0  jz      short loc_140004EF5
0x140004ef2  mov     [r14], r13
0x140004ef5  lea     r14, [rsi+38h]
0x140004ef9  cmp     rbx, rdi
0x140004efc  jz      short loc_140004F4D
0x140004efe  mov     r8, [rbp+38h]; Source
0x140004f02  test    r8, r8
0x140004f05  jz      short loc_140004F4D
0x140004f07  cmp     [r8], r13b
0x140004f0a  jz      short loc_140004F4D
0x140004f0c  mov     rax, r15
0x140004f0f  inc     rax
0x140004f12  cmp     [r8+rax], r13b
0x140004f16  jnz     short loc_140004F0F
0x140004f18  mov     rdx, rdi
0x140004f1b  lea     r12, [rax+1]
0x140004f1f  sub     rdx, rbx; DestinationSize
0x140004f22  cmp     rdx, r12
0x140004f25  jnb     short loc_140004F35
0x140004f27  test    r14, r14
0x140004f2a  jz      short loc_140004F2F
0x140004f2c  mov     [r14], r13
0x140004f2f  lea     r14, [rsi+48h]
0x140004f33  jmp     short loc_140004F5E
0x140004f35  mov     r9, r12; SourceSize
0x140004f38  mov     rcx, rbx; Destination
0x140004f3b  call    memcpy_s
0x140004f40  test    r14, r14
0x140004f43  jz      short loc_140004F48
  ... truncated ...
```
