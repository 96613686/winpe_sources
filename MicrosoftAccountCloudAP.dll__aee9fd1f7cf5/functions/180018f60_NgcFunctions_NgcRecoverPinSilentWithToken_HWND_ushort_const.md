# NgcFunctions::NgcRecoverPinSilentWithToken(HWND__ *,ushort const *)

- ea: `0x180018f60`
- end: `0x180019016`
- name: `?NgcRecoverPinSilentWithToken@NgcFunctions@@UEAAJPEAUHWND__@@PEBG@Z`
- size: `182`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, HWND, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800011fc`
- `0x180001a44`
- `0x1800168f0`
- `0x180016924`
- `0x18001696c`
- `0x1800176a4`
- `0x180018f60`

## import_xrefs

- `ngcrecovery!NgcRecoverPinSilentWithToken` at `0x180018fb7`
- `ngcrecovery!NgcRecoverPinSilentWithToken` at `0x180018fb7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcRecoverPinSilentWithToken(NgcFunctions *this, HWND a2, const unsigned __int16 *a3)
{
  __int64 *v5; // rax
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v11[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h] BYREF

  v11[0] = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v5 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
           &v12,
           L"n.rp");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      v11,
      v5);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v12);
  }
  v6 = NgcRecoverPinSilentWithToken(a2, a3);
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    LODWORD(v12) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (__int64)qword_1800443E8,
      v8,
      v9,
      (__int64)&v12);
  }
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(v11);
  return v6;
}

```

## disassembly

```asm
0x180018f60  mov     [rsp+arg_0], rbx
0x180018f65  push    rdi
0x180018f66  sub     rsp, 40h
0x180018f6a  mov     rbx, r8
0x180018f6d  mov     rdi, rdx
0x180018f70  mov     [rsp+48h+var_18], 0
0x180018f79  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180018f80  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x180018f85  test    al, al
0x180018f87  jz      short loc_180018FB1
0x180018f89  lea     rdx, aNRp; "n.rp"
0x180018f90  lea     rcx, [rsp+48h+arg_18]
0x180018f95  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x180018f9a  mov     rdx, rax
0x180018f9d  lea     rcx, [rsp+48h+var_18]
0x180018fa2  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x180018fa7  lea     rcx, [rsp+48h+arg_18]
0x180018fac  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018fb1  mov     rdx, rbx
0x180018fb4  mov     rcx, rdi
0x180018fb7  call    cs:__imp_NgcRecoverPinSilentWithToken
0x180018fbd  mov     ebx, eax
0x180018fbf  mov     ecx, cs:dword_18004D048
0x180018fc5  cmp     ecx, 5
0x180018fc8  jbe     short loc_180018FFF
0x180018fca  mov     rdx, 400000000000h
0x180018fd4  lea     rcx, dword_18004D048
0x180018fdb  call    _tlgKeywordOn
0x180018fe0  test    al, al
0x180018fe2  jz      short loc_180018FFF
0x180018fe4  mov     dword ptr [rsp+48h+arg_18], ebx
0x180018fe8  lea     rax, [rsp+48h+arg_18]
0x180018fed  mov     [rsp+48h+var_28], rax
0x180018ff2  lea     rdx, qword_1800443E8
0x180018ff9  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180018ffe  nop
0x180018fff  lea     rcx, [rsp+48h+var_18]
0x180019004  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180019009  mov     eax, ebx
0x18001900b  mov     rbx, [rsp+48h+arg_0]
0x180019010  add     rsp, 40h
0x180019014  pop     rdi
0x180019015  retn
```
