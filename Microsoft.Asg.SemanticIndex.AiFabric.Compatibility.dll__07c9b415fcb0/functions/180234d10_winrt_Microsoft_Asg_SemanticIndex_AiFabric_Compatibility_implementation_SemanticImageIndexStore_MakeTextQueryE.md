# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1

- ea: `0x180234d10`
- end: `0x18023561c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1`
- size: `2316`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cb00`
- `0x180234d00`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180009cd0`
- `0x18000d230`
- `0x180010400`
- `0x180010dd0`
- `0x18001b680`
- `0x18001b830`
- `0x18001c2d0`
- `0x18001fd50`
- `0x180021690`
- `0x180032bf0`
- `0x180047520`
- `0x18005a7f0`
- `0x1800681e0`
- `0x180078d00`
- `0x180078d10`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x180234d10`
- `0x180242120`

## string_xrefs

- `0x180234e64`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180234eea`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023513a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180234dec`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802351d9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802353d9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x180235259`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync__ResumeCoro_1(
        char *Block)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  int v4; // eax
  char v5; // al
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // r13
  char *v9; // rbx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  HANDLE ProcessHeap; // rax
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // eax
  volatile __int64 *v19; // rbx
  char *v20; // r15
  volatile __int64 *v21; // rbx
  int v22; // ebx
  __int64 v23; // rcx
  int v24; // eax
  RTL_SRWLOCK *v25; // rbx
  __int64 v26; // rax
  _QWORD *v27; // r12
  __int64 v28; // rax
  __int64 v29; // [rsp+30h] [rbp-198h]
  __m256i v30; // [rsp+70h] [rbp-158h]
  void *v31; // [rsp+98h] [rbp-130h]
  _BYTE pExceptionObject[24]; // [rsp+B8h] [rbp-110h] BYREF
  _BYTE v33[24]; // [rsp+D0h] [rbp-F8h] BYREF
  __int128 v34; // [rsp+E8h] [rbp-E0h]
  __int64 v35; // [rsp+100h] [rbp-C8h]
  __int64 v36; // [rsp+108h] [rbp-C0h]
  char v37; // [rsp+118h] [rbp-B0h] BYREF
  __int128 v38; // [rsp+140h] [rbp-88h]

  switch ( *((_WORD *)Block + 76) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_70;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v2 = *((_QWORD *)Block + 18);
      *((_QWORD *)Block + 20) = v2;
      if ( v2 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(
        Block + 168,
        Block + 160);
      v3 = *(_QWORD *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticImageIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::VectorSpaceId(
                        Block + 144,
                        Block + 200);
      if ( v3 )
      {
        *(_OWORD *)(Block + 440) = 0;
        *((_DWORD *)Block + 114) = 1984;
        *((_QWORD *)Block + 58) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 59) = 0;
        v4 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v3 + 48LL))(v3, Block + 440);
        if ( v4 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v4, Block + 456);
        }
        v38 = *(_OWORD *)(Block + 440);
        *((_OWORD *)Block + 13) = v38;
        v5 = 1;
      }
      else
      {
        v5 = 0;
      }
      Block[224] = v5;
      *((_DWORD *)Block + 108) = 0;
      v6 = *((_QWORD *)Block + 18);
      *((_DWORD *)Block + 120) = 1855;
      *((_QWORD *)Block + 61) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 62) = 0;
      v7 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v6 + 56LL))(v6, Block + 432);
      if ( v7 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v7, Block + 480);
      }
      v29 = *((_QWORD *)Block + 22);
      v36 = *((_QWORD *)Block + 23);
      v35 = *((_QWORD *)Block + 22);
      v8 = v36 - v35;
      v9 = Block + 504;
      *((_QWORD *)Block + 63) = 0;
      v10 = *((_QWORD *)Block + 18);
      *((_DWORD *)Block + 128) = 1837;
      *((_QWORD *)Block + 65) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 66) = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v10 + 48LL))(v10, Block + 504);
      if ( v11 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v11, Block + 512);
      }
      *((_QWORD *)Block + 29) = *(_QWORD *)v9;
      *((_QWORD *)Block + 52) = v29;
      *((_QWORD *)Block + 53) = v8;
      v30 = *(__m256i *)winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveCurrentAndPreviousVectorSpace(
                          (unsigned int)&v37,
                          (int)Block + 232,
                          (int)Block + 416,
                          *((_DWORD *)Block + 108),
                          (__int64)(Block + 208),
                          (__int64)&winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId);
      if ( *(_QWORD *)v9 )
      {
        v12 = _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v9 + 24LL));
        if ( v12 )
        {
          if ( v12 < 0 )
            abort();
        }
        else
        {
          v31 = *(void **)v9;
          ProcessHeap = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(ProcessHeap, 0, v31);
        }
      }
      if ( *((_QWORD *)Block + 25) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 200);
      *((_OWORD *)Block + 34) = *(_OWORD *)((char *)v30.m256i_i64 + 4);
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(Block + 240);
      if ( !*((_QWORD *)Block + 30) )
      {
        *((_DWORD *)Block + 86) = 485;
        *((_QWORD *)Block + 44) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticIm"
                                  "ageIndexStore.cpp";
        *((_QWORD *)Block + 45) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(Block + 368),
          L"Failed to make generator available for given options");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v33,
          (const struct winrt::param::hstring *)(Block + 368),
          (const struct winrt::impl::slim_source_location *)(Block + 344));
        throw (winrt::hresult_invalid_argument *)v33;
      }
      *((_QWORD *)Block + 31) = Block + 16;
      *((_QWORD *)Block + 32) = Block + 16;
      *((_DWORD *)Block + 66) = 1;
      *((_QWORD *)Block + 34) = 0;
      *((_QWORD *)Block + 86) = Block + 88;
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)Block + 11);
      v14 = *((_QWORD *)Block + 16);
      *((_QWORD *)Block + 77) = v14;
      if ( v14 )
      {
        (*(void (**)(void))(*(_QWORD *)v14 + 8LL))();
        ReleaseSRWLockExclusive_0((PSRWLOCK)Block + 11);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          Block + 616,
          Block + 16,
          Block + 264);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 616);
      }
      else
      {
        ReleaseSRWLockExclusive_0((PSRWLOCK)Block + 11);
      }
      *((_QWORD *)Block + 76) = 0;
      if ( *((_QWORD *)Block + 30) )
      {
        *((_QWORD *)Block + 88) = 0;
        v15 = (***((__int64 (__fastcall ****)(_QWORD, __int64 *, char *))Block + 30))(
                *((_QWORD *)Block + 30),
                winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>,
                Block + 704);
        v17 = *((_QWORD *)Block + 88);
        v16 = v17;
      }
      else
      {
        v15 = 0;
        v16 = 0;
        v17 = 0;
      }
      *((_QWORD *)Block + 78) = v17;
      *((_DWORD *)Block + 158) = 582;
      *((_QWORD *)Block + 80) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 81) = 0;
      if ( v15 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v15, Block + 632);
      }
      *((_DWORD *)Block + 164) = 584;
      *((_QWORD *)Block + 83) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generat"
                                "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)Block + 84) = 0;
      v18 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v16 + 80LL))(v16, Block + 608);
      if ( v18 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v18, Block + 656);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 624);
      *((_QWORD *)Block + 35) = *((_QWORD *)Block + 76);
      if ( *((_DWORD *)Block + 28) == 2 )
      {
        *((_DWORD *)Block + 146) = 5672;
        *((_QWORD *)Block + 74) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)Block + 75) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(Block + 584));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)Block + 36) = 0;
      *((_QWORD *)Block + 37) = Block + 280;
      *((_QWORD *)Block + 38) = 0;
      Block[312] = 1;
      *((_WORD *)Block + 76) = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(
                              (_QWORD *)Block + 36,
                              (__int64)Block) )
        return;
      goto LABEL_46;
    case 6:
