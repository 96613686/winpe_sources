# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync$_ResumeCoro$1

- ea: `0x180232030`
- end: `0x1802326b0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync$_ResumeCoro$1`
- size: `1664`
- prototype: ``
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180232010`
- `0x1802326b0`

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
- `0x18006df00`
- `0x1801d1e70`
- `0x1801d2b20`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180232030`

## string_xrefs

- `0x18023215b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023240b`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802322af`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x180232559`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon_asg::SemanticIndex::SemanticIndexStore_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator_winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator_::LoadAsync__ResumeCoro_1(
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
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync(
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
0x180232030  mov     [rsp+Block], rcx
0x180232035  push    rbx
0x180232036  push    rsi
0x180232037  push    rdi
0x180232038  push    r12
0x18023203a  push    r14
0x18023203c  push    r15
0x18023203e  sub     rsp, 138h
0x180232045  mov     rsi, [rsp+168h+Block]
0x18023204d  lea     rdi, [rsi+90h]
0x180232054  mov     [rsp+168h+var_138], rdi
0x180232059  movzx   eax, word ptr [rdi]
0x18023205c  mov     [rsp+168h+var_148], ax
0x180232061  inc     ax; switch 9 cases
0x180232064  cmp     ax, 8
0x180232068  ja      def_180232083; jumptable 0000000180232083 default case, case 0
0x18023206e  movsx   rax, ax
0x180232072  lea     rdx, cs:180000000h
0x180232079  mov     ecx, ds:(jpt_180232083 - 180000000h)[rdx+rax*4]
0x180232080  add     rcx, rdx
0x180232083  jmp     rcx; switch jump
0x180232085  jmp     loc_180232612; jumptable 0000000180232083 case 3
0x18023208a  xor     r14d, r14d; jumptable 0000000180232083 case 2
0x18023208d  test    byte ptr [rsi+88h], 1
0x180232094  jz      loc_180232330
0x18023209a  mov     [rsi+98h], r14
0x1802320a1  mov     r15, [rsi+80h]
0x1802320a8  mov     r8b, 1
0x1802320ab  lea     rdx, [rsi+0A0h]
0x1802320b2  mov     rcx, r15
0x1802320b5  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x1802320ba  mov     ebx, r14d
0x1802320bd  mov     rax, [r15+0E8h]
0x1802320c4  lea     rdx, [rax-10h]
0x1802320c8  test    rax, rax
0x1802320cb  cmovz   rdx, r14
0x1802320cf  test    rdx, rdx
0x1802320d2  jz      short loc_1802320F6
0x1802320d4  mov     rbx, rdx
0x1802320d7  mov     rax, [rdx+8]
0x1802320db  test    rax, rax
0x1802320de  js      short loc_1802320F1
0x1802320e0  lea     rcx, [rax+1]
0x1802320e4  lock cmpxchg [rdx+8], rcx
0x1802320ea  jz      short loc_1802320F6
0x1802320ec  test    rax, rax
0x1802320ef  jns     short loc_1802320E0
0x1802320f1  lock inc dword ptr [rax+rax+18h]
0x1802320f6  mov     [rsi+98h], rbx
0x1802320fd  movzx   eax, byte ptr [rsi+0A8h]
0x180232104  mov     [rsp+168h+var_128], al
0x180232108  test    al, al
0x18023210a  jz      short loc_18023211D
0x18023210c  mov     rcx, [rsi+0A0h]; _Mtx_t
0x180232113  mov     [rsp+168h+var_130], rcx
0x180232118  call    _Mtx_unlock
0x18023211d  lea     r8, [rsi+1A0h]
0x180232124  mov     byte ptr [rsi+1C0h], 0
0x18023212b  lea     r15, [rsi+0B0h]
0x180232132  mov     [rsp+168h+arg_8], rbx
0x18023213a  mov     rdx, r15
0x18023213d  mov     rcx, rbx
0x180232140  call    ?TryLoadCoreAsync@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@ImageEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x180232145  nop
0x180232146  mov     eax, [rsi+70h]
0x180232149  cmp     eax, 2
0x18023214c  jnz     short loc_18023218B
0x18023214e  lea     rdx, [rsi+1C8h]; struct winrt::impl::slim_source_location *
0x180232155  mov     dword ptr [rdx], 1628h
0x18023215b  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180232162  mov     [rsi+1D0h], rax
0x180232169  mov     [rsi+1D8h], r14
0x180232170  lea     rcx, [rsp+168h+pExceptionObject]; this
0x180232175  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023217a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180232181  lea     rcx, [rsp+168h+pExceptionObject]; pExceptionObject
0x180232186  call    _CxxThrowException
0x18023218b  lea     rcx, [rsi+0B8h]
0x180232192  mov     [rcx], r14
0x180232195  mov     [rsi+0C0h], r15
0x18023219c  mov     [rsi+0C8h], r14
0x1802321a3  mov     byte ptr [rsi+0D0h], 1
0x1802321aa  mov     eax, 4
0x1802321af  mov     [rdi], ax
0x1802321b2  mov     rdx, rsi
0x1802321b5  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x1802321ba  test    al, al
0x1802321bc  jz      loc_180232243
0x1802321c2  jmp     loc_180232678
0x1802321c7  mov     rbx, [rsi+0B8h]; jumptable 0000000180232083 case 5
0x1802321ce  test    rbx, rbx
0x1802321d1  jz      short loc_180232201
0x1802321d3  mov     [rsp+168h+var_B0], rbx
0x1802321db  xor     r14d, r14d
0x1802321de  mov     eax, r14d
0x1802321e1  xchg    rax, [rbx]
0x1802321e4  cmp     rax, 1
0x1802321e8  jnz     short loc_180232201
0x1802321ea  nop     word ptr [rax+rax+00h]
0x1802321f0  call    _Thrd_yield
0x1802321f5  mov     rax, r14
0x1802321f8  xchg    rax, [rbx]
0x1802321fb  cmp     rax, 1
0x1802321ff  jz      short loc_1802321F0
0x180232201  lea     rcx, [rsi+0B0h]
0x180232208  mov     rax, [rcx]
0x18023220b  mov     [rsp+168h+arg_18], rax
0x180232213  test    rax, rax
0x180232216  jz      short loc_18023221E
0x180232218  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023221d  nop
0x18023221e  lea     rcx, [rsi+98h]
0x180232225  mov     rax, [rcx]
0x180232228  mov     [rsp+168h+arg_8], rax
0x180232230  test    rax, rax
0x180232233  jz      short loc_18023223B
0x180232235  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18023223a  nop
0x18023223b  jmp     loc_180232612; jumptable 0000000180232083 cases -1,1
0x180232240  xor     r14d, r14d; jumptable 0000000180232083 case 4
0x180232243  lea     rcx, [rsi+0B8h]
0x18023224a  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x18023224f  movzx   r15d, al
0x180232253  mov     rbx, [rsi+0B8h]
0x18023225a  test    rbx, rbx
0x18023225d  jz      short loc_180232284
0x18023225f  mov     [rsp+168h+var_B0], rbx
0x180232267  mov     rcx, r14
0x18023226a  xchg    rcx, [rbx]
0x18023226d  cmp     rcx, 1
0x180232271  jnz     short loc_180232284
0x180232273  call    _Thrd_yield
0x180232278  mov     rax, r14
0x18023227b  xchg    rax, [rbx]
0x18023227e  cmp     rax, 1
0x180232282  jz      short loc_180232273
0x180232284  lea     rcx, [rsi+0B0h]
0x18023228b  mov     rax, [rcx]
0x18023228e  mov     [rsp+168h+arg_18], rax
0x180232296  test    rax, rax
0x180232299  jz      short loc_1802322A0
0x18023229b  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802322a0  test    r15b, r15b
0x1802322a3  jnz     short loc_180232314
0x1802322a5  mov     dword ptr [rsi+0D8h], 6E0h
0x1802322af  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x1802322b6  mov     [rsi+0E0h], rax
0x1802322bd  mov     [rsi+0E8h], r14
0x1802322c4  lea     rdx, aFailedToLoadPr; "Failed to load primary embedding model "...
0x1802322cb  lea     rcx, [rsi+0F0h]; this
0x1802322d2  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1802322d7  lea     rcx, [rsi+110h]; this
0x1802322de  mov     edx, 83EBAD1Dh; int
0x1802322e3  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x1802322e8  lea     r9, [rsi+0D8h]
0x1802322ef  lea     r8, [rsi+0F0h]
0x1802322f6  mov     edx, [rax]
0x1802322f8  lea     rcx, [rsp+168h+var_F8]
0x1802322fd  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180232302  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x180232309  lea     rcx, [rsp+168h+var_F8]; pExceptionObject
0x18023230e  call    _CxxThrowException
0x180232314  lea     rcx, [rsi+98h]
0x18023231b  mov     rax, [rcx]
0x18023231e  mov     [rsp+168h+arg_8], rax
0x180232326  test    rax, rax
0x180232329  jz      short loc_180232330
0x18023232b  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x180232330  test    dword ptr [rsi+88h], 2
0x18023233a  jz      loc_1802325E1
0x180232340  mov     [rsi+118h], r14
0x180232347  mov     r15, [rsi+80h]
0x18023234e  mov     r8b, 1
0x180232351  lea     rdx, [rsi+120h]
0x180232358  mov     rcx, r15
0x18023235b  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x180232360  mov     rbx, r14
0x180232363  mov     rax, [r15+0F0h]
0x18023236a  lea     rdx, [rax-10h]
0x18023236e  test    rax, rax
0x180232371  cmovz   rdx, r14
0x180232375  test    rdx, rdx
0x180232378  jz      short loc_1802323A6
0x18023237a  mov     rbx, rdx
0x18023237d  mov     rax, [rdx+8]
0x180232381  test    rax, rax
0x180232384  js      short loc_1802323A1
0x180232386  nop     word ptr [rax+rax+00000000h]
0x180232390  lea     rcx, [rax+1]
0x180232394  lock cmpxchg [rdx+8], rcx
0x18023239a  jz      short loc_1802323A6
0x18023239c  test    rax, rax
0x18023239f  jns     short loc_180232390
0x1802323a1  lock inc dword ptr [rax+rax+18h]
0x1802323a6  mov     [rsi+118h], rbx
0x1802323ad  movzx   eax, byte ptr [rsi+128h]
0x1802323b4  mov     [rsp+168h+var_118], al
0x1802323b8  test    al, al
0x1802323ba  jz      short loc_1802323CD
0x1802323bc  mov     rcx, [rsi+120h]; _Mtx_t
0x1802323c3  mov     [rsp+168h+var_120], rcx
0x1802323c8  call    _Mtx_unlock
0x1802323cd  lea     r8, [rsi+1E0h]
0x1802323d4  mov     byte ptr [rsi+200h], 0
0x1802323db  lea     r15, [rsi+130h]
0x1802323e2  mov     [rsp+168h+arg_10], rbx
0x1802323ea  mov     rdx, r15
0x1802323ed  mov     rcx, rbx
0x1802323f0  call    ?TryLoadCoreAsync@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?AU?$IAsyncOperation@_N@Foundation@Windows@8@V?$optional@UVectorSpaceResolutionOptions@TextEmbeddingsGenerator@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::TryLoadCoreAsync(std::optional<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator::VectorSpaceResolutionOptions>)
0x1802323f5  nop
0x1802323f6  mov     eax, [rsi+70h]
0x1802323f9  cmp     eax, 2
0x1802323fc  jnz     short loc_180232441
0x1802323fe  lea     rdx, [rsi+208h]; struct winrt::impl::slim_source_location *
0x180232405  mov     dword ptr [rdx], 1628h
0x18023240b  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180232412  mov     [rsi+210h], rax
0x180232419  mov     [rsi+218h], r14
0x180232420  lea     rcx, [rsp+168h+var_E0]; this
0x180232428  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023242d  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180232434  lea     rcx, [rsp+168h+var_E0]; pExceptionObject
0x18023243c  call    _CxxThrowException
0x180232441  lea     rcx, [rsi+138h]
0x180232448  mov     [rcx], r14
0x18023244b  mov     [rsi+140h], r15
0x180232452  mov     qword ptr [rsi+148h], 0
0x18023245d  mov     byte ptr [rsi+150h], 1
0x180232464  mov     eax, 6
0x180232469  mov     [rdi], ax
0x18023246c  mov     rdx, rsi
0x18023246f  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@UTextEmbeddingsGenerator@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@Uguid@4@_N@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator>,winrt::guid,bool>::promise_type>)
0x180232474  test    al, al
0x180232476  jz      short loc_1802324F0
0x180232478  jmp     loc_180232678
0x18023247d  mov     rbx, [rsi+138h]; jumptable 0000000180232083 case 7
0x180232484  test    rbx, rbx
0x180232487  jz      short loc_1802324B1
0x180232489  mov     [rsp+168h+var_90], rbx
0x180232491  xor     r14d, r14d
0x180232494  mov     eax, r14d
0x180232497  xchg    rax, [rbx]
0x18023249a  cmp     rax, 1
0x18023249e  jnz     short loc_1802324B1
0x1802324a0  call    _Thrd_yield
0x1802324a5  mov     rax, r14
0x1802324a8  xchg    rax, [rbx]
0x1802324ab  cmp     rax, 1
0x1802324af  jz      short loc_1802324A0
0x1802324b1  lea     rcx, [rsi+130h]
0x1802324b8  mov     rax, [rcx]
0x1802324bb  mov     [rsp+168h+var_140], rax
0x1802324c0  test    rax, rax
0x1802324c3  jz      short loc_1802324CB
0x1802324c5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802324ca  nop
0x1802324cb  lea     rcx, [rsi+118h]
0x1802324d2  mov     rax, [rcx]
0x1802324d5  mov     [rsp+168h+arg_10], rax
0x1802324dd  test    rax, rax
0x1802324e0  jz      short loc_1802324E8
0x1802324e2  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x1802324e7  nop
0x1802324e8  jmp     loc_180232612; jumptable 0000000180232083 cases -1,1
0x1802324ed  xor     r14d, r14d; jumptable 0000000180232083 case 6
0x1802324f0  lea     rcx, [rsi+138h]
0x1802324f7  call    ?await_resume@?$await_adapter@U?$IAsyncOperation@_N@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperation<bool>,1>::await_resume(void)
0x1802324fc  movzx   r15d, al
0x180232500  mov     rbx, [rsi+138h]
0x180232507  test    rbx, rbx
0x18023250a  jz      short loc_180232531
0x18023250c  mov     [rsp+168h+var_90], rbx
0x180232514  mov     rcx, r14
0x180232517  xchg    rcx, [rbx]
0x18023251a  cmp     rcx, 1
0x18023251e  jnz     short loc_180232531
0x180232520  call    _Thrd_yield
0x180232525  mov     rax, r14
0x180232528  xchg    rax, [rbx]
0x18023252b  cmp     rax, 1
0x18023252f  jz      short loc_180232520
0x180232531  lea     rcx, [rsi+130h]
0x180232538  mov     rax, [rcx]
0x18023253b  mov     [rsp+168h+var_140], rax
0x180232540  test    rax, rax
0x180232543  jz      short loc_18023254A
0x180232545  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023254a  test    r15b, r15b
0x18023254d  jnz     short loc_1802325C4
0x18023254f  mov     dword ptr [rsi+158h], 6F0h
0x180232559  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180232560  mov     [rsi+160h], rax
0x180232567  mov     [rsi+168h], r14
0x18023256e  lea     rdx, aFailedToLoadTe_1; "Failed to load text query embedding mod"...
0x180232575  lea     rcx, [rsi+170h]; this
0x18023257c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180232581  lea     rcx, [rsi+190h]; this
0x180232588  mov     edx, 83EBAD1Dh; int
0x18023258d  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180232592  lea     r9, [rsi+158h]
  ... truncated ...
```
