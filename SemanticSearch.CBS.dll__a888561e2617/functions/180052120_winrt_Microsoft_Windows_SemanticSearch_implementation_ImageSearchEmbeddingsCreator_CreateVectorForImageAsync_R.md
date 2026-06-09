# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync$_ResumeCoro$1_0

- ea: `0x180052120`
- end: `0x1800524b8`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync$_ResumeCoro$1_0`
- size: `920`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e640`
- `0x180051d70`

## callees

- `0x180002bb0`
- `0x180009fa0`
- `0x18000a710`
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
- `0x180052120`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052258`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800522c3`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180052258`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800522c3`

## string_xrefs

- `0x180052208`: `CreateVectorForImageAsync`
- `0x18005228f`: `CreateVectorForImageAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync__ResumeCoro_1_0(
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
  __int64 *VectorForImageInternal; // rsi
  __int64 *v15; // rdi
  __int64 v16; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v18; // [rsp+58h] [rbp-30h]

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
        if ( _InterlockedIncrement(&dword_180086690) == 1 )
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
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorForImageAsync", &dword_180086690);
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
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorForImageAsync");
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
      VectorForImageInternal = winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(
                                 *((_QWORD *)a1 + 30),
                                 (__int64 *)a1 + 25,
                                 (__int64)(a1 + 144),
                                 (__int64)(a1 + 152));
      v15 = (__int64 *)(a1 + 120);
      if ( a1 + 120 != (char *)VectorForImageInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *VectorForImageInternal;
        *VectorForImageInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 200);
      v18 = *((_QWORD *)a1 + 23);
      if ( v18 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 26) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 26) )
        goto LABEL_42;
      return;
    case 5:
      v18 = *((_QWORD *)a1 + 23);
      if ( v18 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_42:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 144);
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
0x180052120  mov     r11, rsp
0x180052123  mov     [r11+10h], rbx
0x180052127  mov     [r11+18h], rsi
0x18005212b  mov     [r11+8], rcx
0x18005212f  push    rdi
0x180052130  push    r14
0x180052132  push    r15
0x180052134  sub     rsp, 70h
0x180052138  mov     rax, cs:__security_cookie
0x18005213f  xor     rax, rsp
0x180052142  mov     [rsp+88h+var_20], rax
0x180052147  mov     rbx, rcx
0x18005214a  mov     [rsp+88h+var_60], rcx
0x18005214f  lea     r15, [rbx+0A0h]
0x180052156  mov     [rsp+88h+var_50], r15
0x18005215b  movzx   eax, word ptr [r15]
0x18005215f  mov     [rsp+88h+var_68], ax
0x180052164  inc     ax; switch 7 cases
0x180052167  cmp     ax, 6
0x18005216b  ja      def_180052186; jumptable 0000000180052186 default case, case 0
0x180052171  movsx   rax, ax
0x180052175  lea     rdx, cs:180000000h
0x18005217c  mov     ecx, ds:(jpt_180052186 - 180000000h)[rdx+rax*4]
0x180052183  add     rcx, rdx
0x180052186  jmp     rcx; switch jump
0x180052188  jmp     loc_180052440; jumptable 0000000180052186 case 3
0x18005218d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180052186 case 2
0x180052194  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180052199  test    al, al
0x18005219b  jz      loc_18005225F
0x1800521a1  mov     eax, 1
0x1800521a6  lock xadd cs:dword_180086690, eax
0x1800521ae  inc     eax
0x1800521b0  cmp     eax, 1
0x1800521b3  jnz     loc_1800522CA
0x1800521b9  mov     rcx, [rbx+88h]
0x1800521c0  mov     rax, [rcx]
0x1800521c3  lea     rdx, [rbx+0A8h]
0x1800521ca  mov     rax, [rax+28h]
0x1800521ce  call    cs:__guard_dispatch_icall_fptr
0x1800521d4  mov     rdi, [rax]
0x1800521d7  test    rdi, rdi
0x1800521da  jz      short loc_1800521E2
0x1800521dc  mov     rdi, [rdi+10h]
0x1800521e0  jmp     short loc_1800521E9
0x1800521e2  lea     rdi, qword_18006D0D8
0x1800521e9  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x1800521ee  mov     rcx, [rax+8]
0x1800521f2  test    rcx, rcx
0x1800521f5  jz      short loc_18005221B
0x1800521f7  cmp     dword ptr [rcx], 0
0x1800521fa  jbe     short loc_18005221B
0x1800521fc  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180052201  lea     r9, dword_180086690; volatile int *
0x180052208  lea     r8, aCreatevectorfo_2; "CreateVectorForImageAsync"
0x18005220f  mov     rdx, rdi; wchar_t *
0x180052212  mov     rcx, rax; this
0x180052215  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x18005221a  nop
0x18005221b  mov     rdi, [rbx+0A8h]
0x180052222  cmp     rdi, 0
0x180052226  jz      loc_1800522CA
0x18005222c  mov     [rsp+88h+var_58], rdi
0x180052231  mov     ecx, 0FFFFFFFFh
0x180052236  lock xadd [rdi+18h], ecx
0x18005223b  sub     ecx, 1
0x18005223e  jnz     short loc_180052254
0x180052240  call    WINRT_IMPL_GetProcessHeap
0x180052245  mov     rcx, rax; hHeap
0x180052248  mov     r8, rdi; lpMem
0x18005224b  xor     edx, edx; dwFlags
0x18005224d  call    WINRT_IMPL_HeapFree
0x180052252  jmp     short loc_1800522CA
0x180052254  test    ecx, ecx
0x180052256  jns     short loc_1800522CA
0x180052258  call    cs:__imp_abort
0x18005225f  mov     rcx, [rbx+88h]
0x180052266  mov     rax, [rcx]
0x180052269  lea     rdx, [rbx+0B0h]
0x180052270  mov     rax, [rax+28h]
0x180052274  call    cs:__guard_dispatch_icall_fptr
0x18005227a  mov     rdi, [rax]
0x18005227d  test    rdi, rdi
0x180052280  jz      short loc_180052288
0x180052282  mov     rdi, [rdi+10h]
0x180052286  jmp     short loc_18005228F
0x180052288  lea     rdi, qword_18006D0D8
0x18005228f  lea     rdx, aCreatevectorfo_2; "CreateVectorForImageAsync"
0x180052296  mov     rcx, rdi; wchar_t *
0x180052299  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x18005229e  mov     rdi, [rbx+0B0h]
0x1800522a5  cmp     rdi, 0
0x1800522a9  jz      short loc_1800522CA
0x1800522ab  mov     [rsp+88h+var_58], rdi
0x1800522b0  mov     ecx, 0FFFFFFFFh
0x1800522b5  lock xadd [rdi+18h], ecx
0x1800522ba  sub     ecx, 1
0x1800522bd  jz      short loc_180052240
0x1800522bf  test    ecx, ecx
0x1800522c1  jns     short loc_1800522CA
0x1800522c3  call    cs:__imp_abort
0x1800522ca  mov     rdx, [rbx+88h]
0x1800522d1  mov     [rbx+0F0h], rdx
0x1800522d8  mov     qword ptr [rbx+0B8h], 0
0x1800522e3  test    rdx, rdx
0x1800522e6  jz      short loc_180052316
0x1800522e8  mov     [rbx+0B8h], rdx
0x1800522ef  mov     rax, [rdx+8]
0x1800522f3  test    rax, rax
0x1800522f6  js      short loc_180052311
0x1800522f8  nop     dword ptr [rax+rax+00000000h]
0x180052300  lea     rcx, [rax+1]
0x180052304  lock cmpxchg [rdx+8], rcx
0x18005230a  jz      short loc_180052316
0x18005230c  test    rax, rax
0x18005230f  jns     short loc_180052300
0x180052311  lock inc dword ptr [rax+rax+18h]
0x180052316  mov     byte ptr [rbx+0C0h], 0
0x18005231d  mov     eax, [rbx+70h]
0x180052320  cmp     eax, 2
0x180052323  jnz     short loc_18005235B
0x180052325  lea     rdx, [rbx+0D8h]; struct winrt::impl::slim_source_location *
0x18005232c  mov     dword ptr [rdx], 0F8Ch
0x180052332  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180052339  mov     [rbx+0E0h], rax
0x180052340  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180052345  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005234a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180052351  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180052356  call    _CxxThrowException
0x18005235b  mov     eax, 4
0x180052360  mov     [r15], ax
0x180052364  mov     rdx, rbx
0x180052367  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18005236c  jmp     loc_180052475
0x180052371  lea     rcx, [rbx+0B8h]; jumptable 0000000180052186 case 5
0x180052378  mov     rax, [rcx]
0x18005237b  mov     [rsp+88h+var_30], rax
0x180052380  test    rax, rax
0x180052383  jz      short loc_18005238B
0x180052385  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18005238a  nop
0x18005238b  jmp     loc_180052440; jumptable 0000000180052186 cases -1,1
0x180052390  lea     r9, [rbx+98h]; jumptable 0000000180052186 case 4
0x180052397  lea     r8, [rbx+90h]
0x18005239e  lea     rdx, [rbx+0C8h]
0x1800523a5  mov     rcx, [rbx+0F0h]
0x1800523ac  call    ?CreateVectorForImageInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x1800523b1  mov     rsi, rax
0x1800523b4  lea     rdi, [rbx+78h]
0x1800523b8  cmp     rdi, rax
0x1800523bb  jz      short loc_1800523D8
0x1800523bd  cmp     qword ptr [rdi], 0
0x1800523c1  jz      short loc_1800523CB
0x1800523c3  mov     rcx, rdi
0x1800523c6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800523cb  mov     rax, [rsi]
0x1800523ce  mov     qword ptr [rsi], 0
0x1800523d5  mov     [rdi], rax
0x1800523d8  mov     rax, [rbx+0C8h]
0x1800523df  mov     [rsp+88h+var_58], rax
0x1800523e4  test    rax, rax
0x1800523e7  jz      short loc_1800523F6
0x1800523e9  lea     rcx, [rbx+0C8h]
0x1800523f0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800523f5  nop
0x1800523f6  lea     rcx, [rbx+0B8h]
0x1800523fd  mov     rax, [rcx]
0x180052400  mov     [rsp+88h+var_30], rax
0x180052405  test    rax, rax
0x180052408  jz      short loc_180052410
0x18005240a  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x18005240f  nop
0x180052410  jmp     short loc_18005241C
0x180052412  mov     r15, [rsp+88h+var_50]
0x180052417  mov     rbx, [rsp+88h+var_60]
0x18005241c  lea     rax, [rbx+10h]
0x180052420  lea     rcx, [rbx+0D0h]
0x180052427  mov     [rcx], rax
0x18005242a  xor     eax, eax
0x18005242c  mov     [r15], ax
0x180052430  mov     [rbx], rax
0x180052433  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x180052438  test    al, al
0x18005243a  jnz     short loc_180052475
0x18005243c  nop     dword ptr [rax+00h]
0x180052440  lea     rcx, [rbx+10h]; jumptable 0000000180052186 cases -1,1
0x180052444  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x180052449  lea     rcx, [rbx+90h]
0x180052450  cmp     qword ptr [rcx], 0
0x180052454  jz      short loc_18005245B
0x180052456  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005245b  cmp     word ptr [rbx+0A2h], 0
0x180052463  jz      short loc_180052475
0x180052465  mov     edx, 100h; unsigned __int64
0x18005246a  mov     rcx, rbx; void *
0x18005246d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180052472  jmp     short loc_180052475
0x180052474  int     3; Trap to Debugger
0x180052475  mov     rcx, [rsp+88h+var_20]
0x18005247a  xor     rcx, rsp; StackCookie
0x18005247d  call    __security_check_cookie
0x180052482  lea     r11, [rsp+88h+var_18]
0x180052487  mov     rbx, [r11+28h]
0x18005248b  mov     rsi, [r11+30h]
0x18005248f  mov     rsp, r11
0x180052492  pop     r15
0x180052494  pop     r14
0x180052496  pop     rdi
0x180052497  retn
```
