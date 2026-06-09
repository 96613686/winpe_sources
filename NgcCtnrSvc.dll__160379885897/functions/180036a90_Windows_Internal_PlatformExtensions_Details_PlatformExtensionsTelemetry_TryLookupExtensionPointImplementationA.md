# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x180036a90`
- end: `0x180036bc9`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `313`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180014838`

## callees

- `0x180002184`
- `0x180012e40`
- `0x180016f70`
- `0x1800189f4`
- `0x180019b48`
- `0x18001ced8`
- `0x180024b04`
- `0x180036a90`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036b44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036b44`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036adc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036adc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036b33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036b33`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  __int64 v10; // rcx
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v11);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v11);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    v11 = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (__int64)word_1800A7C1A,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      &StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x180036a90  push    rbx
0x180036a92  push    rsi
0x180036a93  push    rdi
0x180036a94  sub     rsp, 40h
0x180036a98  mov     rsi, rdx
0x180036a9b  mov     rdi, rcx
0x180036a9e  lea     rdx, [rsp+58h+arg_0]
0x180036aa3  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036aa8  mov     rbx, [rdi+110h]
0x180036aaf  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036ab4  mov     r8d, [rax]
0x180036ab7  cmp     r8d, 5
0x180036abb  jbe     short loc_180036AEA
0x180036abd  mov     rdx, 200000000000h
0x180036ac7  mov     rcx, rax
0x180036aca  call    _tlgKeywordOn
0x180036acf  test    al, al
0x180036ad1  jz      short loc_180036AEA
0x180036ad3  lea     rdx, [rbx+8]; ActivityId
0x180036ad7  mov     ecx, 3; ControlCode
0x180036adc  call    cs:__imp_EventActivityIdControl
0x180036ae3  nop     dword ptr [rax+rax+00h]
0x180036ae8  jmp     short loc_180036AF1
0x180036aea  xorps   xmm0, xmm0
0x180036aed  movups  xmmword ptr [rbx+8], xmm0
0x180036af1  lea     rcx, [rsp+58h+arg_0]
0x180036af6  mov     dword ptr [rbx], 1
0x180036afc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180036b01  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036b06  mov     rbx, rax
0x180036b09  mov     ecx, [rax]
0x180036b0b  cmp     ecx, 5
0x180036b0e  jbe     loc_180036BAE
0x180036b14  mov     rdx, 200000000000h
0x180036b1e  mov     rcx, rax
0x180036b21  call    _tlgKeywordOn
0x180036b26  test    al, al
0x180036b28  jz      loc_180036BAE
0x180036b2e  xor     edx, edx; length
0x180036b30  mov     rcx, rsi; string
0x180036b33  call    cs:__imp_WindowsGetStringRawBuffer
0x180036b3a  nop     dword ptr [rax+rax+00h]
0x180036b3f  mov     [rsp+58h+arg_10], rax
0x180036b44  call    cs:__imp_GetCurrentThreadId
0x180036b4b  nop     dword ptr [rax+rax+00h]
0x180036b50  mov     r8, [rdi+110h]
0x180036b57  mov     [rsp+58h+arg_0], eax
0x180036b5b  mov     [rsp+58h+arg_18], 0
0x180036b64  cmp     byte ptr [r8+4], 0
0x180036b69  jz      short loc_180036B78
0x180036b6b  lea     rcx, [r8+18h]; struct _GUID *
0x180036b6f  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180036b74  test    al, al
0x180036b76  jz      short loc_180036B7A
0x180036b78  xor     ecx, ecx
0x180036b7a  lea     rax, [rsp+58h+arg_10]
0x180036b7f  mov     r9, rcx
0x180036b82  mov     [rsp+58h+var_28], rax
0x180036b87  lea     rdx, word_1800A7C1A
0x180036b8e  lea     rax, [rsp+58h+arg_0]
0x180036b93  add     r8, 8
0x180036b97  mov     [rsp+58h+var_30], rax
0x180036b9c  mov     rcx, rbx
0x180036b9f  lea     rax, [rsp+58h+arg_18]
0x180036ba4  mov     [rsp+58h+var_38], rax
0x180036ba9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180036bae  lea     rcx, [rdi+120h]; this
0x180036bb5  cmp     dword ptr [rcx+18h], 0
0x180036bb9  jnz     short loc_180036BC0
0x180036bbb  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180036bc0  add     rsp, 40h
0x180036bc4  pop     rdi
0x180036bc5  pop     rsi
0x180036bc6  pop     rbx
0x180036bc7  retn
```
