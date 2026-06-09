# NgcFunctions::NgcDeleteContainer(ushort const *,ushort const *,ushort const *)

- ea: `0x180018450`
- end: `0x180018516`
- name: `?NgcDeleteContainer@NgcFunctions@@UEAAJPEBG00@Z`
- size: `198`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
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
- `0x180018450`

## import_xrefs

- `cryptngc!NgcDeleteContainer` at `0x1800184b2`
- `cryptngc!NgcDeleteContainer` at `0x1800184b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcDeleteContainer(
        NgcFunctions *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v13; // [rsp+30h] [rbp-18h] BYREF
  __int64 v14[2]; // [rsp+38h] [rbp-10h] BYREF

  v14[0] = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v7 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
           &v13,
           L"n.dc");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      v14,
      v7);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v13);
  }
  v8 = NgcDeleteContainer(a2, a3, a4);
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    LODWORD(v13) = v8;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v9,
      (__int64)byte_180044581,
      v10,
      v11,
      (__int64)&v13);
  }
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(v14);
  return v8;
}

```

## disassembly

```asm
0x180018450  mov     [rsp+arg_0], rbx
0x180018455  mov     [rsp+arg_8], rsi
0x18001845a  push    rdi
0x18001845b  sub     rsp, 40h
0x18001845f  mov     rbx, r9
0x180018462  mov     rdi, r8
0x180018465  mov     rsi, rdx
0x180018468  mov     [rsp+48h+var_10], 0
0x180018471  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180018478  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18001847d  test    al, al
0x18001847f  jz      short loc_1800184A9
0x180018481  lea     rdx, aNDc; "n.dc"
0x180018488  lea     rcx, [rsp+48h+var_18]
0x18001848d  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x180018492  mov     rdx, rax
0x180018495  lea     rcx, [rsp+48h+var_10]
0x18001849a  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x18001849f  lea     rcx, [rsp+48h+var_18]
0x1800184a4  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x1800184a9  mov     r8, rbx
0x1800184ac  mov     rdx, rdi
0x1800184af  mov     rcx, rsi
0x1800184b2  call    cs:__imp_NgcDeleteContainer
0x1800184b8  mov     ebx, eax
0x1800184ba  mov     ecx, cs:dword_18004D048
0x1800184c0  cmp     ecx, 5
0x1800184c3  jbe     short loc_1800184FA
0x1800184c5  mov     rdx, 400000000000h
0x1800184cf  lea     rcx, dword_18004D048
0x1800184d6  call    _tlgKeywordOn
0x1800184db  test    al, al
0x1800184dd  jz      short loc_1800184FA
0x1800184df  mov     dword ptr [rsp+48h+var_18], ebx
0x1800184e3  lea     rax, [rsp+48h+var_18]
0x1800184e8  mov     [rsp+48h+var_28], rax
0x1800184ed  lea     rdx, byte_180044581
0x1800184f4  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1800184f9  nop
0x1800184fa  lea     rcx, [rsp+48h+var_10]
0x1800184ff  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018504  mov     eax, ebx
0x180018506  mov     rbx, [rsp+48h+arg_0]
0x18001850b  mov     rsi, [rsp+48h+arg_8]
0x180018510  add     rsp, 40h
0x180018514  pop     rdi
0x180018515  retn
```
