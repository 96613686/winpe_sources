# RegisterPackageDependency(winrt::hstring)

- ea: `0x18007806c`
- end: `0x1800783b1`
- name: `?RegisterPackageDependency@@YAXUhstring@winrt@@@Z`
- size: `837`
- prototype: `int __fastcall(volatile signed __int32 **)`
- caller_count: `2`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18007496c`
- `0x180075284`

## callees

- `0x1800058cb`
- `0x18000591f`
- `0x18000c478`
- `0x1800189b8`
- `0x180019c3c`
- `0x1800620b0`
- `0x18006bcd4`
- `0x180074340`
- `0x180074c08`
- `0x18007806c`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007823c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007834a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007823c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18007834a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800782db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180078295`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800782db`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800782a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800782e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800782a3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800782e9`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x1800782bc`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x1800782bc`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18007826a`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x18007826a`

## string_xrefs

- `0x180078354`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`
- `0x18007838a`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`
- `0x18007839f`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\modelpackagemanager.cpp`

## pseudocode

```c
int __fastcall RegisterPackageDependency(volatile signed __int32 **a1)
{
  int v2; // eax
  LPVOID v3; // rbx
  int v4; // eax
  volatile signed __int32 *v5; // rbx
  int v6; // eax
  int v7; // eax
  HANDLE ProcessHeap; // rax
  const wchar_t *v9; // rdx
  int PackageDependency; // eax
  void *v11; // rbx
  HANDLE v12; // rax
  int result; // eax
  void *v14; // rbx
  HANDLE v15; // rax
  volatile signed __int32 *v16; // rbx
  int v17; // edi
  HANDLE v18; // rax
  __int64 v19; // [rsp+50h] [rbp-19h] BYREF
  __int64 v20; // [rsp+58h] [rbp-11h] BYREF
  LPVOID v21; // [rsp+60h] [rbp-9h]
  LPVOID *v22; // [rsp+68h] [rbp-1h]
  void *v23; // [rsp+70h] [rbp+7h]
  char v24; // [rsp+78h] [rbp+Fh]
  int v25; // [rsp+80h] [rbp+17h] BYREF
  __int128 v26; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  LPVOID lpMem; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 v29; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID v30; // [rsp+E8h] [rbp+7Fh] BYREF

  lpMem = &qword_1800AF7D8;
  _InterlockedIncrement64(&qword_1800AF7D8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::operator()(
      a1,
      &v19,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_1800AF7D8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_1800AF7D8, 0xFFFFFFFFFFFFFFFFuLL);
    lpMem = _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      &v19,
      &lpMem);
  }
  v21 = 0;
  v22 = 0;
  LOBYTE(v23) = 1;
  lpMem = 0;
  v25 = 0;
  v26 = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *, _QWORD, __int64))(*(_QWORD *)v19 + 96LL))(
         v19,
         *a1,
         0,
         512);
  if ( v2 < 0 )
    winrt::throw_hresult((unsigned int)v2, &v25);
  v3 = lpMem;
  winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>::get(
    &lpMem,
    &v29);
  if ( v3 )
    winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&lpMem);
  if ( !(unsigned __int8)winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult2<winrt::Windows::Management::Deployment::DeploymentResult>::IsRegistered(&v29) )
  {
    lpMem = 0;
    v25 = 0;
    v26 = 0;
    v4 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v29 + 48LL))(v29, &lpMem);
    if ( v4 < 0 )
      winrt::throw_hresult((unsigned int)v4, &v25);
    v5 = (volatile signed __int32 *)lpMem;
    v21 = lpMem;
    LODWORD(lpMem) = 0;
    v25 = 0;
    v26 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v29 + 64LL))(v29, &lpMem);
    if ( v6 < 0 )
      winrt::throw_hresult((unsigned int)v6, &v25);
    if ( (int)lpMem < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
        (const char *)(unsigned int)lpMem,
        3);
    if ( v5 )
    {
      v7 = _InterlockedDecrement(v5 + 6);
      if ( v7 )
      {
        if ( v7 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v5);
      }
    }
  }
  v20 = 0;
  v30 = 0;
  v22 = &v30;
  v23 = 0;
  v24 = 1;
  if ( *a1 )
    v9 = (const wchar_t *)*((_QWORD *)*a1 + 2);
  else
    v9 = &pszText;
  PackageDependency = TryCreatePackageDependency(0, v9, 0, 0);
  if ( PackageDependency < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      (const char *)(unsigned int)PackageDependency,
      0);
  if ( v24 )
  {
    v11 = *v22;
    *v22 = v23;
    if ( v11 )
    {
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v11);
    }
  }
  result = AddPackageDependency(v30, 0, 1, &v20);
  if ( result < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\modelpackagemanager.cpp",
      (const char *)(unsigned int)result,
      0);
  v14 = v30;
  v30 = 0;
  if ( v14 )
  {
    v15 = GetProcessHeap();
    result = HeapFree(v15, 0, v14);
  }
  if ( v29 )
    result = winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v29);
  if ( v19 )
    result = winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v19);
  v16 = *a1;
  if ( *a1 )
  {
    v17 = _InterlockedDecrement(v16 + 6);
    if ( v17 )
    {
      if ( v17 < 0 )
        abort();
    }
    else
    {
      v18 = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(v18, 0, (LPVOID)v16);
    }
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18007806c  mov     [rsp-8+arg_0], rcx
0x180078071  push    rbp
0x180078072  push    rbx
0x180078073  push    rsi
0x180078074  push    rdi
0x180078075  push    r14
0x180078077  lea     rbp, [rsp-37h]
0x18007807c  sub     rsp, 0A0h
0x180078083  mov     rsi, rcx
0x180078086  xor     r14d, r14d
0x180078089  lea     rax, qword_1800AF7D8
0x180078090  mov     [rbp+57h+lpMem], rax
0x180078094  lock inc cs:qword_1800AF7D8
0x18007809c  cmp     cs:??$factory_cache_entry_v@UPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A, r14; factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>
0x1800780a3  jz      short loc_1800780C4
0x1800780a5  lea     r8, ??$factory_cache_entry_v@UPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@3U?$factory_cache_entry@UPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::Internal::PackageManagerInternal,winrt::Windows::Foundation::IActivationFactory>
0x1800780ac  lea     rdx, [rbp+57h+var_70]
0x1800780b0  call    ??R_lambda_3b774df9feaf32ce198fda5ed74d0bf7_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x1800780b5  nop
0x1800780b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800780ba  lock add cs:qword_1800AF7D8, rdi
0x1800780c2  jmp     short loc_1800780E9
0x1800780c4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800780c8  lock add cs:qword_1800AF7D8, rdi
0x1800780d0  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3b774df9feaf32ce198fda5ed74d0bf7_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_3b774df9feaf32ce198fda5ed74d0bf7_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800780d7  mov     [rbp+57h+lpMem], rax
0x1800780db  lea     r8, [rbp+57h+lpMem]
0x1800780df  lea     rdx, [rbp+57h+var_70]
0x1800780e3  call    ??$call@P6A?AUPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@56@@Z@?$factory_cache_entry@UPackageManagerInternal@Internal@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@56@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManagerInternal@Internal@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@72@@Z@Z
0x1800780e8  nop
0x1800780e9  mov     [rbp+57h+var_60], r14
0x1800780ed  mov     [rbp+57h+var_58], r14
0x1800780f1  mov     byte ptr [rbp+57h+var_50], 1
0x1800780f5  mov     [rbp+57h+lpMem], r14
0x1800780f9  mov     rcx, [rbp+57h+var_70]
0x1800780fd  mov     [rbp+57h+var_40], r14d
0x180078101  xorps   xmm0, xmm0
0x180078104  movdqu  [rbp+57h+var_38], xmm0
0x180078109  mov     rax, [rcx]
0x18007810c  lea     rdx, [rbp+57h+lpMem]
0x180078110  mov     [rsp+0C0h+var_88], rdx
0x180078115  mov     [rsp+0C0h+var_90], r14
0x18007811a  mov     [rsp+0C0h+var_98], r14
0x18007811f  mov     [rsp+0C0h+var_A0], 3; int
0x180078127  mov     r9d, 200h
0x18007812d  xor     r8d, r8d
0x180078130  mov     rdx, [rsi]
0x180078133  mov     rax, [rax+60h]
0x180078137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007813c  test    eax, eax
0x18007813e  js      loc_180078366
0x180078144  mov     rbx, [rbp+57h+lpMem]
0x180078148  mov     [rbp+57h+lpMem], rbx
0x18007814c  lea     rdx, [rbp+57h+arg_10]
0x180078150  lea     rcx, [rbp+57h+lpMem]
0x180078154  call    ?get@?$consume_Windows_Foundation_IAsyncOperationWithProgress@U?$IAsyncOperationWithProgress@UDeploymentResult@Deployment@Management@Windows@winrt@@UDeploymentProgress@2345@@Foundation@Windows@winrt@@UDeploymentResult@Deployment@Management@34@UDeploymentProgress@6734@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperationWithProgress<winrt::Windows::Foundation::IAsyncOperationWithProgress<winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>,winrt::Windows::Management::Deployment::DeploymentResult,winrt::Windows::Management::Deployment::DeploymentProgress>::get(void)
0x180078159  nop
0x18007815a  test    rbx, rbx
0x18007815d  jz      short loc_180078169
0x18007815f  lea     rcx, [rbp+57h+lpMem]
0x180078163  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180078168  nop
0x180078169  lea     rcx, [rbp+57h+arg_10]
0x18007816d  call    ?IsRegistered@?$consume_Windows_Management_Deployment_IDeploymentResult2@UDeploymentResult@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Management_Deployment_IDeploymentResult2<winrt::Windows::Management::Deployment::DeploymentResult>::IsRegistered(void)
0x180078172  test    al, al
0x180078174  jnz     loc_18007820F
0x18007817a  mov     [rbp+57h+lpMem], r14
0x18007817e  mov     rcx, [rbp+57h+arg_10]
0x180078182  mov     [rbp+57h+var_40], r14d
0x180078186  xorps   xmm0, xmm0
0x180078189  movdqu  [rbp+57h+var_38], xmm0
0x18007818e  mov     rax, [rcx]
0x180078191  lea     rdx, [rbp+57h+lpMem]
0x180078195  mov     rax, [rax+30h]
0x180078199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007819e  test    eax, eax
0x1800781a0  js      loc_180078372
0x1800781a6  mov     rbx, [rbp+57h+lpMem]
0x1800781aa  mov     [rbp+57h+var_60], rbx
0x1800781ae  mov     dword ptr [rbp+57h+lpMem], r14d
0x1800781b2  mov     rcx, [rbp+57h+arg_10]
0x1800781b6  mov     [rbp+57h+var_40], r14d
0x1800781ba  xorps   xmm0, xmm0
0x1800781bd  movdqu  [rbp+57h+var_38], xmm0
0x1800781c2  mov     rax, [rcx]
0x1800781c5  lea     rdx, [rbp+57h+lpMem]
0x1800781c9  mov     rax, [rax+40h]
0x1800781cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781d2  test    eax, eax
0x1800781d4  js      loc_18007837E
0x1800781da  mov     r9d, dword ptr [rbp+57h+lpMem]; char *
0x1800781de  mov     rcx, [rbp+5Fh]; this
0x1800781e2  test    r9d, r9d
0x1800781e5  js      loc_18007838A
0x1800781eb  test    rbx, rbx
0x1800781ee  jz      short loc_18007820F
0x1800781f0  mov     eax, edi
0x1800781f2  lock xadd [rbx+18h], eax
0x1800781f7  sub     eax, 1
0x1800781fa  jnz     short loc_180078238
0x1800781fc  nop
0x1800781fd  call    WINRT_IMPL_GetProcessHeap
0x180078202  mov     rcx, rax; hHeap
0x180078205  mov     r8, rbx; lpMem
0x180078208  xor     edx, edx; dwFlags
0x18007820a  call    WINRT_IMPL_HeapFree
0x18007820f  mov     [rbp+57h+var_68], r14
0x180078213  mov     [rbp+57h+arg_18], r14
0x180078217  lea     rax, [rbp+57h+arg_18]
0x18007821b  mov     [rbp+57h+var_58], rax
0x18007821f  mov     [rbp+57h+var_50], r14
0x180078223  mov     [rbp+57h+var_48], 1
0x180078227  mov     r8, r14
0x18007822a  mov     rax, [rsi]
0x18007822d  test    rax, rax
0x180078230  jz      short loc_180078243
0x180078232  mov     rdx, [rax+10h]
0x180078236  jmp     short loc_18007824A
0x180078238  test    eax, eax
0x18007823a  jns     short loc_18007820F
0x18007823c  call    cs:__imp_abort
0x180078243  lea     rdx, pszText
0x18007824a  lea     rax, [rbp+57h+var_50]
0x18007824e  mov     [rsp+0C0h+var_88], rax
0x180078253  mov     dword ptr [rsp+0C0h+var_90], 1
0x18007825b  mov     [rsp+0C0h+var_98], r14
0x180078260  mov     [rsp+0C0h+var_A0], r14d; int
0x180078265  xor     r9d, r9d
0x180078268  xor     ecx, ecx
0x18007826a  call    cs:__imp_TryCreatePackageDependency
0x180078270  mov     rcx, [rbp+5Fh]; this
0x180078274  test    eax, eax
0x180078276  js      loc_18007839C
0x18007827c  cmp     [rbp+57h+var_48], r14b
0x180078280  jz      short loc_1800782A9
0x180078282  mov     rcx, [rbp+57h+var_58]
0x180078286  mov     rbx, [rcx]
0x180078289  mov     rax, [rbp+57h+var_50]
0x18007828d  mov     [rcx], rax
0x180078290  test    rbx, rbx
0x180078293  jz      short loc_1800782A9
0x180078295  call    cs:__imp_GetProcessHeap
0x18007829b  mov     rcx, rax; hHeap
0x18007829e  mov     r8, rbx; lpMem
0x1800782a1  xor     edx, edx; dwFlags
0x1800782a3  call    cs:__imp_HeapFree
0x1800782a9  mov     qword ptr [rsp+0C0h+var_A0], r14; int
0x1800782ae  lea     r9, [rbp+57h+var_68]
0x1800782b2  xor     edx, edx
0x1800782b4  lea     r8d, [rdx+1]
0x1800782b8  mov     rcx, [rbp+57h+arg_18]
0x1800782bc  call    cs:__imp_AddPackageDependency
0x1800782c2  mov     rcx, [rbp+5Fh]; this
0x1800782c6  test    eax, eax
0x1800782c8  js      loc_180078351
0x1800782ce  mov     rbx, [rbp+57h+arg_18]
0x1800782d2  mov     [rbp+57h+arg_18], r14
0x1800782d6  test    rbx, rbx
0x1800782d9  jz      short loc_1800782F0
0x1800782db  call    cs:__imp_GetProcessHeap
0x1800782e1  mov     rcx, rax; hHeap
0x1800782e4  mov     r8, rbx; lpMem
0x1800782e7  xor     edx, edx; dwFlags
0x1800782e9  call    cs:__imp_HeapFree
0x1800782ef  nop
0x1800782f0  cmp     [rbp+57h+arg_10], r14
0x1800782f4  jz      short loc_180078300
0x1800782f6  lea     rcx, [rbp+57h+arg_10]
0x1800782fa  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x1800782ff  nop
0x180078300  cmp     [rbp+57h+var_70], r14
0x180078304  jz      short loc_180078310
0x180078306  lea     rcx, [rbp+57h+var_70]
0x18007830a  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18007830f  nop
0x180078310  mov     rbx, [rsi]
0x180078313  test    rbx, rbx
0x180078316  jz      short loc_180078338
0x180078318  lock xadd [rbx+18h], edi
0x18007831d  sub     edi, 1
0x180078320  jnz     short loc_180078346
0x180078322  nop
0x180078323  call    WINRT_IMPL_GetProcessHeap
0x180078328  mov     rcx, rax; hHeap
0x18007832b  mov     r8, rbx; lpMem
0x18007832e  xor     edx, edx; dwFlags
0x180078330  call    WINRT_IMPL_HeapFree
0x180078335  mov     [rsi], r14
0x180078338  add     rsp, 0A0h
0x18007833f  pop     r14
0x180078341  pop     rdi
0x180078342  pop     rsi
0x180078343  pop     rbx
0x180078344  pop     rbp
0x180078345  retn
0x180078346  test    edi, edi
0x180078348  jns     short loc_180078335
0x18007834a  call    cs:__imp_abort
0x180078351  mov     r9d, eax; char *
0x180078354  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x18007835b  mov     edx, 49h ; 'I'; void *
0x180078360  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180078366  lea     rdx, [rbp+57h+var_40]
0x18007836a  mov     ecx, eax
0x18007836c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180078372  lea     rdx, [rbp+57h+var_40]
0x180078376  mov     ecx, eax
0x180078378  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18007837e  lea     rdx, [rbp+57h+var_40]
0x180078382  mov     ecx, eax
0x180078384  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18007838a  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x180078391  mov     edx, 34h ; '4'; void *
0x180078396  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007839c  mov     r9d, eax; char *
0x18007839f  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\search\\com"...
0x1800783a6  mov     edx, 42h ; 'B'; void *
0x1800783ab  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
