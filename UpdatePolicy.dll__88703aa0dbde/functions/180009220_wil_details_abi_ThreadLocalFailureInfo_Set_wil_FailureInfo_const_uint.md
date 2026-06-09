# wil::details_abi::ThreadLocalFailureInfo::Set(wil::FailureInfo const &,uint)

- ea: `0x180009220`
- end: `0x180009420`
- name: `?Set@ThreadLocalFailureInfo@details_abi@wil@@QEAAXAEBUFailureInfo@3@I@Z`
- size: `512`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalFailureInfo *__hidden this, const struct wil::FailureInfo *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180009680`

## callees

- `0x180007c08`
- `0x180007d40`
- `0x180009220`
- `0x180009890`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009313`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009321`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009321`

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
  void *v29; // rax

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
    v29 = (void *)wil::details::WriteResultString<wchar_t const *>(v20, v24, *((_QWORD *)a2 + 3), (char *)this + 56);
    memset(v29, 0, v24 - (_BYTE *)v29);
  }
}

```

## disassembly

```asm
0x180009220  mov     [rsp+arg_0], rbx
0x180009225  mov     [rsp+arg_8], rbp
0x18000922a  mov     [rsp+arg_10], rsi
0x18000922f  push    rdi
0x180009230  push    r12
0x180009232  push    r13
0x180009234  push    r14
0x180009236  push    r15
0x180009238  sub     rsp, 20h
0x18000923c  mov     [rcx+4], r8d
0x180009240  xor     r12d, r12d
0x180009243  mov     eax, [rdx+8]
0x180009246  mov     rsi, rcx
0x180009249  mov     [rcx+8], eax
0x18000924c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180009250  mov     [rcx+10h], r12
0x180009254  mov     r13, rdx
0x180009257  movzx   eax, word ptr [rdx+40h]
0x18000925b  mov     [rcx+18h], ax
0x18000925f  mov     al, [rdx]
0x180009261  mov     [rcx+1Ah], al
0x180009264  mov     [rcx+20h], r12
0x180009268  mov     rax, [rdx+88h]
0x18000926f  mov     [rcx+28h], rax
0x180009273  mov     rax, [rdx+90h]
0x18000927a  mov     [rcx+30h], rax
0x18000927e  mov     [rcx+38h], r12
0x180009282  mov     rcx, [rdx+38h]
0x180009286  lea     edx, [r12+1]
0x18000928b  test    rcx, rcx
0x18000928e  jnz     short loc_180009295
0x180009290  mov     r8d, edx
0x180009293  jmp     short loc_1800092A5
0x180009295  mov     rax, r15
0x180009298  inc     rax
0x18000929b  cmp     [rcx+rax], r12b
0x18000929f  jnz     short loc_180009298
0x1800092a1  lea     r8, [rax+1]; unsigned __int64
0x1800092a5  mov     rcx, [r13+80h]
0x1800092ac  test    rcx, rcx
0x1800092af  jz      short loc_1800092C1
0x1800092b1  mov     rax, r15
0x1800092b4  inc     rax
0x1800092b7  cmp     [rcx+rax], r12b
0x1800092bb  jnz     short loc_1800092B4
0x1800092bd  lea     rdx, [rax+1]
0x1800092c1  mov     rcx, [r13+18h]
0x1800092c5  test    rcx, rcx
0x1800092c8  jnz     short loc_1800092CF
0x1800092ca  lea     eax, [rcx+2]
0x1800092cd  jmp     short loc_1800092E4
0x1800092cf  mov     rax, r15
0x1800092d2  inc     rax
0x1800092d5  cmp     [rcx+rax*2], r12w
0x1800092da  jnz     short loc_1800092D2
0x1800092dc  lea     rax, ds:2[rax*2]
0x1800092e4  lea     rbp, [rax+rdx]
0x1800092e8  add     rbp, r8
0x1800092eb  lea     rdi, [rsi+48h]
0x1800092ef  cmp     [rsi+40h], r12
0x1800092f3  jz      short loc_1800092FA
0x1800092f5  cmp     [rdi], rbp
0x1800092f8  jnb     short loc_18000932E
0x1800092fa  mov     rdx, rbp; dwBytes
0x1800092fd  mov     ecx, 8; dwFlags
0x180009302  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x180009307  mov     r14, rax
0x18000930a  test    rax, rax
0x18000930d  jz      short loc_18000932E
0x18000930f  mov     rbx, [rsi+40h]
0x180009313  call    cs:__imp_GetProcessHeap
0x180009319  mov     r8, rbx; lpMem
0x18000931c  xor     edx, edx; dwFlags
0x18000931e  mov     rcx, rax; hHeap
0x180009321  call    cs:__imp_HeapFree
0x180009327  mov     [rsi+40h], r14
0x18000932b  mov     [rdi], rbp
0x18000932e  mov     rbx, [rsi+40h]
0x180009332  test    rbx, rbx
0x180009335  jz      loc_180009403
0x18000933b  mov     rdx, [rdi]; DestinationSize
0x18000933e  lea     rdi, [rsi+10h]
0x180009342  mov     r8, [r13+38h]; Source
0x180009346  lea     rbp, [rdx+rbx]
0x18000934a  cmp     rbx, rbp
0x18000934d  jz      short loc_180009386
0x18000934f  test    r8, r8
0x180009352  jz      short loc_180009386
0x180009354  cmp     [r8], r12b
0x180009357  jz      short loc_180009386
0x180009359  mov     rax, r15
0x18000935c  inc     rax
0x18000935f  cmp     [r8+rax], r12b
0x180009363  jnz     short loc_18000935C
0x180009365  lea     r14, [rax+1]
0x180009369  cmp     rdx, r14
0x18000936c  jb      short loc_180009386
0x18000936e  mov     r9, r14; SourceSize
0x180009371  mov     rcx, rbx; Destination
0x180009374  call    memcpy_s
0x180009379  test    rdi, rdi
0x18000937c  jz      short loc_180009381
0x18000937e  mov     [rdi], rbx
0x180009381  add     rbx, r14
0x180009384  jmp     short loc_18000938E
0x180009386  test    rdi, rdi
0x180009389  jz      short loc_18000938E
0x18000938b  mov     [rdi], r12
0x18000938e  mov     r8, [r13+80h]; Source
0x180009395  lea     rdi, [rsi+20h]
0x180009399  cmp     rbx, rbp
0x18000939c  jz      short loc_1800093D8
0x18000939e  test    r8, r8
0x1800093a1  jz      short loc_1800093D8
0x1800093a3  cmp     [r8], r12b
0x1800093a6  jz      short loc_1800093D8
0x1800093a8  inc     r15
0x1800093ab  cmp     [r8+r15], r12b
0x1800093af  jnz     short loc_1800093A8
0x1800093b1  mov     rdx, rbp
0x1800093b4  lea     r14, [r15+1]
0x1800093b8  sub     rdx, rbx; DestinationSize
0x1800093bb  cmp     rdx, r14
0x1800093be  jb      short loc_1800093D8
0x1800093c0  mov     r9, r14; SourceSize
0x1800093c3  mov     rcx, rbx; Destination
0x1800093c6  call    memcpy_s
0x1800093cb  test    rdi, rdi
0x1800093ce  jz      short loc_1800093D3
0x1800093d0  mov     [rdi], rbx
0x1800093d3  add     rbx, r14
0x1800093d6  jmp     short loc_1800093E0
0x1800093d8  test    rdi, rdi
0x1800093db  jz      short loc_1800093E0
0x1800093dd  mov     [rdi], r12
0x1800093e0  mov     r8, [r13+18h]
0x1800093e4  lea     r9, [rsi+38h]
0x1800093e8  mov     rdx, rbp
0x1800093eb  mov     rcx, rbx
0x1800093ee  call    ??$WriteResultString@PEB_W@details@wil@@YAPEAEPEAE0PEB_WPEAPEB_W@Z; wil::details::WriteResultString<wchar_t const *>(uchar *,uchar *,wchar_t const *,wchar_t const * *)
0x1800093f3  sub     rbp, rax
0x1800093f6  xor     edx, edx; Val
0x1800093f8  mov     r8, rbp; Size
0x1800093fb  mov     rcx, rax; void *
0x1800093fe  call    memset
0x180009403  mov     rbx, [rsp+48h+arg_0]
0x180009408  mov     rbp, [rsp+48h+arg_8]
0x18000940d  mov     rsi, [rsp+48h+arg_10]
0x180009412  add     rsp, 20h
0x180009416  pop     r15
0x180009418  pop     r14
0x18000941a  pop     r13
0x18000941c  pop     r12
0x18000941e  pop     rdi
0x18000941f  retn
```
