# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x1800419d4`
- end: `0x180041af6`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `290`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180042b40`

## callees

- `0x18000171c`
- `0x18000257c`
- `0x18000c14c`
- `0x1800123bc`
- `0x180017304`
- `0x180019304`
- `0x180040ccc`
- `0x1800419d4`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a6d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041a6d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180041a20`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180041a20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041a78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041a78`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // ebx
  DWORD CurrentThreadId; // eax
  __int64 v9; // r8
  int v10; // ecx
  DWORD v11; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v11);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (int)v6;
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
      (unsigned int)&word_1800A1B06,
      v9 + 8,
      v10,
      (__int64)&v13,
      (__int64)&v11,
      (__int64)&StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x1800419d4  push    rbx
0x1800419d6  push    rsi
0x1800419d7  push    rdi
0x1800419d8  sub     rsp, 40h
0x1800419dc  mov     rsi, rdx
0x1800419df  mov     rdi, rcx
0x1800419e2  lea     rdx, [rsp+58h+arg_0]
0x1800419e7  call    ?LockExclusive@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800419ec  mov     rbx, [rdi+110h]
0x1800419f3  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800419f8  mov     r8d, [rax]
0x1800419fb  cmp     r8d, 5
0x1800419ff  jbe     short loc_180041A28
0x180041a01  mov     rdx, 200000000000h
0x180041a0b  mov     rcx, rax
0x180041a0e  call    _tlgKeywordOn
0x180041a13  test    al, al
0x180041a15  jz      short loc_180041A28
0x180041a17  lea     rdx, [rbx+8]; ActivityId
0x180041a1b  mov     ecx, 3; ControlCode
0x180041a20  call    cs:__imp_EventActivityIdControl
0x180041a26  jmp     short loc_180041A2F
0x180041a28  xorps   xmm0, xmm0
0x180041a2b  movups  xmmword ptr [rbx+8], xmm0
0x180041a2f  lea     rcx, [rsp+58h+arg_0]
0x180041a34  mov     dword ptr [rbx], 1
0x180041a3a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041a3f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180041a44  mov     rbx, rax
0x180041a47  mov     ecx, [rax]
0x180041a49  cmp     ecx, 5
0x180041a4c  jbe     loc_180041ADC
0x180041a52  mov     rdx, 200000000000h
0x180041a5c  mov     rcx, rax
0x180041a5f  call    _tlgKeywordOn
0x180041a64  test    al, al
0x180041a66  jz      short loc_180041ADC
0x180041a68  xor     edx, edx; length
0x180041a6a  mov     rcx, rsi; string
0x180041a6d  call    cs:__imp_WindowsGetStringRawBuffer
0x180041a73  mov     [rsp+58h+arg_10], rax
0x180041a78  call    cs:__imp_GetCurrentThreadId
0x180041a7e  mov     r8, [rdi+110h]
0x180041a85  mov     [rsp+58h+arg_0], eax
0x180041a89  mov     [rsp+58h+arg_18], 0
0x180041a92  cmp     byte ptr [r8+4], 0
0x180041a97  jz      short loc_180041AA6
0x180041a99  lea     rcx, [r8+18h]; struct _GUID *
0x180041a9d  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180041aa2  test    al, al
0x180041aa4  jz      short loc_180041AA8
0x180041aa6  xor     ecx, ecx
0x180041aa8  lea     rax, [rsp+58h+arg_10]
0x180041aad  mov     r9, rcx
0x180041ab0  mov     [rsp+58h+var_28], rax
0x180041ab5  lea     rdx, word_1800A1B06
0x180041abc  lea     rax, [rsp+58h+arg_0]
0x180041ac1  add     r8, 8
0x180041ac5  mov     [rsp+58h+var_30], rax
0x180041aca  mov     rcx, rbx
0x180041acd  lea     rax, [rsp+58h+arg_18]
0x180041ad2  mov     [rsp+58h+var_38], rax
0x180041ad7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180041adc  lea     rcx, [rdi+120h]; this
0x180041ae3  cmp     dword ptr [rcx+18h], 0
0x180041ae7  jnz     short loc_180041AEE
0x180041ae9  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180041aee  add     rsp, 40h
0x180041af2  pop     rdi
0x180041af3  pop     rsi
0x180041af4  pop     rbx
0x180041af5  retn
```
