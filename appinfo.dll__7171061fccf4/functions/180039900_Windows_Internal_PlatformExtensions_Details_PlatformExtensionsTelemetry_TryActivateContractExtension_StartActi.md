# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x180039900`
- end: `0x180039a4a`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x18003b4c4`

## callees

- `0x1800032e4`
- `0x18000b330`
- `0x180010490`
- `0x180011910`
- `0x180011fd0`
- `0x18001a35c`
- `0x1800384dc`
- `0x180039900`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039959`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180039959`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800399ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800399ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800399b0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800399b0`

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
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // rcx
  DWORD v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
  __int64 v18; // [rsp+68h] [rbp-10h] BYREF
  RTL_SRWLOCK *v19; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v19);
  v8 = *(_QWORD *)(a1 + 272);
  v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
    EventActivityIdControl(3u, (LPGUID)(v8 + 8));
  else
    *(_OWORD *)(v8 + 8) = 0;
  *(_DWORD *)v8 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v19);
  v10 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v11 = (__int64)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
  {
    v16 = a4;
    LODWORD(v19) = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *(_QWORD *)(a1 + 272);
    v15 = CurrentThreadId;
    v18 = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v11,
      (__int64)byte_1800558BB,
      v13 + 8,
      v14,
      (__int64)&v18,
      (__int64)&v15,
      &StringRawBuffer,
      (__int64)&v19,
      &v16);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180039900  push    rbp
0x180039902  push    rbx
0x180039903  push    rsi
0x180039904  push    rdi
0x180039905  push    r14
0x180039907  push    r15
0x180039909  mov     rbp, rsp
0x18003990c  sub     rsp, 78h
0x180039910  mov     r15, rdx
0x180039913  mov     r14, r9
0x180039916  lea     rdx, [rbp+arg_0]
0x18003991a  mov     ebx, r8d
0x18003991d  mov     rsi, rcx
0x180039920  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180039925  mov     rdi, [rsi+110h]
0x18003992c  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180039931  mov     r8d, [rax]
0x180039934  cmp     r8d, 5
0x180039938  jbe     short loc_180039961
0x18003993a  mov     rdx, 400000000000h
0x180039944  mov     rcx, rax
0x180039947  call    _tlgKeywordOn
0x18003994c  test    al, al
0x18003994e  jz      short loc_180039961
0x180039950  lea     rdx, [rdi+8]; ActivityId
0x180039954  mov     ecx, 3; ControlCode
0x180039959  call    cs:__imp_EventActivityIdControl
0x18003995f  jmp     short loc_180039968
0x180039961  xorps   xmm0, xmm0
0x180039964  movups  xmmword ptr [rdi+8], xmm0
0x180039968  lea     rcx, [rbp+arg_0]
0x18003996c  mov     dword ptr [rdi], 1
0x180039972  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180039977  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18003997c  mov     rdi, rax
0x18003997f  mov     ecx, [rax]
0x180039981  cmp     ecx, 5
0x180039984  jbe     loc_180039A2B
0x18003998a  mov     rdx, 400000000000h
0x180039994  mov     rcx, rax
0x180039997  call    _tlgKeywordOn
0x18003999c  test    al, al
0x18003999e  jz      loc_180039A2B
0x1800399a4  xor     edx, edx; length
0x1800399a6  mov     [rbp+var_20], r14
0x1800399aa  mov     rcx, r15; string
0x1800399ad  mov     dword ptr [rbp+arg_0], ebx
0x1800399b0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800399b6  mov     [rbp+var_18], rax
0x1800399ba  call    cs:__imp_GetCurrentThreadId
0x1800399c0  mov     r8, [rsi+110h]
0x1800399c7  mov     [rbp+var_28], eax
0x1800399ca  mov     [rbp+var_10], 0
0x1800399d2  cmp     byte ptr [r8+4], 0
0x1800399d7  jz      short loc_1800399E6
0x1800399d9  lea     rcx, [r8+18h]; struct _GUID *
0x1800399dd  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800399e2  test    al, al
0x1800399e4  jz      short loc_1800399E8
0x1800399e6  xor     ecx, ecx
0x1800399e8  lea     rax, [rbp+var_20]
0x1800399ec  mov     r9, rcx
0x1800399ef  mov     [rsp+78h+var_38], rax
0x1800399f4  lea     rdx, byte_1800558BB
0x1800399fb  lea     rax, [rbp+arg_0]
0x1800399ff  add     r8, 8
0x180039a03  mov     [rsp+78h+var_40], rax
0x180039a08  mov     rcx, rdi
0x180039a0b  lea     rax, [rbp+var_18]
0x180039a0f  mov     [rsp+78h+var_48], rax
0x180039a14  lea     rax, [rbp+var_28]
0x180039a18  mov     [rsp+78h+var_50], rax
0x180039a1d  lea     rax, [rbp+var_10]
0x180039a21  mov     [rsp+78h+var_58], rax
0x180039a26  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180039a2b  lea     rcx, [rsi+120h]; this
0x180039a32  cmp     dword ptr [rcx+18h], 0
0x180039a36  jnz     short loc_180039A3D
0x180039a38  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180039a3d  add     rsp, 78h
0x180039a41  pop     r15
0x180039a43  pop     r14
0x180039a45  pop     rdi
0x180039a46  pop     rsi
0x180039a47  pop     rbx
0x180039a48  pop     rbp
0x180039a49  retn
```
