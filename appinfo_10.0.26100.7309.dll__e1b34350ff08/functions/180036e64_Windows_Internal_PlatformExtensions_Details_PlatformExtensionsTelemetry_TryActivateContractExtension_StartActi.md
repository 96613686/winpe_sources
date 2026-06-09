# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x180036e64`
- end: `0x180036fc5`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `353`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180038760`

## callees

- `0x18000337c`
- `0x18000b520`
- `0x18000cb30`
- `0x180010970`
- `0x1800187bc`
- `0x18002009c`
- `0x1800357d8`
- `0x180036e64`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036ec4`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180036ec4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036f2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180036f2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f1f`

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
      (unsigned int)&unk_1800511D9,
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
0x180036e64  mov     [rsp-18h+arg_8], rbx
0x180036e69  mov     [rsp-18h+arg_10], rsi
0x180036e6e  mov     [rsp-18h+arg_18], rdi
0x180036e73  push    rbp
0x180036e74  push    r14
0x180036e76  push    r15
0x180036e78  mov     rbp, rsp
0x180036e7b  sub     rsp, 70h
0x180036e7f  mov     r15, rdx
0x180036e82  mov     r14, r9
0x180036e85  lea     rdx, [rbp+arg_0]
0x180036e89  mov     ebx, r8d
0x180036e8c  mov     rdi, rcx
0x180036e8f  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180036e94  mov     rsi, [rdi+110h]
0x180036e9b  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036ea0  cmp     dword ptr [rax], 5
0x180036ea3  jbe     short loc_180036ED2
0x180036ea5  mov     rdx, 400000000000h
0x180036eaf  mov     rcx, rax
0x180036eb2  call    _tlgKeywordOn
0x180036eb7  test    al, al
0x180036eb9  jz      short loc_180036ED2
0x180036ebb  lea     rdx, [rsi+8]; ActivityId
0x180036ebf  mov     ecx, 3; ControlCode
0x180036ec4  call    cs:__imp_EventActivityIdControl
0x180036ecb  nop     dword ptr [rax+rax+00h]
0x180036ed0  jmp     short loc_180036ED9
0x180036ed2  xorps   xmm0, xmm0
0x180036ed5  movups  xmmword ptr [rsi+8], xmm0
0x180036ed9  lea     rcx, [rbp+arg_0]
0x180036edd  mov     dword ptr [rsi], 1
0x180036ee3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180036ee8  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180036eed  mov     rsi, rax
0x180036ef0  cmp     dword ptr [rax], 5
0x180036ef3  jbe     loc_180036F95
0x180036ef9  mov     rdx, 400000000000h
0x180036f03  mov     rcx, rax
0x180036f06  call    _tlgKeywordOn
0x180036f0b  test    al, al
0x180036f0d  jz      loc_180036F95
0x180036f13  xor     edx, edx; length
0x180036f15  mov     [rbp+var_18], r14
0x180036f19  mov     rcx, r15; string
0x180036f1c  mov     [rbp+arg_0], ebx
0x180036f1f  call    cs:__imp_WindowsGetStringRawBuffer
0x180036f26  nop     dword ptr [rax+rax+00h]
0x180036f2b  mov     [rbp+var_10], rax
0x180036f2f  call    cs:__imp_GetCurrentThreadId
0x180036f36  nop     dword ptr [rax+rax+00h]
0x180036f3b  and     [rbp+var_8], 0
0x180036f40  mov     rcx, rdi
0x180036f43  mov     [rbp+var_20], eax
0x180036f46  call    ?zInternalRelatedId@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalRelatedId(void)
0x180036f4b  mov     r8, [rdi+110h]
0x180036f52  lea     rcx, [rbp+var_18]
0x180036f56  mov     [rsp+70h+var_30], rcx
0x180036f5b  lea     rdx, unk_1800511D9
0x180036f62  lea     rcx, [rbp+arg_0]
0x180036f66  add     r8, 8
0x180036f6a  mov     [rsp+70h+var_38], rcx
0x180036f6f  mov     r9, rax
0x180036f72  lea     rcx, [rbp+var_10]
0x180036f76  mov     [rsp+70h+var_40], rcx
0x180036f7b  lea     rcx, [rbp+var_20]
0x180036f7f  mov     [rsp+70h+var_48], rcx
0x180036f84  lea     rcx, [rbp+var_8]
0x180036f88  mov     [rsp+70h+var_50], rcx
0x180036f8d  mov     rcx, rsi
0x180036f90  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180036f95  cmp     dword ptr [rdi+138h], 0
0x180036f9c  jnz     short loc_180036FAA
0x180036f9e  lea     rcx, [rdi+120h]; this
0x180036fa5  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180036faa  lea     r11, [rsp+70h+var_s0]
0x180036faf  mov     rbx, [r11+28h]
0x180036fb3  mov     rsi, [r11+30h]
0x180036fb7  mov     rdi, [r11+38h]
0x180036fbb  mov     rsp, r11
0x180036fbe  pop     r15
0x180036fc0  pop     r14
0x180036fc2  pop     rbp
0x180036fc3  retn
```
