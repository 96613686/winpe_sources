# PendingRequest::CreateTimeoutTimer(void)

- ea: `0x18008e09c`
- end: `0x18008e19e`
- name: `?CreateTimeoutTimer@PendingRequest@@QEAAXXZ`
- size: `258`
- prototype: `void __fastcall(PVOID Parameter)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800901a4`

## callees

- `0x18000b7a4`
- `0x18000b7fc`
- `0x180033c04`
- `0x18008a400`
- `0x18008d4f0`
- `0x18008e09c`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e124`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18008e124`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e117`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18008e117`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e18f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18008e18f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18008e166`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18008e166`

## string_xrefs

- `0x18008e175`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall PendingRequest::CreateTimeoutTimer(char *Parameter)
{
  __int64 v2; // rax
  __int64 v3; // rbx
  __int64 v4; // rcx
  const char *v5; // r9
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  char *v8; // [rsp+80h] [rbp+18h] BYREF
  PSRWLOCK SRWLock; // [rsp+88h] [rbp+20h] BYREF

  Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, &ResumeCancellationParamsLock);
  try
  {
    v2 = std::map<void *,Microsoft::WRL::ComPtr<PendingRequest>>::_Try_emplace<void *,>();
    v3 = *(_QWORD *)v2;
    if ( *(char **)(*(_QWORD *)v2 + 40LL) != Parameter )
    {
      v8 = Parameter;
      Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v8);
      v4 = *(_QWORD *)(v3 + 40);
      *(_QWORD *)(v3 + 40) = Parameter;
      if ( v4 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    EnterCriticalSection((LPCRITICAL_SECTION)(Parameter + 16));
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(Parameter + 240);
    if ( !CreateTimerQueueTimer(
            (PHANDLE)Parameter + 31,
            0,
            _lambda_c43cae5ec51b34eff5149e02b6daf679_::_lambda_invoker_cdecl_,
            Parameter,
            0x9C40u,
            0,
            0) )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0x781,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        v5);
    if ( Parameter != (char *)-16LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)(Parameter + 16));
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x786,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      v5);
    CancelResumeAfterPrecacheTimerThreadProc(Parameter);
    throw;
  }
}

```

## disassembly

```asm
0x18008e09c  mov     rax, rsp
0x18008e09f  mov     [rax+8], rcx
0x18008e0a3  push    rbx
0x18008e0a4  push    rsi
0x18008e0a5  push    rdi
0x18008e0a6  sub     rsp, 50h
0x18008e0aa  mov     rdi, rcx
0x18008e0ad  lea     rdx, ?ResumeCancellationParamsLock@@3VSRWLock@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::SRWLock ResumeCancellationParamsLock
0x18008e0b4  lea     rcx, [rax+20h]
0x18008e0b8  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18008e0bd  nop
0x18008e0be  mov     [rsp+68h+arg_8], rdi
0x18008e0c3  lea     r8, [rsp+68h+arg_8]
0x18008e0c8  lea     rdx, [rsp+68h+var_28]
0x18008e0cd  call    ??$_Try_emplace@PEAX$$V@?$map@PEAXV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@@std@@@5@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@QEAXV?$ComPtr@VPendingRequest@@@WRL@Microsoft@@@std@@PEAX@std@@_N@1@$$QEAPEAX@Z; std::map<void *,Microsoft::WRL::ComPtr<PendingRequest>>::_Try_emplace<void *,>(void * &&)
0x18008e0d2  mov     rbx, [rax]
0x18008e0d5  cmp     [rbx+28h], rdi
0x18008e0d9  jz      short loc_18008E10A
0x18008e0db  mov     [rsp+68h+arg_10], rdi
0x18008e0e3  lea     rcx, [rsp+68h+arg_10]
0x18008e0eb  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18008e0f0  mov     rcx, [rbx+28h]
0x18008e0f4  mov     [rbx+28h], rdi
0x18008e0f8  test    rcx, rcx
0x18008e0fb  jz      short loc_18008E10A
0x18008e0fd  mov     rax, [rcx]
0x18008e100  mov     rax, [rax+10h]
0x18008e104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e109  nop
0x18008e10a  mov     rcx, [rsp+68h+SRWLock]; SRWLock
0x18008e112  test    rcx, rcx
0x18008e115  jz      short loc_18008E11D
0x18008e117  call    cs:__imp_ReleaseSRWLockExclusive
0x18008e11d  lea     rsi, [rdi+10h]
0x18008e121  mov     rcx, rsi; lpCriticalSection
0x18008e124  call    cs:__imp_EnterCriticalSection
0x18008e12a  mov     [rsp+68h+arg_8], rsi
0x18008e12f  lea     rbx, [rdi+0F0h]
0x18008e136  mov     rcx, rbx
0x18008e139  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x18008e13e  lea     rcx, [rbx+8]; phNewTimer
0x18008e142  mov     [rsp+68h+Flags], 0; Flags
0x18008e14a  mov     [rsp+68h+Period], 0; Period
0x18008e152  mov     [rsp+68h+DueTime], 9C40h; DueTime
0x18008e15a  mov     r9, rdi; Parameter
0x18008e15d  lea     r8, ?_lambda_invoker_cdecl_@_lambda_c43cae5ec51b34eff5149e02b6daf679_@@CA@PEAXE@Z; Callback
0x18008e164  xor     edx, edx; TimerQueue
0x18008e166  call    cs:__imp_CreateTimerQueueTimer
0x18008e16c  mov     rcx, [rsp+68h]; this
0x18008e171  test    eax, eax
0x18008e173  jnz     short loc_18008E187
0x18008e175  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008e17c  mov     edx, 781h; void *
0x18008e181  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18008e187  test    rsi, rsi
0x18008e18a  jz      short loc_18008E196
0x18008e18c  mov     rcx, rsi; lpCriticalSection
0x18008e18f  call    cs:__imp_LeaveCriticalSection
0x18008e195  nop
0x18008e196  add     rsp, 50h
0x18008e19a  pop     rdi
0x18008e19b  pop     rsi
0x18008e19c  pop     rbx
0x18008e19d  retn
```
