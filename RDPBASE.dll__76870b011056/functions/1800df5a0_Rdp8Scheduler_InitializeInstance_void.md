# Rdp8Scheduler::InitializeInstance(void)

- ea: `0x1800df5a0`
- end: `0x1800df848`
- name: `?InitializeInstance@Rdp8Scheduler@@UEAAJXZ`
- size: `680`
- prototype: `__int64 __fastcall(Rdp8Scheduler *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800018a4`
- `0x1800df5a0`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800df76b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800df76b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800df74b`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1800df74b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800df5d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x1800df5d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df7bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800df7bf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800df5eb`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800df5eb`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800df79b`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!SetThreadAffinityMask` at `0x1800df79b`
- `OLEAUT32!__imp_VariantInit` at `0x1800df62b`
- `OLEAUT32!__imp_VariantInit` at `0x1800df67c`
- `OLEAUT32!__imp_VariantInit` at `0x1800df6c5`
- `OLEAUT32!__imp_VariantInit` at `0x1800df62b`
- `OLEAUT32!__imp_VariantInit` at `0x1800df67c`
- `OLEAUT32!__imp_VariantInit` at `0x1800df6c5`
- `OLEAUT32!__imp_VariantClear` at `0x1800df672`
- `OLEAUT32!__imp_VariantClear` at `0x1800df6bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800df708`
- `OLEAUT32!__imp_VariantClear` at `0x1800df672`
- `OLEAUT32!__imp_VariantClear` at `0x1800df6bb`
- `OLEAUT32!__imp_VariantClear` at `0x1800df708`

## string_xrefs

- `0x1800df68d`: `Rdp8Scheduler::NormalSchedulerThreadPriority`
- `0x1800df63c`: `Rdp8Scheduler::NumberSchedulerThreads`
- `0x1800df6d6`: `CollabEnableRdpThreadsDpiAwareness`
- `0x1800df806`: `Failed to create thread`

## pseudocode

```c
__int64 __fastcall Rdp8Scheduler::InitializeInstance(Rdp8Scheduler *this)
{
  BOOL v2; // r15d
  void *v3; // rcx
  DWORD dwNumberOfProcessors; // esi
  int v5; // eax
  bool v6; // zf
  LONG lVal; // ecx
  unsigned int v8; // eax
  __int64 v9; // r14
  HANDLE Thread; // rax
  __int64 v11; // rbx
  unsigned int v12; // ebx
  signed int LastError; // eax
  int v15; // ecx
  int v16; // r8d
  int v17; // r9d
  const char *v18; // [rsp+50h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-21h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+70h] [rbp-9h] BYREF
  int v21; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v22; // [rsp+E8h] [rbp+6Fh] BYREF
  const char *v23; // [rsp+F0h] [rbp+77h] BYREF
  const char *v24; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 1;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  v3 = (void *)*((_QWORD *)this + 17);
  memset(&pvarg, 0, sizeof(pvarg));
  ResetEvent(v3);
  dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  *((_DWORD *)this + 230) = 0;
  if ( dwNumberOfProcessors )
  {
    v5 = 64;
    if ( dwNumberOfProcessors >= 0x40 )
      goto LABEL_5;
  }
  else
  {
    dwNumberOfProcessors = 1;
  }
  v5 = dwNumberOfProcessors;
LABEL_5:
  v6 = *((_QWORD *)this + 183) == 0;
  *((_DWORD *)this + 36) = v5;
  if ( !v6 )
  {
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 183) + 24LL))(
           *((_QWORD *)this + 183),
           L"Rdp8Scheduler::NumberSchedulerThreads",
           &pvarg) >= 0
      && pvarg.vt == 3 )
    {
      lVal = pvarg.lVal;
      if ( *((_DWORD *)this + 36) < pvarg.lVal )
        lVal = *((_DWORD *)this + 36);
      *((_DWORD *)this + 36) = lVal;
    }
    VariantClear(&pvarg);
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 183) + 24LL))(
           *((_QWORD *)this + 183),
           L"Rdp8Scheduler::NormalSchedulerThreadPriority",
           &pvarg) >= 0
      && pvarg.vt == 11 )
    {
      v2 = pvarg.iVal != -1;
    }
    VariantClear(&pvarg);
    VariantInit(&pvarg);
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 183) + 24LL))(
           *((_QWORD *)this + 183),
           L"CollabEnableRdpThreadsDpiAwareness",
           &pvarg) >= 0
      && pvarg.vt == 11 )
    {
      *((_DWORD *)this + 231) = pvarg.iVal == -1;
    }
    VariantClear(&pvarg);
  }
  v8 = *((_DWORD *)this + 36);
  v9 = 0;
  *((_DWORD *)this + 37) = 0;
  if ( v8 )
  {
    while ( 1 )
    {
      Thread = CreateThread(0, 0, Rdp8Scheduler::STATIC_RunThreadProc, this, 0x60u, (LPDWORD)this + v9 + 166);
      *((_QWORD *)this + v9 + 19) = Thread;
      if ( !Thread )
        break;
      if ( v2 )
        SetThreadPriority(Thread, 15);
      v8 = *((_DWORD *)this + 36);
      v9 = (unsigned int)(v9 + 1);
      if ( (unsigned int)v9 >= v8 )
        goto LABEL_23;
    }
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)CallbackContext > 2 )
    {
      v21 = 738;
      v23 = "InitializeInstance";
      v22 = v12;
      v24 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdp8scheduler.cpp";
      v18 = "Failed to create thread";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v15,
        (unsigned int)byte_1801BCD69,
        v16,
        v17,
        (__int64)&v18,
        (__int64)&v22,
        (__int64)&v24,
        (__int64)&v21,
        (__int64)&v23);
    }
  }
  else
  {
LABEL_23:
    if ( v8 == dwNumberOfProcessors )
    {
      v11 = 0;
      if ( v8 )
      {
        do
        {
          SetThreadAffinityMask(*((HANDLE *)this + v11 + 19), 1LL << v11);
          v11 = (unsigned int)(v11 + 1);
        }
        while ( (unsigned int)v11 < *((_DWORD *)this + 36) );
      }
    }
    return 0;
  }
  return v12;
}

