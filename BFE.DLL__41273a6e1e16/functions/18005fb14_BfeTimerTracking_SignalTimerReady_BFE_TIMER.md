# BfeTimerTracking::SignalTimerReady(BFE_TIMER_ *)

- ea: `0x18005fb14`
- end: `0x18005fba8`
- name: `?SignalTimerReady@BfeTimerTracking@@QEAAXPEAUBFE_TIMER_@@@Z`
- size: `148`
- prototype: `void __fastcall(BfeTimerTracking *__hidden this, struct BFE_TIMER_ *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c090`

## callees

- `0x180045864`
- `0x1800592f4`
- `0x18005fb14`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005fb7e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005fb7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fb2b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005fb2b`

## pseudocode

```c
void __fastcall BfeTimerTracking::SignalTimerReady(BfeTimerTracking *this, struct BFE_TIMER_ *a2)
{
  __int64 v3; // rcx
  __int64 i; // rbx
  RTL_SRWLOCK *v5; // [rsp+20h] [rbp-18h] BYREF

  AcquireSRWLockExclusive(&gBfeTimerTracking);
  v5 = &gBfeTimerTracking;
  for ( i = qword_1800F23B8; i != qword_1800F23C0 && *(struct BFE_TIMER_ **)i != a2; i += 8 )
    ;
  if ( i != qword_1800F23C0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)i + 16LL) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v3);
    *(_DWORD *)(*(_QWORD *)i + 16LL) = 1;
    SubmitThreadpoolWork(pwk);
    *(_QWORD *)&xmmword_1800F2440 = xmmword_1800F2440 + 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x18005fb14  mov     [rsp+arg_0], rbx
0x18005fb19  push    rdi
0x18005fb1a  sub     rsp, 30h
0x18005fb1e  mov     rdi, rdx
0x18005fb21  lea     rbx, ?gBfeTimerTracking@@3VBfeTimerTracking@@A; BfeTimerTracking gBfeTimerTracking
0x18005fb28  mov     rcx, rbx; SRWLock
0x18005fb2b  call    cs:__imp_AcquireSRWLockExclusive
0x18005fb32  nop     dword ptr [rax+rax+00h]
0x18005fb37  mov     [rsp+38h+var_18], rbx
0x18005fb3c  mov     rbx, cs:qword_1800F23B8
0x18005fb43  mov     rax, cs:qword_1800F23C0
0x18005fb4a  jmp     short loc_18005FB55
0x18005fb4c  cmp     [rbx], rdi
0x18005fb4f  jz      short loc_18005FB5A
0x18005fb51  add     rbx, 8
0x18005fb55  cmp     rbx, rax
0x18005fb58  jnz     short loc_18005FB4C
0x18005fb5a  cmp     rbx, rax
0x18005fb5d  jz      short loc_18005FB91
0x18005fb5f  mov     rax, [rbx]
0x18005fb62  cmp     dword ptr [rax+10h], 1
0x18005fb66  jnz     short loc_18005FB6D
0x18005fb68  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "foundTimer->get()->state != BFE_TIMER_FIRED")
0x18005fb6d  mov     rax, [rbx]
0x18005fb70  mov     dword ptr [rax+10h], 1
0x18005fb77  mov     rcx, cs:pwk; pwk
0x18005fb7e  call    cs:__imp_SubmitThreadpoolWork
0x18005fb85  nop     dword ptr [rax+rax+00h]
0x18005fb8a  inc     qword ptr cs:xmmword_1800F2440
0x18005fb91  lea     rcx, [rsp+38h+var_18]
0x18005fb96  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005fb9b  nop
0x18005fb9c  mov     rbx, [rsp+38h+arg_0]
0x18005fba1  add     rsp, 30h
0x18005fba5  pop     rdi
0x18005fba6  retn
```
