# NgcFunctions::NgcCreateUserIdKeyEx(_NGC_IDP_ACCOUNT_INFO *,ushort const *,HWND__ *,ushort const *,unsigned __int64,ulong,ushort * *,uchar * *,ulong *,unsigned __int64 *)

- ea: `0x180018230`
- end: `0x18001834a`
- name: `?NgcCreateUserIdKeyEx@NgcFunctions@@UEAAJPEAU_NGC_IDP_ACCOUNT_INFO@@PEBGPEAUHWND__@@1_KKPEAPEAGPEAPEAEPEAKPEA_K@Z`
- size: `282`
- prototype: `__int64 __fastcall(NgcFunctions *__hidden this, struct _NGC_IDP_ACCOUNT_INFO *, const unsigned __int16 *, HWND, const unsigned __int16 *, unsigned __int64, unsigned int, unsigned __int16 **, unsigned __int8 **, unsigned int *, unsigned __int64 *)`
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
- `0x180018230`

## import_xrefs

- `cryptngc!NgcCreateUserIdKeyEx` at `0x1800182e6`
- `cryptngc!NgcCreateUserIdKeyEx` at `0x1800182e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcFunctions::NgcCreateUserIdKeyEx(
        NgcFunctions *this,
        struct _NGC_IDP_ACCOUNT_INFO *a2,
        const unsigned __int16 *a3,
        HWND a4,
        const unsigned __int16 *a5,
        unsigned __int64 a6,
        unsigned int a7,
        unsigned __int16 **a8,
        unsigned __int8 **a9,
        unsigned int *a10,
        unsigned __int64 *a11)
{
  __int64 *v14; // rax
  unsigned int UserIdKey; // ebx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  __int64 v20; // [rsp+50h] [rbp-18h] BYREF
  __int64 v21[2]; // [rsp+58h] [rbp-10h] BYREF

  v21[0] = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl'::`2'::impl) )
  {
    v14 = std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,unsigned short const (&)[5],0>(
            &v20,
            L"n.ce");
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(
      v21,
      v14);
    std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(&v20);
  }
  UserIdKey = NgcCreateUserIdKeyEx(a2, a3, a4, a5, a6, a7, a8, a9, a10, a11);
  if ( (unsigned int)dword_18004D048 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18004D048, 0x400000000000LL) )
  {
    LODWORD(v20) = UserIdKey;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      v16,
      (__int64)byte_1800444C5,
      v17,
      v18,
      (__int64)&v20);
  }
  std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(v21);
  return UserIdKey;
}

```

## disassembly

```asm
0x180018230  mov     [rsp+arg_0], rbx
0x180018235  mov     [rsp+arg_8], rsi
0x18001823a  push    rdi
0x18001823b  sub     rsp, 60h
0x18001823f  mov     rbx, r9
0x180018242  mov     rdi, r8
0x180018245  mov     rsi, rdx
0x180018248  mov     [rsp+68h+var_10], 0
0x180018251  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry> `wil::Feature<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::GetImpl(void)'::`2'::impl
0x180018258  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EnhancedPerfTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnhancedPerfTelemetry>::__private_IsEnabled(void)
0x18001825d  test    al, al
0x18001825f  jz      short loc_180018289
0x180018261  lea     rdx, aNCe; "n.ce"
0x180018268  lea     rcx, [rsp+68h+var_18]
0x18001826d  call    ??$make_unique@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@AEAY04$$CBG$0A@@std@@YA?AV?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@0@AEAY04$$CBG@Z; std::make_unique<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation,ushort const (&)[5],0>(ushort const (&)[5])
0x180018272  mov     rdx, rax
0x180018275  lea     rcx, [rsp+68h+var_10]
0x18001827a  call    ??$?4U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@$0A@@?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::operator=<std::default_delete<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>,0>(std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation> &&)
0x18001827f  lea     rcx, [rsp+68h+var_18]
0x180018284  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018289  mov     rax, [rsp+68h+arg_50]
0x180018291  mov     [rsp+68h+var_20], rax
0x180018296  mov     rax, [rsp+68h+arg_48]
0x18001829e  mov     [rsp+68h+var_28], rax
0x1800182a3  mov     rax, [rsp+68h+arg_40]
0x1800182ab  mov     [rsp+68h+var_30], rax
0x1800182b0  mov     rax, [rsp+68h+arg_38]
0x1800182b8  mov     [rsp+68h+var_38], rax
0x1800182bd  mov     eax, [rsp+68h+arg_30]
0x1800182c4  mov     [rsp+68h+var_40], eax
0x1800182c8  mov     rax, [rsp+68h+arg_28]
0x1800182d0  mov     [rsp+68h+var_48], rax
0x1800182d5  mov     r9, [rsp+68h+arg_20]
0x1800182dd  mov     r8, rbx
0x1800182e0  mov     rdx, rdi
0x1800182e3  mov     rcx, rsi
0x1800182e6  call    cs:__imp_NgcCreateUserIdKeyEx
0x1800182ec  mov     ebx, eax
0x1800182ee  mov     ecx, cs:dword_18004D048
0x1800182f4  cmp     ecx, 5
0x1800182f7  jbe     short loc_18001832E
0x1800182f9  mov     rdx, 400000000000h
0x180018303  lea     rcx, dword_18004D048
0x18001830a  call    _tlgKeywordOn
0x18001830f  test    al, al
0x180018311  jz      short loc_18001832E
0x180018313  mov     dword ptr [rsp+68h+var_18], ebx
0x180018317  lea     rax, [rsp+68h+var_18]
0x18001831c  mov     [rsp+68h+var_48], rax
0x180018321  lea     rdx, byte_1800444C5
0x180018328  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18001832d  nop
0x18001832e  lea     rcx, [rsp+68h+var_10]
0x180018333  call    ??1?$unique_ptr@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@U?$default_delete@VScopedRequestTelemetryOperation@OnlineId@Authentication@Security@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>::~unique_ptr<Windows::Internal::Security::Authentication::OnlineId::ScopedRequestTelemetryOperation>(void)
0x180018338  mov     eax, ebx
0x18001833a  mov     rbx, [rsp+68h+arg_0]
0x18001833f  mov     rsi, [rsp+68h+arg_8]
0x180018344  add     rsp, 60h
0x180018348  pop     rdi
0x180018349  retn
```
