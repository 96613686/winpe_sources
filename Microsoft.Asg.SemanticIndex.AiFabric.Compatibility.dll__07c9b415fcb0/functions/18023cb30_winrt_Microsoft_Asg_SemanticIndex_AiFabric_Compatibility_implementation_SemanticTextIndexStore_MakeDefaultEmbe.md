# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1

- ea: `0x18023cb30`
- end: `0x18023d130`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18004af80`
- `0x18023cb20`

## callees

- `0x180003bd0`
- `0x180003df0`
- `0x18000d230`
- `0x180010dd0`
- `0x18001b680`
- `0x18001b830`
- `0x18001fd50`
- `0x180021690`
- `0x180032bf0`
- `0x180047520`
- `0x18005a7f0`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x18023cb30`
- `0x180242120`

## string_xrefs

- `0x18023cca2`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18023cd3e`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x18023cf21`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x18023cdcd`: `Vector space does not have a model accessor factory registered`
- `0x18023cdb8`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticTextIndexStore.cpp`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticTextIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync__ResumeCoro_1(
        _WORD *a1)
{
  __int64 (__fastcall ***v2)(_QWORD, __int64 *, __int64); // rbx
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // eax
  volatile __int64 *v7; // rbx
  __int64 *v8; // rdi
  volatile __int64 *v9; // rbx
  int v10; // ebx
  __int64 v11; // rcx
  int v12; // eax
  RTL_SRWLOCK *v13; // rbx
  __int64 v14; // r13
  __int64 v15; // rcx
  _QWORD *v16; // rbx
  __int64 v17; // rax
  _BYTE pExceptionObject[24]; // [rsp+50h] [rbp-C8h] BYREF
  _BYTE v19[24]; // [rsp+68h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+80h] [rbp-98h]
  __int64 v21; // [rsp+90h] [rbp-88h]

  switch ( a1[70] )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_49;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_OWORD *)a1 + 20) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(a1 + 76);
      v2 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64))*((_QWORD *)a1 + 19);
      if ( !v2 )
      {
        *((_DWORD *)a1 + 64) = 176;
        *((_QWORD *)a1 + 33) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticTextIndexStore.cpp";
        *((_QWORD *)a1 + 34) = 0;
        winrt::param::hstring::hstring(
          (winrt::param::hstring *)(a1 + 140),
          L"Vector space does not have a model accessor factory registered");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)v19,
          (const struct winrt::param::hstring *)(a1 + 140),
          (const struct winrt::impl::slim_source_location *)(a1 + 128));
        throw (winrt::hresult_invalid_argument *)v19;
      }
      *((_QWORD *)a1 + 68) = a1 + 8;
      *((_QWORD *)a1 + 20) = a1 + 8;
      *((_QWORD *)a1 + 21) = a1 + 8;
      *((_DWORD *)a1 + 44) = 1;
      *((_QWORD *)a1 + 23) = 0;
      *((_QWORD *)a1 + 54) = a1 + 44;
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)a1 + 11);
      v3 = *((_QWORD *)a1 + 16);
      *((_QWORD *)a1 + 48) = v3;
      if ( v3 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
        ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 192,
          a1 + 8,
          a1 + 88);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 192);
      }
      else
      {
        ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
      }
      *((_QWORD *)a1 + 47) = 0;
      *((_QWORD *)a1 + 59) = 0;
      v4 = (**v2)(
             v2,
             winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>,
             (__int64)(a1 + 236));
      v5 = *((_QWORD *)a1 + 59);
      *((_QWORD *)a1 + 49) = v5;
      *((_DWORD *)a1 + 100) = 582;
      *((_QWORD *)a1 + 51) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated "
                             "Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)a1 + 52) = 0;
      if ( v4 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v4, a1 + 200);
      }
      *((_DWORD *)a1 + 112) = 584;
      *((_QWORD *)a1 + 57) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated "
                             "Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
      *((_QWORD *)a1 + 58) = 0;
      v6 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v5 + 80LL))(v5, a1 + 188);
      if ( v6 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v6, a1 + 224);
      }
      winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 196);
      *((_QWORD *)a1 + 24) = *((_QWORD *)a1 + 47);
      if ( *((_DWORD *)a1 + 28) == 2 )
      {
        *((_DWORD *)a1 + 88) = 5672;
        *((_QWORD *)a1 + 45) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Windows.Foundation.h";
        *((_QWORD *)a1 + 46) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 176));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *((_QWORD *)a1 + 25) = 0;
      *((_QWORD *)a1 + 26) = a1 + 96;
      *((_QWORD *)a1 + 27) = 0;
      *((_BYTE *)a1 + 224) = 1;
      a1[70] = 6;
      if ( (unsigned __int8)winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(
                              (_QWORD *)a1 + 25,
                              (__int64)a1) )
        return;
      goto LABEL_25;
    case 6:
