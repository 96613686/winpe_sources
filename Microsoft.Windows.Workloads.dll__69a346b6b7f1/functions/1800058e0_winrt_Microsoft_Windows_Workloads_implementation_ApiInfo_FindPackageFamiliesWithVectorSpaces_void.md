# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::FindPackageFamiliesWithVectorSpaces(void)

- ea: `0x1800058e0`
- end: `0x1800060ab`
- name: `?FindPackageFamiliesWithVectorSpaces@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAAXXZ`
- size: `1995`
- prototype: `void __fastcall(winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800057f0`

## callees

- `0x1800029f0`
- `0x1800040a0`
- `0x180004810`
- `0x180004c70`
- `0x180005750`
- `0x1800058e0`
- `0x1800098d0`
- `0x18000c970`
- `0x1800157c0`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006004`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000600b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006012`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006019`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006020`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006004`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000600b`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006012`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006019`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006020`

## string_xrefs

- `0x180005932`: `com.microsoft.windows.workload.vectorspace`

## pseudocode

```c
void __fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::FindPackageFamiliesWithVectorSpaces(
        winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *this)
{
  winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *v1; // rbx
  int v2; // eax
  __int64 v3; // rcx
  int v4; // r14d
  int v5; // r14d
  int v6; // eax
  unsigned int v7; // r14d
  unsigned int v8; // esi
  int v9; // eax
  int v10; // r14d
  int v11; // eax
  unsigned int v12; // r14d
  int v13; // eax
  __int64 v14; // rdi
  int v15; // r14d
  int v16; // eax
  __int64 v17; // rbx
  int v18; // r14d
  int v19; // eax
  int v20; // r14d
  int v21; // eax
  __int64 v22; // rdi
  int v23; // r14d
  int v24; // eax
  __int64 v25; // rbx
  int v26; // r14d
  int v27; // eax
  int v28; // eax
  __int64 v29; // rax
  int v30; // r14d
  __int64 v31; // rbx
  __int64 (__fastcall *v32)(__int64, LPVOID, __int64 *); // rdi
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r15
  __int64 v36; // rcx
  __int64 v37; // rcx
  volatile signed __int32 *v38; // rsi
  struct winrt::impl::hstring_header *v39; // rdx
  volatile signed __int32 *v40; // r13
  volatile signed __int32 *v41; // rdi
  struct winrt::impl::hstring_header *v42; // rdx
  volatile signed __int32 *v43; // r12
  const wchar_t *v44; // rbx
  struct winrt::impl::hstring_header *v45; // rdx
  struct winrt::impl::hstring_header *v46; // rdx
  struct winrt::impl::hstring_header *v47; // rdx
  void *v48; // rbx
  int v49; // eax
  HANDLE ProcessHeap; // rax
  int v51; // eax
  HANDLE v52; // rax
  int v53; // eax
  HANDLE v54; // rax
  int v55; // eax
  HANDLE v56; // rax
  int v57; // eax
  HANDLE v58; // rax
  int v59; // eax
  HANDLE v60; // rax
  __int64 v61; // [rsp+20h] [rbp-E0h]
  __int64 v62; // [rsp+20h] [rbp-E0h]
  unsigned int v63; // [rsp+24h] [rbp-DCh]
  LPVOID lpMem[2]; // [rsp+28h] [rbp-D8h] BYREF
  struct winrt::impl::hstring_header *v65; // [rsp+38h] [rbp-C8h]
  const wchar_t *v66; // [rsp+40h] [rbp-C0h]
  LPVOID *v67; // [rsp+48h] [rbp-B8h]
  __int64 v68; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v69; // [rsp+58h] [rbp-A8h] BYREF
  winrt::Microsoft::Windows::Workloads::implementation::ApiInfo *v70; // [rsp+60h] [rbp-A0h]
  __int64 v71; // [rsp+68h] [rbp-98h] BYREF
  __int64 v72; // [rsp+70h] [rbp-90h] BYREF
  __int128 v73; // [rsp+78h] [rbp-88h] BYREF
  __int64 v74; // [rsp+88h] [rbp-78h]
  __int64 v75; // [rsp+90h] [rbp-70h]
  winrt::impl *v76; // [rsp+98h] [rbp-68h]
  volatile signed __int32 *v77; // [rsp+A0h] [rbp-60h]
  volatile signed __int32 *v78; // [rsp+A8h] [rbp-58h]
  const wchar_t *v79; // [rsp+B0h] [rbp-50h]
  char v80[16]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v81; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v82; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v83; // [rsp+D8h] [rbp-28h] BYREF
  winrt::impl *v84; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v85; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v86; // [rsp+F0h] [rbp-10h] BYREF
  int v87; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v88; // [rsp+100h] [rbp+0h] BYREF
  winrt::impl *v89; // [rsp+108h] [rbp+8h] BYREF
  const wchar_t *v90; // [rsp+110h] [rbp+10h] BYREF
  winrt::impl *v91; // [rsp+118h] [rbp+18h] BYREF
  __int64 *v92; // [rsp+120h] [rbp+20h] BYREF

  v1 = this;
  v70 = this;
  lpMem[1] = (LPVOID)0x2A00000001LL;
  v66 = L"com.microsoft.windows.workload.vectorspace";
  lpMem[0] = &lpMem[1];
  v89 = (winrt::impl *)lpMem;
  v92 = &qword_180059EC8;
  _InterlockedIncrement64(&qword_180059EC8);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> )
  {
    v83 = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
                                                               + 48LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
           lpMem[0],
           &v83);
    if ( v2 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v2);
    }
    v3 = v83;
    v4 = 14336;
    _InterlockedDecrement64(&qword_180059EC8);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059EC8);
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::call<_lambda_cb41fde99ba74c6248b3ce76f09f9615_ &>(
      0,
      &v83,
      (_QWORD **)&v89);
    v4 = 2048;
    v3 = v83;
  }
  v5 = v4 | 0x400;
  v85 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v3 + 48LL))(v3, &v85);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  v92 = v85;
  v7 = v5 | 0x4000;
  v8 = 0;
  HIDWORD(v61) = 0;
  v87 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v85 + 56))(v85, &v87);
  if ( v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9);
  }
  if ( v87 )
  {
    do
    {
      v88 = 0;
      v10 = v7 | 4;
      v11 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(*v85 + 48))(v85, v8, &v88);
      if ( v11 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v11);
      }
      v12 = v10 & 0xFFFFFFF9 | 2;
      v81 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 72LL))(v88, &v81);
      if ( v13 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v13);
      }
      v14 = v81;
      v86 = v81;
      v15 = v12 | 8;
      v81 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 48LL))(v86, &v81);
      if ( v16 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v16);
      }
      v17 = v81;
      v18 = v15 | 0x10;
      v84 = 0;
      v19 = (*(__int64 (__fastcall **)(__int64, winrt::impl **))(*(_QWORD *)v81 + 104LL))(v81, &v84);
      if ( v19 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v19);
      }
      v76 = v84;
      v20 = v18 | 1;
      if ( v17 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
      if ( v14 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
      v81 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 72LL))(v88, &v81);
      if ( v21 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v21);
      }
      v22 = v81;
      v86 = v81;
      v23 = v20 | 0x20;
      v81 = 0;
      v24 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v86 + 48LL))(v86, &v81);
      if ( v24 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v24);
      }
      v25 = v81;
      v26 = v23 | 0x40;
      v90 = 0;
      v27 = (*(__int64 (__fastcall **)(__int64, const wchar_t **))(*(_QWORD *)v81 + 56LL))(v81, &v90);
      if ( v27 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v27);
      }
      if ( v25 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v81);
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
      v81 = 0;
      v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v88 + 80LL))(v88, &v81);
      if ( v28 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v28);
      }
      v72 = v81;
      lpMem[1] = (LPVOID)0xB00000001LL;
      v66 = L"VectorSpace";
      lpMem[0] = &lpMem[1];
      v29 = 0;
      v86 = 0;
      v30 = v26 | 0x180;
      LODWORD(v61) = v30;
      if ( v81 )
      {
        v82 = 0;
        (**(void (__fastcall ***)(__int64, __int64 *, __int64 *))v81)(
          v81,
          winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
          &v82);
        v31 = v82;
        v29 = v86;
      }
      else
      {
        v31 = 0;
      }
      v82 = v31;
      v32 = *(__int64 (__fastcall **)(__int64, LPVOID, __int64 *))(*(_QWORD *)v31 + 48LL);
      if ( v29 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
      v33 = v32(v31, lpMem[0], &v86);
      if ( v33 != -2147483637 && v33 != -2147467259 && v33 != -2147024894 && v33 < 0 )
      {
        _mm_lfence();
        winrt::throw_hresult((unsigned int)v33);
      }
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v82);
      v34 = v86;
      if ( v86 )
      {
        v82 = 0;
        (**(void (__fastcall ***)(__int64, __int64 *, __int64 *))v86)(
          v86,
          winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>,
          &v82);
        v35 = v82;
        v71 = v82;
        if ( v82 )
        {
          *(_OWORD *)lpMem = 0;
          v65 = 0;
          v66 = 0;
          std::wstring::_Construct<1,wchar_t const *>(lpMem, L"@Id", 3u);
          v68 = v35;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
          winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
            v36,
            &v89,
            &v68,
            lpMem,
            v61);
          v73 = 0;
          v74 = 0;
          v75 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v73, L"@Type", 5u);
          v69 = v35;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
          winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(
            v37,
            &v91,
            &v69,
            &v73,
            v62);
          v38 = (volatile signed __int32 *)v89;
          v40 = (volatile signed __int32 *)winrt::impl::duplicate_hstring(v89, v39);
          v77 = v40;
          v41 = (volatile signed __int32 *)v91;
          v43 = (volatile signed __int32 *)winrt::impl::duplicate_hstring(v91, v42);
          v78 = v43;
          v44 = v90;
          v79 = v90;
          lpMem[0] = winrt::impl::duplicate_hstring(v84, v45);
          v67 = &lpMem[1];
          lpMem[1] = winrt::impl::duplicate_hstring((winrt::impl *)v40, v46);
          v65 = winrt::impl::duplicate_hstring((winrt::impl *)v43, v47);
          v66 = v44;
          v30 |= 0x200u;
          std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>,0>>::_Emplace<std::pair<winrt::hstring,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>(
            (char *)v70 + 104,
            v80,
            lpMem);
          winrt::Microsoft::Windows::Workloads::implementation::VectorSpace::~VectorSpace((winrt::Microsoft::Windows::Workloads::implementation::VectorSpace *)&lpMem[1]);
          v48 = lpMem[0];
          if ( lpMem[0] )
          {
            v49 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
            if ( v49 )
            {
              if ( v49 < 0 )
                abort();
            }
            else
            {
              ProcessHeap = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(ProcessHeap, 0, v48);
            }
            lpMem[0] = 0;
            v35 = v82;
          }
          if ( v43 )
          {
            v51 = _InterlockedDecrement(v43 + 6);
            if ( v51 )
            {
              if ( v51 < 0 )
                goto LABEL_80;
            }
            else
            {
              v52 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v52, 0, (LPVOID)v43);
            }
            v35 = v82;
          }
          if ( v40 )
          {
            v53 = _InterlockedDecrement(v40 + 6);
            if ( v53 )
            {
              if ( v53 < 0 )
LABEL_80:
                abort();
            }
            else
            {
              v54 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v54, 0, (LPVOID)v40);
            }
            v35 = v82;
          }
          if ( v41 )
          {
            v55 = _InterlockedDecrement(v41 + 6);
            if ( v55 )
            {
              if ( v55 < 0 )
                abort();
              v91 = 0;
              v35 = v82;
            }
            else
            {
              v56 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v56, 0, (LPVOID)v41);
              v91 = 0;
              v35 = v82;
            }
          }
          if ( v38 )
          {
            v57 = _InterlockedDecrement(v38 + 6);
            if ( v57 )
            {
              if ( v57 < 0 )
                abort();
            }
            else
            {
              v58 = WINRT_IMPL_GetProcessHeap();
              WINRT_IMPL_HeapFree(v58, 0, (LPVOID)v38);
            }
            v89 = 0;
            v35 = v82;
          }
          v8 = v63;
        }
        if ( v35 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v71);
        v34 = v86;
      }
      v7 = v30 & 0xFFFFFEFF;
      if ( v34 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v86);
      if ( v81 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v72);
      if ( v84 )
      {
        v59 = _InterlockedDecrement((volatile signed __int32 *)v84 + 6);
        if ( v59 )
        {
          if ( v59 < 0 )
            abort();
        }
        else
        {
          v60 = WINRT_IMPL_GetProcessHeap();
          WINRT_IMPL_HeapFree(v60, 0, v84);
        }
      }
      if ( v88 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v88);
      HIDWORD(v61) = ++v8;
    }
    while ( v8 != v87 );
    v1 = v70;
  }
  if ( v85 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v92);
  *((_BYTE *)v1 + 73) = 1;
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v83);
}

