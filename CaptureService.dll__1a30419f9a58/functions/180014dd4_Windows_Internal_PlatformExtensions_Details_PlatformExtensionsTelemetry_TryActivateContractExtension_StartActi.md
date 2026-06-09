# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x180014dd4`
- end: `0x180014f2e`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `346`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b7bc`

## callees

- `0x180002314`
- `0x18000254c`
- `0x180005568`
- `0x1800123bc`
- `0x180013130`
- `0x180014dd4`
- `0x180015070`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014e84`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e8e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014e8e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014e2d`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014e2d`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  __int64 v8; // rdi
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r9
  __int64 v11; // r8
  const struct _tlgProvider_t *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v17; // r8
  __int64 v18; // r9
  DWORD v19; // [rsp+50h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-20h] BYREF
  __int64 *StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
  __int64 v22; // [rsp+68h] [rbp-10h] BYREF
  RTL_SRWLOCK *v23; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v23);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = *(unsigned int *)v9;
  if ( (unsigned int)v11 > 5 && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v11, v10) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v23);
  v12 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v15 = (__int64)v12;
  if ( *(_DWORD *)v12 > 5u && (unsigned __int8)tlgKeywordOn(v12, 0x400000000000LL, v13, v14) )
  {
    v20 = a4;
    LODWORD(v23) = a3;
    StringRawBuffer = (__int64 *)WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v17 = *(_QWORD *)(a1 + 272);
    v19 = CurrentThreadId;
    v22 = 0;
    if ( !*(_BYTE *)(v17 + 4)
      || (v18 = v17 + 24, !*(_DWORD *)(v17 + 24))
      && !*(_DWORD *)(v17 + 28)
      && !*(_DWORD *)(v17 + 32)
      && !*(_DWORD *)(v17 + 36) )
    {
      v18 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v15,
      (__int64)byte_1800286B1,
      v17 + 8,
      v18,
      (__int64)&v22,
      (__int64)&v19,
      &StringRawBuffer,
      (__int64)&v23,
      &v20);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180014dd4  push    rbp
0x180014dd6  push    rbx
0x180014dd7  push    rsi
0x180014dd8  push    rdi
0x180014dd9  push    r14
0x180014ddb  push    r15
0x180014ddd  mov     rbp, rsp
0x180014de0  sub     rsp, 78h
0x180014de4  mov     r15, rdx
0x180014de7  mov     r14, r9
0x180014dea  lea     rdx, [rbp+arg_0]
0x180014dee  mov     ebx, r8d
0x180014df1  mov     rsi, rcx
0x180014df4  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014df9  mov     rdi, [rsi+110h]
0x180014e00  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180014e05  mov     r8d, [rax]
0x180014e08  cmp     r8d, 5
0x180014e0c  jbe     short loc_180014E35
0x180014e0e  mov     rdx, 400000000000h
0x180014e18  mov     rcx, rax
0x180014e1b  call    _tlgKeywordOn
0x180014e20  test    al, al
0x180014e22  jz      short loc_180014E35
0x180014e24  lea     rdx, [rdi+8]; ActivityId
0x180014e28  mov     ecx, 3; ControlCode
0x180014e2d  call    cs:__imp_EventActivityIdControl
0x180014e33  jmp     short loc_180014E3C
0x180014e35  xorps   xmm0, xmm0
0x180014e38  movups  xmmword ptr [rdi+8], xmm0
0x180014e3c  lea     rcx, [rbp+arg_0]
0x180014e40  mov     dword ptr [rdi], 1
0x180014e46  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e4b  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180014e50  mov     rdi, rax
0x180014e53  mov     ecx, [rax]
0x180014e55  cmp     ecx, 5
0x180014e58  jbe     loc_180014F0F
0x180014e5e  mov     rdx, 400000000000h
0x180014e68  mov     rcx, rax
0x180014e6b  call    _tlgKeywordOn
0x180014e70  test    al, al
0x180014e72  jz      loc_180014F0F
0x180014e78  xor     edx, edx; length
0x180014e7a  mov     [rbp+var_20], r14
0x180014e7e  mov     rcx, r15; string
0x180014e81  mov     dword ptr [rbp+arg_0], ebx
0x180014e84  call    cs:__imp_WindowsGetStringRawBuffer
0x180014e8a  mov     [rbp+var_18], rax
0x180014e8e  call    cs:__imp_GetCurrentThreadId
0x180014e94  mov     r8, [rsi+110h]
0x180014e9b  mov     [rbp+var_28], eax
0x180014e9e  mov     [rbp+var_10], 0
0x180014ea6  cmp     byte ptr [r8+4], 0
0x180014eab  jz      short loc_180014ECC
0x180014ead  lea     r9, [r8+18h]
0x180014eb1  cmp     dword ptr [r9], 0
0x180014eb5  jnz     short loc_180014ECF
0x180014eb7  cmp     dword ptr [r9+4], 0
0x180014ebc  jnz     short loc_180014ECF
0x180014ebe  cmp     dword ptr [r9+8], 0
0x180014ec3  jnz     short loc_180014ECF
0x180014ec5  cmp     dword ptr [r9+0Ch], 0
0x180014eca  jnz     short loc_180014ECF
0x180014ecc  xor     r9d, r9d
0x180014ecf  lea     rax, [rbp+var_20]
0x180014ed3  add     r8, 8
0x180014ed7  mov     [rsp+78h+var_38], rax
0x180014edc  lea     rdx, byte_1800286B1
0x180014ee3  lea     rax, [rbp+arg_0]
0x180014ee7  mov     rcx, rdi
0x180014eea  mov     [rsp+78h+var_40], rax
0x180014eef  lea     rax, [rbp+var_18]
0x180014ef3  mov     [rsp+78h+var_48], rax
0x180014ef8  lea     rax, [rbp+var_28]
0x180014efc  mov     [rsp+78h+var_50], rax
0x180014f01  lea     rax, [rbp+var_10]
0x180014f05  mov     [rsp+78h+var_58], rax
0x180014f0a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014f0f  lea     rcx, [rsi+120h]; this
0x180014f16  cmp     dword ptr [rcx+18h], 0
0x180014f1a  jnz     short loc_180014F21
0x180014f1c  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180014f21  add     rsp, 78h
0x180014f25  pop     r15
0x180014f27  pop     r14
0x180014f29  pop     rdi
0x180014f2a  pop     rsi
0x180014f2b  pop     rbx
0x180014f2c  pop     rbp
0x180014f2d  retn
```
