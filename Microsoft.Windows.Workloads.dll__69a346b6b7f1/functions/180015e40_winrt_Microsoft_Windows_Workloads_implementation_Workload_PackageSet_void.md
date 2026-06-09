# winrt::Microsoft::Windows::Workloads::implementation::Workload::PackageSet(void)

- ea: `0x180015e40`
- end: `0x1800166b7`
- name: `?PackageSet@Workload@implementation@Workloads@Windows@Microsoft@winrt@@QEAA?AU0Deployment@Management@456@XZ`
- size: `2167`
- prototype: `__int64 *__fastcall(_QWORD *, __int64 *)`
- caller_count: `2`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018f00`
- `0x180018fd0`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180004a00`
- `0x180013bd0`
- `0x180014bb0`
- `0x180014d10`
- `0x180014e70`
- `0x180015e40`
- `0x1800166c0`
- `0x180016760`
- `0x180019f30`
- `0x18001a0e0`
- `0x18001c400`
- `0x18001c560`
- `0x18001c810`
- `0x18001c8c0`
- `0x18001d320`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x180036f4c`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016056`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016382`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001645a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800165cd`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016056`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016382`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001645a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x1800165cd`

## string_xrefs

- `0x18001664d`: `Didn't find registered manifest package despite PackageManager saying it was ready`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 *__fastcall winrt::Microsoft::Windows::Workloads::implementation::Workload::PackageSet(_QWORD *a1, __int64 *a2)
{
  LPVOID v4; // rbx
  void *v5; // rcx
  void (*v6)(void); // rax
  __int64 v7; // rcx
  char v8; // di
  void *v9; // rcx
  int v10; // eax
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  int v13; // eax
  HANDLE ProcessHeap; // rax
  int v15; // eax
  LPVOID v16; // rdi
  int v17; // eax
  LPVOID v18; // rcx
  LPVOID v19; // rdi
  int v20; // eax
  __int64 v21; // rcx
  bool v22; // al
  int v23; // eax
  int v24; // eax
  volatile signed __int32 *v25; // r14
  int v26; // eax
  LPVOID v27; // r12
  int v28; // eax
  void *v29; // rdi
  int v30; // eax
  char v31; // di
  int v32; // eax
  LPVOID v33; // rdi
  int v34; // eax
  LPVOID v35; // rcx
  LPVOID v36; // rdi
  int v37; // eax
  volatile signed __int32 *v38; // rdi
  int v39; // eax
  HANDLE v40; // rax
  void (__fastcall ***v41)(LPVOID, __int64 *, LPVOID *); // rdi
  LPVOID v42; // rcx
  LPVOID v43; // r12
  int v44; // eax
  __int64 v45; // rax
  void *v46; // rcx
  signed __int32 v47; // r13d
  int v48; // eax
  LPVOID v49; // rbx
  __int64 v50; // rax
  void *v51; // rcx
  signed __int32 v52; // r13d
  HANDLE v53; // rax
  winrt::hresult *v55; // rax
  __int64 *v56; // [rsp+30h] [rbp-89h] BYREF
  __int64 (__fastcall *v57)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+38h] [rbp-81h] BYREF
  int v58; // [rsp+40h] [rbp-79h]
  LPVOID v59; // [rsp+48h] [rbp-71h]
  __int64 v60[4]; // [rsp+50h] [rbp-69h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-49h] BYREF
  LPVOID v62; // [rsp+88h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-29h] BYREF
  LPVOID v64; // [rsp+98h] [rbp-21h] BYREF
  LPVOID v65; // [rsp+A0h] [rbp-19h] BYREF
  bool v66[8]; // [rsp+A8h] [rbp-11h] BYREF
  void *v67; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v68; // [rsp+B8h] [rbp-1h] BYREF
  void (__fastcall ***v69)(_QWORD, __int64 *, LPVOID *); // [rsp+C0h] [rbp+7h] BYREF
  __int64 v70; // [rsp+C8h] [rbp+Fh] BYREF

  v56 = a2;
  v4 = 0;
  v58 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_54112284>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_54112284>::GetImpl'::`2'::impl) )
  {
    v5 = (void *)a1[5];
    v62 = v5;
    if ( !v5 )
    {
LABEL_5:
      winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(a1, a2, &v62);
      return a2;
    }
    v6 = *(void (**)(void))(*(_QWORD *)v5 + 8LL);
LABEL_4:
    v6();
    goto LABEL_5;
  }
  lpMem = 0;
  v8 = winrt::Windows::Foundation::operator==(a1 + 6, &lpMem);
  if ( lpMem )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
  if ( v8 )
  {
    v9 = (void *)a1[5];
    v62 = v9;
    if ( !v9 )
      goto LABEL_5;
    v6 = *(void (**)(void))(*(_QWORD *)v9 + 8LL);
    goto LABEL_4;
  }
  v56 = &qword_180059E98;
  _InterlockedIncrement64(&qword_180059E98);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(
      v7,
      &v67,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059E98);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059E98);
    v57 = _lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v7,
      (__int64)&v67,
      (void (__fastcall **)(__int64, __int64 *))&v57);
  }
  lpMem = 0;
  v10 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)a1[5] + 48LL))(a1[5], &lpMem);
  if ( v10 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v10);
  }
  v11 = (volatile signed __int32 *)lpMem;
  v56 = (__int64 *)lpMem;
  v12 = (*(__int64 (__fastcall **)(void *, LPVOID))(*(_QWORD *)v67 + 56LL))(v67, lpMem);
  if ( v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12);
  }
  if ( v11 )
  {
    v13 = _InterlockedDecrement(v11 + 6);
    if ( v13 )
    {
      if ( v13 < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
    }
  }
  v62 = 0;
  v15 = (*(__int64 (__fastcall **)(void *, LPVOID *))(*(_QWORD *)v67 + 80LL))(v67, &v62);
  if ( v15 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v15);
  }
  v16 = v62;
  v57 = (__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *))v62;
  v17 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v62 + 104LL))(v62, a1[6]);
  if ( v17 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v17);
  }
  if ( v16 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
  winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager::GetDefault();
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55648890>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55648890>::GetImpl'::`2'::impl) )
  {
    LODWORD(v65) = 0;
    v62 = 0;
    if ( v68 )
    {
      (**(void (__fastcall ***)(__int64, __int64 *, LPVOID *))v68)(
        v68,
        winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManager2>,
        &v62);
      v18 = v62;
      v19 = v62;
    }
    else
    {
      v18 = 0;
      v19 = 0;
    }
    v20 = (*(__int64 (__fastcall **)(LPVOID, void *, LPVOID *))(*(_QWORD *)v18 + 64LL))(v18, v67, &v65);
    if ( v20 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v20);
    }
    if ( v19 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
    v22 = (_DWORD)v65 == 1;
  }
  else
  {
    v66[0] = 0;
    v23 = (*(__int64 (__fastcall **)(__int64, void *, bool *))(*(_QWORD *)v68 + 64LL))(v68, v67, v66);
    if ( v23 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v23);
    }
    v22 = v66[0];
  }
  if ( v22 )
  {
    v56 = &qword_180059F48;
    _InterlockedIncrement64(&qword_180059F48);
    if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> )
    {
      _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(
        v21,
        &v70,
        &winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>);
      _InterlockedDecrement64(&qword_180059F48);
    }
    else
    {
      _InterlockedDecrement64(&qword_180059F48);
      v57 = _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::Management::Deployment::PackageManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        v21,
        (__int64)&v70,
        (void (__fastcall **)(__int64, __int64 *))&v57);
    }
    v65 = 0;
    v24 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)a1[6] + 64LL))(a1[6], &v65);
    if ( v24 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v24);
    }
    v25 = (volatile signed __int32 *)v65;
    v59 = v65;
    v62 = 0;
    v26 = (*(__int64 (__fastcall **)(__int64, _QWORD, LPVOID, LPVOID *))(*(_QWORD *)v70 + 160LL))(v70, 0, v65, &v62);
    if ( v26 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v26);
    }
    v27 = v62;
    v57 = (__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *))v62;
    v62 = 0;
    lpMem = 0;
    v28 = (*(__int64 (__fastcall **)(__int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *), LPVOID *))(*(_QWORD *)v57 + 48LL))(
            v57,
            &lpMem);
    if ( v28 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v28);
    }
    v29 = lpMem;
    v64 = lpMem;
    v66[0] = 0;
    v30 = (*(__int64 (__fastcall **)(LPVOID, bool *))(*(_QWORD *)lpMem + 56LL))(lpMem, v66);
    if ( v30 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v30);
    }
    if ( v66[0] )
    {
      lpMem = v29;
    }
    else
    {
      lpMem = 0;
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
    }
    v31 = winrt::Windows::Foundation::operator==(&lpMem, &v62);
    if ( lpMem )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
    if ( v62 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
    if ( v31 )
    {
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v60,
        L"Didn't find registered manifest package despite PackageManager saying it was ready");
      v55 = winrt::hresult::hresult((winrt::hresult *)&v65, -2147418113);
      winrt::hresult_error::hresult_error(pExceptionObject, *(unsigned int *)v55, v60);
      throw (winrt::hresult_error *)pExceptionObject;
    }
    v62 = 0;
    v32 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v27 + 48LL))(v27, &v62);
    if ( v32 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v32);
    }
    v33 = v62;
    v64 = v62;
    v69 = 0;
    v58 = 6142;
    v34 = (*(__int64 (__fastcall **)(LPVOID, void (__fastcall ****)(_QWORD, __int64 *, LPVOID *)))(*(_QWORD *)v62 + 48LL))(
            v62,
            &v69);
    if ( v34 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v34);
    }
    if ( v33 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
    v62 = 0;
    lpMem = 0;
    if ( v69 )
    {
      (**v69)(v69, winrt::impl::guid_v<winrt::Windows::ApplicationModel::IPackage8>, &lpMem);
      v35 = lpMem;
      v36 = lpMem;
    }
    else
    {
      v35 = 0;
      v36 = 0;
    }
    v37 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v35 + 72LL))(v35, &v62);
    if ( v37 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v37);
    }
    if ( v36 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
    v38 = (volatile signed __int32 *)v62;
    v56 = (__int64 *)v62;
    v60[0] = (__int64)v62;
    winrt::Microsoft::Windows::Workloads::implementation::WorkloadManager::LoadForResourceDll(&lpMem, v60);
    if ( v38 )
    {
      v39 = _InterlockedDecrement(v38 + 6);
      if ( v39 )
      {
        if ( v39 < 0 )
          abort();
      }
      else
      {
        v40 = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(v40, 0, v62);
      }
      v25 = (volatile signed __int32 *)v65;
    }
    v64 = 0;
    v41 = (void (__fastcall ***)(LPVOID, __int64 *, LPVOID *))lpMem;
    v62 = 0;
    if ( lpMem )
    {
      (**(void (__fastcall ***)(LPVOID, __int64 *, LPVOID *))lpMem)(
        lpMem,
        &winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager6>,
        &v62);
      v42 = v62;
      v43 = v62;
    }
    else
    {
      v42 = 0;
      v43 = 0;
    }
    v44 = (*(__int64 (__fastcall **)(LPVOID, LPVOID *))(*(_QWORD *)v42 + 56LL))(v42, &v64);
    if ( v44 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v44);
    }
    if ( v43 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v62);
    v45 = winrt::impl::consume_Microsoft_Windows_Workloads_IWorkloadManager6<winrt::Microsoft::Windows::Workloads::WorkloadManager>::Version(a1 + 3);
    if ( v64 == (LPVOID)v45 )
    {
      v46 = (void *)a1[5];
      v64 = v46;
      if ( v46 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v46 + 8LL))(v46);
      winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(a1, a2, &v64);
      if ( v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      if ( v69 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v69);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
      if ( !v25 )
        goto LABEL_105;
      v47 = _InterlockedExchangeAdd(v25 + 6, 0xFFFFFFFF);
      if ( v47 != 1 )
      {
        if ( v47 - 1 < 0 )
          abort();
        goto LABEL_105;
      }
    }
    else
    {
      v56 = (__int64 *)a1[4];
      v62 = 0;
      v64 = 0;
      if ( v41 )
      {
        (**v41)(v41, &winrt::impl::guid_v<winrt::Microsoft::Windows::Workloads::IWorkloadManager6>, &v64);
        v4 = v64;
      }
      v48 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, LPVOID *))(*(_QWORD *)v4 + 64LL))(v4, v56, &v62);
      if ( v48 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v48);
      }
      if ( v4 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v64);
      v49 = v62;
      v56 = (__int64 *)v62;
      v50 = (__int64)v62 + 24;
      if ( !v62 )
        v50 = 40;
      v51 = *(void **)v50;
      v64 = v51;
      if ( v51 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 8LL))(v51);
      winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(a1, a2, &v64);
      if ( v49 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v56);
      if ( v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
      if ( v69 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v69);
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v57);
      if ( !v25 )
        goto LABEL_105;
      v52 = _InterlockedExchangeAdd(v25 + 6, 0xFFFFFFFF);
      if ( v52 != 1 )
      {
        if ( v52 - 1 < 0 )
          abort();
        goto LABEL_105;
      }
    }
    v53 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v53, 0, v65);
