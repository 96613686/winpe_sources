# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync$_ResumeCoro$1

- ea: `0x18023b8f0`
- end: `0x18023bf70`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync$_ResumeCoro$1`
- size: `1664`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18023b8d0`
- `0x18023bf70`

## callees

- `0x180003350`
- `0x180003bd0`
- `0x180003fb0`
- `0x180004510`
- `0x18000b2a0`
- `0x18000d230`
- `0x18001bc40`
- `0x18001fd80`
- `0x180020670`
- `0x18002f8e0`
- `0x180047520`
- `0x180062570`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023b8f0`

## string_xrefs

- `0x18023ba1b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023bccb`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023bb6f`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18023be19`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync__ResumeCoro_1(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _WORD *v4; // rdi
  __int64 v5; // r15
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  signed __int64 v9; // rax
  signed __int64 v10; // rtt
  volatile __int64 *v11; // rbx
  char v12; // r15
  volatile __int64 *v13; // rbx
  unsigned int *v14; // rax
  __int64 v15; // r15
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // rdx
  signed __int64 v19; // rax
  signed __int64 v20; // rtt
  volatile __int64 *v21; // rbx
  char v22; // r15
  volatile __int64 *v23; // rbx
  unsigned int *v24; // rax
  _BYTE pExceptionObject[24]; // [rsp+58h] [rbp-110h] BYREF
  _BYTE v26[24]; // [rsp+70h] [rbp-F8h] BYREF
  _BYTE v27[24]; // [rsp+88h] [rbp-E0h] BYREF
  _BYTE v28[24]; // [rsp+A0h] [rbp-C8h] BYREF
  __int64 v29; // [rsp+B8h] [rbp-B0h]
  __int64 v30; // [rsp+D8h] [rbp-90h]

  v4 = (_WORD *)(a1 + 144);
  switch ( *(_WORD *)(a1 + 144) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_65;
    case 2:
      if ( (*(_BYTE *)(a1 + 136) & 1) == 0 )
        goto LABEL_33;
      *(_QWORD *)(a1 + 152) = 0;
      v5 = *(_QWORD *)(a1 + 128);
      LOBYTE(a3) = 1;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        v5,
        a1 + 160,
        a3);
      v6 = 0;
      v7 = *(_QWORD *)(v5 + 232);
      v8 = v7 - 16;
      if ( !v7 )
        v8 = 0;
      if ( !v8 )
        goto LABEL_10;
      v6 = v8;
      v9 = *(_QWORD *)(v8 + 8);
      if ( v9 < 0 )
        goto LABEL_9;
      break;
    case 4:
      goto LABEL_24;
    case 5:
      v11 = *(volatile __int64 **)(a1 + 184);
      if ( v11 )
      {
        v29 = *(_QWORD *)(a1 + 184);
        while ( _InterlockedExchange64(v11, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 176) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
      if ( *(_QWORD *)(a1 + 152) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 152);
      goto LABEL_65;
    case 6:
      goto LABEL_55;
    case 7:
      v21 = *(volatile __int64 **)(a1 + 312);
      if ( v21 )
      {
        v30 = *(_QWORD *)(a1 + 312);
        while ( _InterlockedExchange64(v21, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 304) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 304);
      if ( *(_QWORD *)(a1 + 280) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 280);
      goto LABEL_65;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
    v10 = v9;
    v9 = _InterlockedCompareExchange64((volatile signed __int64 *)(v8 + 8), v9 + 1, v9);
    if ( v10 == v9 )
      break;
    if ( v9 < 0 )
    {
LABEL_9:
      _InterlockedIncrement((volatile signed __int32 *)(2 * v9 + 24));
      break;
    }
  }
LABEL_10:
  *(_QWORD *)(a1 + 152) = v6;
  if ( *(_BYTE *)(a1 + 168) )
    Mtx_unlock(*(_Mtx_t *)(a1 + 160));
  *(_BYTE *)(a1 + 448) = 0;
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(
    v6,
    a1 + 176,
    a1 + 416);
  if ( *(_DWORD *)(a1 + 112) == 2 )
  {
    *(_DWORD *)(a1 + 456) = 5672;
    *(_QWORD *)(a1 + 464) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated F"
                            "iles\\winrt\\Windows.Foundation.h";
    *(_QWORD *)(a1 + 472) = 0;
    winrt::hresult_canceled::hresult_canceled(
      (winrt::hresult_canceled *)pExceptionObject,
      (const struct winrt::impl::slim_source_location *)(a1 + 456));
    throw (winrt::hresult_canceled *)pExceptionObject;
  }
  *(_QWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 192) = a1 + 176;
  *(_QWORD *)(a1 + 200) = 0;
  *(_BYTE *)(a1 + 208) = 1;
  *v4 = 4;
  if ( !(unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                           (_QWORD *)(a1 + 184),
                           a1) )
  {
LABEL_24:
    v12 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 184);
    v13 = *(volatile __int64 **)(a1 + 184);
    if ( v13 )
    {
      v29 = *(_QWORD *)(a1 + 184);
      while ( _InterlockedExchange64(v13, 0) == 1 )
        Thrd_yield();
    }
    if ( *(_QWORD *)(a1 + 176) )
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 176);
    if ( !v12 )
    {
      *(_DWORD *)(a1 + 216) = 1760;
      *(_QWORD *)(a1 + 224) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
      *(_QWORD *)(a1 + 232) = 0;
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)(a1 + 240),
        L"Failed to load primary embedding model - migration of underlying index may be required");
      v14 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 272), -2081706723);
      winrt::hresult_error::hresult_error(v26, *v14, a1 + 240, a1 + 216);
      throw (winrt::hresult_error *)v26;
    }
    if ( *(_QWORD *)(a1 + 152) )
      winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 152);
LABEL_33:
    if ( (*(_DWORD *)(a1 + 136) & 2) != 0 )
    {
      *(_QWORD *)(a1 + 280) = 0;
      v15 = *(_QWORD *)(a1 + 128);
      LOBYTE(a3) = 1;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
        v15,
        a1 + 288,
        a3);
      v16 = 0;
      v17 = *(_QWORD *)(v15 + 240);
      v18 = v17 - 16;
      if ( !v17 )
        v18 = 0;
      if ( v18 )
      {
        v16 = v18;
        v19 = *(_QWORD *)(v18 + 8);
        if ( v19 < 0 )
        {
LABEL_40:
          _InterlockedIncrement((volatile signed __int32 *)(2 * v19 + 24));
        }
        else
        {
          while ( 1 )
          {
            v20 = v19;
            v19 = _InterlockedCompareExchange64((volatile signed __int64 *)(v18 + 8), v19 + 1, v19);
            if ( v20 == v19 )
              break;
            if ( v19 < 0 )
              goto LABEL_40;
          }
        }
      }
      *(_QWORD *)(a1 + 280) = v16;
      if ( *(_BYTE *)(a1 + 296) )
        Mtx_unlock(*(_Mtx_t *)(a1 + 288));
      *(_BYTE *)(a1 + 512) = 0;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(
        v16,
        a1 + 304,
        a1 + 480);
      if ( *(_DWORD *)(a1 + 112) == 2 )
      {
        *(_DWORD *)(a1 + 520) = 5672;
        *(_QWORD *)(a1 + 528) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Windows.Foundation.h";
        *(_QWORD *)(a1 + 536) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v27,
          (const struct winrt::impl::slim_source_location *)(a1 + 520));
        throw (winrt::hresult_canceled *)v27;
      }
      *(_QWORD *)(a1 + 312) = 0;
      *(_QWORD *)(a1 + 320) = a1 + 304;
      *(_QWORD *)(a1 + 328) = 0;
      *(_BYTE *)(a1 + 336) = 1;
      *v4 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(
                              (_QWORD *)(a1 + 312),
                              a1) )
        return;
LABEL_55:
      v22 = winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(a1 + 312);
      v23 = *(volatile __int64 **)(a1 + 312);
      if ( v23 )
      {
        v30 = *(_QWORD *)(a1 + 312);
        while ( _InterlockedExchange64(v23, 0) == 1 )
          Thrd_yield();
      }
      if ( *(_QWORD *)(a1 + 304) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 304);
      if ( !v22 )
      {
        *(_DWORD *)(a1 + 344) = 1776;
        *(_QWORD *)(a1 + 352) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
        *(_QWORD *)(a1 + 360) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 368),
          L"Failed to load text query embedding model - migration of underlying index may be required");
        v24 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(a1 + 400), -2081706723);
        winrt::hresult_error::hresult_error(v28, *v24, a1 + 368, a1 + 344);
        throw (winrt::hresult_error *)v28;
      }
      if ( *(_QWORD *)(a1 + 280) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(a1 + 280);
    }
    *(_QWORD *)(a1 + 408) = a1 + 16;
    *v4 = 0;
    *(_QWORD *)a1 = 0;
    if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator> &,winrt::com_ptr<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>,asg::CancellationTokenSource>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
    {
LABEL_65:
      if ( *(_QWORD *)(a1 + 104) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 104);
      if ( *(_QWORD *)(a1 + 96) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      __ExceptionPtrDestroy((void *)(a1 + 72));
      winrt::impl::root_implements<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::hstring,std::map<winrt::hstring,winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::hstring>>>::subtract_final_reference(a1 + 16);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *(_WORD *)(a1 + 146) )
        operator delete((void *)a1);
    }
  }
}

```

