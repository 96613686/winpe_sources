# winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync$_ResumeCoro$1

- ea: `0x180051d80`
- end: `0x18005211c`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync$_ResumeCoro$1`
- size: `924`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000e9c0`
- `0x180051d60`

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
- `0x180051d80`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180051ebe`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180051f29`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180051ebe`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180051f29`

## string_xrefs

- `0x180051e6e`: `CreateVectorForImageAsync`
- `0x180051ef5`: `CreateVectorForImageAsync`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r12
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
  __int64 *VectorForImageInternal; // r14
  __int64 *v15; // rsi
  __int64 v16; // rax
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v18; // [rsp+58h] [rbp-30h]

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
        if ( _InterlockedIncrement(&dword_1800866F8) == 1 )
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
            TelemetryLogger::InitApiData_(v6, v5, L"CreateVectorForImageAsync", &dword_1800866F8);
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
        TelemetryLogger::LogWclApiUsage(v10, L"CreateVectorForImageAsync");
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
      VectorForImageInternal = winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(
                                 *((_QWORD *)a1 + 28),
                                 (__int64 *)a1 + 24,
                                 (__int64)(a1 + 144),
                                 (__int64)(a1 + 188));
      v15 = (__int64 *)(a1 + 120);
      if ( a1 + 120 != (char *)VectorForImageInternal )
      {
        if ( *v15 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        v16 = *VectorForImageInternal;
        *VectorForImageInternal = 0;
        *v15 = v16;
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
      v18 = *((_QWORD *)a1 + 22);
      if ( v18 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
      *((_QWORD *)a1 + 25) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 25) )
        goto LABEL_42;
      return;
    case 5:
      v18 = *((_QWORD *)a1 + 22);
      if ( v18 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref();
LABEL_42:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_QWORD *)a1 + 18) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 144);
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
0x180051d80  mov     r11, rsp
0x180051d83  mov     [r11+10h], rbx
0x180051d87  mov     [r11+18h], rsi
0x180051d8b  mov     [r11+20h], rdi
0x180051d8f  mov     [r11+8], rcx
0x180051d93  push    r12
0x180051d95  push    r14
0x180051d97  push    r15
0x180051d99  sub     rsp, 70h
0x180051d9d  mov     rax, cs:__security_cookie
0x180051da4  xor     rax, rsp
0x180051da7  mov     [rsp+88h+var_20], rax
0x180051dac  mov     rbx, rcx
0x180051daf  mov     [rsp+88h+var_60], rcx
0x180051db4  lea     r12, [rbx+98h]
0x180051dbb  mov     [rsp+88h+var_50], r12
0x180051dc0  movzx   eax, word ptr [r12]
0x180051dc5  mov     [rsp+88h+var_68], ax
0x180051dca  inc     ax; switch 7 cases
0x180051dcd  cmp     ax, 6
0x180051dd1  ja      def_180051DEC; jumptable 0000000180051DEC default case, case 0
0x180051dd7  movsx   rax, ax
0x180051ddb  lea     rdx, cs:180000000h
0x180051de2  mov     ecx, ds:(jpt_180051DEC - 180000000h)[rdx+rax*4]
0x180051de9  add     rcx, rdx
0x180051dec  jmp     rcx; switch jump
0x180051dee  jmp     loc_1800520A0; jumptable 0000000180051DEC case 3
0x180051df3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@3@XZ@4V453@A; jumptable 0000000180051DEC case 2
0x180051dfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BatchWclApiUsageEvents@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BatchWclApiUsageEvents>::__private_IsEnabled(void)
0x180051dff  test    al, al
0x180051e01  jz      loc_180051EC5
0x180051e07  mov     eax, 1
0x180051e0c  lock xadd cs:dword_1800866F8, eax
0x180051e14  inc     eax
0x180051e16  cmp     eax, 1
0x180051e19  jnz     loc_180051F30
0x180051e1f  mov     rcx, [rbx+88h]
0x180051e26  mov     rax, [rcx]
0x180051e29  lea     rdx, [rbx+0A0h]
0x180051e30  mov     rax, [rax+28h]
0x180051e34  call    cs:__guard_dispatch_icall_fptr
0x180051e3a  mov     rdi, [rax]
0x180051e3d  test    rdi, rdi
0x180051e40  jz      short loc_180051E48
0x180051e42  mov     rdi, [rdi+10h]
0x180051e46  jmp     short loc_180051E4F
0x180051e48  lea     rdi, qword_18006D0D8
0x180051e4f  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180051e54  mov     rcx, [rax+8]
0x180051e58  test    rcx, rcx
0x180051e5b  jz      short loc_180051E81
0x180051e5d  cmp     dword ptr [rcx], 0
0x180051e60  jbe     short loc_180051E81
0x180051e62  call    ?Instance@TelemetryLogger@@KAPEAV1@XZ; TelemetryLogger::Instance(void)
0x180051e67  lea     r9, dword_1800866F8; volatile int *
0x180051e6e  lea     r8, aCreatevectorfo_2; "CreateVectorForImageAsync"
0x180051e75  mov     rdx, rdi; wchar_t *
0x180051e78  mov     rcx, rax; this
0x180051e7b  call    ?InitApiData_@TelemetryLogger@@QEAAXPEB_W0PECJ@Z; TelemetryLogger::InitApiData_(wchar_t const *,wchar_t const *,long volatile *)
0x180051e80  nop
0x180051e81  mov     rdi, [rbx+0A0h]
0x180051e88  cmp     rdi, 0
0x180051e8c  jz      loc_180051F30
0x180051e92  mov     [rsp+88h+var_58], rdi
0x180051e97  mov     ecx, 0FFFFFFFFh
0x180051e9c  lock xadd [rdi+18h], ecx
0x180051ea1  sub     ecx, 1
0x180051ea4  jnz     short loc_180051EBA
0x180051ea6  call    WINRT_IMPL_GetProcessHeap
0x180051eab  mov     rcx, rax; hHeap
0x180051eae  mov     r8, rdi; lpMem
0x180051eb1  xor     edx, edx; dwFlags
0x180051eb3  call    WINRT_IMPL_HeapFree
0x180051eb8  jmp     short loc_180051F30
0x180051eba  test    ecx, ecx
0x180051ebc  jns     short loc_180051F30
0x180051ebe  call    cs:__imp_abort
0x180051ec5  mov     rcx, [rbx+88h]
0x180051ecc  mov     rax, [rcx]
0x180051ecf  lea     rdx, [rbx+0A8h]
0x180051ed6  mov     rax, [rax+28h]
0x180051eda  call    cs:__guard_dispatch_icall_fptr
0x180051ee0  mov     rdi, [rax]
0x180051ee3  test    rdi, rdi
0x180051ee6  jz      short loc_180051EEE
0x180051ee8  mov     rdi, [rdi+10h]
0x180051eec  jmp     short loc_180051EF5
0x180051eee  lea     rdi, qword_18006D0D8
0x180051ef5  lea     rdx, aCreatevectorfo_2; "CreateVectorForImageAsync"
0x180051efc  mov     rcx, rdi; wchar_t *
0x180051eff  call    ?LogWclApiUsage@TelemetryLogger@@SAXPEB_W0@Z; TelemetryLogger::LogWclApiUsage(wchar_t const *,wchar_t const *)
0x180051f04  mov     rdi, [rbx+0A8h]
0x180051f0b  cmp     rdi, 0
0x180051f0f  jz      short loc_180051F30
0x180051f11  mov     [rsp+88h+var_58], rdi
0x180051f16  mov     ecx, 0FFFFFFFFh
0x180051f1b  lock xadd [rdi+18h], ecx
0x180051f20  sub     ecx, 1
0x180051f23  jz      short loc_180051EA6
0x180051f25  test    ecx, ecx
0x180051f27  jns     short loc_180051F30
0x180051f29  call    cs:__imp_abort
0x180051f30  mov     rdx, [rbx+88h]
0x180051f37  mov     [rbx+0E0h], rdx
0x180051f3e  xor     edi, edi
0x180051f40  mov     [rbx+0B0h], rdi
0x180051f47  test    rdx, rdx
0x180051f4a  jz      short loc_180051F76
0x180051f4c  mov     [rbx+0B0h], rdx
0x180051f53  mov     rax, [rdx+8]
0x180051f57  test    rax, rax
0x180051f5a  js      short loc_180051F71
0x180051f5c  nop     dword ptr [rax+00h]
0x180051f60  lea     rcx, [rax+1]
0x180051f64  lock cmpxchg [rdx+8], rcx
0x180051f6a  jz      short loc_180051F76
0x180051f6c  test    rax, rax
0x180051f6f  jns     short loc_180051F60
0x180051f71  lock inc dword ptr [rax+rax+18h]
0x180051f76  mov     byte ptr [rbx+0B8h], 0
0x180051f7d  mov     eax, [rbx+70h]
0x180051f80  cmp     eax, 2
0x180051f83  jnz     short loc_180051FBB
0x180051f85  lea     rdx, [rbx+0D0h]; struct winrt::impl::slim_source_location *
0x180051f8c  mov     dword ptr [rdx], 0F8Ch
0x180051f92  lea     rax, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180051f99  mov     [rbx+0D8h], rax
0x180051fa0  lea     rcx, [rsp+88h+pExceptionObject]; this
0x180051fa5  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180051faa  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180051fb1  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x180051fb6  call    _CxxThrowException
0x180051fbb  mov     eax, 4
0x180051fc0  mov     [r12], ax
0x180051fc5  mov     rdx, rbx
0x180051fc8  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180051fcd  jmp     loc_1800520D5
0x180051fd2  lea     rcx, [rbx+0B0h]; jumptable 0000000180051DEC case 5
0x180051fd9  mov     rax, [rcx]
0x180051fdc  mov     [rsp+88h+var_30], rax
0x180051fe1  test    rax, rax
0x180051fe4  jz      short loc_180051FEC
0x180051fe6  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180051feb  nop
0x180051fec  jmp     loc_1800520A0; jumptable 0000000180051DEC cases -1,1
0x180051ff1  lea     r9, [rbx+0BCh]; jumptable 0000000180051DEC case 4
0x180051ff8  xor     edi, edi
0x180051ffa  mov     [r9], edi
0x180051ffd  lea     r8, [rbx+90h]
0x180052004  lea     rdx, [rbx+0C0h]
0x18005200b  mov     rcx, [rbx+0E0h]
0x180052012  call    ?CreateVectorForImageInternal@ImageSearchEmbeddingsCreator@implementation@SemanticSearch@Windows@Microsoft@winrt@@AEAA?AUEmbeddingVector@3456@AEBUImageBuffer@Imaging@456@AEBW4WorkloadPriority@Workloads@456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::ImageSearchEmbeddingsCreator::CreateVectorForImageInternal(winrt::Microsoft::Windows::Imaging::ImageBuffer const &,winrt::Microsoft::Windows::Workloads::WorkloadPriority const &)
0x180052017  mov     r14, rax
0x18005201a  lea     rsi, [rbx+78h]
0x18005201e  cmp     rsi, rax
0x180052021  jz      short loc_180052039
0x180052023  cmp     [rsi], rdi
0x180052026  jz      short loc_180052030
0x180052028  mov     rcx, rsi
0x18005202b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180052030  mov     rax, [r14]
0x180052033  mov     [r14], rdi
0x180052036  mov     [rsi], rax
0x180052039  mov     rax, [rbx+0C0h]
0x180052040  mov     [rsp+88h+var_58], rax
0x180052045  test    rax, rax
0x180052048  jz      short loc_180052057
0x18005204a  lea     rcx, [rbx+0C0h]
0x180052051  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180052056  nop
0x180052057  lea     rcx, [rbx+0B0h]
0x18005205e  mov     rax, [rcx]
0x180052061  mov     [rsp+88h+var_30], rax
0x180052066  test    rax, rax
0x180052069  jz      short loc_180052071
0x18005206b  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$vector@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@V?$allocator@UEmbedding@SemanticSearch@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::Microsoft::Windows::SemanticSearch::Embedding,std::vector<winrt::Microsoft::Windows::SemanticSearch::Embedding>,winrt::impl::single_threaded_collection_base>>::unconditional_release_ref(void)
0x180052070  nop
0x180052071  jmp     short loc_18005207F
0x180052073  xor     edi, edi
0x180052075  mov     r12, [rsp+88h+var_50]
0x18005207a  mov     rbx, [rsp+88h+var_60]
0x18005207f  lea     rax, [rbx+10h]
0x180052083  lea     rcx, [rbx+0C8h]
0x18005208a  mov     [rcx], rax
0x18005208d  xor     eax, eax
0x18005208f  mov     [r12], ax
0x180052094  mov     [rbx], rdi
0x180052097  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUSemanticTextEmbeddingsCreator@implementation@SemanticSearch@3Microsoft@4@U?$array_view@$$CB_J@4@W4WorkloadPriority@Workloads@384@@std@@U?$IAsyncOperation@UEmbeddingVector@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18005209c  test    al, al
0x18005209e  jnz     short loc_1800520D5
0x1800520a0  lea     rcx, [rbx+10h]; jumptable 0000000180051DEC cases -1,1
0x1800520a4  call    ??1promise_type@?$coroutine_traits@U?$IAsyncOperation@UITextEmbeddingsModel@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@AEAUImageEmbeddingTextModelFactory@implementation@SemanticSearch@3Microsoft@4@@std@@UEAA@XZ; std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type(void)
0x1800520a9  lea     rcx, [rbx+90h]
0x1800520b0  cmp     qword ptr [rcx], 0
0x1800520b4  jz      short loc_1800520BB
0x1800520b6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800520bb  cmp     word ptr [rbx+9Ah], 0
0x1800520c3  jz      short loc_1800520D5
0x1800520c5  mov     edx, 0F0h; unsigned __int64
0x1800520ca  mov     rcx, rbx; void *
0x1800520cd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800520d2  jmp     short loc_1800520D5
0x1800520d4  int     3; Trap to Debugger
0x1800520d5  mov     rcx, [rsp+88h+var_20]
0x1800520da  xor     rcx, rsp; StackCookie
0x1800520dd  call    __security_check_cookie
0x1800520e2  lea     r11, [rsp+88h+var_18]
0x1800520e7  mov     rbx, [r11+28h]
0x1800520eb  mov     rsi, [r11+30h]
0x1800520ef  mov     rdi, [r11+38h]
0x1800520f3  mov     rsp, r11
0x1800520f6  pop     r15
0x1800520f8  pop     r14
0x1800520fa  pop     r12
0x1800520fc  retn
```