LABEL_105:
    if ( v70 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v70);
    goto LABEL_107;
  }
  v62 = v67;
  if ( v67 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v67 + 8LL))(v67);
  winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(a1, a2, &v62);
LABEL_107:
  if ( v68 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v68);
  if ( v67 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v67);
  return a2;
}

```

## disassembly

```asm
0x180015e40  mov     [rsp-8+arg_10], rbx
0x180015e45  push    rbp
0x180015e46  push    rsi
0x180015e47  push    rdi
0x180015e48  push    r12
0x180015e4a  push    r13
0x180015e4c  push    r14
0x180015e4e  push    r15
0x180015e50  lea     rbp, [rsp-27h]
0x180015e55  sub     rsp, 0E0h
0x180015e5c  mov     rax, cs:__security_cookie
0x180015e63  xor     rax, rsp
0x180015e66  mov     [rbp+57h+var_40], rax
0x180015e6a  mov     r15, rdx
0x180015e6d  mov     rsi, rcx
0x180015e70  mov     [rsp+110h+var_E0], rdx
0x180015e75  xor     ebx, ebx
0x180015e77  mov     [rbp+57h+var_D0], ebx
0x180015e7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_54112284@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_54112284@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54112284> `wil::Feature<__WilFeatureTraits_Feature_54112284>::GetImpl(void)'::`2'::impl
0x180015e81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_54112284@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_54112284>::__private_IsEnabled(void)
0x180015e86  test    al, al
0x180015e88  jnz     short loc_180015EB8
0x180015e8a  mov     rcx, [rsi+28h]
0x180015e8e  mov     [rbp+57h+var_88], rcx
0x180015e92  test    rcx, rcx
0x180015e95  jz      short loc_180015EA4
0x180015e97  mov     rdx, [rcx]
0x180015e9a  mov     rax, [rdx+8]
0x180015e9e  call    cs:__guard_dispatch_icall_fptr
0x180015ea4  lea     r8, [rbp+57h+var_88]
0x180015ea8  mov     rdx, r15
0x180015eab  mov     rcx, rsi
0x180015eae  call    ?PreparePackageSetForUse@Workload@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AUPackageSet@Deployment@Management@456@U789456@@Z; winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(winrt::Microsoft::Windows::Management::Deployment::PackageSet)
0x180015eb3  jmp     loc_1800165A1
0x180015eb8  mov     [rbp+57h+lpMem], rbx
0x180015ebc  lea     rdx, [rbp+57h+lpMem]
0x180015ec0  lea     rcx, [rsi+30h]
0x180015ec4  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180015ec9  movzx   edi, al
0x180015ecc  cmp     [rbp+57h+lpMem], rbx
0x180015ed0  jz      short loc_180015EDB
0x180015ed2  lea     rcx, [rbp+57h+lpMem]
0x180015ed6  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180015edb  test    dil, dil
0x180015ede  jz      short loc_180015EF6
0x180015ee0  mov     rcx, [rsi+28h]
0x180015ee4  mov     [rbp+57h+var_88], rcx
0x180015ee8  test    rcx, rcx
0x180015eeb  jz      short loc_180015EA4
0x180015eed  mov     rax, [rcx]
0x180015ef0  mov     rax, [rax+8]
0x180015ef4  jmp     short loc_180015E9E
0x180015ef6  lea     rax, qword_180059E98
0x180015efd  mov     [rsp+110h+var_E0], rax
0x180015f02  lock inc cs:qword_180059E98
0x180015f0a  cmp     cs:??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180015f12  jz      short loc_180015F2F
0x180015f14  lea     r8, ??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180015f1b  lea     rdx, [rbp+57h+var_60]
0x180015f1f  call    ??R_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180015f24  nop
0x180015f25  lock dec cs:qword_180059E98
0x180015f2d  jmp     short loc_180015F52
0x180015f2f  lock dec cs:qword_180059E98
0x180015f37  lea     rax, ?_lambda_invoker_cdecl_@_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180015f3e  mov     [rsp+110h+var_D8], rax
0x180015f43  lea     r8, [rsp+110h+var_D8]
0x180015f48  lea     rdx, [rbp+57h+var_60]
0x180015f4c  call    ??$call@P6A?AUPackageSet@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSet@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180015f51  nop
0x180015f52  mov     [rbp+57h+lpMem], rbx
0x180015f56  mov     rcx, [rsi+28h]
0x180015f5a  mov     rax, [rcx]
0x180015f5d  lea     rdx, [rbp+57h+lpMem]
0x180015f61  mov     rax, [rax+30h]
0x180015f65  call    cs:__guard_dispatch_icall_fptr
0x180015f6b  test    eax, eax
0x180015f6d  js      loc_1800165DF
0x180015f73  mov     rdi, [rbp+57h+lpMem]
0x180015f77  mov     [rsp+110h+var_E0], rdi
0x180015f7c  mov     rcx, [rbp+57h+var_60]
0x180015f80  mov     rax, [rcx]
0x180015f83  mov     rdx, rdi
0x180015f86  mov     rax, [rax+38h]
0x180015f8a  call    cs:__guard_dispatch_icall_fptr
0x180015f90  test    eax, eax
0x180015f92  js      loc_1800165EA
0x180015f98  mov     r13d, 0FFFFFFFFh
0x180015f9e  test    rdi, rdi
0x180015fa1  jz      short loc_180015FC7
0x180015fa3  mov     eax, r13d
0x180015fa6  lock xadd [rdi+18h], eax
0x180015fab  sub     eax, 1
0x180015fae  jnz     loc_18001604E
0x180015fb4  call    WINRT_IMPL_GetProcessHeap
0x180015fb9  mov     rcx, rax; hHeap
0x180015fbc  mov     r8, [rbp+57h+lpMem]; lpMem
0x180015fc0  xor     edx, edx; dwFlags
0x180015fc2  call    WINRT_IMPL_HeapFree
0x180015fc7  mov     [rbp+57h+var_88], rbx
0x180015fcb  mov     rcx, [rbp+57h+var_60]
0x180015fcf  mov     rax, [rcx]
0x180015fd2  lea     rdx, [rbp+57h+var_88]
0x180015fd6  mov     rax, [rax+50h]
0x180015fda  call    cs:__guard_dispatch_icall_fptr
0x180015fe0  test    eax, eax
0x180015fe2  js      loc_1800165F5
0x180015fe8  mov     rdi, [rbp+57h+var_88]
0x180015fec  mov     [rsp+110h+var_D8], rdi
0x180015ff1  mov     rax, [rdi]
0x180015ff4  mov     rdx, [rsi+30h]
0x180015ff8  mov     rcx, rdi
0x180015ffb  mov     rax, [rax+68h]
0x180015fff  call    cs:__guard_dispatch_icall_fptr
0x180016005  test    eax, eax
0x180016007  js      loc_180016600
0x18001600d  test    rdi, rdi
0x180016010  jz      short loc_18001601C
0x180016012  lea     rcx, [rsp+110h+var_D8]
0x180016017  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001601c  lea     rcx, [rbp+57h+var_58]
0x180016020  call    ?GetDefault@PackageDeploymentManager@Deployment@Management@Windows@Microsoft@winrt@@SA@XZ; winrt::Microsoft::Windows::Management::Deployment::PackageDeploymentManager::GetDefault(void)
0x180016025  nop
0x180016026  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55648890@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55648890@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55648890> `wil::Feature<__WilFeatureTraits_Feature_55648890>::GetImpl(void)'::`2'::impl
0x18001602d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55648890@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55648890>::__private_IsEnabled(void)
0x180016032  mov     rcx, [rbp+57h+var_58]
0x180016036  test    al, al
0x180016038  jz      short loc_1800160B3
0x18001603a  mov     dword ptr [rbp+57h+var_70], ebx
0x18001603d  mov     [rbp+57h+var_88], rbx
0x180016041  test    rcx, rcx
0x180016044  jnz     short loc_18001605D
0x180016046  mov     rcx, rbx
0x180016049  mov     rdi, rbx
0x18001604c  jmp     short loc_18001607F
0x18001604e  test    eax, eax
0x180016050  jns     loc_180015FC7
0x180016056  call    cs:__imp_abort
0x18001605d  mov     rax, [rcx]
0x180016060  lea     r8, [rbp+57h+var_88]
0x180016064  lea     rdx, ??$guid_v@UIPackageDeploymentManager2@Deployment@Management@Windows@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Windows::Management::Deployment::IPackageDeploymentManager2>
0x18001606b  mov     rax, [rax]
0x18001606e  call    cs:__guard_dispatch_icall_fptr
0x180016074  mov     rcx, [rbp+57h+var_88]
0x180016078  mov     [rbp+57h+var_88], rcx
0x18001607c  mov     rdi, rcx
0x18001607f  mov     rax, [rcx]
0x180016082  lea     r8, [rbp+57h+var_70]
0x180016086  mov     rdx, [rbp+57h+var_60]
0x18001608a  mov     rax, [rax+40h]
0x18001608e  call    cs:__guard_dispatch_icall_fptr
0x180016094  test    eax, eax
0x180016096  js      loc_18001660B
0x18001609c  test    rdi, rdi
0x18001609f  jz      short loc_1800160AA
0x1800160a1  lea     rcx, [rbp+57h+var_88]
0x1800160a5  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800160aa  cmp     dword ptr [rbp+57h+var_70], 1
0x1800160ae  setz    al
0x1800160b1  jmp     short loc_1800160D8
0x1800160b3  mov     [rbp+57h+var_68], 0
0x1800160b7  mov     rax, [rcx]
0x1800160ba  lea     r8, [rbp+57h+var_68]
0x1800160be  mov     rdx, [rbp+57h+var_60]
0x1800160c2  mov     rax, [rax+40h]
0x1800160c6  call    cs:__guard_dispatch_icall_fptr
0x1800160cc  test    eax, eax
0x1800160ce  js      loc_180016616
0x1800160d4  movzx   eax, [rbp+57h+var_68]
0x1800160d8  test    al, al
0x1800160da  jnz     short loc_18001610A
0x1800160dc  mov     rcx, [rbp+57h+var_60]
0x1800160e0  mov     [rbp+57h+var_88], rcx
0x1800160e4  test    rcx, rcx
0x1800160e7  jz      short loc_1800160F6
0x1800160e9  mov     rax, [rcx]
0x1800160ec  mov     rax, [rax+8]
0x1800160f0  call    cs:__guard_dispatch_icall_fptr
0x1800160f6  lea     r8, [rbp+57h+var_88]
0x1800160fa  mov     rdx, r15
0x1800160fd  mov     rcx, rsi
0x180016100  call    ?PreparePackageSetForUse@Workload@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AUPackageSet@Deployment@Management@456@U789456@@Z; winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(winrt::Microsoft::Windows::Management::Deployment::PackageSet)
0x180016105  jmp     loc_180016580
0x18001610a  lea     rax, qword_180059F48
0x180016111  mov     [rsp+110h+var_E0], rax
0x180016116  lock inc cs:qword_180059F48
0x18001611e  cmp     cs:??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A, 0; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x180016126  jz      short loc_180016143
0x180016128  lea     r8, ??$factory_cache_entry_v@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@3U?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@12@A; factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Management::Deployment::PackageManager,winrt::Windows::Foundation::IActivationFactory>
0x18001612f  lea     rdx, [rbp+57h+var_48]
0x180016133  call    ??R_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180016138  nop
0x180016139  lock dec cs:qword_180059F48
0x180016141  jmp     short loc_180016166
0x180016143  lock dec cs:qword_180059F48
0x18001614b  lea     rax, ?_lambda_invoker_cdecl_@_lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_6fd1ee5d6179fa7e6cafc7c7248cd72e_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180016152  mov     [rsp+110h+var_D8], rax
0x180016157  lea     r8, [rsp+110h+var_D8]
0x18001615c  lea     rdx, [rbp+57h+var_48]
0x180016160  call    ??$call@P6A?AUPackageManager@Deployment@Management@Windows@winrt@@AEBUIActivationFactory@Foundation@45@@Z@?$factory_cache_entry@UPackageManager@Deployment@Management@Windows@winrt@@UIActivationFactory@Foundation@45@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageManager@Deployment@Management@Windows@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180016165  nop
0x180016166  mov     [rbp+57h+var_70], rbx
0x18001616a  mov     rcx, [rsi+30h]
0x18001616e  mov     rax, [rcx]
0x180016171  lea     rdx, [rbp+57h+var_70]
0x180016175  mov     rax, [rax+40h]
0x180016179  call    cs:__guard_dispatch_icall_fptr
0x18001617f  test    eax, eax
0x180016181  js      loc_180016621
0x180016187  mov     r14, [rbp+57h+var_70]
0x18001618b  mov     [rbp+57h+var_C8], r14
0x18001618f  mov     [rbp+57h+var_88], rbx
0x180016193  mov     rcx, [rbp+57h+var_48]
0x180016197  mov     rax, [rcx]
0x18001619a  lea     r9, [rbp+57h+var_88]
0x18001619e  mov     r8, r14
0x1800161a1  xor     edx, edx
0x1800161a3  mov     rax, [rax+0A0h]
0x1800161aa  call    cs:__guard_dispatch_icall_fptr
0x1800161b0  test    eax, eax
0x1800161b2  js      loc_18001662C
0x1800161b8  mov     r12, [rbp+57h+var_88]
0x1800161bc  mov     [rsp+110h+var_D8], r12
0x1800161c1  mov     [rbp+57h+var_88], rbx
0x1800161c5  mov     [rbp+57h+lpMem], rbx
0x1800161c9  mov     rax, [r12]
0x1800161cd  lea     rdx, [rbp+57h+lpMem]
0x1800161d1  mov     rcx, r12
0x1800161d4  mov     rax, [rax+30h]
0x1800161d8  call    cs:__guard_dispatch_icall_fptr
0x1800161de  test    eax, eax
0x1800161e0  js      loc_180016637
0x1800161e6  mov     rdi, [rbp+57h+lpMem]
0x1800161ea  mov     [rbp+57h+var_78], rdi
0x1800161ee  mov     [rbp+57h+var_68], 0
0x1800161f2  mov     rax, [rdi]
0x1800161f5  lea     rdx, [rbp+57h+var_68]
0x1800161f9  mov     rcx, rdi
0x1800161fc  mov     rax, [rax+38h]
0x180016200  call    cs:__guard_dispatch_icall_fptr
0x180016206  test    eax, eax
0x180016208  js      loc_180016642
0x18001620e  cmp     [rbp+57h+var_68], 0
0x180016212  jnz     short loc_180016223
0x180016214  mov     [rbp+57h+lpMem], rbx
0x180016218  lea     rcx, [rbp+57h+var_78]
0x18001621c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016221  jmp     short loc_180016227
0x180016223  mov     [rbp+57h+lpMem], rdi
0x180016227  lea     rdx, [rbp+57h+var_88]
0x18001622b  lea     rcx, [rbp+57h+lpMem]
0x18001622f  call    ??8Foundation@Windows@winrt@@YA_NAEBUIUnknown@012@0@Z; winrt::Windows::Foundation::operator==(winrt::Windows::Foundation::IUnknown const &,winrt::Windows::Foundation::IUnknown const &)
0x180016234  movzx   edi, al
0x180016237  cmp     [rbp+57h+lpMem], 0
0x18001623c  jz      short loc_180016248
0x18001623e  lea     rcx, [rbp+57h+lpMem]
0x180016242  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016247  nop
0x180016248  cmp     [rbp+57h+var_88], 0
0x18001624d  jz      short loc_180016258
0x18001624f  lea     rcx, [rbp+57h+var_88]
0x180016253  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180016258  test    dil, dil
0x18001625b  jnz     loc_18001664D
0x180016261  mov     [rbp+57h+var_88], rbx
0x180016265  mov     rax, [r12]
0x180016269  lea     rdx, [rbp+57h+var_88]
0x18001626d  mov     rcx, r12
0x180016270  mov     rax, [rax+30h]
0x180016274  call    cs:__guard_dispatch_icall_fptr
0x18001627a  test    eax, eax
0x18001627c  js      loc_18001668B
0x180016282  mov     rdi, [rbp+57h+var_88]
0x180016286  mov     [rbp+57h+var_78], rdi
0x18001628a  mov     [rbp+57h+var_50], rbx
0x18001628e  mov     [rbp+57h+var_D0], 17FEh
0x180016295  mov     rax, [rdi]
0x180016298  lea     rdx, [rbp+57h+var_50]
0x18001629c  mov     rcx, rdi
0x18001629f  mov     rax, [rax+30h]
0x1800162a3  call    cs:__guard_dispatch_icall_fptr
0x1800162a9  test    eax, eax
0x1800162ab  js      loc_180016696
0x1800162b1  test    rdi, rdi
0x1800162b4  jz      short loc_1800162BF
0x1800162b6  lea     rcx, [rbp+57h+var_78]
0x1800162ba  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800162bf  mov     [rbp+57h+var_88], rbx
0x1800162c3  mov     rcx, [rbp+57h+var_50]
0x1800162c7  mov     [rbp+57h+lpMem], rbx
0x1800162cb  test    rcx, rcx
0x1800162ce  jnz     short loc_1800162D8
0x1800162d0  mov     rcx, rbx
0x1800162d3  mov     rdi, rbx
0x1800162d6  jmp     short loc_1800162FA
0x1800162d8  mov     rax, [rcx]
0x1800162db  lea     r8, [rbp+57h+lpMem]
0x1800162df  lea     rdx, ??$guid_v@UIPackage8@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::IPackage8>
0x1800162e6  mov     rax, [rax]
0x1800162e9  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
