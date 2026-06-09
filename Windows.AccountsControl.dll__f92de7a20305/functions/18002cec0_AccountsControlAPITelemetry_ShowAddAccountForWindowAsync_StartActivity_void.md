# AccountsControlAPITelemetry::ShowAddAccountForWindowAsync::StartActivity(void)

- ea: `0x18002cec0`
- end: `0x18002cfc5`
- name: `?StartActivity@ShowAddAccountForWindowAsync@AccountsControlAPITelemetry@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(AccountsControlAPITelemetry::ShowAddAccountForWindowAsync *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002c0d0`

## callees

- `0x18000171c`
- `0x180001934`
- `0x18000c14c`
- `0x1800123bc`
- `0x180017304`
- `0x180019304`
- `0x18002a264`
- `0x18002cec0`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002cf09`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18002cf09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cf4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cf4d`

## pseudocode

```c
void __fastcall AccountsControlAPITelemetry::ShowAddAccountForWindowAsync::StartActivity(
        AccountsControlAPITelemetry::ShowAddAccountForWindowAsync *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  int v6; // edi
  __int64 v7; // r8
  int v8; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = AccountsControlAPITelemetry::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v4 = AccountsControlAPITelemetry::Provider();
  v6 = (int)v4;
  if ( *(_DWORD *)v4 > 5u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = 50331648;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4) || _tlgGuidIsZero((const struct _GUID *)(v7 + 24)) )
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v6,
      (unsigned int)&unk_18009EE18,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (AccountsControlAPITelemetry::ShowAddAccountForWindowAsync *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x18002cec0  mov     [rsp+arg_10], rbx
0x18002cec5  push    rdi
0x18002cec6  sub     rsp, 30h
0x18002ceca  mov     rbx, rcx
0x18002cecd  lea     rdx, [rsp+38h+arg_0]
0x18002ced2  call    ?LockExclusive@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002ced7  mov     rdi, [rbx+110h]
0x18002cede  call    ?Provider@AccountsControlAPITelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountsControlAPITelemetry::Provider(void)
0x18002cee3  mov     edx, [rax]
0x18002cee5  cmp     edx, 5
0x18002cee8  jbe     short loc_18002CF11
0x18002ceea  mov     rdx, 400000000000h
0x18002cef4  mov     rcx, rax
0x18002cef7  call    _tlgKeywordOn
0x18002cefc  test    al, al
0x18002cefe  jz      short loc_18002CF11
0x18002cf00  lea     rdx, [rdi+8]; ActivityId
0x18002cf04  mov     ecx, 3; ControlCode
0x18002cf09  call    cs:__imp_EventActivityIdControl
0x18002cf0f  jmp     short loc_18002CF18
0x18002cf11  xorps   xmm0, xmm0
0x18002cf14  movups  xmmword ptr [rdi+8], xmm0
0x18002cf18  mov     dword ptr [rdi], 1
0x18002cf1e  lea     rcx, [rsp+38h+arg_0]
0x18002cf23  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002cf28  call    ?Provider@AccountsControlAPITelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountsControlAPITelemetry::Provider(void)
0x18002cf2d  mov     rdi, rax
0x18002cf30  mov     ecx, [rax]
0x18002cf32  cmp     ecx, 5
0x18002cf35  jbe     short loc_18002CFA7
0x18002cf37  mov     rdx, 400000000000h
0x18002cf41  mov     rcx, rax
0x18002cf44  call    _tlgKeywordOn
0x18002cf49  test    al, al
0x18002cf4b  jz      short loc_18002CFA7
0x18002cf4d  call    cs:__imp_GetCurrentThreadId
0x18002cf53  mov     [rsp+38h+arg_0], eax
0x18002cf57  mov     [rsp+38h+arg_8], 3000000h
0x18002cf60  mov     r8, [rbx+110h]
0x18002cf67  cmp     byte ptr [r8+4], 0
0x18002cf6c  jz      short loc_18002CF7B
0x18002cf6e  lea     rcx, [r8+18h]; struct _GUID *
0x18002cf72  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x18002cf77  test    al, al
0x18002cf79  jz      short loc_18002CF7D
0x18002cf7b  xor     ecx, ecx
0x18002cf7d  add     r8, 8
0x18002cf81  lea     rax, [rsp+38h+arg_0]
0x18002cf86  mov     [rsp+38h+var_10], rax
0x18002cf8b  lea     rax, [rsp+38h+arg_8]
0x18002cf90  mov     [rsp+38h+var_18], rax
0x18002cf95  mov     r9, rcx
0x18002cf98  lea     rdx, unk_18009EE18
0x18002cf9f  mov     rcx, rdi
0x18002cfa2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002cfa7  lea     rcx, [rbx+120h]; this
0x18002cfae  cmp     dword ptr [rcx+18h], 0
0x18002cfb2  jnz     short loc_18002CFBA
0x18002cfb4  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18002cfb9  nop
0x18002cfba  mov     rbx, [rsp+38h+arg_10]
0x18002cfbf  add     rsp, 30h
0x18002cfc3  pop     rdi
0x18002cfc4  retn
```
