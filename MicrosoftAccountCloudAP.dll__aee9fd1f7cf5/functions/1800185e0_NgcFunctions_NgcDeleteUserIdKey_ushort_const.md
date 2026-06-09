# NgcFunctions::NgcDeleteUserIdKey(ushort const *)

- ea: `0x1800185e0`
- end: `0x180018647`
- name: `?NgcDeleteUserIdKey@NgcFunctions@@UEAAJPEBG@Z`
- size: `103`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800168f0`
- `0x180016924`
- `0x18001696c`
- `0x1800176a4`
- `0x1800185e0`

## import_xrefs

- `cryptngc!NgcDeleteUserIdKey` at `0x18001862d`
- `cryptngc!NgcDeleteUserIdKey` at `0x18001862d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcDeleteUserIdKey(NgcFunctions *this, const unsigned __int16 *a2)
{
  __int64 *v3; // rax
  unsigned int v4; // ebx
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF
  __int64 v7; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v3 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
           &v7,
           L"n.du");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      &v6,
      v3);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v7);
  }
  v4 = NgcDeleteUserIdKey(a2);
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v6);
  return v4;
}

```

## disassembly

```asm
0x1800185e0  push    rbx
0x1800185e2  sub     rsp, 20h
0x1800185e6  mov     rbx, rdx
0x1800185e9  mov     [rsp+28h+arg_10], 0
0x1800185f2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x1800185f9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x1800185fe  test    al, al
0x180018600  jz      short loc_18001862A
0x180018602  lea     rdx, aNDu; "n.du"
0x180018609  lea     rcx, [rsp+28h+arg_18]
0x18001860e  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x180018613  mov     rdx, rax
0x180018616  lea     rcx, [rsp+28h+arg_10]
0x18001861b  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x180018620  lea     rcx, [rsp+28h+arg_18]
0x180018625  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x18001862a  mov     rcx, rbx
0x18001862d  call    cs:__imp_NgcDeleteUserIdKey
0x180018633  mov     ebx, eax
0x180018635  lea     rcx, [rsp+28h+arg_10]
0x18001863a  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x18001863f  mov     eax, ebx
0x180018641  add     rsp, 20h
0x180018645  pop     rbx
0x180018646  retn
```