```

## disassembly

```asm
0x1800df5a0  push    rbp
0x1800df5a2  push    rbx
0x1800df5a3  push    rsi
0x1800df5a4  push    rdi
0x1800df5a5  push    r14
0x1800df5a7  push    r15
0x1800df5a9  lea     rbp, [rsp-2Fh]
0x1800df5ae  sub     rsp, 0A8h
0x1800df5b5  xorps   xmm0, xmm0
0x1800df5b8  mov     rdi, rcx
0x1800df5bb  lea     rcx, [rbp+57h+SystemInfo]; lpSystemInfo
0x1800df5bf  mov     r15d, 1
0x1800df5c5  movups  xmmword ptr [rbp+57h+SystemInfo], xmm0
0x1800df5c9  movups  xmmword ptr [rbp+57h+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1800df5cd  movups  xmmword ptr [rbp+57h+SystemInfo.dwNumberOfProcessors], xmm0
0x1800df5d1  call    cs:__imp_GetSystemInfo
0x1800df5d7  mov     rcx, [rdi+88h]; hEvent
0x1800df5de  xorps   xmm0, xmm0
0x1800df5e1  xor     eax, eax
0x1800df5e3  movups  xmmword ptr [rbp+57h+pvarg], xmm0
0x1800df5e7  mov     qword ptr [rbp+57h+pvarg+10h], rax
0x1800df5eb  call    cs:__imp_ResetEvent
0x1800df5f1  mov     esi, [rbp+57h+SystemInfo.dwNumberOfProcessors]
0x1800df5f4  mov     dword ptr [rdi+398h], 0
0x1800df5fe  cmp     esi, r15d
0x1800df601  jnb     short loc_1800DF608
0x1800df603  mov     esi, r15d
0x1800df606  jmp     short loc_1800DF611
0x1800df608  mov     eax, 40h ; '@'
0x1800df60d  cmp     esi, eax
0x1800df60f  jnb     short loc_1800DF613
0x1800df611  mov     eax, esi
0x1800df613  cmp     qword ptr [rdi+5B8h], 0
0x1800df61b  mov     [rdi+90h], eax
0x1800df621  jz      loc_1800DF70E
0x1800df627  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df62b  call    cs:__imp_VariantInit
0x1800df631  mov     rcx, [rdi+5B8h]
0x1800df638  lea     r8, [rbp+57h+pvarg]
0x1800df63c  lea     rdx, aRdp8schedulerN_0; "Rdp8Scheduler::NumberSchedulerThreads"
0x1800df643  mov     rax, [rcx]
0x1800df646  mov     rax, [rax+18h]
0x1800df64a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df64f  test    eax, eax
0x1800df651  js      short loc_1800DF66E
0x1800df653  cmp     word ptr [rbp+57h+pvarg], 3
0x1800df658  jnz     short loc_1800DF66E
0x1800df65a  mov     eax, [rdi+90h]
0x1800df660  mov     ecx, dword ptr [rbp+57h+pvarg+8]
0x1800df663  cmp     eax, ecx
0x1800df665  cmovb   ecx, eax
0x1800df668  mov     [rdi+90h], ecx
0x1800df66e  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df672  call    cs:__imp_VariantClear
0x1800df678  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df67c  call    cs:__imp_VariantInit
0x1800df682  mov     rcx, [rdi+5B8h]
0x1800df689  lea     r8, [rbp+57h+pvarg]
0x1800df68d  lea     rdx, aRdp8schedulerN; "Rdp8Scheduler::NormalSchedulerThreadPri"...
0x1800df694  mov     rax, [rcx]
0x1800df697  mov     rax, [rax+18h]
0x1800df69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6a0  test    eax, eax
0x1800df6a2  js      short loc_1800DF6B7
0x1800df6a4  cmp     word ptr [rbp+57h+pvarg], 0Bh
0x1800df6a9  jnz     short loc_1800DF6B7
0x1800df6ab  xor     r15d, r15d
0x1800df6ae  cmp     word ptr [rbp+57h+pvarg+8], 0FFFFh
0x1800df6b3  setnz   r15b
0x1800df6b7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df6bb  call    cs:__imp_VariantClear
0x1800df6c1  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df6c5  call    cs:__imp_VariantInit
0x1800df6cb  mov     rcx, [rdi+5B8h]
0x1800df6d2  lea     r8, [rbp+57h+pvarg]
0x1800df6d6  lea     rdx, aCollabenablerd; "CollabEnableRdpThreadsDpiAwareness"
0x1800df6dd  mov     rax, [rcx]
0x1800df6e0  mov     rax, [rax+18h]
0x1800df6e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800df6e9  test    eax, eax
0x1800df6eb  js      short loc_1800DF704
0x1800df6ed  cmp     word ptr [rbp+57h+pvarg], 0Bh
0x1800df6f2  jnz     short loc_1800DF704
0x1800df6f4  xor     eax, eax
0x1800df6f6  cmp     word ptr [rbp+57h+pvarg+8], 0FFFFh
0x1800df6fb  setz    al
0x1800df6fe  mov     [rdi+39Ch], eax
0x1800df704  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800df708  call    cs:__imp_VariantClear
0x1800df70e  mov     eax, [rdi+90h]
0x1800df714  xor     r14d, r14d
0x1800df717  mov     dword ptr [rdi+94h], 0
0x1800df721  test    eax, eax
0x1800df723  jz      short loc_1800DF77F
0x1800df725  lea     rax, [rdi+298h]
0x1800df72c  mov     r9, rdi; lpParameter
0x1800df72f  lea     rax, [rax+r14*4]
0x1800df733  xor     edx, edx; dwStackSize
0x1800df735  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x1800df73a  lea     r8, ?STATIC_RunThreadProc@Rdp8Scheduler@@CAKPEAX@Z; lpStartAddress
0x1800df741  xor     ecx, ecx; lpThreadAttributes
0x1800df743  mov     [rsp+0D0h+dwCreationFlags], 60h ; '`'; dwCreationFlags
0x1800df74b  call    cs:__imp_CreateThread
0x1800df751  mov     [rdi+r14*8+98h], rax
0x1800df759  test    rax, rax
0x1800df75c  jz      short loc_1800DF7BF
0x1800df75e  test    r15d, r15d
0x1800df761  jz      short loc_1800DF771
0x1800df763  mov     edx, 0Fh; nPriority
0x1800df768  mov     rcx, rax; hThread
0x1800df76b  call    cs:__imp_SetThreadPriority
0x1800df771  mov     eax, [rdi+90h]
0x1800df777  inc     r14d
0x1800df77a  cmp     r14d, eax
0x1800df77d  jb      short loc_1800DF725
0x1800df77f  cmp     eax, esi
0x1800df781  jnz     short loc_1800DF7AB
0x1800df783  xor     ebx, ebx
0x1800df785  test    eax, eax
0x1800df787  jz      short loc_1800DF7AB
0x1800df789  mov     ecx, ebx
0x1800df78b  mov     edx, 1
0x1800df790  shl     rdx, cl; dwThreadAffinityMask
0x1800df793  mov     rcx, [rdi+rbx*8+98h]; hThread
0x1800df79b  call    cs:__imp_SetThreadAffinityMask
0x1800df7a1  inc     ebx
0x1800df7a3  cmp     ebx, [rdi+90h]
0x1800df7a9  jb      short loc_1800DF789
0x1800df7ab  xor     ebx, ebx
0x1800df7ad  mov     eax, ebx
0x1800df7af  add     rsp, 0A8h
0x1800df7b6  pop     r15
0x1800df7b8  pop     r14
0x1800df7ba  pop     rdi
0x1800df7bb  pop     rsi
0x1800df7bc  pop     rbx
0x1800df7bd  pop     rbp
0x1800df7be  retn
0x1800df7bf  call    cs:__imp_GetLastError
0x1800df7c5  mov     ebx, eax
0x1800df7c7  test    eax, eax
0x1800df7c9  jle     short loc_1800DF7D4
0x1800df7cb  movzx   ebx, ax
0x1800df7ce  or      ebx, 80070000h
0x1800df7d4  mov     eax, cs:CallbackContext
0x1800df7da  cmp     eax, 2
0x1800df7dd  jbe     short loc_1800DF7AD
0x1800df7df  lea     rax, aInitializeinst_1; "InitializeInstance"
0x1800df7e6  mov     [rbp+57h+arg_0], 2E2h
0x1800df7ed  mov     [rbp+57h+arg_10], rax
0x1800df7f1  lea     rdx, byte_1801BCD69
0x1800df7f8  lea     rax, aOnecoreTermsrv_82; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800df7ff  mov     [rbp+57h+arg_8], ebx
0x1800df802  mov     [rbp+57h+arg_18], rax
0x1800df806  lea     rax, aFailedToCreate_27; "Failed to create thread"
0x1800df80d  mov     [rbp+57h+var_80], rax
0x1800df811  lea     rax, [rbp+57h+arg_10]
0x1800df815  mov     [rsp+0D0h+var_90], rax
0x1800df81a  lea     rax, [rbp+57h+arg_0]
0x1800df81e  mov     [rsp+0D0h+var_98], rax
0x1800df823  lea     rax, [rbp+57h+arg_18]
0x1800df827  mov     [rsp+0D0h+var_A0], rax
0x1800df82c  lea     rax, [rbp+57h+arg_8]
0x1800df830  mov     [rsp+0D0h+lpThreadId], rax
0x1800df835  lea     rax, [rbp+57h+var_80]
0x1800df839  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax
0x1800df83e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800df843  jmp     loc_1800DF7AD
```
