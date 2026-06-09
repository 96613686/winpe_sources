# StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::StartActivity(void)

- ea: `0x180018c60`
- end: `0x180018d95`
- name: `?StartActivity@DoMaintenanceTasks@MaintenanceTasks@WinRT@Trace@StateRepository@@QEAAXXZ`
- size: `309`
- prototype: `void __fastcall(StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180018180`

## callees

- `0x180001858`
- `0x180002980`
- `0x18000719c`
- `0x180009530`
- `0x1800185f8`
- `0x180018c60`
- `0x180018d9c`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018caf`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018caf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018ce0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018ce0`

## pseudocode

```c
void __fastcall StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks::StartActivity(
        StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v5; // r8
  const GUID *v6; // r9
  DWORD v7; // [rsp+30h] [rbp-9h] BYREF
  __int64 v8; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v9; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v10; // [rsp+60h] [rbp+27h]
  __int64 v11; // [rsp+68h] [rbp+2Fh]
  DWORD *v12; // [rsp+70h] [rbp+37h]
  __int64 v13; // [rsp+78h] [rbp+3Fh]

  wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v7);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StateRepository::Tracing::Client::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  v3 = StateRepository::Tracing::Client::Provider();
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v5 = *((_QWORD *)this + 34);
    v7 = CurrentThreadId;
    v8 = 0;
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = (const GUID *)(v5 + 24), !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    v11 = 8;
    v13 = 4;
    v12 = &v7;
    v10 = &v8;
    tlgWriteTransfer_EventWriteTransfer(
      (__int64)v3,
      (unsigned __int8 *)&word_180030126,
      (const GUID *)(v5 + 8),
      v6,
      4u,
      &v9);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StateRepository::Trace::WinRT::MaintenanceTasks::DoMaintenanceTasks *)((char *)this + 288));
}

```

## disassembly

```asm
0x180018c60  mov     [rsp-8+arg_8], rbx
0x180018c65  mov     [rsp-8+arg_10], rdi
0x180018c6a  push    rbp
0x180018c6b  lea     rbp, [rsp-57h]
0x180018c70  sub     rsp, 90h
0x180018c77  mov     rax, cs:__security_cookie
0x180018c7e  xor     rax, rsp
0x180018c81  mov     [rbp+57h+var_10], rax
0x180018c85  lea     rdx, [rbp+57h+var_60]
0x180018c89  mov     rbx, rcx
0x180018c8c  call    ?LockExclusive@?$ActivityBase@VClient@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Client,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018c91  mov     rdi, [rbx+110h]
0x180018c98  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180018c9d  mov     r8d, [rax]
0x180018ca0  cmp     r8d, 5
0x180018ca4  jbe     short loc_180018CB7
0x180018ca6  lea     rdx, [rdi+8]; ActivityId
0x180018caa  mov     ecx, 3; ControlCode
0x180018caf  call    cs:__imp_EventActivityIdControl
0x180018cb5  jmp     short loc_180018CBE
0x180018cb7  xorps   xmm0, xmm0
0x180018cba  movups  xmmword ptr [rdi+8], xmm0
0x180018cbe  lea     rcx, [rbp+57h+var_60]
0x180018cc2  mov     dword ptr [rdi], 1
0x180018cc8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180018ccd  call    ?Provider@Client@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Client::Provider(void)
0x180018cd2  mov     rdi, rax
0x180018cd5  mov     ecx, [rax]
0x180018cd7  cmp     ecx, 5
0x180018cda  jbe     loc_180018D62
0x180018ce0  call    cs:__imp_GetCurrentThreadId
0x180018ce6  mov     r8, [rbx+110h]
0x180018ced  mov     [rbp+57h+var_60], eax
0x180018cf0  mov     [rbp+57h+var_58], 0
0x180018cf8  cmp     byte ptr [r8+4], 0
0x180018cfd  jz      short loc_180018D1E
0x180018cff  lea     r9, [r8+18h]
0x180018d03  cmp     dword ptr [r9], 0
0x180018d07  jnz     short loc_180018D21
0x180018d09  cmp     dword ptr [r9+4], 0
0x180018d0e  jnz     short loc_180018D21
0x180018d10  cmp     dword ptr [r9+8], 0
0x180018d15  jnz     short loc_180018D21
0x180018d17  cmp     dword ptr [r9+0Ch], 0
0x180018d1c  jnz     short loc_180018D21
0x180018d1e  xor     r9d, r9d
0x180018d21  mov     ecx, 4
0x180018d26  mov     [rbp+57h+var_28], 8
0x180018d2e  lea     rax, [rbp+57h+var_60]
0x180018d32  mov     [rbp+57h+var_18], rcx
0x180018d36  mov     [rbp+57h+var_20], rax
0x180018d3a  lea     rdx, word_180030126
0x180018d41  lea     rax, [rbp+57h+var_58]
0x180018d45  add     r8, 8
0x180018d49  mov     [rbp+57h+var_30], rax
0x180018d4d  lea     rax, [rbp+57h+var_50]
0x180018d51  mov     [rsp+90h+var_68], rax
0x180018d56  mov     [rsp+90h+var_70], ecx
0x180018d5a  mov     rcx, rdi
0x180018d5d  call    _tlgWriteTransfer_EventWriteTransfer
0x180018d62  lea     rcx, [rbx+120h]; this
0x180018d69  cmp     dword ptr [rcx+18h], 0
0x180018d6d  jnz     short loc_180018D74
0x180018d6f  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018d74  mov     rcx, [rbp+57h+var_10]
0x180018d78  xor     rcx, rsp; StackCookie
0x180018d7b  call    __security_check_cookie
0x180018d80  lea     r11, [rsp+90h+var_s0]
0x180018d88  mov     rbx, [r11+18h]
0x180018d8c  mov     rdi, [r11+20h]
0x180018d90  mov     rsp, r11
0x180018d93  pop     rbp
0x180018d94  retn
```
