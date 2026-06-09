# ClientApiErrorTrace::ClientApiErrorTrace(char const *,void const *,int,void const *)

- ea: `0x1800d00d4`
- end: `0x1800d0482`
- name: `??0ClientApiErrorTrace@@QEAA@PEBDPEBXH1@Z`
- size: `942`
- prototype: `ClientApiErrorTrace *__fastcall(ClientApiErrorTrace *__hidden this, const char *, const void *, int, const void *)`
- caller_count: `11`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800b6080`
- `0x1800ce610`
- `0x1800ce930`
- `0x1800cfb90`
- `0x1800cff20`
- `0x1800d15b0`
- `0x18015b570`
- `0x18015cb00`
- `0x18015e080`
- `0x18017bcc0`
- `0x180260e80`

## callees

- `0x180098180`
- `0x1800d00d4`
- `0x1800deac4`
- `0x1800fbdf4`
- `0x1801e9258`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d02bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d032a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d02bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d032a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d02cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d02cd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d0338`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d01b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d02e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d01b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0200`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0259`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d0276`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d02e9`

## string_xrefs

- `0x1800d03de`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x1800d042d`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`
- `0x1800d0463`: `MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
ClientApiErrorTrace *__fastcall ClientApiErrorTrace::ClientApiErrorTrace(
        ClientApiErrorTrace *this,
        const char *a2,
        const void *a3,
        int a4,
        HINSTANCE a5)
{
  __int128 *v6; // rbx
  char v7; // si
  _QWORD *v8; // rdi
  _OWORD *v9; // rbx
  _OWORD *v10; // rax
  __int64 v11; // rbx
  unsigned __int64 v12; // r8
  DWORD CurrentThreadId; // r12d
  unsigned __int64 v14; // r15
  __int64 i; // rcx
  _QWORD *v16; // rcx
  __int128 **v17; // rcx
  __int128 *v18; // rax
  void *v19; // rbx
  HANDLE ProcessHeap; // rax
  _QWORD **v21; // rcx
  _QWORD *v22; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  char *v26; // rax
  signed __int64 v27; // rdx
  signed __int64 v28; // rax
  const struct wil::FailureInfo *v29; // rdx
  __int128 v30; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID lpMem[2]; // [rsp+40h] [rbp-C0h]
  __int128 v32; // [rsp+50h] [rbp-B0h] BYREF
  __int128 *v33; // [rsp+60h] [rbp-A0h]
  int v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  char v36; // [rsp+78h] [rbp-88h]
  char v37[16]; // [rsp+80h] [rbp-80h] BYREF
  LPVOID v38; // [rsp+90h] [rbp-70h]
  char v39; // [rsp+98h] [rbp-68h]
  _QWORD v40[3]; // [rsp+A0h] [rbp-60h] BYREF
  int v41; // [rsp+B8h] [rbp-48h]
  _BYTE v42[224]; // [rsp+D0h] [rbp-30h] BYREF
  void *retaddr; // [rsp+1B8h] [rbp+B8h]

  if ( a5 < g_hInstance || a5 > (HINSTANCE)((char *)g_hInstance + g_ModuleSize) )
  {
    v6 = (__int128 *)UiaImportantTraceLoggingProvider::WatchCurrentThread(v37, a2, "object=%p, parameter=%d", a3, a4);
    v7 = 1;
  }
  else
  {
    v30 = 0;
    *(_OWORD *)lpMem = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    v36 = 0;
    v6 = &v30;
    v7 = 2;
  }
  *(_OWORD *)this = 0;
  *((_OWORD *)this + 1) = 0;
  *(_DWORD *)this = *(_DWORD *)v6;
  *((_QWORD *)this + 1) = *((_QWORD *)v6 + 1);
  *((_QWORD *)this + 2) = *((_QWORD *)v6 + 2);
  *((_QWORD *)v6 + 2) = 0;
  *((_BYTE *)this + 24) = *((_BYTE *)v6 + 24);
  *((_BYTE *)v6 + 24) = 0;
  v8 = (_QWORD *)((char *)this + 32);
  v9 = v6 + 2;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = *((_QWORD *)v9 + 1);
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 14) = 0;
  *((_QWORD *)this + 8) = *((_QWORD *)v9 + 4);
  *((_BYTE *)this + 72) = 0;
  if ( *((_DWORD *)v9 + 6) )
  {
    if ( *((_DWORD *)v9 + 6) != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
      wil::details::g_pfnReportFatalUsageError(
        "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
        retaddr);
    *((_DWORD *)v9 + 6) = 0;
    while ( 1 )
    {
      v10 = **(_OWORD ***)v9;
      if ( !v10 )
        break;
      if ( v10 == v9 )
      {
        **(_QWORD **)v9 = *((_QWORD *)v9 + 2);
        break;
      }
      *(_QWORD *)v9 = v10 + 1;
    }
    *(_QWORD *)v9 = 0;
    if ( *((_DWORD *)this + 14) )
    {
      memset_0(v42, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v42, v29);
    }
    v11 = wil::details::g_pThreadFailureCallbacks;
    if ( wil::details::g_pThreadFailureCallbacks )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = ((unsigned __int64)CurrentThreadId >> 2) % 0xA;
      for ( i = *(_QWORD *)(v11 + 8 * v14); i; i = *(_QWORD *)(i + 8) )
      {
        if ( *(_DWORD *)i == CurrentThreadId )
        {
          v16 = (_QWORD *)(i + 16);
          goto LABEL_17;
        }
      }
      v26 = (char *)wil::details::ProcessHeapAlloc(0, 0x18u, v12);
      v27 = (signed __int64)v26;
      if ( v26 )
      {
        *(_DWORD *)v26 = CurrentThreadId;
        *((_DWORD *)v26 + 1) = 0;
        *((_QWORD *)v26 + 1) = 0;
        v16 = v26 + 16;
        *((_QWORD *)v26 + 2) = 0;
        do
        {
          v28 = *(_QWORD *)(v11 + 8 * v14);
          *(_QWORD *)(v27 + 8) = v28;
        }
        while ( v28 != _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 8 * v14), v27, v28) );
      }
      else
      {
        v16 = 0;
      }
LABEL_17:
      *v8 = v16;
      if ( v16 )
      {
        *((_QWORD *)this + 6) = *v16;
        *v16 = v8;
        *((_DWORD *)this + 14) = GetCurrentThreadId();
      }
    }
    else
    {
      *v8 = 0;
    }
  }
  *((_QWORD *)this + 8) = this;
  if ( (v7 & 2) != 0 )
  {
    v7 &= ~2u;
    if ( v34 )
    {
      if ( v34 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v34 = 0;
      v17 = (__int128 **)v32;
      while ( 1 )
      {
        v18 = *v17;
        if ( !*v17 )
          break;
        if ( v18 == &v32 )
        {
          *v17 = v33;
          break;
        }
        v17 = (__int128 **)(v18 + 1);
        *(_QWORD *)&v32 = v18 + 1;
      }
      *(_QWORD *)&v32 = 0;
    }
    if ( LOBYTE(lpMem[1]) )
    {
      v19 = lpMem[0];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v19);
      LOBYTE(lpMem[1]) = 0;
    }
    lpMem[0] = 0;
  }
  if ( (v7 & 1) != 0 )
  {
    if ( v41 )
    {
      if ( v41 != GetCurrentThreadId() && wil::details::g_pfnReportFatalUsageError )
        wil::details::g_pfnReportFatalUsageError(
          "MEMORY CORRUPTION: Calling code is leaking an activity thread-watcher and releasing it on another thread",
          retaddr);
      v41 = 0;
      v21 = (_QWORD **)v40[0];
      while ( 1 )
      {
        v22 = *v21;
        if ( !*v21 )
          break;
        if ( v22 == v40 )
        {
          *v21 = (_QWORD *)v40[2];
          break;
        }
        v21 = (_QWORD **)(v22 + 2);
        v40[0] = v22 + 2;
      }
      v40[0] = 0;
    }
    if ( v39 )
    {
      v23 = v38;
      v24 = GetProcessHeap();
      HeapFree(v24, 0, v23);
    }
  }
  return this;
}

```

