# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1

- ea: `0x18023d140`
- end: `0x18023da4c`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1`
- size: `2316`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004b040`
- `0x18023d130`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x180009cd0`
- `0x18000d230`
- `0x180010400`
- `0x180010dd0`
- `0x18001b680`
- `0x18001b830`
- `0x18001fd50`
- `0x180021690`
- `0x180032bf0`
- `0x180047520`
- `0x18004ae40`
- `0x18005a7f0`
- `0x1800680b0`
- `0x180078d00`
- `0x180078d10`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7110`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023d140`
- `0x180242120`

## string_xrefs

- `0x18023d294`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023d31a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023d56a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023d21c`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023d609`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023d809`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x18023d689`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync__ResumeCoro_1(
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
      v3 = *(_QWORD *)winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::VectorSpaceId(
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
      *((_DWORD *)Block + 120) = 3357;
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
      *((_DWORD *)Block + 128) = 3339;
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
                          (__int64)&winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId);
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
        *((_DWORD *)Block + 86) = 223;
        *((_QWORD *)Block + 44) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTe"
                                  "xtIndexStore.cpp";
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
0x18023d140  mov     r11, rsp
0x18023d143  mov     [r11+10h], rbx
0x18023d147  mov     [r11+18h], rsi
0x18023d14b  mov     [r11+8], rcx
0x18023d14f  push    rdi
0x18023d150  push    r12
0x18023d152  push    r13
0x18023d154  push    r14
0x18023d156  push    r15
0x18023d158  sub     rsp, 1A0h
0x18023d15f  mov     rax, cs:__security_cookie
0x18023d166  xor     rax, rsp
0x18023d169  mov     [rsp+1C8h+var_30], rax
0x18023d171  mov     rsi, rcx
0x18023d174  mov     [rsp+1C8h+var_188], rcx
0x18023d179  movzx   eax, word ptr [rsi+98h]
0x18023d180  mov     [rsp+1C8h+var_190], ax
0x18023d185  inc     ax; switch 9 cases
0x18023d188  cmp     ax, 8
0x18023d18c  ja      def_18023D1A7; jumptable 000000018023D1A7 default case, cases 0,4,5
0x18023d192  movsx   rax, ax
0x18023d196  lea     rdx, cs:180000000h
0x18023d19d  mov     ecx, ds:(jpt_18023D1A7 - 180000000h)[rdx+rax*4]
0x18023d1a4  add     rcx, rdx
0x18023d1a7  jmp     rcx; switch jump
0x18023d1a9  jmp     loc_18023D9C4; jumptable 000000018023D1A7 case 3
0x18023d1ae  xor     r14d, r14d; jumptable 000000018023D1A7 case 2
0x18023d1b1  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023d1b8  mov     rcx, [rsi+90h]
0x18023d1bf  mov     [rsi+0A0h], rcx
0x18023d1c6  test    rcx, rcx
0x18023d1c9  jz      short loc_18023D1D8
0x18023d1cb  mov     rax, [rcx]
0x18023d1ce  mov     rax, [rax+8]
0x18023d1d2  call    cs:__guard_dispatch_icall_fptr
0x18023d1d8  lea     rcx, [rsi+0A8h]
0x18023d1df  lea     rdx, [rsi+0A0h]
0x18023d1e6  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticTextIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions)
0x18023d1eb  nop
0x18023d1ec  lea     rdx, [rsi+0C8h]
0x18023d1f3  lea     rcx, [rsi+90h]
0x18023d1fa  call    ?VectorSpaceId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticTextIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::VectorSpaceId(void)
0x18023d1ff  nop
0x18023d200  mov     rcx, [rax]
0x18023d203  test    rcx, rcx
0x18023d206  jz      short loc_18023D274
0x18023d208  xorps   xmm0, xmm0
0x18023d20b  movups  xmmword ptr [rsi+1B8h], xmm0
0x18023d212  mov     dword ptr [rsi+1C8h], 7C0h
0x18023d21c  lea     r13, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023d223  mov     [rsi+1D0h], r13
0x18023d22a  mov     [rsi+1D8h], r14
0x18023d231  mov     rax, [rcx]
0x18023d234  lea     rdx, [rsi+1B8h]
0x18023d23b  mov     rax, [rax+30h]
0x18023d23f  call    cs:__guard_dispatch_icall_fptr
0x18023d245  test    eax, eax
0x18023d247  jns     short loc_18023D25A
0x18023d249  lfence
0x18023d24c  lea     rdx, [rsi+1C8h]
0x18023d253  mov     ecx, eax
0x18023d255  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023d25a  movups  xmm0, xmmword ptr [rsi+1B8h]
0x18023d261  movups  [rsp+1C8h+var_88], xmm0
0x18023d269  movups  xmmword ptr [rsi+0D0h], xmm0
0x18023d270  mov     al, 1
0x18023d272  jmp     short loc_18023D276
0x18023d274  xor     al, al
0x18023d276  mov     [rsi+0E0h], al
0x18023d27c  mov     [rsi+1B0h], r14d
0x18023d283  mov     rcx, [rsi+90h]
0x18023d28a  mov     dword ptr [rsi+1E0h], 0D1Dh
0x18023d294  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023d29b  mov     [rsi+1E8h], rax
0x18023d2a2  mov     [rsi+1F0h], r14
0x18023d2a9  mov     rax, [rcx]
0x18023d2ac  lea     rdx, [rsi+1B0h]
0x18023d2b3  mov     rax, [rax+38h]
0x18023d2b7  call    cs:__guard_dispatch_icall_fptr
0x18023d2bd  test    eax, eax
0x18023d2bf  jns     short loc_18023D2D2
0x18023d2c1  lfence
0x18023d2c4  lea     rdx, [rsi+1E0h]
0x18023d2cb  mov     ecx, eax
0x18023d2cd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023d2d2  mov     rax, [rsi+0B0h]
0x18023d2d9  mov     [rsp+1C8h+var_198], rax
0x18023d2de  mov     r13, [rsi+0B8h]
0x18023d2e5  mov     [rsp+1C8h+var_C0], r13
0x18023d2ed  mov     rax, [rsi+0B0h]
0x18023d2f4  mov     [rsp+1C8h+var_C8], rax
0x18023d2fc  sub     r13, rax
0x18023d2ff  lea     rbx, [rsi+1F8h]
0x18023d306  mov     [rbx], r14
0x18023d309  mov     rcx, [rsi+90h]
0x18023d310  mov     dword ptr [rsi+200h], 0D0Bh
0x18023d31a  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023d321  mov     [rsi+208h], rax
0x18023d328  mov     [rsi+210h], r14
0x18023d32f  mov     rax, [rcx]
0x18023d332  mov     rdx, rbx
0x18023d335  mov     rax, [rax+30h]
0x18023d339  call    cs:__guard_dispatch_icall_fptr
0x18023d33f  test    eax, eax
0x18023d341  jns     short loc_18023D354
0x18023d343  lfence
0x18023d346  lea     rdx, [rsi+200h]
0x18023d34d  mov     ecx, eax
0x18023d34f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023d354  lea     rdx, [rsi+0E8h]
0x18023d35b  mov     rax, [rbx]
0x18023d35e  mov     [rdx], rax
0x18023d361  lea     r8, [rsi+1A0h]
0x18023d368  mov     rax, [rsp+1C8h+var_198]
0x18023d36d  mov     [r8], rax
0x18023d370  mov     [rsi+1A8h], r13
0x18023d377  mov     r9d, [rsi+1B0h]
0x18023d37e  mov     [rsp+1C8h+var_18C], r9d
0x18023d383  lea     rax, [rsi+0D0h]
0x18023d38a  lea     rcx, ?VectorSpaceId@SpaceV6@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId
0x18023d391  mov     [rsp+1C8h+var_1A0], rcx
0x18023d396  mov     [rsp+1C8h+var_1A8], rax
0x18023d39b  lea     rcx, [rsp+1C8h+var_B0]
0x18023d3a3  call    ?ResolveCurrentAndPreviousVectorSpace@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUVectorSpaceResolution@1234567@AEBUhstring@7@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@234567@AEBV?$optional@Uguid@winrt@@@std@@AEBUguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveCurrentAndPreviousVectorSpace(winrt::hstring const &,std::span<uchar const,-1>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,std::optional<winrt::guid> const &,winrt::guid const &)
0x18023d3a8  movups  xmm0, xmmword ptr [rax]
0x18023d3ab  movups  [rsp+1C8h+var_158], xmm0
0x18023d3b0  movups  xmm1, xmmword ptr [rax+10h]
0x18023d3b4  movups  [rsp+1C8h+var_148], xmm1
0x18023d3bc  movsd   xmm0, qword ptr [rax+20h]
0x18023d3c1  movsd   [rsp+1C8h+var_138], xmm0
0x18023d3ca  mov     edi, 0FFFFFFFFh
0x18023d3cf  cmp     qword ptr [rbx], 0
0x18023d3d3  jz      short loc_18023D40D
0x18023d3d5  mov     rcx, [rbx]
0x18023d3d8  mov     eax, edi
0x18023d3da  lock xadd [rcx+18h], eax
0x18023d3df  sub     eax, 1
0x18023d3e2  jnz     short loc_18023D403
0x18023d3e4  mov     rbx, [rbx]
0x18023d3e7  mov     [rsp+1C8h+var_130], rbx
0x18023d3ef  call    WINRT_IMPL_GetProcessHeap
0x18023d3f4  mov     rcx, rax; hHeap
0x18023d3f7  mov     r8, rbx; lpMem
0x18023d3fa  xor     edx, edx; dwFlags
0x18023d3fc  call    WINRT_IMPL_HeapFree
0x18023d401  jmp     short loc_18023D40D
0x18023d403  test    eax, eax
0x18023d405  jns     short loc_18023D40D
0x18023d407  call    abort
0x18023d40d  mov     rax, [rsi+0C8h]
0x18023d414  mov     [rsp+1C8h+var_128], rax
0x18023d41c  test    rax, rax
0x18023d41f  jz      short loc_18023D42D
0x18023d421  lea     rcx, [rsi+0C8h]
0x18023d428  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d42d  lea     rdx, [rsi+220h]
0x18023d434  movups  xmm0, [rsp+1C8h+var_158+4]
0x18023d439  movaps  xmmword ptr [rdx], xmm0
0x18023d43c  lea     rcx, [rsi+0F0h]
0x18023d443  call    ?TryGetTextEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUITextEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(winrt::guid)
0x18023d448  nop
0x18023d449  cmp     qword ptr [rsi+0F0h], 0
0x18023d451  jz      loc_18023D67F
0x18023d457  lea     rbx, [rsi+10h]
0x18023d45b  mov     [rsi+0F8h], rbx
0x18023d462  mov     [rsi+100h], rbx
0x18023d469  mov     dword ptr [rsi+108h], 1
0x18023d473  mov     [rsi+110h], r14
0x18023d47a  lea     r12, [rbx+48h]
0x18023d47e  mov     [rsi+2B0h], r12
0x18023d485  mov     rcx, r12; SRWLock
0x18023d488  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023d48d  mov     rax, [rbx+70h]
0x18023d491  mov     [rsi+268h], rax
0x18023d498  test    rax, rax
0x18023d49b  jz      short loc_18023D4E7
0x18023d49d  mov     [rsp+1C8h+var_170], rax
0x18023d4a2  mov     r9, [rax]
0x18023d4a5  mov     rcx, [rsi+268h]
0x18023d4ac  mov     [rsp+1C8h+var_170], rcx
0x18023d4b1  mov     rax, [r9+8]
0x18023d4b5  call    cs:__guard_dispatch_icall_fptr
0x18023d4bb  mov     rcx, r12; SRWLock
0x18023d4be  call    ReleaseSRWLockExclusive_0
0x18023d4c3  lea     r8, [rsi+108h]
0x18023d4ca  mov     rdx, rbx
0x18023d4cd  lea     rcx, [rsi+268h]
0x18023d4d4  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x18023d4d9  lea     rcx, [rsi+268h]
0x18023d4e0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d4e5  jmp     short loc_18023D4EF
0x18023d4e7  mov     rcx, r12; SRWLock
0x18023d4ea  call    ReleaseSRWLockExclusive_0
0x18023d4ef  mov     [rsi+260h], r14
0x18023d4f6  cmp     qword ptr [rsi+0F0h], 0
0x18023d4fe  jnz     short loc_18023D50B
0x18023d500  mov     eax, r14d
0x18023d503  mov     rcx, r14
0x18023d506  mov     rdx, r14
0x18023d509  jmp     short loc_18023D556
0x18023d50b  mov     [rsi+2C0h], r14
0x18023d512  mov     rax, [rsi+0F0h]
0x18023d519  mov     [rsp+1C8h+var_198], rax
0x18023d51e  mov     rcx, [rax]
0x18023d521  mov     rax, [rcx]
0x18023d524  mov     rcx, [rsi+0F0h]
0x18023d52b  mov     [rsp+1C8h+var_198], rcx
0x18023d530  lea     r8, [rsi+2C0h]
0x18023d537  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18023d53e  call    cs:__guard_dispatch_icall_fptr
0x18023d544  mov     rdx, [rsi+2C0h]
0x18023d54b  mov     rcx, rdx
0x18023d54e  mov     [rsp+1C8h+var_120], rdx
0x18023d556  mov     [rsi+270h], rdx
0x18023d55d  lea     rdx, [rsi+278h]
0x18023d564  mov     dword ptr [rdx], 246h
0x18023d56a  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023d571  mov     [rsi+280h], r8
0x18023d578  mov     [rsi+288h], r14
0x18023d57f  test    eax, eax
0x18023d581  jns     short loc_18023D58D
0x18023d583  lfence
0x18023d586  mov     ecx, eax
0x18023d588  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023d58d  mov     dword ptr [rsi+290h], 248h
0x18023d597  mov     [rsi+298h], r8
0x18023d59e  mov     [rsi+2A0h], r14
0x18023d5a5  mov     rax, [rcx]
0x18023d5a8  lea     rdx, [rsi+260h]
0x18023d5af  mov     rax, [rax+50h]
0x18023d5b3  call    cs:__guard_dispatch_icall_fptr
0x18023d5b9  test    eax, eax
0x18023d5bb  jns     short loc_18023D5CF
0x18023d5bd  lfence
0x18023d5c0  lea     rdx, [rsi+290h]
0x18023d5c7  mov     ecx, eax
0x18023d5c9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023d5cf  lea     rcx, [rsi+270h]
0x18023d5d6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d5db  lea     rdx, [rsi+118h]
0x18023d5e2  mov     rax, [rsi+260h]
0x18023d5e9  mov     [rsp+1C8h+var_118], rax
0x18023d5f1  mov     [rdx], rax
0x18023d5f4  mov     eax, [rsi+70h]
0x18023d5f7  cmp     eax, 2
0x18023d5fa  jnz     short loc_18023D63F
0x18023d5fc  lea     rdx, [rsi+248h]; struct winrt::impl::slim_source_location *
0x18023d603  mov     dword ptr [rdx], 1628h
0x18023d609  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023d610  mov     [rsi+250h], rax
0x18023d617  mov     [rsi+258h], r14
0x18023d61e  lea     rcx, [rsp+1C8h+pExceptionObject]; this
0x18023d626  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023d62b  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023d632  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x18023d63a  call    _CxxThrowException
0x18023d63f  lea     rcx, [rsi+120h]
0x18023d646  mov     [rcx], r14
0x18023d649  mov     [rsi+128h], rdx
0x18023d650  mov     [rsi+130h], r14
0x18023d657  mov     byte ptr [rsi+138h], 1
0x18023d65e  mov     eax, 6
0x18023d663  mov     [rsi+98h], ax
0x18023d66a  mov     rdx, rsi
0x18023d66d  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x18023d672  test    al, al
0x18023d674  jz      loc_18023D781
0x18023d67a  jmp     loc_18023D9F9
0x18023d67f  mov     dword ptr [rsi+158h], 0DFh
0x18023d689  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023d690  mov     [rsi+160h], rax
0x18023d697  mov     [rsi+168h], r14
0x18023d69e  lea     rdx, aFailedToMakeGe; "Failed to make generator available for "...
0x18023d6a5  lea     rcx, [rsi+170h]; this
0x18023d6ac  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023d6b1  lea     r8, [rsi+158h]; struct winrt::impl::slim_source_location *
0x18023d6b8  lea     rdx, [rsi+170h]; struct winrt::param::hstring *
0x18023d6bf  lea     rcx, [rsp+1C8h+var_F8]; this
0x18023d6c7  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023d6cc  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18023d6d3  lea     rcx, [rsp+1C8h+var_F8]; pExceptionObject
0x18023d6db  call    _CxxThrowException
0x18023d6e1  cmp     qword ptr [rsi+120h], 0; jumptable 000000018023D1A7 case 7
0x18023d6e9  jz      short loc_18023D717
0x18023d6eb  mov     rbx, [rsi+120h]
0x18023d6f2  mov     qword ptr [rsp+1C8h+var_158], rbx
0x18023d6f7  xor     r14d, r14d
0x18023d6fa  mov     eax, r14d
0x18023d6fd  xchg    rax, [rbx]
0x18023d700  cmp     rax, 1
0x18023d704  jnz     short loc_18023D717
0x18023d706  call    _Thrd_yield
0x18023d70b  mov     rax, r14
0x18023d70e  xchg    rax, [rbx]
0x18023d711  cmp     rax, 1
0x18023d715  jz      short loc_18023D706
0x18023d717  lea     rcx, [rsi+118h]
0x18023d71e  mov     rax, [rcx]
0x18023d721  mov     [rsp+1C8h+var_168], rax
0x18023d726  test    rax, rax
  ... truncated ...
```
