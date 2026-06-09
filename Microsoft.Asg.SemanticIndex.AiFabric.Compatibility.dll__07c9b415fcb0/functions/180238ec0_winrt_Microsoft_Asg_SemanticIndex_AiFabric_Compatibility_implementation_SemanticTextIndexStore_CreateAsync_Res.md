# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateAsync$_ResumeCoro$1

- ea: `0x180238ec0`
- end: `0x180239648`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateAsync$_ResumeCoro$1`
- size: `1928`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18004aa50`
- `0x180238eb0`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180003fb0`
- `0x180004510`
- `0x18000b2a0`
- `0x18000d230`
- `0x18001afb0`
- `0x18001b1f0`
- `0x18001fd20`
- `0x180020e60`
- `0x180047520`
- `0x1800475c0`
- `0x18004ab90`
- `0x1801d1dd0`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f7190`
- `0x1801f97e0`
- `0x180206a58`
- `0x180238ec0`
- `0x18023a270`
- `0x180242120`

## string_xrefs

- `0x180239131`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802393cf`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180238fb3`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`
- `0x180239180`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::CreateAsync__ResumeCoro_1(
        char *Block)
{
  _WORD *v2; // rsi
  __int64 v3; // rcx
  _QWORD *v4; // rdi
  __int64 v5; // rax
  char IsEmbeddingsGeneratorAvailableForOptionsCore; // r15
  unsigned int *v7; // rax
  char *v8; // rax
  __int64 *v9; // r15
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rdi
  volatile __int64 *v16; // rdi
  volatile __int64 *v17; // rdi
  __int64 v18; // r13
  __int64 v19; // r15
  _QWORD *v20; // rdi
  __int64 v21; // [rsp+20h] [rbp-188h]
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-158h] BYREF
  _BYTE v23[24]; // [rsp+68h] [rbp-140h] BYREF
  _BYTE v24[24]; // [rsp+80h] [rbp-128h] BYREF
  _BYTE v25[24]; // [rsp+98h] [rbp-110h] BYREF
  volatile __int64 *v26; // [rsp+B0h] [rbp-F8h]

  v2 = Block + 144;
  switch ( *((_WORD *)Block + 72) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_53;
    case 2:
      v3 = *((_QWORD *)Block + 17);
      if ( !v3 )
      {
        *((_DWORD *)Block + 38) = 74;
        *((_QWORD *)Block + 20) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
        *((_QWORD *)Block + 21) = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)(Block + 176), L"options");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v24,
          (const struct winrt::param::hstring *)(Block + 176),
          (const struct winrt::impl::slim_source_location *)(Block + 152));
        throw (winrt::hresult_invalid_argument *)v24;
      }
      v4 = Block + 208;
      *((_QWORD *)Block + 26) = v3;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
      *((_QWORD *)Block + 46) = Block + 208;
      v5 = *((_QWORD *)Block + 26);
      *((_QWORD *)Block + 47) = v5;
      if ( v5 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v5 + 8LL))(*v4);
      IsEmbeddingsGeneratorAvailableForOptionsCore = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailableForOptionsCore(Block + 376);
      if ( *v4 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 208);
      if ( !IsEmbeddingsGeneratorAvailableForOptionsCore )
      {
        *((_DWORD *)Block + 54) = 81;
        *((_QWORD *)Block + 28) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
        *((_QWORD *)Block + 29) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(Block + 240),
          L"SemanticTextIndexStore models not yet available; call MakeAvailable first");
        v7 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)(Block + 272), -2081706722);
        winrt::hresult_error::hresult_error(pExceptionObject, *v7, Block + 240, Block + 216);
        throw (winrt::hresult_error *)pExceptionObject;
      }
      v8 = (char *)operator new(0xA0u);
      *(_OWORD *)v8 = 0;
      *(_OWORD *)(v8 + 120) = 0;
      *(_OWORD *)(v8 + 136) = 0;
      *((_QWORD *)v8 + 19) = 0;
      *((_QWORD *)v8 + 2) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStore>::`vftable';
      *((_QWORD *)v8 + 3) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStore2>::`vftable';
      *((_QWORD *)v8 + 4) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Windows::Foundation::IClosable>::`vftable';
      *((_QWORD *)v8 + 5) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>::`vftable';
      *((_QWORD *)v8 + 6) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex>::`vftable';
      *((_QWORD *)v8 + 7) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex2>::`vftable';
      *((_QWORD *)v8 + 8) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex2>::`vftable';
      *((_QWORD *)v8 + 9) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>::`vftable';
      *((_QWORD *)v8 + 10) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex3>::`vftable';
      *((_QWORD *)v8 + 11) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex4>::`vftable';
      *((_QWORD *)v8 + 12) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex4>::`vftable';
      *((_QWORD *)v8 + 13) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>::`vftable';
      *((_QWORD *)v8 + 14) = &winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex5>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_QWORD *)v8 + 1) = 1;
      *((_QWORD *)v8 + 16) = 0;
      *((_QWORD *)v8 + 17) = 0;
      *((_DWORD *)v8 + 36) = 1000;
      *(_QWORD *)v8 = &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>::`vftable';
      *((_QWORD *)Block + 48) = v8;
      *((_QWORD *)Block + 35) = v8;
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      Block[289] = 0;
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 98) = 5672;
        *((_QWORD *)Block + 50) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 51) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v23,
          (const struct winrt::impl::slim_source_location *)(Block + 392));
        throw (winrt::hresult_canceled *)v23;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(
        &winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>::`vftable',
        Block);
      return;
    case 4:
      v9 = (__int64 *)(Block + 304);
      v10 = *((_QWORD *)Block + 17);
      *((_QWORD *)Block + 38) = v10;
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
      *((_QWORD *)Block + 37) = v9;
      v11 = operator new(0x6F0u);
      *((_QWORD *)Block + 52) = v11;
      v11[1] = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync__DestroyCoro_2;
      **((_QWORD **)Block + 52) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync__ResumeCoro_1;
      v12 = *((_QWORD *)Block + 52);
      *(_QWORD *)(v12 + 128) = *((_QWORD *)Block + 48);
      v13 = *v9;
      *v9 = 0;
      *(_QWORD *)(v12 + 136) = v13;
      *(_DWORD *)(*((_QWORD *)Block + 52) + 144LL) = 65538;
      v14 = *((_QWORD *)Block + 52);
      *(_OWORD *)(v14 + 16) = 0;
      *(_OWORD *)(v14 + 32) = 0;
      *(_OWORD *)(v14 + 48) = 0;
      *(_OWORD *)(v14 + 64) = 0;
      *(_OWORD *)(v14 + 80) = 0;
      *(_OWORD *)(v14 + 96) = 0;
      *(_QWORD *)(v14 + 112) = 0;
      v15 = *((_QWORD *)Block + 52);
      *(_QWORD *)(v15 + 32) = &winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable';
      *(_QWORD *)(v15 + 40) = &winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *(_QWORD *)(v15 + 24) = 1;
      *(_QWORD *)(v15 + 48) = 0;
      *(_QWORD *)(v15 + 56) = 0;
      *(_BYTE *)(v15 + 64) = 0;
      *(_QWORD *)(v15 + 16) = &winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable';
      *(_QWORD *)(v15 + 72) = 0;
      *(_QWORD *)(v15 + 80) = 0;
      __ExceptionPtrCreate((void *)(v15 + 72));
      *(_QWORD *)(v15 + 88) = 0;
      *(_QWORD *)(v15 + 96) = 0;
      *(_QWORD *)(v15 + 104) = 0;
      *(_DWORD *)(v15 + 112) = 0;
      *(_BYTE *)(v15 + 116) = 0;
      *(_QWORD *)(v15 + 16) = &std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::`vftable';
      v21 = *((_QWORD *)Block + 52);
      *((_QWORD *)Block + 39) = v21 + 32;
      if ( v21 != -32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(v21 + 32) + 8LL))(v21 + 32);
      *(_BYTE *)(*((_QWORD *)Block + 52) + 120LL) = 0;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::InitializeAsync__ResumeCoro_1(*((char **)Block + 52));
      if ( *v9 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 304);
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 560) = 5672;
        *((_QWORD *)Block + 281) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gene"
                                   "rated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 282) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)v25,
          (const struct winrt::impl::slim_source_location *)(Block + 2240));
        throw (winrt::hresult_canceled *)v25;
      }
      *((_QWORD *)Block + 40) = 0;
      *((_QWORD *)Block + 41) = Block + 312;
      *((_QWORD *)Block + 42) = 0;
      Block[344] = 1;
      *v2 = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>(
                              (_QWORD *)Block + 40,
                              (__int64)Block) )
        return;
      goto LABEL_38;
    case 5:
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *((_QWORD *)Block + 48) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
      goto LABEL_53;
    case 6:
LABEL_38:
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_resume(Block + 320);
      if ( *((_QWORD *)Block + 40) )
      {
        v17 = (volatile __int64 *)*((_QWORD *)Block + 40);
        v26 = v17;
        while ( _InterlockedExchange64(v17, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 39) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 312);
      v18 = *((_QWORD *)Block + 48);
      v19 = v18 + 16;
      v20 = Block + 120;
      if ( Block + 120 != Block + 352 )
      {
        if ( *v20 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 120);
        *v20 = v19;
        if ( v18 != -16 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v18 + 16);
      }
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( v18 )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
      *((_QWORD *)Block + 45) = Block + 16;
      *v2 = 0;
      *(_QWORD *)Block = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryEmbeddings const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticQueryOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::QueryResult>,void>::final_suspend_awaiter::await_suspend(Block + 360) )
        goto LABEL_53;
      return;
    case 7:
      if ( *((_QWORD *)Block + 40) )
      {
        v16 = (volatile __int64 *)*((_QWORD *)Block + 40);
        v26 = v16;
        while ( _InterlockedExchange64(v16, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 39) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 312);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      if ( *((_QWORD *)Block + 48) )
        winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(Block + 280);
LABEL_53:
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
0x180238ec0  mov     rax, rsp
0x180238ec3  mov     [rax+10h], rbx
0x180238ec7  mov     [rax+18h], rsi
0x180238ecb  mov     [rax+20h], rdi
0x180238ecf  mov     [rax+8], rcx
0x180238ed3  push    r13
0x180238ed5  push    r14
0x180238ed7  push    r15
0x180238ed9  sub     rsp, 190h
0x180238ee0  mov     rbx, rcx
0x180238ee3  mov     [rsp+1A8h+var_170], rcx
0x180238ee8  lea     rsi, [rbx+90h]
0x180238eef  mov     [rsp+1A8h+var_168], rsi
0x180238ef4  movzx   eax, word ptr [rsi]
0x180238ef7  mov     [rsp+1A8h+var_178], ax
0x180238efc  inc     ax; switch 9 cases
0x180238eff  cmp     ax, 8
0x180238f03  ja      def_180238F1E; jumptable 0000000180238F1E default case, case 0
0x180238f09  movsx   rax, ax
0x180238f0d  lea     rdx, cs:180000000h
0x180238f14  mov     ecx, ds:(jpt_180238F1E - 180000000h)[rdx+rax*4]
0x180238f1b  add     rcx, rdx
0x180238f1e  jmp     rcx; switch jump
0x180238f20  jmp     loc_1802395D0; jumptable 0000000180238F1E case 3
0x180238f25  xor     r14d, r14d; jumptable 0000000180238F1E case 2
0x180238f28  mov     rcx, [rbx+88h]
0x180238f2f  test    rcx, rcx
0x180238f32  jz      loc_180239176
0x180238f38  lea     rdi, [rbx+0D0h]
0x180238f3f  mov     [rdi], rcx
0x180238f42  mov     rax, [rcx]
0x180238f45  mov     rax, [rax+8]
0x180238f49  call    cs:__guard_dispatch_icall_fptr
0x180238f4f  mov     [rbx+170h], rdi
0x180238f56  mov     rax, [rdi]
0x180238f59  mov     [rbx+178h], rax
0x180238f60  cmp     rax, r14
0x180238f63  jz      short loc_180238F7F
0x180238f65  mov     [rsp+1A8h+var_188], rax
0x180238f6a  mov     rdx, [rax]
0x180238f6d  mov     rcx, [rdi]
0x180238f70  mov     [rsp+1A8h+var_188], rcx
0x180238f75  mov     rax, [rdx+8]
0x180238f79  call    cs:__guard_dispatch_icall_fptr
0x180238f7f  lea     rcx, [rbx+178h]
0x180238f86  call    ?IsEmbeddingsGeneratorAvailableForOptionsCore@SemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@CA_NUSemanticTextIndexStoreOptions@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailableForOptionsCore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x180238f8b  movzx   r15d, al
0x180238f8f  mov     rdx, [rdi]
0x180238f92  mov     [rsp+1A8h+var_188], rdx
0x180238f97  test    rdx, rdx
0x180238f9a  jz      short loc_180238FA4
0x180238f9c  mov     rcx, rdi
0x180238f9f  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180238fa4  test    r15b, r15b
0x180238fa7  jnz     short loc_180239017
0x180238fa9  mov     dword ptr [rbx+0D8h], 51h ; 'Q'
0x180238fb3  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180238fba  mov     [rbx+0E0h], rax
0x180238fc1  mov     [rbx+0E8h], r14
0x180238fc8  lea     rdx, aSemantictextin; "SemanticTextIndexStore models not yet a"...
0x180238fcf  lea     rcx, [rbx+0F0h]; this
0x180238fd6  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180238fdb  lea     rcx, [rbx+110h]; this
0x180238fe2  mov     edx, 83EBAD1Eh; int
0x180238fe7  call    ??0hresult@winrt@@QEAA@H@Z; winrt::hresult::hresult(int)
0x180238fec  lea     r9, [rbx+0D8h]
0x180238ff3  lea     r8, [rbx+0F0h]
0x180238ffa  mov     edx, [rax]
0x180238ffc  lea     rcx, [rsp+1A8h+pExceptionObject]
0x180239001  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180239006  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x18023900d  lea     rcx, [rsp+1A8h+pExceptionObject]; pExceptionObject
0x180239012  call    _CxxThrowException
0x180239017  mov     ecx, 0A0h; Size
0x18023901c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180239021  xorps   xmm0, xmm0
0x180239024  movaps  xmmword ptr [rax], xmm0
0x180239027  xorps   xmm1, xmm1
0x18023902a  xor     ecx, ecx
0x18023902c  movups  xmmword ptr [rax+78h], xmm1
0x180239030  movups  xmmword ptr [rax+88h], xmm1
0x180239037  mov     [rax+98h], rcx
0x18023903e  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStore@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStore>::`vftable'
0x180239045  mov     [rax+10h], rcx
0x180239049  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStore2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStore2>::`vftable'
0x180239050  mov     [rax+18h], rcx
0x180239054  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UIClosable@Foundation@Windows@8@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Windows::Foundation::IClosable>::`vftable'
0x18023905b  mov     [rax+20h], rcx
0x18023905f  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex>::`vftable'
0x180239066  mov     [rax+28h], rcx
0x18023906a  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndex@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex>::`vftable'
0x180239071  mov     [rax+30h], rcx
0x180239075  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex2>::`vftable'
0x18023907c  mov     [rax+38h], rcx
0x180239080  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndex2@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex2>::`vftable'
0x180239087  mov     [rax+40h], rcx
0x18023908b  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex3>::`vftable'
0x180239092  mov     [rax+48h], rcx
0x180239096  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndex3@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex3>::`vftable'
0x18023909d  mov     [rax+50h], rcx
0x1802390a1  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex4@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex4>::`vftable'
0x1802390a8  mov     [rax+58h], rcx
0x1802390ac  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndex4@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex4>::`vftable'
0x1802390b3  mov     [rax+60h], rcx
0x1802390b7  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticIndex5@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticIndex5>::`vftable'
0x1802390be  mov     [rax+68h], rcx
0x1802390c2  lea     rcx, ??_7?$produce@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndex5@345678@@impl@winrt@@6B@; const winrt::impl::produce<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndex5>::`vftable'
0x1802390c9  mov     [rax+70h], rcx
0x1802390cd  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802390d4  mov     qword ptr [rax+8], 1
0x1802390dc  mov     [rax+80h], r14
0x1802390e3  xor     ecx, ecx
0x1802390e5  mov     [rax+88h], rcx
0x1802390ec  mov     dword ptr [rax+90h], 3E8h
0x1802390f6  lea     rcx, ??_7?$heap_implements@USemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore>::`vftable'
0x1802390fd  mov     [rax], rcx
0x180239100  mov     [rbx+180h], rax
0x180239107  mov     [rbx+118h], rax
0x18023910e  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180239115  mov     byte ptr [rbx+121h], 0
0x18023911c  mov     eax, [rbx+70h]
0x18023911f  cmp     eax, 2
0x180239122  jnz     short loc_180239161
0x180239124  lea     rdx, [rbx+188h]; struct winrt::impl::slim_source_location *
0x18023912b  mov     dword ptr [rdx], 1628h
0x180239131  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180239138  mov     [rbx+190h], rax
0x18023913f  mov     [rbx+198h], r14
0x180239146  lea     rcx, [rsp+1A8h+var_140]; this
0x18023914b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x180239150  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180239157  lea     rcx, [rsp+1A8h+var_140]; pExceptionObject
0x18023915c  call    _CxxThrowException
0x180239161  mov     eax, 4
0x180239166  mov     [rsi], ax
0x180239169  mov     rdx, rbx
0x18023916c  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::coroutine_handle<void>)
0x180239171  jmp     loc_180239605
0x180239176  mov     dword ptr [rbx+98h], 4Ah ; 'J'
0x180239180  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180239187  mov     [rbx+0A0h], rax
0x18023918e  mov     [rbx+0A8h], r14
0x180239195  lea     rdx, aOptions; "options"
0x18023919c  lea     rcx, [rbx+0B0h]; this
0x1802391a3  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1802391a8  lea     r8, [rbx+98h]; struct winrt::impl::slim_source_location *
0x1802391af  lea     rdx, [rbx+0B0h]; struct winrt::param::hstring *
0x1802391b6  lea     rcx, [rsp+1A8h+var_128]; this
0x1802391be  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1802391c3  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802391ca  lea     rcx, [rsp+1A8h+var_128]; pExceptionObject
0x1802391d2  call    _CxxThrowException
0x1802391d8  mov     eax, 0FFFFFFFFh; jumptable 0000000180238F1E case 5
0x1802391dd  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1802391e5  sub     eax, 1
0x1802391e8  jz      short loc_1802391F4
0x1802391ea  test    eax, eax
0x1802391ec  jns     short loc_1802391F4
0x1802391ee  call    abort
0x1802391f4  cmp     qword ptr [rbx+180h], 0
0x1802391fc  jz      short loc_18023920B
0x1802391fe  lea     rcx, [rbx+118h]
0x180239205  call    ?unconditional_release_ref@?$com_ptr@U?$vector_impl@Uguid@winrt@@V?$vector@Uguid@winrt@@V?$allocator@Uguid@winrt@@@std@@@std@@Umulti_threaded_collection_base@impl@2@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::vector_impl<winrt::guid,std::vector<winrt::guid>,winrt::impl::multi_threaded_collection_base>>::unconditional_release_ref(void)
0x18023920a  nop
0x18023920b  jmp     loc_1802395D0; jumptable 0000000180238F1E cases -1,1
0x180239210  lea     r15, [rbx+130h]; jumptable 0000000180238F1E case 4
0x180239217  mov     rcx, [rbx+88h]
0x18023921e  mov     [r15], rcx
0x180239221  test    rcx, rcx
0x180239224  jz      short loc_180239233
0x180239226  mov     rax, [rcx]
0x180239229  mov     rax, [rax+8]
0x18023922d  call    cs:__guard_dispatch_icall_fptr
0x180239233  mov     [rbx+128h], r15
0x18023923a  mov     ecx, 6F0h; Size
0x18023923f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180239244  mov     [rbx+1A0h], rax
0x18023924b  mov     [rsp+1A8h+var_188], rax
0x180239250  lea     rcx, winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__InitializeAsync$_DestroyCoro$2
0x180239257  mov     [rax+8], rcx
0x18023925b  mov     rax, [rbx+1A0h]
0x180239262  mov     [rsp+1A8h+var_188], rax
0x180239267  lea     rcx, winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__InitializeAsync$_ResumeCoro$1
0x18023926e  mov     [rax], rcx
0x180239271  mov     rcx, [rbx+1A0h]
0x180239278  mov     [rsp+1A8h+var_188], rcx
0x18023927d  mov     rax, [rbx+180h]
0x180239284  mov     [rcx+80h], rax
0x18023928b  mov     rax, [r15]
0x18023928e  xor     r14d, r14d
0x180239291  mov     [r15], r14
0x180239294  mov     [rcx+88h], rax
0x18023929b  mov     rax, [rbx+1A0h]
0x1802392a2  mov     [rsp+1A8h+var_188], rax
0x1802392a7  mov     dword ptr [rax+90h], 10002h
0x1802392b1  mov     rax, [rbx+1A0h]
0x1802392b8  mov     [rsp+1A8h+var_188], rax
0x1802392bd  xorps   xmm0, xmm0
0x1802392c0  xor     ecx, ecx
0x1802392c2  movups  xmmword ptr [rax+10h], xmm0
0x1802392c6  movups  xmmword ptr [rax+20h], xmm0
0x1802392ca  movups  xmmword ptr [rax+30h], xmm0
0x1802392ce  movups  xmmword ptr [rax+40h], xmm0
0x1802392d2  movups  xmmword ptr [rax+50h], xmm0
0x1802392d6  movups  xmmword ptr [rax+60h], xmm0
0x1802392da  mov     [rax+70h], rcx
0x1802392de  mov     rdi, [rbx+1A0h]
0x1802392e5  mov     [rsp+1A8h+var_188], rdi
0x1802392ea  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticTextIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncAction@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction>::`vftable'
0x1802392f1  mov     [rdi+20h], rax
0x1802392f5  lea     rax, ??_7?$produce@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticTextIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncInfo@Foundation@Windows@winrt@@@impl@winrt@@6B@; const winrt::impl::produce<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncInfo>::`vftable'
0x1802392fc  mov     [rdi+28h], rax
0x180239300  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180239307  mov     qword ptr [rdi+18h], 1
0x18023930f  mov     [rdi+30h], r14
0x180239313  mov     [rdi+38h], r14
0x180239317  mov     [rdi+40h], cl
0x18023931a  lea     rax, ??_7?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticTextIndexStoreOptions@789Asg@Microsoft@4@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@6B@; const winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::`vftable'
0x180239321  mov     [rdi+10h], rax
0x180239325  lea     rcx, [rdi+48h]; void *
0x180239329  mov     [rcx], r14
0x18023932c  mov     [rcx+8], r14
0x180239330  call    ?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x180239335  mov     [rdi+58h], r14
0x180239339  mov     [rdi+60h], r14
0x18023933d  mov     [rdi+68h], r14
0x180239341  xor     eax, eax
0x180239343  mov     [rdi+70h], eax
0x180239346  mov     [rdi+74h], al
0x180239349  lea     rax, ??_7promise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUSemanticTextIndexStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@USemanticTextIndexStoreOptions@789Asg@Microsoft@4@@std@@6B@; const std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::`vftable'
0x180239350  mov     [rdi+10h], rax
0x180239354  mov     rax, [rbx+1A0h]
0x18023935b  mov     [rsp+1A8h+var_188], rax
0x180239360  lea     rcx, [rax+20h]
0x180239364  lea     rdi, [rbx+138h]
0x18023936b  mov     [rdi], rcx
0x18023936e  test    rcx, rcx
0x180239371  jz      short loc_180239381
0x180239373  mov     rax, [rcx]
0x180239376  mov     rax, [rax+8]
0x18023937a  call    cs:__guard_dispatch_icall_fptr
0x180239380  nop
0x180239381  mov     rax, [rbx+1A0h]
0x180239388  mov     [rsp+1A8h+var_188], rax
0x18023938d  xor     ecx, ecx
0x18023938f  mov     [rax+78h], cl
0x180239392  mov     rcx, [rbx+1A0h]; Block
0x180239399  mov     [rsp+1A8h+var_188], rcx
0x18023939e  call    winrt__Microsoft__Asg__SemanticIndex__AiFabric__Compatibility__implementation__SemanticTextIndexStore__InitializeAsync$_ResumeCoro$1
0x1802393a3  nop
0x1802393a4  mov     rax, [r15]
0x1802393a7  mov     [rsp+1A8h+var_160], rax
0x1802393ac  test    rax, rax
0x1802393af  jz      short loc_1802393BA
0x1802393b1  mov     rcx, r15
0x1802393b4  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802393b9  nop
0x1802393ba  mov     eax, [rbx+70h]
0x1802393bd  cmp     eax, 2
0x1802393c0  jnz     short loc_180239405
0x1802393c2  lea     rdx, [rbx+8C0h]; struct winrt::impl::slim_source_location *
0x1802393c9  mov     dword ptr [rdx], 1628h
0x1802393cf  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802393d6  mov     [rbx+8C8h], rax
0x1802393dd  mov     [rbx+8D0h], r14
0x1802393e4  lea     rcx, [rsp+1A8h+var_110]; this
0x1802393ec  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802393f1  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802393f8  lea     rcx, [rsp+1A8h+var_110]; pExceptionObject
0x180239400  call    _CxxThrowException
0x180239405  lea     rcx, [rbx+140h]
0x18023940c  mov     [rcx], r14
0x18023940f  mov     [rbx+148h], rdi
0x180239416  mov     [rbx+150h], r14
0x18023941d  mov     byte ptr [rbx+158h], 1
0x180239424  mov     eax, 6
0x180239429  mov     [rsi], ax
0x18023942c  mov     rdx, rbx
0x18023942f  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@UIAsyncAction@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncAction,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type>)
0x180239434  test    al, al
0x180239436  jz      loc_1802394D6
0x18023943c  jmp     loc_180239605
0x180239441  cmp     qword ptr [rbx+140h], 0; jumptable 0000000180238F1E case 7
0x180239449  jz      short loc_180239481
0x18023944b  mov     rdi, [rbx+140h]
0x180239452  mov     rcx, rdi
0x180239455  mov     [rsp+1A8h+var_F8], rcx
0x18023945d  xor     r14d, r14d
0x180239460  mov     eax, r14d
0x180239463  xchg    rax, [rcx]
0x180239466  cmp     rax, 1
0x18023946a  jnz     short loc_180239481
0x18023946c  nop     dword ptr [rax+00h]
0x180239470  call    _Thrd_yield
0x180239475  mov     rax, r14
0x180239478  xchg    rax, [rdi]
0x18023947b  cmp     rax, 1
0x18023947f  jz      short loc_180239470
0x180239481  lea     rcx, [rbx+138h]
0x180239488  mov     rax, [rcx]
  ... truncated ...
```