## disassembly

```asm
0x1800d00d4  push    rbp
0x1800d00d6  push    rbx
0x1800d00d7  push    rsi
0x1800d00d8  push    rdi
0x1800d00d9  push    r12
0x1800d00db  push    r13
0x1800d00dd  push    r14
0x1800d00df  push    r15
0x1800d00e1  lea     rbp, [rsp-78h]
0x1800d00e6  sub     rsp, 178h
0x1800d00ed  mov     r14, rcx
0x1800d00f0  xor     r13d, r13d
0x1800d00f3  mov     [rbp+0B0h+arg_0], r13d
0x1800d00fa  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800d0101  cmp     [rbp+0B0h+arg_20], rcx
0x1800d0108  jb      loc_1800D0355
0x1800d010e  mov     eax, cs:?g_ModuleSize@@3KA; ulong g_ModuleSize
0x1800d0114  add     rax, rcx
0x1800d0117  cmp     [rbp+0B0h+arg_20], rax
0x1800d011e  ja      loc_1800D0355
0x1800d0124  xorps   xmm0, xmm0
0x1800d0127  movups  [rsp+1B0h+var_180], xmm0
0x1800d012c  movups  xmmword ptr [rsp+1B0h+lpMem], xmm0
0x1800d0131  movdqu  [rsp+1B0h+var_160], xmm0
0x1800d0137  mov     [rsp+1B0h+var_150], r13
0x1800d013c  mov     [rsp+1B0h+var_148], r13d
0x1800d0141  mov     [rsp+1B0h+var_140], r13
0x1800d0146  mov     [rsp+1B0h+var_138], r13b
0x1800d014b  lea     rbx, [rsp+1B0h+var_180]
0x1800d0150  lea     esi, [r13+2]
0x1800d0154  xorps   xmm0, xmm0
0x1800d0157  movups  xmmword ptr [r14], xmm0
0x1800d015b  movups  xmmword ptr [r14+10h], xmm0
0x1800d0160  mov     ecx, [rbx]
0x1800d0162  mov     [r14], ecx
0x1800d0165  mov     rcx, [rbx+8]
0x1800d0169  mov     [r14+8], rcx
0x1800d016d  mov     rcx, [rbx+10h]
0x1800d0171  mov     [r14+10h], rcx
0x1800d0175  mov     [rbx+10h], r13
0x1800d0179  mov     al, [rbx+18h]
0x1800d017c  mov     [r14+18h], al
0x1800d0180  mov     [rbx+18h], r13b
0x1800d0184  lea     rdi, [r14+20h]
0x1800d0188  add     rbx, 20h ; ' '
0x1800d018c  mov     [rdi], r13
0x1800d018f  mov     rax, [rbx+8]
0x1800d0193  mov     [rdi+8], rax
0x1800d0197  mov     [rdi+10h], r13
0x1800d019b  mov     [rdi+18h], r13d
0x1800d019f  mov     rax, [rbx+20h]
0x1800d01a3  mov     [rdi+20h], rax
0x1800d01a7  mov     [rdi+28h], r13b
0x1800d01ab  cmp     [rbx+18h], r13d
0x1800d01af  jz      loc_1800D0262
0x1800d01b5  call    cs:__imp_GetCurrentThreadId
0x1800d01bb  cmp     [rbx+18h], eax
0x1800d01be  jnz     loc_1800D03C7
0x1800d01c4  mov     [rbx+18h], r13d
0x1800d01c8  mov     rcx, [rbx]
0x1800d01cb  mov     rax, [rcx]
0x1800d01ce  test    rax, rax
0x1800d01d1  jz      short loc_1800D01E3
0x1800d01d3  cmp     rax, rbx
0x1800d01d6  jnz     loc_1800D03EF
0x1800d01dc  mov     rax, [rbx+10h]
0x1800d01e0  mov     [rcx], rax
0x1800d01e3  mov     [rbx], r13
0x1800d01e6  cmp     [rdi+18h], r13d
0x1800d01ea  jnz     loc_1800D03FB
0x1800d01f0  mov     rbx, cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x1800d01f7  test    rbx, rbx
0x1800d01fa  jz      loc_1800D037A
0x1800d0200  call    cs:__imp_GetCurrentThreadId
0x1800d0206  mov     r12d, eax
0x1800d0209  mov     r15d, eax
0x1800d020c  shr     r15, 2
0x1800d0210  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800d021a  mul     r15
0x1800d021d  shr     rdx, 3
0x1800d0221  lea     rcx, [rdx+rdx*4]
0x1800d0225  add     rcx, rcx
0x1800d0228  sub     r15, rcx
0x1800d022b  mov     rcx, [rbx+r15*8]
0x1800d022f  test    rcx, rcx
0x1800d0232  jz      loc_1800D0382
0x1800d0238  cmp     [rcx], r12d
0x1800d023b  jz      short loc_1800D0243
0x1800d023d  mov     rcx, [rcx+8]
0x1800d0241  jmp     short loc_1800D022F
0x1800d0243  add     rcx, 10h
0x1800d0247  mov     [rdi], rcx
0x1800d024a  test    rcx, rcx
0x1800d024d  jz      short loc_1800D0262
0x1800d024f  mov     rax, [rcx]
0x1800d0252  mov     [rdi+10h], rax
0x1800d0256  mov     [rcx], rdi
0x1800d0259  call    cs:__imp_GetCurrentThreadId
0x1800d025f  mov     [rdi+18h], eax
0x1800d0262  mov     [r14+40h], r14
0x1800d0266  test    sil, 2
0x1800d026a  jz      short loc_1800D02DD
0x1800d026c  and     esi, 0FFFFFFFDh
0x1800d026f  cmp     [rsp+1B0h+var_148], r13d
0x1800d0274  jz      short loc_1800D02B3
0x1800d0276  call    cs:__imp_GetCurrentThreadId
0x1800d027c  cmp     [rsp+1B0h+var_148], eax
0x1800d0280  jnz     loc_1800D0416
0x1800d0286  mov     [rsp+1B0h+var_148], r13d
0x1800d028b  mov     rcx, qword ptr [rsp+1B0h+var_160]
0x1800d0290  mov     rax, [rcx]
0x1800d0293  test    rax, rax
0x1800d0296  jz      short loc_1800D02AE
0x1800d0298  lea     rdx, [rsp+1B0h+var_160]
0x1800d029d  cmp     rax, rdx
0x1800d02a0  jnz     loc_1800D043E
0x1800d02a6  mov     rax, [rsp+1B0h+var_150]
0x1800d02ab  mov     [rcx], rax
0x1800d02ae  mov     qword ptr [rsp+1B0h+var_160], r13
0x1800d02b3  cmp     byte ptr [rsp+1B0h+lpMem+8], r13b
0x1800d02b8  jz      short loc_1800D02D8
0x1800d02ba  mov     rbx, [rsp+1B0h+lpMem]
0x1800d02bf  call    cs:__imp_GetProcessHeap
0x1800d02c5  mov     r8, rbx; lpMem
0x1800d02c8  xor     edx, edx; dwFlags
0x1800d02ca  mov     rcx, rax; hHeap
0x1800d02cd  call    cs:__imp_HeapFree
0x1800d02d3  mov     byte ptr [rsp+1B0h+lpMem+8], r13b
0x1800d02d8  mov     [rsp+1B0h+lpMem], r13
0x1800d02dd  test    sil, 1
0x1800d02e1  jz      short loc_1800D033E
0x1800d02e3  cmp     [rbp+0B0h+var_F8], r13d
0x1800d02e7  jz      short loc_1800D0320
0x1800d02e9  call    cs:__imp_GetCurrentThreadId
0x1800d02ef  cmp     [rbp+0B0h+var_F8], eax
0x1800d02f2  jnz     loc_1800D044C
0x1800d02f8  mov     [rbp+0B0h+var_F8], r13d
0x1800d02fc  mov     rcx, [rbp+0B0h+var_110]
0x1800d0300  mov     rax, [rcx]
0x1800d0303  test    rax, rax
0x1800d0306  jz      short loc_1800D031C
0x1800d0308  lea     rdx, [rbp+0B0h+var_110]
0x1800d030c  cmp     rax, rdx
0x1800d030f  jnz     loc_1800D0474
0x1800d0315  mov     rax, [rbp+0B0h+var_100]
0x1800d0319  mov     [rcx], rax
0x1800d031c  mov     [rbp+0B0h+var_110], r13
0x1800d0320  cmp     [rbp+0B0h+var_118], r13b
0x1800d0324  jz      short loc_1800D033E
0x1800d0326  mov     rbx, [rbp+0B0h+var_120]
0x1800d032a  call    cs:__imp_GetProcessHeap
0x1800d0330  mov     r8, rbx; lpMem
0x1800d0333  xor     edx, edx; dwFlags
0x1800d0335  mov     rcx, rax; hHeap
0x1800d0338  call    cs:__imp_HeapFree
0x1800d033e  mov     rax, r14
0x1800d0341  add     rsp, 178h
0x1800d0348  pop     r15
0x1800d034a  pop     r14
0x1800d034c  pop     r13
0x1800d034e  pop     r12
0x1800d0350  pop     rdi
0x1800d0351  pop     rsi
0x1800d0352  pop     rbx
0x1800d0353  pop     rbp
0x1800d0354  retn
0x1800d0355  mov     [rsp+1B0h+var_190], r9d
0x1800d035a  mov     r9, r8
0x1800d035d  lea     r8, aObjectPParamet; "object=%p, parameter=%d"
0x1800d0364  lea     rcx, [rbp+0B0h+var_130]
0x1800d0368  call    ?WatchCurrentThread@UiaImportantTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; UiaImportantTraceLoggingProvider::WatchCurrentThread(char const *,char const *,...)
0x1800d036d  mov     rbx, rax
0x1800d0370  mov     esi, 1
0x1800d0375  jmp     loc_1800D0154
0x1800d037a  mov     [rdi], r13
0x1800d037d  jmp     loc_1800D0262
0x1800d0382  mov     edx, 18h; dwBytes
0x1800d0387  xor     ecx, ecx; dwFlags
0x1800d0389  call    ?ProcessHeapAlloc@details@wil@@YAPEAXK_K@Z; wil::details::ProcessHeapAlloc(ulong,unsigned __int64)
0x1800d038e  mov     rdx, rax
0x1800d0391  test    rax, rax
0x1800d0394  jz      short loc_1800D03BF
0x1800d0396  mov     [rax], r12d
0x1800d0399  xor     eax, eax
0x1800d039b  mov     [rdx+4], eax
0x1800d039e  mov     [rdx+8], r13
0x1800d03a2  lea     rcx, [rdx+10h]
0x1800d03a6  mov     [rcx], r13
0x1800d03a9  mov     rax, [rbx+r15*8]
0x1800d03ad  mov     [rdx+8], rax
0x1800d03b1  lock cmpxchg [rbx+r15*8], rdx
0x1800d03b7  jz      loc_1800D0247
0x1800d03bd  jmp     short loc_1800D03A9
0x1800d03bf  mov     rcx, r13
0x1800d03c2  jmp     loc_1800D0247
0x1800d03c7  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800d03ce  test    rax, rax
0x1800d03d1  jz      loc_1800D01C4
0x1800d03d7  mov     rdx, [rbp+0B8h]
0x1800d03de  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800d03e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d03ea  jmp     loc_1800D01C4
0x1800d03ef  add     rax, 10h
0x1800d03f3  mov     [rbx], rax
0x1800d03f6  jmp     loc_1800D01C8
0x1800d03fb  xor     edx, edx; Val
0x1800d03fd  mov     r8d, 98h; Size
0x1800d0403  lea     rcx, [rbp+0B0h+var_E0]; void *
0x1800d0407  call    memset_0
0x1800d040c  lea     rcx, [rbp+0B0h+var_E0]; this
0x1800d0410  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800d0416  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800d041d  test    rax, rax
0x1800d0420  jz      loc_1800D0286
0x1800d0426  mov     rdx, [rbp+0B8h]
0x1800d042d  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800d0434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d0439  jmp     loc_1800D0286
0x1800d043e  lea     rcx, [rax+10h]
0x1800d0442  mov     qword ptr [rsp+1B0h+var_160], rcx
0x1800d0447  jmp     loc_1800D0290
0x1800d044c  mov     rax, cs:?g_pfnReportFatalUsageError@details@wil@@3P6AXPEBDPEBX@_EEA
0x1800d0453  test    rax, rax
0x1800d0456  jz      loc_1800D02F8
0x1800d045c  mov     rdx, [rbp+0B8h]
0x1800d0463  lea     rcx, aMemoryCorrupti; "MEMORY CORRUPTION: Calling code is leak"...
0x1800d046a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d046f  jmp     loc_1800D02F8
0x1800d0474  lea     rcx, [rax+10h]
0x1800d0478  mov     [rbp+0B0h+var_110], rcx
0x1800d047c  jmp     loc_1800D0300
```
