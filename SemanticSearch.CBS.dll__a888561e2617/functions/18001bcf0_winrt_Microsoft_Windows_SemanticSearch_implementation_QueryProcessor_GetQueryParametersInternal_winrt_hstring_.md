# winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18001bcf0`
- end: `0x18001bfb7`
- name: `?GetQueryParametersInternal@QueryProcessor@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUQueryParameters@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `711`
- prototype: ``
- caller_count: `4`
- callee_count: `15`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b880`
- `0x18001bb90`
- `0x180053fa0`
- `0x180054370`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180009580`
- `0x18000fc60`
- `0x180010050`
- `0x180010910`
- `0x180011960`
- `0x180015a70`
- `0x1800161b0`
- `0x18001b5c0`
- `0x18001bcf0`
- `0x18001d0d0`
- `0x18001db40`
- `0x18001e260`
- `0x18004c8cc`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001becb`
- `KERNEL32!LeaveCriticalSection` at `0x18001becb`
- `KERNEL32!EnterCriticalSection` at `0x18001be9e`
- `KERNEL32!EnterCriticalSection` at `0x18001be9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd6f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3,
        __int64 a4)
{
  const struct _tlgProvider_t *v8; // rax
  struct _RTL_CRITICAL_SECTION *v9; // rax
  wil::details::in1diag3 *v10; // rcx
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  int v12; // r9d
  __int64 v13; // rdx
  __int64 v14; // rax
  const struct _tlgProvider_t *v15; // rax
  winrt::hresult *v17; // rax
  winrt::hresult *v18; // rax
  winrt::hresult *v19; // rax
  __int64 v20; // [rsp+30h] [rbp-99h] BYREF
  struct _RTL_CRITICAL_SECTION *v21; // [rsp+38h] [rbp-91h] BYREF
  const char *v22; // [rsp+40h] [rbp-89h]
  __int128 v23; // [rsp+48h] [rbp-81h] BYREF
  __int128 v24; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v25[24]; // [rsp+70h] [rbp-59h]
  __int64 v26; // [rsp+88h] [rbp-41h]
  _QWORD v27[3]; // [rsp+90h] [rbp-39h] BYREF
  _QWORD v28[4]; // [rsp+A8h] [rbp-21h] BYREF
  _OWORD v29[3]; // [rsp+C8h] [rbp-1h] BYREF

  *(_QWORD *)&v23 = a2;
  v8 = TraceLogger::Provider();
  if ( *(_DWORD *)v8 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v8,
      (unsigned __int8 *)byte_180079A8D);
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_QP>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_QP>::GetImpl'::`2'::impl) )
  {
    LODWORD(v21) = 54;
    v22 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\QueryParsing\\QueryProcessor.cpp";
    v17 = winrt::hresult::hresult((winrt::hresult *)&v20, -2147467259);
    winrt::throw_hresult(*(unsigned int *)v17, &v21);
  }
  if ( *(_BYTE *)(a1 + 72) )
  {
    LODWORD(v21) = 59;
    v22 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\QueryParsing\\QueryProcessor.cpp";
    v18 = winrt::hresult::hresult((winrt::hresult *)&v20, -2147483629);
    winrt::throw_hresult(*(unsigned int *)v18, &v21);
  }
  if ( !*a3 )
  {
    LODWORD(v21) = 65;
    v22 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\QueryParsing\\QueryProcessor.cpp";
    v19 = winrt::hresult::hresult((winrt::hresult *)&v20, -2147024809);
    winrt::throw_hresult(*(unsigned int *)v19, &v21);
  }
  v9 = (struct _RTL_CRITICAL_SECTION *)CoTaskMemAlloc(0x110u);
  v11 = v9;
  if ( !v9 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v10);
  v9->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::test_data_interface::`vftable';
  *(_QWORD *)&v24 = 0xC10002BF180BLL;
  *((_QWORD *)&v24 + 1) = "QueryParsingTest";
  *(_WORD *)v25 = 1;
  *(_OWORD *)&v25[8] = 0;
  v26 = 0;
  v29[0] = v24;
  v29[1] = *(_OWORD *)v25;
  v29[2] = 0u;
  tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(&v9->LockCount, v9, v29);
  v11->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable';
  LODWORD(v11[6].LockSemaphore) = 1;
  v11[6].OwningThread = &v11->OwningThread;
  v21 = v11;
  tip2::details::shared_data<0,0,0>::start((__int64)&v11->LockCount, &v23);
  v28[0] = a1;
  v28[1] = a3;
  v28[2] = a4;
  v20 = a1 + 40;
  *(_QWORD *)&v23 = a1 + 40;
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal_::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor__winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal_::_2_::_lambda_1____::_2_::_lambda_1___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor__winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal_::_2_::_lambda_1____::_2_::_lambda_2___AIFabricHelpers::SessionWrapper_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor_winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor_winrt::Microsoft::Windows::SemanticSearchInternal::IQueryProcessorSession3_0_::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearch::QueryProcessor__winrt::Microsoft::Windows::SemanticSearch::implementation::QueryProcessor::GetQueryParametersInternal_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)v27,
    (unsigned int)v28,
    (unsigned int)&v23,
    v12,
    (__int64)&v20);
  v28[0] = v27[2];
  *(_QWORD *)&v29[0] = v27[1];
  *(_QWORD *)&v24 = v27[0];
  *(_QWORD *)&v23 = operator new(0x30u);
  v13 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryParameters>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryParameters>(
          v23,
          &v24,
          v29,
          v28);
  v14 = v13 + 16;
  if ( !v13 )
    v14 = 0;
  *a2 = v14;
  EnterCriticalSection(v11 + 5);
  LODWORD(v11[1].SpinCount) |= 0x300u;
  if ( v11[6].DebugInfo )
    tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v11->LockCount, 2u);
  if ( v11 != (struct _RTL_CRITICAL_SECTION *)-200LL )
    LeaveCriticalSection(v11 + 5);
  v15 = TraceLogger::Provider();
  if ( *(_DWORD *)v15 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v15,
      (unsigned __int8 *)&dword_180079A74);
  winrt::Microsoft::Windows::SemanticSearchInternal::QueryParametersInternal::~QueryParametersInternal((winrt::Microsoft::Windows::SemanticSearchInternal::QueryParametersInternal *)v27);
  tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(v11);
  return a2;
}

```

