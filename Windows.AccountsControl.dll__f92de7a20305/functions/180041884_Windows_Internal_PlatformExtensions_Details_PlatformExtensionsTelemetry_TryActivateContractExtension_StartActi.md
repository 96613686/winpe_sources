# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x180041884`
- end: `0x1800419ce`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `330`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x180042770`

## callees

- `0x18000171c`
- `0x180002640`
- `0x18000c14c`
- `0x1800123bc`
- `0x180017304`
- `0x180019304`
- `0x180040ccc`
- `0x180041884`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041934`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180041934`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800418dd`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x1800418dd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004193e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004193e`

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
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // ecx
  DWORD v15; // [rsp+50h] [rbp-28h] BYREF
  __int64 v16; // [rsp+58h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
  __int64 v18; // [rsp+68h] [rbp-10h] BYREF
  int v19; // [rsp+B0h] [rbp+38h] BYREF

  wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
  v11 = (int)v10;
  if ( *(_DWORD *)v10 > 5u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL) )
  {
    v16 = a4;
    v19 = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *(_QWORD *)(a1 + 272);
    v15 = CurrentThreadId;
    v18 = 0;
    if ( !*(_BYTE *)(v13 + 4) || _tlgGuidIsZero((const struct _GUID *)(v13 + 24)) )
      v14 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v11,
      (unsigned int)&byte_1800A1F37,
      v13 + 8,
      v14,
      (__int64)&v18,
      (__int64)&v15,
      (__int64)&StringRawBuffer,
      (__int64)&v19,
      (__int64)&v16);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180041884  push    rbp
0x180041886  push    rbx
0x180041887  push    rsi
0x180041888  push    rdi
0x180041889  push    r14
0x18004188b  push    r15
0x18004188d  mov     rbp, rsp
0x180041890  sub     rsp, 78h
0x180041894  mov     r15, rdx
0x180041897  mov     r14, r9
0x18004189a  lea     rdx, [rbp+arg_0]
0x18004189e  mov     ebx, r8d
0x1800418a1  mov     rsi, rcx
0x1800418a4  call    ?LockExclusive@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800418a9  mov     rdi, [rsi+110h]
0x1800418b0  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1800418b5  mov     r8d, [rax]
0x1800418b8  cmp     r8d, 5
0x1800418bc  jbe     short loc_1800418E5
0x1800418be  mov     rdx, 400000000000h
0x1800418c8  mov     rcx, rax
0x1800418cb  call    _tlgKeywordOn
0x1800418d0  test    al, al
0x1800418d2  jz      short loc_1800418E5
0x1800418d4  lea     rdx, [rdi+8]; ActivityId
0x1800418d8  mov     ecx, 3; ControlCode
0x1800418dd  call    cs:__imp_EventActivityIdControl
0x1800418e3  jmp     short loc_1800418EC
0x1800418e5  xorps   xmm0, xmm0
0x1800418e8  movups  xmmword ptr [rdi+8], xmm0
0x1800418ec  lea     rcx, [rbp+arg_0]
0x1800418f0  mov     dword ptr [rdi], 1
0x1800418f6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800418fb  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180041900  mov     rdi, rax
0x180041903  mov     ecx, [rax]
0x180041905  cmp     ecx, 5
0x180041908  jbe     loc_1800419AF
0x18004190e  mov     rdx, 400000000000h
0x180041918  mov     rcx, rax
0x18004191b  call    _tlgKeywordOn
0x180041920  test    al, al
0x180041922  jz      loc_1800419AF
0x180041928  xor     edx, edx; length
0x18004192a  mov     [rbp+var_20], r14
0x18004192e  mov     rcx, r15; string
0x180041931  mov     [rbp+arg_0], ebx
0x180041934  call    cs:__imp_WindowsGetStringRawBuffer
0x18004193a  mov     [rbp+var_18], rax
0x18004193e  call    cs:__imp_GetCurrentThreadId
0x180041944  mov     r8, [rsi+110h]
0x18004194b  mov     [rbp+var_28], eax
0x18004194e  mov     [rbp+var_10], 0
0x180041956  cmp     byte ptr [r8+4], 0
0x18004195b  jz      short loc_18004196A
0x18004195d  lea     rcx, [r8+18h]; struct _GUID *
0x180041961  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180041966  test    al, al
0x180041968  jz      short loc_18004196C
0x18004196a  xor     ecx, ecx
0x18004196c  lea     rax, [rbp+var_20]
0x180041970  mov     r9, rcx
0x180041973  mov     [rsp+78h+var_38], rax
0x180041978  lea     rdx, byte_1800A1F37
0x18004197f  lea     rax, [rbp+arg_0]
0x180041983  add     r8, 8
0x180041987  mov     [rsp+78h+var_40], rax
0x18004198c  mov     rcx, rdi
0x18004198f  lea     rax, [rbp+var_18]
0x180041993  mov     [rsp+78h+var_48], rax
0x180041998  lea     rax, [rbp+var_28]
0x18004199c  mov     [rsp+78h+var_50], rax
0x1800419a1  lea     rax, [rbp+var_10]
0x1800419a5  mov     [rsp+78h+var_58], rax
0x1800419aa  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800419af  lea     rcx, [rsi+120h]; this
0x1800419b6  cmp     dword ptr [rcx+18h], 0
0x1800419ba  jnz     short loc_1800419C1
0x1800419bc  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800419c1  add     rsp, 78h
0x1800419c5  pop     r15
0x1800419c7  pop     r14
0x1800419c9  pop     rdi
0x1800419ca  pop     rsi
0x1800419cb  pop     rbx
0x1800419cc  pop     rbp
0x1800419cd  retn
```
