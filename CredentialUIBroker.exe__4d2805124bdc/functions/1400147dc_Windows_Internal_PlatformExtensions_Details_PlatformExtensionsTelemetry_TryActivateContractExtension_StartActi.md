# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x1400147dc`
- end: `0x140014926`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `330`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting`

## callers

- `0x140016a54`

## callees

- `0x140002d54`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x140011aa0`
- `0x1400147dc`
- `0x140014a54`
- `0x140018fc0`

## import_xrefs

- `ADVAPI32!EventActivityIdControl` at `0x140014835`
- `ADVAPI32!EventActivityIdControl` at `0x140014835`
- `KERNEL32!GetCurrentThreadId` at `0x140014896`
- `KERNEL32!GetCurrentThreadId` at `0x140014896`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001488c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14001488c`

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
  __int64 v18; // rcx
  DWORD v19; // [rsp+50h] [rbp-28h] BYREF
  __int64 v20; // [rsp+58h] [rbp-20h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-18h] BYREF
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
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v17 = *(_QWORD *)(a1 + 272);
    v19 = CurrentThreadId;
    v22 = 0;
    if ( !*(_BYTE *)(v17 + 4) || _tlgGuidIsZero((const struct _GUID *)(v17 + 24)) )
      v18 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v15,
      (__int64)&byte_1400267F7,
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
0x1400147dc  push    rbp
0x1400147de  push    rbx
0x1400147df  push    rsi
0x1400147e0  push    rdi
0x1400147e1  push    r14
0x1400147e3  push    r15
0x1400147e5  mov     rbp, rsp
0x1400147e8  sub     rsp, 78h
0x1400147ec  mov     r15, rdx
0x1400147ef  mov     r14, r9
0x1400147f2  lea     rdx, [rbp+arg_0]
0x1400147f6  mov     ebx, r8d
0x1400147f9  mov     rsi, rcx
0x1400147fc  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140014801  mov     rdi, [rsi+110h]
0x140014808  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14001480d  mov     r8d, [rax]
0x140014810  cmp     r8d, 5
0x140014814  jbe     short loc_14001483D
0x140014816  mov     rdx, 400000000000h
0x140014820  mov     rcx, rax
0x140014823  call    _tlgKeywordOn
0x140014828  test    al, al
0x14001482a  jz      short loc_14001483D
0x14001482c  lea     rdx, [rdi+8]; ActivityId
0x140014830  mov     ecx, 3; ControlCode
0x140014835  call    cs:__imp_EventActivityIdControl
0x14001483b  jmp     short loc_140014844
0x14001483d  xorps   xmm0, xmm0
0x140014840  movups  xmmword ptr [rdi+8], xmm0
0x140014844  lea     rcx, [rbp+arg_0]
0x140014848  mov     dword ptr [rdi], 1
0x14001484e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140014853  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x140014858  mov     rdi, rax
0x14001485b  mov     ecx, [rax]
0x14001485d  cmp     ecx, 5
0x140014860  jbe     loc_140014907
0x140014866  mov     rdx, 400000000000h
0x140014870  mov     rcx, rax
0x140014873  call    _tlgKeywordOn
0x140014878  test    al, al
0x14001487a  jz      loc_140014907
0x140014880  xor     edx, edx; length
0x140014882  mov     [rbp+var_20], r14
0x140014886  mov     rcx, r15; string
0x140014889  mov     dword ptr [rbp+arg_0], ebx
0x14001488c  call    cs:__imp_WindowsGetStringRawBuffer
0x140014892  mov     [rbp+var_18], rax
0x140014896  call    cs:__imp_GetCurrentThreadId
0x14001489c  mov     r8, [rsi+110h]
0x1400148a3  mov     [rbp+var_28], eax
0x1400148a6  mov     [rbp+var_10], 0
0x1400148ae  cmp     byte ptr [r8+4], 0
0x1400148b3  jz      short loc_1400148C2
0x1400148b5  lea     rcx, [r8+18h]; struct _GUID *
0x1400148b9  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1400148be  test    al, al
0x1400148c0  jz      short loc_1400148C4
0x1400148c2  xor     ecx, ecx
0x1400148c4  lea     rax, [rbp+var_20]
0x1400148c8  mov     r9, rcx
0x1400148cb  mov     [rsp+78h+var_38], rax
0x1400148d0  lea     rdx, byte_1400267F7
0x1400148d7  lea     rax, [rbp+arg_0]
0x1400148db  add     r8, 8
0x1400148df  mov     [rsp+78h+var_40], rax
0x1400148e4  mov     rcx, rdi
0x1400148e7  lea     rax, [rbp+var_18]
0x1400148eb  mov     [rsp+78h+var_48], rax
0x1400148f0  lea     rax, [rbp+var_28]
0x1400148f4  mov     [rsp+78h+var_50], rax
0x1400148f9  lea     rax, [rbp+var_10]
0x1400148fd  mov     [rsp+78h+var_58], rax
0x140014902  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x140014907  lea     rcx, [rsi+120h]; this
0x14001490e  cmp     dword ptr [rcx+18h], 0
0x140014912  jnz     short loc_140014919
0x140014914  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x140014919  add     rsp, 78h
0x14001491d  pop     r15
0x14001491f  pop     r14
0x140014921  pop     rdi
0x140014922  pop     rsi
0x140014923  pop     rbx
0x140014924  pop     rbp
0x140014925  retn
```
