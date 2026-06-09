# UiaManagerImpl::RemoveEndpointRegistration(_GUID)

- ea: `0x18000ba00`
- end: `0x18000bcc2`
- name: `?RemoveEndpointRegistration@UiaManagerImpl@@QEAAXU_GUID@@@Z`
- size: `706`
- prototype: `void(UiaManagerImpl *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000b8b0`

## callees

- `0x180005610`
- `0x1800065f8`
- `0x18000ba00`
- `0x180010e14`
- `0x180031540`
- `0x180043680`
- `0x180043a30`
- `0x180044188`
- `0x180091010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000baf8`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x18000baf8`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000bb13`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x18000bb13`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bbf5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000bbf5`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bb42`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000bb42`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ba4c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ba4c`

## string_xrefs

- `0x18000bcaf`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall UiaManagerImpl::RemoveEndpointRegistration(UiaManagerImpl *this, struct _GUID *a2)
{
  ULONGLONG *v4; // rbx
  __int64 v5; // rcx
  __int64 v6; // rcx
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rcx
  ULONG UserDataCount; // [rsp+20h] [rbp-A8h]
  WINBOOL fPending; // [rsp+30h] [rbp-98h] BYREF
  EVENT_DESCRIPTOR Context; // [rsp+38h] [rbp-90h] BYREF
  GUID ProviderId; // [rsp+50h] [rbp-78h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+60h] [rbp-68h] BYREF
  void *v15; // [rsp+70h] [rbp-58h]
  int v16; // [rsp+78h] [rbp-50h]
  int v17; // [rsp+7Ch] [rbp-4Ch]
  struct _GUID *v18; // [rsp+80h] [rbp-48h]
  __int64 v19; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *(_QWORD *)&Context.Id = 0;
  fPending = 0;
  if ( __std_init_once_begin_initialize(
         &`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         (LPVOID *)&Context)
    && fPending )
  {
    *(_QWORD *)&Context.Id = &qword_1800C4F30;
    qword_1800C4F38 = 0;
    byte_1800C4F40 = 0;
    dword_1800C4F44 = 0;
    qword_1800C4F30 = (__int64)&UiaManagerTraceLoggingProvider::`vftable';
    CallbackContext = &`UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_::_lambda_invoker_cdecl_);
    v4 = (ULONGLONG *)CallbackContext;
    qword_1800C4F38 = (__int64)CallbackContext;
    byte_1800C4F40 = 1;
    ProviderId = *(GUID *)(*((_QWORD *)CallbackContext + 1) - 16LL);
    if ( *((_QWORD *)CallbackContext + 4) )
      __fastfail(5u);
    *((_QWORD *)CallbackContext + 5) = 0;
    v4[6] = 0;
    if ( !EventRegister(&ProviderId, tlgEnableCallback, v4, v4 + 4) )
      EventSetInformation(v4[4], 2, v4[1], *(unsigned __int16 *)v4[1]);
    dword_1800C4F44 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800C4F30 + 8))(&qword_1800C4F30);
    InitOnceComplete(&`UiaManagerTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_1800C4F30);
  }
  v5 = *(_QWORD *)(*(_QWORD *)&Context.Id + 8LL);
  if ( *(_DWORD *)v5 > 4u )
  {
    v18 = a2;
    v19 = 16;
    *(_QWORD *)&Context.Id = 0x40B000000LL;
    Context.Keyword = 0;
    UserData.Ptr = *(_QWORD *)(v5 + 8);
    UserData.Size = *(unsigned __int16 *)UserData.Ptr;
    UserData.Reserved = 2;
    v15 = &unk_1800AD9C0;
    v16 = 58;
    v17 = 1;
    fPending = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(*(_QWORD *)(v5 + 32), &Context, 0, 0, 3u, &UserData);
  }
  if ( memcmp_0(a2, &GUID_NULL, 0x10u) )
  {
    try
    {
      ThreadSafeMap<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::RemoveValue((UiaManagerImpl *)((char *)this + 232));
      ThreadSafeMap<_GUID,std::optional<ProviderEntrypointId>>::RemoveValue((char *)this + 376, a2);
      v6 = *(_QWORD *)UiaManagerImpl::GetUiaManagerEndpointStateNotifier(this, &Context);
      ProviderId = *a2;
      v7 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v6 + 32LL))(v6, &ProviderId);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x138,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
          (const char *)(unsigned int)v7,
          UserDataCount);
      v9 = *(_QWORD *)&Context.Id;
      if ( *(_QWORD *)&Context.Id )
      {
        *(_QWORD *)&Context.Id = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x13B,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        v8);
    }
  }
}

```

## disassembly

```asm
0x18000ba00  mov     [rsp+arg_10], rbx
0x18000ba05  push    rsi
0x18000ba06  push    rdi
0x18000ba07  push    r12
0x18000ba09  push    r14
0x18000ba0b  push    r15
0x18000ba0d  sub     rsp, 0A0h
0x18000ba14  mov     rax, cs:__security_cookie
0x18000ba1b  xor     rax, rsp
0x18000ba1e  mov     [rsp+0C8h+var_38], rax
0x18000ba26  mov     rdi, rdx
0x18000ba29  mov     rsi, rcx
0x18000ba2c  xor     r15d, r15d
0x18000ba2f  mov     [rsp+0C8h+Context], r15
0x18000ba34  mov     [rsp+0C8h+fPending], r15d
0x18000ba39  lea     r9, [rsp+0C8h+Context]; lpContext
0x18000ba3e  lea     r8, [rsp+0C8h+fPending]; fPending
0x18000ba43  xor     edx, edx; dwFlags
0x18000ba45  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000ba4c  call    cs:__imp___std_init_once_begin_initialize
0x18000ba52  test    eax, eax
0x18000ba54  jz      loc_18000BB48
0x18000ba5a  cmp     [rsp+0C8h+fPending], r15d
0x18000ba5f  jz      loc_18000BB48
0x18000ba65  lea     r12, qword_1800C4F30
0x18000ba6c  mov     [rsp+0C8h+Context], r12
0x18000ba71  mov     cs:qword_1800C4F38, r15
0x18000ba78  mov     cs:byte_1800C4F40, r15b
0x18000ba7f  mov     cs:dword_1800C4F44, r15d
0x18000ba86  lea     rax, ??_7UiaManagerTraceLoggingProvider@@6B@; const UiaManagerTraceLoggingProvider::`vftable'
0x18000ba8d  mov     cs:qword_1800C4F30, rax
0x18000ba94  lea     rax, ?__hInner@?1???0StaticHandle@UiaManagerTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UiaManagerTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000ba9b  mov     cs:CallbackContext, rax
0x18000baa2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b7707e9d8a7acf1d20efe6f60d8bc70_@@CA@XZ; void (__cdecl *)()
0x18000baa9  call    atexit
0x18000baae  mov     rbx, cs:CallbackContext
0x18000bab5  mov     cs:qword_1800C4F38, rbx
0x18000babc  mov     cs:byte_1800C4F40, 1
0x18000bac3  mov     rax, [rbx+8]
0x18000bac7  movups  xmm0, xmmword ptr [rax-10h]
0x18000bacb  movups  xmmword ptr [rsp+0C8h+ProviderId.Data1], xmm0
0x18000bad0  cmp     [rbx+20h], r15
0x18000bad4  jz      short loc_18000BADD
0x18000bad6  mov     ecx, 5
0x18000badb  int     29h; Win8: RtlFailFast(ecx)
0x18000badd  mov     [rbx+28h], r15
0x18000bae1  mov     [rbx+30h], r15
0x18000bae5  lea     r9, [rbx+20h]; RegHandle
0x18000bae9  mov     r8, rbx; CallbackContext
0x18000baec  lea     rdx, _tlgEnableCallback; EnableCallback
0x18000baf3  lea     rcx, [rsp+0C8h+ProviderId]; ProviderId
0x18000baf8  call    cs:__imp_EventRegister
0x18000bafe  test    eax, eax
0x18000bb00  jnz     short loc_18000BB19
0x18000bb02  mov     r8, [rbx+8]
0x18000bb06  movzx   r9d, word ptr [r8]
0x18000bb0a  mov     edx, 2
0x18000bb0f  mov     rcx, [rbx+20h]
0x18000bb13  call    cs:__imp_EventSetInformation
0x18000bb19  mov     cs:dword_1800C4F44, 1
0x18000bb23  mov     rax, cs:qword_1800C4F30
0x18000bb2a  mov     rcx, r12
0x18000bb2d  mov     rax, [rax+8]
0x18000bb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb36  mov     r8, r12; lpContext
0x18000bb39  xor     edx, edx; dwFlags
0x18000bb3b  lea     rcx, ?wrapper@?1??Instance@UiaManagerTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUiaManagerTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x18000bb42  call    cs:__imp_InitOnceComplete
0x18000bb48  mov     rax, [rsp+0C8h+Context]
0x18000bb4d  mov     rcx, [rax+8]
0x18000bb51  mov     eax, [rcx]
0x18000bb53  cmp     eax, 4
0x18000bb56  jbe     loc_18000BBFB
0x18000bb5c  mov     [rsp+0C8h+var_48], rdi
0x18000bb64  mov     [rsp+0C8h+var_40], 10h
0x18000bb70  mov     dword ptr [rsp+0C8h+Context], 0B000000h
0x18000bb78  movzx   eax, cs:word_1800AD9B6
0x18000bb7f  mov     dword ptr [rsp+0C8h+Context+4], eax
0x18000bb83  mov     [rsp+0C8h+var_88], r15
0x18000bb88  mov     rax, [rcx+8]
0x18000bb8c  mov     [rsp+0C8h+var_68.Ptr], rax
0x18000bb91  movzx   eax, word ptr [rax]
0x18000bb94  mov     [rsp+0C8h+var_68.Size], eax
0x18000bb98  mov     dword ptr [rsp+0C8h+var_68.0Ch], 2
0x18000bba0  lea     rax, unk_1800AD9C0
0x18000bba7  mov     [rsp+0C8h+var_58], rax
0x18000bbac  mov     [rsp+0C8h+var_50], 3Ah ; ':'
0x18000bbb4  mov     [rsp+0C8h+var_4C], 1
0x18000bbbc  lea     rax, _TraceLoggingMetadataEnd
0x18000bbc3  lea     rdx, _TraceLoggingMetadata
0x18000bbca  sub     eax, edx
0x18000bbcc  mov     [rsp+0C8h+fPending], eax
0x18000bbd0  mov     eax, [rsp+0C8h+fPending]
0x18000bbd4  lea     rax, [rsp+0C8h+var_68]
0x18000bbd9  mov     [rsp+0C8h+UserData], rax; UserData
0x18000bbde  mov     [rsp+0C8h+UserDataCount], 3; int
0x18000bbe6  xor     r9d, r9d; RelatedActivityId
0x18000bbe9  xor     r8d, r8d; ActivityId
0x18000bbec  lea     rdx, [rsp+0C8h+Context]; EventDescriptor
0x18000bbf1  mov     rcx, [rcx+20h]; RegHandle
0x18000bbf5  call    cs:__imp_EventWriteTransfer
0x18000bbfb  mov     r8d, 10h; Size
0x18000bc01  lea     rdx, GUID_NULL; Buf2
0x18000bc08  mov     rcx, rdi; Buf1
0x18000bc0b  call    memcmp_0
0x18000bc10  test    eax, eax
0x18000bc12  jz      short loc_18000BC84
0x18000bc14  lea     rcx, [rsi+0E8h]; this
0x18000bc1b  mov     rdx, rdi
0x18000bc1e  call    ?RemoveValue@?$ThreadSafeMap@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@@QEAAXAEBU_GUID@@@Z; ThreadSafeMap<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::RemoveValue(_GUID const &)
0x18000bc23  lea     rcx, [rsi+178h]
0x18000bc2a  mov     rdx, rdi
0x18000bc2d  call    ?RemoveValue@?$ThreadSafeMap@U_GUID@@V?$optional@VProviderEntrypointId@@@std@@@@QEAAXAEBU_GUID@@@Z; ThreadSafeMap<_GUID,std::optional<ProviderEntrypointId>>::RemoveValue(_GUID const &)
0x18000bc32  lea     rdx, [rsp+0C8h+Context]
0x18000bc37  mov     rcx, rsi
0x18000bc3a  call    ?GetUiaManagerEndpointStateNotifier@UiaManagerImpl@@AEAA?AV?$ComPtr@UIUiaManagerEndpointStateNotifierSink@@@WRL@Microsoft@@XZ; UiaManagerImpl::GetUiaManagerEndpointStateNotifier(void)
0x18000bc3f  nop
0x18000bc40  mov     rcx, [rax]
0x18000bc43  movups  xmm0, xmmword ptr [rdi]
0x18000bc46  movaps  xmmword ptr [rsp+0C8h+ProviderId.Data1], xmm0
0x18000bc4b  mov     rax, [rcx]
0x18000bc4e  lea     rdx, [rsp+0C8h+ProviderId]
0x18000bc53  mov     rax, [rax+20h]
0x18000bc57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc5c  mov     rcx, [rsp+0C8h]; this
0x18000bc64  test    eax, eax
0x18000bc66  js      short loc_18000BCAC
0x18000bc68  mov     rcx, [rsp+0C8h+Context]
0x18000bc6d  test    rcx, rcx
0x18000bc70  jz      short loc_18000BC84
0x18000bc72  mov     [rsp+0C8h+Context], r15
0x18000bc77  mov     rax, [rcx]
0x18000bc7a  mov     rax, [rax+10h]
0x18000bc7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc83  nop
0x18000bc84  mov     rcx, [rsp+0C8h+var_38]
0x18000bc8c  xor     rcx, rsp; StackCookie
0x18000bc8f  call    __security_check_cookie
0x18000bc94  mov     rbx, [rsp+0C8h+arg_10]
0x18000bc9c  add     rsp, 0A0h
0x18000bca3  pop     r15
0x18000bca5  pop     r14
0x18000bca7  pop     r12
0x18000bca9  pop     rdi
0x18000bcaa  pop     rsi
0x18000bcab  retn
0x18000bcac  mov     r9d, eax; char *
0x18000bcaf  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18000bcb6  mov     edx, 138h; void *
0x18000bcbb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
