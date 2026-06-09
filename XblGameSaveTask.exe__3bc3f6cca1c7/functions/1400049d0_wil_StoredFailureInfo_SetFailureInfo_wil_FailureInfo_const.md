# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x1400049d0`
- end: `0x140004ffa`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1578`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1400028e0`

## callees

- `0x140001f36`
- `0x1400049d0`
- `0x140005568`
- `0x140005768`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004bdf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004bdf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004bd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004bd1`

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
0x1400049d0  push    rbx
0x1400049d2  push    rbp
0x1400049d3  push    rsi
0x1400049d4  push    rdi
0x1400049d5  push    r12
0x1400049d7  push    r13
0x1400049d9  push    r14
0x1400049db  push    r15
0x1400049dd  sub     rsp, 28h
0x1400049e1  movups  xmm0, xmmword ptr [rdx]
0x1400049e4  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400049e8  mov     rsi, rcx
0x1400049eb  mov     rbp, rdx
0x1400049ee  movups  xmmword ptr [rcx], xmm0
0x1400049f1  movups  xmm1, xmmword ptr [rdx+10h]
0x1400049f5  lea     ebx, [r15+3]
0x1400049f9  movups  xmmword ptr [rcx+10h], xmm1
0x1400049fd  movups  xmm0, xmmword ptr [rdx+20h]
0x140004a01  movups  xmmword ptr [rcx+20h], xmm0
0x140004a05  movups  xmm1, xmmword ptr [rdx+30h]
0x140004a09  movups  xmmword ptr [rcx+30h], xmm1
0x140004a0d  movups  xmm0, xmmword ptr [rdx+40h]
0x140004a11  movups  xmmword ptr [rcx+40h], xmm0
0x140004a15  movups  xmm1, xmmword ptr [rdx+50h]
0x140004a19  movups  xmmword ptr [rcx+50h], xmm1
0x140004a1d  movups  xmm0, xmmword ptr [rdx+60h]
0x140004a21  movups  xmmword ptr [rcx+60h], xmm0
0x140004a25  movups  xmm1, xmmword ptr [rdx+70h]
0x140004a29  movups  xmmword ptr [rcx+70h], xmm1
0x140004a2d  movups  xmm0, xmmword ptr [rdx+80h]
0x140004a34  movups  xmmword ptr [rcx+80h], xmm0
0x140004a3b  mov     rax, [rdx+90h]
0x140004a42  mov     [rcx+90h], rax
0x140004a49  mov     rcx, [rdx+18h]
0x140004a4d  xor     edx, edx
0x140004a4f  test    rcx, rcx
0x140004a52  jnz     short loc_140004A59
0x140004a54  mov     r13d, ebx
0x140004a57  jmp     short loc_140004A6D
0x140004a59  mov     rax, r15
0x140004a5c  inc     rax
0x140004a5f  cmp     [rcx+rax*2], dx
0x140004a63  jnz     short loc_140004A5C
0x140004a65  lea     r13, ds:2[rax*2]
0x140004a6d  mov     rcx, [rbp+28h]
0x140004a71  test    rcx, rcx
0x140004a74  jnz     short loc_140004A7C
0x140004a76  lea     r12d, [rcx+1]
0x140004a7a  jmp     short loc_140004A8B
0x140004a7c  mov     rax, r15
0x140004a7f  inc     rax
0x140004a82  cmp     [rcx+rax], dl
0x140004a85  jnz     short loc_140004A7F
0x140004a87  lea     r12, [rax+1]
0x140004a8b  mov     rcx, [rbp+30h]
0x140004a8f  test    rcx, rcx
0x140004a92  jnz     short loc_140004A9A
0x140004a94  lea     r14d, [rcx+1]
0x140004a98  jmp     short loc_140004AA9
0x140004a9a  mov     rax, r15
0x140004a9d  inc     rax
0x140004aa0  cmp     [rcx+rax], dl
0x140004aa3  jnz     short loc_140004A9D
0x140004aa5  lea     r14, [rax+1]
0x140004aa9  mov     rcx, [rbp+38h]
0x140004aad  test    rcx, rcx
0x140004ab0  jnz     short loc_140004AB7
0x140004ab2  lea     edi, [rcx+1]
0x140004ab5  jmp     short loc_140004AC6
0x140004ab7  mov     rax, r15
0x140004aba  inc     rax
0x140004abd  cmp     [rcx+rax], dl
0x140004ac0  jnz     short loc_140004ABA
0x140004ac2  lea     rdi, [rax+1]
0x140004ac6  mov     rcx, [rbp+48h]
0x140004aca  test    rcx, rcx
0x140004acd  jnz     short loc_140004AD5
0x140004acf  lea     r11d, [rcx+1]
0x140004ad3  jmp     short loc_140004AE4
0x140004ad5  mov     rax, r15
0x140004ad8  inc     rax
0x140004adb  cmp     [rcx+rax], dl
0x140004ade  jnz     short loc_140004AD8
0x140004ae0  lea     r11, [rax+1]
0x140004ae4  mov     rcx, [rbp+80h]
0x140004aeb  test    rcx, rcx
0x140004aee  jnz     short loc_140004AF6
0x140004af0  lea     r10d, [rcx+1]
0x140004af4  jmp     short loc_140004B05
0x140004af6  mov     rax, r15
0x140004af9  inc     rax
0x140004afc  cmp     [rcx+rax], dl
0x140004aff  jnz     short loc_140004AF9
0x140004b01  lea     r10, [rax+1]
0x140004b05  mov     rcx, [rbp+70h]
0x140004b09  test    rcx, rcx
0x140004b0c  jnz     short loc_140004B14
0x140004b0e  lea     r9d, [rcx+1]
0x140004b12  jmp     short loc_140004B23
0x140004b14  mov     rax, r15
0x140004b17  inc     rax
0x140004b1a  cmp     [rcx+rax], dl
0x140004b1d  jnz     short loc_140004B17
0x140004b1f  lea     r9, [rax+1]
0x140004b23  mov     rcx, [rbp+78h]
0x140004b27  test    rcx, rcx
0x140004b2a  jnz     short loc_140004B31
0x140004b2c  mov     r8, rbx
0x140004b2f  jmp     short loc_140004B45
0x140004b31  mov     rax, r15
0x140004b34  inc     rax
0x140004b37  cmp     [rcx+rax*2], dx
0x140004b3b  jnz     short loc_140004B34
0x140004b3d  lea     r8, ds:2[rax*2]
0x140004b45  mov     rcx, [rbp+58h]
0x140004b49  test    rcx, rcx
0x140004b4c  jnz     short loc_140004B53
0x140004b4e  lea     edx, [rcx+1]
0x140004b51  jmp     short loc_140004B62
0x140004b53  mov     rax, r15
0x140004b56  inc     rax
0x140004b59  cmp     [rcx+rax], dl
0x140004b5c  jnz     short loc_140004B56
0x140004b5e  lea     rdx, [rax+1]
0x140004b62  mov     rcx, [rbp+60h]
0x140004b66  test    rcx, rcx
0x140004b69  jz      short loc_140004B81
0x140004b6b  mov     rax, r15
0x140004b6e  xor     ebx, ebx
0x140004b70  inc     rax
0x140004b73  cmp     [rcx+rax*2], bx
0x140004b77  jnz     short loc_140004B70
0x140004b79  lea     rbx, ds:2[rax*2]
0x140004b81  lea     rax, [rbx+rdx]
0x140004b85  add     rax, r8
0x140004b88  add     rax, r9
0x140004b8b  add     rax, r10
0x140004b8e  add     rax, r11
0x140004b91  add     rax, rdi
0x140004b94  lea     rdi, [rsi+98h]
0x140004b9b  mov     rcx, [rdi]
0x140004b9e  add     r14, rax
0x140004ba1  add     r14, r12
0x140004ba4  add     r14, r13
0x140004ba7  xor     r13d, r13d
0x140004baa  test    rcx, rcx
0x140004bad  jz      short loc_140004BEC
0x140004baf  cmp     dword ptr [rcx], 1
0x140004bb2  jnz     short loc_140004BC2
0x140004bb4  cmp     [rsi+0A0h], r14
0x140004bbb  jnb     short loc_140004BF7
0x140004bbd  test    rcx, rcx
0x140004bc0  jz      short loc_140004BEC
0x140004bc2  mov     eax, r15d
0x140004bc5  lock xadd [rcx], eax
0x140004bc9  add     eax, r15d
0x140004bcc  jnz     short loc_140004BE5
0x140004bce  mov     rbx, [rdi]
0x140004bd1  call    cs:__imp_GetProcessHeap
0x140004bd7  mov     r8, rbx; lpMem
0x140004bda  xor     edx, edx; dwFlags
0x140004bdc  mov     rcx, rax; hHeap
0x140004bdf  call    cs:__imp_HeapFree
0x140004be5  mov     [rdi], r13
0x140004be8  mov     [rdi+8], r13
0x140004bec  mov     rdx, r14; unsigned __int64
0x140004bef  mov     rcx, rdi; this
0x140004bf2  call    ?create@shared_buffer@details@wil@@QEAA_N_K@Z; wil::details::shared_buffer::create(unsigned __int64)
0x140004bf7  mov     rax, [rdi]
0x140004bfa  lea     rcx, [rax+4]
0x140004bfe  neg     rax
0x140004c01  sbb     rbx, rbx
0x140004c04  and     rbx, rcx
0x140004c07  jz      loc_140004FE9
0x140004c0d  mov     rdx, [rdi+8]; DestinationSize
0x140004c11  lea     r14, [rsi+18h]
0x140004c15  lea     rdi, [rbx+rdx]
0x140004c19  cmp     rbx, rdi
0x140004c1c  jz      short loc_140004C6D
0x140004c1e  mov     r8, [rbp+18h]; Source
0x140004c22  test    r8, r8
0x140004c25  jz      short loc_140004C6D
0x140004c27  cmp     [r8], r13w
0x140004c2b  jz      short loc_140004C6D
0x140004c2d  mov     rax, r15
0x140004c30  inc     rax
0x140004c33  cmp     [r8+rax*2], r13w
0x140004c38  jnz     short loc_140004C30
0x140004c3a  lea     r12, ds:2[rax*2]
0x140004c42  cmp     rdx, r12
0x140004c45  jnb     short loc_140004C55
0x140004c47  test    r14, r14
0x140004c4a  jz      short loc_140004C4F
0x140004c4c  mov     [r14], r13
0x140004c4f  lea     r14, [rsi+28h]
0x140004c53  jmp     short loc_140004C7E
0x140004c55  mov     r9, r12; SourceSize
0x140004c58  mov     rcx, rbx; Destination
0x140004c5b  call    memcpy_s
0x140004c60  test    r14, r14
0x140004c63  jz      short loc_140004C68
0x140004c65  mov     [r14], rbx
0x140004c68  add     rbx, r12
0x140004c6b  jmp     short loc_140004C75
0x140004c6d  test    r14, r14
0x140004c70  jz      short loc_140004C75
0x140004c72  mov     [r14], r13
0x140004c75  lea     r14, [rsi+28h]
0x140004c79  cmp     rbx, rdi
0x140004c7c  jz      short loc_140004CCD
0x140004c7e  mov     r8, [rbp+28h]; Source
0x140004c82  test    r8, r8
0x140004c85  jz      short loc_140004CCD
0x140004c87  cmp     [r8], r13b
0x140004c8a  jz      short loc_140004CCD
0x140004c8c  mov     rax, r15
0x140004c8f  inc     rax
0x140004c92  cmp     [r8+rax], r13b
0x140004c96  jnz     short loc_140004C8F
0x140004c98  mov     rdx, rdi
0x140004c9b  lea     r12, [rax+1]
0x140004c9f  sub     rdx, rbx; DestinationSize
0x140004ca2  cmp     rdx, r12
0x140004ca5  jnb     short loc_140004CB5
0x140004ca7  test    r14, r14
0x140004caa  jz      short loc_140004CAF
0x140004cac  mov     [r14], r13
0x140004caf  lea     r14, [rsi+30h]
0x140004cb3  jmp     short loc_140004CDE
0x140004cb5  mov     r9, r12; SourceSize
0x140004cb8  mov     rcx, rbx; Destination
0x140004cbb  call    memcpy_s
0x140004cc0  test    r14, r14
0x140004cc3  jz      short loc_140004CC8
0x140004cc5  mov     [r14], rbx
0x140004cc8  add     rbx, r12
0x140004ccb  jmp     short loc_140004CD5
0x140004ccd  test    r14, r14
0x140004cd0  jz      short loc_140004CD5
0x140004cd2  mov     [r14], r13
0x140004cd5  lea     r14, [rsi+30h]
0x140004cd9  cmp     rbx, rdi
0x140004cdc  jz      short loc_140004D2D
0x140004cde  mov     r8, [rbp+30h]; Source
0x140004ce2  test    r8, r8
0x140004ce5  jz      short loc_140004D2D
0x140004ce7  cmp     [r8], r13b
0x140004cea  jz      short loc_140004D2D
0x140004cec  mov     rax, r15
0x140004cef  inc     rax
0x140004cf2  cmp     [r8+rax], r13b
0x140004cf6  jnz     short loc_140004CEF
0x140004cf8  mov     rdx, rdi
0x140004cfb  lea     r12, [rax+1]
0x140004cff  sub     rdx, rbx; DestinationSize
0x140004d02  cmp     rdx, r12
0x140004d05  jnb     short loc_140004D15
0x140004d07  test    r14, r14
0x140004d0a  jz      short loc_140004D0F
0x140004d0c  mov     [r14], r13
0x140004d0f  lea     r14, [rsi+38h]
0x140004d13  jmp     short loc_140004D3E
0x140004d15  mov     r9, r12; SourceSize
0x140004d18  mov     rcx, rbx; Destination
0x140004d1b  call    memcpy_s
0x140004d20  test    r14, r14
0x140004d23  jz      short loc_140004D28
0x140004d25  mov     [r14], rbx
0x140004d28  add     rbx, r12
0x140004d2b  jmp     short loc_140004D35
0x140004d2d  test    r14, r14
0x140004d30  jz      short loc_140004D35
0x140004d32  mov     [r14], r13
0x140004d35  lea     r14, [rsi+38h]
0x140004d39  cmp     rbx, rdi
0x140004d3c  jz      short loc_140004D8D
0x140004d3e  mov     r8, [rbp+38h]; Source
0x140004d42  test    r8, r8
0x140004d45  jz      short loc_140004D8D
0x140004d47  cmp     [r8], r13b
0x140004d4a  jz      short loc_140004D8D
0x140004d4c  mov     rax, r15
0x140004d4f  inc     rax
0x140004d52  cmp     [r8+rax], r13b
0x140004d56  jnz     short loc_140004D4F
0x140004d58  mov     rdx, rdi
0x140004d5b  lea     r12, [rax+1]
0x140004d5f  sub     rdx, rbx; DestinationSize
0x140004d62  cmp     rdx, r12
0x140004d65  jnb     short loc_140004D75
0x140004d67  test    r14, r14
0x140004d6a  jz      short loc_140004D6F
0x140004d6c  mov     [r14], r13
0x140004d6f  lea     r14, [rsi+48h]
0x140004d73  jmp     short loc_140004D9E
0x140004d75  mov     r9, r12; SourceSize
0x140004d78  mov     rcx, rbx; Destination
0x140004d7b  call    memcpy_s
0x140004d80  test    r14, r14
0x140004d83  jz      short loc_140004D88
  ... truncated ...
```
