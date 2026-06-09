# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x180036fcc`
- end: `0x1800370ed`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `289`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180038aac`

## callees

- `0x18000b520`
- `0x18000c1b0`
- `0x18000cb30`
- `0x180010970`
- `0x1800187bc`
- `0x18002009c`
- `0x1800357d8`
- `0x180036fcc`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180037014`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180037014`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180037076`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037065`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037065`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(
        Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *this,
        HSTRING a2)
{
  __int64 v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  const struct _tlgProvider_t *v6; // rax
  int v7; // edi
  DWORD CurrentThreadId; // eax
  int v9; // eax
  DWORD v10; // [rsp+60h] [rbp+8h] BYREF
  PCWSTR StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
  __int64 v12; // [rsp+78h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &v10);
  v4 = *((_QWORD *)this + 34);
  v5 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v4 + 8));
  else
    *(_OWORD *)(v4 + 8) = 0;
  *(_DWORD *)v4 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  v6 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v7 = (int)v6;
  if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x200000000000LL) )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v12 = 0;
    v10 = CurrentThreadId;
    v9 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(this);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v7,
      (unsigned int)&unk_180052BD8,
      *((_QWORD *)this + 34) + 8,
      v9,
      (__int64)&v12,
      (__int64)&v10,
      (__int64)&StringRawBuffer);
  }
  if ( !*((_DWORD *)this + 78) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *)((char *)this + 288));
}

```

## disassembly

```asm
0x180036fcc  push    rbx
0x180036fce  push    rsi
0x180036fcf  push    rdi
0x180036fd0  sub     rsp, 40h
0x180036fd4  mov     rsi, rdx
0x180036fd7  mov     rbx, rcx
0x180036fda  lea     rdx, [rsp+58h+arg_0]
0x180036fdf  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036fe4  mov     rdi, [rbx+110h]
0x180036feb  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036ff0  cmp     dword ptr [rax], 5
0x180036ff3  jbe     short loc_180037022
0x180036ff5  mov     rdx, 200000000000h
0x180036fff  mov     rcx, rax
0x180037002  call    _tlgKeywordOn
0x180037007  test    al, al
0x180037009  jz      short loc_180037022
0x18003700b  lea     rdx, [rdi+8]; ActivityId
0x18003700f  mov     ecx, 3; ControlCode
0x180037014  call    cs:__imp_EventActivityIdControl
0x18003701b  nop     dword ptr [rax+rax+00h]
0x180037020  jmp     short loc_180037029
0x180037022  xorps   xmm0, xmm0
0x180037025  movups  xmmword ptr [rdi+8], xmm0
0x180037029  lea     rcx, [rsp+58h+arg_0]
0x18003702e  mov     dword ptr [rdi], 1
0x180037034  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180037039  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003703e  mov     rdi, rax
0x180037041  cmp     dword ptr [rax], 5
0x180037044  jbe     loc_1800370CF
0x18003704a  mov     rdx, 200000000000h
0x180037054  mov     rcx, rax
0x180037057  call    _tlgKeywordOn
0x18003705c  test    al, al
0x18003705e  jz      short loc_1800370CF
0x180037060  xor     edx, edx; length
0x180037062  mov     rcx, rsi; string
0x180037065  call    cs:__imp_WindowsGetStringRawBuffer
0x18003706c  nop     dword ptr [rax+rax+00h]
0x180037071  mov     [rsp+58h+arg_10], rax
0x180037076  call    cs:__imp_GetCurrentThreadId
0x18003707d  nop     dword ptr [rax+rax+00h]
0x180037082  and     [rsp+58h+arg_18], 0
0x180037088  mov     rcx, rbx
0x18003708b  mov     [rsp+58h+arg_0], eax
0x18003708f  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180037094  mov     r8, [rbx+110h]
0x18003709b  lea     rcx, [rsp+58h+arg_10]
0x1800370a0  mov     [rsp+58h+var_28], rcx
0x1800370a5  lea     rdx, unk_180052BD8
0x1800370ac  lea     rcx, [rsp+58h+arg_0]
0x1800370b1  add     r8, 8
0x1800370b5  mov     [rsp+58h+var_30], rcx
0x1800370ba  mov     r9, rax
0x1800370bd  lea     rcx, [rsp+58h+arg_18]
0x1800370c2  mov     [rsp+58h+var_38], rcx
0x1800370c7  mov     rcx, rdi
0x1800370ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800370cf  cmp     dword ptr [rbx+138h], 0
0x1800370d6  jnz     short loc_1800370E4
0x1800370d8  lea     rcx, [rbx+120h]; this
0x1800370df  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800370e4  add     rsp, 40h
0x1800370e8  pop     rdi
0x1800370e9  pop     rsi
0x1800370ea  pop     rbx
0x1800370eb  retn
```
