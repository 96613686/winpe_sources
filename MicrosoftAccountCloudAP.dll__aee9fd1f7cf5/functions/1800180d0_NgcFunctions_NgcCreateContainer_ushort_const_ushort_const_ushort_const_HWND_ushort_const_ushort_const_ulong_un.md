# NgcFunctions::NgcCreateContainer(ushort const *,ushort const *,ushort const *,HWND__ *,ushort const *,ushort const *,ulong,unsigned __int64 *)

- ea: `0x1800180d0`
- end: `0x180018229`
- name: `?NgcCreateContainer@NgcFunctions@@UEAAJPEBG00PEAUHWND__@@00KPEA_K@Z`
- size: `345`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, HWND, const unsigned __int16 *, const unsigned __int16 *, unsigned int, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001a44`
- `0x180003160`
- `0x18000d91c`
- `0x1800168f0`
- `0x180016924`
- `0x18001696c`
- `0x1800176a4`
- `0x1800180d0`

## import_xrefs

- `cryptngc!NgcCreateContainer` at `0x1800181a8`
- `cryptngc!NgcCreateContainer` at `0x1800181a8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcCreateContainer(
        NgcFunctions *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        HWND a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        unsigned int a8,
        unsigned __int64 *a9)
{
  __int64 *v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int v18; // [rsp+60h] [rbp-49h] BYREF
  __int64 v19; // [rsp+68h] [rbp-41h] BYREF
  __int64 v20; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v21[3]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v22; // [rsp+90h] [rbp-19h] BYREF

  v20 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v12 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
            &v19,
            L"n.cc");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      &v20,
      v12);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v19);
  }
  v22 = 0;
  v18 = 0;
  memset(v21, 0, sizeof(v21));
  v13 = NgcCreateContainer(a2, a3, a4, a5, a6, a7, a8, &v22, v21, &v18, a9);
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    LODWORD(v19) = v13;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v14,
      (__int64)byte_180044533,
      v15,
      v16,
      (__int64)&v19);
  }
  Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>((__int64)v21);
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v20);
  return v13;
}

```

## disassembly

```asm
0x1800180d0  mov     [rsp-8+arg_0], rbx
0x1800180d5  push    rbp
0x1800180d6  push    rsi
0x1800180d7  push    rdi
0x1800180d8  push    r12
0x1800180da  push    r13
0x1800180dc  push    r14
0x1800180de  push    r15
0x1800180e0  lea     rbp, [rsp-7]
0x1800180e5  sub     rsp, 0B0h
0x1800180ec  mov     rax, cs:__security_cookie
0x1800180f3  xor     rax, rsp
0x1800180f6  mov     [rbp+37h+var_40], rax
0x1800180fa  mov     rsi, r9
0x1800180fd  mov     rdi, r8
0x180018100  mov     rbx, rdx
0x180018103  mov     r14, [rbp+37h+arg_20]
0x180018107  mov     r15, [rbp+37h+arg_28]
0x18001810b  mov     r12, [rbp+37h+arg_30]
0x18001810f  mov     r13, [rbp+37h+arg_40]
0x180018116  mov     [rbp+37h+var_70], 0
0x18001811e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180018125  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18001812a  test    al, al
0x18001812c  jz      short loc_180018153
0x18001812e  lea     rdx, aNCc; "n.cc"
0x180018135  lea     rcx, [rbp+37h+var_78]
0x180018139  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x18001813e  mov     rdx, rax
0x180018141  lea     rcx, [rbp+37h+var_70]
0x180018145  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x18001814a  lea     rcx, [rbp+37h+var_78]
0x18001814e  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018153  xorps   xmm0, xmm0
0x180018156  movups  [rbp+37h+var_50], xmm0
0x18001815a  xor     eax, eax
0x18001815c  mov     [rbp+37h+var_80], eax
0x18001815f  mov     [rbp+37h+var_68], rax
0x180018163  mov     [rbp+37h+var_58], rax
0x180018167  mov     [rbp+37h+var_60], rax
0x18001816b  mov     [rsp+0E0h+var_90], r13
0x180018170  lea     rax, [rbp+37h+var_80]
0x180018174  mov     [rsp+0E0h+var_98], rax
0x180018179  lea     rax, [rbp+37h+var_68]
0x18001817d  mov     [rsp+0E0h+var_A0], rax
0x180018182  lea     rax, [rbp+37h+var_50]
0x180018186  mov     [rsp+0E0h+var_A8], rax
0x18001818b  mov     eax, [rbp+37h+arg_38]
0x18001818e  mov     [rsp+0E0h+var_B0], eax
0x180018192  mov     [rsp+0E0h+var_B8], r12
0x180018197  mov     [rsp+0E0h+var_C0], r15
0x18001819c  mov     r9, r14
0x18001819f  mov     r8, rsi
0x1800181a2  mov     rdx, rdi
0x1800181a5  mov     rcx, rbx
0x1800181a8  call    cs:__imp_NgcCreateContainer
0x1800181ae  mov     ebx, eax
0x1800181b0  mov     ecx, cs:dword_18004D048
0x1800181b6  cmp     ecx, 5
0x1800181b9  jbe     short loc_1800181ED
0x1800181bb  mov     rdx, 400000000000h
0x1800181c5  lea     rcx, dword_18004D048
0x1800181cc  call    _tlgKeywordOn
0x1800181d1  test    al, al
0x1800181d3  jz      short loc_1800181ED
0x1800181d5  mov     dword ptr [rbp+37h+var_78], ebx
0x1800181d8  lea     rax, [rbp+37h+var_78]
0x1800181dc  mov     [rsp+0E0h+var_C0], rax
0x1800181e1  lea     rdx, byte_180044533
0x1800181e8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800181ed  lea     rcx, [rbp+37h+var_68]
0x1800181f1  call    ??1?$Auto@PEAPEAXV?$LocalAllocFunctor@PEAPEAX@@VDummyContext@@@@QEAA@XZ; Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>::~Auto<void * *,LocalAllocFunctor<void * *>,DummyContext>(void)
0x1800181f6  nop
0x1800181f7  lea     rcx, [rbp+37h+var_70]
0x1800181fb  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018200  mov     eax, ebx
0x180018202  mov     rcx, [rbp+37h+var_40]
0x180018206  xor     rcx, rsp; StackCookie
0x180018209  call    __security_check_cookie
0x18001820e  mov     rbx, [rsp+0E0h+arg_0]
0x180018216  add     rsp, 0B0h
0x18001821d  pop     r15
0x18001821f  pop     r14
0x180018221  pop     r13
0x180018223  pop     r12
0x180018225  pop     rdi
0x180018226  pop     rsi
0x180018227  pop     rbp
0x180018228  retn
```
