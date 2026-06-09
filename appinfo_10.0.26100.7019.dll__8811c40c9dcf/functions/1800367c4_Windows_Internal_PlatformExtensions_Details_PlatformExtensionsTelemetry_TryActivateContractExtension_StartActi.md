# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x1800367c4`
- end: `0x180036925`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `353`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x1800380c0`

## callees

- `0x18000337c`
- `0x18000b520`
- `0x18000cb30`
- `0x180010830`
- `0x18001850c`
- `0x180021310`
- `0x180035728`
- `0x1800367c4`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036824`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036824`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003688f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003688f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003687f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003687f`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rsi
  const struct _tlgProvider_t *v9; // rax
  const struct _tlgProvider_t *v10; // rax
  int v11; // esi
  int v12; // eax
  DWORD CurrentThreadId; // [rsp+50h] [rbp-20h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-10h] BYREF
  __int64 v16; // [rsp+68h] [rbp-8h] BYREF
  int v17; // [rsp+90h] [rbp+20h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v17);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = (int)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
  {
    v14 = a4;
    v17 = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    v16 = 0;
    CurrentThreadId = GetCurrentThreadId();
    v12 = wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(a1);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v11,
      (unsigned int)&unk_18004FEBE,
      *(_QWORD *)(a1 + 272) + 8,
      v12,
      (__int64)&v16,
      (__int64)&CurrentThreadId,
      (__int64)&StringRawBuffer,
      (__int64)&v17,
      (__int64)&v14);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x1800367c4  mov     [rsp-18h+arg_8], rbx
0x1800367c9  mov     [rsp-18h+arg_10], rsi
0x1800367ce  mov     [rsp-18h+arg_18], rdi
0x1800367d3  push    rbp
0x1800367d4  push    r14
0x1800367d6  push    r15
0x1800367d8  mov     rbp, rsp
0x1800367db  sub     rsp, 70h
0x1800367df  mov     r15, rdx
0x1800367e2  mov     r14, r9
0x1800367e5  lea     rdx, [rbp+arg_0]
0x1800367e9  mov     ebx, r8d
0x1800367ec  mov     rdi, rcx
0x1800367ef  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800367f4  mov     rsi, [rdi+110h]
0x1800367fb  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036800  cmp     dword ptr [rax], 5
0x180036803  jbe     short loc_180036832
0x180036805  mov     rdx, 400000000000h
0x18003680f  mov     rcx, rax
0x180036812  call    _tlgKeywordOn
0x180036817  test    al, al
0x180036819  jz      short loc_180036832
0x18003681b  lea     rdx, [rsi+8]; ActivityId
0x18003681f  mov     ecx, 3; ControlCode
0x180036824  call    cs:__imp_EventActivityIdControl
0x18003682b  nop     dword ptr [rax+rax+00h]
0x180036830  jmp     short loc_180036839
0x180036832  xorps   xmm0, xmm0
0x180036835  movups  xmmword ptr [rsi+8], xmm0
0x180036839  lea     rcx, [rbp+arg_0]
0x18003683d  mov     dword ptr [rsi], 1
0x180036843  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180036848  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003684d  mov     rsi, rax
0x180036850  cmp     dword ptr [rax], 5
0x180036853  jbe     loc_1800368F5
0x180036859  mov     rdx, 400000000000h
0x180036863  mov     rcx, rax
0x180036866  call    _tlgKeywordOn
0x18003686b  test    al, al
0x18003686d  jz      loc_1800368F5
0x180036873  xor     edx, edx; length
0x180036875  mov     [rbp+var_18], r14
0x180036879  mov     rcx, r15; string
0x18003687c  mov     [rbp+arg_0], ebx
0x18003687f  call    cs:__imp_WindowsGetStringRawBuffer
0x180036886  nop     dword ptr [rax+rax+00h]
0x18003688b  mov     [rbp+var_10], rax
0x18003688f  call    cs:__imp_GetCurrentThreadId
0x180036896  nop     dword ptr [rax+rax+00h]
0x18003689b  and     [rbp+var_8], 0
0x1800368a0  mov     rcx, rdi
0x1800368a3  mov     [rbp+var_20], eax
0x1800368a6  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x1800368ab  mov     r8, [rdi+110h]
0x1800368b2  lea     rcx, [rbp+var_18]
0x1800368b6  mov     [rsp+70h+var_30], rcx
0x1800368bb  lea     rdx, unk_18004FEBE
0x1800368c2  lea     rcx, [rbp+arg_0]
0x1800368c6  add     r8, 8
0x1800368ca  mov     [rsp+70h+var_38], rcx
0x1800368cf  mov     r9, rax
0x1800368d2  lea     rcx, [rbp+var_10]
0x1800368d6  mov     [rsp+70h+var_40], rcx
0x1800368db  lea     rcx, [rbp+var_20]
0x1800368df  mov     [rsp+70h+var_48], rcx
0x1800368e4  lea     rcx, [rbp+var_8]
0x1800368e8  mov     [rsp+70h+var_50], rcx
0x1800368ed  mov     rcx, rsi
0x1800368f0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800368f5  cmp     dword ptr [rdi+138h], 0
0x1800368fc  jnz     short loc_18003690A
0x1800368fe  lea     rcx, [rdi+120h]; this
0x180036905  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18003690a  lea     r11, [rsp+70h+var_s0]
0x18003690f  mov     rbx, [r11+28h]
0x180036913  mov     rsi, [r11+30h]
0x180036917  mov     rdi, [r11+38h]
0x18003691b  mov     rsp, r11
0x18003691e  pop     r15
0x180036920  pop     r14
0x180036922  pop     rbp
0x180036923  retn
```