## disassembly

```asm
0x18001bcf0  mov     [rsp-8+arg_0], rbx
0x18001bcf5  mov     [rsp-8+arg_10], rsi
0x18001bcfa  mov     [rsp-8+arg_18], rdi
0x18001bcff  push    rbp
0x18001bd00  push    r12
0x18001bd02  push    r13
0x18001bd04  push    r14
0x18001bd06  push    r15
0x18001bd08  lea     rbp, [rsp-37h]
0x18001bd0d  sub     rsp, 100h
0x18001bd14  mov     r12, r9
0x18001bd17  mov     r14, r8
0x18001bd1a  mov     rdi, rdx
0x18001bd1d  mov     rsi, rcx
0x18001bd20  mov     qword ptr [rsp+120h+var_D8], rdx
0x18001bd25  xor     r13d, r13d
0x18001bd28  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001bd2d  cmp     dword ptr [rax], 5
0x18001bd30  jbe     short loc_18001BD41
0x18001bd32  lea     rdx, byte_180079A8D
0x18001bd39  mov     rcx, rax
0x18001bd3c  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001bd41  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_QP@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_QP@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_QP> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_QP>::GetImpl(void)'::`2'::impl
0x18001bd48  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_QP@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_QP>::__private_IsEnabled(void)
0x18001bd4d  test    al, al
0x18001bd4f  jz      loc_18001BF27
0x18001bd55  movzx   eax, byte ptr [rsi+48h]
0x18001bd59  test    al, al
0x18001bd5b  jnz     loc_18001BF57
0x18001bd61  cmp     [r14], r13
0x18001bd64  jz      loc_18001BF87
0x18001bd6a  mov     ecx, 110h; cb
0x18001bd6f  call    cs:__imp_CoTaskMemAlloc
0x18001bd75  mov     rbx, rax
0x18001bd78  test    rax, rax
0x18001bd7b  jz      loc_18001BF21
0x18001bd81  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18001bd88  mov     [rbx], rax
0x18001bd8b  mov     dword ptr [rbp+57h+var_C0], 2BF180Bh
0x18001bd92  mov     dword ptr [rbp+57h+var_C0+4], 0C100h
0x18001bd99  lea     rax, aQueryparsingte; "QueryParsingTest"
0x18001bda0  mov     qword ptr [rbp+57h+var_C0+8], rax
0x18001bda4  mov     word ptr [rbp+57h+var_B0], 1
0x18001bdaa  xorps   xmm0, xmm0
0x18001bdad  movdqu  xmmword ptr [rbp+57h+var_B0+8], xmm0
0x18001bdb2  mov     [rbp+57h+var_98], r13
0x18001bdb6  movups  xmm0, [rbp+57h+var_C0]
0x18001bdba  movups  [rbp+57h+var_58], xmm0
0x18001bdbe  movups  xmm1, xmmword ptr [rbp+57h+var_B0]
0x18001bdc2  movups  [rbp+57h+var_48], xmm1
0x18001bdc6  movups  xmm0, xmmword ptr [rbp-49h]
0x18001bdca  movups  [rbp+57h+var_38], xmm0
0x18001bdce  lea     r8, [rbp+57h+var_58]
0x18001bdd2  mov     rdx, rbx
0x18001bdd5  lea     rcx, [rbx+8]
0x18001bdd9  call    ??0?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@AEAUtest_data_interface@12@AEBUtest_info@2@@Z; tip2::details::shared_data<0,0,0>::shared_data<0,0,0>(tip2::details::test_data_interface &,tip2::test_info const &)
0x18001bdde  lea     rax, ??_7?$merged_data@U_tip_ImageEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ImageEmbeddingsTest,AIFabricTipTest::_tip_ImageEmbeddingsTest>::`vftable'
0x18001bde5  mov     [rbx], rax
0x18001bde8  mov     dword ptr [rbx+108h], 1
0x18001bdf2  lea     rax, [rbx+10h]
0x18001bdf6  mov     [rbx+100h], rax
0x18001bdfd  mov     [rsp+120h+var_E8], rbx
0x18001be02  lea     rdx, [rsp+120h+var_D8]
0x18001be07  lea     rcx, [rbx+8]
0x18001be0b  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x18001be10  nop
0x18001be11  lea     rax, [rsi+28h]
0x18001be15  mov     [rbp+57h+var_78], rsi
0x18001be19  mov     [rbp+57h+var_70], r14
0x18001be1d  mov     [rbp+57h+var_68], r12
0x18001be21  mov     [rsp+120h+var_F0], rax
0x18001be26  mov     qword ptr [rsp+120h+var_D8], rax
0x18001be2b  lea     rax, [rsp+120h+var_F0]
0x18001be30  mov     [rsp+120h+var_100], rax
0x18001be35  lea     r8, [rsp+120h+var_D8]
0x18001be3a  lea     rdx, [rbp+57h+var_78]
0x18001be3e  lea     rcx, [rbp+57h+var_90]
0x18001be42  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor__GetQueryParametersInternal____2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor_winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor_winrt__Microsoft__Windows__SemanticSearchInternal__IQueryProcessorSession3_0___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor__winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor__GetQueryParametersInternal____2____lambda_1_______2____lambda_1___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor_winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor_winrt__Microsoft__Windows__SemanticSearchInternal__IQueryProcessorSession3_0___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor__winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor__GetQueryParametersInternal____2____lambda_1_______2____lambda_2___AIFabricHelpers__SessionWrapper_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor_winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor_winrt__Microsoft__Windows__SemanticSearchInternal__IQueryProcessorSession3_0___TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearch__QueryProcessor__winrt__Microsoft__Windows__SemanticSearch__implementation__QueryProcessor__GetQueryParametersInternal____2____lambda_1_______2____lambda_3___
0x18001be47  nop
0x18001be48  mov     rax, [rbp+57h+var_80]
0x18001be4c  mov     [rbp+57h+var_78], rax
0x18001be50  mov     rax, [rbp+57h+var_88]
0x18001be54  mov     qword ptr [rbp+57h+var_58], rax
0x18001be58  mov     rax, [rbp+57h+var_90]
0x18001be5c  mov     qword ptr [rbp+57h+var_C0], rax
0x18001be60  mov     ecx, 30h ; '0'; Size
0x18001be65  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001be6a  mov     qword ptr [rsp+120h+var_D8], rax
0x18001be6f  lea     r9, [rbp+57h+var_78]
0x18001be73  lea     r8, [rbp+57h+var_58]
0x18001be77  lea     rdx, [rbp+57h+var_C0]
0x18001be7b  mov     rcx, rax
0x18001be7e  call    ??0?$heap_implements@UQueryParameters@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@AEBUhstring@2@00@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryParameters>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::QueryParameters>(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)
0x18001be83  mov     rdx, rax
0x18001be86  add     rax, 10h
0x18001be8a  test    rdx, rdx
0x18001be8d  cmovz   rax, r13
0x18001be91  mov     [rdi], rax
0x18001be94  lea     rsi, [rbx+0C8h]
0x18001be9b  mov     rcx, rsi; lpCriticalSection
0x18001be9e  call    cs:__imp_EnterCriticalSection
0x18001bea4  or      dword ptr [rbx+48h], 300h
0x18001beab  cmp     qword ptr [rbx+0F0h], 0
0x18001beb3  jz      short loc_18001BEC3
0x18001beb5  mov     edx, 2
0x18001beba  lea     rcx, [rbx+8]
0x18001bebe  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001bec3  test    rsi, rsi
0x18001bec6  jz      short loc_18001BED1
0x18001bec8  mov     rcx, rsi; lpCriticalSection
0x18001becb  call    cs:__imp_LeaveCriticalSection
0x18001bed1  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18001bed6  cmp     dword ptr [rax], 5
0x18001bed9  jbe     short loc_18001BEEB
0x18001bedb  lea     rdx, dword_180079A74
0x18001bee2  mov     rcx, rax
0x18001bee5  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001beea  nop
0x18001beeb  lea     rcx, [rbp+57h+var_90]; this
0x18001beef  call    ??1QueryParametersInternal@SemanticSearchInternal@Windows@Microsoft@winrt@@QEAA@XZ; winrt::Microsoft::Windows::SemanticSearchInternal::QueryParametersInternal::~QueryParametersInternal(void)
0x18001bef4  nop
0x18001bef5  mov     rcx, rbx; pv
0x18001bef8  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x18001befd  mov     rax, rdi
0x18001bf00  lea     r11, [rsp+120h+var_20]
0x18001bf08  mov     rbx, [r11+30h]
0x18001bf0c  mov     rsi, [r11+40h]
0x18001bf10  mov     rdi, [r11+48h]
0x18001bf14  mov     rsp, r11
0x18001bf17  pop     r15
0x18001bf19  pop     r14
0x18001bf1b  pop     r13
0x18001bf1d  pop     r12
0x18001bf1f  pop     rbp
0x18001bf20  retn
0x18001bf21  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001bf27  mov     dword ptr [rsp+120h+var_E8], 36h ; '6'
0x18001bf2f  lea     rax, aCW1SProductApi_21; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001bf36  mov     [rsp+120h+var_E0], rax
0x18001bf3b  mov     edx, 80004005h; int
0x18001bf40  lea     rcx, [rsp+120h+var_F0]; this
0x18001bf45  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001bf4a  lea     rdx, [rsp+120h+var_E8]
0x18001bf4f  mov     ecx, [rax]
0x18001bf51  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001bf57  mov     dword ptr [rsp+120h+var_E8], 3Bh ; ';'
0x18001bf5f  lea     rax, aCW1SProductApi_21; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001bf66  mov     [rsp+120h+var_E0], rax
0x18001bf6b  mov     edx, 80000013h; int
0x18001bf70  lea     rcx, [rsp+120h+var_F0]; this
0x18001bf75  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001bf7a  lea     rdx, [rsp+120h+var_E8]
0x18001bf7f  mov     ecx, [rax]
0x18001bf81  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18001bf87  mov     dword ptr [rsp+120h+var_E8], 41h ; 'A'
0x18001bf8f  lea     rax, aCW1SProductApi_21; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18001bf96  mov     [rsp+120h+var_E0], rax
0x18001bf9b  mov     edx, 80070057h; int
0x18001bfa0  lea     rcx, [rsp+120h+var_F0]; this
0x18001bfa5  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18001bfaa  lea     rdx, [rsp+120h+var_E8]
0x18001bfaf  mov     ecx, [rax]
0x18001bfb1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
