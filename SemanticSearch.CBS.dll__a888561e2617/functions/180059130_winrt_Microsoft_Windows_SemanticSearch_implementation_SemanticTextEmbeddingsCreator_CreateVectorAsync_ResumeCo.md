# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync$_ResumeCoro$1_0

- ea: `0x180059130`
- end: `0x1800594fc`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync$_ResumeCoro$1_0`
- size: `972`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180033c70`
- `0x180058d50`

## callees

- `0x180002bb0`
- `0x180009fa0`
- `0x18000d050`
- `0x180010000`
- `0x180010230`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x180033f70`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x180059130`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059268`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800592d3`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005948f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059268`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800592d3`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005948f`

## string_xrefs

- `0x180059218`: `CreateVectorAsync`
- `0x18005929f`: `CreateVectorAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorAsync__ResumeCoro_1_0(
        char *a1)
{
  _WORD *v2; // r15
  unsigned __int64 v3; // rcx
  __int64 v4; // rax
  const wchar_t *v5; // rdi
  TelemetryLogger *v6; // rax
  volatile signed __int32 *v7; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v9; // rax
  const wchar_t *v10; // rdi
  __int64 v11; // rdx
  signed __int64 v12; // rax
  signed __int64 v13; // rtt
  char *VectorInternal; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // ecx
  HANDLE v19; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h]

  v2 = a1 + 160;
  switch ( *((_WORD *)a1 + 80) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_42;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086A1C) == 1 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(
                 *((_QWORD *)a1 + 17),
                 a1 + 168);
          if ( *(_QWORD *)v4 )
            v5 = *(const wchar_t **)(*(_QWORD *)v4 + 16LL);
          else
            v5 = (const wchar_t *)&qword_18006D0D8;
          v3 = *((_QWORD *)TelemetryLogger::Instance() + 1);
          if ( v3 && *(_DWORD *)v3 )
          {
            v6 = TelemetryLogger::Instance();
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorAsync", &dword_180086A1C);
          }
          v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 21);
          if ( v7 )
          {
            v3 = (unsigned int)_InterlockedDecrement(v7 + 6);
            if ( !(_DWORD)v3 )
            {
LABEL_12:
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v7);
              goto LABEL_22;
            }
            if ( (v3 & 0x80000000) != 0LL )
              abort();
          }
        }
      }
      else
      {
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(*((_QWORD *)a1 + 17), a1 + 176);
        if ( *(_QWORD *)v9 )
          v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
        else
          v10 = (const wchar_t *)&qword_18006D0D8;
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorAsync");
        v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 22);
        if ( v7 )
        {
          v3 = (unsigned int)_InterlockedDecrement(v7 + 6);
          if ( !(_DWORD)v3 )
            goto LABEL_12;
          if ( (v3 & 0x80000000) != 0LL )
            abort();
        }
      }
LABEL_22:
      v11 = *((_QWORD *)a1 + 17);
      *((_QWORD *)a1 + 30) = v11;
      *((_QWORD *)a1 + 23) = 0;
      if ( v11 )
      {
        *((_QWORD *)a1 + 23) = v11;
        v12 = *(_QWORD *)(v11 + 8);
        if ( v12 < 0 )
        {
LABEL_26:
          _InterlockedIncrement((volatile signed __int32 *)(2 * v12 + 24));
        }
        else
        {
          while ( 1 )
          {
            v3 = v12 + 1;
            v13 = v12;
            v12 = _InterlockedCompareExchange64((volatile signed __int64 *)(v11 + 8), v12 + 1, v12);
            if ( v13 == v12 )
              break;
            if ( v12 < 0 )
              goto LABEL_26;
          }
        }
      }
      a1[192] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 54) = 3980;
        *((_QWORD *)a1 + 28) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 216));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *((_DWORD *)a1 + 49) = 0;
      VectorInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(
                                 *((_QWORD *)a1 + 30),
                                 a1 + 200,
                                 a1 + 144);
      v15 = a1 + 120;
      if ( a1 + 120 != VectorInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *(_QWORD *)VectorInternal;
        *(_QWORD *)VectorInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      v21 = *((_QWORD *)a1 + 23);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 26) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 26) )
        goto LABEL_42;
      return;
    case 5:
      v21 = *((_QWORD *)a1 + 23);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_42:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      v17 = (volatile signed __int32 *)*((_QWORD *)a1 + 18);
      if ( v17 )
      {
        v18 = _InterlockedDecrement(v17 + 6);
        if ( v18 )
        {
          if ( v18 < 0 )
            abort();
        }
        else
        {
          v19 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v19, 0, (LPVOID)v17);
        }
        *((_QWORD *)a1 + 18) = 0;
      }
      if ( *((_WORD *)a1 + 81) )
        operator delete(a1);
      return;
    default:
      __debugbreak();
      return;
  }
}

