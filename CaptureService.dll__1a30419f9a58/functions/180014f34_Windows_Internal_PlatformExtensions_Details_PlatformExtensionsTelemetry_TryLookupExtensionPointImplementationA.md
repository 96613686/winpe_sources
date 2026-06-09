# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid::StartActivity(HSTRING__ *)

- ea: `0x180014f34`
- end: `0x18001506a`
- name: `?StartActivity@TryLookupExtensionPointImplementationAcid@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@@Z`
- size: `310`
- prototype: `void(Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryLookupExtensionPointImplementationAcid *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callers

- `0x180017520`

## callees

- `0x180002250`
- `0x18000254c`
- `0x180005568`
- `0x1800123bc`
- `0x180013130`
- `0x180014f34`
- `0x180015070`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014fd1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014fd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014fdc`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f80`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x180014f80`

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
  __int64 v14; // r9
  RTL_SRWLOCK *v15; // [rsp+60h] [rbp+8h] BYREF
  __int64 *StringRawBuffer; // [rsp+70h] [rbp+18h] BYREF
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
    StringRawBuffer = (__int64 *)WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v13 = *((_QWORD *)this + 34);
    LODWORD(v15) = CurrentThreadId;
    v17 = 0;
    if ( !*(_BYTE *)(v13 + 4)
      || (v14 = v13 + 24, !*(_DWORD *)(v13 + 24))
      && !*(_DWORD *)(v13 + 28)
      && !*(_DWORD *)(v13 + 32)
      && !*(_DWORD *)(v13 + 36) )
    {
      v14 = 0;
    }
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      v11,
      (__int64)&word_180028F66,
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
0x180014f34  push    rbx
0x180014f36  push    rsi
0x180014f37  push    rdi
0x180014f38  sub     rsp, 40h
0x180014f3c  mov     rsi, rdx
0x180014f3f  mov     rdi, rcx
0x180014f42  lea     rdx, [rsp+58h+arg_0]
0x180014f47  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180014f4c  mov     rbx, [rdi+110h]
0x180014f53  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180014f58  mov     r8d, [rax]
0x180014f5b  cmp     r8d, 5
0x180014f5f  jbe     short loc_180014F88
0x180014f61  mov     rdx, 200000000000h
0x180014f6b  mov     rcx, rax
0x180014f6e  call    _tlgKeywordOn
0x180014f73  test    al, al
0x180014f75  jz      short loc_180014F88
0x180014f77  lea     rdx, [rbx+8]; ActivityId
0x180014f7b  mov     ecx, 3; ControlCode
0x180014f80  call    cs:__imp_EventActivityIdControl
0x180014f86  jmp     short loc_180014F8F
0x180014f88  xorps   xmm0, xmm0
0x180014f8b  movups  xmmword ptr [rbx+8], xmm0
0x180014f8f  lea     rcx, [rsp+58h+arg_0]
0x180014f94  mov     dword ptr [rbx], 1
0x180014f9a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014f9f  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x180014fa4  mov     rbx, rax
0x180014fa7  mov     ecx, [rax]
0x180014fa9  cmp     ecx, 5
0x180014fac  jbe     loc_180015050
0x180014fb2  mov     rdx, 200000000000h
0x180014fbc  mov     rcx, rax
0x180014fbf  call    _tlgKeywordOn
0x180014fc4  test    al, al
0x180014fc6  jz      loc_180015050
0x180014fcc  xor     edx, edx; length
0x180014fce  mov     rcx, rsi; string
0x180014fd1  call    cs:__imp_WindowsGetStringRawBuffer
0x180014fd7  mov     [rsp+58h+arg_10], rax
0x180014fdc  call    cs:__imp_GetCurrentThreadId
0x180014fe2  mov     r8, [rdi+110h]
0x180014fe9  mov     dword ptr [rsp+58h+arg_0], eax
0x180014fed  mov     [rsp+58h+arg_18], 0
0x180014ff6  cmp     byte ptr [r8+4], 0
0x180014ffb  jz      short loc_18001501C
0x180014ffd  lea     r9, [r8+18h]
0x180015001  cmp     dword ptr [r9], 0
0x180015005  jnz     short loc_18001501F
0x180015007  cmp     dword ptr [r9+4], 0
0x18001500c  jnz     short loc_18001501F
0x18001500e  cmp     dword ptr [r9+8], 0
0x180015013  jnz     short loc_18001501F
0x180015015  cmp     dword ptr [r9+0Ch], 0
0x18001501a  jnz     short loc_18001501F
0x18001501c  xor     r9d, r9d
0x18001501f  lea     rax, [rsp+58h+arg_10]
0x180015024  add     r8, 8
0x180015028  mov     [rsp+58h+var_28], rax
0x18001502d  lea     rdx, word_180028F66
0x180015034  lea     rax, [rsp+58h+arg_0]
0x180015039  mov     rcx, rbx
0x18001503c  mov     [rsp+58h+var_30], rax
0x180015041  lea     rax, [rsp+58h+arg_18]
0x180015046  mov     [rsp+58h+var_38], rax
0x18001504b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180015050  lea     rcx, [rdi+120h]; this
0x180015057  cmp     dword ptr [rcx+18h], 0
0x18001505b  jnz     short loc_180015062
0x18001505d  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x180015062  add     rsp, 40h
0x180015066  pop     rdi
0x180015067  pop     rsi
0x180015068  pop     rbx
0x180015069  retn
```
