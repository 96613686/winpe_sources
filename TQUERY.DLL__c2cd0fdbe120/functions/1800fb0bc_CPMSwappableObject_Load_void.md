# CPMSwappableObject::Load(void)

- ea: `0x1800fb0bc`
- end: `0x1800fb2f0`
- name: `?Load@CPMSwappableObject@@QEAAJXZ`
- size: `564`
- prototype: `__int64 __fastcall(CPMSwappableObject *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x180204b40`

## callees

- `0x180038f08`
- `0x180068af4`
- `0x180068b14`
- `0x1800699a0`
- `0x1800763b4`
- `0x180078410`
- `0x1800eb364`
- `0x1800fb0bc`
- `0x1800fb2f8`
- `0x1801480fc`
- `0x1801590bc`
- `0x18017315c`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb1dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb1f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb299`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb1dc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb1f5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800fb299`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb2cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb227`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb2c2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fb2cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fb1e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fb1e5`

## string_xrefs

- `0x1800fb133`: `[PerfCounter] pmo::Load() failed because object is already loaded`
- `0x1800fb1a6`: `[PerfCounter] spo::Load() failed because CreateInstance() failed`

## pseudocode

```c
__int64 __fastcall CPMSwappableObject::Load(CPMSwappableObject *this, __int64 a2, __int64 a3, const wchar_t *a4)
{
  _DWORD *v4; // r14
  __int64 v6; // rdx
  unsigned int v7; // ebx
  unsigned int v9; // ebx
  __int64 (__fastcall *v10)(_DWORD *, __int64, _QWORD); // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  const wchar_t *v13; // r9
  unsigned int v14; // r12d
  volatile signed __int32 *v15; // rbx
  int v16; // r14d
  CEventSem *v17; // rbp
  volatile __int32 *DwordCounter; // r10
  __int64 v19; // r11
  unsigned int *v20; // rax
  int v21[24]; // [rsp+20h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v4 = (_DWORD *)*((_QWORD *)this + 20);
  if ( !v4[70] )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\pmswap.cxx\"",
      (const wchar_t *)0x7C,
      (unsigned int)L"[PerfCounter] pmo::Load() failed because library did not init OK",
      a4);
    v6 = 125;
    v7 = -2147207627;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\pmswap.cxx",
      (const char *)v7,
      v21[0]);
    return v7;
  }
  if ( *((_QWORD *)this + 18) )
  {
    SearchIndexerTrace::Error(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\pmswap.cxx\"",
      (const wchar_t *)0x81,
      (unsigned int)L"[PerfCounter] pmo::Load() failed because object is already loaded",
      a4);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\pmswap.cxx",
      (const char *)0x8000FFFFLL,
      v21[0]);
  }
  v9 = *((_DWORD *)this + 42);
  v10 = *(__int64 (__fastcall **)(_DWORD *, __int64, _QWORD))(*(_QWORD *)v4 + 8LL);
  v11 = TLMString<32,32,1024>::TLMString<32,32,1024>(v21, (char *)this + 176);
  v12 = v10(v4, v11, v9);
  *((_QWORD *)this + 18) = v12;
  if ( !v12 )
  {
    SearchIndexerTrace::Information(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\tquery\\\\fteutil\\\\pmswap.cxx\"",
      (const wchar_t *)0x8A,
      (unsigned int)L"[PerfCounter] spo::Load() failed because CreateInstance() failed",
      v13);
    v6 = 139;
    v7 = -2147207626;
    goto LABEL_3;
  }
  v14 = *((_DWORD *)this + 42);
  v15 = (volatile signed __int32 *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  _InterlockedIncrement((volatile signed __int32 *)this + 4);
  *((_DWORD *)this + 5) = GetCurrentThreadId();
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( *((_DWORD *)this + 6) )
  {
    CSyncReadWrite::LokInitWriteEvent((CPMSwappableObject *)((char *)this + 16));
    v17 = (CPMSwappableObject *)((char *)this + 136);
    CEventSem::Reset((CPMSwappableObject *)((char *)this + 136));
    v16 = 1;
  }
  else
  {
    v16 = 0;
    v17 = (CPMSwappableObject *)((char *)this + 136);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( v16 )
    CEventSem::Wait(v17, 0xFFFFFFFF, 0);
  if ( *((_DWORD *)this + 43) )
  {
    do
    {
      v14 += 2;
      DwordCounter = (volatile __int32 *)PerfObjectInstance::GetDwordCounter(*((PerfObjectInstance **)this + 18), v14);
      v20 = (unsigned int *)(*((_QWORD *)this + 19) + 4 * v19);
      _InterlockedExchange(DwordCounter, 0);
      _InterlockedExchange64((volatile __int64 *)this + 2 * (unsigned int)v19 + 35, (__int64)DwordCounter);
      _InterlockedAdd(DwordCounter, *v20);
    }
    while ( (unsigned int)(v19 + 1) < *((_DWORD *)this + 43) );
  }
  EnterCriticalSection((LPCRITICAL_SECTION)this + 2);
  if ( *v15 == 1 )
    *((_DWORD *)this + 5) = 0;
  _InterlockedDecrement(v15);
  CSyncReadWrite::LokInitReadEvent((CPMSwappableObject *)((char *)this + 16));
  CEventSem::Set((CPMSwappableObject *)((char *)this + 128));
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 2);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return 0;
}

```

