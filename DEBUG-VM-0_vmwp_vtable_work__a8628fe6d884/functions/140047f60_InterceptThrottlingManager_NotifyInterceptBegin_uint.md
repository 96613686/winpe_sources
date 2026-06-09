# InterceptThrottlingManager::NotifyInterceptBegin(uint)

- ea: `0x140047f60`
- end: `0x1400481c6`
- name: `?NotifyInterceptBegin@InterceptThrottlingManager@@QEAAXI@Z`
- size: `614`
- prototype: `void __fastcall(InterceptThrottlingManager *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140047f40`

## callees

- `0x1400014a4`
- `0x140047f60`
- `0x140057010`
- `0x1400570fc`
- `0x140132940`
- `0x140132c90`
- `0x1402c2010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140048150`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140048150`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14004809e`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14004809e`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140047fed`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140047fed`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140047faa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14004818a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140047faa`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14004818a`

## pseudocode

```c
void __fastcall InterceptThrottlingManager::NotifyInterceptBegin(InterceptThrottlingManager *this, unsigned int a2)
{
  __int64 v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // r8
  WINBOOL fPending; // [rsp+30h] [rbp-19h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp-11h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+40h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp+7h] BYREF
  __int16 *v10; // [rsp+60h] [rbp+17h]
  int v11; // [rsp+68h] [rbp+1Fh]
  int v12; // [rsp+6Ch] [rbp+23h]
  char *v13; // [rsp+70h] [rbp+27h]
  __int64 v14; // [rsp+78h] [rbp+2Fh]

  PerformanceCount.QuadPart = 0;
  v3 = *((_QWORD *)this + 15) + 80LL * a2;
  ++*(_QWORD *)(v3 + 24);
  *(_DWORD *)(v3 + 72) = 1;
  QueryPerformanceCounter(&PerformanceCount);
  if ( PerformanceCount.QuadPart - *((_QWORD *)this + 12) >= *((_QWORD *)this + 11) )
  {
    if ( !_interlockedbittestandset((volatile signed __int32 *)this + 6, 2u) )
    {
      *(_QWORD *)&Context.Id = 0;
      fPending = 0;
      if ( InitOnceBeginInitialize(&`VmWorkerInterceptTrace::Instance'::`2'::wrapper, 0, &fPending, (LPVOID *)&Context)
        && fPending )
      {
        qword_1403B7EC8 = 0;
        *(_QWORD *)&Context.Id = &qword_1403B7EC0;
        byte_1403B7ED0 = 0;
        dword_1403B7ED4 = 0;
        qword_1403B7EC0 = (__int64)&GuestStateFileTraceProvider::`vftable';
        CallbackContext = &`VmWorkerInterceptTrace::StaticHandle::StaticHandle'::`2'::__hInner;
        atexit(_lambda_c638a0893179ad876d752144997a212c_::_lambda_invoker_cdecl_);
        qword_1403B7EC8 = (__int64)CallbackContext;
        byte_1403B7ED0 = 1;
        TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
        dword_1403B7ED4 = 1;
        (*(void (__fastcall **)(__int64 *))(qword_1403B7EC0 + 8))(&qword_1403B7EC0);
        InitOnceComplete(&`VmWorkerInterceptTrace::Instance'::`2'::wrapper, 0, &qword_1403B7EC0);
      }
      v4 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
      if ( *(_DWORD *)v4 > 4u )
      {
        v14 = 16;
        v13 = (char *)this + 188;
        UserData.Ptr = *(_QWORD *)(v4 + 8);
        *(_QWORD *)&Context.Id = 0x40B000000LL;
        Context.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)UserData.Ptr;
        v10 = word_14035FCA2;
        UserData.Reserved = 2;
        v11 = 30;
        v12 = 1;
        fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(*(_QWORD *)(v4 + 32), &Context, 0, 0, 3u, &UserData);
      }
    }
    InterceptThrottlingManager::AdjustVpBalance(
      this,
      (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
      PerformanceCount.QuadPart);
    v5 = *(_QWORD *)(v3 + 16);
    if ( v5 < 0 )
    {
      InterceptThrottlingManager::DelayIntercept(
        this,
        (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
        -v5,
        PerformanceCount.QuadPart);
      QueryPerformanceCounter(&PerformanceCount);
      InterceptThrottlingManager::AdjustVpBalance(
        this,
        (struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *)v3,
        PerformanceCount.QuadPart);
    }
  }
}

```

## disassembly

```asm
0x140047f60  mov     [rsp-8+arg_18], rbx
0x140047f65  push    rbp
0x140047f66  push    rdi
0x140047f67  push    r14
0x140047f69  lea     rbp, [rsp-47h]
0x140047f6e  sub     rsp, 90h
0x140047f75  mov     rax, cs:__security_cookie
0x140047f7c  xor     rax, rsp
0x140047f7f  mov     [rbp+57h+var_20], rax
0x140047f83  mov     eax, edx
0x140047f85  mov     rbx, rcx
0x140047f88  xor     r14d, r14d
0x140047f8b  mov     qword ptr [rbp+57h+PerformanceCount], r14
0x140047f8f  lea     rdi, [rax+rax*4]
0x140047f93  shl     rdi, 4
0x140047f97  add     rdi, [rcx+78h]
0x140047f9b  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x140047f9f  inc     qword ptr [rdi+18h]
0x140047fa3  mov     dword ptr [rdi+48h], 1
0x140047faa  call    cs:__imp_QueryPerformanceCounter
0x140047fb1  nop     dword ptr [rax+rax+00h]
0x140047fb6  mov     rax, qword ptr [rbp+57h+PerformanceCount]
0x140047fba  sub     rax, [rbx+60h]
0x140047fbe  cmp     rax, [rbx+58h]
0x140047fc2  jl      loc_1400481A5
0x140047fc8  lock bts dword ptr [rbx+18h], 2
0x140047fce  jb      loc_14004815C
0x140047fd4  lea     r9, [rbp+57h+Context]; lpContext
0x140047fd8  mov     [rbp+57h+Context], r14
0x140047fdc  lea     r8, [rbp+57h+fPending]; fPending
0x140047fe0  mov     [rbp+57h+fPending], r14d
0x140047fe4  xor     edx, edx; dwFlags
0x140047fe6  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x140047fed  call    cs:__imp_InitOnceBeginInitialize
0x140047ff4  nop     dword ptr [rax+rax+00h]
0x140047ff9  test    eax, eax
0x140047ffb  jz      loc_1400480B2
0x140048001  cmp     [rbp+57h+fPending], r14d
0x140048005  jz      loc_1400480B2
0x14004800b  mov     [rsp+0A0h+arg_10], rsi
0x140048013  lea     rax, ??_7GuestStateFileTraceProvider@@6B@; const GuestStateFileTraceProvider::`vftable'
0x14004801a  lea     rsi, qword_1403B7EC0
0x140048021  mov     cs:qword_1403B7EC8, r14
0x140048028  mov     [rbp+57h+Context], rsi
0x14004802c  mov     cs:byte_1403B7ED0, r14b
0x140048033  mov     cs:dword_1403B7ED4, r14d
0x14004803a  mov     cs:qword_1403B7EC0, rax
0x140048041  lea     rax, ?__hInner@?1???0StaticHandle@VmWorkerInterceptTrace@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `VmWorkerInterceptTrace::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140048048  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_c638a0893179ad876d752144997a212c_@@CA@XZ; void (__cdecl *)()
0x14004804f  mov     cs:CallbackContext, rax
0x140048056  call    atexit
0x14004805b  mov     rcx, cs:CallbackContext; CallbackContext
0x140048062  mov     cs:qword_1403B7EC8, rcx
0x140048069  mov     cs:byte_1403B7ED0, 1
0x140048070  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140048075  mov     rax, cs:qword_1403B7EC0
0x14004807c  mov     rcx, rsi
0x14004807f  mov     cs:dword_1403B7ED4, 1
0x140048089  mov     rax, [rax+8]
0x14004808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048092  mov     r8, rsi; lpContext
0x140048095  lea     rcx, ?wrapper@?1??Instance@VmWorkerInterceptTrace@@KAPEAV2@XZ@4V?$static_lazy@VVmWorkerInterceptTrace@@@details@wil@@A; lpInitOnce
0x14004809c  xor     edx, edx; dwFlags
0x14004809e  call    cs:__imp_InitOnceComplete
0x1400480a5  nop     dword ptr [rax+rax+00h]
0x1400480aa  mov     rsi, [rsp+0A0h+arg_10]
0x1400480b2  mov     rax, [rbp+57h+Context]
0x1400480b6  mov     rcx, [rax+8]
0x1400480ba  mov     eax, [rcx]
0x1400480bc  cmp     eax, 4
0x1400480bf  jbe     loc_14004815C
0x1400480c5  lea     rax, [rbx+0BCh]
0x1400480cc  mov     [rbp+57h+var_28], 10h
0x1400480d4  mov     [rbp+57h+var_30], rax
0x1400480d8  lea     rdx, _TraceLoggingMetadata
0x1400480df  movzx   eax, cs:word_14035FC98
0x1400480e6  xor     r9d, r9d; RelatedActivityId
0x1400480e9  mov     dword ptr [rbp+57h+Context+4], eax
0x1400480ec  xor     r8d, r8d; ActivityId
0x1400480ef  mov     rax, [rcx+8]
0x1400480f3  mov     [rbp+57h+var_50.Ptr], rax
0x1400480f7  mov     dword ptr [rbp+57h+Context], 0B000000h
0x1400480fe  mov     [rbp+57h+var_58], r14
0x140048102  movzx   eax, word ptr [rax]
0x140048105  mov     [rbp+57h+var_50.Size], eax
0x140048108  lea     rax, word_14035FCA2
0x14004810f  mov     [rbp+57h+var_40], rax
0x140048113  lea     rax, _TraceLoggingMetadataEnd
0x14004811a  sub     eax, edx
0x14004811c  mov     dword ptr [rbp+57h+var_50.0Ch], 2
0x140048123  mov     [rbp+57h+var_38], 1Eh
0x14004812a  lea     rdx, [rbp+57h+Context]; EventDescriptor
0x14004812e  mov     [rbp+57h+var_34], 1
0x140048135  mov     [rbp+57h+fPending], eax
0x140048138  mov     eax, [rbp+57h+fPending]
0x14004813b  mov     rcx, [rcx+20h]; RegHandle
0x14004813f  lea     rax, [rbp+57h+var_50]
0x140048143  mov     [rsp+0A0h+UserData], rax; UserData
0x140048148  mov     [rsp+0A0h+UserDataCount], 3; UserDataCount
0x140048150  call    cs:__imp_EventWriteTransfer
0x140048157  nop     dword ptr [rax+rax+00h]
0x14004815c  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140048160  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x140048163  mov     rcx, rbx; this
0x140048166  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x14004816b  mov     r8, [rdi+10h]
0x14004816f  test    r8, r8
0x140048172  jns     short loc_1400481A5
0x140048174  mov     r9, qword ptr [rbp+57h+PerformanceCount]; __int64
0x140048178  neg     r8; __int64
0x14004817b  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x14004817e  mov     rcx, rbx; this
0x140048181  call    ?DelayIntercept@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J1@Z; InterceptThrottlingManager::DelayIntercept(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64,__int64)
0x140048186  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x14004818a  call    cs:__imp_QueryPerformanceCounter
0x140048191  nop     dword ptr [rax+rax+00h]
0x140048196  mov     r8, qword ptr [rbp+57h+PerformanceCount]; __int64
0x14004819a  mov     rdx, rdi; struct InterceptThrottlingManager::_VP_INTERCEPT_INFO *
0x14004819d  mov     rcx, rbx; this
0x1400481a0  call    ?AdjustVpBalance@InterceptThrottlingManager@@AEAAXPEAU_VP_INTERCEPT_INFO@1@_J@Z; InterceptThrottlingManager::AdjustVpBalance(InterceptThrottlingManager::_VP_INTERCEPT_INFO *,__int64)
0x1400481a5  mov     rcx, [rbp+57h+var_20]
0x1400481a9  xor     rcx, rsp; StackCookie
0x1400481ac  call    __security_check_cookie
0x1400481b1  mov     rbx, [rsp+0A0h+arg_18]
0x1400481b9  add     rsp, 90h
0x1400481c0  pop     r14
0x1400481c2  pop     rdi
0x1400481c3  pop     rbp
0x1400481c4  retn
```