LABEL_25:
      v8 = (__int64 *)(a1 + 116);
      winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(
        a1 + 100,
        a1 + 116);
      v9 = (volatile __int64 *)*((_QWORD *)a1 + 25);
      if ( v9 )
      {
        v21 = *((_QWORD *)a1 + 25);
        while ( _InterlockedExchange64(v9, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      v10 = 2;
      v11 = *v8;
      if ( *v8 )
      {
        *((_DWORD *)a1 + 124) = 0;
        *((_DWORD *)a1 + 126) = 1440;
        *((_QWORD *)a1 + 64) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generate"
                               "d Files\\winrt\\Microsoft.Windows.Management.Deployment.h";
        *((_QWORD *)a1 + 65) = 0;
        v12 = (*(__int64 (__fastcall **)(__int64, _WORD *))(*(_QWORD *)v11 + 48LL))(v11, a1 + 248);
        if ( v12 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v12, a1 + 252);
        }
        if ( *((_DWORD *)a1 + 124) != 1 )
          v10 = 3;
      }
      *((_DWORD *)a1 + 60) = v10;
      *((_QWORD *)a1 + 31) = 0x3FF0000000000000LL;
      v20 = *((_OWORD *)a1 + 15);
      *((_OWORD *)a1 + 11) = v20;
      v13 = (RTL_SRWLOCK *)*((_QWORD *)a1 + 54);
      WINRT_IMPL_AcquireSRWLockExclusive(v13);
      v14 = *((_QWORD *)a1 + 21);
      v15 = *(_QWORD *)(v14 + 112);
      *((_QWORD *)a1 + 61) = v15;
      if ( v15 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
        ReleaseSRWLockExclusive_0(v13);
        winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(
          a1 + 244,
          v14,
          a1 + 88);
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 244);
      }
      else
      {
        ReleaseSRWLockExclusive_0(v13);
      }
      WINRT_IMPL_AcquireSRWLockExclusive((PSRWLOCK)a1 + 11);
      v16 = a1 + 60;
      if ( a1 + 60 != (_WORD *)v8 )
      {
        if ( *v16 )
          winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 60);
        v17 = *v8;
        *v8 = 0;
        *v16 = v17;
      }
      ReleaseSRWLockExclusive_0((PSRWLOCK)a1 + 11);
      if ( *v8 )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 116);
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 76);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
      *((_QWORD *)a1 + 39) = *((_QWORD *)a1 + 68);
      a1[70] = 0;
      *(_QWORD *)a1 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>::final_suspend_awaiter::await_suspend() )
        goto LABEL_49;
      return;
    case 7:
      v7 = (volatile __int64 *)*((_QWORD *)a1 + 25);
      if ( v7 )
      {
        v21 = *((_QWORD *)a1 + 25);
        while ( _InterlockedExchange64(v7, 0) == 1 )
          Thrd_yield();
      }
      if ( *((_QWORD *)a1 + 24) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 96);
      if ( *((_QWORD *)a1 + 19) )
        winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(a1 + 76);
      if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
        abort();
