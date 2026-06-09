# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultTextQueryEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1

- ea: `0x180233de0`
- end: `0x1802343e0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultTextQueryEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ca40`
- `0x180233dd0`

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
- `0x180233de0`
- `0x180242120`

## string_xrefs

- `0x180233f52`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180233fee`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x1802341d1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x180234068`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`
- `0x18023407d`: `Vector space does not have a model accessor factory registered`

## pseudocode

```c
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultTextQueryEmbeddingsGeneratorAvailableAsync__ResumeCoro_1(
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
      *((_OWORD *)a1 + 20) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(a1 + 76);
      v2 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64))*((_QWORD *)a1 + 19);
      if ( !v2 )
      {
        *((_DWORD *)a1 + 64) = 437;
        *((_QWORD *)a1 + 33) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\SemanticImageIndexStore.cpp";
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
0x180233de0  mov     [rsp+Block], rcx
0x180233de5  push    rbx
0x180233de6  push    rsi
0x180233de7  push    rdi
0x180233de8  push    r12
0x180233dea  push    r13
0x180233dec  push    r14
0x180233dee  push    r15
0x180233df0  sub     rsp, 0E0h
0x180233df7  mov     rsi, [rsp+118h+Block]
0x180233dff  movzx   eax, word ptr [rsi+8Ch]
0x180233e06  mov     [rsp+118h+var_F8], ax
0x180233e0b  inc     ax; switch 9 cases
0x180233e0e  cmp     ax, 8
0x180233e12  ja      def_180233E2D; jumptable 0000000180233E2D default case, cases 0,4,5
0x180233e18  movsx   rax, ax
0x180233e1c  lea     rdx, cs:180000000h
0x180233e23  mov     ecx, ds:(jpt_180233E2D - 180000000h)[rdx+rax*4]
0x180233e2a  add     rcx, rdx
0x180233e2d  jmp     rcx; switch jump
0x180233e2f  jmp     loc_180234382; jumptable 0000000180233E2D case 3
0x180233e34  xor     r14d, r14d; jumptable 0000000180233E2D case 2
0x180233e37  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180233e3e  lea     rdx, [rsi+140h]
0x180233e45  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x180233e4c  movaps  xmmword ptr [rdx], xmm0
0x180233e4f  lea     rcx, [rsi+98h]
0x180233e56  call    ?TryGetTextEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUITextEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetTextEmbeddingsModelFactory(winrt::guid)
0x180233e5b  nop
0x180233e5c  mov     rbx, [rsi+98h]
0x180233e63  test    rbx, rbx
0x180233e66  jz      loc_18023405E
0x180233e6c  lea     rdi, [rsi+10h]
0x180233e70  mov     [rsi+220h], rdi
0x180233e77  mov     [rsi+0A0h], rdi
0x180233e7e  mov     [rsi+0A8h], rdi
0x180233e85  mov     dword ptr [rsi+0B0h], 1
0x180233e8f  mov     [rsi+0B8h], r14
0x180233e96  lea     r15, [rdi+48h]
0x180233e9a  mov     [rsi+1B0h], r15
0x180233ea1  mov     rcx, r15; SRWLock
0x180233ea4  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180233ea9  mov     rcx, [rdi+70h]
0x180233ead  mov     [rsi+180h], rcx
0x180233eb4  test    rcx, rcx
0x180233eb7  jz      short loc_180233EF7
0x180233eb9  mov     [rsp+118h+var_E8], rcx
0x180233ebe  mov     rax, [rcx]
0x180233ec1  mov     rax, [rax+8]
0x180233ec5  call    cs:__guard_dispatch_icall_fptr
0x180233ecb  mov     rcx, r15; SRWLock
0x180233ece  call    ReleaseSRWLockExclusive_0
0x180233ed3  lea     r8, [rsi+0B0h]
0x180233eda  mov     rdx, rdi
0x180233edd  lea     rcx, [rsi+180h]
0x180233ee4  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x180233ee9  lea     rcx, [rsi+180h]
0x180233ef0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233ef5  jmp     short loc_180233EFF
0x180233ef7  mov     rcx, r15; SRWLock
0x180233efa  call    ReleaseSRWLockExclusive_0
0x180233eff  mov     [rsi+178h], r14
0x180233f06  mov     [rsi+1D8h], r14
0x180233f0d  mov     [rsp+118h+arg_10], rbx
0x180233f15  mov     rax, [rbx]
0x180233f18  lea     r8, [rsi+1D8h]
0x180233f1f  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x180233f26  mov     rcx, rbx
0x180233f29  mov     rax, [rax]
0x180233f2c  call    cs:__guard_dispatch_icall_fptr
0x180233f32  mov     rcx, [rsi+1D8h]
0x180233f39  mov     [rsp+118h+var_E0], rcx
0x180233f3e  mov     [rsi+188h], rcx
0x180233f45  lea     rdx, [rsi+190h]
0x180233f4c  mov     dword ptr [rdx], 246h
0x180233f52  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180233f59  mov     [rsi+198h], r8
0x180233f60  mov     [rsi+1A0h], r14
0x180233f67  test    eax, eax
0x180233f69  jns     short loc_180233F75
0x180233f6b  lfence
0x180233f6e  mov     ecx, eax
0x180233f70  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180233f75  mov     dword ptr [rsi+1C0h], 248h
0x180233f7f  mov     [rsi+1C8h], r8
0x180233f86  mov     [rsi+1D0h], r14
0x180233f8d  mov     rax, [rcx]
0x180233f90  lea     rdx, [rsi+178h]
0x180233f97  mov     rax, [rax+50h]
0x180233f9b  call    cs:__guard_dispatch_icall_fptr
0x180233fa1  test    eax, eax
0x180233fa3  jns     short loc_180233FB7
0x180233fa5  lfence
0x180233fa8  lea     rdx, [rsi+1C0h]
0x180233faf  mov     ecx, eax
0x180233fb1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180233fb7  lea     rcx, [rsi+188h]
0x180233fbe  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233fc3  lea     rdx, [rsi+0C0h]
0x180233fca  mov     rax, [rsi+178h]
0x180233fd1  mov     [rsp+118h+var_D8], rax
0x180233fd6  mov     [rdx], rax
0x180233fd9  mov     eax, [rsi+70h]
0x180233fdc  cmp     eax, 2
0x180233fdf  jnz     short loc_18023401E
0x180233fe1  lea     rdx, [rsi+160h]; struct winrt::impl::slim_source_location *
0x180233fe8  mov     dword ptr [rdx], 1628h
0x180233fee  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180233ff5  mov     [rsi+168h], rax
0x180233ffc  mov     [rsi+170h], r14
0x180234003  lea     rcx, [rsp+118h+pExceptionObject]; this
0x180234008  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18023400d  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180234014  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180234019  call    _CxxThrowException
0x18023401e  lea     rcx, [rsi+0C8h]
0x180234025  mov     [rcx], r14
0x180234028  mov     [rsi+0D0h], rdx
0x18023402f  mov     [rsi+0D8h], r14
0x180234036  mov     byte ptr [rsi+0E0h], 1
0x18023403d  mov     eax, 6
0x180234042  mov     [rsi+8Ch], ax
0x180234049  mov     rdx, rsi
0x18023404c  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x180234051  test    al, al
0x180234053  jz      loc_18023414F
0x180234059  jmp     loc_1802343A5
0x18023405e  mov     dword ptr [rsi+100h], 1B5h
0x180234068  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18023406f  mov     [rsi+108h], rax
0x180234076  mov     [rsi+110h], r14
0x18023407d  lea     rdx, aVectorSpaceDoe; "Vector space does not have a model acce"...
0x180234084  lea     rcx, [rsi+118h]; this
0x18023408b  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180234090  lea     r8, [rsi+100h]; struct winrt::impl::slim_source_location *
0x180234097  lea     rdx, [rsi+118h]; struct winrt::param::hstring *
0x18023409e  lea     rcx, [rsp+118h+var_B0]; this
0x1802340a3  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1802340a8  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1802340af  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x1802340b4  call    _CxxThrowException
0x1802340ba  mov     rbx, [rsi+0C8h]; jumptable 0000000180233E2D case 7
0x1802340c1  test    rbx, rbx
0x1802340c4  jz      short loc_1802340F1
0x1802340c6  mov     [rsp+118h+var_88], rbx
0x1802340ce  xor     r14d, r14d
0x1802340d1  mov     eax, r14d
0x1802340d4  xchg    rax, [rbx]
0x1802340d7  cmp     rax, 1
0x1802340db  jnz     short loc_1802340F1
0x1802340dd  nop     dword ptr [rax]
0x1802340e0  call    _Thrd_yield
0x1802340e5  mov     rax, r14
0x1802340e8  xchg    rax, [rbx]
0x1802340eb  cmp     rax, 1
0x1802340ef  jz      short loc_1802340E0
0x1802340f1  lea     rcx, [rsi+0C0h]
0x1802340f8  mov     rax, [rcx]
0x1802340fb  mov     [rsp+118h+arg_18], rax
0x180234103  test    rax, rax
0x180234106  jz      short loc_18023410E
0x180234108  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023410d  nop
0x18023410e  lea     rcx, [rsi+98h]
0x180234115  mov     rax, [rcx]
0x180234118  mov     [rsp+118h+arg_10], rax
0x180234120  test    rax, rax
0x180234123  jz      short loc_18023412B
0x180234125  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023412a  nop
0x18023412b  mov     eax, 0FFFFFFFFh
0x180234130  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180234138  sub     eax, 1
0x18023413b  jz      short loc_180234147
0x18023413d  test    eax, eax
0x18023413f  jns     short loc_180234147
0x180234141  call    abort
0x180234147  jmp     loc_180234382; jumptable 0000000180233E2D cases -1,1
0x18023414c  xor     r14d, r14d; jumptable 0000000180233E2D case 6
0x18023414f  lea     rdi, [rsi+0E8h]
0x180234156  mov     rdx, rdi
0x180234159  lea     rcx, [rsi+0C8h]
0x180234160  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180234165  nop
0x180234166  mov     rbx, [rsi+0C8h]
0x18023416d  test    rbx, rbx
0x180234170  jz      short loc_180234197
0x180234172  mov     [rsp+118h+var_88], rbx
0x18023417a  mov     rax, r14
0x18023417d  xchg    rax, [rbx]
0x180234180  cmp     rax, 1
0x180234184  jnz     short loc_180234197
0x180234186  call    _Thrd_yield
0x18023418b  mov     rax, r14
0x18023418e  xchg    rax, [rbx]
0x180234191  cmp     rax, 1
0x180234195  jz      short loc_180234186
0x180234197  lea     rcx, [rsi+0C0h]
0x18023419e  mov     rax, [rcx]
0x1802341a1  mov     [rsp+118h+arg_18], rax
0x1802341a9  test    rax, rax
0x1802341ac  jz      short loc_1802341B3
0x1802341ae  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802341b3  mov     ebx, 2
0x1802341b8  mov     rcx, [rdi]
0x1802341bb  test    rcx, rcx
0x1802341be  jz      short loc_18023422C
0x1802341c0  mov     [rsi+1F0h], r14d
0x1802341c7  mov     dword ptr [rsi+1F8h], 5A0h
0x1802341d1  lea     rax, aCW1SX64Release_14; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802341d8  mov     [rsi+200h], rax
0x1802341df  mov     [rsi+208h], r14
0x1802341e6  mov     [rsp+118h+var_F0], rcx
0x1802341eb  mov     rax, [rcx]
0x1802341ee  lea     rdx, [rsi+1F0h]
0x1802341f5  mov     rax, [rax+30h]
0x1802341f9  call    cs:__guard_dispatch_icall_fptr
0x1802341ff  test    eax, eax
0x180234201  jns     short loc_180234214
0x180234203  lfence
0x180234206  lea     rdx, [rsi+1F8h]
0x18023420d  mov     ecx, eax
0x18023420f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180234214  mov     eax, [rsi+1F0h]
0x18023421a  mov     [rsp+118h+arg_8], eax
0x180234221  mov     ecx, 3
0x180234226  cmp     eax, 1
0x180234229  cmovnz  ebx, ecx
0x18023422c  mov     [rsi+0F0h], ebx
0x180234232  mov     rax, 3FF0000000000000h
0x18023423c  mov     [rsi+0F8h], rax
0x180234243  movups  xmm0, xmmword ptr [rsi+0F0h]
0x18023424a  movups  [rsp+118h+var_98], xmm0
0x180234252  movups  xmmword ptr [rsi+0B0h], xmm0
0x180234259  mov     rbx, [rsi+1B0h]
0x180234260  mov     rcx, rbx; SRWLock
0x180234263  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180234268  mov     r13, [rsi+0A8h]
0x18023426f  mov     rcx, [r13+70h]
0x180234273  mov     [rsi+1E8h], rcx
0x18023427a  test    rcx, rcx
0x18023427d  jz      short loc_1802342BD
0x18023427f  mov     [rsp+118h+var_D0], rcx
0x180234284  mov     rax, [rcx]
0x180234287  mov     rax, [rax+8]
0x18023428b  call    cs:__guard_dispatch_icall_fptr
0x180234291  mov     rcx, rbx; SRWLock
0x180234294  call    ReleaseSRWLockExclusive_0
0x180234299  lea     r8, [rsi+0B0h]
0x1802342a0  mov     rdx, r13
0x1802342a3  lea     rcx, [rsi+1E8h]
0x1802342aa  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x1802342af  lea     rcx, [rsi+1E8h]
0x1802342b6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802342bb  jmp     short loc_1802342C5
0x1802342bd  mov     rcx, rbx; SRWLock
0x1802342c0  call    ReleaseSRWLockExclusive_0
0x1802342c5  lea     rcx, [rsi+58h]; SRWLock
0x1802342c9  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1802342ce  lea     rbx, [rsi+78h]
0x1802342d2  cmp     rbx, rdi
0x1802342d5  jz      short loc_1802342EE
0x1802342d7  cmp     qword ptr [rbx], 0
0x1802342db  jz      short loc_1802342E5
0x1802342dd  mov     rcx, rbx
0x1802342e0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802342e5  mov     rax, [rdi]
0x1802342e8  mov     [rdi], r14
0x1802342eb  mov     [rbx], rax
0x1802342ee  lea     rcx, [rsi+58h]; SRWLock
0x1802342f2  call    ReleaseSRWLockExclusive_0
0x1802342f7  nop
0x1802342f8  mov     rax, [rdi]
0x1802342fb  mov     [rsp+118h+var_F0], rax
0x180234300  test    rax, rax
0x180234303  jz      short loc_180234312
0x180234305  lea     rcx, [rsi+0E8h]
0x18023430c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180234311  nop
0x180234312  lea     rcx, [rsi+98h]
0x180234319  mov     rax, [rcx]
0x18023431c  mov     [rsp+118h+arg_10], rax
0x180234324  test    rax, rax
0x180234327  jz      short loc_18023432F
0x180234329  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18023432e  nop
0x18023432f  mov     eax, 0FFFFFFFFh
0x180234334  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023433c  sub     eax, 1
0x18023433f  jz      short loc_18023434B
0x180234341  test    eax, eax
0x180234343  jns     short loc_18023434B
0x180234345  call    abort
0x18023434b  mov     rax, [rsi+220h]
0x180234352  jmp     short loc_180234363
0x180234354  mov     rsi, [rsp+118h+Block]
0x18023435c  lea     rax, [rsi+10h]
0x180234360  xor     r14d, r14d
0x180234363  lea     rcx, [rsi+138h]
0x18023436a  mov     [rcx], rax
  ... truncated ...
```
