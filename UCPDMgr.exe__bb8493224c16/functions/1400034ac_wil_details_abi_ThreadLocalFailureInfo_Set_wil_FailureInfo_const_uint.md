# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x1400034ac`
- end: `0x1400036ac`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *this, const struct wil::FailureInfo *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140003910`

## callees

- `0x140001714`
- `0x1400034ac`
- `0x1400046a0`
- `0x14000f340`
- `0x14000f550`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400035ad`
- `KERNEL32!HeapFree` at `0x1400035ad`
- `KERNEL32!GetProcessHeap` at `0x14000359f`
- `KERNEL32!GetProcessHeap` at `0x14000359f`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalFailureInfo::Set(
        wil::details_abi::ThreadLocalFailureInfo *this,
        const struct wil::FailureInfo *a2,
        int a3)
{
  __int64 v4; // r15
  __int64 v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rbp
  rsize_t *v16; // rdi
  LPVOID v17; // r14
  void *v18; // rbx
  HANDLE ProcessHeap; // rax
  char *v20; // rbx
  rsize_t v21; // rdx
  char **v22; // rdi
  _BYTE *v23; // r8
  char *v24; // rbp
  __int64 v25; // rax
  __int64 v26; // r14
  _BYTE *v27; // r8
  char **v28; // rdi
  char *v29; // rax

  *((_DWORD *)this + 1) = a3;
  *((_DWORD *)this + 2) = *((_DWORD *)a2 + 2);
  v4 = -1;
  *((_QWORD *)this + 2) = 0;
  *((_WORD *)this + 12) = *((_WORD *)a2 + 32);
  *((_BYTE *)this + 26) = *(_BYTE *)a2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)a2 + 17);
  *((_QWORD *)this + 6) = *((_QWORD *)a2 + 18);
  *((_QWORD *)this + 7) = 0;
  v6 = *((_QWORD *)a2 + 7);
  v7 = 1;
  if ( v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_BYTE *)(v6 + v9) );
    v8 = v9 + 1;
  }
  else
  {
    v8 = 1;
  }
  v10 = *((_QWORD *)a2 + 16);
  if ( v10 )
  {
    v11 = -1;
    do
      ++v11;
    while ( *(_BYTE *)(v10 + v11) );
    v7 = v11 + 1;
  }
  v12 = *((_QWORD *)a2 + 3);
  if ( v12 )
  {
    v14 = -1;
    do
      ++v14;
    while ( *(_WORD *)(v12 + 2 * v14) );
    v13 = 2 * v14 + 2;
  }
  else
  {
    v13 = 2;
  }
  v15 = v8 + v13 + v7;
  v16 = (rsize_t *)((char *)this + 72);
  if ( !*((_QWORD *)this + 8) || *v16 < v15 )
  {
    v17 = wil::details::ProcessHeapAlloc(8u, v8 + v13 + v7);
    if ( v17 )
    {
      v18 = (void *)*((_QWORD *)this + 8);
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v18);
      *((_QWORD *)this + 8) = v17;
      *v16 = v15;
    }
  }
  v20 = (char *)*((_QWORD *)this + 8);
  if ( v20 )
  {
    v21 = *v16;
    v22 = (char **)((char *)this + 16);
    v23 = (_BYTE *)*((_QWORD *)a2 + 7);
    v24 = &v20[v21];
    if ( v20 == &v20[v21] )
      goto LABEL_29;
    if ( !v23 )
      goto LABEL_29;
    if ( !*v23 )
      goto LABEL_29;
    v25 = -1;
    do
      ++v25;
    while ( v23[v25] );
    v26 = v25 + 1;
    if ( v21 >= v25 + 1 )
    {
      memcpy_s(*((void *const *)this + 8), v21, v23, v25 + 1);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = v20;
      v20 += v26;
    }
    else
    {
LABEL_29:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-16LL )
        *v22 = 0;
    }
    v27 = (_BYTE *)*((_QWORD *)a2 + 16);
    v28 = (char **)((char *)this + 32);
    if ( v20 == v24 || !v27 || !*v27 )
      goto LABEL_39;
    do
      ++v4;
    while ( v27[v4] );
    if ( v24 - v20 >= (unsigned __int64)(v4 + 1) )
    {
      memcpy_s(v20, v24 - v20, v27, v4 + 1);
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = v20;
      v20 += v4 + 1;
    }
    else
    {
LABEL_39:
      if ( this != (wil::details_abi::ThreadLocalFailureInfo *)-32LL )
        *v28 = 0;
    }
    v29 = wil::details::WriteResultString<wchar_t const *>(v20, v24, *((_WORD **)a2 + 3), (_QWORD *)this + 7);
    memset(v29, 0, v24 - v29);
  }
}

