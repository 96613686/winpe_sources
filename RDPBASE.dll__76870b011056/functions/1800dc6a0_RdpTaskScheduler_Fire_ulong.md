# RdpTaskScheduler::Fire(ulong)

- ea: `0x1800dc6a0`
- end: `0x1800dc7fb`
- name: `?Fire@RdpTaskScheduler@@UEAAXK@Z`
- size: `347`
- prototype: `void(RdpTaskScheduler *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800018a4`
- `0x1800dc6a0`
- `0x1800dcd24`
- `0x180162010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dc6c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800dc6c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc6bc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800dc6bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800dc7f4`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800dc6de`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800dc6de`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dc7df`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800dc7df`

## string_xrefs

- `0x1800dc75d`: `onecore\termsrv\rdpplatform\rdpenc\globalcontext\rdptaskscheduler.cpp`
- `0x1800dc777`: `Fire - m_workThreadPool is null`

## pseudocode

```c
void __fastcall RdpTaskScheduler::Fire(RdpTaskScheduler *this, unsigned int a2)
{
  RTL_SRWLOCK *v2; // r14
  __int64 v3; // rbp
  ULONGLONG TickCount64; // rax
  __int64 v6; // r15
  _QWORD *v7; // rdi
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  const char *v12; // [rsp+50h] [rbp-48h] BYREF
  int v13; // [rsp+A0h] [rbp+8h] BYREF
  int v14; // [rsp+A8h] [rbp+10h] BYREF
  const char *v15; // [rsp+B0h] [rbp+18h] BYREF
  const char *v16; // [rsp+B8h] [rbp+20h] BYREF

  v2 = (RTL_SRWLOCK *)((char *)this + 224);
  v3 = a2;
  AcquireSRWLockExclusive((PSRWLOCK)this + 28);
  TickCount64 = GetTickCount64();
  if ( (_DWORD)v3 )
  {
    v6 = TickCount64 + v3;
    v7 = (_QWORD *)((char *)this + 160);
    if ( !IsThreadpoolTimerSet(*((PTP_TIMER *)this + 18)) || v6 < *v7 )
    {
      v8 = *((_QWORD *)this + 5);
      *v7 = v6;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      RdpTaskScheduler::ResetTimer((RdpTaskScheduler *)((char *)this - 8), v3);
    }
  }
  else
  {
    RdpTaskScheduler::ResetTimer((RdpTaskScheduler *)((char *)this - 8), 0);
    if ( *((_QWORD *)this + 17) )
    {
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 8LL))(*((_QWORD *)this + 5));
      SubmitThreadpoolWork(*((PTP_WORK *)this + 17));
    }
    else if ( (unsigned int)CallbackContext > 2 )
    {
      v14 = 780;
      v15 = "Fire";
      v13 = -2147467261;
      v16 = "onecore\\termsrv\\rdpplatform\\rdpenc\\globalcontext\\rdptaskscheduler.cpp";
      v12 = "Fire - m_workThreadPool is null";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)byte_1801BBCBD,
        v10,
        v11,
        (__int64)&v12,
        (__int64)&v13,
        (__int64)&v16,
        (__int64)&v14,
        (__int64)&v15);
    }
  }
  ReleaseSRWLockExclusive(v2);
}

```

## disassembly

