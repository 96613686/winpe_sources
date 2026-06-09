# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1

- ea: `0x1802343f0`
- end: `0x180234cfc`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync$_ResumeCoro$1`
- size: `2316`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c560`
- `0x1802343e0`

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
- `0x18005a4b0`
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
- `0x1802343f0`
- `0x180242120`

## string_xrefs

- `0x180234544`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1802345ca`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023481a`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1802344cc`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802348b9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180234ab9`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x180234939`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeEmbeddingsGeneratorAvailableForOptionsAsync__ResumeCoro_1(
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
      goto LABEL_69;
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
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetImageEmbeddingsModelFactory(
        Block + 240,
        Block + 544);
      if ( !*((_QWORD *)Block + 30) )
      {
        *((_DWORD *)Block + 86) = 354;
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
      goto LABEL_45;
    case 6:
LABEL_45:
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
        goto LABEL_69;
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
LABEL_69:
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
0x1802343f0  mov     r11, rsp
0x1802343f3  mov     [r11+10h], rbx
0x1802343f7  mov     [r11+18h], rsi
0x1802343fb  mov     [r11+8], rcx
0x1802343ff  push    rdi
0x180234400  push    r12
0x180234402  push    r13
0x180234404  push    r14
0x180234406  push    r15
0x180234408  sub     rsp, 1A0h
0x18023440f  mov     rax, cs:__security_cookie
0x180234416  xor     rax, rsp
0x180234419  mov     [rsp+1C8h+var_30], rax
0x180234421  mov     rsi, rcx
0x180234424  mov     [rsp+1C8h+var_188], rcx
0x180234429  movzx   eax, word ptr [rsi+98h]
0x180234430  mov     [rsp+1C8h+var_190], ax
0x180234435  inc     ax; switch 9 cases
0x180234438  cmp     ax, 8
0x18023443c  ja      def_180234457; jumptable 0000000180234457 default case, cases 0,4,5
0x180234442  movsx   rax, ax
0x180234446  lea     rdx, cs:180000000h
0x18023444d  mov     ecx, ds:(jpt_180234457 - 180000000h)[rdx+rax*4]
0x180234454  add     rcx, rdx
0x180234457  jmp     rcx; switch jump
0x180234459  jmp     loc_180234C74; jumptable 0000000180234457 case 3
0x18023445e  xor     r14d, r14d; jumptable 0000000180234457 case 2
0x180234461  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180234468  mov     rcx, [rsi+90h]
0x18023446f  mov     [rsi+0A0h], rcx
0x180234476  test    rcx, rcx
0x180234479  jz      short loc_180234488
0x18023447b  mov     rax, [rcx]
0x18023447e  mov     rax, [rax+8]
0x180234482  call    cs:__guard_dispatch_icall_fptr
0x180234488  lea     rcx, [rsi+0A8h]
0x18023448f  lea     rdx, [rsi+0A0h]
0x180234496  call    ?GetDbAesKeyStore@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUDbAesKeyStore@Sqlite@asg@@USemanticImageIndexStoreOptions@234567@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::GetDbAesKeyStore(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions)
0x18023449b  nop
0x18023449c  lea     rdx, [rsi+0C8h]
0x1802344a3  lea     rcx, [rsi+90h]
0x1802344aa  call    ?VectorSpaceId@?$consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticImageIndexStoreOptions4@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Microsoft_Asg_SemanticIndex_AiFabric_Compatibility_ISemanticImageIndexStoreOptions4<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::VectorSpaceId(void)
0x1802344af  nop
0x1802344b0  mov     rcx, [rax]
0x1802344b3  test    rcx, rcx
0x1802344b6  jz      short loc_180234524
0x1802344b8  xorps   xmm0, xmm0
0x1802344bb  movups  xmmword ptr [rsi+1B8h], xmm0
0x1802344c2  mov     dword ptr [rsi+1C8h], 7C0h
0x1802344cc  lea     r13, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802344d3  mov     [rsi+1D0h], r13
0x1802344da  mov     [rsi+1D8h], r14
0x1802344e1  mov     rax, [rcx]
0x1802344e4  lea     rdx, [rsi+1B8h]
0x1802344eb  mov     rax, [rax+30h]
0x1802344ef  call    cs:__guard_dispatch_icall_fptr
0x1802344f5  test    eax, eax
0x1802344f7  jns     short loc_18023450A
0x1802344f9  lfence
0x1802344fc  lea     rdx, [rsi+1C8h]
0x180234503  mov     ecx, eax
0x180234505  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023450a  movups  xmm0, xmmword ptr [rsi+1B8h]
0x180234511  movups  [rsp+1C8h+var_88], xmm0
0x180234519  movups  xmmword ptr [rsi+0D0h], xmm0
0x180234520  mov     al, 1
0x180234522  jmp     short loc_180234526
0x180234524  xor     al, al
0x180234526  mov     [rsi+0E0h], al
0x18023452c  mov     [rsi+1B0h], r14d
0x180234533  mov     rcx, [rsi+90h]
0x18023453a  mov     dword ptr [rsi+1E0h], 73Fh
0x180234544  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023454b  mov     [rsi+1E8h], rax
0x180234552  mov     [rsi+1F0h], r14
0x180234559  mov     rax, [rcx]
0x18023455c  lea     rdx, [rsi+1B0h]
0x180234563  mov     rax, [rax+38h]
0x180234567  call    cs:__guard_dispatch_icall_fptr
0x18023456d  test    eax, eax
0x18023456f  jns     short loc_180234582
0x180234571  lfence
0x180234574  lea     rdx, [rsi+1E0h]
0x18023457b  mov     ecx, eax
0x18023457d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234582  mov     rax, [rsi+0B0h]
0x180234589  mov     [rsp+1C8h+var_198], rax
0x18023458e  mov     r13, [rsi+0B8h]
0x180234595  mov     [rsp+1C8h+var_C0], r13
0x18023459d  mov     rax, [rsi+0B0h]
0x1802345a4  mov     [rsp+1C8h+var_C8], rax
0x1802345ac  sub     r13, rax
0x1802345af  lea     rbx, [rsi+1F8h]
0x1802345b6  mov     [rbx], r14
0x1802345b9  mov     rcx, [rsi+90h]
0x1802345c0  mov     dword ptr [rsi+200h], 72Dh
0x1802345ca  lea     rax, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802345d1  mov     [rsi+208h], rax
0x1802345d8  mov     [rsi+210h], r14
0x1802345df  mov     rax, [rcx]
0x1802345e2  mov     rdx, rbx
0x1802345e5  mov     rax, [rax+30h]
0x1802345e9  call    cs:__guard_dispatch_icall_fptr
0x1802345ef  test    eax, eax
0x1802345f1  jns     short loc_180234604
0x1802345f3  lfence
0x1802345f6  lea     rdx, [rsi+200h]
0x1802345fd  mov     ecx, eax
0x1802345ff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234604  lea     rdx, [rsi+0E8h]
0x18023460b  mov     rax, [rbx]
0x18023460e  mov     [rdx], rax
0x180234611  lea     r8, [rsi+1A0h]
0x180234618  mov     rax, [rsp+1C8h+var_198]
0x18023461d  mov     [r8], rax
0x180234620  mov     [rsi+1A8h], r13
0x180234627  mov     r9d, [rsi+1B0h]
0x18023462e  mov     [rsp+1C8h+var_18C], r9d
0x180234633  lea     rax, [rsi+0D0h]
0x18023463a  lea     rcx, ?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x180234641  mov     [rsp+1C8h+var_1A0], rcx
0x180234646  mov     [rsp+1C8h+var_1A8], rax
0x18023464b  lea     rcx, [rsp+1C8h+var_B0]
0x180234653  call    ?ResolveCurrentAndPreviousVectorSpace@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUVectorSpaceResolution@1234567@AEBUhstring@7@V?$span@$$CBE$0?0@std@@W4IndexCreationDisposition@234567@AEBV?$optional@Uguid@winrt@@@std@@AEBUguid@7@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ResolveCurrentAndPreviousVectorSpace(winrt::hstring const &,std::span<uchar const,-1>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexCreationDisposition,std::optional<winrt::guid> const &,winrt::guid const &)
0x180234658  movups  xmm0, xmmword ptr [rax]
0x18023465b  movups  [rsp+1C8h+var_158], xmm0
0x180234660  movups  xmm1, xmmword ptr [rax+10h]
0x180234664  movups  [rsp+1C8h+var_148], xmm1
0x18023466c  movsd   xmm0, qword ptr [rax+20h]
0x180234671  movsd   [rsp+1C8h+var_138], xmm0
0x18023467a  mov     edi, 0FFFFFFFFh
0x18023467f  cmp     qword ptr [rbx], 0
0x180234683  jz      short loc_1802346BD
0x180234685  mov     rcx, [rbx]
0x180234688  mov     eax, edi
0x18023468a  lock xadd [rcx+18h], eax
0x18023468f  sub     eax, 1
0x180234692  jnz     short loc_1802346B3
0x180234694  mov     rbx, [rbx]
0x180234697  mov     [rsp+1C8h+var_130], rbx
0x18023469f  call    WINRT_IMPL_GetProcessHeap
0x1802346a4  mov     rcx, rax; hHeap
0x1802346a7  mov     r8, rbx; lpMem
0x1802346aa  xor     edx, edx; dwFlags
0x1802346ac  call    WINRT_IMPL_HeapFree
0x1802346b1  jmp     short loc_1802346BD
0x1802346b3  test    eax, eax
0x1802346b5  jns     short loc_1802346BD
0x1802346b7  call    abort
0x1802346bd  mov     rax, [rsi+0C8h]
0x1802346c4  mov     [rsp+1C8h+var_128], rax
0x1802346cc  test    rax, rax
0x1802346cf  jz      short loc_1802346DD
0x1802346d1  lea     rcx, [rsi+0C8h]
0x1802346d8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802346dd  lea     rdx, [rsi+220h]
0x1802346e4  movups  xmm0, [rsp+1C8h+var_158+4]
0x1802346e9  movaps  xmmword ptr [rdx], xmm0
0x1802346ec  lea     rcx, [rsi+0F0h]
0x1802346f3  call    ?TryGetImageEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUIImageEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetImageEmbeddingsModelFactory(winrt::guid)
0x1802346f8  nop
0x1802346f9  cmp     qword ptr [rsi+0F0h], 0
0x180234701  jz      loc_18023492F
0x180234707  lea     rbx, [rsi+10h]
0x18023470b  mov     [rsi+0F8h], rbx
0x180234712  mov     [rsi+100h], rbx
0x180234719  mov     dword ptr [rsi+108h], 1
0x180234723  mov     [rsi+110h], r14
0x18023472a  lea     r12, [rbx+48h]
0x18023472e  mov     [rsi+2B0h], r12
0x180234735  mov     rcx, r12; SRWLock
0x180234738  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023473d  mov     rax, [rbx+70h]
0x180234741  mov     [rsi+268h], rax
0x180234748  test    rax, rax
0x18023474b  jz      short loc_180234797
0x18023474d  mov     [rsp+1C8h+var_170], rax
0x180234752  mov     r9, [rax]
0x180234755  mov     rcx, [rsi+268h]
0x18023475c  mov     [rsp+1C8h+var_170], rcx
0x180234761  mov     rax, [r9+8]
0x180234765  call    cs:__guard_dispatch_icall_fptr
0x18023476b  mov     rcx, r12; SRWLock
0x18023476e  call    ReleaseSRWLockExclusive_0
0x180234773  lea     r8, [rsi+108h]
0x18023477a  mov     rdx, rbx
0x18023477d  lea     rcx, [rsi+268h]
0x180234784  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x180234789  lea     rcx, [rsi+268h]
0x180234790  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180234795  jmp     short loc_18023479F
0x180234797  mov     rcx, r12; SRWLock
0x18023479a  call    ReleaseSRWLockExclusive_0
0x18023479f  mov     [rsi+260h], r14
0x1802347a6  cmp     qword ptr [rsi+0F0h], 0
0x1802347ae  jnz     short loc_1802347BB
0x1802347b0  mov     eax, r14d
0x1802347b3  mov     rcx, r14
0x1802347b6  mov     rdx, r14
0x1802347b9  jmp     short loc_180234806
0x1802347bb  mov     [rsi+2C0h], r14
0x1802347c2  mov     rax, [rsi+0F0h]
0x1802347c9  mov     [rsp+1C8h+var_198], rax
0x1802347ce  mov     rcx, [rax]
0x1802347d1  mov     rax, [rcx]
0x1802347d4  mov     rcx, [rsi+0F0h]
0x1802347db  mov     [rsp+1C8h+var_198], rcx
0x1802347e0  lea     r8, [rsi+2C0h]
0x1802347e7  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x1802347ee  call    cs:__guard_dispatch_icall_fptr
0x1802347f4  mov     rdx, [rsi+2C0h]
0x1802347fb  mov     rcx, rdx
0x1802347fe  mov     [rsp+1C8h+var_120], rdx
0x180234806  mov     [rsi+270h], rdx
0x18023480d  lea     rdx, [rsi+278h]
0x180234814  mov     dword ptr [rdx], 246h
0x18023481a  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180234821  mov     [rsi+280h], r8
0x180234828  mov     [rsi+288h], r14
0x18023482f  test    eax, eax
0x180234831  jns     short loc_18023483D
0x180234833  lfence
0x180234836  mov     ecx, eax
0x180234838  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023483d  mov     dword ptr [rsi+290h], 248h
0x180234847  mov     [rsi+298h], r8
0x18023484e  mov     [rsi+2A0h], r14
0x180234855  mov     rax, [rcx]
0x180234858  lea     rdx, [rsi+260h]
0x18023485f  mov     rax, [rax+50h]
0x180234863  call    cs:__guard_dispatch_icall_fptr
0x180234869  test    eax, eax
0x18023486b  jns     short loc_18023487F
0x18023486d  lfence
0x180234870  lea     rdx, [rsi+290h]
0x180234877  mov     ecx, eax
0x180234879  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023487f  lea     rcx, [rsi+270h]
0x180234886  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023488b  lea     rdx, [rsi+118h]
0x180234892  mov     rax, [rsi+260h]
0x180234899  mov     [rsp+1C8h+var_118], rax
0x1802348a1  mov     [rdx], rax
0x1802348a4  mov     eax, [rsi+70h]
0x1802348a7  cmp     eax, 2
0x1802348aa  jnz     short loc_1802348EF
0x1802348ac  lea     rdx, [rsi+248h]; struct winrt::impl::slim_source_location *
0x1802348b3  mov     dword ptr [rdx], 1628h
0x1802348b9  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802348c0  mov     [rsi+250h], rax
0x1802348c7  mov     [rsi+258h], r14
0x1802348ce  lea     rcx, [rsp+1C8h+pExceptionObject]; this
0x1802348d6  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802348db  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x1802348e2  lea     rcx, [rsp+1C8h+pExceptionObject]; pExceptionObject
0x1802348ea  call    _CxxThrowException
0x1802348ef  lea     rcx, [rsi+120h]
0x1802348f6  mov     [rcx], r14
0x1802348f9  mov     [rsi+128h], rdx
0x180234900  mov     [rsi+130h], r14
0x180234907  mov     byte ptr [rsi+138h], 1
0x18023490e  mov     eax, 6
0x180234913  mov     [rsi+98h], ax
0x18023491a  mov     rdx, rsi
0x18023491d  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x180234922  test    al, al
0x180234924  jz      loc_180234A31
0x18023492a  jmp     loc_180234CA9
0x18023492f  mov     dword ptr [rsi+158h], 162h
0x180234939  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180234940  mov     [rsi+160h], rax
0x180234947  mov     [rsi+168h], r14
0x18023494e  lea     rdx, aFailedToMakeGe; "Failed to make generator available for "...
0x180234955  lea     rcx, [rsi+170h]; this
0x18023495c  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180234961  lea     r8, [rsi+158h]; struct winrt::impl::slim_source_location *
0x180234968  lea     rdx, [rsi+170h]; struct winrt::param::hstring *
0x18023496f  lea     rcx, [rsp+1C8h+var_F8]; this
0x180234977  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023497c  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180234983  lea     rcx, [rsp+1C8h+var_F8]; pExceptionObject
0x18023498b  call    _CxxThrowException
0x180234991  cmp     qword ptr [rsi+120h], 0; jumptable 0000000180234457 case 7
0x180234999  jz      short loc_1802349C7
0x18023499b  mov     rbx, [rsi+120h]
0x1802349a2  mov     qword ptr [rsp+1C8h+var_158], rbx
0x1802349a7  xor     r14d, r14d
0x1802349aa  mov     eax, r14d
0x1802349ad  xchg    rax, [rbx]
0x1802349b0  cmp     rax, 1
0x1802349b4  jnz     short loc_1802349C7
0x1802349b6  call    _Thrd_yield
0x1802349bb  mov     rax, r14
0x1802349be  xchg    rax, [rbx]
0x1802349c1  cmp     rax, 1
0x1802349c5  jz      short loc_1802349B6
0x1802349c7  lea     rcx, [rsi+118h]
0x1802349ce  mov     rax, [rcx]
0x1802349d1  mov     [rsp+1C8h+var_168], rax
0x1802349d6  test    rax, rax
  ... truncated ...
```
