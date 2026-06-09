# winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(winrt::Microsoft::Windows::Management::Deployment::PackageSet)

- ea: `0x180016760`
- end: `0x180017027`
- name: `?PreparePackageSetForUse@Workload@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AUPackageSet@Deployment@Management@456@U789456@@Z`
- size: `2247`
- prototype: `__int64 *__fastcall(__int64, __int64 *, _QWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015e40`

## callees

- `0x1800027d0`
- `0x1800029f0`
- `0x180003db0`
- `0x1800040a0`
- `0x180004810`
- `0x1800127c0`
- `0x180013c10`
- `0x180013d70`
- `0x180014230`
- `0x180014650`
- `0x180014bb0`
- `0x180014d10`
- `0x180016760`
- `0x18001b540`
- `0x18001c3a0`
- `0x180030ae5`
- `0x180030aeb`
- `0x180032dc0`
- `0x180034ef0`
- `0x18003bed0`
- `0x18003c020`
- `0x18003c6e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001699b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016e96`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016e9d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016ea4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016f54`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18001699b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016e96`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016e9d`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016ea4`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180016f54`

## string_xrefs

- `0x1800168b2`: `_arm64.msix`
- `0x1800168b9`: `_x64.msix`

## pseudocode

```c
__int64 *__fastcall winrt::Microsoft::Windows::Workloads::implementation::Workload::PreparePackageSetForUse(
        __int64 a1,
        __int64 *a2,
        _QWORD *a3)
{
  volatile signed __int32 *v5; // rsi
  int v6; // eax
  volatile signed __int32 *v7; // rcx
  int v8; // eax
  volatile signed __int32 *v9; // rbx
  int v10; // eax
  int v11; // eax
  HANDLE ProcessHeap; // rax
  bool v13; // al
  wchar_t *v14; // rcx
  int v15; // eax
  LPVOID v16; // rbx
  int v17; // edi
  unsigned int v18; // r15d
  int v19; // eax
  bool i; // zf
  int v21; // edi
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // edi
  int v25; // eax
  volatile signed __int32 *v26; // rbx
  int v27; // edi
  int v28; // eax
  int v29; // eax
  HANDLE v30; // rax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  int v35; // eax
  int v36; // eax
  LPVOID v37; // rbx
  int v38; // edi
  const wchar_t *v39; // rdx
  unsigned __int64 v40; // r8
  int v41; // eax
  HANDLE v42; // rax
  __int128 *p_Src; // rsi
  char *v44; // rbx
  __int64 trivial_2; // rax
  unsigned __int64 v46; // r9
  __int64 v47; // rdx
  __int128 *v48; // rax
  unsigned __int64 v49; // rbx
  _WORD *v50; // rdx
  unsigned __int64 v51; // r8
  int v52; // edi
  __int128 *v53; // rdx
  int v54; // edi
  __int128 *v55; // rdx
  __int64 v56; // rcx
  int v57; // eax
  __int64 (__fastcall *v58)(const struct winrt::Windows::Foundation::IActivationFactory *); // rbx
  int v59; // edi
  int v60; // eax
  int v61; // eax
  LPVOID v62; // rsi
  int v63; // eax
  __int64 v64; // rax
  int v65; // r14d
  __int64 v67; // rax
  int v68; // r14d
  HANDLE v69; // rax
  __int64 v70; // [rsp+20h] [rbp-E0h]
  __int64 v71; // [rsp+28h] [rbp-D8h]
  __int64 v72; // [rsp+30h] [rbp-D0h]
  __int128 v73; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v74; // [rsp+60h] [rbp-A0h]
  __int128 *v75; // [rsp+68h] [rbp-98h]
  void *v76; // [rsp+70h] [rbp-90h]
  _QWORD *v77; // [rsp+78h] [rbp-88h]
  LPVOID v78; // [rsp+80h] [rbp-80h]
  LPVOID v79; // [rsp+88h] [rbp-78h] BYREF
  LPVOID lpMem; // [rsp+90h] [rbp-70h] BYREF
  __int64 (__fastcall *v81)(const struct winrt::Windows::Foundation::IActivationFactory *); // [rsp+98h] [rbp-68h] BYREF
  LPVOID v82; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v83; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v84; // [rsp+B0h] [rbp-50h] BYREF
  int v85; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v86; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v87; // [rsp+C8h] [rbp-38h] BYREF
  __int128 Src; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v89; // [rsp+E0h] [rbp-20h]
  unsigned __int64 v90; // [rsp+E8h] [rbp-18h]
  __int64 *v91; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v92; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v93; // [rsp+108h] [rbp+8h]
  unsigned __int64 v94; // [rsp+110h] [rbp+10h]
  wchar_t Buffer[104]; // [rsp+120h] [rbp+20h] BYREF

  v91 = a2;
  v77 = a3;
  v5 = 0;
  v82 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(**(_QWORD **)(a1 + 24) + 48LL))(*(_QWORD *)(a1 + 24), &v82);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  v7 = (volatile signed __int32 *)v82;
  v78 = v82;
  if ( v82 && *((_DWORD *)v82 + 1) )
  {
    v91 = &qword_180059E98;
    _InterlockedIncrement64(&qword_180059E98);
    if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> )
    {
      _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(
        v82,
        &v87,
        &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>);
      _InterlockedDecrement64(&qword_180059E98);
    }
    else
    {
      _InterlockedDecrement64(&qword_180059E98);
      v81 = _lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_;
      winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
        (__int64)v82,
        (__int64)&v87,
        (void (__fastcall **)(__int64, __int64 *))&v81);
    }
    lpMem = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 48LL))(*a3, &lpMem);
    if ( v8 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v8);
    }
    v9 = (volatile signed __int32 *)lpMem;
    v91 = (__int64 *)lpMem;
    v10 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v87 + 56LL))(v87, lpMem);
    if ( v10 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v10);
    }
    if ( v9 )
    {
      v11 = _InterlockedDecrement(v9 + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
      }
    }
    v13 = IsRunningOnArm64();
    v14 = L"_x64.msix";
    if ( v13 )
      v14 = L"_arm64.msix";
    v76 = v14;
    lpMem = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(*(_QWORD *)*a3 + 80LL))(*a3, &lpMem);
    if ( v15 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v15);
    }
    v16 = lpMem;
    v91 = (__int64 *)lpMem;
    v17 = 245760;
    v18 = 0;
    v85 = 0;
    v19 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)lpMem + 56LL))(lpMem, &v85);
    if ( v19 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v19);
    }
    for ( i = v85 == 0; !i; i = v18 == v85 )
    {
      v84 = 0;
      v21 = v17 | 8;
      v22 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int64 *))(*(_QWORD *)v16 + 48LL))(v16, v18, &v84);
      if ( v22 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v22);
      }
      v79 = &qword_180059E58;
      _InterlockedIncrement64(&qword_180059E58);
      v24 = v21 & 0xFFFFFFE3 | 0x14;
      if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> )
      {
        _lambda_7594da771ace6cdf2aaf7146f13b50fc_::operator()(
          v23,
          &v83,
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>);
        _InterlockedDecrement64(&qword_180059E58);
      }
      else
      {
        _InterlockedDecrement64(&qword_180059E58);
        v79 = _lambda_7594da771ace6cdf2aaf7146f13b50fc_::_lambda_invoker_cdecl_;
        winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
          v23,
          (__int64)&v83,
          (void (__fastcall **)(__int64, __int64 *))&v79);
      }
      v79 = 0;
      v25 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v84 + 64LL))(v84, &v79);
      if ( v25 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v25);
      }
      v26 = (volatile signed __int32 *)v79;
      v27 = v24 | 0x20;
      v28 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v83 + 72LL))(v83, v79);
      if ( v28 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v28);
      }
      if ( v26 )
      {
        v29 = _InterlockedDecrement(v26 + 6);
        if ( v29 )
        {
          if ( v29 < 0 )
            abort();
        }
        else
        {
          v30 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v30, 0, v79);
        }
      }
      v79 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v84 + 80LL))(v84, &v79);
      if ( v31 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v31);
      }
      v32 = (*(__int64 (__fastcall **)(__int64, LPVOID))(*(_QWORD *)v83 + 88LL))(v83, v79);
      if ( v32 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v32);
      }
      LODWORD(v79) = 0;
      v33 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v84 + 96LL))(v84, &v79);
      if ( v33 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v33);
      }
      v34 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v83 + 104LL))(v83, (unsigned int)v79);
      if ( v34 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v34);
      }
      memset(Buffer, 0, 0xC8u);
      v86 = 0;
      v35 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v84 + 80LL))(v84, &v86);
      if ( v35 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v35);
      }
      LODWORD(v72) = HIWORD(v86);
      LODWORD(v71) = WORD2(v86);
      LODWORD(v70) = WORD1(v86);
      swprintf_s(Buffer, 0x64u, L"%hu.%hu.%hu.%hu", (unsigned __int16)v86, v70, v71, v72);
      v79 = 0;
      v36 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v84 + 64LL))(v84, &v79);
      if ( v36 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v36);
      }
      v37 = v79;
      v38 = v27 | 0x40;
      if ( v79 )
      {
        v39 = (const wchar_t *)*((_QWORD *)v79 + 2);
        v5 = (volatile signed __int32 *)v79;
      }
      else
      {
        v39 = &::Src;
      }
      Src = 0;
      v89 = 0;
      v90 = 0;
      v40 = -1;
      do
        ++v40;
      while ( v39[v40] );
      std::wstring::_Construct<1,wchar_t const *>(&Src, v39, v40);
      if ( v37 )
      {
        v41 = _InterlockedDecrement(v5 + 6);
        if ( v41 )
        {
          if ( v41 < 0 )
            abort();
        }
        else
        {
          v42 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v42, 0, (LPVOID)v5);
        }
      }
      p_Src = &Src;
      if ( v90 > 7 )
        p_Src = (__int128 *)Src;
      if ( !v89
        || (_mm_lfence(),
            v44 = (char *)p_Src + 2 * v89,
            trivial_2 = _std_find_trivial_2(p_Src, v44, 95),
            (char *)trivial_2 == v44) )
      {
        v46 = -1;
      }
      else
      {
        v46 = (trivial_2 - (__int64)p_Src) >> 1;
      }
      if ( v89 < v46 )
        std::_String_val<std::_Simple_types<char>>::_Xran();
      _mm_lfence();
      v47 = -1;
      if ( v89 - v46 != -1 )
        v47 = v89 - v46;
      v48 = &Src;
      if ( v90 > 7 )
        v48 = (__int128 *)Src;
      v49 = v89 - v47;
      memmove((char *)v48 + 2 * v46, (char *)v48 + 2 * v46 + 2 * v47, 2 * (v89 - v47 - v46) + 2);
      v89 = v49;
      std::wstring::append(&Src, L"_");
      std::wstring::append(&Src, Buffer);
      std::wstring::append(&Src, v76);
      v50 = (_WORD *)*((_QWORD *)v82 + 2);
      v51 = -1;
      do
        ++v51;
      while ( v50[v51] );
      v92 = 0;
      v93 = 0;
      v94 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v92, v50, v51);
      v52 = v38 | 0x180;
      v53 = &Src;
      if ( v90 > 7 )
        v53 = (__int128 *)Src;
      v73 = 0;
      v74 = 0;
      v75 = 0;
      std::wstring::_Construct<1,wchar_t const *>(&v73, v53, v89);
      v54 = v52 | 0x600;
      std::filesystem::path::operator/=((std::filesystem *)&v92, (std::filesystem *)&v73);
      std::wstring::_Tidy_deallocate((__int64)&v73);
      v55 = &v92;
      if ( v94 > 7 )
        v55 = (__int128 *)v92;
      v56 = -1;
      do
        ++v56;
      while ( *((_WORD *)v55 + v56) );
      if ( (_DWORD)v56 )
      {
        if ( *((_WORD *)v55 + (unsigned int)v56) )
          abort();
        DWORD2(v73) = 1;
        HIDWORD(v73) = v56;
        v75 = v55;
        *(_QWORD *)&v73 = (char *)&v73 + 8;
      }
      else
      {
        *(_QWORD *)&v73 = 0;
      }
      v79 = &v73;
      _InterlockedIncrement64(&qword_180059E78);
      if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
      {
        v81 = 0;
        v57 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 (__fastcall **)(const struct winrt::Windows::Foundation::IActivationFactory *)))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> + 48LL))(
                winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
                v73,
                &v81);
        if ( v57 < 0 )
        {
          _mm_lfence();
          winrt::throw_hresult((unsigned int)v57);
        }
        v58 = v81;
        v59 = v54 | 0x3800;
        _InterlockedDecrement64(&qword_180059E78);
      }
      else
      {
        _InterlockedDecrement64(&qword_180059E78);
        winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
          0,
          &v81,
          (_QWORD **)&v79);
        v59 = v54 | 0x800;
        v58 = v81;
      }
      v60 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall *)(const struct winrt::Windows::Foundation::IActivationFactory *)))(*(_QWORD *)v83 + 120LL))(
              v83,
              v58);
      if ( v60 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v60);
      }
      v79 = 0;
      v61 = (*(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v87 + 80LL))(v87, &v79);
      if ( v61 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v61);
      }
      v62 = v79;
      v17 = v59 | 2;
      v63 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)v79 + 104LL))(v79, v83);
      if ( v63 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v63);
      }
      if ( v62 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v79);
      if ( v58 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
      std::wstring::_Tidy_deallocate((__int64)&v92);
      std::wstring::_Tidy_deallocate((__int64)&Src);
      if ( v83 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
      if ( v84 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v84);
      ++v18;
      v16 = lpMem;
      v5 = 0;
    }
    if ( v16 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v91);
    v64 = v87;
    v87 = 0;
    *a2 = v64;
    v65 = _InterlockedDecrement((volatile signed __int32 *)v82 + 6);
    if ( v65 )
    {
      if ( v65 >= 0 )
        goto LABEL_91;
LABEL_98:
      abort();
    }
LABEL_96:
    v69 = WINRT_IMPL_GetProcessHeap();
    WINRT_IMPL_HeapFree(v69, 0, v82);
    goto LABEL_91;
  }
  v67 = *a3;
  *a3 = 0;
  *a2 = v67;
  if ( !v7 )
    goto LABEL_91;
  v68 = _InterlockedDecrement(v7 + 6);
  if ( !v68 )
    goto LABEL_96;
  if ( v68 < 0 )
    goto LABEL_98;