## disassembly

```asm
0x1800fb0bc  mov     [rsp+arg_8], rbx
0x1800fb0c1  mov     [rsp+arg_10], rbp
0x1800fb0c6  push    rsi
0x1800fb0c7  push    rdi
0x1800fb0c8  push    r12
0x1800fb0ca  push    r14
0x1800fb0cc  push    r15
0x1800fb0ce  sub     rsp, 80h
0x1800fb0d5  mov     r14, [rcx+0A0h]
0x1800fb0dc  mov     rsi, rcx
0x1800fb0df  cmp     dword ptr [r14+118h], 0
0x1800fb0e7  jnz     short loc_1800FB129
0x1800fb0e9  lea     r8, aPerfcounterPmo; "[PerfCounter] pmo::Load() failed becaus"...
0x1800fb0f0  mov     edx, 7Ch ; '|'; wchar_t *
0x1800fb0f5  lea     rcx, aOnecoreuapBase_280; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800fb0fc  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800fb101  mov     edx, 7Dh ; '}'; void *
0x1800fb106  mov     ebx, 80043635h
0x1800fb10b  mov     rcx, [rsp+0A8h]; this
0x1800fb113  lea     r8, aOnecoreuapBase_224; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800fb11a  mov     r9d, ebx; char *
0x1800fb11d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb122  mov     eax, ebx
0x1800fb124  jmp     loc_1800FB2D4
0x1800fb129  cmp     qword ptr [rcx+90h], 0
0x1800fb131  jz      short loc_1800FB16B
0x1800fb133  lea     r8, aPerfcounterPmo_0; "[PerfCounter] pmo::Load() failed becaus"...
0x1800fb13a  mov     edx, 81h; wchar_t *
0x1800fb13f  lea     rcx, aOnecoreuapBase_280; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800fb146  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800fb14b  mov     rcx, [rsp+0A8h]; this
0x1800fb153  lea     r8, aOnecoreuapBase_224; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800fb15a  mov     r9d, 8000FFFFh; char *
0x1800fb160  mov     edx, 82h; void *
0x1800fb165  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fb16b  mov     rax, [r14]
0x1800fb16e  lea     rdx, [rcx+0B0h]
0x1800fb175  mov     ebx, [rcx+0A8h]
0x1800fb17b  lea     rcx, [rsp+0A8h+var_88]
0x1800fb180  mov     rdi, [rax+8]
0x1800fb184  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@AEBV0@@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(TLMString<32,32,1024> const &)
0x1800fb189  mov     rdx, rax
0x1800fb18c  mov     r8d, ebx
0x1800fb18f  mov     rax, rdi
0x1800fb192  mov     rcx, r14
0x1800fb195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fb19a  mov     [rsi+90h], rax
0x1800fb1a1  test    rax, rax
0x1800fb1a4  jnz     short loc_1800FB1CD
0x1800fb1a6  lea     r8, aPerfcounterSpo; "[PerfCounter] spo::Load() failed becaus"...
0x1800fb1ad  mov     edx, 8Ah; wchar_t *
0x1800fb1b2  lea     rcx, aOnecoreuapBase_280; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800fb1b9  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x1800fb1be  mov     edx, 8Bh
0x1800fb1c3  mov     ebx, 80043636h
0x1800fb1c8  jmp     loc_1800FB10B
0x1800fb1cd  mov     r12d, [rsi+0A8h]
0x1800fb1d4  lea     rbx, [rsi+10h]
0x1800fb1d8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800fb1dc  call    cs:__imp_EnterCriticalSection
0x1800fb1e2  lock inc dword ptr [rbx]
0x1800fb1e5  call    cs:__imp_GetCurrentThreadId
0x1800fb1eb  lea     rdi, [rbx+40h]
0x1800fb1ef  mov     [rbx+4], eax
0x1800fb1f2  mov     rcx, rdi; lpCriticalSection
0x1800fb1f5  call    cs:__imp_EnterCriticalSection
0x1800fb1fb  cmp     dword ptr [rbx+8], 0
0x1800fb1ff  jnz     short loc_1800FB20A
0x1800fb201  xor     r14d, r14d
0x1800fb204  lea     rbp, [rbx+78h]
0x1800fb208  jmp     short loc_1800FB224
0x1800fb20a  mov     rcx, rbx; this
0x1800fb20d  call    ?LokInitWriteEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitWriteEvent(void)
0x1800fb212  lea     rbp, [rbx+78h]
0x1800fb216  mov     rcx, rbp; this
0x1800fb219  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x1800fb21e  mov     r14d, 1
0x1800fb224  mov     rcx, rdi; lpCriticalSection
0x1800fb227  call    cs:__imp_LeaveCriticalSection
0x1800fb22d  test    r14d, r14d
0x1800fb230  jz      short loc_1800FB240
0x1800fb232  xor     r8d, r8d; int
0x1800fb235  or      edx, 0FFFFFFFFh; unsigned int
0x1800fb238  mov     rcx, rbp; this
0x1800fb23b  call    ?Wait@CEventSem@@QEAAKKH@Z; CEventSem::Wait(ulong,int)
0x1800fb240  xor     r11d, r11d
0x1800fb243  cmp     [rsi+0ACh], r11d
0x1800fb24a  jbe     short loc_1800FB296
0x1800fb24c  mov     rcx, [rsi+90h]; this
0x1800fb253  add     r12d, 2
0x1800fb257  mov     edx, r12d; unsigned int
0x1800fb25a  call    ?GetDwordCounter@PerfObjectInstance@@QEAAPEAKK@Z; PerfObjectInstance::GetDwordCounter(ulong)
0x1800fb25f  mov     rcx, [rsi+98h]
0x1800fb266  mov     r10, rax
0x1800fb269  mov     edx, r11d
0x1800fb26c  lea     rax, [rcx+r11*4]
0x1800fb270  xor     ecx, ecx
0x1800fb272  xchg    ecx, [r10]
0x1800fb275  shl     rdx, 4
0x1800fb279  mov     rcx, r10
0x1800fb27c  xchg    rcx, [rdx+rsi+118h]
0x1800fb284  mov     eax, [rax]
0x1800fb286  lock add [r10], eax
0x1800fb28a  inc     r11d
0x1800fb28d  cmp     r11d, [rsi+0ACh]
0x1800fb294  jb      short loc_1800FB24C
0x1800fb296  mov     rcx, rdi; lpCriticalSection
0x1800fb299  call    cs:__imp_EnterCriticalSection
0x1800fb29f  cmp     dword ptr [rbx], 1
0x1800fb2a2  jnz     short loc_1800FB2AB
0x1800fb2a4  mov     dword ptr [rbx+4], 0
0x1800fb2ab  lock dec dword ptr [rbx]
0x1800fb2ae  mov     rcx, rbx; this
0x1800fb2b1  call    ?LokInitReadEvent@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::LokInitReadEvent(void)
0x1800fb2b6  lea     rcx, [rbx+70h]; this
0x1800fb2ba  call    ?Set@CEventSem@@QEAAXXZ; CEventSem::Set(void)
0x1800fb2bf  mov     rcx, rdi; lpCriticalSection
0x1800fb2c2  call    cs:__imp_LeaveCriticalSection
0x1800fb2c8  lea     rcx, [rbx+10h]; lpCriticalSection
0x1800fb2cc  call    cs:__imp_LeaveCriticalSection
0x1800fb2d2  xor     eax, eax
0x1800fb2d4  lea     r11, [rsp+0A8h+var_28]
0x1800fb2dc  mov     rbx, [r11+38h]
0x1800fb2e0  mov     rbp, [r11+40h]
0x1800fb2e4  mov     rsp, r11
0x1800fb2e7  pop     r15
0x1800fb2e9  pop     r14
0x1800fb2eb  pop     r12
0x1800fb2ed  pop     rdi
0x1800fb2ee  pop     rsi
0x1800fb2ef  retn
```
