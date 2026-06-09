# wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)

- ea: `0x180005ef0`
- end: `0x1800063a0`
- name: `?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z`
- size: `1200`
- prototype: `void __fastcall(wil::StoredFailureInfo *__hidden this, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1800052b0`

## callees

- `0x180002ee0`
- `0x180005ef0`
- `0x180007c62`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180006224`
- `msvcrt!memcpy_s` at `0x1800062f8`
- `msvcrt!memcpy_s` at `0x180006364`
- `msvcrt!memcpy_s` at `0x180006224`
- `msvcrt!memcpy_s` at `0x1800062f8`
- `msvcrt!memcpy_s` at `0x180006364`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000616c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000616c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000619a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800060f1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006139`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000615d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000619a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006147`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061a8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800060ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006147`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800061a8`

## pseudocode

```c
void __fastcall wil::StoredFailureInfo::SetFailureInfo(wil::StoredFailureInfo *this, const struct wil::FailureInfo *a2)
{
  __int64 v2; // rbp
  __int64 v5; // r9
  __int64 v6; // rcx
  __int64 v7; // r13
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // r14
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rcx
  __int64 v22; // r11
  __int64 v23; // rax
  __int64 v24; // rcx
  __int64 v25; // r10
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rax
  volatile signed __int32 *v35; // rcx
  unsigned __int64 v36; // r15
  void *v37; // rbx
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v39; // rcx
  void *v40; // rbx
  HANDLE v41; // rax
  HANDLE v42; // rax
  volatile signed __int32 *v43; // rax
  volatile signed __int32 *v44; // r14
  volatile signed __int32 *v45; // rax
  void *v46; // rbx
  HANDLE v47; // rax
  char *v48; // rbx
  rsize_t v49; // rdx
  char **v50; // r15
  char *v51; // r14
  _WORD *v52; // r8
  __int64 v53; // rax
  unsigned __int64 v54; // r12
  char *v55; // rax
  char *v56; // rax
  char *v57; // rax
  char *v58; // rax
  char *v59; // rax
  char **v60; // r15
  char *v61; // rbx
  _WORD *v62; // r8
  __int64 v63; // rax
  unsigned __int64 v64; // r12
  char *v65; // rax
  char **v66; // rdi
  char *v67; // rbx
  _WORD *v68; // r8
  rsize_t v69; // rbp

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
  v35 = (volatile signed __int32 *)*((_QWORD *)this + 19);
  v36 = v7 + v10 + v16 + v19 + v22 + v25 + v28 + v5 + v31 + v13;
  if ( v35 )
  {
    if ( *v35 == 1 && *((_QWORD *)this + 20) >= v36 )
      goto LABEL_67;
    if ( _InterlockedExchangeAdd(v35, 0xFFFFFFFF) == 1 )
    {
      v37 = (void *)*((_QWORD *)this + 19);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v37);
    }
    *((_QWORD *)this + 19) = 0;
    *((_QWORD *)this + 20) = 0;
  }
  if ( v36 )
  {
    v42 = GetProcessHeap();
    v43 = (volatile signed __int32 *)HeapAlloc(v42, 0, v36 + 4);
    v44 = v43;
    if ( v43 )
    {
      *v43 = 0;
      v45 = (volatile signed __int32 *)*((_QWORD *)this + 19);
      if ( v45 )
      {
        if ( _InterlockedExchangeAdd(v45, 0xFFFFFFFF) == 1 )
        {
          v46 = (void *)*((_QWORD *)this + 19);
          v47 = GetProcessHeap();
          HeapFree(v47, 0, v46);
        }
        *((_QWORD *)this + 20) = 0;
      }
      *((_QWORD *)this + 19) = v44;
      *((_QWORD *)this + 20) = v36;
      _InterlockedIncrement(v44);
    }
  }
  else
  {
    v39 = (volatile signed __int32 *)*((_QWORD *)this + 19);
    if ( v39 )
    {
      if ( _InterlockedExchangeAdd(v39, 0xFFFFFFFF) == 1 )
      {
        v40 = (void *)*((_QWORD *)this + 19);
        v41 = GetProcessHeap();
        HeapFree(v41, 0, v40);
      }
      *((_QWORD *)this + 19) = 0;
      *((_QWORD *)this + 20) = 0;
    }
  }