LABEL_49:
      std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type::~promise_type(a1 + 8);
      if ( a1[71] )
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
0x18023cb30  mov     [rsp+Block], rcx
0x18023cb35  push    rbx
0x18023cb36  push    rsi
0x18023cb37  push    rdi
0x18023cb38  push    r12
0x18023cb3a  push    r13
0x18023cb3c  push    r14
0x18023cb3e  push    r15
0x18023cb40  sub     rsp, 0E0h
0x18023cb47  mov     rsi, [rsp+118h+Block]
0x18023cb4f  movzx   eax, word ptr [rsi+8Ch]
0x18023cb56  mov     [rsp+118h+var_F8], ax
0x18023cb5b  inc     ax; switch 9 cases
0x18023cb5e  cmp     ax, 8
0x18023cb62  ja      def_18023CB7D; jumptable 000000018023CB7D default case, cases 0,4,5
0x18023cb68  movsx   rax, ax
0x18023cb6c  lea     rdx, cs:180000000h
0x18023cb73  mov     ecx, ds:(jpt_18023CB7D - 180000000h)[rdx+rax*4]
0x18023cb7a  add     rcx, rdx
0x18023cb7d  jmp     rcx; switch jump
0x18023cb7f  jmp     loc_18023D0D2; jumptable 000000018023CB7D case 3
0x18023cb84  xor     r14d, r14d; jumptable 000000018023CB7D case 2
0x18023cb87  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023cb8e  lea     rdx, [rsi+140h]
0x18023cb95  movups  xmm0, cs:?VectorSpaceId@SpaceV6@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SpaceV6::VectorSpaceId
0x18023cb9c  movaps  xmmword ptr [rdx], xmm0
0x18023cb9f  lea     rcx, [rsi+98h]
0x18023cba6  call    ?TryGetTextEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUITextEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(winrt::guid)
0x18023cbab  nop
0x18023cbac  mov     rbx, [rsi+98h]
0x18023cbb3  test    rbx, rbx
0x18023cbb6  jz      loc_18023CDAE
0x18023cbbc  lea     rdi, [rsi+10h]
0x18023cbc0  mov     [rsi+220h], rdi
0x18023cbc7  mov     [rsi+0A0h], rdi
0x18023cbce  mov     [rsi+0A8h], rdi
0x18023cbd5  mov     dword ptr [rsi+0B0h], 1
0x18023cbdf  mov     [rsi+0B8h], r14
0x18023cbe6  lea     r15, [rdi+48h]
0x18023cbea  mov     [rsi+1B0h], r15
0x18023cbf1  mov     rcx, r15; SRWLock
0x18023cbf4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023cbf9  mov     rcx, [rdi+70h]
0x18023cbfd  mov     [rsi+180h], rcx
0x18023cc04  test    rcx, rcx
0x18023cc07  jz      short loc_18023CC47
0x18023cc09  mov     [rsp+118h+var_E8], rcx
0x18023cc0e  mov     rax, [rcx]
0x18023cc11  mov     rax, [rax+8]
0x18023cc15  call    cs:__guard_dispatch_icall_fptr
0x18023cc1b  mov     rcx, r15; SRWLock
0x18023cc1e  call    ReleaseSRWLockExclusive_0
0x18023cc23  lea     r8, [rsi+0B0h]
0x18023cc2a  mov     rdx, rdi
0x18023cc2d  lea     rcx, [rsi+180h]
0x18023cc34  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x18023cc39  lea     rcx, [rsi+180h]
0x18023cc40  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023cc45  jmp     short loc_18023CC4F
0x18023cc47  mov     rcx, r15; SRWLock
0x18023cc4a  call    ReleaseSRWLockExclusive_0
0x18023cc4f  mov     [rsi+178h], r14
0x18023cc56  mov     [rsi+1D8h], r14
0x18023cc5d  mov     [rsp+118h+arg_10], rbx
0x18023cc65  mov     rax, [rbx]
0x18023cc68  lea     r8, [rsi+1D8h]
0x18023cc6f  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x18023cc76  mov     rcx, rbx
0x18023cc79  mov     rax, [rax]
0x18023cc7c  call    cs:__guard_dispatch_icall_fptr
0x18023cc82  mov     rcx, [rsi+1D8h]
0x18023cc89  mov     [rsp+118h+var_E0], rcx
0x18023cc8e  mov     [rsi+188h], rcx
0x18023cc95  lea     rdx, [rsi+190h]
0x18023cc9c  mov     dword ptr [rdx], 246h
0x18023cca2  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023cca9  mov     [rsi+198h], r8
0x18023ccb0  mov     [rsi+1A0h], r14
0x18023ccb7  test    eax, eax
0x18023ccb9  jns     short loc_18023CCC5
0x18023ccbb  lfence
0x18023ccbe  mov     ecx, eax
0x18023ccc0  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023ccc5  mov     dword ptr [rsi+1C0h], 248h
0x18023cccf  mov     [rsi+1C8h], r8
0x18023ccd6  mov     [rsi+1D0h], r14
0x18023ccdd  mov     rax, [rcx]
0x18023cce0  lea     rdx, [rsi+178h]
0x18023cce7  mov     rax, [rax+50h]
0x18023cceb  call    cs:__guard_dispatch_icall_fptr
0x18023ccf1  test    eax, eax
0x18023ccf3  jns     short loc_18023CD07
0x18023ccf5  lfence
0x18023ccf8  lea     rdx, [rsi+1C0h]
0x18023ccff  mov     ecx, eax
0x18023cd01  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023cd07  lea     rcx, [rsi+188h]
0x18023cd0e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023cd13  lea     rdx, [rsi+0C0h]
0x18023cd1a  mov     rax, [rsi+178h]
0x18023cd21  mov     [rsp+118h+var_D8], rax
0x18023cd26  mov     [rdx], rax
0x18023cd29  mov     eax, [rsi+70h]
0x18023cd2c  cmp     eax, 2
0x18023cd2f  jnz     short loc_18023CD6E
0x18023cd31  lea     rdx, [rsi+160h]; struct winrt::impl::slim_source_location *
0x18023cd38  mov     dword ptr [rdx], 1628h
0x18023cd3e  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023cd45  mov     [rsi+168h], rax
0x18023cd4c  mov     [rsi+170h], r14
0x18023cd53  lea     rcx, [rsp+118h+pExceptionObject]; this
0x18023cd58  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023cd5d  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18023cd64  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x18023cd69  call    _CxxThrowException
0x18023cd6e  lea     rcx, [rsi+0C8h]
0x18023cd75  mov     [rcx], r14
0x18023cd78  mov     [rsi+0D0h], rdx
0x18023cd7f  mov     [rsi+0D8h], r14
0x18023cd86  mov     byte ptr [rsi+0E0h], 1
0x18023cd8d  mov     eax, 6
0x18023cd92  mov     [rsi+8Ch], ax
0x18023cd99  mov     rdx, rsi
0x18023cd9c  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x18023cda1  test    al, al
0x18023cda3  jz      loc_18023CE9F
0x18023cda9  jmp     loc_18023D0F5
0x18023cdae  mov     dword ptr [rsi+100h], 0B0h
0x18023cdb8  lea     rax, aCW1SSrcSemanti_28; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023cdbf  mov     [rsi+108h], rax
0x18023cdc6  mov     [rsi+110h], r14
0x18023cdcd  lea     rdx, aVectorSpaceDoe; "Vector space does not have a model acce"...
0x18023cdd4  lea     rcx, [rsi+118h]; this
0x18023cddb  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18023cde0  lea     r8, [rsi+100h]; struct winrt::impl::slim_source_location *
0x18023cde7  lea     rdx, [rsi+118h]; struct winrt::param::hstring *
0x18023cdee  lea     rcx, [rsp+118h+var_B0]; this
0x18023cdf3  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18023cdf8  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18023cdff  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x18023ce04  call    _CxxThrowException
0x18023ce0a  mov     rbx, [rsi+0C8h]; jumptable 000000018023CB7D case 7
0x18023ce11  test    rbx, rbx
0x18023ce14  jz      short loc_18023CE41
0x18023ce16  mov     [rsp+118h+var_88], rbx
0x18023ce1e  xor     r14d, r14d
0x18023ce21  mov     eax, r14d
0x18023ce24  xchg    rax, [rbx]
0x18023ce27  cmp     rax, 1
0x18023ce2b  jnz     short loc_18023CE41
0x18023ce2d  nop     dword ptr [rax]
0x18023ce30  call    _Thrd_yield
0x18023ce35  mov     rax, r14
0x18023ce38  xchg    rax, [rbx]
0x18023ce3b  cmp     rax, 1
0x18023ce3f  jz      short loc_18023CE30
0x18023ce41  lea     rcx, [rsi+0C0h]
0x18023ce48  mov     rax, [rcx]
0x18023ce4b  mov     [rsp+118h+arg_18], rax
0x18023ce53  test    rax, rax
0x18023ce56  jz      short loc_18023CE5E
0x18023ce58  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ce5d  nop
0x18023ce5e  lea     rcx, [rsi+98h]
0x18023ce65  mov     rax, [rcx]
0x18023ce68  mov     [rsp+118h+arg_10], rax
0x18023ce70  test    rax, rax
0x18023ce73  jz      short loc_18023CE7B
0x18023ce75  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023ce7a  nop
0x18023ce7b  mov     eax, 0FFFFFFFFh
0x18023ce80  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023ce88  sub     eax, 1
0x18023ce8b  jz      short loc_18023CE97
0x18023ce8d  test    eax, eax
0x18023ce8f  jns     short loc_18023CE97
0x18023ce91  call    abort
0x18023ce97  jmp     loc_18023D0D2; jumptable 000000018023CB7D cases -1,1
0x18023ce9c  xor     r14d, r14d; jumptable 000000018023CB7D case 6
0x18023ce9f  lea     rdi, [rsi+0E8h]
0x18023cea6  mov     rdx, rdi
0x18023cea9  lea     rcx, [rsi+0C8h]
0x18023ceb0  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x18023ceb5  nop
0x18023ceb6  mov     rbx, [rsi+0C8h]
0x18023cebd  test    rbx, rbx
0x18023cec0  jz      short loc_18023CEE7
0x18023cec2  mov     [rsp+118h+var_88], rbx
0x18023ceca  mov     rax, r14
0x18023cecd  xchg    rax, [rbx]
0x18023ced0  cmp     rax, 1
0x18023ced4  jnz     short loc_18023CEE7
0x18023ced6  call    _Thrd_yield
0x18023cedb  mov     rax, r14
0x18023cede  xchg    rax, [rbx]
0x18023cee1  cmp     rax, 1
0x18023cee5  jz      short loc_18023CED6
0x18023cee7  lea     rcx, [rsi+0C0h]
0x18023ceee  mov     rax, [rcx]
0x18023cef1  mov     [rsp+118h+arg_18], rax
0x18023cef9  test    rax, rax
0x18023cefc  jz      short loc_18023CF03
0x18023cefe  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023cf03  mov     ebx, 2
0x18023cf08  mov     rcx, [rdi]
0x18023cf0b  test    rcx, rcx
0x18023cf0e  jz      short loc_18023CF7C
0x18023cf10  mov     [rsi+1F0h], r14d
0x18023cf17  mov     dword ptr [rsi+1F8h], 5A0h
0x18023cf21  lea     rax, aCW1SX64Release_14; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x18023cf28  mov     [rsi+200h], rax
0x18023cf2f  mov     [rsi+208h], r14
0x18023cf36  mov     [rsp+118h+var_F0], rcx
0x18023cf3b  mov     rax, [rcx]
0x18023cf3e  lea     rdx, [rsi+1F0h]
0x18023cf45  mov     rax, [rax+30h]
0x18023cf49  call    cs:__guard_dispatch_icall_fptr
0x18023cf4f  test    eax, eax
0x18023cf51  jns     short loc_18023CF64
0x18023cf53  lfence
0x18023cf56  lea     rdx, [rsi+1F8h]
0x18023cf5d  mov     ecx, eax
0x18023cf5f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18023cf64  mov     eax, [rsi+1F0h]
0x18023cf6a  mov     [rsp+118h+arg_8], eax
0x18023cf71  mov     ecx, 3
0x18023cf76  cmp     eax, 1
0x18023cf79  cmovnz  ebx, ecx
0x18023cf7c  mov     [rsi+0F0h], ebx
0x18023cf82  mov     rax, 3FF0000000000000h
0x18023cf8c  mov     [rsi+0F8h], rax
0x18023cf93  movups  xmm0, xmmword ptr [rsi+0F0h]
0x18023cf9a  movups  [rsp+118h+var_98], xmm0
0x18023cfa2  movups  xmmword ptr [rsi+0B0h], xmm0
0x18023cfa9  mov     rbx, [rsi+1B0h]
0x18023cfb0  mov     rcx, rbx; SRWLock
0x18023cfb3  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023cfb8  mov     r13, [rsi+0A8h]
0x18023cfbf  mov     rcx, [r13+70h]
0x18023cfc3  mov     [rsi+1E8h], rcx
0x18023cfca  test    rcx, rcx
0x18023cfcd  jz      short loc_18023D00D
0x18023cfcf  mov     [rsp+118h+var_D0], rcx
0x18023cfd4  mov     rax, [rcx]
0x18023cfd7  mov     rax, [rax+8]
0x18023cfdb  call    cs:__guard_dispatch_icall_fptr
0x18023cfe1  mov     rcx, rbx; SRWLock
0x18023cfe4  call    ReleaseSRWLockExclusive_0
0x18023cfe9  lea     r8, [rsi+0B0h]
0x18023cff0  mov     rdx, r13
0x18023cff3  lea     rcx, [rsi+1E8h]
0x18023cffa  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x18023cfff  lea     rcx, [rsi+1E8h]
0x18023d006  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d00b  jmp     short loc_18023D015
0x18023d00d  mov     rcx, rbx; SRWLock
0x18023d010  call    ReleaseSRWLockExclusive_0
0x18023d015  lea     rcx, [rsi+58h]; SRWLock
0x18023d019  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18023d01e  lea     rbx, [rsi+78h]
0x18023d022  cmp     rbx, rdi
0x18023d025  jz      short loc_18023D03E
0x18023d027  cmp     qword ptr [rbx], 0
0x18023d02b  jz      short loc_18023D035
0x18023d02d  mov     rcx, rbx
0x18023d030  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d035  mov     rax, [rdi]
0x18023d038  mov     [rdi], r14
0x18023d03b  mov     [rbx], rax
0x18023d03e  lea     rcx, [rsi+58h]; SRWLock
0x18023d042  call    ReleaseSRWLockExclusive_0
0x18023d047  nop
0x18023d048  mov     rax, [rdi]
0x18023d04b  mov     [rsp+118h+var_F0], rax
0x18023d050  test    rax, rax
0x18023d053  jz      short loc_18023D062
0x18023d055  lea     rcx, [rsi+0E8h]
0x18023d05c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d061  nop
0x18023d062  lea     rcx, [rsi+98h]
0x18023d069  mov     rax, [rcx]
0x18023d06c  mov     [rsp+118h+arg_10], rax
0x18023d074  test    rax, rax
0x18023d077  jz      short loc_18023D07F
0x18023d079  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023d07e  nop
0x18023d07f  mov     eax, 0FFFFFFFFh
0x18023d084  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023d08c  sub     eax, 1
0x18023d08f  jz      short loc_18023D09B
0x18023d091  test    eax, eax
0x18023d093  jns     short loc_18023D09B
0x18023d095  call    abort
0x18023d09b  mov     rax, [rsi+220h]
0x18023d0a2  jmp     short loc_18023D0B3
0x18023d0a4  mov     rsi, [rsp+118h+Block]
0x18023d0ac  lea     rax, [rsi+10h]
0x18023d0b0  xor     r14d, r14d
0x18023d0b3  lea     rcx, [rsi+138h]
0x18023d0ba  mov     [rcx], rax
  ... truncated ...
```
