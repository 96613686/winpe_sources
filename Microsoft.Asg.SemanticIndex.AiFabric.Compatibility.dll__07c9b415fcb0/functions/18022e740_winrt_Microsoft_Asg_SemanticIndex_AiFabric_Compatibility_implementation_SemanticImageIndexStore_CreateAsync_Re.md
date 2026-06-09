# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateAsync$_ResumeCoro$1

- ea: `0x18022e740`
- end: `0x18022ee78`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateAsync$_ResumeCoro$1`
- size: `1848`
- prototype: `void __fastcall(char *Block)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001b8f0`
- `0x18022e730`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180003fb0`
- `0x180004510`
- `0x18000b2a0`
- `0x18000d230`
- `0x18001afb0`
- `0x18001b1f0`
- `0x18001b4a0`
- `0x18001fd20`
- `0x180020e60`
- `0x180047520`
- `0x1800475c0`
- `0x1801d1dd0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x18022e740`
- `0x180230600`
- `0x180242120`

## string_xrefs

- `0x18022e964`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022ec02`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18022e7e6`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`
- `0x18022e9b3`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::CreateAsync__ResumeCoro_1(
        char *Block)
{
  _WORD *v2; // rsi
  __int64 v3; // rcx
  unsigned int *v4; // rax
  char *v5; // rax
  __int64 *v6; // r15
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rdi
  volatile __int64 *v13; // rdi
  volatile __int64 *v14; // rdi
  __int64 v15; // r13
  __int64 v16; // r15
  _QWORD *v17; // rdi
  __int64 v18; // [rsp+20h] [rbp-178h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-148h] BYREF
  _BYTE v20[24]; // [rsp+68h] [rbp-130h] BYREF
  _BYTE v21[24]; // [rsp+80h] [rbp-118h] BYREF
  _BYTE v22[24]; // [rsp+98h] [rbp-100h] BYREF
  volatile __int64 *v23; // [rsp+B0h] [rbp-E8h]

  v2 = Block + 144;
  switch ( *((_WORD *)Block + 72) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_47;
    case 2:
      v3 = *((_QWORD *)Block + 17);
      if ( !v3 )
      {
        *((_DWORD *)Block + 38) = 98;
        *((_QWORD *)Block + 20) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticIm"
                                  "ageIndexStore.cpp";
        *((_QWORD *)Block + 21) = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)(Block + 176), L"options");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v21,
          (const struct winrt::param::hstring *)(Block + 176),
          (const struct winrt::impl::slim_source_location *)(Block + 152));
        throw (winrt::hresult_invalid_argument *)v21;
      }
      *((_QWORD *)Block + 26) = v3;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      if ( !(unsigned __int8)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::IsAvailableCore(Block + 208) )
      {
        *((_DWORD *)Block + 54) = 105;
        *((_QWORD *)Block + 28) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticIm"
                                  "ageIndexStore.cpp";
        *((_QWORD *)Block + 29) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(Block + 240),
          L"SemanticImageIndexStore models not yet available; call MakeAvailable first");
        v4 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(Block + 272), -2081706722);
        winrt::hresult_error::hresult_error(pExceptionObject, *v4, Block + 240, Block + 216);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v5 = (char *)operator new(0xA0u);
      *(_OWORD *)v5 = 0;
      *(_OWORD *)(v5 + 120) = 0;
      *(_OWORD *)(v5 + 136) = 0;
      *((_QWORD *)v5 + 19) = 0;
      *((_QWORD *)v5 + 2) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStore>::`vftable';
      *((_QWORD *)v5 + 3) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStore2>::`vftable';
      *((_QWORD *)v5 + 4) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IClosable>::`vftable';
      *((_QWORD *)v5 + 5) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>::`vftable';
      *((_QWORD *)v5 + 6) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex>::`vftable';
      *((_QWORD *)v5 + 7) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex2>::`vftable';
      *((_QWORD *)v5 + 8) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex2>::`vftable';
      *((_QWORD *)v5 + 9) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>::`vftable';
      *((_QWORD *)v5 + 10) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex3>::`vftable';
      *((_QWORD *)v5 + 11) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex4>::`vftable';
      *((_QWORD *)v5 + 12) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex4>::`vftable';
      *((_QWORD *)v5 + 13) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>::`vftable';
      *((_QWORD *)v5 + 14) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex5>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v5 + 1) = 1;
      *((_QWORD *)v5 + 16) = 0;
      *((_QWORD *)v5 + 17) = 0;
      *((_DWORD *)v5 + 36) = 1000;
      *(_QWORD *)v5 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>::`vftable';
      *((_QWORD *)Block + 46) = v5;
      *((_QWORD *)Block + 35) = v5;
      Block[288] = 0;
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 94) = 5672;
        *((_QWORD *)Block + 48) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 49) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v20,
          (const struct winrt::impl::slim_source_location *)(Block + 376));
        throw (winrt::hresult_canceled *)v20;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(
        &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>::`vftable',
        Block);
      return;
    case 4:
      v6 = (__int64 *)(Block + 304);
      v7 = *((_QWORD *)Block + 17);
      *((_QWORD *)Block + 38) = v7;
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      *((_QWORD *)Block + 37) = v6;
      v8 = operator new(0x770u);
      *((_QWORD *)Block + 50) = v8;
      v8[1] = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::InitializeAsync__DestroyCoro_2;
      **((_QWORD **)Block + 50) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::InitializeAsync__ResumeCoro_1;
      v9 = *((_QWORD *)Block + 50);
      *(_QWORD *)(v9 + 128) = *((_QWORD *)Block + 46);
      v10 = *v6;
      *v6 = 0;
      *(_QWORD *)(v9 + 136) = v10;
      *(_DWORD *)(*((_QWORD *)Block + 50) + 144LL) = 65538;
      v11 = *((_QWORD *)Block + 50);
      *(_OWORD *)(v11 + 16) = 0;
      *(_OWORD *)(v11 + 32) = 0;
      *(_OWORD *)(v11 + 48) = 0;
      *(_OWORD *)(v11 + 64) = 0;
      *(_OWORD *)(v11 + 80) = 0;
      *(_OWORD *)(v11 + 96) = 0;
      *(_QWORD *)(v11 + 112) = 0;
      v12 = *((_QWORD *)Block + 50);
      *(_QWORD *)(v12 + 32) = &winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
      *(_QWORD *)(v12 + 40) = &winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)(v12 + 24) = 1;
      *(_QWORD *)(v12 + 48) = 0;
      *(_QWORD *)(v12 + 56) = 0;
      *(_BYTE *)(v12 + 64) = 0;
      *(_QWORD *)(v12 + 16) = &winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
      *(_QWORD *)(v12 + 72) = 0;
      *(_QWORD *)(v12 + 80) = 0;
      __ExceptionPtrCreate((void *)(v12 + 72));
      *(_QWORD *)(v12 + 88) = 0;
      *(_QWORD *)(v12 + 96) = 0;
      *(_QWORD *)(v12 + 104) = 0;
      *(_DWORD *)(v12 + 112) = 0;
      *(_BYTE *)(v12 + 116) = 0;
      *(_QWORD *)(v12 + 16) = &std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type::`vftable';
      v18 = *((_QWORD *)Block + 50);
      *((_QWORD *)Block + 39) = v18 + 32;
      if ( v18 != -32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v18 + 32) + 8LL))(v18 + 32);
      *(_BYTE *)(*((_QWORD *)Block + 50) + 120LL) = 0;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::InitializeAsync__ResumeCoro_1(*((void **)Block + 50));
      if ( *v6 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 304);
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 588) = 5672;
        *((_QWORD *)Block + 295) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 296) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v22,
          (const struct winrt::impl::slim_source_location *)(Block + 2352));
        throw (winrt::hresult_canceled *)v22;
      }
      *((_QWORD *)Block + 40) = 0;
      *((_QWORD *)Block + 41) = Block + 312;
      *((_QWORD *)Block + 42) = 0;
      Block[344] = 1;
      *v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>(
                              Block + 320,
                              Block) )
        return;
      goto LABEL_32;
    case 5:
      if ( *((_QWORD *)Block + 46) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      goto LABEL_47;
    case 6:
LABEL_32:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(Block + 320);
      if ( *((_QWORD *)Block + 40) )
      {
        v14 = (volatile __int64 *)*((_QWORD *)Block + 40);
        v23 = v14;
        while ( _InterlockedExchange64(v14, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 39) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 312);
      v15 = *((_QWORD *)Block + 46);
      v16 = v15 + 16;
      v17 = Block + 120;
      if ( Block + 120 != Block + 352 )
      {
        if ( *v17 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 120);
        *v17 = v16;
        if ( v15 != -16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v15 + 16);
      }
      if ( v15 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)Block + 45) = Block + 16;
      *v2 = 0;
      *(_QWORD *)Block = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(Block + 360) )
        goto LABEL_47;
      return;
    case 7:
      if ( *((_QWORD *)Block + 40) )
      {
        v13 = (volatile __int64 *)*((_QWORD *)Block + 40);
        v23 = v13;
        while ( _InterlockedExchange64(v13, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 39) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 312);
      if ( *((_QWORD *)Block + 46) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_47:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(Block + 16);
      if ( *((_QWORD *)Block + 17) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 136);
      if ( *((_WORD *)Block + 73) )
        operator delete(Block);
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18022e740  mov     rax, rsp
0x18022e743  mov     [rax+10h], rbx
0x18022e747  mov     [rax+18h], rsi
0x18022e74b  mov     [rax+20h], rdi
0x18022e74f  mov     [rax+8], rcx
0x18022e753  push    r13
0x18022e755  push    r14
0x18022e757  push    r15
0x18022e759  sub     rsp, 180h
0x18022e760  mov     rbx, rcx
0x18022e763  mov     [rsp+198h+var_160], rcx
0x18022e768  lea     rsi, [rbx+90h]
0x18022e76f  mov     [rsp+198h+var_158], rsi
0x18022e774  movzx   eax, word ptr [rsi]
0x18022e777  mov     [rsp+198h+var_168], ax
0x18022e77c  inc     ax; switch 9 cases
0x18022e77f  cmp     ax, 8
0x18022e783  ja      def_18022E79E; jumptable 000000018022E79E default case, case 0
0x18022e789  movsx   rax, ax
0x18022e78d  lea     rdx, cs:180000000h
0x18022e794  mov     ecx, ds:(jpt_18022E79E - 180000000h)[rdx+rax*4]
0x18022e79b  add     rcx, rdx
0x18022e79e  jmp     rcx; switch jump
0x18022e7a0  jmp     loc_18022EE00; jumptable 000000018022E79E case 3
0x18022e7a5  xor     r14d, r14d; jumptable 000000018022E79E case 2
0x18022e7a8  mov     rcx, [rbx+88h]
0x18022e7af  test    rcx, rcx
0x18022e7b2  jz      loc_18022E9A9
0x18022e7b8  mov     [rbx+0D0h], rcx
0x18022e7bf  mov     rax, [rcx]
0x18022e7c2  mov     rax, [rax+8]
0x18022e7c6  call    cs:__guard_dispatch_icall_fptr
0x18022e7cc  lea     rcx, [rbx+0D0h]
0x18022e7d3  call    ?IsAvailableCore@SemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@CA_NUSemanticImageIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::IsAvailableCore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x18022e7d8  test    al, al
0x18022e7da  jnz     short loc_18022E84A
0x18022e7dc  mov     dword ptr [rbx+0D8h], 69h ; 'i'
0x18022e7e6  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022e7ed  mov     [rbx+0E0h], rax
0x18022e7f4  mov     [rbx+0E8h], r14
0x18022e7fb  lea     rdx, aSemanticimagei; "SemanticImageIndexStore models not yet "...
0x18022e802  lea     rcx, [rbx+0F0h]; this
0x18022e809  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022e80e  lea     rcx, [rbx+110h]; this
0x18022e815  mov     edx, 83EBAD1Eh; int
0x18022e81a  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x18022e81f  lea     r9, [rbx+0D8h]
0x18022e826  lea     r8, [rbx+0F0h]
0x18022e82d  mov     edx, [rax]
0x18022e82f  lea     rcx, [rsp+198h+pExceptionObject]
0x18022e834  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022e839  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18022e840  lea     rcx, [rsp+198h+pExceptionObject]; pExceptionObject
0x18022e845  call    _CxxThrowException
0x18022e84a  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022e851  mov     ecx, 0A0h; Size
0x18022e856  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022e85b  xorps   xmm0, xmm0
0x18022e85e  movaps  xmmword ptr [rax], xmm0
0x18022e861  xorps   xmm1, xmm1
0x18022e864  xor     ecx, ecx
0x18022e866  movups  xmmword ptr [rax+78h], xmm1
0x18022e86a  movups  xmmword ptr [rax+88h], xmm1
0x18022e871  mov     [rax+98h], rcx
0x18022e878  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStore@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStore>::`vftable'
0x18022e87f  mov     [rax+10h], rcx
0x18022e883  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStore2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStore2>::`vftable'
0x18022e88a  mov     [rax+18h], rcx
0x18022e88e  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIClosable@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Windows::Foundation::IClosable>::`vftable'
0x18022e895  mov     [rax+20h], rcx
0x18022e899  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>::`vftable'
0x18022e8a0  mov     [rax+28h], rcx
0x18022e8a4  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndex@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex>::`vftable'
0x18022e8ab  mov     [rax+30h], rcx
0x18022e8af  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex2>::`vftable'
0x18022e8b6  mov     [rax+38h], rcx
0x18022e8ba  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndex2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex2>::`vftable'
0x18022e8c1  mov     [rax+40h], rcx
0x18022e8c5  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>::`vftable'
0x18022e8cc  mov     [rax+48h], rcx
0x18022e8d0  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndex3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex3>::`vftable'
0x18022e8d7  mov     [rax+50h], rcx
0x18022e8db  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex4@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex4>::`vftable'
0x18022e8e2  mov     [rax+58h], rcx
0x18022e8e6  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndex4@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex4>::`vftable'
0x18022e8ed  mov     [rax+60h], rcx
0x18022e8f1  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex5@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>::`vftable'
0x18022e8f8  mov     [rax+68h], rcx
0x18022e8fc  lea     rcx, ??_7?$produce@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndex5@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndex5>::`vftable'
0x18022e903  mov     [rax+70h], rcx
0x18022e907  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022e90e  mov     qword ptr [rax+8], 1
0x18022e916  mov     [rax+80h], r14
0x18022e91d  xor     ecx, ecx
0x18022e91f  mov     [rax+88h], rcx
0x18022e926  mov     dword ptr [rax+90h], 3E8h
0x18022e930  lea     rcx, ??_7?$heap_implements@USemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore>::`vftable'
0x18022e937  mov     [rax], rcx
0x18022e93a  mov     [rbx+170h], rax
0x18022e941  mov     [rbx+118h], rax
0x18022e948  mov     byte ptr [rbx+120h], 0
0x18022e94f  mov     eax, [rbx+70h]
0x18022e952  cmp     eax, 2
0x18022e955  jnz     short loc_18022E994
0x18022e957  lea     rdx, [rbx+178h]; struct winrt::impl::slim_source_location *
0x18022e95e  mov     dword ptr [rdx], 1628h
0x18022e964  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022e96b  mov     [rbx+180h], rax
0x18022e972  mov     [rbx+188h], r14
0x18022e979  lea     rcx, [rsp+198h+var_130]; this
0x18022e97e  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022e983  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022e98a  lea     rcx, [rsp+198h+var_130]; pExceptionObject
0x18022e98f  call    _CxxThrowException
0x18022e994  mov     eax, 4
0x18022e999  mov     [rsi], ax
0x18022e99c  mov     rdx, rbx
0x18022e99f  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x18022e9a4  jmp     loc_18022EE35
0x18022e9a9  mov     dword ptr [rbx+98h], 62h ; 'b'
0x18022e9b3  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18022e9ba  mov     [rbx+0A0h], rax
0x18022e9c1  mov     [rbx+0A8h], r14
0x18022e9c8  lea     rdx, aOptions; "options"
0x18022e9cf  lea     rcx, [rbx+0B0h]; this
0x18022e9d6  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18022e9db  lea     r8, [rbx+98h]; struct winrt::impl::slim_source_location *
0x18022e9e2  lea     rdx, [rbx+0B0h]; struct winrt::param::hstring *
0x18022e9e9  lea     rcx, [rsp+198h+var_118]; this
0x18022e9f1  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18022e9f6  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18022e9fd  lea     rcx, [rsp+198h+var_118]; pExceptionObject
0x18022ea05  call    _CxxThrowException
0x18022ea0b  cmp     qword ptr [rbx+170h], 0; jumptable 000000018022E79E case 5
0x18022ea13  jz      short loc_18022EA22
0x18022ea15  lea     rcx, [rbx+118h]
0x18022ea1c  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022ea21  nop
0x18022ea22  mov     eax, 0FFFFFFFFh
0x18022ea27  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022ea2f  sub     eax, 1
0x18022ea32  jz      short loc_18022EA3E
0x18022ea34  test    eax, eax
0x18022ea36  jns     short loc_18022EA3E
0x18022ea38  call    abort
0x18022ea3e  jmp     loc_18022EE00; jumptable 000000018022E79E cases -1,1
0x18022ea43  lea     r15, [rbx+130h]; jumptable 000000018022E79E case 4
0x18022ea4a  mov     rcx, [rbx+88h]
0x18022ea51  mov     [r15], rcx
0x18022ea54  test    rcx, rcx
0x18022ea57  jz      short loc_18022EA66
0x18022ea59  mov     rax, [rcx]
0x18022ea5c  mov     rax, [rax+8]
0x18022ea60  call    cs:__guard_dispatch_icall_fptr
0x18022ea66  mov     [rbx+128h], r15
0x18022ea6d  mov     ecx, 770h; Size
0x18022ea72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18022ea77  mov     [rbx+190h], rax
0x18022ea7e  mov     [rsp+198h+var_178], rax
0x18022ea83  lea     rcx, winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__InitializeAsync$_DestroyCoro$2
0x18022ea8a  mov     [rax+8], rcx
0x18022ea8e  mov     rax, [rbx+190h]
0x18022ea95  mov     [rsp+198h+var_178], rax
0x18022ea9a  lea     rcx, winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__InitializeAsync$_ResumeCoro$1
0x18022eaa1  mov     [rax], rcx
0x18022eaa4  mov     rcx, [rbx+190h]
0x18022eaab  mov     [rsp+198h+var_178], rcx
0x18022eab0  mov     rax, [rbx+170h]
0x18022eab7  mov     [rcx+80h], rax
0x18022eabe  mov     rax, [r15]
0x18022eac1  xor     r14d, r14d
0x18022eac4  mov     [r15], r14
0x18022eac7  mov     [rcx+88h], rax
0x18022eace  mov     rax, [rbx+190h]
0x18022ead5  mov     [rsp+198h+var_178], rax
0x18022eada  mov     dword ptr [rax+90h], 10002h
0x18022eae4  mov     rax, [rbx+190h]
0x18022eaeb  mov     [rsp+198h+var_178], rax
0x18022eaf0  xorps   xmm0, xmm0
0x18022eaf3  xor     ecx, ecx
0x18022eaf5  movups  xmmword ptr [rax+10h], xmm0
0x18022eaf9  movups  xmmword ptr [rax+20h], xmm0
0x18022eafd  movups  xmmword ptr [rax+30h], xmm0
0x18022eb01  movups  xmmword ptr [rax+40h], xmm0
0x18022eb05  movups  xmmword ptr [rax+50h], xmm0
0x18022eb09  movups  xmmword ptr [rax+60h], xmm0
0x18022eb0d  mov     [rax+70h], rcx
0x18022eb11  mov     rdi, [rbx+190h]
0x18022eb18  mov     [rsp+198h+var_178], rdi
0x18022eb1d  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticImageIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x18022eb24  mov     [rdi+20h], rax
0x18022eb28  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticImageIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x18022eb2f  mov     [rdi+28h], rax
0x18022eb33  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022eb3a  mov     qword ptr [rdi+18h], 1
0x18022eb42  mov     [rdi+30h], r14
0x18022eb46  mov     [rdi+38h], r14
0x18022eb4a  mov     [rdi+40h], cl
0x18022eb4d  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticImageIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x18022eb54  mov     [rdi+10h], rax
0x18022eb58  lea     rcx, [rdi+48h]; void *
0x18022eb5c  mov     [rcx], r14
0x18022eb5f  mov     [rcx+8], r14
0x18022eb63  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x18022eb68  mov     [rdi+58h], r14
0x18022eb6c  mov     [rdi+60h], r14
0x18022eb70  mov     [rdi+68h], r14
0x18022eb74  xor     eax, eax
0x18022eb76  mov     [rdi+70h], eax
0x18022eb79  mov     [rdi+74h], al
0x18022eb7c  lea     rax, ??_7promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticImageIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticImageIndexStoreOptions@789Asg@Microsoft@4@@std@@6B@; const std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type::`vftable'
0x18022eb83  mov     [rdi+10h], rax
0x18022eb87  mov     rax, [rbx+190h]
0x18022eb8e  mov     [rsp+198h+var_178], rax
0x18022eb93  lea     rcx, [rax+20h]
0x18022eb97  lea     rdi, [rbx+138h]
0x18022eb9e  mov     [rdi], rcx
0x18022eba1  test    rcx, rcx
0x18022eba4  jz      short loc_18022EBB4
0x18022eba6  mov     rax, [rcx]
0x18022eba9  mov     rax, [rax+8]
0x18022ebad  call    cs:__guard_dispatch_icall_fptr
0x18022ebb3  nop
0x18022ebb4  mov     rax, [rbx+190h]
0x18022ebbb  mov     [rsp+198h+var_178], rax
0x18022ebc0  xor     ecx, ecx
0x18022ebc2  mov     [rax+78h], cl
0x18022ebc5  mov     rcx, [rbx+190h]; Block
0x18022ebcc  mov     [rsp+198h+var_178], rcx
0x18022ebd1  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticImageIndexStore__InitializeAsync$_ResumeCoro$1
0x18022ebd6  nop
0x18022ebd7  mov     rax, [r15]
0x18022ebda  mov     [rsp+198h+var_150], rax
0x18022ebdf  test    rax, rax
0x18022ebe2  jz      short loc_18022EBED
0x18022ebe4  mov     rcx, r15
0x18022ebe7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022ebec  nop
0x18022ebed  mov     eax, [rbx+70h]
0x18022ebf0  cmp     eax, 2
0x18022ebf3  jnz     short loc_18022EC38
0x18022ebf5  lea     rdx, [rbx+930h]; struct winrt::impl::slim_source_location *
0x18022ebfc  mov     dword ptr [rdx], 1628h
0x18022ec02  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18022ec09  mov     [rbx+938h], rax
0x18022ec10  mov     [rbx+940h], r14
0x18022ec17  lea     rcx, [rsp+198h+var_100]; this
0x18022ec1f  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18022ec24  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18022ec2b  lea     rcx, [rsp+198h+var_100]; pExceptionObject
0x18022ec33  call    _CxxThrowException
0x18022ec38  lea     rcx, [rbx+140h]
0x18022ec3f  mov     [rcx], r14
0x18022ec42  mov     [rbx+148h], rdi
0x18022ec49  mov     [rbx+150h], r14
0x18022ec50  mov     byte ptr [rbx+158h], 1
0x18022ec57  mov     eax, 6
0x18022ec5c  mov     [rsi], ax
0x18022ec5f  mov     rdx, rbx
0x18022ec62  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>)
0x18022ec67  test    al, al
0x18022ec69  jz      loc_18022ED06
0x18022ec6f  jmp     loc_18022EE35
0x18022ec74  cmp     qword ptr [rbx+140h], 0; jumptable 000000018022E79E case 7
0x18022ec7c  jz      short loc_18022ECB1
0x18022ec7e  mov     rdi, [rbx+140h]
0x18022ec85  mov     rcx, rdi
0x18022ec88  mov     [rsp+198h+var_E8], rcx
0x18022ec90  xor     r14d, r14d
0x18022ec93  mov     eax, r14d
0x18022ec96  xchg    rax, [rcx]
0x18022ec99  cmp     rax, 1
0x18022ec9d  jnz     short loc_18022ECB1
0x18022ec9f  nop
0x18022eca0  call    _Thrd_yield
0x18022eca5  mov     rax, r14
0x18022eca8  xchg    rax, [rdi]
0x18022ecab  cmp     rax, 1
0x18022ecaf  jz      short loc_18022ECA0
0x18022ecb1  lea     rcx, [rbx+138h]
0x18022ecb8  mov     rax, [rcx]
0x18022ecbb  mov     [rsp+198h+var_170], rax
0x18022ecc0  test    rax, rax
0x18022ecc3  jz      short loc_18022ECCB
0x18022ecc5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18022ecca  nop
0x18022eccb  cmp     qword ptr [rbx+170h], 0
0x18022ecd3  jz      short loc_18022ECE2
0x18022ecd5  lea     rcx, [rbx+118h]
0x18022ecdc  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18022ece1  nop
0x18022ece2  mov     eax, 0FFFFFFFFh
0x18022ece7  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18022ecef  sub     eax, 1
0x18022ecf2  jz      short loc_18022ECFE
0x18022ecf4  test    eax, eax
0x18022ecf6  jns     short loc_18022ECFE
0x18022ecf8  call    abort
0x18022ecfe  jmp     loc_18022EE00; jumptable 000000018022E79E cases -1,1
0x18022ed03  xor     r14d, r14d; jumptable 000000018022E79E case 6
  ... truncated ...
```