LABEL_67:
  v48 = (char *)((*((_QWORD *)this + 19) + 4LL) & -(__int64)(*((_QWORD *)this + 19) != 0));
  if ( v48 )
  {
    v49 = *((_QWORD *)this + 20);
    v50 = (char **)((char *)this + 24);
    v51 = &v48[v49];
    if ( v48 == &v48[v49] )
      goto LABEL_77;
    v52 = (_WORD *)*((_QWORD *)a2 + 3);
    if ( !v52 )
      goto LABEL_77;
    if ( !*v52 )
      goto LABEL_77;
    v53 = -1;
    do
      ++v53;
    while ( v52[v53] );
    v54 = 2 * v53 + 2;
    if ( v49 >= v54 )
    {
      memcpy_s(v48, v49, v52, 2 * v53 + 2);
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v50 = v48;
      v48 += v54;
    }
    else
    {
LABEL_77:
      if ( this != (wil::StoredFailureInfo *)-24LL )
        *v50 = 0;
    }
    v55 = wil::details::WriteResultString<char const *>(v48, v51, *((_BYTE **)a2 + 5), (_QWORD *)this + 5);
    v56 = wil::details::WriteResultString<char const *>(v55, v51, *((_BYTE **)a2 + 6), (_QWORD *)this + 6);
    v57 = wil::details::WriteResultString<char const *>(v56, v51, *((_BYTE **)a2 + 7), (_QWORD *)this + 7);
    v58 = wil::details::WriteResultString<char const *>(v57, v51, *((_BYTE **)a2 + 9), (_QWORD *)this + 9);
    v59 = wil::details::WriteResultString<char const *>(v58, v51, *((_BYTE **)a2 + 16), (_QWORD *)this + 16);
    v60 = (char **)((char *)this + 120);
    v61 = wil::details::WriteResultString<char const *>(v59, v51, *((_BYTE **)a2 + 14), (_QWORD *)this + 14);
    if ( v61 == v51 )
      goto LABEL_88;
    v62 = (_WORD *)*((_QWORD *)a2 + 15);
    if ( !v62 )
      goto LABEL_88;
    if ( !*v62 )
      goto LABEL_88;
    v63 = -1;
    do
      ++v63;
    while ( v62[v63] );
    v64 = 2 * v63 + 2;
    if ( v51 - v61 >= v64 )
    {
      memcpy_s(v61, v51 - v61, v62, 2 * v63 + 2);
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v60 = v61;
      v61 += v64;
    }
    else
    {
LABEL_88:
      if ( this != (wil::StoredFailureInfo *)-120LL )
        *v60 = 0;
    }
    v65 = wil::details::WriteResultString<char const *>(v61, v51, *((_BYTE **)a2 + 11), (_QWORD *)this + 11);
    v66 = (char **)((char *)this + 96);
    v67 = v65;
    if ( v65 == v51 )
      goto LABEL_98;
    v68 = (_WORD *)*((_QWORD *)a2 + 12);
    if ( !v68 || !*v68 )
      goto LABEL_98;
    do
      ++v2;
    while ( v68[v2] );
    v69 = 2 * v2 + 2;
    if ( v51 - v65 >= v69 )
    {
      memcpy_s(v65, v51 - v65, v68, v69);
      if ( v66 )
        *v66 = v67;
      v67 += v69;
    }
    else
    {
LABEL_98:
      if ( v66 )
        *v66 = 0;
    }
    memset_0(v67, 0, v51 - v67);
  }
}