LABEL_91:
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return a2;
}

```

## disassembly

```asm
0x180016760  mov     [rsp-8+arg_18], rbx
0x180016765  push    rbp
0x180016766  push    rsi
0x180016767  push    rdi
0x180016768  push    r12
0x18001676a  push    r13
0x18001676c  push    r14
0x18001676e  push    r15
0x180016770  lea     rbp, [rsp-100h]
0x180016778  sub     rsp, 200h
0x18001677f  mov     rax, cs:__security_cookie
0x180016786  xor     rax, rsp
0x180016789  mov     [rbp+130h+var_40], rax
0x180016790  mov     r12, r8
0x180016793  mov     r13, rdx
0x180016796  mov     [rbp+130h+var_140], rdx
0x18001679a  mov     [rsp+230h+var_1B8], r8
0x18001679f  xor     esi, esi
0x1800167a1  mov     [rsp+230h+var_1F0], esi
0x1800167a5  mov     [rbp+130h+var_190], rsi
0x1800167a9  mov     rcx, [rcx+18h]
0x1800167ad  mov     rax, [rcx]
0x1800167b0  lea     rdx, [rbp+130h+var_190]
0x1800167b4  mov     rax, [rax+30h]
0x1800167b8  call    cs:__guard_dispatch_icall_fptr
0x1800167be  test    eax, eax
0x1800167c0  js      loc_180016F66
0x1800167c6  mov     rcx, [rbp+130h+var_190]
0x1800167ca  mov     [rbp+130h+var_1B0], rcx
0x1800167ce  test    rcx, rcx
0x1800167d1  jz      loc_180016F16
0x1800167d7  cmp     [rcx+4], esi
0x1800167da  jz      loc_180016F16
0x1800167e0  lea     rax, qword_180059E98
0x1800167e7  mov     [rbp+130h+var_140], rax
0x1800167eb  lock inc cs:qword_180059E98
0x1800167f3  cmp     cs:??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, rsi; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x1800167fa  jz      short loc_180016817
0x1800167fc  lea     r8, ??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180016803  lea     rdx, [rbp+130h+var_168]
0x180016807  call    ??R_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x18001680c  nop
0x18001680d  lock dec cs:qword_180059E98
0x180016815  jmp     short loc_180016838
0x180016817  lock dec cs:qword_180059E98
0x18001681f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180016826  mov     [rbp+130h+var_198], rax
0x18001682a  lea     r8, [rbp+130h+var_198]
0x18001682e  lea     rdx, [rbp+130h+var_168]
0x180016832  call    ??$call@P6A?AUPackageSet@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSet@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x180016837  nop
0x180016838  mov     [rbp+130h+lpMem], rsi
0x18001683c  mov     rcx, [r12]
0x180016840  mov     rax, [rcx]
0x180016843  lea     rdx, [rbp+130h+lpMem]
0x180016847  mov     rax, [rax+30h]
0x18001684b  call    cs:__guard_dispatch_icall_fptr
0x180016851  test    eax, eax
0x180016853  js      loc_180016F71
0x180016859  mov     rbx, [rbp+130h+lpMem]
0x18001685d  mov     [rbp+130h+var_140], rbx
0x180016861  mov     rcx, [rbp+130h+var_168]
0x180016865  mov     rax, [rcx]
0x180016868  mov     rdx, rbx
0x18001686b  mov     rax, [rax+38h]
0x18001686f  call    cs:__guard_dispatch_icall_fptr
0x180016875  test    eax, eax
0x180016877  js      loc_180016F7C
0x18001687d  mov     r14, 0FFFFFFFFFFFFFFFFh
0x180016884  test    rbx, rbx
0x180016887  jz      short loc_1800168AD
0x180016889  mov     eax, r14d
0x18001688c  lock xadd [rbx+18h], eax
0x180016891  sub     eax, 1
0x180016894  jnz     loc_180016993
0x18001689a  call    WINRT_IMPL_GetProcessHeap
0x18001689f  mov     rcx, rax; hHeap
0x1800168a2  mov     r8, [rbp+130h+lpMem]; lpMem
0x1800168a6  xor     edx, edx; dwFlags
0x1800168a8  call    WINRT_IMPL_HeapFree
0x1800168ad  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x1800168b2  lea     rdx, aArm64Msix; "_arm64.msix"
0x1800168b9  lea     rcx, aX64Msix; "_x64.msix"
0x1800168c0  test    al, al
0x1800168c2  cmovnz  rcx, rdx
0x1800168c6  mov     [rsp+230h+var_1C0], rcx
0x1800168cb  mov     [rbp+130h+lpMem], rsi
0x1800168cf  mov     rcx, [r12]
0x1800168d3  mov     rax, [rcx]
0x1800168d6  lea     rdx, [rbp+130h+lpMem]
0x1800168da  mov     rax, [rax+50h]
0x1800168de  call    cs:__guard_dispatch_icall_fptr
0x1800168e4  test    eax, eax
0x1800168e6  js      loc_180016F87
0x1800168ec  mov     rbx, [rbp+130h+lpMem]
0x1800168f0  mov     [rbp+130h+var_140], rbx
0x1800168f4  mov     edi, 3C000h
0x1800168f9  mov     r15d, esi
0x1800168fc  mov     [rbp+130h+var_178], esi
0x1800168ff  mov     rax, [rbx]
0x180016902  lea     rdx, [rbp+130h+var_178]
0x180016906  mov     rcx, rbx
0x180016909  mov     rax, [rax+38h]
0x18001690d  call    cs:__guard_dispatch_icall_fptr
0x180016913  test    eax, eax
0x180016915  js      loc_180016F92
0x18001691b  cmp     [rbp+130h+var_178], esi
0x18001691e  jz      loc_180016EAB
0x180016924  mov     [rbp+130h+var_180], rsi
0x180016928  or      edi, 8
0x18001692b  mov     [rsp+230h+var_1F0], edi
0x18001692f  mov     rax, [rbx]
0x180016932  lea     r8, [rbp+130h+var_180]
0x180016936  mov     edx, r15d
0x180016939  mov     rcx, rbx
0x18001693c  mov     rax, [rax+30h]
0x180016940  call    cs:__guard_dispatch_icall_fptr
0x180016946  test    eax, eax
0x180016948  js      loc_180016F5B
0x18001694e  and     edi, 0FFFFFFF7h
0x180016951  or      edi, 4
0x180016954  mov     [rsp+230h+var_1F0], edi
0x180016958  lea     rax, qword_180059E58
0x18001695f  mov     [rbp+130h+var_1A8], rax
0x180016963  lock inc cs:qword_180059E58
0x18001696b  or      edi, 10h
0x18001696e  cmp     cs:??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x180016976  jz      short loc_1800169A2
0x180016978  lea     r8, ??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x18001697f  lea     rdx, [rbp+130h+var_188]
0x180016983  call    ??R_lambda_7594da771ace6cdf2aaf7146f13b50fc_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_7594da771ace6cdf2aaf7146f13b50fc_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180016988  nop
0x180016989  lock dec cs:qword_180059E58
0x180016991  jmp     short loc_1800169C3
0x180016993  test    eax, eax
0x180016995  jns     loc_1800168AD
0x18001699b  call    cs:__imp_abort
0x1800169a2  lock dec cs:qword_180059E58
0x1800169aa  lea     rax, ?_lambda_invoker_cdecl_@_lambda_7594da771ace6cdf2aaf7146f13b50fc_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_7594da771ace6cdf2aaf7146f13b50fc_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800169b1  mov     [rbp+130h+var_1A8], rax
0x1800169b5  lea     r8, [rbp+130h+var_1A8]
0x1800169b9  lea     rdx, [rbp+130h+var_188]
0x1800169bd  call    ??$call@P6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800169c2  nop
0x1800169c3  mov     [rbp+130h+var_1A8], rsi
0x1800169c7  mov     rcx, [rbp+130h+var_180]
0x1800169cb  mov     rax, [rcx]
0x1800169ce  lea     rdx, [rbp+130h+var_1A8]
0x1800169d2  mov     rax, [rax+40h]
0x1800169d6  call    cs:__guard_dispatch_icall_fptr
0x1800169dc  test    eax, eax
0x1800169de  js      loc_18001701C
0x1800169e4  mov     rbx, [rbp+130h+var_1A8]
0x1800169e8  mov     [rsp+230h+var_1E8], rbx
0x1800169ed  or      edi, 20h
0x1800169f0  mov     rcx, [rbp+130h+var_188]
0x1800169f4  mov     rax, [rcx]
0x1800169f7  mov     rdx, rbx
0x1800169fa  mov     rax, [rax+48h]
0x1800169fe  call    cs:__guard_dispatch_icall_fptr
0x180016a04  test    eax, eax
0x180016a06  js      loc_180017011
0x180016a0c  test    rbx, rbx
0x180016a0f  jz      short loc_180016A3B
0x180016a11  mov     eax, r14d
0x180016a14  lock xadd [rbx+18h], eax
0x180016a19  sub     eax, 1
0x180016a1c  jnz     short loc_180016A33
0x180016a1e  call    WINRT_IMPL_GetProcessHeap
0x180016a23  mov     rcx, rax; hHeap
0x180016a26  mov     r8, [rbp+130h+var_1A8]; lpMem
0x180016a2a  xor     edx, edx; dwFlags
0x180016a2c  call    WINRT_IMPL_HeapFree
0x180016a31  jmp     short loc_180016A3B
0x180016a33  test    eax, eax
0x180016a35  js      loc_180016E96
0x180016a3b  mov     [rbp+130h+var_1A8], rsi
0x180016a3f  mov     rcx, [rbp+130h+var_180]
0x180016a43  mov     rax, [rcx]
0x180016a46  lea     rdx, [rbp+130h+var_1A8]
0x180016a4a  mov     rax, [rax+50h]
0x180016a4e  call    cs:__guard_dispatch_icall_fptr
0x180016a54  test    eax, eax
0x180016a56  js      loc_180017006
0x180016a5c  mov     rcx, [rbp+130h+var_188]
0x180016a60  mov     rax, [rcx]
0x180016a63  mov     rdx, [rbp+130h+var_1A8]
0x180016a67  mov     rax, [rax+58h]
0x180016a6b  call    cs:__guard_dispatch_icall_fptr
0x180016a71  test    eax, eax
0x180016a73  js      loc_180016FFB
0x180016a79  mov     dword ptr [rbp+130h+var_1A8], esi
0x180016a7c  mov     rcx, [rbp+130h+var_180]
0x180016a80  mov     rax, [rcx]
0x180016a83  lea     rdx, [rbp+130h+var_1A8]
0x180016a87  mov     rax, [rax+60h]
0x180016a8b  call    cs:__guard_dispatch_icall_fptr
0x180016a91  test    eax, eax
0x180016a93  js      loc_180016FF0
0x180016a99  mov     rcx, [rbp+130h+var_188]
0x180016a9d  mov     rax, [rcx]
0x180016aa0  mov     edx, dword ptr [rbp+130h+var_1A8]
0x180016aa3  mov     rax, [rax+68h]
0x180016aa7  call    cs:__guard_dispatch_icall_fptr
0x180016aad  test    eax, eax
0x180016aaf  js      loc_180016FE5
0x180016ab5  xor     edx, edx; Val
0x180016ab7  mov     r8d, 0C8h; Size
0x180016abd  lea     rcx, [rbp+130h+Buffer]; void *
0x180016ac1  call    memset
0x180016ac6  mov     [rbp+130h+var_170], rsi
0x180016aca  mov     rcx, [rbp+130h+var_180]
0x180016ace  mov     rax, [rcx]
0x180016ad1  lea     rdx, [rbp+130h+var_170]
0x180016ad5  mov     rax, [rax+50h]
0x180016ad9  call    cs:__guard_dispatch_icall_fptr
0x180016adf  test    eax, eax
0x180016ae1  js      loc_180016FDA
0x180016ae7  movzx   eax, word ptr [rbp+130h+var_170+6]
0x180016aeb  movzx   ecx, word ptr [rbp+130h+var_170+4]
0x180016aef  movzx   edx, word ptr [rbp+130h+var_170+2]
0x180016af3  movzx   r9d, word ptr [rbp+130h+var_170]
0x180016af8  mov     [rsp+230h+var_200], eax
0x180016afc  mov     dword ptr [rsp+230h+var_208], ecx
0x180016b00  mov     dword ptr [rsp+230h+var_210], edx
0x180016b04  lea     r8, aHuHuHuHu; "%hu.%hu.%hu.%hu"
0x180016b0b  mov     edx, 64h ; 'd'; BufferCount
0x180016b10  lea     rcx, [rbp+130h+Buffer]; Buffer
0x180016b14  call    swprintf_s
0x180016b19  mov     [rbp+130h+var_1A8], rsi
0x180016b1d  mov     rcx, [rbp+130h+var_180]
0x180016b21  mov     rax, [rcx]
0x180016b24  lea     rdx, [rbp+130h+var_1A8]
0x180016b28  mov     rax, [rax+40h]
0x180016b2c  call    cs:__guard_dispatch_icall_fptr
0x180016b32  test    eax, eax
0x180016b34  js      loc_180016FCF
0x180016b3a  mov     rbx, [rbp+130h+var_1A8]
0x180016b3e  mov     [rsp+230h+var_1E8], rbx
0x180016b43  or      edi, 40h
0x180016b46  test    rbx, rbx
0x180016b49  jz      short loc_180016B54
0x180016b4b  mov     rdx, [rbx+10h]
0x180016b4f  mov     rsi, rbx
0x180016b52  jmp     short loc_180016B5B
0x180016b54  lea     rdx, Src
0x180016b5b  xorps   xmm0, xmm0
0x180016b5e  movups  [rbp+130h+Src], xmm0
0x180016b62  xor     eax, eax
0x180016b64  mov     [rbp+130h+var_150], rax
0x180016b68  mov     [rbp+130h+var_148], rax
0x180016b6c  mov     r8, r14
0x180016b6f  nop
0x180016b70  inc     r8
0x180016b73  cmp     [rdx+r8*2], ax
0x180016b78  jnz     short loc_180016B70
0x180016b7a  lea     rcx, [rbp+130h+Src]
0x180016b7e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180016b83  nop
0x180016b84  test    rbx, rbx
0x180016b87  jz      short loc_180016BB2
0x180016b89  mov     eax, r14d
0x180016b8c  lock xadd [rsi+18h], eax
0x180016b91  sub     eax, 1
0x180016b94  jnz     short loc_180016BAA
0x180016b96  call    WINRT_IMPL_GetProcessHeap
0x180016b9b  mov     rcx, rax; hHeap
0x180016b9e  mov     r8, rsi; lpMem
0x180016ba1  xor     edx, edx; dwFlags
0x180016ba3  call    WINRT_IMPL_HeapFree
0x180016ba8  jmp     short loc_180016BB2
0x180016baa  test    eax, eax
0x180016bac  js      loc_180016E9D
0x180016bb2  lea     rsi, [rbp+130h+Src]
0x180016bb6  cmp     [rbp+130h+var_148], 7
0x180016bbb  cmova   rsi, qword ptr [rbp+130h+Src]
0x180016bc0  cmp     [rbp+130h+var_150], 0
0x180016bc5  jbe     short loc_180016BF3
0x180016bc7  lfence
0x180016bca  mov     rax, [rbp+130h+var_150]
0x180016bce  lea     rbx, [rsi+rax*2]
0x180016bd2  mov     r8d, 5Fh ; '_'
0x180016bd8  mov     rdx, rbx
0x180016bdb  mov     rcx, rsi
0x180016bde  call    __std_find_trivial_2
0x180016be3  mov     r9, rax
0x180016be6  cmp     rax, rbx
0x180016be9  jz      short loc_180016BF3
0x180016beb  sub     r9, rsi
0x180016bee  sar     r9, 1
0x180016bf1  jmp     short loc_180016BF6
0x180016bf3  mov     r9, r14
0x180016bf6  cmp     [rbp+130h+var_150], r9
0x180016bfa  jb      loc_180016FC9
0x180016c00  lfence
0x180016c03  mov     rbx, [rbp+130h+var_150]
0x180016c07  mov     rax, rbx
0x180016c0a  sub     rax, r9
0x180016c0d  mov     rdx, r14
0x180016c10  cmp     rax, r14
  ... truncated ...
```