```

## disassembly

```asm
0x1400034ac  mov     [rsp+arg_0], rbx
0x1400034b1  mov     [rsp+arg_8], rbp
0x1400034b6  mov     [rsp+arg_10], rsi
0x1400034bb  push    rdi
0x1400034bc  push    r12
0x1400034be  push    r13
0x1400034c0  push    r14
0x1400034c2  push    r15
0x1400034c4  sub     rsp, 20h
0x1400034c8  mov     [rcx+4], r8d
0x1400034cc  xor     r12d, r12d
0x1400034cf  mov     eax, [rdx+8]
0x1400034d2  mov     rsi, rcx
0x1400034d5  mov     [rcx+8], eax
0x1400034d8  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400034dc  mov     [rcx+10h], r12
0x1400034e0  mov     r13, rdx
0x1400034e3  movzx   eax, word ptr [rdx+40h]
0x1400034e7  mov     [rcx+18h], ax
0x1400034eb  mov     al, [rdx]
0x1400034ed  mov     [rcx+1Ah], al
0x1400034f0  mov     [rcx+20h], r12
0x1400034f4  mov     rax, [rdx+88h]
0x1400034fb  mov     [rcx+28h], rax
0x1400034ff  mov     rax, [rdx+90h]
0x140003506  mov     [rcx+30h], rax
0x14000350a  mov     [rcx+38h], r12
0x14000350e  mov     rcx, [rdx+38h]
0x140003512  lea     edx, [r12+1]
0x140003517  test    rcx, rcx
0x14000351a  jnz     short loc_140003521
0x14000351c  mov     r8d, edx
0x14000351f  jmp     short loc_140003531
0x140003521  mov     rax, r15
0x140003524  inc     rax
0x140003527  cmp     [rcx+rax], r12b
0x14000352b  jnz     short loc_140003524
0x14000352d  lea     r8, [rax+1]; unsigned __int64
0x140003531  mov     rcx, [r13+80h]
0x140003538  test    rcx, rcx
0x14000353b  jz      short loc_14000354D
0x14000353d  mov     rax, r15
0x140003540  inc     rax
0x140003543  cmp     [rcx+rax], r12b
0x140003547  jnz     short loc_140003540
0x140003549  lea     rdx, [rax+1]
0x14000354d  mov     rcx, [r13+18h]
0x140003551  test    rcx, rcx
0x140003554  jnz     short loc_14000355B
0x140003556  lea     eax, [rcx+2]
0x140003559  jmp     short loc_140003570
0x14000355b  mov     rax, r15
0x14000355e  inc     rax
0x140003561  cmp     [rcx+rax*2], r12w
0x140003566  jnz     short loc_14000355E
0x140003568  lea     rax, ds:2[rax*2]
0x140003570  lea     rbp, [rax+rdx]
0x140003574  add     rbp, r8
0x140003577  lea     rdi, [rsi+48h]
0x14000357b  cmp     [rsi+40h], r12
0x14000357f  jz      short loc_140003586
0x140003581  cmp     [rdi], rbp
0x140003584  jnb     short loc_1400035BA
0x140003586  mov     rdx, rbp; dwBytes
0x140003589  mov     ecx, 8; dwFlags
0x14000358e  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x140003593  mov     r14, rax
0x140003596  test    rax, rax
0x140003599  jz      short loc_1400035BA
0x14000359b  mov     rbx, [rsi+40h]
0x14000359f  call    cs:__imp_GetProcessHeap
0x1400035a5  mov     r8, rbx; lpMem
0x1400035a8  xor     edx, edx; dwFlags
0x1400035aa  mov     rcx, rax; hHeap
0x1400035ad  call    cs:__imp_HeapFree
0x1400035b3  mov     [rsi+40h], r14
0x1400035b7  mov     [rdi], rbp
0x1400035ba  mov     rbx, [rsi+40h]
0x1400035be  test    rbx, rbx
0x1400035c1  jz      loc_14000368F
0x1400035c7  mov     rdx, [rdi]; DestinationSize
0x1400035ca  lea     rdi, [rsi+10h]
0x1400035ce  mov     r8, [r13+38h]; Source
0x1400035d2  lea     rbp, [rdx+rbx]
0x1400035d6  cmp     rbx, rbp
0x1400035d9  jz      short loc_140003612
0x1400035db  test    r8, r8
0x1400035de  jz      short loc_140003612
0x1400035e0  cmp     [r8], r12b
0x1400035e3  jz      short loc_140003612
0x1400035e5  mov     rax, r15
0x1400035e8  inc     rax
0x1400035eb  cmp     [r8+rax], r12b
0x1400035ef  jnz     short loc_1400035E8
0x1400035f1  lea     r14, [rax+1]
0x1400035f5  cmp     rdx, r14
0x1400035f8  jb      short loc_140003612
0x1400035fa  mov     r9, r14; SourceSize
0x1400035fd  mov     rcx, rbx; Destination
0x140003600  call    memcpy_s
0x140003605  test    rdi, rdi
0x140003608  jz      short loc_14000360D
0x14000360a  mov     [rdi], rbx
0x14000360d  add     rbx, r14
0x140003610  jmp     short loc_14000361A
0x140003612  test    rdi, rdi
0x140003615  jz      short loc_14000361A
0x140003617  mov     [rdi], r12
0x14000361a  mov     r8, [r13+80h]; Source
0x140003621  lea     rdi, [rsi+20h]
0x140003625  cmp     rbx, rbp
0x140003628  jz      short loc_140003664
0x14000362a  test    r8, r8
0x14000362d  jz      short loc_140003664
0x14000362f  cmp     [r8], r12b
0x140003632  jz      short loc_140003664
0x140003634  inc     r15
0x140003637  cmp     [r8+r15], r12b
0x14000363b  jnz     short loc_140003634
0x14000363d  mov     rdx, rbp
0x140003640  lea     r14, [r15+1]
0x140003644  sub     rdx, rbx; DestinationSize
0x140003647  cmp     rdx, r14
0x14000364a  jb      short loc_140003664
0x14000364c  mov     r9, r14; SourceSize
0x14000364f  mov     rcx, rbx; Destination
0x140003652  call    memcpy_s
0x140003657  test    rdi, rdi
0x14000365a  jz      short loc_14000365F
0x14000365c  mov     [rdi], rbx
0x14000365f  add     rbx, r14
0x140003662  jmp     short loc_14000366C
0x140003664  test    rdi, rdi
0x140003667  jz      short loc_14000366C
0x140003669  mov     [rdi], r12
0x14000366c  mov     r8, [r13+18h]
0x140003670  lea     r9, [rsi+38h]
0x140003674  mov     rdx, rbp
0x140003677  mov     rcx, rbx
0x14000367a  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x14000367f  sub     rbp, rax
0x140003682  xor     edx, edx; Val
0x140003684  mov     r8, rbp; Size
0x140003687  mov     rcx, rax; void *
0x14000368a  call    memset
0x14000368f  mov     rbx, [rsp+48h+arg_0]
0x140003694  mov     rbp, [rsp+48h+arg_8]
0x140003699  mov     rsi, [rsp+48h+arg_10]
0x14000369e  add     rsp, 20h
0x1400036a2  pop     r15
0x1400036a4  pop     r14
0x1400036a6  pop     r13
0x1400036a8  pop     r12
0x1400036aa  pop     rdi
0x1400036ab  retn
```
