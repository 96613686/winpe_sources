# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x180039a50`
- end: `0x180039b72`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `290`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b818`

## callees

- `0x18000b330`
- `0x18000bb70`
- `0x180010490`
- `0x180011910`
- `0x180011fd0`
- `0x18001a35c`
- `0x1800384dc`
- `0x180039a50`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039a9c`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039a9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039af4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039af4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039ae9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180039ae9`

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
  const GUID *v10; // rcx
  RTL_SRWLOCK *v11; // [rsp+60h] [rbp+8h] BYREF
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
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (__int64)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v9 = *((_QWORD *)this + 34);
    LODWORD(v11) = CurrentThreadId;
    v13 = 0;
    if ( !*(_BYTE *)(v9 + 4) || _tlgGuidIsZero((const struct _GUID *)(v9 + 24)) )
      v10 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned __int8 *)&word_180054EB6,
      (const GUID *)(v9 + 8),
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
0x180039a50  push    rbx
0x180039a52  push    rsi
0x180039a53  push    rdi
0x180039a54  sub     rsp, 40h
0x180039a58  mov     rsi, rdx
0x180039a5b  mov     rdi, rcx
0x180039a5e  lea     rdx, [rsp+58h+arg_0]
0x180039a63  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180039a68  mov     rbx, [rdi+110h]
0x180039a6f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180039a74  mov     r8d, [rax]
0x180039a77  cmp     r8d, 5
0x180039a7b  jbe     short loc_180039AA4
0x180039a7d  mov     rdx, 200000000000h
0x180039a87  mov     rcx, rax
0x180039a8a  call    _tlgKeywordOn
0x180039a8f  test    al, al
0x180039a91  jz      short loc_180039AA4
0x180039a93  lea     rdx, [rbx+8]; ActivityId
0x180039a97  mov     ecx, 3; ControlCode
0x180039a9c  call    cs:__imp_EventActivityIdControl
0x180039aa2  jmp     short loc_180039AAB
0x180039aa4  xorps   xmm0, xmm0
0x180039aa7  movups  xmmword ptr [rbx+8], xmm0
0x180039aab  lea     rcx, [rsp+58h+arg_0]
0x180039ab0  mov     dword ptr [rbx], 1
0x180039ab6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180039abb  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180039ac0  mov     rbx, rax
0x180039ac3  mov     ecx, [rax]
0x180039ac5  cmp     ecx, 5
0x180039ac8  jbe     loc_180039B58
0x180039ace  mov     rdx, 200000000000h
0x180039ad8  mov     rcx, rax
0x180039adb  call    _tlgKeywordOn
0x180039ae0  test    al, al
0x180039ae2  jz      short loc_180039B58
0x180039ae4  xor     edx, edx; length
0x180039ae6  mov     rcx, rsi; string
0x180039ae9  call    cs:__imp_WindowsGetStringRawBuffer
0x180039aef  mov     [rsp+58h+arg_10], rax
0x180039af4  call    cs:__imp_GetCurrentThreadId
0x180039afa  mov     r8, [rdi+110h]
0x180039b01  mov     dword ptr [rsp+58h+arg_0], eax
0x180039b05  mov     [rsp+58h+arg_18], 0
0x180039b0e  cmp     byte ptr [r8+4], 0
0x180039b13  jz      short loc_180039B22
0x180039b15  lea     rcx, [r8+18h]; struct _GUID *
0x180039b19  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180039b1e  test    al, al
0x180039b20  jz      short loc_180039B24
0x180039b22  xor     ecx, ecx
0x180039b24  lea     rax, [rsp+58h+arg_10]
0x180039b29  mov     r9, rcx
0x180039b2c  mov     [rsp+58h+var_28], rax
0x180039b31  lea     rdx, word_180054EB6
0x180039b38  lea     rax, [rsp+58h+arg_0]
0x180039b3d  add     r8, 8
0x180039b41  mov     [rsp+58h+var_30], rax
0x180039b46  mov     rcx, rbx
0x180039b49  lea     rax, [rsp+58h+arg_18]
0x180039b4e  mov     [rsp+58h+var_38], rax
0x180039b53  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180039b58  lea     rcx, [rdi+120h]; this
0x180039b5f  cmp     dword ptr [rcx+18h], 0
0x180039b63  jnz     short loc_180039B6A
0x180039b65  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180039b6a  add     rsp, 40h
0x180039b6e  pop     rdi
0x180039b6f  pop     rsi
0x180039b70  pop     rbx
0x180039b71  retn
```
