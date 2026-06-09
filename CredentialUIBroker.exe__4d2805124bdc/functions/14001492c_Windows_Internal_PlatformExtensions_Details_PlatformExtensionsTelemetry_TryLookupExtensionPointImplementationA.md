# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x14001492c`
- end: `0x140014a4e`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `290`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140017060`

## callees

- `0x140002c90`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x140011aa0`
- `0x14001492c`
- `0x140014a54`
- `0x140018fc0`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140014978`
- `ADVAPI32!EventActivityIdControl` at `0x140014978`
- `KERNEL32!GetCurrentThreadId` at `0x1400149d0`
- `KERNEL32!GetCurrentThreadId` at `0x1400149d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400149c5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1400149c5`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rbx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rbx
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  RTL_SRWLOCK *v15; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v17; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v15);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = *(unsigned int *)v5;
  if ( (unsigned int)v7 > 5 && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v7, v6) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v15);
  v8 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = (__int64)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x200000000000LL, v9, v10) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v15) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v11,
      (__int64)byte_140025DE5,
      v13 + 8,
      v14,
      (__int64)&v17,
      (__int64)&v15,
      &StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x14001492c  push    rbx
0x14001492e  push    rsi
0x14001492f  push    rdi
0x140014930  sub     rsp, 40h
0x140014934  mov     rsi, rdx
0x140014937  mov     rdi, rcx
0x14001493a  lea     rdx, [rsp+58h+arg_0]
0x14001493f  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140014944  mov     rbx, [rdi+110h]
0x14001494b  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140014950  mov     r8d, [rax]
0x140014953  cmp     r8d, 5
0x140014957  jbe     short loc_140014980
0x140014959  mov     rdx, 200000000000h
0x140014963  mov     rcx, rax
0x140014966  call    _tlgKeywordOn
0x14001496b  test    al, al
0x14001496d  jz      short loc_140014980
0x14001496f  lea     rdx, [rbx+8]; ActivityId
0x140014973  mov     ecx, 3; ControlCode
0x140014978  call    cs:__imp_EventActivityIdControl
0x14001497e  jmp     short loc_140014987
0x140014980  xorps   xmm0, xmm0
0x140014983  movups  xmmword ptr [rbx+8], xmm0
0x140014987  lea     rcx, [rsp+58h+arg_0]
0x14001498c  mov     dword ptr [rbx], 1
0x140014992  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140014997  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14001499c  mov     rbx, rax
0x14001499f  mov     ecx, [rax]
0x1400149a1  cmp     ecx, 5
0x1400149a4  jbe     loc_140014A34
0x1400149aa  mov     rdx, 200000000000h
0x1400149b4  mov     rcx, rax
0x1400149b7  call    _tlgKeywordOn
0x1400149bc  test    al, al
0x1400149be  jz      short loc_140014A34
0x1400149c0  xor     edx, edx; length
0x1400149c2  mov     rcx, rsi; string
0x1400149c5  call    cs:__imp_WindowsGetStringRawBuffer
0x1400149cb  mov     [rsp+58h+arg_10], rax
0x1400149d0  call    cs:__imp_GetCurrentThreadId
0x1400149d6  mov     r8, [rdi+110h]
0x1400149dd  mov     dword ptr [rsp+58h+arg_0], eax
0x1400149e1  mov     [rsp+58h+arg_18], 0
0x1400149ea  cmp     byte ptr [r8+4], 0
0x1400149ef  jz      short loc_1400149FE
0x1400149f1  lea     rcx, [r8+18h]; struct _GUID *
0x1400149f5  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400149fa  test    al, al
0x1400149fc  jz      short loc_140014A00
0x1400149fe  xor     ecx, ecx
0x140014a00  lea     rax, [rsp+58h+arg_10]
0x140014a05  mov     r9, rcx
0x140014a08  mov     [rsp+58h+var_28], rax
0x140014a0d  lea     rdx, byte_140025DE5
0x140014a14  lea     rax, [rsp+58h+arg_0]
0x140014a19  add     r8, 8
0x140014a1d  mov     [rsp+58h+var_30], rax
0x140014a22  mov     rcx, rbx
0x140014a25  lea     rax, [rsp+58h+arg_18]
0x140014a2a  mov     [rsp+58h+var_38], rax
0x140014a2f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x140014a34  lea     rcx, [rdi+120h]; this
0x140014a3b  cmp     dword ptr [rcx+18h], 0
0x140014a3f  jnz     short loc_140014A46
0x140014a41  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140014a46  add     rsp, 40h
0x140014a4a  pop     rdi
0x140014a4b  pop     rsi
0x140014a4c  pop     rbx
0x140014a4d  retn
```