LABEL_46:
      v20 = Block + 320;
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        Block + 288,
        Block + 320);
      if ( *((_QWORD *)Block + 36) )
      {
        v21 = (volatile __int64 *)*((_QWORD *)Block + 36);
        while ( _InterlockedExchange64(v21, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 35) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 280);
      v22 = 2;
      if ( *(_QWORD *)v20 )
      {
        *((_DWORD *)Block + 181) = 0;
        v23 = *(_QWORD *)v20;
        *((_DWORD *)Block + 182) = 1440;
        *((_QWORD *)Block + 92) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Gener"
                                  "ated Files\\winrt\\Microsoft.Windows.Management.Deployment.h";
        *((_QWORD *)Block + 93) = 0;
        v24 = (*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v23 + 48LL))(v23, Block + 724);
        if ( v24 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v24, Block + 728);
        }
        if ( *((_DWORD *)Block + 181) != 1 )
          v22 = 3;
      }
      *((_DWORD *)Block + 82) = v22;
      *((_QWORD *)Block + 42) = 0x3FF0000000000000LL;
      v34 = *(_OWORD *)(Block + 328);
      *(_OWORD *)(Block + 264) = v34;
      v25 = (RTL_SRWLOCK *)*((_QWORD *)Block + 86);
      WINRT_IMPL_AcquireSRWLockExclusive(v25);
      v26 = *(_QWORD *)(*((_QWORD *)Block + 32) + 112LL);
      *((_QWORD *)Block + 89) = v26;
      if ( v26 )
      {
        (*(void (**)(void))(*(_QWORD *)v26 + 8LL))();
        ReleaseSRWLockExclusive_0(v25);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          Block + 712,
          *((_QWORD *)Block + 32),
          Block + 264);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 712);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v25);
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)Block + 11);
      v27 = Block + 120;
      if ( Block + 120 != v20 )
      {
        if ( *v27 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 120);
        v28 = *(_QWORD *)v20;
        *(_QWORD *)v20 = 0;
        *v27 = v28;
      }
      ReleaseSRWLockExclusive_0((PSRWLOCK)Block + 11);
      if ( *(_QWORD *)v20 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 320);
      if ( *((_QWORD *)Block + 30) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 240);
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(Block + 168);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)Block + 50) = Block + 16;
      *((_WORD *)Block + 76) = 0;
      *(_QWORD *)Block = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend() )
        goto LABEL_70;
      return;
    case 7:
      if ( *((_QWORD *)Block + 36) )
      {
        v19 = (volatile __int64 *)*((_QWORD *)Block + 36);
        while ( _InterlockedExchange64(v19, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)Block + 35) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 280);
      if ( *((_QWORD *)Block + 30) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 240);
      std::vector<unsigned char,asg::secure_allocator<unsigned char>>::_Tidy(Block + 168);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_70:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(Block + 16);
      if ( *((_QWORD *)Block + 18) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(Block + 144);
      if ( *((_WORD *)Block + 77) )
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
0x180234d10  mov     r11, rsp
0x180234d13  mov     [r11+10h], rbx
0x180234d17  mov     [r11+18h], rsi
0x180234d1b  mov     [r11+8], rcx
0x180234d1f  push    rdi
0x180234d20  push    r12
0x180234d22  push    r13
0x180234d24  push    r14
0x180234d26  push    r15
0x180234d28  sub     rsp, 1A0h
0x180234d2f  mov     rax, cs:__security_cookie
0x180234d36  xor     rax, rsp
0x180234d39  mov     [rsp+1C8h+var_30], rax
0x180234d41  mov     rsi, rcx
0x180234d44  mov     [rsp+1C8h+var_188], rcx
0x180234d49  movzx   eax, word ptr [rsi+98h]
0x180234d50  mov     [rsp+1C8h+var_190], ax
0x180234d55  inc     ax; switch 9 cases
0x180234d58  cmp     ax, 8
0x180234d5c  ja      def_180234D77; jumptable 0000000180234D77 default case, cases 0,4,5
0x180234d62  movsx   rax, ax
0x180234d66  lea     rdx, cs:180000000h
0x180234d6d  mov     ecx, ds:(jpt_180234D77 - 180000000h)[rdx+rax*4]
0x180234d74  add     rcx, rdx
0x180234d77  jmp     rcx; switch jump
0x180234d79  jmp     loc_180235594; jumptable 0000000180234D77 case 3
0x180234d7e  xor     r14d, r14d; jumptable 0000000180234D77 case 2
0x180234d81  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180234d88  mov     rcx, [rsi+90h]
0x180234d8f  mov     [rsi+0A0h], rcx
0x180234d96  test    rcx, rcx
0x180234d99  jz      short loc_180234DA8
0x180234d9b  mov     rax, [rcx]
0x180234d9e  mov     rax, [rax+8]
0x180234da2  call    cs:__guard_dispatch_icall_fptr
0x180234da8  lea     rcx, [rsi+0A8h]
0x180234daf  lea     rdx, [rsi+0A0h]
0x180234db6  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticImageIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x180234dbb  nop
0x180234dbc  lea     rdx, [rsi+0C8h]
0x180234dc3  lea     rcx, [rsi+90h]
0x180234dca  call    ?VectorSpaceId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticImageIndexStoreOptions4@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticImageIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::VectorSpaceId(void)
0x180234dcf  nop
0x180234dd0  mov     rcx, [rax]
0x180234dd3  test    rcx, rcx
0x180234dd6  jz      short loc_180234E44
0x180234dd8  xorps   xmm0, xmm0
0x180234ddb  movups  xmmword ptr [rsi+1B8h], xmm0
0x180234de2  mov     dword ptr [rsi+1C8h], 7C0h
0x180234dec  lea     r13, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180234df3  mov     [rsi+1D0h], r13
0x180234dfa  mov     [rsi+1D8h], r14
0x180234e01  mov     rax, [rcx]
0x180234e04  lea     rdx, [rsi+1B8h]
0x180234e0b  mov     rax, [rax+30h]
0x180234e0f  call    cs:__guard_dispatch_icall_fptr
0x180234e15  test    eax, eax
0x180234e17  jns     short loc_180234E2A
0x180234e19  lfence
0x180234e1c  lea     rdx, [rsi+1C8h]
0x180234e23  mov     ecx, eax
0x180234e25  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234e2a  movups  xmm0, xmmword ptr [rsi+1B8h]
0x180234e31  movups  [rsp+1C8h+var_88], xmm0
0x180234e39  movups  xmmword ptr [rsi+0D0h], xmm0
0x180234e40  mov     al, 1
0x180234e42  jmp     short loc_180234E46
0x180234e44  xor     al, al
0x180234e46  mov     [rsi+0E0h], al
0x180234e4c  mov     [rsi+1B0h], r14d
0x180234e53  mov     rcx, [rsi+90h]
0x180234e5a  mov     dword ptr [rsi+1E0h], 73Fh
0x180234e64  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180234e6b  mov     [rsi+1E8h], rax
0x180234e72  mov     [rsi+1F0h], r14
0x180234e79  mov     rax, [rcx]
0x180234e7c  lea     rdx, [rsi+1B0h]
0x180234e83  mov     rax, [rax+38h]
0x180234e87  call    cs:__guard_dispatch_icall_fptr
0x180234e8d  test    eax, eax
0x180234e8f  jns     short loc_180234EA2
0x180234e91  lfence
0x180234e94  lea     rdx, [rsi+1E0h]
0x180234e9b  mov     ecx, eax
0x180234e9d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234ea2  mov     rax, [rsi+0B0h]
0x180234ea9  mov     [rsp+1C8h+var_198], rax
0x180234eae  mov     r13, [rsi+0B8h]
0x180234eb5  mov     [rsp+1C8h+var_C0], r13
0x180234ebd  mov     rax, [rsi+0B0h]
0x180234ec4  mov     [rsp+1C8h+var_C8], rax
0x180234ecc  sub     r13, rax
0x180234ecf  lea     rbx, [rsi+1F8h]
0x180234ed6  mov     [rbx], r14
0x180234ed9  mov     rcx, [rsi+90h]
0x180234ee0  mov     dword ptr [rsi+200h], 72Dh
0x180234eea  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180234ef1  mov     [rsi+208h], rax
0x180234ef8  mov     [rsi+210h], r14
0x180234eff  mov     rax, [rcx]
0x180234f02  mov     rdx, rbx
0x180234f05  mov     rax, [rax+30h]
0x180234f09  call    cs:__guard_dispatch_icall_fptr
0x180234f0f  test    eax, eax
0x180234f11  jns     short loc_180234F24
0x180234f13  lfence
0x180234f16  lea     rdx, [rsi+200h]
0x180234f1d  mov     ecx, eax
0x180234f1f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234f24  lea     rdx, [rsi+0E8h]
0x180234f2b  mov     rax, [rbx]
0x180234f2e  mov     [rdx], rax
0x180234f31  lea     r8, [rsi+1A0h]
0x180234f38  mov     rax, [rsp+1C8h+var_198]
0x180234f3d  mov     [r8], rax
0x180234f40  mov     [rsi+1A8h], r13
0x180234f47  mov     r9d, [rsi+1B0h]
0x180234f4e  mov     [rsp+1C8h+var_18C], r9d
0x180234f53  lea     rax, [rsi+0D0h]
0x180234f5a  lea     rcx, ?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x180234f61  mov     [rsp+1C8h+var_1A0], rcx
0x180234f66  mov     [rsp+1C8h+var_1A8], rax
0x180234f6b  lea     rcx, [rsp+1C8h+var_B0]
0x180234f73  call    ?ResolveCurrentAndPreviousVectorSpace@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUVectorSpaceResolution@1234567@AEBUhstring@7@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@234567@AEBV?$optional@Uguid@winrt@@@std@@AEBUguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveCurrentAndPreviousVectorSpace(winrt::hstring const &,std::span<uchar const,-1>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,std::optional<winrt::guid> const &,winrt::guid const &)
0x180234f78  movups  xmm0, xmmword ptr [rax]
0x180234f7b  movups  [rsp+1C8h+var_158], xmm0
0x180234f80  movups  xmm1, xmmword ptr [rax+10h]
0x180234f84  movups  [rsp+1C8h+var_148], xmm1
0x180234f8c  movsd   xmm0, qword ptr [rax+20h]
0x180234f91  movsd   [rsp+1C8h+var_138], xmm0
0x180234f9a  mov     edi, 0FFFFFFFFh
0x180234f9f  cmp     qword ptr [rbx], 0
0x180234fa3  jz      short loc_180234FDD
0x180234fa5  mov     rcx, [rbx]
0x180234fa8  mov     eax, edi
0x180234faa  lock xadd [rcx+18h], eax
0x180234faf  sub     eax, 1
0x180234fb2  jnz     short loc_180234FD3
0x180234fb4  mov     rbx, [rbx]
0x180234fb7  mov     [rsp+1C8h+var_130], rbx
0x180234fbf  call    WINRT_IMPL_GetProcessHeap
0x180234fc4  mov     rcx, rax; hHeap
0x180234fc7  mov     r8, rbx; lpMem
0x180234fca  xor     edx, edx; dwFlags
0x180234fcc  call    WINRT_IMPL_HeapFree
0x180234fd1  jmp     short loc_180234FDD
0x180234fd3  test    eax, eax
0x180234fd5  jns     short loc_180234FDD
0x180234fd7  call    abort
0x180234fdd  mov     rax, [rsi+0C8h]
0x180234fe4  mov     [rsp+1C8h+var_128], rax
0x180234fec  test    rax, rax
0x180234fef  jz      short loc_180234FFD
0x180234ff1  lea     rcx, [rsi+0C8h]
0x180234ff8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180234ffd  lea     rdx, [rsi+220h]
0x180235004  movups  xmm0, [rsp+1C8h+var_158+4]
0x180235009  movaps  xmmword ptr [rdx], xmm0
0x18023500c  lea     rcx, [rsi+0F0h]
0x180235013  call    ?TryGetTextEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUITextEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(winrt::guid)
0x180235018  nop
0x180235019  cmp     qword ptr [rsi+0F0h], 0
0x180235021  jz      loc_18023524F
0x180235027  lea     rbx, [rsi+10h]
0x18023502b  mov     [rsi+0F8h], rbx
0x180235032  mov     [rsi+100h], rbx
0x180235039  mov     dword ptr [rsi+108h], 1
0x180235043  mov     [rsi+110h], r14
0x18023504a  lea     r12, [rbx+48h]
0x18023504e  mov     [rsi+2B0h], r12
0x180235055  mov     rcx, r12; SRWLock
0x180235058  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023505d  mov     rax, [rbx+70h]
0x180235061  mov     [rsi+268h], rax
0x180235068  test    rax, rax
0x18023506b  jz      short loc_1802350B7
0x18023506d  mov     [rsp+1C8h+var_170], rax
0x180235072  mov     r9, [rax]
0x180235075  mov     rcx, [rsi+268h]
0x18023507c  mov     [rsp+1C8h+var_170], rcx
0x180235081  mov     rax, [r9+8]
0x180235085  call    cs:__guard_dispatch_icall_fptr
0x18023508b  mov     rcx, r12; SRWLock
0x18023508e  call    ReleaseSRWLockExclusive_0
0x180235093  lea     r8, [rsi+108h]
0x18023509a  mov     rdx, rbx
0x18023509d  lea     rcx, [rsi+268h]
0x1802350a4  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x1802350a9  lea     rcx, [rsi+268h]
0x1802350b0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802350b5  jmp     short loc_1802350BF
0x1802350b7  mov     rcx, r12; SRWLock
0x1802350ba  call    ReleaseSRWLockExclusive_0
0x1802350bf  mov     [rsi+260h], r14
0x1802350c6  cmp     qword ptr [rsi+0F0h], 0
0x1802350ce  jnz     short loc_1802350DB
0x1802350d0  mov     eax, r14d
0x1802350d3  mov     rcx, r14
0x1802350d6  mov     rdx, r14
0x1802350d9  jmp     short loc_180235126
0x1802350db  mov     [rsi+2C0h], r14
0x1802350e2  mov     rax, [rsi+0F0h]
0x1802350e9  mov     [rsp+1C8h+var_198], rax
0x1802350ee  mov     rcx, [rax]
0x1802350f1  mov     rax, [rcx]
0x1802350f4  mov     rcx, [rsi+0F0h]
0x1802350fb  mov     [rsp+1C8h+var_198], rcx
0x180235100  lea     r8, [rsi+2C0h]
0x180235107  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18023510e  call    cs:__guard_dispatch_icall_fptr
0x180235114  mov     rdx, [rsi+2C0h]
0x18023511b  mov     rcx, rdx
0x18023511e  mov     [rsp+1C8h+var_120], rdx
0x180235126  mov     [rsi+270h], rdx
0x18023512d  lea     rdx, [rsi+278h]
0x180235134  mov     dword ptr [rdx], 246h
0x18023513a  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180235141  mov     [rsi+280h], r8
0x180235148  mov     [rsi+288h], r14
0x18023514f  test    eax, eax
0x180235151  jns     short loc_18023515D
0x180235153  lfence
0x180235156  mov     ecx, eax
0x180235158  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023515d  mov     dword ptr [rsi+290h], 248h
0x180235167  mov     [rsi+298h], r8
0x18023516e  mov     [rsi+2A0h], r14
0x180235175  mov     rax, [rcx]
0x180235178  lea     rdx, [rsi+260h]
0x18023517f  mov     rax, [rax+50h]
0x180235183  call    cs:__guard_dispatch_icall_fptr
0x180235189  test    eax, eax
0x18023518b  jns     short loc_18023519F
0x18023518d  lfence
0x180235190  lea     rdx, [rsi+290h]
0x180235197  mov     ecx, eax
0x180235199  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023519f  lea     rcx, [rsi+270h]
0x1802351a6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802351ab  lea     rdx, [rsi+118h]
0x1802351b2  mov     rax, [rsi+260h]
0x1802351b9  mov     [rsp+1C8h+var_118], rax
0x1802351c1  mov     [rdx], rax
0x1802351c4  mov     eax, [rsi+70h]
0x1802351c7  cmp     eax, 2
0x1802351ca  jnz     short loc_18023520F
0x1802351cc  lea     rdx, [rsi+248h]; struct winrt::impl::slim_source_location *
0x1802351d3  mov     dword ptr [rdx], 1628h
0x1802351d9  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802351e0  mov     [rsi+250h], rax
0x1802351e7  mov     [rsi+258h], r14
0x1802351ee  lea     rcx, [rsp+1C8h+pExceptionObject]; this
0x1802351f6  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802351fb  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180235202  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x18023520a  call    _CxxThrowException
0x18023520f  lea     rcx, [rsi+120h]
0x180235216  mov     [rcx], r14
0x180235219  mov     [rsi+128h], rdx
0x180235220  mov     [rsi+130h], r14
0x180235227  mov     byte ptr [rsi+138h], 1
0x18023522e  mov     eax, 6
0x180235233  mov     [rsi+98h], ax
0x18023523a  mov     rdx, rsi
0x18023523d  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x180235242  test    al, al
0x180235244  jz      loc_180235351
0x18023524a  jmp     loc_1802355C9
0x18023524f  mov     dword ptr [rsi+158h], 1E5h
0x180235259  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180235260  mov     [rsi+160h], rax
0x180235267  mov     [rsi+168h], r14
0x18023526e  lea     rdx, aFailedToMakeGe; "Failed to make generator available for "...
0x180235275  lea     rcx, [rsi+170h]; this
0x18023527c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180235281  lea     r8, [rsi+158h]; struct winrt::impl::slim_source_location *
0x180235288  lea     rdx, [rsi+170h]; struct winrt::param::hstring *
0x18023528f  lea     rcx, [rsp+1C8h+var_F8]; this
0x180235297  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023529c  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802352a3  lea     rcx, [rsp+1C8h+var_F8]; pExceptionObject
0x1802352ab  call    _CxxThrowException
0x1802352b1  cmp     qword ptr [rsi+120h], 0; jumptable 0000000180234D77 case 7
0x1802352b9  jz      short loc_1802352E7
0x1802352bb  mov     rbx, [rsi+120h]
0x1802352c2  mov     qword ptr [rsp+1C8h+var_158], rbx
0x1802352c7  xor     r14d, r14d
0x1802352ca  mov     eax, r14d
0x1802352cd  xchg    rax, [rbx]
0x1802352d0  cmp     rax, 1
0x1802352d4  jnz     short loc_1802352E7
0x1802352d6  call    _Thrd_yield
0x1802352db  mov     rax, r14
0x1802352de  xchg    rax, [rbx]
0x1802352e1  cmp     rax, 1
0x1802352e5  jz      short loc_1802352D6
0x1802352e7  lea     rcx, [rsi+118h]
0x1802352ee  mov     rax, [rcx]
0x1802352f1  mov     [rsp+1C8h+var_168], rax
0x1802352f6  test    rax, rax
  ... truncated ...
```