```

## disassembly

```asm
0x180059130  mov     r11, rsp
0x180059133  mov     [r11+10h], rbx
0x180059137  mov     [r11+18h], rsi
0x18005913b  mov     [r11+8], rcx
0x18005913f  push    rdi
0x180059140  push    r14
0x180059142  push    r15
0x180059144  sub     rsp, 70h
0x180059148  mov     rax, cs:__security_cookie
0x18005914f  xor     rax, rsp
0x180059152  mov     [rsp+88h+var_20], rax
0x180059157  mov     rbx, rcx
0x18005915a  mov     [rsp+88h+var_60], rcx
0x18005915f  lea     r15, [rbx+0A0h]
0x180059166  mov     [rsp+88h+var_50], r15
0x18005916b  movzx   eax, word ptr [r15]
0x18005916f  mov     [rsp+88h+var_68], ax
0x180059174  inc     ax; switch 7 cases
0x180059177  cmp     ax, 6
0x18005917b  ja      def_180059196; jumptable 0000000180059196 default case, case 0
0x180059181  movsx   rax, ax
0x180059185  lea     rdx, cs:180000000h
0x18005918c  mov     ecx, ds:(jpt_180059196 - 180000000h)[rdx+rax*4]
0x180059193  add     rcx, rdx
0x180059196  jmp     rcx; switch jump
0x180059198  jmp     loc_180059453; jumptable 0000000180059196 case 3
0x18005919d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180059196 case 2
0x1800591a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x1800591a9  test    al, al
0x1800591ab  jz      loc_18005926F
0x1800591b1  mov     eax, 1
0x1800591b6  lock xadd cs:dword_180086A1C, eax
0x1800591be  inc     eax
0x1800591c0  cmp     eax, 1
0x1800591c3  jnz     loc_1800592DA
0x1800591c9  mov     rcx, [rbx+88h]
0x1800591d0  mov     rax, [rcx]
0x1800591d3  lea     rdx, [rbx+0A8h]
0x1800591da  mov     rax, [rax+28h]
0x1800591de  call    cs:__guard_dispatch_icall_fptr
0x1800591e4  mov     rdi, [rax]
0x1800591e7  test    rdi, rdi
0x1800591ea  jz      short loc_1800591F2
0x1800591ec  mov     rdi, [rdi+10h]
0x1800591f0  jmp     short loc_1800591F9
0x1800591f2  lea     rdi, qword_18006D0D8
0x1800591f9  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800591fe  mov     rcx, [rax+8]
0x180059202  test    rcx, rcx
0x180059205  jz      short loc_18005922B
0x180059207  cmp     dword ptr [rcx], 0
0x18005920a  jbe     short loc_18005922B
0x18005920c  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180059211  lea     r9, dword_180086A1C; volatile int *
0x180059218  lea     r8, aCreatevectoras; "CreateVectorAsync"
0x18005921f  mov     rdx, rdi; wchar_t *
0x180059222  mov     rcx, rax; this
0x180059225  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18005922a  nop
0x18005922b  mov     rdi, [rbx+0A8h]
0x180059232  cmp     rdi, 0
0x180059236  jz      loc_1800592DA
0x18005923c  mov     [rsp+88h+var_58], rdi
0x180059241  mov     ecx, 0FFFFFFFFh
0x180059246  lock xadd [rdi+18h], ecx
0x18005924b  sub     ecx, 1
0x18005924e  jnz     short loc_180059264
0x180059250  call    WINRT_IMPL_GetProcessHeap
0x180059255  mov     rcx, rax; hHeap
0x180059258  mov     r8, rdi; lpMem
0x18005925b  xor     edx, edx; dwFlags
0x18005925d  call    WINRT_IMPL_HeapFree
0x180059262  jmp     short loc_1800592DA
0x180059264  test    ecx, ecx
0x180059266  jns     short loc_1800592DA
0x180059268  call    cs:__imp_abort
0x18005926f  mov     rcx, [rbx+88h]
0x180059276  mov     rax, [rcx]
0x180059279  lea     rdx, [rbx+0B0h]
0x180059280  mov     rax, [rax+28h]
0x180059284  call    cs:__guard_dispatch_icall_fptr
0x18005928a  mov     rdi, [rax]
0x18005928d  test    rdi, rdi
0x180059290  jz      short loc_180059298
0x180059292  mov     rdi, [rdi+10h]
0x180059296  jmp     short loc_18005929F
0x180059298  lea     rdi, qword_18006D0D8
0x18005929f  lea     rdx, aCreatevectoras; "CreateVectorAsync"
0x1800592a6  mov     rcx, rdi; wchar_t *
0x1800592a9  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x1800592ae  mov     rdi, [rbx+0B0h]
0x1800592b5  cmp     rdi, 0
0x1800592b9  jz      short loc_1800592DA
0x1800592bb  mov     [rsp+88h+var_58], rdi
0x1800592c0  mov     ecx, 0FFFFFFFFh
0x1800592c5  lock xadd [rdi+18h], ecx
0x1800592ca  sub     ecx, 1
0x1800592cd  jz      short loc_180059250
0x1800592cf  test    ecx, ecx
0x1800592d1  jns     short loc_1800592DA
0x1800592d3  call    cs:__imp_abort
0x1800592da  mov     rdx, [rbx+88h]
0x1800592e1  mov     [rbx+0F0h], rdx
0x1800592e8  mov     qword ptr [rbx+0B8h], 0
0x1800592f3  test    rdx, rdx
0x1800592f6  jz      short loc_180059326
0x1800592f8  mov     [rbx+0B8h], rdx
0x1800592ff  mov     rax, [rdx+8]
0x180059303  test    rax, rax
0x180059306  js      short loc_180059321
0x180059308  nop     dword ptr [rax+rax+00000000h]
0x180059310  lea     rcx, [rax+1]
0x180059314  lock cmpxchg [rdx+8], rcx
0x18005931a  jz      short loc_180059326
0x18005931c  test    rax, rax
0x18005931f  jns     short loc_180059310
0x180059321  lock inc dword ptr [rax+rax+18h]
0x180059326  mov     byte ptr [rbx+0C0h], 0
0x18005932d  mov     eax, [rbx+70h]
0x180059330  cmp     eax, 2
0x180059333  jnz     short loc_18005936B
0x180059335  lea     rdx, [rbx+0D8h]; struct winrt::impl::slim_source_location *
0x18005933c  mov     dword ptr [rdx], 0F8Ch
0x180059342  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180059349  mov     [rbx+0E0h], rax
0x180059350  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180059355  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005935a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180059361  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180059366  call    _CxxThrowException
0x18005936b  mov     eax, 4
0x180059370  mov     [r15], ax
0x180059374  mov     rdx, rbx
0x180059377  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18005937c  jmp     loc_1800594BB
0x180059381  lea     rcx, [rbx+0B8h]; jumptable 0000000180059196 case 5
0x180059388  mov     rax, [rcx]
0x18005938b  mov     [rsp+88h+var_30], rax
0x180059390  test    rax, rax
0x180059393  jz      short loc_18005939B
0x180059395  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18005939a  nop
0x18005939b  jmp     loc_180059453; jumptable 0000000180059196 cases -1,1
0x1800593a0  lea     r9, [rbx+0C4h]; jumptable 0000000180059196 case 4
0x1800593a7  mov     dword ptr [r9], 0
0x1800593ae  lea     r8, [rbx+90h]
0x1800593b5  lea     rdx, [rbx+0C8h]
0x1800593bc  mov     rcx, [rbx+0F0h]
0x1800593c3  call    ?CreateVectorInternal@SemanticTextEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator::CreateVectorInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x1800593c8  mov     rsi, rax
0x1800593cb  lea     rdi, [rbx+78h]
0x1800593cf  cmp     rdi, rax
0x1800593d2  jz      short loc_1800593EF
0x1800593d4  cmp     qword ptr [rdi], 0
0x1800593d8  jz      short loc_1800593E2
0x1800593da  mov     rcx, rdi
0x1800593dd  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800593e2  mov     rax, [rsi]
0x1800593e5  mov     qword ptr [rsi], 0
0x1800593ec  mov     [rdi], rax
0x1800593ef  mov     rax, [rbx+0C8h]
0x1800593f6  mov     [rsp+88h+var_58], rax
0x1800593fb  test    rax, rax
0x1800593fe  jz      short loc_18005940D
0x180059400  lea     rcx, [rbx+0C8h]
0x180059407  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005940c  nop
0x18005940d  lea     rcx, [rbx+0B8h]
0x180059414  mov     rax, [rcx]
0x180059417  mov     [rsp+88h+var_30], rax
0x18005941c  test    rax, rax
0x18005941f  jz      short loc_180059427
0x180059421  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180059426  nop
0x180059427  jmp     short loc_180059433
0x180059429  mov     r15, [rsp+88h+var_50]
0x18005942e  mov     rbx, [rsp+88h+var_60]
0x180059433  lea     rax, [rbx+10h]
0x180059437  lea     rcx, [rbx+0D0h]
0x18005943e  mov     [rcx], rax
0x180059441  xor     eax, eax
0x180059443  mov     [r15], ax
0x180059447  mov     [rbx], rax
0x18005944a  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005944f  test    al, al
0x180059451  jnz     short loc_1800594BB
0x180059453  lea     rcx, [rbx+10h]; jumptable 0000000180059196 cases -1,1
0x180059457  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005945c  mov     rdi, [rbx+90h]
0x180059463  test    rdi, rdi
0x180059466  jz      short loc_1800594A1
0x180059468  mov     ecx, 0FFFFFFFFh
0x18005946d  lock xadd [rdi+18h], ecx
0x180059472  sub     ecx, 1
0x180059475  jnz     short loc_18005948B
0x180059477  call    WINRT_IMPL_GetProcessHeap
0x18005947c  mov     rcx, rax; hHeap
0x18005947f  mov     r8, rdi; lpMem
0x180059482  xor     edx, edx; dwFlags
0x180059484  call    WINRT_IMPL_HeapFree
0x180059489  jmp     short loc_180059496
0x18005948b  test    ecx, ecx
0x18005948d  jns     short loc_180059496
0x18005948f  call    cs:__imp_abort
0x180059496  mov     qword ptr [rbx+90h], 0
0x1800594a1  cmp     word ptr [rbx+0A2h], 0
0x1800594a9  jz      short loc_1800594BB
0x1800594ab  mov     edx, 100h; unsigned __int64
0x1800594b0  mov     rcx, rbx; void *
0x1800594b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800594b8  jmp     short loc_1800594BB
0x1800594ba  int     3; Trap to Debugger
0x1800594bb  mov     rcx, [rsp+88h+var_20]
0x1800594c0  xor     rcx, rsp; StackCookie
0x1800594c3  call    __security_check_cookie
0x1800594c8  lea     r11, [rsp+88h+var_18]
0x1800594cd  mov     rbx, [r11+28h]
0x1800594d1  mov     rsi, [r11+30h]
0x1800594d5  mov     rsp, r11
0x1800594d8  pop     r15
0x1800594da  pop     r14
0x1800594dc  pop     rdi
0x1800594dd  retn
```
