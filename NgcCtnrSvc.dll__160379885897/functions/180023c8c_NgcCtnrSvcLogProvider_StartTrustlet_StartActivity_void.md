# NgcCtnrSvcLogProvider::StartTrustlet::StartActivity(void)

- ea: `0x180023c8c`
- end: `0x180023d9e`
- name: `?StartActivity@StartTrustlet@NgcCtnrSvcLogProvider@@QEAAXXZ`
- size: `274`
- prototype: `void __fastcall(NgcCtnrSvcLogProvider::StartTrustlet *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180023a88`

## callees

- `0x1800023b4`
- `0x180012e40`
- `0x1800190b4`
- `0x180019b48`
- `0x18001ced8`
- `0x180023c8c`
- `0x180024b04`
- `0x18003a780`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023d1f`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023cd5`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180023cd5`

## pseudocode

```c
void __fastcall NgcCtnrSvcLogProvider::StartTrustlet::StartActivity(NgcCtnrSvcLogProvider::StartTrustlet *this)
{
  __int64 v2; // rdi
  const struct _tlgProvider_t *v3; // rax
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rcx
  DWORD CurrentThreadId; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+48h] [rbp+10h] BYREF

  wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &CurrentThreadId);
  v2 = *((_QWORD *)this + 34);
  v3 = NgcCtnrSvcLogProvider::Provider();
  if ( *(_DWORD *)v3 > 4u && (unsigned __int8)tlgKeywordOn(v3, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v2 + 8));
  else
    *(_OWORD *)(v2 + 8) = 0;
  *(_DWORD *)v2 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&CurrentThreadId);
  v4 = NgcCtnrSvcLogProvider::Provider();
  v6 = (__int64)v4;
  if ( *(_DWORD *)v4 > 4u && (unsigned __int8)tlgKeywordOn(v4, 0x400000000000LL) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v10 = 0x1000000;
    v7 = *((_QWORD *)this + 34);
    if ( !*(_BYTE *)(v7 + 4) || _tlgGuidIsZero((const struct _GUID *)(v7 + 24)) )
      v8 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v6,
      (__int64)&byte_1800A8DE7,
      v7 + 8,
      v8,
      (__int64)&v10,
      (__int64)&CurrentThreadId);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching(
      (NgcCtnrSvcLogProvider::StartTrustlet *)((char *)this + 288),
      v5);
}

```

## disassembly

```asm
0x180023c8c  mov     [rsp+arg_10], rbx
0x180023c91  push    rdi
0x180023c92  sub     rsp, 30h
0x180023c96  mov     rbx, rcx
0x180023c99  lea     rdx, [rsp+38h+arg_0]
0x180023c9e  call    ?LockExclusive@?$ActivityBase@VNgcCtnrSvcLogProvider@@$00$0EAAAAAAAAAAA@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<NgcCtnrSvcLogProvider,1,70368744177664,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180023ca3  mov     rdi, [rbx+110h]
0x180023caa  call    ?Provider@NgcCtnrSvcLogProvider@@SAPEBU_tlgProvider_t@@XZ; NgcCtnrSvcLogProvider::Provider(void)
0x180023caf  mov     edx, [rax]
0x180023cb1  cmp     edx, 4
0x180023cb4  jbe     short loc_180023CE3
0x180023cb6  mov     rdx, 400000000000h
0x180023cc0  mov     rcx, rax
0x180023cc3  call    _tlgKeywordOn
0x180023cc8  test    al, al
0x180023cca  jz      short loc_180023CE3
0x180023ccc  lea     rdx, [rdi+8]; ActivityId
0x180023cd0  mov     ecx, 3; ControlCode
0x180023cd5  call    cs:__imp_EventActivityIdControl
0x180023cdc  nop     dword ptr [rax+rax+00h]
0x180023ce1  jmp     short loc_180023CEA
0x180023ce3  xorps   xmm0, xmm0
0x180023ce6  movups  xmmword ptr [rdi+8], xmm0
0x180023cea  mov     dword ptr [rdi], 1
0x180023cf0  lea     rcx, [rsp+38h+arg_0]
0x180023cf5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180023cfa  call    ?Provider@NgcCtnrSvcLogProvider@@SAPEBU_tlgProvider_t@@XZ; NgcCtnrSvcLogProvider::Provider(void)
0x180023cff  mov     rdi, rax
0x180023d02  mov     ecx, [rax]
0x180023d04  cmp     ecx, 4
0x180023d07  jbe     short loc_180023D7F
0x180023d09  mov     rdx, 400000000000h
0x180023d13  mov     rcx, rax
0x180023d16  call    _tlgKeywordOn
0x180023d1b  test    al, al
0x180023d1d  jz      short loc_180023D7F
0x180023d1f  call    cs:__imp_GetCurrentThreadId
0x180023d26  nop     dword ptr [rax+rax+00h]
0x180023d2b  mov     [rsp+38h+arg_0], eax
0x180023d2f  mov     [rsp+38h+arg_8], 1000000h
0x180023d38  mov     r8, [rbx+110h]
0x180023d3f  cmp     byte ptr [r8+4], 0
0x180023d44  jz      short loc_180023D53
0x180023d46  lea     rcx, [r8+18h]; struct _GUID *
0x180023d4a  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180023d4f  test    al, al
0x180023d51  jz      short loc_180023D55
0x180023d53  xor     ecx, ecx
0x180023d55  add     r8, 8
0x180023d59  lea     rax, [rsp+38h+arg_0]
0x180023d5e  mov     [rsp+38h+var_10], rax
0x180023d63  lea     rax, [rsp+38h+arg_8]
0x180023d68  mov     [rsp+38h+var_18], rax
0x180023d6d  mov     r9, rcx
0x180023d70  lea     rdx, byte_1800A8DE7
0x180023d77  mov     rcx, rdi
0x180023d7a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180023d7f  lea     rcx, [rbx+120h]; this
0x180023d86  cmp     dword ptr [rcx+18h], 0
0x180023d8a  jnz     short loc_180023D92
0x180023d8c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180023d91  nop
0x180023d92  mov     rbx, [rsp+38h+arg_10]
0x180023d97  add     rsp, 30h
0x180023d9b  pop     rdi
0x180023d9c  retn
```
