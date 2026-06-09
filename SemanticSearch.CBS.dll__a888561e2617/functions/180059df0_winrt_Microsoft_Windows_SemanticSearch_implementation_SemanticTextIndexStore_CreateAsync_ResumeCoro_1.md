# winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::CreateAsync$_ResumeCoro$1

- ea: `0x180059df0`
- end: `0x18005a3f8`
- name: `winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::CreateAsync$_ResumeCoro$1`
- size: `1544`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `21`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180038290`
- `0x180059de0`

## callees

- `0x180002bb0`
- `0x180009580`
- `0x180009fa0`
- `0x18000d050`
- `0x180014100`
- `0x180014840`
- `0x180037ea0`
- `0x180038e00`
- `0x180039d80`
- `0x18003dc90`
- `0x1800454f0`
- `0x18004c070`
- `0x18004c090`
- `0x18004c46c`
- `0x18004c4d8`
- `0x18004c8ac`
- `0x18004c8cc`
- `0x18004df50`
- `0x18004ecf0`
- `0x180059df0`
- `0x18005e260`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059f00`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005a0a1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005a32c`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180059f00`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005a0a1`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18005a32c`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::CreateAsync__ResumeCoro_1(
        char *a1)
{
  _WORD *v2; // r14
  __int64 v3; // rcx
  char *v4; // rcx
  _QWORD *v5; // rdx
  const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *Async; // rax
  volatile __int64 *v7; // rsi
  __int64 *v8; // r15
  int v9; // eax
  volatile __int64 *v10; // rsi
  _QWORD *v11; // rcx
  _QWORD *v12; // rsi
  __int64 v13; // rax
  _QWORD *v14; // r13
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-D8h] BYREF
  _BYTE v16[24]; // [rsp+88h] [rbp-C0h] BYREF
  _BYTE v17[24]; // [rsp+A0h] [rbp-A8h] BYREF

  v2 = a1 + 144;
  switch ( *((_WORD *)a1 + 72) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_57;
    case 2:
      *((_DWORD *)a1 + 67) = 0;
      winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered();
      winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::EnsureVectorSpaceId(
        a1 + 152,
        *((_QWORD *)a1 + 17));
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      a1[161] = 0;
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 58) = 3980;
        *((_QWORD *)a1 + 30) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 232));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(v3, a1);
      return;
    case 4:
      if ( !*((_QWORD *)a1 + 19) || *((_QWORD *)a1 + 19) == 16 )
      {
        if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
        {
          Init_thread_header(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          if ( __TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA == -1 )
          {
            `winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null = 0;
            atexit(winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl_winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions_winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions__::_2_::_dynamic_atexit_destructor_for__null__);
            Init_thread_footer(&__TSS0__1____GetAsgImpl_USemanticTextIndexStoreOptions_implementation_SemanticSearch_Windows_Microsoft_winrt__U13456__implementation_SemanticSearch_Windows_Microsoft_winrt__YAAEB_PAEBUSemanticTextIndexStoreOptions_2345__Z_4HA);
          }
        }
        v5 = &`winrt::Microsoft::Windows::SemanticSearch::implementation::GetAsgImpl<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStoreOptions,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions>'::`2'::null;
      }
      else
      {
        v5 = (_QWORD *)(*((_QWORD *)a1 + 19) - 16LL + 56);
      }
      Async = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(
                (const struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *)(a1 + 168),
                v5);
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 62) = 3980;
        *((_QWORD *)a1 + 32) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v16,
          (const struct winrt::impl::slim_source_location *)(a1 + 248));
        throw (winrt::hresult_canceled *)v16;
      }
      *((_QWORD *)a1 + 22) = 0;
      *((_QWORD *)a1 + 23) = Async;
      *((_QWORD *)a1 + 24) = 0;
      a1[200] = 1;
      *v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions const &>::promise_type>(
                              (__int64)(a1 + 176),
                              (__int64)a1) )
        return;
      goto LABEL_31;
    case 5:
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      v4 = a1 + 152;
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v4);
      goto LABEL_57;
    case 6:
