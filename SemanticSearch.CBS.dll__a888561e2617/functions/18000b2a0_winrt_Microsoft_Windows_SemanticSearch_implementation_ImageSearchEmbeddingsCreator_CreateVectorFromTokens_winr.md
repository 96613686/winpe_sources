# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens(winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)

- ea: `0x18000b2a0`
- end: `0x18000b6a4`
- name: `?CreateVectorFromTokens@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUEmbeddingVector@3456@U?$array_view@$$CB_J@6@AEBW4WorkloadPriority@Workloads@456@@Z`
- size: `1028`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `broker_com_uri`

## callers

- `0x18000e390`
- `0x18000e410`

## callees

- `0x1800018b0`
- `0x180001f40`
- `0x180002bb0`
- `0x180008840`
- `0x180009580`
- `0x18000b2a0`
- `0x18000b6b0`
- `0x18000cf50`
- `0x18000ed90`
- `0x18000f690`
- `0x18000fba0`
- `0x18000fc60`
- `0x180010230`
- `0x180010740`
- `0x180010910`
- `0x180014540`
- `0x180015090`
- `0x1800151a0`
- `0x180015450`
- `0x180015a70`
- `0x18004c070`
- `0x18004c8cc`
- `0x180051379`
- `0x18005137f`
- `0x18005e260`
- `0x18005e2c0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000b3c5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000b636`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000b3c5`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000b636`
- `KERNEL32!LeaveCriticalSection` at `0x18000b576`
- `KERNEL32!LeaveCriticalSection` at `0x18000b576`
- `KERNEL32!EnterCriticalSection` at `0x18000b549`
- `KERNEL32!EnterCriticalSection` at `0x18000b549`

## string_xrefs