```asm
0x1800dc6a0  push    rbx
0x1800dc6a2  push    rbp
0x1800dc6a3  push    rsi
0x1800dc6a4  push    rdi
0x1800dc6a5  push    r14
0x1800dc6a7  push    r15
0x1800dc6a9  sub     rsp, 68h
0x1800dc6ad  lea     r14, [rcx+0E0h]
0x1800dc6b4  mov     ebp, edx
0x1800dc6b6  mov     rbx, rcx
0x1800dc6b9  mov     rcx, r14; SRWLock
0x1800dc6bc  call    cs:__imp_AcquireSRWLockExclusive
0x1800dc6c2  call    cs:__imp_GetTickCount64
0x1800dc6c8  test    ebp, ebp
0x1800dc6ca  jz      short loc_1800DC714
0x1800dc6cc  mov     rcx, [rbx+90h]; pti
0x1800dc6d3  lea     r15, [rax+rbp]
0x1800dc6d7  lea     rdi, [rbx+0A0h]
0x1800dc6de  call    cs:__imp_IsThreadpoolTimerSet
0x1800dc6e4  test    eax, eax
0x1800dc6e6  jz      short loc_1800DC6F1
0x1800dc6e8  cmp     r15, [rdi]
0x1800dc6eb  jge     loc_1800DC7E5
0x1800dc6f1  mov     rcx, [rbx+28h]
0x1800dc6f5  mov     [rdi], r15
0x1800dc6f8  mov     rax, [rcx]
0x1800dc6fb  mov     rax, [rax+8]
0x1800dc6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc704  mov     edx, ebp; unsigned int
0x1800dc706  lea     rcx, [rbx-8]; this
0x1800dc70a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x1800dc70f  jmp     loc_1800DC7E5
0x1800dc714  xor     edx, edx; unsigned int
0x1800dc716  lea     rcx, [rbx-8]; this
0x1800dc71a  call    ?ResetTimer@RdpTaskScheduler@@IEAAXK@Z; RdpTaskScheduler::ResetTimer(ulong)
0x1800dc71f  cmp     qword ptr [rbx+88h], 0
0x1800dc727  jnz     loc_1800DC7C8
0x1800dc72d  mov     eax, cs:CallbackContext
0x1800dc733  cmp     eax, 2
0x1800dc736  jbe     loc_1800DC7E5
0x1800dc73c  lea     rax, aFire; "Fire"
0x1800dc743  mov     [rsp+98h+arg_8], 30Ch
0x1800dc74e  mov     [rsp+98h+arg_10], rax
0x1800dc756  lea     rdx, byte_1801BBCBD
0x1800dc75d  lea     rax, aOnecoreTermsrv_52; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x1800dc764  mov     [rsp+98h+arg_0], 80004003h
0x1800dc76f  mov     [rsp+98h+arg_18], rax
0x1800dc777  lea     rax, aFireMWorkthrea; "Fire - m_workThreadPool is null"
0x1800dc77e  mov     [rsp+98h+var_48], rax
0x1800dc783  lea     rax, [rsp+98h+arg_10]
0x1800dc78b  mov     [rsp+98h+var_58], rax
0x1800dc790  lea     rax, [rsp+98h+arg_8]
0x1800dc798  mov     [rsp+98h+var_60], rax
0x1800dc79d  lea     rax, [rsp+98h+arg_18]
0x1800dc7a5  mov     [rsp+98h+var_68], rax
0x1800dc7aa  lea     rax, [rsp+98h+arg_0]
0x1800dc7b2  mov     [rsp+98h+var_70], rax
0x1800dc7b7  lea     rax, [rsp+98h+var_48]
0x1800dc7bc  mov     [rsp+98h+var_78], rax
0x1800dc7c1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800dc7c6  jmp     short loc_1800DC7E5
0x1800dc7c8  mov     rcx, [rbx+28h]
0x1800dc7cc  mov     rax, [rcx]
0x1800dc7cf  mov     rax, [rax+8]
0x1800dc7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800dc7d8  mov     rcx, [rbx+88h]; pwk
0x1800dc7df  call    cs:__imp_SubmitThreadpoolWork
0x1800dc7e5  mov     rcx, r14
0x1800dc7e8  add     rsp, 68h
0x1800dc7ec  pop     r15
0x1800dc7ee  pop     r14
0x1800dc7f0  pop     rdi
0x1800dc7f1  pop     rsi
0x1800dc7f2  pop     rbp
0x1800dc7f3  pop     rbx
0x1800dc7f4  jmp     cs:__imp_ReleaseSRWLockExclusive
```
