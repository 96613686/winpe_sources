# StateRepository::Logging::DatabaseCache::Clear::StartActivity(void)

- ea: `0x18002afd0`
- end: `0x18002b0ba`
- name: `?StartActivity@Clear@DatabaseCache@Logging@StateRepository@@QEAAXXZ`
- size: `234`
- prototype: `void __fastcall(StateRepository::Logging::DatabaseCache::Clear *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18002a5f4`

## callees

- `0x1800020f0`
- `0x18000c984`
- `0x18000f460`
- `0x180017a50`
- `0x18002a95c`
- `0x18002afd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b033`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002b005`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002b005`

## pseudocode

```c
void __fastcall StateRepository::Logging::DatabaseCache::Clear::StartActivity(
        StateRepository::Logging::DatabaseCache::Clear *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  int v4; // edi
  DWORD CurrentThreadId; // eax
  __int64 v6; // r8
  int v7; // r9d
  DWORD v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v8);
  v2 = *((_QWORD *)this + 34);
  if ( *(_DWORD *)StateRepository::Tracing::Service::Provider() <= 5u )
    *(_OWORD *)(v2 + 8) = 0;
  else
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  v3 = StateRepository::Tracing::Service::Provider();
  v4 = (int)v3;
  if ( *(_DWORD *)v3 > 5u )
  {
    CurrentThreadId = GetCurrentThreadId();
    v6 = *((_QWORD *)this + 34);
    v8 = CurrentThreadId;
    v9 = 0;
    if ( !*(_BYTE *)(v6 + 4)
      || (v7 = v6 + 24, !*(_DWORD *)(v6 + 24))
      && !*(_DWORD *)(v6 + 28)
      && !*(_DWORD *)(v6 + 32)
      && !*(_DWORD *)(v6 + 36) )
    {
      v7 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v4,
      (unsigned int)&dword_18004600C,
      v6 + 8,
      v7,
      (__int64)&v9,
      (__int64)&v8);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((StateRepository::Logging::DatabaseCache::Clear *)((char *)this + 288));
}

```

## disassembly

```asm
0x18002afd0  mov     [rsp+arg_10], rbx
0x18002afd5  push    rdi
0x18002afd6  sub     rsp, 30h
0x18002afda  lea     rdx, [rsp+38h+arg_0]
0x18002afdf  mov     rbx, rcx
0x18002afe2  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002afe7  mov     rdi, [rbx+110h]
0x18002afee  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002aff3  mov     r8d, [rax]
0x18002aff6  cmp     r8d, 5
0x18002affa  jbe     short loc_18002B00D
0x18002affc  lea     rdx, [rdi+8]; ActivityId
0x18002b000  mov     ecx, 3; ControlCode
0x18002b005  call    cs:__imp_EventActivityIdControl
0x18002b00b  jmp     short loc_18002B014
0x18002b00d  xorps   xmm0, xmm0
0x18002b010  movups  xmmword ptr [rdi+8], xmm0
0x18002b014  lea     rcx, [rsp+38h+arg_0]
0x18002b019  mov     dword ptr [rdi], 1
0x18002b01f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002b024  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x18002b029  mov     rdi, rax
0x18002b02c  mov     ecx, [rax]
0x18002b02e  cmp     ecx, 5
0x18002b031  jbe     short loc_18002B09D
0x18002b033  call    cs:__imp_GetCurrentThreadId
0x18002b039  mov     r8, [rbx+110h]
0x18002b040  mov     [rsp+38h+arg_0], eax
0x18002b044  mov     [rsp+38h+arg_8], 0
0x18002b04d  cmp     byte ptr [r8+4], 0
0x18002b052  jz      short loc_18002B073
0x18002b054  lea     r9, [r8+18h]
0x18002b058  cmp     dword ptr [r9], 0
0x18002b05c  jnz     short loc_18002B076
0x18002b05e  cmp     dword ptr [r9+4], 0
0x18002b063  jnz     short loc_18002B076
0x18002b065  cmp     dword ptr [r9+8], 0
0x18002b06a  jnz     short loc_18002B076
0x18002b06c  cmp     dword ptr [r9+0Ch], 0
0x18002b071  jnz     short loc_18002B076
0x18002b073  xor     r9d, r9d
0x18002b076  lea     rax, [rsp+38h+arg_0]
0x18002b07b  add     r8, 8
0x18002b07f  mov     [rsp+38h+var_10], rax
0x18002b084  lea     rdx, dword_18004600C
0x18002b08b  lea     rax, [rsp+38h+arg_8]
0x18002b090  mov     rcx, rdi
0x18002b093  mov     [rsp+38h+var_18], rax
0x18002b098  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002b09d  lea     rcx, [rbx+120h]; this
0x18002b0a4  cmp     dword ptr [rcx+18h], 0
0x18002b0a8  jnz     short loc_18002B0AF
0x18002b0aa  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002b0af  mov     rbx, [rsp+38h+arg_10]
0x18002b0b4  add     rsp, 30h
0x18002b0b8  pop     rdi
0x18002b0b9  retn
```