## disassembly

```asm
0x18023b8f0  mov     [rsp+Block], rcx
0x18023b8f5  push    rbx
0x18023b8f6  push    rsi
0x18023b8f7  push    rdi
0x18023b8f8  push    r12
0x18023b8fa  push    r14
0x18023b8fc  push    r15
0x18023b8fe  sub     rsp, 138h
0x18023b905  mov     rsi, [rsp+168h+Block]
0x18023b90d  lea     rdi, [rsi+90h]
0x18023b914  mov     [rsp+168h+var_138], rdi
0x18023b919  movzx   eax, word ptr [rdi]
0x18023b91c  mov     [rsp+168h+var_148], ax
0x18023b921  inc     ax; switch 9 cases
0x18023b924  cmp     ax, 8
0x18023b928  ja      def_18023B943; jumptable 000000018023B943 default case, case 0
0x18023b92e  movsx   rax, ax
0x18023b932  lea     rdx, cs:180000000h
0x18023b939  mov     ecx, ds:(jpt_18023B943 - 180000000h)[rdx+rax*4]
0x18023b940  add     rcx, rdx
0x18023b943  jmp     rcx; switch jump
0x18023b945  jmp     loc_18023BED2; jumptable 000000018023B943 case 3
0x18023b94a  xor     r14d, r14d; jumptable 000000018023B943 case 2
0x18023b94d  test    byte ptr [rsi+88h], 1
0x18023b954  jz      loc_18023BBF0
0x18023b95a  mov     [rsi+98h], r14
0x18023b961  mov     r15, [rsi+80h]
0x18023b968  mov     r8b, 1
0x18023b96b  lea     rdx, [rsi+0A0h]
0x18023b972  mov     rcx, r15
0x18023b975  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18023b97a  mov     ebx, r14d
0x18023b97d  mov     rax, [r15+0E8h]
0x18023b984  lea     rdx, [rax-10h]
0x18023b988  test    rax, rax
0x18023b98b  cmovz   rdx, r14
0x18023b98f  test    rdx, rdx
0x18023b992  jz      short loc_18023B9B6
0x18023b994  mov     rbx, rdx
0x18023b997  mov     rax, [rdx+8]
0x18023b99b  test    rax, rax
0x18023b99e  js      short loc_18023B9B1
0x18023b9a0  lea     rcx, [rax+1]
0x18023b9a4  lock cmpxchg [rdx+8], rcx
0x18023b9aa  jz      short loc_18023B9B6
0x18023b9ac  test    rax, rax
0x18023b9af  jns     short loc_18023B9A0
0x18023b9b1  lock inc dword ptr [rax+rax+18h]
0x18023b9b6  mov     [rsi+98h], rbx
0x18023b9bd  movzx   eax, byte ptr [rsi+0A8h]
0x18023b9c4  mov     [rsp+168h+var_128], al
0x18023b9c8  test    al, al
0x18023b9ca  jz      short loc_18023B9DD
0x18023b9cc  mov     rcx, [rsi+0A0h]; _Mtx_t
0x18023b9d3  mov     [rsp+168h+var_130], rcx
0x18023b9d8  call    _Mtx_unlock
0x18023b9dd  lea     r8, [rsi+1A0h]
0x18023b9e4  mov     byte ptr [rsi+1C0h], 0
0x18023b9eb  lea     r15, [rsi+0B0h]
0x18023b9f2  mov     [rsp+168h+arg_8], rbx
0x18023b9fa  mov     rdx, r15
0x18023b9fd  mov     rcx, rbx
0x18023ba00  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x18023ba05  nop
0x18023ba06  mov     eax, [rsi+70h]
0x18023ba09  cmp     eax, 2
0x18023ba0c  jnz     short loc_18023BA4B
0x18023ba0e  lea     rdx, [rsi+1C8h]; struct winrt::impl::slim_source_location *
0x18023ba15  mov     dword ptr [rdx], 1628h
0x18023ba1b  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023ba22  mov     [rsi+1D0h], rax
0x18023ba29  mov     [rsi+1D8h], r14
0x18023ba30  lea     rcx, [rsp+168h+pExceptionObject]; this
0x18023ba35  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023ba3a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023ba41  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x18023ba46  call    _CxxThrowException
0x18023ba4b  lea     rcx, [rsi+0B8h]
0x18023ba52  mov     [rcx], r14
0x18023ba55  mov     [rsi+0C0h], r15
0x18023ba5c  mov     [rsi+0C8h], r14
0x18023ba63  mov     byte ptr [rsi+0D0h], 1
0x18023ba6a  mov     eax, 4
0x18023ba6f  mov     [rdi], ax
0x18023ba72  mov     rdx, rsi
0x18023ba75  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18023ba7a  test    al, al
0x18023ba7c  jz      loc_18023BB03
0x18023ba82  jmp     loc_18023BF38
0x18023ba87  mov     rbx, [rsi+0B8h]; jumptable 000000018023B943 case 5
0x18023ba8e  test    rbx, rbx
0x18023ba91  jz      short loc_18023BAC1
0x18023ba93  mov     [rsp+168h+var_B0], rbx
0x18023ba9b  xor     r14d, r14d
0x18023ba9e  mov     eax, r14d
0x18023baa1  xchg    rax, [rbx]
0x18023baa4  cmp     rax, 1
0x18023baa8  jnz     short loc_18023BAC1
0x18023baaa  nop     word ptr [rax+rax+00h]
0x18023bab0  call    _Thrd_yield
0x18023bab5  mov     rax, r14
0x18023bab8  xchg    rax, [rbx]
0x18023babb  cmp     rax, 1
0x18023babf  jz      short loc_18023BAB0
0x18023bac1  lea     rcx, [rsi+0B0h]
0x18023bac8  mov     rax, [rcx]
0x18023bacb  mov     [rsp+168h+arg_18], rax
0x18023bad3  test    rax, rax
0x18023bad6  jz      short loc_18023BADE
0x18023bad8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023badd  nop
0x18023bade  lea     rcx, [rsi+98h]
0x18023bae5  mov     rax, [rcx]
0x18023bae8  mov     [rsp+168h+arg_8], rax
0x18023baf0  test    rax, rax
0x18023baf3  jz      short loc_18023BAFB
0x18023baf5  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18023bafa  nop
0x18023bafb  jmp     loc_18023BED2; jumptable 000000018023B943 cases -1,1
0x18023bb00  xor     r14d, r14d; jumptable 000000018023B943 case 4
0x18023bb03  lea     rcx, [rsi+0B8h]
0x18023bb0a  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18023bb0f  movzx   r15d, al
0x18023bb13  mov     rbx, [rsi+0B8h]
0x18023bb1a  test    rbx, rbx
0x18023bb1d  jz      short loc_18023BB44
0x18023bb1f  mov     [rsp+168h+var_B0], rbx
0x18023bb27  mov     rcx, r14
0x18023bb2a  xchg    rcx, [rbx]
0x18023bb2d  cmp     rcx, 1
0x18023bb31  jnz     short loc_18023BB44
0x18023bb33  call    _Thrd_yield
0x18023bb38  mov     rax, r14
0x18023bb3b  xchg    rax, [rbx]
0x18023bb3e  cmp     rax, 1
0x18023bb42  jz      short loc_18023BB33
0x18023bb44  lea     rcx, [rsi+0B0h]
0x18023bb4b  mov     rax, [rcx]
0x18023bb4e  mov     [rsp+168h+arg_18], rax
0x18023bb56  test    rax, rax
0x18023bb59  jz      short loc_18023BB60
0x18023bb5b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023bb60  test    r15b, r15b
0x18023bb63  jnz     short loc_18023BBD4
0x18023bb65  mov     dword ptr [rsi+0D8h], 6E0h
0x18023bb6f  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023bb76  mov     [rsi+0E0h], rax
0x18023bb7d  mov     [rsi+0E8h], r14
0x18023bb84  lea     rdx, aFailedToLoadPr; "Failed to load primary embedding model "...
0x18023bb8b  lea     rcx, [rsi+0F0h]; this
0x18023bb92  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023bb97  lea     rcx, [rsi+110h]; this
0x18023bb9e  mov     edx, 83EBAD1Dh; int
0x18023bba3  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18023bba8  lea     r9, [rsi+0D8h]
0x18023bbaf  lea     r8, [rsi+0F0h]
0x18023bbb6  mov     edx, [rax]
0x18023bbb8  lea     rcx, [rsp+168h+var_F8]
0x18023bbbd  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023bbc2  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18023bbc9  lea     rcx, [rsp+168h+var_F8]; pExceptionObject
0x18023bbce  call    _CxxThrowException
0x18023bbd4  lea     rcx, [rsi+98h]
0x18023bbdb  mov     rax, [rcx]
0x18023bbde  mov     [rsp+168h+arg_8], rax
0x18023bbe6  test    rax, rax
0x18023bbe9  jz      short loc_18023BBF0
0x18023bbeb  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18023bbf0  test    dword ptr [rsi+88h], 2
0x18023bbfa  jz      loc_18023BEA1
0x18023bc00  mov     [rsi+118h], r14
0x18023bc07  mov     r15, [rsi+80h]
0x18023bc0e  mov     r8b, 1
0x18023bc11  lea     rdx, [rsi+120h]
0x18023bc18  mov     rcx, r15
0x18023bc1b  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18023bc20  mov     rbx, r14
0x18023bc23  mov     rax, [r15+0F0h]
0x18023bc2a  lea     rdx, [rax-10h]
0x18023bc2e  test    rax, rax
0x18023bc31  cmovz   rdx, r14
0x18023bc35  test    rdx, rdx
0x18023bc38  jz      short loc_18023BC66
0x18023bc3a  mov     rbx, rdx
0x18023bc3d  mov     rax, [rdx+8]
0x18023bc41  test    rax, rax
0x18023bc44  js      short loc_18023BC61
0x18023bc46  nop     word ptr [rax+rax+00000000h]
0x18023bc50  lea     rcx, [rax+1]
0x18023bc54  lock cmpxchg [rdx+8], rcx
0x18023bc5a  jz      short loc_18023BC66
0x18023bc5c  test    rax, rax
0x18023bc5f  jns     short loc_18023BC50
0x18023bc61  lock inc dword ptr [rax+rax+18h]
0x18023bc66  mov     [rsi+118h], rbx
0x18023bc6d  movzx   eax, byte ptr [rsi+128h]
0x18023bc74  mov     [rsp+168h+var_118], al
0x18023bc78  test    al, al
0x18023bc7a  jz      short loc_18023BC8D
0x18023bc7c  mov     rcx, [rsi+120h]; _Mtx_t
0x18023bc83  mov     [rsp+168h+var_120], rcx
0x18023bc88  call    _Mtx_unlock
0x18023bc8d  lea     r8, [rsi+1E0h]
0x18023bc94  mov     byte ptr [rsi+200h], 0
0x18023bc9b  lea     r15, [rsi+130h]
0x18023bca2  mov     [rsp+168h+arg_10], rbx
0x18023bcaa  mov     rdx, r15
0x18023bcad  mov     rcx, rbx
0x18023bcb0  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x18023bcb5  nop
0x18023bcb6  mov     eax, [rsi+70h]
0x18023bcb9  cmp     eax, 2
0x18023bcbc  jnz     short loc_18023BD01
0x18023bcbe  lea     rdx, [rsi+208h]; struct winrt::impl::slim_source_location *
0x18023bcc5  mov     dword ptr [rdx], 1628h
0x18023bccb  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023bcd2  mov     [rsi+210h], rax
0x18023bcd9  mov     [rsi+218h], r14
0x18023bce0  lea     rcx, [rsp+168h+var_E0]; this
0x18023bce8  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023bced  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023bcf4  lea     rcx, [rsp+168h+var_E0]; pExceptionObject
0x18023bcfc  call    _CxxThrowException
0x18023bd01  lea     rcx, [rsi+138h]
0x18023bd08  mov     [rcx], r14
0x18023bd0b  mov     [rsi+140h], r15
0x18023bd12  mov     qword ptr [rsi+148h], 0
0x18023bd1d  mov     byte ptr [rsi+150h], 1
0x18023bd24  mov     eax, 6
0x18023bd29  mov     [rdi], ax
0x18023bd2c  mov     rdx, rsi
0x18023bd2f  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x18023bd34  test    al, al
0x18023bd36  jz      short loc_18023BDB0
0x18023bd38  jmp     loc_18023BF38
0x18023bd3d  mov     rbx, [rsi+138h]; jumptable 000000018023B943 case 7
0x18023bd44  test    rbx, rbx
0x18023bd47  jz      short loc_18023BD71
0x18023bd49  mov     [rsp+168h+var_90], rbx
0x18023bd51  xor     r14d, r14d
0x18023bd54  mov     eax, r14d
0x18023bd57  xchg    rax, [rbx]
0x18023bd5a  cmp     rax, 1
0x18023bd5e  jnz     short loc_18023BD71
0x18023bd60  call    _Thrd_yield
0x18023bd65  mov     rax, r14
0x18023bd68  xchg    rax, [rbx]
0x18023bd6b  cmp     rax, 1
0x18023bd6f  jz      short loc_18023BD60
0x18023bd71  lea     rcx, [rsi+130h]
0x18023bd78  mov     rax, [rcx]
0x18023bd7b  mov     [rsp+168h+var_140], rax
0x18023bd80  test    rax, rax
0x18023bd83  jz      short loc_18023BD8B
0x18023bd85  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023bd8a  nop
0x18023bd8b  lea     rcx, [rsi+118h]
0x18023bd92  mov     rax, [rcx]
0x18023bd95  mov     [rsp+168h+arg_10], rax
0x18023bd9d  test    rax, rax
0x18023bda0  jz      short loc_18023BDA8
0x18023bda2  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18023bda7  nop
0x18023bda8  jmp     loc_18023BED2; jumptable 000000018023B943 cases -1,1
0x18023bdad  xor     r14d, r14d; jumptable 000000018023B943 case 6
0x18023bdb0  lea     rcx, [rsi+138h]
0x18023bdb7  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18023bdbc  movzx   r15d, al
0x18023bdc0  mov     rbx, [rsi+138h]
0x18023bdc7  test    rbx, rbx
0x18023bdca  jz      short loc_18023BDF1
0x18023bdcc  mov     [rsp+168h+var_90], rbx
0x18023bdd4  mov     rcx, r14
0x18023bdd7  xchg    rcx, [rbx]
0x18023bdda  cmp     rcx, 1
0x18023bdde  jnz     short loc_18023BDF1
0x18023bde0  call    _Thrd_yield
0x18023bde5  mov     rax, r14
0x18023bde8  xchg    rax, [rbx]
0x18023bdeb  cmp     rax, 1
0x18023bdef  jz      short loc_18023BDE0
0x18023bdf1  lea     rcx, [rsi+130h]
0x18023bdf8  mov     rax, [rcx]
0x18023bdfb  mov     [rsp+168h+var_140], rax
0x18023be00  test    rax, rax
0x18023be03  jz      short loc_18023BE0A
0x18023be05  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023be0a  test    r15b, r15b
0x18023be0d  jnz     short loc_18023BE84
0x18023be0f  mov     dword ptr [rsi+158h], 6F0h
0x18023be19  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023be20  mov     [rsi+160h], rax
0x18023be27  mov     [rsi+168h], r14
0x18023be2e  lea     rdx, aFailedToLoadTe_1; "Failed to load text query embedding mod"...
0x18023be35  lea     rcx, [rsi+170h]; this
0x18023be3c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023be41  lea     rcx, [rsi+190h]; this
0x18023be48  mov     edx, 83EBAD1Dh; int
0x18023be4d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18023be52  lea     r9, [rsi+158h]
  ... truncated ...
```