- `0x18000b392`: `CreateVectorFromTokens`
- `0x18000b3f5`: `CreateVectorFromTokens`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 *__fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens(
        unsigned int *a1,
        __int64 *a2,
        __int64 a3,
        int *a4)
{
  char v8; // bl
  __int64 v9; // rax
  const wchar_t *v10; // rbx
  _DWORD *v11; // rcx
  TelemetryLogger *v12; // rax
  void *v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  const wchar_t *v16; // rbx
  int v17; // eax
  HANDLE ProcessHeap; // rax
  const struct _tlgProvider_t *v19; // rax
  int v20; // r9d
  __int64 v21; // rdi
  size_t v22; // rdi
  size_t v23; // rbx
  __int64 v24; // rdx
  __int64 v25; // r8
  int v26; // eax
  const struct _tlgProvider_t *v27; // rax
  struct _RTL_CRITICAL_SECTION *v28; // rbx
  __int128 *v29; // rdi
  __int64 v30; // rax
  __int64 v31; // rcx
  winrt::hresult *v33; // rax
  winrt::hresult *v34; // rax
  LPVOID lpMem[2]; // [rsp+30h] [rbp-69h] BYREF
  unsigned int *v36; // [rsp+40h] [rbp-59h] BYREF
  const char *v37; // [rsp+48h] [rbp-51h]
  __int64 *v38; // [rsp+50h] [rbp-49h] BYREF
  const char *v39; // [rsp+58h] [rbp-41h]
  _QWORD v40[2]; // [rsp+60h] [rbp-39h] BYREF
  __int64 v41; // [rsp+70h] [rbp-29h] BYREF
  int v42; // [rsp+78h] [rbp-21h]
  unsigned int *v43; // [rsp+80h] [rbp-19h]
  __int128 v44; // [rsp+90h] [rbp-9h] BYREF
  __int128 v45; // [rsp+A0h] [rbp+7h] BYREF
  size_t v46; // [rsp+B0h] [rbp+17h]

  v38 = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::GetImpl'::`2'::impl) )
  {
    LODWORD(v38) = 170;
    v39 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v33 = winrt::hresult::hresult((winrt::hresult *)lpMem, -2147467259);
    winrt::throw_hresult(*(unsigned int *)v33, &v38);
  }
  lpMem[0] = 0;
  v8 = winrt::Windows::Foundation::operator==(a1 + 14, lpMem);
  if ( lpMem[0] )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(lpMem);
  if ( v8 )
  {
    LODWORD(v38) = 175;
    v39 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\ImageSearch\\ImageSearchEmbeddingsCreator.cpp";
    v34 = winrt::hresult::hresult((winrt::hresult *)lpMem, -2147483629);
    winrt::throw_hresult(*(unsigned int *)v34, &v38);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
  {
    if ( _InterlockedIncrement(&dword_180086680) == 1 )
    {
      v9 = (*(__int64 (__fastcall **)(unsigned int *, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
      if ( *(_QWORD *)v9 )
        v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
      else
        v10 = (const wchar_t *)&qword_18006D0D8;
      v11 = (_DWORD *)*((_QWORD *)TelemetryLogger::Instance() + 1);
      if ( v11 && *v11 )
      {
        v12 = TelemetryLogger::Instance();
        TelemetryLogger::InitApiData_(v12, v10, L"CreateVectorFromTokens", &dword_180086680);
      }
      v13 = lpMem[0];
      if ( lpMem[0] )
      {
        v14 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
        if ( v14 )
        {
          if ( v14 < 0 )
            abort();
          goto LABEL_23;
        }
LABEL_22:
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
LABEL_23:
        lpMem[0] = 0;
      }
    }
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(unsigned int *, LPVOID *))(*(_QWORD *)a1 + 40LL))(a1, lpMem);
    if ( *(_QWORD *)v15 )
      v16 = *(const wchar_t **)(*(_QWORD *)v15 + 16LL);
    else
      v16 = (const wchar_t *)&qword_18006D0D8;
    TelemetryLogger::LogWclApiUsage(v16, L"CreateVectorFromTokens");
    v13 = lpMem[0];
    if ( lpMem[0] )
    {
      v17 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v17 )
      {
        if ( v17 < 0 )
          abort();
        goto LABEL_23;
      }
      goto LABEL_22;
    }
  }
  lpMem[0] = 0;
  tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(lpMem);
  v19 = TraceLogger::Provider();
  if ( *(_DWORD *)v19 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v19,
      (unsigned __int8 *)&dword_18007933C);
  v21 = a1[16];
  v45 = 0;
  v46 = 0;
  if ( v21 )
  {
    _mm_lfence();
    v22 = 4 * v21;
    *(_QWORD *)&v45 = std::_Allocate<16,std::_Default_allocate_traits>(v22);
    v23 = v22 + v45;
    v46 = v22 + v45;
    memset((void *)v45, 0, v22);
    *((_QWORD *)&v45 + 1) = v23;
  }
  v41 = a3;
  v42 = *a4;
  v43 = a1;
  v38 = (__int64 *)(a1 + 14);
  v36 = a1;
  v37 = (const char *)(a1 + 14);
  RetrySessionOperation__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens_::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens_::_2_::_lambda_1____::_2_::_lambda_1___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens_::_2_::_lambda_1____::_2_::_lambda_2___winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::TryRetryRecreateSessionOperation_winrt::Microsoft::Windows::SemanticSearchInternal::IImageSearchTextEmbeddingsSession4__winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorFromTokens_::_2_::_lambda_1____::_2_::_lambda_3___(
    (unsigned int)v40,
    (unsigned int)&v41,
    (unsigned int)&v36,
    v20,
    (__int64)&v38);
  v24 = (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 2;
  LODWORD(v36) = 159;
  v37 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\Mi"
        "crosoft.Windows.SemanticSearch.h";
  v25 = 4;
  if ( (_DWORD)v24 )
    v25 = v45;
  v26 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64))(*(_QWORD *)v40[0] + 48LL))(v40[0], v24, v25);
  if ( v26 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v26, &v36);
  }
  v27 = TraceLogger::Provider();
  if ( *(_DWORD *)v27 > 5u )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)v27,
      (unsigned __int8 *)&byte_180079317);
  v28 = (struct _RTL_CRITICAL_SECTION *)lpMem[0];
  if ( lpMem[0] )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)lpMem[0] + 5);
    LODWORD(v28[1].SpinCount) |= 0x300u;
    if ( v28[6].DebugInfo )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)&v28->LockCount, 2u);
    if ( v28 != (struct _RTL_CRITICAL_SECTION *)-200LL )
      LeaveCriticalSection(v28 + 5);
  }
  v29 = (__int128 *)winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(
                      a1,
                      &v41);
  v38 = (__int64 *)operator new(0x40u);
  v36 = (unsigned int *)v45;
  LODWORD(v37) = (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 2;
  v44 = *v29;
  v30 = winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(
          v38,
          &v36,
          &v44);
  v31 = v30 + 16;
  if ( !v30 )
    v31 = 0;
  *a2 = v31;
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v40);
  std::vector<float>::_Tidy(&v45);
  if ( v28 )
    tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release((volatile signed __int32 *)v28);
  return a2;
}

