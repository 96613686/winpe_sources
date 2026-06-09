# Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)

- ea: `0x180014714`
- end: `0x180014831`
- name: `?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z`
- size: `285`
- prototype: `void __high(HSTRING, struct Windows::Internal::ApplicationModel::WindowManagement::WindowId, const struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180014414`

## callees

- `0x18000224c`
- `0x180014714`
- `0x180016f70`
- `0x1800193f0`
- `0x180019b48`
- `0x18001ced8`
- `0x180024b04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014788`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014788`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014777`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180014777`

## pseudocode

```c
void __fastcall Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
        __int64 a1,
        HSTRING a2,
        int a3,
        __int64 a4)
{
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rsi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  __int64 v12; // rcx
  DWORD v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-30h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-28h] BYREF
  __int64 v16; // [rsp+68h] [rbp-20h] BYREF
  int v17; // [rsp+90h] [rbp+8h] BYREF

  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart();
  v8 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
  v9 = (__int64)v8;
  if ( *(_DWORD *)v8 > 5u && (unsigned __int8)tlgKeywordOn(v8, 0x400000000000LL) )
  {
    v14 = a4;
    v17 = a3;
    StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
    CurrentThreadId = GetCurrentThreadId();
    v11 = *(_QWORD *)(a1 + 272);
    v13 = CurrentThreadId;
    v16 = 0;
    if ( !*(_BYTE *)(v11 + 4) || _tlgGuidIsZero((const struct _GUID *)(v11 + 24)) )
      v12 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v9,
      (__int64)byte_1800A7365,
      v11 + 8,
      v12,
      (__int64)&v16,
      (__int64)&v13,
      &StringRawBuffer,
      (__int64)&v17,
      &v14);
  }
  if ( !*(_DWORD *)(a1 + 312) )
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)(a1 + 288));
}

```

## disassembly

```asm
0x180014714  mov     [rsp+arg_8], rbx
0x180014719  mov     [rsp+arg_10], rbp
0x18001471e  push    rsi
0x18001471f  push    rdi
0x180014720  push    r14
0x180014722  sub     rsp, 70h
0x180014726  mov     rbp, r9
0x180014729  mov     ebx, r8d
0x18001472c  mov     r14, rdx
0x18001472f  mov     rdi, rcx
0x180014732  call    ?zInternalStart@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStart(void)
0x180014737  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x18001473c  mov     rsi, rax
0x18001473f  mov     r8d, [rax]
0x180014742  cmp     r8d, 5
0x180014746  jbe     loc_180014809
0x18001474c  mov     rdx, 400000000000h
0x180014756  mov     rcx, rax
0x180014759  call    _tlgKeywordOn
0x18001475e  test    al, al
0x180014760  jz      loc_180014809
0x180014766  xor     edx, edx; length
0x180014768  mov     [rsp+88h+var_30], rbp
0x18001476d  mov     rcx, r14; string
0x180014770  mov     [rsp+88h+arg_0], ebx
0x180014777  call    cs:__imp_WindowsGetStringRawBuffer
0x18001477e  nop     dword ptr [rax+rax+00h]
0x180014783  mov     [rsp+88h+var_28], rax
0x180014788  call    cs:__imp_GetCurrentThreadId
0x18001478f  nop     dword ptr [rax+rax+00h]
0x180014794  mov     r8, [rdi+110h]
0x18001479b  mov     [rsp+88h+var_38], eax
0x18001479f  mov     [rsp+88h+var_20], 0
0x1800147a8  cmp     byte ptr [r8+4], 0
0x1800147ad  jz      short loc_1800147BC
0x1800147af  lea     rcx, [r8+18h]; struct _GUID *
0x1800147b3  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800147b8  test    al, al
0x1800147ba  jz      short loc_1800147BE
0x1800147bc  xor     ecx, ecx
0x1800147be  lea     rax, [rsp+88h+var_30]
0x1800147c3  mov     r9, rcx
0x1800147c6  mov     [rsp+88h+var_48], rax
0x1800147cb  lea     rdx, byte_1800A7365
0x1800147d2  lea     rax, [rsp+88h+arg_0]
0x1800147da  add     r8, 8
0x1800147de  mov     [rsp+88h+var_50], rax
0x1800147e3  mov     rcx, rsi
0x1800147e6  lea     rax, [rsp+88h+var_28]
0x1800147eb  mov     [rsp+88h+var_58], rax
0x1800147f0  lea     rax, [rsp+88h+var_38]
0x1800147f5  mov     [rsp+88h+var_60], rax
0x1800147fa  lea     rax, [rsp+88h+var_20]
0x1800147ff  mov     [rsp+88h+var_68], rax
0x180014804  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180014809  lea     rcx, [rdi+120h]; this
0x180014810  cmp     dword ptr [rcx+18h], 0
0x180014814  jnz     short loc_18001481B
0x180014816  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x18001481b  lea     r11, [rsp+88h+var_18]
0x180014820  mov     rbx, [r11+28h]
0x180014824  mov     rbp, [r11+30h]
0x180014828  mov     rsp, r11
0x18001482b  pop     r14
0x18001482d  pop     rdi
0x18001482e  pop     rsi
0x18001482f  retn
```