```

## disassembly

```asm
0x1800058e0  mov     [rsp-8+arg_8], rbx
0x1800058e5  mov     [rsp-8+arg_10], rsi
0x1800058ea  mov     [rsp-8+arg_18], rdi
0x1800058ef  push    rbp
0x1800058f0  push    r12
0x1800058f2  push    r13
0x1800058f4  push    r14
0x1800058f6  push    r15
0x1800058f8  lea     rbp, [rsp-30h]
0x1800058fd  sub     rsp, 130h
0x180005904  mov     rax, cs:__security_cookie
0x18000590b  xor     rax, rsp
0x18000590e  mov     [rbp+50h+var_28], rax
0x180005912  mov     rbx, rcx
0x180005915  mov     [rsp+150h+var_F0], rcx
0x18000591a  xor     r12d, r12d
0x18000591d  mov     [rsp+150h+var_130], r12d
0x180005922  mov     dword ptr [rsp+150h+lpMem+8], 1
0x18000592a  mov     dword ptr [rsp+150h+lpMem+0Ch], 2Ah ; '*'
0x180005932  lea     rax, aComMicrosoftWi; "com.microsoft.windows.workload.vectorsp"...
0x180005939  mov     [rsp+150h+var_110], rax
0x18000593e  lea     rax, [rsp+150h+lpMem+8]
0x180005943  mov     [rsp+150h+lpMem], rax
0x180005948  lea     rax, [rsp+150h+lpMem]
0x18000594d  mov     [rbp+50h+var_48], rax
0x180005951  lea     rax, qword_180059EC8
0x180005958  mov     [rbp+50h+var_30], rax
0x18000595c  lock inc cs:qword_180059EC8
0x180005964  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x18000596b  test    rcx, rcx
0x18000596e  jz      short loc_1800059AA
0x180005970  mov     [rbp+50h+var_78], r12
0x180005974  mov     rax, [rcx]
0x180005977  lea     r8, [rbp+50h+var_78]
0x18000597b  mov     rdx, [rsp+150h+lpMem]
0x180005980  mov     rax, [rax+30h]
0x180005984  call    cs:__guard_dispatch_icall_fptr
0x18000598a  test    eax, eax
0x18000598c  js      loc_18000603D
0x180005992  mov     rcx, [rbp+50h+var_78]
0x180005996  mov     [rbp+50h+var_78], rcx
0x18000599a  mov     r14d, 3800h
0x1800059a0  lock dec cs:qword_180059EC8
0x1800059a8  jmp     short loc_1800059C9
0x1800059aa  lock dec cs:qword_180059EC8
0x1800059b2  lea     r8, [rbp+50h+var_48]
0x1800059b6  lea     rdx, [rbp+50h+var_78]
0x1800059ba  call    ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z
0x1800059bf  mov     r14d, 800h
0x1800059c5  mov     rcx, [rbp+50h+var_78]
0x1800059c9  bts     r14d, 0Ah
0x1800059ce  mov     [rbp+50h+var_68], r12
0x1800059d2  mov     rax, [rcx]
0x1800059d5  lea     rdx, [rbp+50h+var_68]
0x1800059d9  mov     rax, [rax+30h]
0x1800059dd  call    cs:__guard_dispatch_icall_fptr
0x1800059e3  test    eax, eax
0x1800059e5  js      loc_180006048
0x1800059eb  mov     rcx, [rbp+50h+var_68]
0x1800059ef  mov     [rbp+50h+var_30], rcx
0x1800059f3  bts     r14d, 0Eh
0x1800059f8  mov     esi, r12d
0x1800059fb  mov     [rsp+150h+var_12C], r12d
0x180005a00  mov     [rbp+50h+var_58], r12d
0x180005a04  mov     rax, [rcx]
0x180005a07  lea     rdx, [rbp+50h+var_58]
0x180005a0b  mov     rax, [rax+38h]
0x180005a0f  call    cs:__guard_dispatch_icall_fptr
0x180005a15  test    eax, eax
0x180005a17  js      loc_180006053
0x180005a1d  cmp     [rbp+50h+var_58], r12d
0x180005a21  jz      loc_180005FBA
0x180005a27  lea     r15, aVectorspace; "VectorSpace"
0x180005a2e  xchg    ax, ax
0x180005a30  mov     [rbp+50h+var_50], r12
0x180005a34  or      r14d, 4
0x180005a38  mov     [rsp+150h+var_130], r14d
0x180005a3d  mov     rcx, [rbp+50h+var_68]
0x180005a41  mov     rax, [rcx]
0x180005a44  lea     r8, [rbp+50h+var_50]
0x180005a48  mov     edx, esi
0x180005a4a  mov     rax, [rax+30h]
0x180005a4e  call    cs:__guard_dispatch_icall_fptr
0x180005a54  test    eax, eax
0x180005a56  js      loc_180006032
0x180005a5c  and     r14d, 0FFFFFFFBh
0x180005a60  or      r14d, 2
0x180005a64  mov     [rbp+50h+var_88], r12
0x180005a68  mov     rcx, [rbp+50h+var_50]
0x180005a6c  mov     rax, [rcx]
0x180005a6f  lea     rdx, [rbp+50h+var_88]
0x180005a73  mov     rax, [rax+48h]
0x180005a77  call    cs:__guard_dispatch_icall_fptr
0x180005a7d  test    eax, eax
0x180005a7f  js      loc_180006027
0x180005a85  mov     rdi, [rbp+50h+var_88]
0x180005a89  mov     [rbp+50h+var_60], rdi
0x180005a8d  or      r14d, 8
0x180005a91  mov     [rbp+50h+var_88], r12
0x180005a95  mov     rax, [rdi]
0x180005a98  lea     rdx, [rbp+50h+var_88]
0x180005a9c  mov     rcx, rdi
0x180005a9f  mov     rax, [rax+30h]
0x180005aa3  call    cs:__guard_dispatch_icall_fptr
0x180005aa9  test    eax, eax
0x180005aab  js      loc_1800060A0
0x180005ab1  mov     rbx, [rbp+50h+var_88]
0x180005ab5  mov     [rbp+50h+var_88], rbx
0x180005ab9  or      r14d, 10h
0x180005abd  mov     [rbp+50h+var_70], r12
0x180005ac1  mov     rax, [rbx]
0x180005ac4  lea     rdx, [rbp+50h+var_70]
0x180005ac8  mov     rcx, rbx
0x180005acb  mov     rax, [rax+68h]
0x180005acf  call    cs:__guard_dispatch_icall_fptr
0x180005ad5  test    eax, eax
0x180005ad7  js      loc_180006095
0x180005add  mov     rax, [rbp+50h+var_70]
0x180005ae1  mov     [rbp+50h+var_B8], rax
0x180005ae5  or      r14d, 1
0x180005ae9  test    rbx, rbx
0x180005aec  jz      short loc_180005AF8
0x180005aee  lea     rcx, [rbp+50h+var_88]
0x180005af2  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005af7  nop
0x180005af8  test    rdi, rdi
0x180005afb  jz      short loc_180005B06
0x180005afd  lea     rcx, [rbp+50h+var_60]
0x180005b01  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005b06  mov     [rbp+50h+var_88], r12
0x180005b0a  mov     rcx, [rbp+50h+var_50]
0x180005b0e  mov     rax, [rcx]
0x180005b11  lea     rdx, [rbp+50h+var_88]
0x180005b15  mov     rax, [rax+48h]
0x180005b19  call    cs:__guard_dispatch_icall_fptr
0x180005b1f  test    eax, eax
0x180005b21  js      loc_18000608A
0x180005b27  mov     rdi, [rbp+50h+var_88]
0x180005b2b  mov     [rbp+50h+var_60], rdi
0x180005b2f  or      r14d, 20h
0x180005b33  mov     [rbp+50h+var_88], r12
0x180005b37  mov     rax, [rdi]
0x180005b3a  lea     rdx, [rbp+50h+var_88]
0x180005b3e  mov     rcx, rdi
0x180005b41  mov     rax, [rax+30h]
0x180005b45  call    cs:__guard_dispatch_icall_fptr
0x180005b4b  test    eax, eax
0x180005b4d  js      loc_18000607F
0x180005b53  mov     rbx, [rbp+50h+var_88]
0x180005b57  mov     [rbp+50h+var_88], rbx
0x180005b5b  or      r14d, 40h
0x180005b5f  mov     [rbp+50h+var_40], r12
0x180005b63  mov     rax, [rbx]
0x180005b66  lea     rdx, [rbp+50h+var_40]
0x180005b6a  mov     rcx, rbx
0x180005b6d  mov     rax, [rax+38h]
0x180005b71  call    cs:__guard_dispatch_icall_fptr
0x180005b77  test    eax, eax
0x180005b79  js      loc_180006074
0x180005b7f  test    rbx, rbx
0x180005b82  jz      short loc_180005B8E
0x180005b84  lea     rcx, [rbp+50h+var_88]
0x180005b88  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005b8d  nop
0x180005b8e  test    rdi, rdi
0x180005b91  jz      short loc_180005B9C
0x180005b93  lea     rcx, [rbp+50h+var_60]
0x180005b97  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005b9c  mov     [rbp+50h+var_88], r12
0x180005ba0  mov     rcx, [rbp+50h+var_50]
0x180005ba4  mov     rax, [rcx]
0x180005ba7  lea     rdx, [rbp+50h+var_88]
0x180005bab  mov     rax, [rax+50h]
0x180005baf  call    cs:__guard_dispatch_icall_fptr
0x180005bb5  test    eax, eax
0x180005bb7  js      loc_180006069
0x180005bbd  mov     rcx, [rbp+50h+var_88]
0x180005bc1  mov     [rsp+150h+var_E0], rcx
0x180005bc6  bts     r14d, 7
0x180005bcb  mov     dword ptr [rsp+150h+lpMem+8], 1
0x180005bd3  mov     dword ptr [rsp+150h+lpMem+0Ch], 0Bh
0x180005bdb  mov     [rsp+150h+var_110], r15
0x180005be0  lea     rax, [rsp+150h+lpMem+8]
0x180005be5  mov     [rsp+150h+lpMem], rax
0x180005bea  mov     rax, r12
0x180005bed  mov     [rbp+50h+var_60], rax
0x180005bf1  bts     r14d, 8
0x180005bf6  mov     [rsp+150h+var_130], r14d
0x180005bfb  test    rcx, rcx
0x180005bfe  jnz     short loc_180005C05
0x180005c00  mov     rbx, r12
0x180005c03  jmp     short loc_180005C2C
0x180005c05  mov     [rbp+50h+var_80], r12
0x180005c09  mov     rcx, [rbp+50h+var_88]
0x180005c0d  mov     rax, [rcx]
0x180005c10  lea     r8, [rbp+50h+var_80]
0x180005c14  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x180005c1b  mov     rax, [rax]
0x180005c1e  call    cs:__guard_dispatch_icall_fptr
0x180005c24  mov     rbx, [rbp+50h+var_80]
0x180005c28  mov     rax, [rbp+50h+var_60]
0x180005c2c  mov     [rbp+50h+var_80], rbx
0x180005c30  mov     rcx, [rbx]
0x180005c33  mov     rdi, [rcx+30h]
0x180005c37  test    rax, rax
0x180005c3a  jz      short loc_180005C45
0x180005c3c  lea     rcx, [rbp+50h+var_60]
0x180005c40  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005c45  lea     r8, [rbp+50h+var_60]
0x180005c49  mov     rdx, [rsp+150h+lpMem]
0x180005c4e  mov     rcx, rbx
0x180005c51  mov     rax, rdi
0x180005c54  call    cs:__guard_dispatch_icall_fptr
0x180005c5a  cmp     eax, 8000000Bh
0x180005c5f  jz      short loc_180005C77
0x180005c61  cmp     eax, 80004005h
0x180005c66  jz      short loc_180005C77
0x180005c68  cmp     eax, 80070002h
0x180005c6d  jz      short loc_180005C77
0x180005c6f  test    eax, eax
0x180005c71  js      loc_18000605E
0x180005c77  lea     rcx, [rbp+50h+var_80]
0x180005c7b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180005c80  mov     rcx, [rbp+50h+var_60]
0x180005c84  test    rcx, rcx
0x180005c87  jz      loc_180005F3B
0x180005c8d  mov     [rbp+50h+var_80], r12
0x180005c91  mov     rax, [rcx]
0x180005c94  lea     r8, [rbp+50h+var_80]
0x180005c98  lea     rdx, ??$guid_v@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>>
0x180005c9f  mov     rax, [rax]
0x180005ca2  call    cs:__guard_dispatch_icall_fptr
0x180005ca8  mov     r15, [rbp+50h+var_80]
0x180005cac  mov     [rsp+150h+var_E8], r15
0x180005cb1  test    r15, r15
0x180005cb4  jz      loc_180005F21
0x180005cba  xorps   xmm0, xmm0
0x180005cbd  movups  xmmword ptr [rsp+150h+lpMem], xmm0
0x180005cc2  mov     [rsp+150h+var_118], r12
0x180005cc7  mov     [rsp+150h+var_110], r12
0x180005ccc  mov     r8d, 3
0x180005cd2  lea     rdx, aId_0; "@Id"
0x180005cd9  lea     rcx, [rsp+150h+lpMem]
0x180005cde  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005ce3  mov     [rsp+150h+var_100], r15
0x180005ce8  mov     rax, [r15]
0x180005ceb  mov     rcx, r15
0x180005cee  mov     rax, [rax+8]
0x180005cf2  call    cs:__guard_dispatch_icall_fptr
0x180005cf8  lea     r9, [rsp+150h+lpMem]
0x180005cfd  lea     r8, [rsp+150h+var_100]
0x180005d02  lea     rdx, [rbp+50h+var_48]
0x180005d06  call    ?TryGetStringPropertyFromMap@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AUhstring@6@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@46@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,std::wstring)
0x180005d0b  nop
0x180005d0c  xorps   xmm0, xmm0
0x180005d0f  movups  [rsp+150h+var_D8], xmm0
0x180005d14  mov     [rbp+50h+var_C8], r12
0x180005d18  mov     [rbp+50h+var_C0], r12
0x180005d1c  mov     r8d, 5
0x180005d22  lea     rdx, aType; "@Type"
0x180005d29  lea     rcx, [rsp+150h+var_D8]
0x180005d2e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180005d33  mov     [rsp+150h+var_F8], r15
0x180005d38  mov     rax, [r15]
0x180005d3b  mov     rcx, r15
0x180005d3e  mov     rax, [rax+8]
0x180005d42  call    cs:__guard_dispatch_icall_fptr
0x180005d48  lea     r9, [rsp+150h+var_D8]
0x180005d4d  lea     r8, [rsp+150h+var_F8]
0x180005d52  lea     rdx, [rbp+50h+var_38]
0x180005d56  call    ?TryGetStringPropertyFromMap@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AUhstring@6@U?$IMap@Uhstring@winrt@@UIInspectable@Foundation@Windows@2@@Collections@Foundation@46@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::TryGetStringPropertyFromMap(winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Windows::Foundation::IInspectable>,std::wstring)
0x180005d5b  nop
0x180005d5c  mov     rsi, [rbp+50h+var_48]
0x180005d60  mov     rcx, rsi; this
0x180005d63  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005d68  mov     r13, rax
0x180005d6b  mov     [rbp+50h+var_B0], rax
0x180005d6f  mov     rdi, [rbp+50h+var_38]
0x180005d73  mov     rcx, rdi; this
0x180005d76  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005d7b  mov     r12, rax
0x180005d7e  mov     [rbp+50h+var_A8], rax
0x180005d82  mov     rbx, [rbp+50h+var_40]
0x180005d86  mov     [rbp+50h+var_A0], rbx
0x180005d8a  mov     rcx, [rbp+50h+var_70]; this
0x180005d8e  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005d93  mov     [rsp+150h+lpMem], rax
0x180005d98  lea     rax, [rsp+150h+lpMem+8]
0x180005d9d  mov     [rsp+150h+var_108], rax
0x180005da2  mov     rcx, r13; this
0x180005da5  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005daa  mov     [rsp+150h+lpMem+8], rax
0x180005daf  mov     rcx, r12; this
0x180005db2  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x180005db7  mov     [rsp+150h+var_118], rax
0x180005dbc  mov     [rsp+150h+var_110], rbx
0x180005dc1  bts     r14d, 9
0x180005dc6  mov     [rsp+150h+var_130], r14d
0x180005dcb  mov     rcx, [rsp+150h+var_F0]
0x180005dd0  add     rcx, 68h ; 'h'
  ... truncated ...
```
