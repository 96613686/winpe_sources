# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1

- ea: `0x1802337d0`
- end: `0x180233dd0`
- name: `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync$_ResumeCoro$1`
- size: `1536`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c410`
- `0x1802337c0`

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
- `0x18005a4b0`
- `0x180078d56`
- `0x180078d5c`
- `0x1801d31d8`
- `0x1801f7160`
- `0x1801f97e0`
- `0x180206a58`
- `0x1802337d0`
- `0x180242120`

## string_xrefs

- `0x180233942`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1802339de`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180233bc1`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Microsoft.Windows.Management.Deployment.h`
- `0x180233a58`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\SemanticImageIndexStore.cpp`
- `0x180233a6d`: `Vector space does not have a model accessor factory registered`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticImageIndexStore::MakeDefaultEmbeddingsGeneratorAvailableAsync__ResumeCoro_1(
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
      goto LABEL_48;
    case 2:
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      *((_OWORD *)a1 + 20) = winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId;
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetImageEmbeddingsModelFactory(
        a1 + 76,
        a1 + 160);
      v2 = (__int64 (__fastcall ***)(_QWORD, __int64 *, __int64))*((_QWORD *)a1 + 19);
      if ( !v2 )
      {
        *((_DWORD *)a1 + 64) = 307;
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
      goto LABEL_24;
    case 6:
LABEL_24:
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
        goto LABEL_48;
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
LABEL_48:
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
0x1802337d0  mov     [rsp+Block], rcx
0x1802337d5  push    rbx
0x1802337d6  push    rsi
0x1802337d7  push    rdi
0x1802337d8  push    r12
0x1802337da  push    r13
0x1802337dc  push    r14
0x1802337de  push    r15
0x1802337e0  sub     rsp, 0E0h
0x1802337e7  mov     rsi, [rsp+118h+Block]
0x1802337ef  movzx   eax, word ptr [rsi+8Ch]
0x1802337f6  mov     [rsp+118h+var_F8], ax
0x1802337fb  inc     ax; switch 9 cases
0x1802337fe  cmp     ax, 8
0x180233802  ja      def_18023381D; jumptable 000000018023381D default case, cases 0,4,5
0x180233808  movsx   rax, ax
0x18023380c  lea     rdx, cs:180000000h
0x180233813  mov     ecx, ds:(jpt_18023381D - 180000000h)[rdx+rax*4]
0x18023381a  add     rcx, rdx
0x18023381d  jmp     rcx; switch jump
0x18023381f  jmp     loc_180233D72; jumptable 000000018023381D case 3
0x180233824  xor     r14d, r14d; jumptable 000000018023381D case 2
0x180233827  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18023382e  lea     rdx, [rsi+140h]
0x180233835  movups  xmm0, cs:?VectorSpaceId@CompliantFlorenceD3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@2UGuid@asg@@B; asg::Guid const winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::CompliantFlorenceD3::VectorSpaceId
0x18023383c  movaps  xmmword ptr [rdx], xmm0
0x18023383f  lea     rcx, [rsi+98h]
0x180233846  call    ?TryGetImageEmbeddingsModelFactory@SemanticVectorSpaceModelRegistry@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA?AUIImageEmbeddingsModelFactory@345678@Uguid@8@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::SemanticVectorSpaceModelRegistry::TryGetImageEmbeddingsModelFactory(winrt::guid)
0x18023384b  nop
0x18023384c  mov     rbx, [rsi+98h]
0x180233853  test    rbx, rbx
0x180233856  jz      loc_180233A4E
0x18023385c  lea     rdi, [rsi+10h]
0x180233860  mov     [rsi+220h], rdi
0x180233867  mov     [rsi+0A0h], rdi
0x18023386e  mov     [rsi+0A8h], rdi
0x180233875  mov     dword ptr [rsi+0B0h], 1
0x18023387f  mov     [rsi+0B8h], r14
0x180233886  lea     r15, [rdi+48h]
0x18023388a  mov     [rsi+1B0h], r15
0x180233891  mov     rcx, r15; SRWLock
0x180233894  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180233899  mov     rcx, [rdi+70h]
0x18023389d  mov     [rsi+180h], rcx
0x1802338a4  test    rcx, rcx
0x1802338a7  jz      short loc_1802338E7
0x1802338a9  mov     [rsp+118h+var_E8], rcx
0x1802338ae  mov     rax, [rcx]
0x1802338b1  mov     rax, [rax+8]
0x1802338b5  call    cs:__guard_dispatch_icall_fptr
0x1802338bb  mov     rcx, r15; SRWLock
0x1802338be  call    ReleaseSRWLockExclusive_0
0x1802338c3  lea     r8, [rsi+0B0h]
0x1802338ca  mov     rdx, rdi
0x1802338cd  lea     rcx, [rsi+180h]
0x1802338d4  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x1802338d9  lea     rcx, [rsi+180h]
0x1802338e0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802338e5  jmp     short loc_1802338EF
0x1802338e7  mov     rcx, r15; SRWLock
0x1802338ea  call    ReleaseSRWLockExclusive_0
0x1802338ef  mov     [rsi+178h], r14
0x1802338f6  mov     [rsi+1D8h], r14
0x1802338fd  mov     [rsp+118h+arg_10], rbx
0x180233905  mov     rax, [rbx]
0x180233908  lea     r8, [rsi+1D8h]
0x18023390f  lea     rdx, ??$guid_v@UIEmbeddingsModelFactory@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IEmbeddingsModelFactory>
0x180233916  mov     rcx, rbx
0x180233919  mov     rax, [rax]
0x18023391c  call    cs:__guard_dispatch_icall_fptr
0x180233922  mov     rcx, [rsi+1D8h]
0x180233929  mov     [rsp+118h+var_E0], rcx
0x18023392e  mov     [rsi+188h], rcx
0x180233935  lea     rdx, [rsi+190h]
0x18023393c  mov     dword ptr [rdx], 246h
0x180233942  lea     r8, aCW1SX64Release_8; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180233949  mov     [rsi+198h], r8
0x180233950  mov     [rsi+1A0h], r14
0x180233957  test    eax, eax
0x180233959  jns     short loc_180233965
0x18023395b  lfence
0x18023395e  mov     ecx, eax
0x180233960  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180233965  mov     dword ptr [rsi+1C0h], 248h
0x18023396f  mov     [rsi+1C8h], r8
0x180233976  mov     [rsi+1D0h], r14
0x18023397d  mov     rax, [rcx]
0x180233980  lea     rdx, [rsi+178h]
0x180233987  mov     rax, [rax+50h]
0x18023398b  call    cs:__guard_dispatch_icall_fptr
0x180233991  test    eax, eax
0x180233993  jns     short loc_1802339A7
0x180233995  lfence
0x180233998  lea     rdx, [rsi+1C0h]
0x18023399f  mov     ecx, eax
0x1802339a1  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1802339a7  lea     rcx, [rsi+188h]
0x1802339ae  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1802339b3  lea     rdx, [rsi+0C0h]
0x1802339ba  mov     rax, [rsi+178h]
0x1802339c1  mov     [rsp+118h+var_D8], rax
0x1802339c6  mov     [rdx], rax
0x1802339c9  mov     eax, [rsi+70h]
0x1802339cc  cmp     eax, 2
0x1802339cf  jnz     short loc_180233A0E
0x1802339d1  lea     rdx, [rsi+160h]; struct winrt::impl::slim_source_location *
0x1802339d8  mov     dword ptr [rdx], 1628h
0x1802339de  lea     rax, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x1802339e5  mov     [rsi+168h], rax
0x1802339ec  mov     [rsi+170h], r14
0x1802339f3  lea     rcx, [rsp+118h+pExceptionObject]; this
0x1802339f8  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x1802339fd  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x180233a04  lea     rcx, [rsp+118h+pExceptionObject]; pExceptionObject
0x180233a09  call    _CxxThrowException
0x180233a0e  lea     rcx, [rsi+0C8h]
0x180233a15  mov     [rcx], r14
0x180233a18  mov     [rsi+0D0h], rdx
0x180233a1f  mov     [rsi+0D8h], r14
0x180233a26  mov     byte ptr [rsi+0E0h], 1
0x180233a2d  mov     eax, 6
0x180233a32  mov     [rsi+8Ch], ax
0x180233a39  mov     rdx, rsi
0x180233a3c  call    ??$await_suspend@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEAA_NU?$coroutine_handle@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@@std@@@Z; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions>::promise_type>)
0x180233a41  test    al, al
0x180233a43  jz      loc_180233B3F
0x180233a49  jmp     loc_180233D95
0x180233a4e  mov     dword ptr [rsi+100h], 133h
0x180233a58  lea     rax, aCW1SSrcSemanti_43; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180233a5f  mov     [rsi+108h], rax
0x180233a66  mov     [rsi+110h], r14
0x180233a6d  lea     rdx, aVectorSpaceDoe; "Vector space does not have a model acce"...
0x180233a74  lea     rcx, [rsi+118h]; this
0x180233a7b  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x180233a80  lea     r8, [rsi+100h]; struct winrt::impl::slim_source_location *
0x180233a87  lea     rdx, [rsi+118h]; struct winrt::param::hstring *
0x180233a8e  lea     rcx, [rsp+118h+var_B0]; this
0x180233a93  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180233a98  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180233a9f  lea     rcx, [rsp+118h+var_B0]; pExceptionObject
0x180233aa4  call    _CxxThrowException
0x180233aaa  mov     rbx, [rsi+0C8h]; jumptable 000000018023381D case 7
0x180233ab1  test    rbx, rbx
0x180233ab4  jz      short loc_180233AE1
0x180233ab6  mov     [rsp+118h+var_88], rbx
0x180233abe  xor     r14d, r14d
0x180233ac1  mov     eax, r14d
0x180233ac4  xchg    rax, [rbx]
0x180233ac7  cmp     rax, 1
0x180233acb  jnz     short loc_180233AE1
0x180233acd  nop     dword ptr [rax]
0x180233ad0  call    _Thrd_yield
0x180233ad5  mov     rax, r14
0x180233ad8  xchg    rax, [rbx]
0x180233adb  cmp     rax, 1
0x180233adf  jz      short loc_180233AD0
0x180233ae1  lea     rcx, [rsi+0C0h]
0x180233ae8  mov     rax, [rcx]
0x180233aeb  mov     [rsp+118h+arg_18], rax
0x180233af3  test    rax, rax
0x180233af6  jz      short loc_180233AFE
0x180233af8  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233afd  nop
0x180233afe  lea     rcx, [rsi+98h]
0x180233b05  mov     rax, [rcx]
0x180233b08  mov     [rsp+118h+arg_10], rax
0x180233b10  test    rax, rax
0x180233b13  jz      short loc_180233B1B
0x180233b15  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233b1a  nop
0x180233b1b  mov     eax, 0FFFFFFFFh
0x180233b20  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180233b28  sub     eax, 1
0x180233b2b  jz      short loc_180233B37
0x180233b2d  test    eax, eax
0x180233b2f  jns     short loc_180233B37
0x180233b31  call    abort
0x180233b37  jmp     loc_180233D72; jumptable 000000018023381D cases -1,1
0x180233b3c  xor     r14d, r14d; jumptable 000000018023381D case 6
0x180233b3f  lea     rdi, [rsi+0E8h]
0x180233b46  mov     rdx, rdi
0x180233b49  lea     rcx, [rsi+0C8h]
0x180233b50  call    ?await_resume@?$await_adapter@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@$00@impl@winrt@@QEBA@XZ; winrt::impl::await_adapter<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,1>::await_resume(void)
0x180233b55  nop
0x180233b56  mov     rbx, [rsi+0C8h]
0x180233b5d  test    rbx, rbx
0x180233b60  jz      short loc_180233B87
0x180233b62  mov     [rsp+118h+var_88], rbx
0x180233b6a  mov     rax, r14
0x180233b6d  xchg    rax, [rbx]
0x180233b70  cmp     rax, 1
0x180233b74  jnz     short loc_180233B87
0x180233b76  call    _Thrd_yield
0x180233b7b  mov     rax, r14
0x180233b7e  xchg    rax, [rbx]
0x180233b81  cmp     rax, 1
0x180233b85  jz      short loc_180233B76
0x180233b87  lea     rcx, [rsi+0C0h]
0x180233b8e  mov     rax, [rcx]
0x180233b91  mov     [rsp+118h+arg_18], rax
0x180233b99  test    rax, rax
0x180233b9c  jz      short loc_180233BA3
0x180233b9e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233ba3  mov     ebx, 2
0x180233ba8  mov     rcx, [rdi]
0x180233bab  test    rcx, rcx
0x180233bae  jz      short loc_180233C1C
0x180233bb0  mov     [rsi+1F0h], r14d
0x180233bb7  mov     dword ptr [rsi+1F8h], 5A0h
0x180233bc1  lea     rax, aCW1SX64Release_14; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180233bc8  mov     [rsi+200h], rax
0x180233bcf  mov     [rsi+208h], r14
0x180233bd6  mov     [rsp+118h+var_F0], rcx
0x180233bdb  mov     rax, [rcx]
0x180233bde  lea     rdx, [rsi+1F0h]
0x180233be5  mov     rax, [rax+30h]
0x180233be9  call    cs:__guard_dispatch_icall_fptr
0x180233bef  test    eax, eax
0x180233bf1  jns     short loc_180233C04
0x180233bf3  lfence
0x180233bf6  lea     rdx, [rsi+1F8h]
0x180233bfd  mov     ecx, eax
0x180233bff  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180233c04  mov     eax, [rsi+1F0h]
0x180233c0a  mov     [rsp+118h+arg_8], eax
0x180233c11  mov     ecx, 3
0x180233c16  cmp     eax, 1
0x180233c19  cmovnz  ebx, ecx
0x180233c1c  mov     [rsi+0F0h], ebx
0x180233c22  mov     rax, 3FF0000000000000h
0x180233c2c  mov     [rsi+0F8h], rax
0x180233c33  movups  xmm0, xmmword ptr [rsi+0F0h]
0x180233c3a  movups  [rsp+118h+var_98], xmm0
0x180233c42  movups  xmmword ptr [rsi+0B0h], xmm0
0x180233c49  mov     rbx, [rsi+1B0h]
0x180233c50  mov     rcx, rbx; SRWLock
0x180233c53  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180233c58  mov     r13, [rsi+0A8h]
0x180233c5f  mov     rcx, [r13+70h]
0x180233c63  mov     [rsi+1E8h], rcx
0x180233c6a  test    rcx, rcx
0x180233c6d  jz      short loc_180233CAD
0x180233c6f  mov     [rsp+118h+var_D0], rcx
0x180233c74  mov     rax, [rcx]
0x180233c77  mov     rax, [rax+8]
0x180233c7b  call    cs:__guard_dispatch_icall_fptr
0x180233c81  mov     rcx, rbx; SRWLock
0x180233c84  call    ReleaseSRWLockExclusive_0
0x180233c89  lea     r8, [rsi+0B0h]
0x180233c90  mov     rdx, r13
0x180233c93  lea     rcx, [rsi+1E8h]
0x180233c9a  call    ??$invoke@U?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@Upromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@UPackageDeploymentProgress@Deployment@Management@3Microsoft@4@@impl@winrt@@YA_NAEBU?$AsyncOperationProgressHandler@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@1@AEBUpromise_type@?$coroutine_traits@U?$IAsyncOperationWithProgress@UPackageDeploymentResult@Deployment@Management@Windows@Microsoft@winrt@@UPackageDeploymentProgress@23456@@Foundation@Windows@winrt@@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@4@@std@@AEBUPackageDeploymentProgress@Deployment@Management@4Microsoft@1@@Z; winrt::impl::invoke<winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>(winrt::Windows::Foundation::AsyncOperationProgressHandler<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress> const &,std::coroutine_traits<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentResult,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress>,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions>::promise_type const &,winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentProgress const &)
0x180233c9f  lea     rcx, [rsi+1E8h]
0x180233ca6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233cab  jmp     short loc_180233CB5
0x180233cad  mov     rcx, rbx; SRWLock
0x180233cb0  call    ReleaseSRWLockExclusive_0
0x180233cb5  lea     rcx, [rsi+58h]; SRWLock
0x180233cb9  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180233cbe  lea     rbx, [rsi+78h]
0x180233cc2  cmp     rbx, rdi
0x180233cc5  jz      short loc_180233CDE
0x180233cc7  cmp     qword ptr [rbx], 0
0x180233ccb  jz      short loc_180233CD5
0x180233ccd  mov     rcx, rbx
0x180233cd0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233cd5  mov     rax, [rdi]
0x180233cd8  mov     [rdi], r14
0x180233cdb  mov     [rbx], rax
0x180233cde  lea     rcx, [rsi+58h]; SRWLock
0x180233ce2  call    ReleaseSRWLockExclusive_0
0x180233ce7  nop
0x180233ce8  mov     rax, [rdi]
0x180233ceb  mov     [rsp+118h+var_F0], rax
0x180233cf0  test    rax, rax
0x180233cf3  jz      short loc_180233D02
0x180233cf5  lea     rcx, [rsi+0E8h]
0x180233cfc  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233d01  nop
0x180233d02  lea     rcx, [rsi+98h]
0x180233d09  mov     rax, [rcx]
0x180233d0c  mov     [rsp+118h+arg_10], rax
0x180233d14  test    rax, rax
0x180233d17  jz      short loc_180233D1F
0x180233d19  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180233d1e  nop
0x180233d1f  mov     eax, 0FFFFFFFFh
0x180233d24  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, eax; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180233d2c  sub     eax, 1
0x180233d2f  jz      short loc_180233D3B
0x180233d31  test    eax, eax
0x180233d33  jns     short loc_180233D3B
0x180233d35  call    abort
0x180233d3b  mov     rax, [rsi+220h]
0x180233d42  jmp     short loc_180233D53
0x180233d44  mov     rsi, [rsp+118h+Block]
0x180233d4c  lea     rax, [rsi+10h]
0x180233d50  xor     r14d, r14d
0x180233d53  lea     rcx, [rsi+138h]
0x180233d5a  mov     [rcx], rax
  ... truncated ...
```
