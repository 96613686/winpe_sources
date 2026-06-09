# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync$_ResumeCoro$1

- ea: `0x1800524e0`
- end: `0x1800528ac`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync$_ResumeCoro$1`
- size: `972`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a240`
- `0x1800524c0`

## callees

- `0x180002bb0`
- `0x180009fa0`
- `0x18000afa0`
- `0x18000d050`
- `0x180010000`
- `0x180010230`
- `0x180014100`
- `0x180014540`
- `0x180014840`
- `0x180015090`
- `0x1800151a0`
- `0x18004c070`
- `0x18004c090`
- `0x18004ecf0`
- `0x180051379`
- `0x18005137f`
- `0x1800524e0`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052618`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052683`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005283f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052618`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052683`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005283f`

## string_xrefs

- `0x1800525c8`: `CreateVectorForTextAsync`
- `0x18005264f`: `CreateVectorForTextAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextAsync__ResumeCoro_1(
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
  char *VectorForTextInternal; // rsi
  _QWORD *v15; // rdi
  __int64 v16; // rax
  volatile signed __int32 *v17; // rdi
  int v18; // ecx
  HANDLE v19; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v21; // [rsp+58h] [rbp-30h]

  v2 = a1 + 152;
  switch ( *((_WORD *)a1 + 76) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_42;
    case 2:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::GetImpl'::`2'::impl) )
      {
        if ( _InterlockedIncrement(&dword_180086698) == 1 )
        {
          v4 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(
                 *((_QWORD *)a1 + 17),
                 a1 + 160);
          if ( *(_QWORD *)v4 )
            v5 = *(const wchar_t **)(*(_QWORD *)v4 + 16LL);
          else
            v5 = (const wchar_t *)&qword_18006D0D8;
          v3 = *((_QWORD *)TelemetryLogger::Instance() + 1);
          if ( v3 && *(_DWORD *)v3 )
          {
            v6 = TelemetryLogger::Instance();
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorForTextAsync", &dword_180086698);
          }
          v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 20);
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
        v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)a1 + 17) + 40LL))(*((_QWORD *)a1 + 17), a1 + 168);
        if ( *(_QWORD *)v9 )
          v10 = *(const wchar_t **)(*(_QWORD *)v9 + 16LL);
        else
          v10 = (const wchar_t *)&qword_18006D0D8;
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorForTextAsync");
        v7 = (volatile signed __int32 *)*((_QWORD *)a1 + 21);
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
      *((_QWORD *)a1 + 28) = v11;
      *((_QWORD *)a1 + 22) = 0;
      if ( v11 )
      {
        *((_QWORD *)a1 + 22) = v11;
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
      a1[184] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 52) = 3980;
        *((_QWORD *)a1 + 27) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 208));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      *((_DWORD *)a1 + 47) = 0;
      VectorForTextInternal = (char *)winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(
                                        *((_QWORD *)a1 + 28),
                                        a1 + 192,
                                        a1 + 144);
      v15 = a1 + 120;
      if ( a1 + 120 != VectorForTextInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *(_QWORD *)VectorForTextInternal;
        *(_QWORD *)VectorForTextInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
      v21 = *((_QWORD *)a1 + 22);
      if ( v21 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 25) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 25) )
        goto LABEL_42;
      return;
    case 5:
      v21 = *((_QWORD *)a1 + 22);
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
      if ( *((_WORD *)a1 + 77) )
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
0x1800524e0  mov     r11, rsp
0x1800524e3  mov     [r11+10h], rbx
0x1800524e7  mov     [r11+18h], rsi
0x1800524eb  mov     [r11+8], rcx
0x1800524ef  push    rdi
0x1800524f0  push    r14
0x1800524f2  push    r15
0x1800524f4  sub     rsp, 70h
0x1800524f8  mov     rax, cs:__security_cookie
0x1800524ff  xor     rax, rsp
0x180052502  mov     [rsp+88h+var_20], rax
0x180052507  mov     rbx, rcx
0x18005250a  mov     [rsp+88h+var_60], rcx
0x18005250f  lea     r15, [rbx+98h]
0x180052516  mov     [rsp+88h+var_50], r15
0x18005251b  movzx   eax, word ptr [r15]
0x18005251f  mov     [rsp+88h+var_68], ax
0x180052524  inc     ax; switch 7 cases
0x180052527  cmp     ax, 6
0x18005252b  ja      def_180052546; jumptable 0000000180052546 default case, case 0
0x180052531  movsx   rax, ax
0x180052535  lea     rdx, cs:180000000h
0x18005253c  mov     ecx, ds:(jpt_180052546 - 180000000h)[rdx+rax*4]
0x180052543  add     rcx, rdx
0x180052546  jmp     rcx; switch jump
0x180052548  jmp     loc_180052803; jumptable 0000000180052546 case 3
0x18005254d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180052546 case 2
0x180052554  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180052559  test    al, al
0x18005255b  jz      loc_18005261F
0x180052561  mov     eax, 1
0x180052566  lock xadd cs:dword_180086698, eax
0x18005256e  inc     eax
0x180052570  cmp     eax, 1
0x180052573  jnz     loc_18005268A
0x180052579  mov     rcx, [rbx+88h]
0x180052580  mov     rax, [rcx]
0x180052583  lea     rdx, [rbx+0A0h]
0x18005258a  mov     rax, [rax+28h]
0x18005258e  call    cs:__guard_dispatch_icall_fptr
0x180052594  mov     rdi, [rax]
0x180052597  test    rdi, rdi
0x18005259a  jz      short loc_1800525A2
0x18005259c  mov     rdi, [rdi+10h]
0x1800525a0  jmp     short loc_1800525A9
0x1800525a2  lea     rdi, qword_18006D0D8
0x1800525a9  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800525ae  mov     rcx, [rax+8]
0x1800525b2  test    rcx, rcx
0x1800525b5  jz      short loc_1800525DB
0x1800525b7  cmp     dword ptr [rcx], 0
0x1800525ba  jbe     short loc_1800525DB
0x1800525bc  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800525c1  lea     r9, dword_180086698; volatile int *
0x1800525c8  lea     r8, aCreatevectorfo_1; "CreateVectorForTextAsync"
0x1800525cf  mov     rdx, rdi; wchar_t *
0x1800525d2  mov     rcx, rax; this
0x1800525d5  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x1800525da  nop
0x1800525db  mov     rdi, [rbx+0A0h]
0x1800525e2  cmp     rdi, 0
0x1800525e6  jz      loc_18005268A
0x1800525ec  mov     [rsp+88h+var_58], rdi
0x1800525f1  mov     ecx, 0FFFFFFFFh
0x1800525f6  lock xadd [rdi+18h], ecx
0x1800525fb  sub     ecx, 1
0x1800525fe  jnz     short loc_180052614
0x180052600  call    WINRT_IMPL_GetProcessHeap
0x180052605  mov     rcx, rax; hHeap
0x180052608  mov     r8, rdi; lpMem
0x18005260b  xor     edx, edx; dwFlags
0x18005260d  call    WINRT_IMPL_HeapFree
0x180052612  jmp     short loc_18005268A
0x180052614  test    ecx, ecx
0x180052616  jns     short loc_18005268A
0x180052618  call    cs:__imp_abort
0x18005261f  mov     rcx, [rbx+88h]
0x180052626  mov     rax, [rcx]
0x180052629  lea     rdx, [rbx+0A8h]
0x180052630  mov     rax, [rax+28h]
0x180052634  call    cs:__guard_dispatch_icall_fptr
0x18005263a  mov     rdi, [rax]
0x18005263d  test    rdi, rdi
0x180052640  jz      short loc_180052648
0x180052642  mov     rdi, [rdi+10h]
0x180052646  jmp     short loc_18005264F
0x180052648  lea     rdi, qword_18006D0D8
0x18005264f  lea     rdx, aCreatevectorfo_1; "CreateVectorForTextAsync"
0x180052656  mov     rcx, rdi; wchar_t *
0x180052659  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18005265e  mov     rdi, [rbx+0A8h]
0x180052665  cmp     rdi, 0
0x180052669  jz      short loc_18005268A
0x18005266b  mov     [rsp+88h+var_58], rdi
0x180052670  mov     ecx, 0FFFFFFFFh
0x180052675  lock xadd [rdi+18h], ecx
0x18005267a  sub     ecx, 1
0x18005267d  jz      short loc_180052600
0x18005267f  test    ecx, ecx
0x180052681  jns     short loc_18005268A
0x180052683  call    cs:__imp_abort
0x18005268a  mov     rdx, [rbx+88h]
0x180052691  mov     [rbx+0E0h], rdx
0x180052698  mov     qword ptr [rbx+0B0h], 0
0x1800526a3  test    rdx, rdx
0x1800526a6  jz      short loc_1800526D6
0x1800526a8  mov     [rbx+0B0h], rdx
0x1800526af  mov     rax, [rdx+8]
0x1800526b3  test    rax, rax
0x1800526b6  js      short loc_1800526D1
0x1800526b8  nop     dword ptr [rax+rax+00000000h]
0x1800526c0  lea     rcx, [rax+1]
0x1800526c4  lock cmpxchg [rdx+8], rcx
0x1800526ca  jz      short loc_1800526D6
0x1800526cc  test    rax, rax
0x1800526cf  jns     short loc_1800526C0
0x1800526d1  lock inc dword ptr [rax+rax+18h]
0x1800526d6  mov     byte ptr [rbx+0B8h], 0
0x1800526dd  mov     eax, [rbx+70h]
0x1800526e0  cmp     eax, 2
0x1800526e3  jnz     short loc_18005271B
0x1800526e5  lea     rdx, [rbx+0D0h]; struct winrt::impl::slim_source_location *
0x1800526ec  mov     dword ptr [rdx], 0F8Ch
0x1800526f2  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800526f9  mov     [rbx+0D8h], rax
0x180052700  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180052705  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005270a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180052711  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180052716  call    _CxxThrowException
0x18005271b  mov     eax, 4
0x180052720  mov     [r15], ax
0x180052724  mov     rdx, rbx
0x180052727  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18005272c  jmp     loc_18005286B
0x180052731  lea     rcx, [rbx+0B0h]; jumptable 0000000180052546 case 5
0x180052738  mov     rax, [rcx]
0x18005273b  mov     [rsp+88h+var_30], rax
0x180052740  test    rax, rax
0x180052743  jz      short loc_18005274B
0x180052745  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18005274a  nop
0x18005274b  jmp     loc_180052803; jumptable 0000000180052546 cases -1,1
0x180052750  lea     r9, [rbx+0BCh]; jumptable 0000000180052546 case 4
0x180052757  mov     dword ptr [r9], 0
0x18005275e  lea     r8, [rbx+90h]
0x180052765  lea     rdx, [rbx+0C0h]
0x18005276c  mov     rcx, [rbx+0E0h]
0x180052773  call    ?CreateVectorForTextInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUhstring@6@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForTextInternal(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180052778  mov     rsi, rax
0x18005277b  lea     rdi, [rbx+78h]
0x18005277f  cmp     rdi, rax
0x180052782  jz      short loc_18005279F
0x180052784  cmp     qword ptr [rdi], 0
0x180052788  jz      short loc_180052792
0x18005278a  mov     rcx, rdi
0x18005278d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180052792  mov     rax, [rsi]
0x180052795  mov     qword ptr [rsi], 0
0x18005279c  mov     [rdi], rax
0x18005279f  mov     rax, [rbx+0C0h]
0x1800527a6  mov     [rsp+88h+var_58], rax
0x1800527ab  test    rax, rax
0x1800527ae  jz      short loc_1800527BD
0x1800527b0  lea     rcx, [rbx+0C0h]
0x1800527b7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800527bc  nop
0x1800527bd  lea     rcx, [rbx+0B0h]
0x1800527c4  mov     rax, [rcx]
0x1800527c7  mov     [rsp+88h+var_30], rax
0x1800527cc  test    rax, rax
0x1800527cf  jz      short loc_1800527D7
0x1800527d1  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x1800527d6  nop
0x1800527d7  jmp     short loc_1800527E3
0x1800527d9  mov     r15, [rsp+88h+var_50]
0x1800527de  mov     rbx, [rsp+88h+var_60]
0x1800527e3  lea     rax, [rbx+10h]
0x1800527e7  lea     rcx, [rbx+0C8h]
0x1800527ee  mov     [rcx], rax
0x1800527f1  xor     eax, eax
0x1800527f3  mov     [r15], ax
0x1800527f7  mov     [rbx], rax
0x1800527fa  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x1800527ff  test    al, al
0x180052801  jnz     short loc_18005286B
0x180052803  lea     rcx, [rbx+10h]; jumptable 0000000180052546 cases -1,1
0x180052807  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x18005280c  mov     rdi, [rbx+90h]
0x180052813  test    rdi, rdi
0x180052816  jz      short loc_180052851
0x180052818  mov     ecx, 0FFFFFFFFh
0x18005281d  lock xadd [rdi+18h], ecx
0x180052822  sub     ecx, 1
0x180052825  jnz     short loc_18005283B
0x180052827  call    WINRT_IMPL_GetProcessHeap
0x18005282c  mov     rcx, rax; hHeap
0x18005282f  mov     r8, rdi; lpMem
0x180052832  xor     edx, edx; dwFlags
0x180052834  call    WINRT_IMPL_HeapFree
0x180052839  jmp     short loc_180052846
0x18005283b  test    ecx, ecx
0x18005283d  jns     short loc_180052846
0x18005283f  call    cs:__imp_abort
0x180052846  mov     qword ptr [rbx+90h], 0
0x180052851  cmp     word ptr [rbx+9Ah], 0
0x180052859  jz      short loc_18005286B
0x18005285b  mov     edx, 0F0h; unsigned __int64
0x180052860  mov     rcx, rbx; void *
0x180052863  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180052868  jmp     short loc_18005286B
0x18005286a  int     3; Trap to Debugger
0x18005286b  mov     rcx, [rsp+88h+var_20]
0x180052870  xor     rcx, rsp; StackCookie
0x180052873  call    __security_check_cookie
0x180052878  lea     r11, [rsp+88h+var_18]
0x18005287d  mov     rbx, [r11+28h]
0x180052881  mov     rsi, [r11+30h]
0x180052885  mov     rsp, r11
0x180052888  pop     r15
0x18005288a  pop     r14
0x18005288c  pop     rdi
0x18005288d  retn
```
