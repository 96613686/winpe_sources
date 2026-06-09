# NgcFunctions::NgcDeleteContainerEx(ushort const *,ulong)

- ea: `0x180018520`
- end: `0x1800185d5`
- name: `?NgcDeleteContainerEx@NgcFunctions@@UEAAJPEBGK@Z`
- size: `181`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, const unsigned __int16 *, unsigned int)`
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
- `0x180018520`

## import_xrefs

- `cryptngc!NgcDeleteContainerEx` at `0x180018576`
- `cryptngc!NgcDeleteContainerEx` at `0x180018576`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcDeleteContainerEx(NgcFunctions *this, const unsigned __int16 *a2, unsigned int a3)
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
           L"n.de");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      v11,
      v5);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v12);
  }
  v6 = NgcDeleteContainerEx(a2, a3);
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    LODWORD(v12) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v7,
      (__int64)byte_180044559,
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
0x180018520  mov     [rsp+arg_0], rbx
0x180018525  push    rdi
0x180018526  sub     rsp, 40h
0x18001852a  mov     ebx, r8d
0x18001852d  mov     rdi, rdx
0x180018530  mov     [rsp+48h+var_18], 0
0x180018539  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180018540  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x180018545  test    al, al
0x180018547  jz      short loc_180018571
0x180018549  lea     rdx, aNDe; "n.de"
0x180018550  lea     rcx, [rsp+48h+arg_18]
0x180018555  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x18001855a  mov     rdx, rax
0x18001855d  lea     rcx, [rsp+48h+var_18]
0x180018562  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x180018567  lea     rcx, [rsp+48h+arg_18]
0x18001856c  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018571  mov     edx, ebx
0x180018573  mov     rcx, rdi
0x180018576  call    cs:__imp_NgcDeleteContainerEx
0x18001857c  mov     ebx, eax
0x18001857e  mov     ecx, cs:dword_18004D048
0x180018584  cmp     ecx, 5
0x180018587  jbe     short loc_1800185BE
0x180018589  mov     rdx, 400000000000h
0x180018593  lea     rcx, dword_18004D048
0x18001859a  call    _tlgKeywordOn
0x18001859f  test    al, al
0x1800185a1  jz      short loc_1800185BE
0x1800185a3  mov     dword ptr [rsp+48h+arg_18], ebx
0x1800185a7  lea     rax, [rsp+48h+arg_18]
0x1800185ac  mov     [rsp+48h+var_28], rax
0x1800185b1  lea     rdx, byte_180044559
0x1800185b8  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800185bd  nop
0x1800185be  lea     rcx, [rsp+48h+var_18]
0x1800185c3  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x1800185c8  mov     eax, ebx
0x1800185ca  mov     rbx, [rsp+48h+arg_0]
0x1800185cf  add     rsp, 40h
0x1800185d3  pop     rdi
0x1800185d4  retn
```