LABEL_31:
      *((_DWORD *)a1 + 68) = 3535;
      *((_QWORD *)a1 + 35) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Windows.Foundation.h";
      if ( *((int *)a1 + 49) < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult(*((unsigned int *)a1 + 49), a1 + 272);
      }
      if ( *((_DWORD *)a1 + 48) == 2 )
      {
        *((_DWORD *)a1 + 72) = 3432;
        *((_QWORD *)a1 + 37) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gen"
                               "erated Files\\winrt\\Windows.Foundation.h";
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v17,
          (const struct winrt::impl::slim_source_location *)(a1 + 288));
        throw (winrt::hresult_canceled *)v17;
      }
      v8 = (__int64 *)(a1 + 208);
      *((_QWORD *)a1 + 26) = 0;
      *((_DWORD *)a1 + 67) = 4;
      *((_DWORD *)a1 + 76) = 116;
      *((_QWORD *)a1 + 39) = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Windows.Foundation.h";
      v9 = (*(__int64 (__fastcall **)(_QWORD, char *))(***((_QWORD ***)a1 + 23) + 64LL))(
             **((_QWORD **)a1 + 23),
             a1 + 208);
      if ( v9 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v9, a1 + 304);
      }
      if ( *((_QWORD *)a1 + 22) )
      {
        v10 = (volatile __int64 *)*((_QWORD *)a1 + 22);
        while ( _InterlockedExchange64(v10, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 21) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
      winrt::Microsoft::Windows::SemanticSearch::implementation::FixObsoleteSpaceV6(
        (void (__fastcall ****)(_QWORD, __int64 *, __int64 *))a1 + 26,
        (_QWORD *)a1 + 19);
      v11 = operator new(0x70u);
      v12 = v11 + 2;
      v11[2] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore>::`vftable';
      v11[3] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore2>::`vftable';
      v11[4] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IClosable>::`vftable';
      v11[5] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex>::`vftable';
      v11[6] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex>::`vftable';
      v11[7] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex2>::`vftable';
      v11[8] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex2>::`vftable';
      v11[9] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex3>::`vftable';
      v11[10] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex3>::`vftable';
      v11[11] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex4>::`vftable';
      v11[12] = &winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex4>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v11[1] = 1;
      *v11 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore>::`vftable';
      v13 = *v8;
      *v8 = 0;
      v11[13] = v13;
      *v11 = &winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore>::`vftable';
      if ( !v11 )
        v12 = 0;
      *((_QWORD *)a1 + 27) = v12;
      v14 = a1 + 120;
      if ( a1 + 120 == a1 + 216 )
      {
        if ( v12 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 216);
      }
      else
      {
        if ( *v14 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 120);
        *v14 = v12;
      }
      if ( *v8 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 208);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
      *((_QWORD *)a1 + 28) = a1 + 16;
      *v2 = 0;
      *(_QWORD *)a1 = 0;
      if ( !winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextEmbeddingsCreator &,winrt::array_view<__int64 const>,enum winrt::Microsoft::Windows::Workloads::WorkloadPriority>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::EmbeddingVector>,void>::final_suspend_awaiter::await_suspend((__int64 *)a1 + 28) )
        goto LABEL_57;
      return;
    case 7:
      if ( *((_QWORD *)a1 + 22) )
      {
        v7 = (volatile __int64 *)*((_QWORD *)a1 + 22);
        while ( _InterlockedExchange64(v7, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 21) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 168);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 152);
LABEL_57:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ITextEmbeddingsModel>,winrt::Microsoft::Windows::SemanticSearch::implementation::ImageEmbeddingTextModelFactory &>::promise_type::~promise_type((_QWORD *)a1 + 2);
      if ( *((_WORD *)a1 + 73) )
        operator delete(a1);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x180059df0  mov     r11, rsp
0x180059df3  mov     [r11+10h], rbx
0x180059df7  mov     [r11+18h], rsi
0x180059dfb  mov     [r11+8], rcx
0x180059dff  push    rdi
0x180059e00  push    r12
0x180059e02  push    r13
0x180059e04  push    r14
0x180059e06  push    r15
0x180059e08  sub     rsp, 120h
0x180059e0f  mov     rax, cs:__security_cookie
0x180059e16  xor     rax, rsp
0x180059e19  mov     [rsp+148h+var_30], rax
0x180059e21  mov     rbx, rcx
0x180059e24  mov     [rsp+148h+var_118], rcx
0x180059e29  lea     r14, [rbx+90h]
0x180059e30  mov     [rsp+148h+var_108], r14
0x180059e35  movzx   eax, word ptr [r14]
0x180059e39  mov     [rsp+148h+var_128], ax
0x180059e3e  inc     ax; switch 9 cases
0x180059e41  cmp     ax, 8
0x180059e45  ja      def_180059E60; jumptable 0000000180059E60 default case, case 0
0x180059e4b  movsx   rax, ax
0x180059e4f  lea     rdx, cs:180000000h
0x180059e56  mov     ecx, ds:(jpt_180059E60 - 180000000h)[rdx+rax*4]
0x180059e5d  add     rcx, rdx
0x180059e60  jmp     rcx; switch jump
0x180059e62  jmp     loc_18005A380; jumptable 0000000180059E60 case 3
0x180059e67  xor     edi, edi; jumptable 0000000180059E60 case 2
0x180059e69  mov     [rbx+10Ch], edi
0x180059e6f  call    ?EnsureRegistered@AiFabricModelFactories@implementation@SemanticSearch@Windows@Microsoft@winrt@@SAXXZ; winrt::Microsoft::Windows::SemanticSearch::implementation::AiFabricModelFactories::EnsureRegistered(void)
0x180059e74  lea     rcx, [rbx+98h]
0x180059e7b  mov     rdx, [rbx+88h]
0x180059e82  call    ?EnsureVectorSpaceId@SemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@SA?AUSemanticTextIndexStoreOptions@3456@AEBU73456@@Z; winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore::EnsureVectorSpaceId(winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions const &)
0x180059e87  nop
0x180059e88  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180059e8f  mov     [rbx+0A1h], dil
0x180059e96  mov     eax, [rbx+70h]
0x180059e99  cmp     eax, 2
0x180059e9c  jnz     short loc_180059ED4
0x180059e9e  lea     rdx, [rbx+0E8h]; struct winrt::impl::slim_source_location *
0x180059ea5  mov     dword ptr [rdx], 0F8Ch
0x180059eab  lea     rcx, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180059eb2  mov     [rbx+0F0h], rcx
0x180059eb9  lea     rcx, [rsp+148h+pExceptionObject]; this
0x180059ebe  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180059ec3  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180059eca  lea     rcx, [rsp+148h+pExceptionObject]; pExceptionObject
0x180059ecf  call    _CxxThrowException
0x180059ed4  mov     eax, 4
0x180059ed9  mov     [r14], ax
0x180059edd  mov     rdx, rbx
0x180059ee0  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180059ee5  jmp     loc_18005A3A3
0x180059eea  mov     eax, 0FFFFFFFFh; jumptable 0000000180059E60 case 5
0x180059eef  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180059ef7  sub     eax, 1
0x180059efa  jz      short loc_180059F07
0x180059efc  test    eax, eax
0x180059efe  jns     short loc_180059F07
0x180059f00  call    cs:__imp_abort
0x180059f07  lea     rcx, [rbx+98h]
0x180059f0e  mov     rax, [rcx]
0x180059f11  mov     [rsp+148h+var_120], rax
0x180059f16  test    rax, rax
0x180059f19  jz      short loc_180059F21
0x180059f1b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180059f20  nop
0x180059f21  jmp     loc_18005A380; jumptable 0000000180059E60 cases -1,1
0x180059f26  cmp     qword ptr [rbx+98h], 0; jumptable 0000000180059E60 case 4
0x180059f2e  jz      short loc_180059F45
0x180059f30  mov     rax, [rbx+98h]
0x180059f37  sub     rax, 10h
0x180059f3b  jz      short loc_180059F45
0x180059f3d  lea     rdx, [rax+38h]
0x180059f41  xor     edi, edi
0x180059f43  jmp     short loc_180059FA9
0x180059f45  mov     ecx, cs:_tls_index
0x180059f4b  mov     rax, gs:58h
0x180059f54  mov     edx, 4
0x180059f59  mov     rax, [rax+rcx*8]
0x180059f5d  mov     ecx, [rdx+rax]
0x180059f60  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA, ecx
0x180059f66  jle     short loc_180059FA0
0x180059f68  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA
0x180059f6f  call    _Init_thread_header
0x180059f74  cmp     cs:?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA, 0FFFFFFFFh
0x180059f7b  jnz     short loc_180059FA0
0x180059f7d  xor     edi, edi
0x180059f7f  mov     cs:?null@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B, rdi
0x180059f86  lea     rcx, _winrt__Microsoft__Windows__SemanticSearch__implementation__GetAsgImpl_winrt__Microsoft__Windows__SemanticSearch__implementation__SemanticTextIndexStoreOptions_winrt__Microsoft__Windows__SemanticSearch__SemanticTextIndexStoreOptions_____2____dynamic_atexit_destructor_for__null__; void (__cdecl *)()
0x180059f8d  call    atexit
0x180059f92  lea     rcx, ?$TSS0@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4HA
0x180059f99  call    _Init_thread_footer
0x180059f9e  jmp     short loc_180059FA2
0x180059fa0  xor     edi, edi
0x180059fa2  lea     rdx, ?null@?1???$GetAsgImpl@USemanticTextIndexStoreOptions@implementation@SemanticSearch@Windows@Microsoft@winrt@@U13456@@implementation@SemanticSearch@Windows@Microsoft@winrt@@YAAEB_PAEBUSemanticTextIndexStoreOptions@2345@@Z@4U6Compatibility@AiFabric@SemanticIndex@Asg@45@B
0x180059fa9  lea     rcx, [rbx+0A8h]; struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions *
0x180059fb0  call    ?CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::CreateAsync(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions const &)
0x180059fb5  nop
0x180059fb6  mov     ecx, [rbx+70h]
0x180059fb9  cmp     ecx, 2
0x180059fbc  jnz     short loc_180059FFA
0x180059fbe  lea     rdx, [rbx+0F8h]; struct winrt::impl::slim_source_location *
0x180059fc5  mov     dword ptr [rdx], 0F8Ch
0x180059fcb  lea     rcx, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180059fd2  mov     [rbx+100h], rcx
0x180059fd9  lea     rcx, [rsp+148h+var_C0]; this
0x180059fe1  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180059fe6  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180059fed  lea     rcx, [rsp+148h+var_C0]; pExceptionObject
0x180059ff5  call    _CxxThrowException
0x180059ffa  lea     rcx, [rbx+0B0h]
0x18005a001  mov     [rcx], rdi
0x18005a004  mov     [rbx+0B8h], rax
0x18005a00b  mov     qword ptr [rbx+0C0h], 0
0x18005a016  mov     byte ptr [rbx+0C8h], 1
0x18005a01d  mov     eax, 6
0x18005a022  mov     [r14], ax
0x18005a026  mov     rdx, rbx
0x18005a029  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUSemanticTextIndexStoreOptions@SemanticSearch@3Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperation@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticTextIndexStore@SemanticSearch@Windows@Microsoft@winrt@@@Foundation@Windows@winrt@@AEBUSemanticTextIndexStoreOptions@SemanticSearch@3Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions const &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStore>,winrt::Microsoft::Windows::SemanticSearch::SemanticTextIndexStoreOptions const &>::promise_type>)
0x18005a02e  test    al, al
0x18005a030  jz      loc_18005A0C9
0x18005a036  jmp     loc_18005A3A3
0x18005a03b  cmp     qword ptr [rbx+0B0h], 0; jumptable 0000000180059E60 case 7
0x18005a043  jz      short loc_18005A071
0x18005a045  mov     rsi, [rbx+0B0h]
0x18005a04c  mov     [rsp+148h+var_100], rsi
0x18005a051  xor     edi, edi
0x18005a053  mov     eax, edi
0x18005a055  xchg    rax, [rsi]
0x18005a058  cmp     rax, 1
0x18005a05c  jnz     short loc_18005A071
0x18005a05e  xchg    ax, ax
0x18005a060  call    _Thrd_yield
0x18005a065  mov     rax, rdi
0x18005a068  xchg    rax, [rsi]
0x18005a06b  cmp     rax, 1
0x18005a06f  jz      short loc_18005A060
0x18005a071  lea     rcx, [rbx+0A8h]
0x18005a078  mov     rax, [rcx]
0x18005a07b  mov     [rsp+148h+var_110], rax
0x18005a080  test    rax, rax
0x18005a083  jz      short loc_18005A08B
0x18005a085  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a08a  nop
0x18005a08b  mov     eax, 0FFFFFFFFh
0x18005a090  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005a098  sub     eax, 1
0x18005a09b  jz      short loc_18005A0A8
0x18005a09d  test    eax, eax
0x18005a09f  jns     short loc_18005A0A8
0x18005a0a1  call    cs:__imp_abort
0x18005a0a8  lea     rcx, [rbx+98h]
0x18005a0af  mov     rax, [rcx]
0x18005a0b2  mov     [rsp+148h+var_120], rax
0x18005a0b7  test    rax, rax
0x18005a0ba  jz      short loc_18005A0C2
0x18005a0bc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a0c1  nop
0x18005a0c2  jmp     loc_18005A380; jumptable 0000000180059E60 cases -1,1
0x18005a0c7  xor     edi, edi; jumptable 0000000180059E60 case 6
0x18005a0c9  lea     rdx, [rbx+110h]
0x18005a0d0  mov     dword ptr [rdx], 0DCFh
0x18005a0d6  lea     rcx, aCW1SProductApi_33; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18005a0dd  mov     [rbx+118h], rcx
0x18005a0e4  mov     eax, [rbx+0C4h]
0x18005a0ea  mov     [rsp+148h+var_EC], eax
0x18005a0ee  test    eax, eax
0x18005a0f0  jns     short loc_18005A104
0x18005a0f2  lfence
0x18005a0f5  mov     ecx, [rbx+0C4h]
0x18005a0fb  mov     [rsp+148h+var_EC], ecx
0x18005a0ff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005a104  mov     eax, [rbx+0C0h]
0x18005a10a  mov     [rsp+148h+var_F0], eax
0x18005a10e  cmp     eax, 2
0x18005a111  jnz     short loc_18005A149
0x18005a113  lea     rdx, [rbx+120h]; struct winrt::impl::slim_source_location *
0x18005a11a  mov     dword ptr [rdx], 0D68h
0x18005a120  mov     [rbx+128h], rcx
0x18005a127  lea     rcx, [rsp+148h+var_A8]; this
0x18005a12f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18005a134  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18005a13b  lea     rcx, [rsp+148h+var_A8]; pExceptionObject
0x18005a143  call    _CxxThrowException
0x18005a149  lea     r15, [rbx+0D0h]
0x18005a150  mov     [r15], rdi
0x18005a153  mov     dword ptr [rbx+10Ch], 4
0x18005a15d  mov     dword ptr [rbx+130h], 74h ; 't'
0x18005a167  mov     [rbx+138h], rcx
0x18005a16e  mov     rax, [rbx+0B8h]
0x18005a175  mov     [rsp+148h+var_F8], rax
0x18005a17a  mov     rcx, [rax]
0x18005a17d  mov     rax, [rbx+0B8h]
0x18005a184  mov     [rsp+148h+var_F8], rax
0x18005a189  mov     rax, [rax]
0x18005a18c  mov     r8, [rax]
0x18005a18f  mov     rdx, r15
0x18005a192  mov     rax, [r8+40h]
0x18005a196  call    cs:__guard_dispatch_icall_fptr
0x18005a19c  test    eax, eax
0x18005a19e  jns     short loc_18005A1B2
0x18005a1a0  lfence
0x18005a1a3  lea     rdx, [rbx+130h]
0x18005a1aa  mov     ecx, eax
0x18005a1ac  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18005a1b2  cmp     qword ptr [rbx+0B0h], 0
0x18005a1ba  jz      short loc_18005A1E5
0x18005a1bc  mov     rsi, [rbx+0B0h]
0x18005a1c3  mov     [rsp+148h+var_100], rsi
0x18005a1c8  mov     rcx, rdi
0x18005a1cb  xchg    rcx, [rsi]
0x18005a1ce  cmp     rcx, 1
0x18005a1d2  jnz     short loc_18005A1E5
0x18005a1d4  call    _Thrd_yield
0x18005a1d9  mov     rax, rdi
0x18005a1dc  xchg    rax, [rsi]
0x18005a1df  cmp     rax, 1
0x18005a1e3  jz      short loc_18005A1D4
0x18005a1e5  lea     rcx, [rbx+0A8h]
0x18005a1ec  mov     rax, [rcx]
0x18005a1ef  mov     [rsp+148h+var_110], rax
0x18005a1f4  test    rax, rax
0x18005a1f7  jz      short loc_18005A1FE
0x18005a1f9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a1fe  lea     rdx, [rbx+98h]
0x18005a205  mov     rcx, r15
0x18005a208  call    winrt__Microsoft__Windows__SemanticSearch__implementation__FixObsoleteSpaceV6
0x18005a20d  mov     ecx, 70h ; 'p'; Size
0x18005a212  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a217  mov     rcx, rax
0x18005a21a  lea     rsi, [rax+10h]
0x18005a21e  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStore@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore>::`vftable'
0x18005a225  mov     [rsi], rax
0x18005a228  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndexStore2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndexStore2>::`vftable'
0x18005a22f  mov     [rsi+8], rax
0x18005a233  lea     rax, ??_7?$produce@USemanticImageIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UIClosable@Foundation@46@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IClosable>::`vftable'
0x18005a23a  mov     [rsi+10h], rax
0x18005a23e  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticIndex@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex>::`vftable'
0x18005a245  mov     [rsi+18h], rax
0x18005a249  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndex@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex>::`vftable'
0x18005a250  mov     [rsi+20h], rax
0x18005a254  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticIndex2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex2>::`vftable'
0x18005a25b  mov     [rsi+28h], rax
0x18005a25f  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndex2@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex2>::`vftable'
0x18005a266  mov     [rsi+30h], rax
0x18005a26a  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticIndex3@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex3>::`vftable'
0x18005a271  mov     [rsi+38h], rax
0x18005a275  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndex3@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex3>::`vftable'
0x18005a27c  mov     [rsi+40h], rax
0x18005a280  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticIndex4@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticIndex4>::`vftable'
0x18005a287  mov     [rsi+48h], rax
0x18005a28b  lea     rax, ??_7?$produce@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@UISemanticTextIndex4@3456@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore,winrt::Microsoft::Windows::SemanticSearch::ISemanticTextIndex4>::`vftable'
0x18005a292  mov     [rsi+50h], rax
0x18005a296  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005a29d  mov     qword ptr [rcx+8], 1
0x18005a2a5  lea     rax, ??_7?$heap_implements@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore>::`vftable'
0x18005a2ac  mov     [rcx], rax
0x18005a2af  mov     rax, [r15]
0x18005a2b2  mov     [r15], rdi
0x18005a2b5  mov     [rcx+68h], rax
0x18005a2b9  lea     rax, ??_7?$heap_implements@USemanticTextIndexStore@implementation@SemanticSearch@Windows@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Windows::SemanticSearch::implementation::SemanticTextIndexStore>::`vftable'
0x18005a2c0  mov     [rcx], rax
0x18005a2c3  test    rcx, rcx
0x18005a2c6  cmovz   rsi, rdi
0x18005a2ca  lea     rcx, [rbx+0D8h]
0x18005a2d1  mov     [rcx], rsi
0x18005a2d4  lea     r13, [rbx+78h]
0x18005a2d8  cmp     r13, rcx
0x18005a2db  jz      short loc_18005A2F2
0x18005a2dd  cmp     qword ptr [r13+0], 0
0x18005a2e2  jz      short loc_18005A2EC
0x18005a2e4  mov     rcx, r13
0x18005a2e7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a2ec  mov     [r13+0], rsi
0x18005a2f0  jmp     short loc_18005A2FD
0x18005a2f2  test    rsi, rsi
0x18005a2f5  jz      short loc_18005A2FD
0x18005a2f7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a2fc  nop
0x18005a2fd  mov     rax, [r15]
0x18005a300  mov     [rsp+148h+var_90], rax
0x18005a308  test    rax, rax
0x18005a30b  jz      short loc_18005A316
0x18005a30d  mov     rcx, r15
0x18005a310  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18005a315  nop
0x18005a316  mov     eax, 0FFFFFFFFh
0x18005a31b  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18005a323  sub     eax, 1
0x18005a326  jz      short loc_18005A333
0x18005a328  test    eax, eax
0x18005a32a  jns     short loc_18005A333
0x18005a32c  call    cs:__imp_abort
0x18005a333  mov     rax, [rbx+98h]
0x18005a33a  mov     [rsp+148h+var_120], rax
0x18005a33f  test    rax, rax
0x18005a342  jz      short loc_18005A351
0x18005a344  lea     rcx, [rbx+98h]
  ... truncated ...
```
