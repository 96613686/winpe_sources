# AccountsControlTelemetry::AccountsControlBrokerActivity::StartActivity(uchar)

- ea: `0x180017094`
- end: `0x1800171a6`
- name: `?StartActivity@AccountsControlBrokerActivity@AccountsControlTelemetry@@QEAAXE@Z`
- size: `274`
- prototype: `void __fastcall(AccountsControlTelemetry::AccountsControlBrokerActivity *__hidden this, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800137b0`

## callees

- `0x18000171c`
- `0x1800019a4`
- `0x18000c14c`
- `0x1800123bc`
- `0x1800143ec`
- `0x180017094`
- `0x180017304`
- `0x180019304`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800170e0`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800170e0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017128`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017128`

## pseudocode

```c
void __fastcall AccountsControlTelemetry::AccountsControlBrokerActivity::StartActivity(
        AccountsControlTelemetry::AccountsControlBrokerActivity *this,
        unsigned __int8 a2)
{
  int v2; // esi
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  int v11; // [rsp+60h] [rbp+8h] BYREF
  DWORD v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  v2 = a2;
  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v11);
  v4 = *((_QWORD *)this + 34);
  v5 = AccountsControlTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  v6 = AccountsControlTelemetry::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
  {
    v11 = v2;
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v12 = CurrentThreadId;
    v13 = 50331648;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v7,
      (unsigned int)&word_18009E79E,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v12,
      (__int64)&v11);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((AccountsControlTelemetry::AccountsControlBrokerActivity *)((char *)this + 288));
}

```

## disassembly

```asm
0x180017094  push    rbx
0x180017096  push    rsi
0x180017097  push    rdi
0x180017098  sub     rsp, 40h
0x18001709c  movzx   esi, dl
0x18001709f  mov     rdi, rcx
0x1800170a2  lea     rdx, [rsp+58h+arg_0]
0x1800170a7  call    ?LockExclusive@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800170ac  mov     rbx, [rdi+110h]
0x1800170b3  call    ?Provider@AccountsControlTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountsControlTelemetry::Provider(void)
0x1800170b8  mov     r8d, [rax]
0x1800170bb  cmp     r8d, 5
0x1800170bf  jbe     short loc_1800170E8
0x1800170c1  mov     rdx, 400000000000h
0x1800170cb  mov     rcx, rax
0x1800170ce  call    _tlgKeywordOn
0x1800170d3  test    al, al
0x1800170d5  jz      short loc_1800170E8
0x1800170d7  lea     rdx, [rbx+8]; ActivityId
0x1800170db  mov     ecx, 3; ControlCode
0x1800170e0  call    cs:__imp_EventActivityIdControl
0x1800170e6  jmp     short loc_1800170EF
0x1800170e8  xorps   xmm0, xmm0
0x1800170eb  movups  xmmword ptr [rbx+8], xmm0
0x1800170ef  lea     rcx, [rsp+58h+arg_0]
0x1800170f4  mov     dword ptr [rbx], 1
0x1800170fa  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800170ff  call    ?Provider@AccountsControlTelemetry@@SAPEBU_tlgProvider_t@@XZ; AccountsControlTelemetry::Provider(void)
0x180017104  mov     rbx, rax
0x180017107  mov     ecx, [rax]
0x180017109  cmp     ecx, 5
0x18001710c  jbe     short loc_18001718C
0x18001710e  mov     rdx, 400000000000h
0x180017118  mov     rcx, rax
0x18001711b  call    _tlgKeywordOn
0x180017120  test    al, al
0x180017122  jz      short loc_18001718C
0x180017124  mov     [rsp+58h+arg_0], esi
0x180017128  call    cs:__imp_GetCurrentThreadId
0x18001712e  mov     r8, [rdi+110h]
0x180017135  mov     [rsp+58h+arg_10], eax
0x180017139  mov     [rsp+58h+arg_18], 3000000h
0x180017142  cmp     byte ptr [r8+4], 0
0x180017147  jz      short loc_180017156
0x180017149  lea     rcx, [r8+18h]; struct _GUID *
0x18001714d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180017152  test    al, al
0x180017154  jz      short loc_180017158
0x180017156  xor     ecx, ecx
0x180017158  lea     rax, [rsp+58h+arg_0]
0x18001715d  mov     r9, rcx
0x180017160  mov     [rsp+58h+var_28], rax
0x180017165  lea     rdx, word_18009E79E
0x18001716c  lea     rax, [rsp+58h+arg_10]
0x180017171  add     r8, 8
0x180017175  mov     [rsp+58h+var_30], rax
0x18001717a  mov     rcx, rbx
0x18001717d  lea     rax, [rsp+58h+arg_18]
0x180017182  mov     [rsp+58h+var_38], rax
0x180017187  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001718c  lea     rcx, [rdi+120h]; this
0x180017193  cmp     dword ptr [rcx+18h], 0
0x180017197  jnz     short loc_18001719E
0x180017199  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001719e  add     rsp, 40h
0x1800171a2  pop     rdi
0x1800171a3  pop     rsi
0x1800171a4  pop     rbx
0x1800171a5  retn
```