```

## disassembly

```asm
0x180005ef0  push    rbx
0x180005ef2  push    rbp
0x180005ef3  push    rsi
0x180005ef4  push    rdi
0x180005ef5  push    r12
0x180005ef7  push    r13
0x180005ef9  push    r14
0x180005efb  push    r15
0x180005efd  sub     rsp, 28h
0x180005f01  movups  xmm0, xmmword ptr [rdx]
0x180005f04  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180005f08  mov     rdi, rcx
0x180005f0b  mov     rsi, rdx
0x180005f0e  movups  xmmword ptr [rcx], xmm0
0x180005f11  movups  xmm1, xmmword ptr [rdx+10h]
0x180005f15  lea     r9d, [rbp+3]
0x180005f19  movups  xmmword ptr [rcx+10h], xmm1
0x180005f1d  movups  xmm0, xmmword ptr [rdx+20h]
0x180005f21  movups  xmmword ptr [rcx+20h], xmm0
0x180005f25  movups  xmm1, xmmword ptr [rdx+30h]
0x180005f29  movups  xmmword ptr [rcx+30h], xmm1
0x180005f2d  movups  xmm0, xmmword ptr [rdx+40h]
0x180005f31  movups  xmmword ptr [rcx+40h], xmm0
0x180005f35  movups  xmm1, xmmword ptr [rdx+50h]
0x180005f39  movups  xmmword ptr [rcx+50h], xmm1
0x180005f3d  movups  xmm0, xmmword ptr [rdx+60h]
0x180005f41  movups  xmmword ptr [rcx+60h], xmm0
0x180005f45  movups  xmm1, xmmword ptr [rdx+70h]
0x180005f49  movups  xmmword ptr [rcx+70h], xmm1
0x180005f4d  movups  xmm0, xmmword ptr [rdx+80h]
0x180005f54  movups  xmmword ptr [rcx+80h], xmm0
0x180005f5b  mov     rax, [rdx+90h]
0x180005f62  mov     [rcx+90h], rax
0x180005f69  mov     rcx, [rdx+18h]
0x180005f6d  xor     edx, edx
0x180005f6f  test    rcx, rcx
0x180005f72  jnz     short loc_180005F79
0x180005f74  mov     r13d, r9d
0x180005f77  jmp     short loc_180005F8D
0x180005f79  mov     rax, rbp
0x180005f7c  inc     rax
0x180005f7f  cmp     [rcx+rax*2], dx
0x180005f83  jnz     short loc_180005F7C
0x180005f85  lea     r13, ds:2[rax*2]
0x180005f8d  mov     rcx, [rsi+28h]
0x180005f91  test    rcx, rcx
0x180005f94  jnz     short loc_180005F9C
0x180005f96  lea     r12d, [rcx+1]
0x180005f9a  jmp     short loc_180005FAB
0x180005f9c  mov     rax, rbp
0x180005f9f  inc     rax
0x180005fa2  cmp     [rcx+rax], dl
0x180005fa5  jnz     short loc_180005F9F
0x180005fa7  lea     r12, [rax+1]
0x180005fab  mov     rcx, [rsi+30h]
0x180005faf  test    rcx, rcx
0x180005fb2  jnz     short loc_180005FBA
0x180005fb4  lea     r15d, [rcx+1]
0x180005fb8  jmp     short loc_180005FC9
0x180005fba  mov     rax, rbp
0x180005fbd  inc     rax
0x180005fc0  cmp     [rcx+rax], dl
0x180005fc3  jnz     short loc_180005FBD
0x180005fc5  lea     r15, [rax+1]
0x180005fc9  mov     rcx, [rsi+38h]
0x180005fcd  test    rcx, rcx
0x180005fd0  jnz     short loc_180005FD8
0x180005fd2  lea     r14d, [rcx+1]
0x180005fd6  jmp     short loc_180005FE7
0x180005fd8  mov     rax, rbp
0x180005fdb  inc     rax
0x180005fde  cmp     [rcx+rax], dl
0x180005fe1  jnz     short loc_180005FDB
0x180005fe3  lea     r14, [rax+1]
0x180005fe7  mov     rcx, [rsi+48h]
0x180005feb  test    rcx, rcx
0x180005fee  jnz     short loc_180005FF5
0x180005ff0  lea     ebx, [rcx+1]
0x180005ff3  jmp     short loc_180006004
0x180005ff5  mov     rax, rbp
0x180005ff8  inc     rax
0x180005ffb  cmp     [rcx+rax], dl
0x180005ffe  jnz     short loc_180005FF8
0x180006000  lea     rbx, [rax+1]
0x180006004  mov     rcx, [rsi+80h]
0x18000600b  test    rcx, rcx
0x18000600e  jnz     short loc_180006016
0x180006010  lea     r11d, [rcx+1]
0x180006014  jmp     short loc_180006025
0x180006016  mov     rax, rbp
0x180006019  inc     rax
0x18000601c  cmp     [rcx+rax], dl
0x18000601f  jnz     short loc_180006019
0x180006021  lea     r11, [rax+1]
0x180006025  mov     rcx, [rsi+70h]
0x180006029  test    rcx, rcx
0x18000602c  jnz     short loc_180006034
0x18000602e  lea     r10d, [rcx+1]
0x180006032  jmp     short loc_180006043
0x180006034  mov     rax, rbp
0x180006037  inc     rax
0x18000603a  cmp     [rcx+rax], dl
0x18000603d  jnz     short loc_180006037
0x18000603f  lea     r10, [rax+1]
0x180006043  mov     rcx, [rsi+78h]
0x180006047  test    rcx, rcx
0x18000604a  jnz     short loc_180006051
0x18000604c  mov     r8, r9
0x18000604f  jmp     short loc_180006065
0x180006051  mov     rax, rbp
0x180006054  inc     rax
0x180006057  cmp     [rcx+rax*2], dx
0x18000605b  jnz     short loc_180006054
0x18000605d  lea     r8, ds:2[rax*2]
0x180006065  mov     rcx, [rsi+58h]
0x180006069  test    rcx, rcx
0x18000606c  jnz     short loc_180006073
0x18000606e  lea     edx, [rcx+1]
0x180006071  jmp     short loc_180006082
0x180006073  mov     rax, rbp
0x180006076  inc     rax
0x180006079  cmp     [rcx+rax], dl
0x18000607c  jnz     short loc_180006076
0x18000607e  lea     rdx, [rax+1]
0x180006082  mov     rcx, [rsi+60h]
0x180006086  test    rcx, rcx
0x180006089  jz      short loc_1800060A3
0x18000608b  mov     rax, rbp
0x18000608e  xor     r9d, r9d
0x180006091  inc     rax
0x180006094  cmp     [rcx+rax*2], r9w
0x180006099  jnz     short loc_180006091
0x18000609b  lea     r9, ds:2[rax*2]
0x1800060a3  mov     rcx, [rdi+98h]
0x1800060aa  lea     rax, [r9+rdx]
0x1800060ae  add     rax, r8
0x1800060b1  add     rax, r10
0x1800060b4  add     rax, r11
0x1800060b7  add     rax, rbx
0x1800060ba  add     rax, r14
0x1800060bd  add     r15, rax
0x1800060c0  add     r15, r12
0x1800060c3  add     r15, r13
0x1800060c6  xor     r13d, r13d
0x1800060c9  test    rcx, rcx
0x1800060cc  jz      short loc_180006113
0x1800060ce  cmp     dword ptr [rcx], 1
0x1800060d1  jnz     short loc_1800060E0
0x1800060d3  cmp     [rdi+0A0h], r15
0x1800060da  jnb     loc_1800061C7
0x1800060e0  mov     eax, ebp
0x1800060e2  lock xadd [rcx], eax
0x1800060e6  add     eax, ebp
0x1800060e8  jnz     short loc_180006105
0x1800060ea  mov     rbx, [rdi+98h]
0x1800060f1  call    cs:__imp_GetProcessHeap
0x1800060f7  mov     r8, rbx; lpMem
0x1800060fa  xor     edx, edx; dwFlags
0x1800060fc  mov     rcx, rax; hHeap
0x1800060ff  call    cs:__imp_HeapFree
0x180006105  mov     [rdi+98h], r13
0x18000610c  mov     [rdi+0A0h], r13
0x180006113  test    r15, r15
0x180006116  jnz     short loc_18000615D
0x180006118  mov     rcx, [rdi+98h]
0x18000611f  test    rcx, rcx
0x180006122  jz      loc_1800061C7
0x180006128  mov     eax, ebp
0x18000612a  lock xadd [rcx], eax
0x18000612e  add     eax, ebp
0x180006130  jnz     short loc_18000614D
0x180006132  mov     rbx, [rdi+98h]
0x180006139  call    cs:__imp_GetProcessHeap
0x18000613f  mov     r8, rbx; lpMem
0x180006142  xor     edx, edx; dwFlags
0x180006144  mov     rcx, rax; hHeap
0x180006147  call    cs:__imp_HeapFree
0x18000614d  mov     [rdi+98h], r13
0x180006154  mov     [rdi+0A0h], r13
0x18000615b  jmp     short loc_1800061C7
0x18000615d  call    cs:__imp_GetProcessHeap
0x180006163  lea     r8, [r15+4]; dwBytes
0x180006167  xor     edx, edx; dwFlags
0x180006169  mov     rcx, rax; hHeap
0x18000616c  call    cs:__imp_HeapAlloc
0x180006172  mov     r14, rax
0x180006175  test    rax, rax
0x180006178  jz      short loc_1800061C7
0x18000617a  mov     [rax], r13d
0x18000617d  mov     rax, [rdi+98h]
0x180006184  test    rax, rax
0x180006187  jz      short loc_1800061B5
0x180006189  mov     ecx, ebp
0x18000618b  lock xadd [rax], ecx
0x18000618f  add     ecx, ebp
0x180006191  jnz     short loc_1800061AE
0x180006193  mov     rbx, [rdi+98h]
0x18000619a  call    cs:__imp_GetProcessHeap
0x1800061a0  mov     r8, rbx; lpMem
0x1800061a3  xor     edx, edx; dwFlags
0x1800061a5  mov     rcx, rax; hHeap
0x1800061a8  call    cs:__imp_HeapFree
0x1800061ae  mov     [rdi+0A0h], r13
0x1800061b5  mov     [rdi+98h], r14
0x1800061bc  mov     [rdi+0A0h], r15
0x1800061c3  lock inc dword ptr [r14]
0x1800061c7  mov     rax, [rdi+98h]
0x1800061ce  lea     rcx, [rax+4]
0x1800061d2  neg     rax
0x1800061d5  sbb     rbx, rbx
0x1800061d8  and     rbx, rcx
0x1800061db  jz      loc_18000638F
0x1800061e1  mov     rdx, [rdi+0A0h]; DestinationSize
0x1800061e8  lea     r15, [rdi+18h]
0x1800061ec  lea     r14, [rbx+rdx]
0x1800061f0  cmp     rbx, r14
0x1800061f3  jz      short loc_180006237
0x1800061f5  mov     r8, [rsi+18h]; Source
0x1800061f9  test    r8, r8
0x1800061fc  jz      short loc_180006237
0x1800061fe  cmp     [r8], r13w
0x180006202  jz      short loc_180006237
0x180006204  mov     rax, rbp
0x180006207  inc     rax
0x18000620a  cmp     [r8+rax*2], r13w
0x18000620f  jnz     short loc_180006207
0x180006211  lea     r12, ds:2[rax*2]
0x180006219  cmp     rdx, r12
0x18000621c  jb      short loc_180006237
0x18000621e  mov     r9, r12; SourceSize
0x180006221  mov     rcx, rbx; Destination
0x180006224  call    cs:__imp_memcpy_s
0x18000622a  test    r15, r15
0x18000622d  jz      short loc_180006232
0x18000622f  mov     [r15], rbx
0x180006232  add     rbx, r12
0x180006235  jmp     short loc_18000623F
0x180006237  test    r15, r15
0x18000623a  jz      short loc_18000623F
0x18000623c  mov     [r15], r13
0x18000623f  mov     r8, [rsi+28h]
0x180006243  lea     r9, [rdi+28h]
0x180006247  mov     rdx, r14
0x18000624a  mov     rcx, rbx
0x18000624d  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006252  mov     r8, [rsi+30h]
0x180006256  lea     r9, [rdi+30h]
0x18000625a  mov     rdx, r14
0x18000625d  mov     rcx, rax
0x180006260  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006265  mov     r8, [rsi+38h]
0x180006269  lea     r9, [rdi+38h]
0x18000626d  mov     rdx, r14
0x180006270  mov     rcx, rax
0x180006273  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x180006278  mov     r8, [rsi+48h]
0x18000627c  lea     r9, [rdi+48h]
0x180006280  mov     rdx, r14
0x180006283  mov     rcx, rax
0x180006286  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x18000628b  mov     r8, [rsi+80h]
0x180006292  lea     r9, [rdi+80h]
0x180006299  mov     rdx, r14
0x18000629c  mov     rcx, rax
0x18000629f  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800062a4  mov     r8, [rsi+70h]
0x1800062a8  lea     r9, [rdi+70h]
0x1800062ac  mov     rdx, r14
0x1800062af  mov     rcx, rax
0x1800062b2  call    ??$WriteResultString@PEBD@details@wil@@YAPEAEPEAE0PEBDPEAPEBD@Z; wil::details::WriteResultString<char const *>(uchar *,uchar *,char const *,char const * *)
0x1800062b7  lea     r15, [rdi+78h]
0x1800062bb  mov     rbx, rax
0x1800062be  cmp     rax, r14
0x1800062c1  jz      short loc_18000630B
0x1800062c3  mov     r8, [rsi+78h]; Source
0x1800062c7  test    r8, r8
0x1800062ca  jz      short loc_18000630B
0x1800062cc  cmp     [r8], r13w
0x1800062d0  jz      short loc_18000630B
0x1800062d2  mov     rax, rbp
0x1800062d5  inc     rax
0x1800062d8  cmp     [r8+rax*2], r13w
0x1800062dd  jnz     short loc_1800062D5
0x1800062df  mov     rdx, r14
0x1800062e2  lea     r12, ds:2[rax*2]
0x1800062ea  sub     rdx, rbx; DestinationSize
0x1800062ed  cmp     rdx, r12
0x1800062f0  jb      short loc_18000630B
0x1800062f2  mov     r9, r12; SourceSize
0x1800062f5  mov     rcx, rbx; Destination
0x1800062f8  call    cs:__imp_memcpy_s
0x1800062fe  test    r15, r15
0x180006301  jz      short loc_180006306
0x180006303  mov     [r15], rbx
0x180006306  add     rbx, r12
0x180006309  jmp     short loc_180006313
0x18000630b  test    r15, r15
0x18000630e  jz      short loc_180006313
0x180006310  mov     [r15], r13
0x180006313  mov     r8, [rsi+58h]
  ... truncated ...
```
