# AccountsTelemetry::GetAccounts::StartActivity(void)

- ea: `0x18001823c`
- end: `0x180018341`
- name: `?StartActivity@GetAccounts@AccountsTelemetry@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(AccountsTelemetry::GetAccounts *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001408c`

## callees

- `0x180001314`
- `0x180001b0c`
- `0x18000a5c4`
- `0x18000db9c`
- `0x18000e00c`
- `0x18000e794`
- `0x18000ebf4`
- `0x18001823c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800182c9`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018285`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180018285`

## pseudocode

```c
void __fastcall AccountsTelemetry::GetAccounts::StartActivity(AccountsTelemetry::GetAccounts *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  __int64 v5; // r9
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx
  RTL_SRWLOCK *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v13);
  v2 = *((_QWORD *)this + 34);
  v3 = SharedPCAccountManagerLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x200000000000LL, v4, v5) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  v6 = SharedPCAccountManagerLogging::Provider();
  v10 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL, v8, v9) )
  {
    LODWORD(v13) = GetCurrentThreadId();
    v14 = 0;
    v11 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v10,
      (__int64)&dword_18002D7B4,
      v11 + 8,
      v12,
      (__int64)&v14,
      (__int64)&v13);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((AccountsTelemetry::GetAccounts *)((char *)this + 288), v7);
}

```

## disassembly

```asm
0x18001823c  mov     [rsp+arg_10], rbx
0x180018241  push    rdi
0x180018242  sub     rsp, 30h
0x180018246  mov     rbx, rcx
0x180018249  lea     rdx, [rsp+38h+arg_0]
0x18001824e  call    ?LockExclusive@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018253  mov     rdi, [rbx+110h]
0x18001825a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001825f  mov     edx, [rax]
0x180018261  cmp     edx, 5
0x180018264  jbe     short loc_18001828D
0x180018266  mov     rdx, 200000000000h
0x180018270  mov     rcx, rax
0x180018273  call    _tlgKeywordOn
0x180018278  test    al, al
0x18001827a  jz      short loc_18001828D
0x18001827c  lea     rdx, [rdi+8]; ActivityId
0x180018280  mov     ecx, 3; ControlCode
0x180018285  call    cs:__imp_EventActivityIdControl
0x18001828b  jmp     short loc_180018294
0x18001828d  xorps   xmm0, xmm0
0x180018290  movups  xmmword ptr [rdi+8], xmm0
0x180018294  mov     dword ptr [rdi], 1
0x18001829a  lea     rcx, [rsp+38h+arg_0]
0x18001829f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800182a4  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x1800182a9  mov     rdi, rax
0x1800182ac  mov     ecx, [rax]
0x1800182ae  cmp     ecx, 5
0x1800182b1  jbe     short loc_180018323
0x1800182b3  mov     rdx, 200000000000h
0x1800182bd  mov     rcx, rax
0x1800182c0  call    _tlgKeywordOn
0x1800182c5  test    al, al
0x1800182c7  jz      short loc_180018323
0x1800182c9  call    cs:__imp_GetCurrentThreadId
0x1800182cf  mov     dword ptr [rsp+38h+arg_0], eax
0x1800182d3  mov     [rsp+38h+arg_8], 0
0x1800182dc  mov     r8, [rbx+110h]
0x1800182e3  cmp     byte ptr [r8+4], 0
0x1800182e8  jz      short loc_1800182F7
0x1800182ea  lea     rcx, [r8+18h]; struct _GUID *
0x1800182ee  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800182f3  test    al, al
0x1800182f5  jz      short loc_1800182F9
0x1800182f7  xor     ecx, ecx
0x1800182f9  add     r8, 8
0x1800182fd  lea     rax, [rsp+38h+arg_0]
0x180018302  mov     [rsp+38h+var_10], rax
0x180018307  lea     rax, [rsp+38h+arg_8]
0x18001830c  mov     [rsp+38h+var_18], rax
0x180018311  mov     r9, rcx
0x180018314  lea     rdx, dword_18002D7B4
0x18001831b  mov     rcx, rdi
0x18001831e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180018323  lea     rcx, [rbx+120h]; this
0x18001832a  cmp     dword ptr [rcx+18h], 0
0x18001832e  jnz     short loc_180018336
0x180018330  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180018335  nop
0x180018336  mov     rbx, [rsp+38h+arg_10]
0x18001833b  add     rsp, 30h
0x18001833f  pop     rdi
0x180018340  retn
```
