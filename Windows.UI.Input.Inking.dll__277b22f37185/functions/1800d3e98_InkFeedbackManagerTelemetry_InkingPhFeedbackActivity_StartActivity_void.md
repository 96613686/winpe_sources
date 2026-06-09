# InkFeedbackManagerTelemetry::InkingPhFeedbackActivity::StartActivity(void)

- ea: `0x1800d3e98`
- end: `0x1800d3f9d`
- name: `?StartActivity@InkingPhFeedbackActivity@InkFeedbackManagerTelemetry@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(InkFeedbackManagerTelemetry::InkingPhFeedbackActivity *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800d3fa4`

## callees

- `0x180001b9c`
- `0x180003838`
- `0x18000bed8`
- `0x18003add0`
- `0x18003c808`
- `0x18003cfc4`
- `0x1800d3cc0`
- `0x1800d3e98`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d3ee1`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800d3ee1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3f25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800d3f25`

## pseudocode

```c
void __fastcall InkFeedbackManagerTelemetry::InkingPhFeedbackActivity::StartActivity(
        InkFeedbackManagerTelemetry::InkingPhFeedbackActivity *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  __int64 v4; // r8
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // rdx
  __int64 v7; // r8
  int v8; // edi
  __int64 v9; // r8
  int v10; // ecx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<InkFeedbackManagerLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = InkFeedbackManagerLogging::Provider();
  if ( *(_DWORD *)v3 > 5u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL, v4) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&CurrentThreadId);
  v5 = InkFeedbackManagerLogging::Provider();
  v8 = (int)v5;
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x400000000000LL, v7) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v12 = 0x2000000;
    v9 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v8,
      (unsigned int)byte_1801414E5,
      v9 + 8,
      v10,
      (__int64)&v12,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (InkFeedbackManagerTelemetry::InkingPhFeedbackActivity *)((char *)this + 288),
      v6);
}

```

## disassembly

```asm
0x1800d3e98  mov     [rsp+arg_10], rbx
0x1800d3e9d  push    rdi
0x1800d3e9e  sub     rsp, 30h
0x1800d3ea2  mov     rbx, rcx
0x1800d3ea5  lea     rdx, [rsp+38h+arg_0]
0x1800d3eaa  call    ?LockExclusive@?$ActivityBase@VInkFeedbackManagerLogging@@$00$0EAAAAAAAAAAA@$04$0CAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<InkFeedbackManagerLogging,1,70368744177664,5,33554432,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800d3eaf  mov     rdi, [rbx+110h]
0x1800d3eb6  call    ?Provider@InkFeedbackManagerLogging@@SAPEBU_tlgProvider_t@@XZ; InkFeedbackManagerLogging::Provider(void)
0x1800d3ebb  mov     edx, [rax]
0x1800d3ebd  cmp     edx, 5
0x1800d3ec0  jbe     short loc_1800D3EE9
0x1800d3ec2  mov     rdx, 400000000000h
0x1800d3ecc  mov     rcx, rax
0x1800d3ecf  call    _tlgKeywordOn
0x1800d3ed4  test    al, al
0x1800d3ed6  jz      short loc_1800D3EE9
0x1800d3ed8  lea     rdx, [rdi+8]; ActivityId
0x1800d3edc  mov     ecx, 3; ControlCode
0x1800d3ee1  call    cs:__imp_EventActivityIdControl
0x1800d3ee7  jmp     short loc_1800D3EF0
0x1800d3ee9  xorps   xmm0, xmm0
0x1800d3eec  movups  xmmword ptr [rdi+8], xmm0
0x1800d3ef0  mov     dword ptr [rdi], 1
0x1800d3ef6  lea     rcx, [rsp+38h+arg_0]
0x1800d3efb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800d3f00  call    ?Provider@InkFeedbackManagerLogging@@SAPEBU_tlgProvider_t@@XZ; InkFeedbackManagerLogging::Provider(void)
0x1800d3f05  mov     rdi, rax
0x1800d3f08  mov     ecx, [rax]
0x1800d3f0a  cmp     ecx, 5
0x1800d3f0d  jbe     short loc_1800D3F7F
0x1800d3f0f  mov     rdx, 400000000000h
0x1800d3f19  mov     rcx, rax
0x1800d3f1c  call    _tlgKeywordOn
0x1800d3f21  test    al, al
0x1800d3f23  jz      short loc_1800D3F7F
0x1800d3f25  call    cs:__imp_GetCurrentThreadId
0x1800d3f2b  mov     [rsp+38h+arg_0], eax
0x1800d3f2f  mov     [rsp+38h+arg_8], 2000000h
0x1800d3f38  mov     r8, [rbx+110h]
0x1800d3f3f  cmp     byte ptr [r8+4], 0
0x1800d3f44  jz      short loc_1800D3F53
0x1800d3f46  lea     rcx, [r8+18h]; struct _GUID *
0x1800d3f4a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800d3f4f  test    al, al
0x1800d3f51  jz      short loc_1800D3F55
0x1800d3f53  xor     ecx, ecx
0x1800d3f55  add     r8, 8
0x1800d3f59  lea     rax, [rsp+38h+arg_0]
0x1800d3f5e  mov     [rsp+38h+var_10], rax
0x1800d3f63  lea     rax, [rsp+38h+arg_8]
0x1800d3f68  mov     [rsp+38h+var_18], rax
0x1800d3f6d  mov     r9, rcx
0x1800d3f70  lea     rdx, byte_1801414E5
0x1800d3f77  mov     rcx, rdi
0x1800d3f7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800d3f7f  lea     rcx, [rbx+120h]; this
0x1800d3f86  cmp     dword ptr [rcx+18h], 0
0x1800d3f8a  jnz     short loc_1800D3F92
0x1800d3f8c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800d3f91  nop
0x1800d3f92  mov     rbx, [rsp+38h+arg_10]
0x1800d3f97  add     rsp, 30h
0x1800d3f9b  pop     rdi
0x1800d3f9c  retn
```
