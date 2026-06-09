# StateRepository::Logging::DatabaseCache::Clear::StartActivity(void)

- ea: `0x1800afc90`
- end: `0x1800afd7b`
- name: `?StartActivity@Clear@DatabaseCache@Logging@StateRepository@@QEAAXXZ`
- size: `235`
- prototype: `void __fastcall(StateRepository::Logging::DatabaseCache::Clear *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x1800aef70`

## callees

- `0x180005720`
- `0x180016d54`
- `0x180020d64`
- `0x1800a1b90`
- `0x1800af588`
- `0x1800afc90`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800afcc5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800afcc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800afcf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800afcf4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall StateRepository::Logging::DatabaseCache::Clear::StartActivity(
        StateRepository::Logging::DatabaseCache::Clear *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  __int64 v5; // r8
  int v6; // r9d
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v8; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StateRepository::Tracing::Service::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v3 = StateRepository::Tracing::Service::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v8 = 0;
    v5 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v5 + 4)
      || (v6 = v5 + 24, !*(_DWORD *)(v5 + 24))
      && !*(_DWORD *)(v5 + 28)
      && !*(_DWORD *)(v5 + 32)
      && !*(_DWORD *)(v5 + 36) )
    {
      v6 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)byte_18014C331,
      v5 + 8,
      v6,
      (__int64)&v8,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StateRepository::Logging::DatabaseCache::Clear *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800afc90  mov     [rsp+arg_10], rbx
0x1800afc95  push    rdi
0x1800afc96  sub     rsp, 30h
0x1800afc9a  mov     rbx, rcx
0x1800afc9d  lea     rdx, [rsp+38h+arg_0]
0x1800afca2  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800afca7  mov     rdi, [rbx+110h]
0x1800afcae  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800afcb3  mov     r8d, [rax]
0x1800afcb6  cmp     r8d, 5
0x1800afcba  jbe     short loc_1800AFCCD
0x1800afcbc  lea     rdx, [rdi+8]; ActivityId
0x1800afcc0  mov     ecx, 3; ControlCode
0x1800afcc5  call    cs:__imp_EventActivityIdControl
0x1800afccb  jmp     short loc_1800AFCD4
0x1800afccd  xorps   xmm0, xmm0
0x1800afcd0  movups  xmmword ptr [rdi+8], xmm0
0x1800afcd4  mov     dword ptr [rdi], 1
0x1800afcda  lea     rcx, [rsp+38h+arg_0]
0x1800afcdf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800afce4  nop
0x1800afce5  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800afcea  mov     rdi, rax
0x1800afced  mov     ecx, [rax]
0x1800afcef  cmp     ecx, 5
0x1800afcf2  jbe     short loc_1800AFD5E
0x1800afcf4  call    cs:__imp_GetCurrentThreadId
0x1800afcfa  mov     [rsp+38h+arg_0], eax
0x1800afcfe  mov     [rsp+38h+arg_8], 0
0x1800afd07  mov     r8, [rbx+110h]
0x1800afd0e  cmp     byte ptr [r8+4], 0
0x1800afd13  jz      short loc_1800AFD34
0x1800afd15  lea     r9, [r8+18h]
0x1800afd19  cmp     dword ptr [r9], 0
0x1800afd1d  jnz     short loc_1800AFD37
0x1800afd1f  cmp     dword ptr [r9+4], 0
0x1800afd24  jnz     short loc_1800AFD37
0x1800afd26  cmp     dword ptr [r9+8], 0
0x1800afd2b  jnz     short loc_1800AFD37
0x1800afd2d  cmp     dword ptr [r9+0Ch], 0
0x1800afd32  jnz     short loc_1800AFD37
0x1800afd34  xor     r9d, r9d
0x1800afd37  add     r8, 8
0x1800afd3b  lea     rax, [rsp+38h+arg_0]
0x1800afd40  mov     [rsp+38h+var_10], rax
0x1800afd45  lea     rax, [rsp+38h+arg_8]
0x1800afd4a  mov     [rsp+38h+var_18], rax
0x1800afd4f  lea     rdx, byte_18014C331
0x1800afd56  mov     rcx, rdi
0x1800afd59  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800afd5e  lea     rcx, [rbx+120h]; this
0x1800afd65  cmp     dword ptr [rcx+18h], 0
0x1800afd69  jnz     short loc_1800AFD70
0x1800afd6b  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800afd70  mov     rbx, [rsp+38h+arg_10]
0x1800afd75  add     rsp, 30h
0x1800afd79  pop     rdi
0x1800afd7a  retn
```