```

## disassembly

```asm
0x18000b2a0  mov     [rsp-8+arg_10], rbx
0x18000b2a5  push    rbp
0x18000b2a6  push    rsi
0x18000b2a7  push    rdi
0x18000b2a8  push    r12
0x18000b2aa  push    r13
0x18000b2ac  push    r14
0x18000b2ae  push    r15
0x18000b2b0  lea     rbp, [rsp-27h]
0x18000b2b5  sub     rsp, 0C0h
0x18000b2bc  mov     rax, cs:__security_cookie
0x18000b2c3  xor     rax, rsp
0x18000b2c6  mov     [rbp+57h+var_38], rax
0x18000b2ca  mov     r12, r9
0x18000b2cd  mov     r13, r8
0x18000b2d0  mov     r15, rdx
0x18000b2d3  mov     rsi, rcx
0x18000b2d6  mov     [rbp+57h+var_A0], rdx
0x18000b2da  xor     edi, edi
0x18000b2dc  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB> `wil::Feature<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::GetImpl(void)'::`2'::impl
0x18000b2e3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AIFabric_TXTEMB@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AIFabric_TXTEMB>::__private_IsEnabled(void)
0x18000b2e8  test    al, al
0x18000b2ea  jz      loc_18000B64C
0x18000b2f0  mov     [rbp+57h+lpMem], rdi
0x18000b2f4  lea     r14, [rsi+38h]
0x18000b2f8  lea     rdx, [rbp+57h+lpMem]
0x18000b2fc  mov     rcx, r14
0x18000b2ff  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x18000b304  movzx   ebx, al
0x18000b307  cmp     [rbp+57h+lpMem], rdi
0x18000b30b  jz      short loc_18000B316
0x18000b30d  lea     rcx, [rbp+57h+lpMem]
0x18000b311  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000b316  test    bl, bl
0x18000b318  jnz     loc_18000B678
0x18000b31e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents> `wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl(void)'::`2'::impl
0x18000b325  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x18000b32a  test    al, al
0x18000b32c  jz      loc_18000B3CC
0x18000b332  mov     eax, 1
0x18000b337  lock xadd cs:dword_180086680, eax
0x18000b33f  inc     eax
0x18000b341  cmp     eax, 1
0x18000b344  jnz     loc_18000B436
0x18000b34a  mov     rax, [rsi]
0x18000b34d  lea     rdx, [rbp+57h+lpMem]
0x18000b351  mov     rcx, rsi
0x18000b354  mov     rax, [rax+28h]
0x18000b358  call    cs:__guard_dispatch_icall_fptr
0x18000b35e  mov     rbx, [rax]
0x18000b361  test    rbx, rbx
0x18000b364  jz      short loc_18000B36C
0x18000b366  mov     rbx, [rbx+10h]
0x18000b36a  jmp     short loc_18000B373
0x18000b36c  lea     rbx, qword_18006D0D8
0x18000b373  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000b378  mov     rcx, [rax+8]
0x18000b37c  test    rcx, rcx
0x18000b37f  jz      short loc_18000B3A5
0x18000b381  cmp     dword ptr [rcx], 0
0x18000b384  jbe     short loc_18000B3A5
0x18000b386  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x18000b38b  lea     r9, dword_180086680; volatile int *
0x18000b392  lea     r8, aCreatevectorfr_0; "CreateVectorFromTokens"
0x18000b399  mov     rdx, rbx; wchar_t *
0x18000b39c  mov     rcx, rax; this
0x18000b39f  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18000b3a4  nop
0x18000b3a5  mov     rbx, [rbp+57h+lpMem]
0x18000b3a9  test    rbx, rbx
0x18000b3ac  jz      loc_18000B436
0x18000b3b2  mov     eax, 0FFFFFFFFh
0x18000b3b7  lock xadd [rbx+18h], eax
0x18000b3bc  sub     eax, 1
0x18000b3bf  jz      short loc_18000B420
0x18000b3c1  test    eax, eax
0x18000b3c3  jns     short loc_18000B432
0x18000b3c5  call    cs:__imp_abort
0x18000b3cc  mov     rax, [rsi]
0x18000b3cf  lea     rdx, [rbp+57h+lpMem]
0x18000b3d3  mov     rcx, rsi
0x18000b3d6  mov     rax, [rax+28h]
0x18000b3da  call    cs:__guard_dispatch_icall_fptr
0x18000b3e0  mov     rbx, [rax]
0x18000b3e3  test    rbx, rbx
0x18000b3e6  jz      short loc_18000B3EE
0x18000b3e8  mov     rbx, [rbx+10h]
0x18000b3ec  jmp     short loc_18000B3F5
0x18000b3ee  lea     rbx, qword_18006D0D8
0x18000b3f5  lea     rdx, aCreatevectorfr_0; "CreateVectorFromTokens"
0x18000b3fc  mov     rcx, rbx; wchar_t *
0x18000b3ff  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18000b404  mov     rbx, [rbp+57h+lpMem]
0x18000b408  test    rbx, rbx
0x18000b40b  jz      short loc_18000B436
0x18000b40d  mov     eax, 0FFFFFFFFh
0x18000b412  lock xadd [rbx+18h], eax
0x18000b417  sub     eax, 1
0x18000b41a  jnz     loc_18000B62E
0x18000b420  call    WINRT_IMPL_GetProcessHeap
0x18000b425  mov     rcx, rax; hHeap
0x18000b428  mov     r8, rbx; lpMem
0x18000b42b  xor     edx, edx; dwFlags
0x18000b42d  call    WINRT_IMPL_HeapFree
0x18000b432  mov     [rbp+57h+lpMem], rdi
0x18000b436  mov     [rbp+57h+lpMem], rdi
0x18000b43a  lea     rcx, [rbp+57h+lpMem]
0x18000b43e  call    ??$start@V?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@@tip2@@YA?AV?$tip_test@V?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@@0@XZ; tip2::start<tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>>>(void)
0x18000b443  nop
0x18000b444  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000b449  cmp     dword ptr [rax], 5
0x18000b44c  jbe     short loc_18000B45D
0x18000b44e  lea     rdx, dword_18007933C
0x18000b455  mov     rcx, rax
0x18000b458  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b45d  xorps   xmm0, xmm0
0x18000b460  xor     eax, eax
0x18000b462  mov     edi, [rsi+40h]
0x18000b465  movdqu  [rbp+57h+var_50], xmm0
0x18000b46a  mov     [rbp+57h+var_40], rax
0x18000b46e  test    rdi, rdi
0x18000b471  jz      short loc_18000B4A3
0x18000b473  lfence
0x18000b476  lea     rdi, ds:0[rdi*4]
0x18000b47e  mov     rcx, rdi
0x18000b481  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000b486  mov     qword ptr [rbp+57h+var_50], rax
0x18000b48a  lea     rbx, [rdi+rax]
0x18000b48e  mov     [rbp+57h+var_40], rbx
0x18000b492  mov     r8, rdi; Size
0x18000b495  xor     edx, edx; Val
0x18000b497  mov     rcx, rax; void *
0x18000b49a  call    memset
0x18000b49f  mov     qword ptr [rbp+57h+var_50+8], rbx
0x18000b4a3  mov     [rbp+57h+var_80], r13
0x18000b4a7  mov     eax, [r12]
0x18000b4ab  mov     [rbp+57h+var_78], eax
0x18000b4ae  mov     [rbp+57h+var_70], rsi
0x18000b4b2  mov     [rbp+57h+var_A0], r14
0x18000b4b6  mov     qword ptr [rbp+57h+var_B0], rsi
0x18000b4ba  mov     qword ptr [rbp+57h+var_B0+8], r14
0x18000b4be  lea     rax, [rbp+57h+var_A0]
0x18000b4c2  mov     [rsp+0F0h+var_D0], rax
0x18000b4c7  lea     r8, [rbp+57h+var_B0]
0x18000b4cb  lea     rdx, [rbp+57h+var_80]
0x18000b4cf  lea     rcx, [rbp+57h+var_90]
0x18000b4d3  call    RetrySessionOperation__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorFromTokens____2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorFromTokens____2____lambda_1_______2____lambda_1___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorFromTokens____2____lambda_1_______2____lambda_2___winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__TryRetryRecreateSessionOperation_winrt__Microsoft__Windows__SemanticSearchInternal__IImageSearchTextEmbeddingsSession4__winrt__Microsoft__Windows__SemanticSearch__implementation__ImageSearchEmbeddingsCreator__CreateVectorFromTokens____2____lambda_1_______2____lambda_3___
0x18000b4d8  nop
0x18000b4d9  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18000b4dd  sub     rdx, qword ptr [rbp+57h+var_50]
0x18000b4e1  sar     rdx, 2
0x18000b4e5  mov     dword ptr [rbp+57h+var_B0], 9Fh
0x18000b4ec  lea     rax, aCW1SProductApi_25; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b4f3  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18000b4f7  mov     rcx, [rbp+57h+var_90]
0x18000b4fb  mov     rax, [rcx]
0x18000b4fe  mov     r8d, 4
0x18000b504  test    edx, edx
0x18000b506  cmovnz  r8, qword ptr [rbp+57h+var_50]
0x18000b50b  mov     rax, [rax+30h]
0x18000b50f  call    cs:__guard_dispatch_icall_fptr
0x18000b515  test    eax, eax
0x18000b517  js      loc_18000B63D
0x18000b51d  call    ?Provider@TraceLogger@@SAPEBU_tlgProvider_t@@XZ; TraceLogger::Provider(void)
0x18000b522  cmp     dword ptr [rax], 5
0x18000b525  jbe     short loc_18000B536
0x18000b527  lea     rdx, byte_180079317
0x18000b52e  mov     rcx, rax
0x18000b531  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18000b536  mov     rbx, [rbp+57h+lpMem]
0x18000b53a  test    rbx, rbx
0x18000b53d  jz      short loc_18000B57C
0x18000b53f  lea     r14, [rbx+0C8h]
0x18000b546  mov     rcx, r14; lpCriticalSection
0x18000b549  call    cs:__imp_EnterCriticalSection
0x18000b54f  or      dword ptr [rbx+48h], 300h
0x18000b556  cmp     qword ptr [rbx+0F0h], 0
0x18000b55e  jz      short loc_18000B56E
0x18000b560  mov     edx, 2
0x18000b565  lea     rcx, [rbx+8]
0x18000b569  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18000b56e  test    r14, r14
0x18000b571  jz      short loc_18000B57C
0x18000b573  mov     rcx, r14; lpCriticalSection
0x18000b576  call    cs:__imp_LeaveCriticalSection
0x18000b57c  lea     rdx, [rbp+57h+var_80]
0x18000b580  mov     rcx, rsi
0x18000b583  call    ?VectorSpaceId@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@QEAA?AUguid@6@XZ; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::VectorSpaceId(void)
0x18000b588  mov     rdi, rax
0x18000b58b  mov     ecx, 40h ; '@'; Size
0x18000b590  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b595  mov     [rbp+57h+var_A0], rax
0x18000b599  mov     rcx, qword ptr [rbp+57h+var_50]
0x18000b59d  mov     qword ptr [rbp+57h+var_B0], rcx
0x18000b5a1  mov     rdx, qword ptr [rbp+57h+var_50+8]
0x18000b5a5  sub     rdx, rcx
0x18000b5a8  sar     rdx, 2
0x18000b5ac  mov     dword ptr [rbp+57h+var_B0+8], edx
0x18000b5af  movups  xmm0, xmmword ptr [rdi]
0x18000b5b2  movaps  [rbp+57h+var_60], xmm0
0x18000b5b6  movaps  xmm1, [rbp+57h+var_B0]
0x18000b5ba  movdqa  [rbp+57h+var_B0], xmm1
0x18000b5bf  lea     r8, [rbp+57h+var_60]
0x18000b5c3  lea     rdx, [rbp+57h+var_B0]
0x18000b5c7  mov     rcx, rax
0x18000b5ca  call    ??0?$heap_implements@UEmbeddingVector@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@QEAA@U?$array_view@$$CBM@2@Uguid@2@@Z; winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::EmbeddingVector>(winrt::array_view<float const>,winrt::guid)
0x18000b5cf  nop
0x18000b5d0  lea     rcx, [rax+10h]
0x18000b5d4  test    rax, rax
0x18000b5d7  mov     eax, 0
0x18000b5dc  cmovz   rcx, rax
0x18000b5e0  mov     [r15], rcx
0x18000b5e3  lea     rcx, [rbp+57h+var_90]
0x18000b5e7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18000b5ec  nop
0x18000b5ed  lea     rcx, [rbp+57h+var_50]
0x18000b5f1  call    ?_Tidy@?$vector@MV?$allocator@M@std@@@std@@AEAAXXZ; std::vector<float>::_Tidy(void)
0x18000b5f6  nop
0x18000b5f7  test    rbx, rbx
0x18000b5fa  jz      short loc_18000B604
0x18000b5fc  mov     rcx, rbx; pv
0x18000b5ff  call    ?Release@?$merged_data@U_tip_TextEmbeddingsTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_TextEmbeddingsTest,AIFabricTipTest::_tip_TextEmbeddingsTest>::Release(void)
0x18000b604  mov     rax, r15
0x18000b607  mov     rcx, [rbp+57h+var_38]
0x18000b60b  xor     rcx, rsp; StackCookie
0x18000b60e  call    __security_check_cookie
0x18000b613  mov     rbx, [rsp+0F0h+arg_10]
0x18000b61b  add     rsp, 0C0h
0x18000b622  pop     r15
0x18000b624  pop     r14
0x18000b626  pop     r13
0x18000b628  pop     r12
0x18000b62a  pop     rdi
0x18000b62b  pop     rsi
0x18000b62c  pop     rbp
0x18000b62d  retn
0x18000b62e  test    eax, eax
0x18000b630  jns     loc_18000B432
0x18000b636  call    cs:__imp_abort
0x18000b63d  lfence
0x18000b640  lea     rdx, [rbp+57h+var_B0]
0x18000b644  mov     ecx, eax
0x18000b646  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b64c  mov     dword ptr [rbp+57h+var_A0], 0AAh
0x18000b653  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b65a  mov     [rbp+57h+var_98], rax
0x18000b65e  mov     edx, 80004005h; int
0x18000b663  lea     rcx, [rbp+57h+lpMem]; this
0x18000b667  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000b66c  lea     rdx, [rbp+57h+var_A0]
0x18000b670  mov     ecx, [rax]
0x18000b672  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18000b678  mov     dword ptr [rbp+57h+var_A0], 0AFh
0x18000b67f  lea     rax, aCW1SProductApi_8; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18000b686  mov     [rbp+57h+var_98], rax
0x18000b68a  mov     edx, 80000013h; int
0x18000b68f  lea     rcx, [rbp+57h+lpMem]; this
0x18000b693  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18000b698  lea     rdx, [rbp+57h+var_A0]
0x18000b69c  mov     ecx, [rax]
0x18000b69e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
