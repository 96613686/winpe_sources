# AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>(void)

- ea: `0x18003f9f0`
- end: `0x18003fb45`
- name: `??$IsAvailable@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA_NXZ`
- size: `341`
- prototype: `__int64()`
- caller_count: `3`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003ff20`
- `0x1800480f0`
- `0x18005dd60`

## callees

- `0x1800018b0`
- `0x180008520`
- `0x180008600`
- `0x180010230`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180015a70`
- `0x18003f9f0`
- `0x1800406a0`
- `0x18004c070`

## string_xrefs

- `0x18003fa61`: `Microsoft.Windows.SemanticSearch.Tokenizer`
- `0x18003face`: `Microsoft.Windows.SemanticSearch.Tokenizer`

## pseudocode

```c
__int64 AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>()
{
  const struct _tlgProvider_t *v0; // rax
  const wchar_t *v1; // rbx
  _DWORD *v2; // rcx
  TelemetryLogger *v3; // rax
  const wchar_t *v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  wchar_t *v7[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v8; // [rsp+30h] [rbp-28h]

  v0 = TraceLogger::Provider();
  if ( *(_DWORD *)v0 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v0,
      word_18007998A);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`7'::__apiCallCounter) != 1 )
      goto LABEL_15;
    *(_OWORD *)v7 = 0;
    v8 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v7, L"Microsoft.Windows.SemanticSearch.Tokenizer", 0x2Au);
    v1 = (const wchar_t *)v7;
    if ( *((_QWORD *)&v8 + 1) > 7u )
      v1 = v7[0];
    v2 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
    if ( v2 && *v2 )
    {
      v3 = TelemetryLogger::Instance();
      TelemetryLogger::InitApiData_(
        v3,
        v1,
        L"IsAvailable",
        &`AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>'::`7'::__apiCallCounter);
    }
  }
  else
  {
    *(_OWORD *)v7 = 0;
    v8 = 0;
    std::wstring::_Construct<1,wchar_t const *>(v7, L"Microsoft.Windows.SemanticSearch.Tokenizer", 0x2Au);
    v4 = (const wchar_t *)v7;
    if ( *((_QWORD *)&v8 + 1) > 7u )
      v4 = v7[0];
    TelemetryLogger::LogWclApiUsage(v4, L"IsAvailable");
  }
  std::wstring::_Tidy_deallocate(v7);
LABEL_15:
  v5 = TraceLogger::Provider();
  if ( *(_DWORD *)v5 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v5,
      &word_180079816);
  *(_OWORD *)v7 = 0;
  return AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>(v7);
}

```

## disassembly

```asm
0x18003f9f0  push    rbx
0x18003f9f2  sub     rsp, 50h
0x18003f9f6  mov     rax, cs:__security_cookie
0x18003f9fd  xor     rax, rsp
0x18003fa00  mov     [rsp+58h+var_18], rax
0x18003fa05  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18003fa0a  cmp     dword ptr [rax], 5
0x18003fa0d  jbe     short loc_18003FA1E
0x18003fa0f  lea     rdx, word_18007998A
0x18003fa16  mov     rcx, rax
0x18003fa19  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003fa1e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18003fa25  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18003fa2a  test    al, al
0x18003fa2c  jz      loc_18003FAB7
0x18003fa32  mov     eax, 1
0x18003fa37  lock xadd cs:?__apiCallCounter@?6???$IsAvailable@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA_NXZ@4JC, eax; long volatile `AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>(void)'::`7'::__apiCallCounter
0x18003fa3f  inc     eax
0x18003fa41  cmp     eax, 1
0x18003fa44  jnz     loc_18003FB06
0x18003fa4a  xorps   xmm0, xmm0
0x18003fa4d  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18003fa52  xorps   xmm1, xmm1
0x18003fa55  movdqu  [rsp+58h+var_28], xmm1
0x18003fa5b  mov     r8d, 2Ah ; '*'
0x18003fa61  lea     rdx, aMicrosoftWindo_8; "Microsoft.Windows.SemanticSearch.Tokeni"...
0x18003fa68  lea     rcx, [rsp+58h+var_38]
0x18003fa6d  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003fa72  lea     rbx, [rsp+58h+var_38]
0x18003fa77  cmp     qword ptr [rsp+58h+var_28+8], 7
0x18003fa7d  cmova   rbx, [rsp+58h+var_38]
0x18003fa83  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18003fa88  mov     rcx, [rax+8]
0x18003fa8c  test    rcx, rcx
0x18003fa8f  jz      short loc_18003FAB5
0x18003fa91  cmp     dword ptr [rcx], 0
0x18003fa94  jbe     short loc_18003FAB5
0x18003fa96  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18003fa9b  lea     r9, ?__apiCallCounter@?6???$IsAvailable@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA_NXZ@4JC; volatile int *
0x18003faa2  lea     r8, aIsavailable; "IsAvailable"
0x18003faa9  mov     rdx, rbx; wchar_t *
0x18003faac  mov     rcx, rax; this
0x18003faaf  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18003fab4  nop
0x18003fab5  jmp     short loc_18003FAFC
0x18003fab7  xorps   xmm0, xmm0
0x18003faba  movups  xmmword ptr [rsp+58h+var_38], xmm0
0x18003fabf  xorps   xmm1, xmm1
0x18003fac2  movdqu  [rsp+58h+var_28], xmm1
0x18003fac8  mov     r8d, 2Ah ; '*'
0x18003face  lea     rdx, aMicrosoftWindo_8; "Microsoft.Windows.SemanticSearch.Tokeni"...
0x18003fad5  lea     rcx, [rsp+58h+var_38]
0x18003fada  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18003fadf  lea     rcx, [rsp+58h+var_38]
0x18003fae4  cmp     qword ptr [rsp+58h+var_28+8], 7
0x18003faea  cmova   rcx, [rsp+58h+var_38]; wchar_t *
0x18003faf0  lea     rdx, aIsavailable; "IsAvailable"
0x18003faf7  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18003fafc  lea     rcx, [rsp+58h+var_38]
0x18003fb01  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003fb06  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18003fb0b  cmp     dword ptr [rax], 5
0x18003fb0e  jbe     short loc_18003FB1F
0x18003fb10  lea     rdx, word_180079816
0x18003fb17  mov     rcx, rax
0x18003fb1a  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18003fb1f  xorps   xmm0, xmm0
0x18003fb22  movdqa  xmmword ptr [rsp+58h+var_38], xmm0
0x18003fb28  lea     rcx, [rsp+58h+var_38]
0x18003fb2d  call    ??$IsAvailable@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@@?$SessionWrapper@UTokenizer@SemanticSearch@Windows@Microsoft@winrt@@U1implementation@2345@UITokenizerSession2@SemanticSearchInternal@345@$0A@@AIFabricHelpers@@SA_NUguid@winrt@@@Z; AIFabricHelpers::SessionWrapper<winrt::Microsoft::Windows::SemanticSearch::Tokenizer,winrt::Microsoft::Windows::SemanticSearch::implementation::Tokenizer,winrt::Microsoft::Windows::SemanticSearchInternal::ITokenizerSession2,0>::IsAvailable<winrt::Microsoft::Windows::SemanticSearch::Tokenizer>(winrt::guid)
0x18003fb32  mov     rcx, [rsp+58h+var_18]
0x18003fb37  xor     rcx, rsp; StackCookie
0x18003fb3a  call    __security_check_cookie
0x18003fb3f  add     rsp, 50h
0x18003fb43  pop     rbx
0x18003fb44  retn
```
