# winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageSet(winrt::guid)

- ea: `0x180006110`
- end: `0x1800067a8`
- name: `?GetPackageSet@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@QEAA?AUPackageSet@Deployment@Management@456@Uguid@6@@Z`
- size: `1688`
- prototype: `__int64 **__fastcall(__int64, __int64 **, _OWORD *)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000a9e0`

## callees

- `0x180003db0`
- `0x1800040a0`
- `0x180004810`
- `0x180004a00`
- `0x1800057f0`
- `0x180006110`
- `0x180006940`
- `0x18000cf30`
- `0x18000d9a0`
- `0x180013bd0`
- `0x180013c10`
- `0x180013d70`
- `0x180014230`
- `0x180014bb0`
- `0x180014d10`
- `0x180014e70`
- `0x180014f90`
- `0x1800157c0`
- `0x180030ae5`
- `0x180030aeb`
- `0x180034ef0`
- `0x18003509c`
- `0x180036f4c`
- `0x18003bed0`
- `0x18003bf20`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000661f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006626`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000661f`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180006626`

## string_xrefs

- `0x18000622f`: `C:\temp\temp.msix`

## pseudocode

```c
__int64 **__fastcall winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::GetPackageSet(
        __int64 a1,
        __int64 **a2,
        _OWORD *a3)
{
  int v6; // r14d
  char v7; // di
  struct winrt::impl::hstring_header *v8; // rdx
  _QWORD *v9; // r8
  __int64 *v10; // rbx
  volatile signed __int32 *v11; // rsi
  struct winrt::impl::hstring_header *v12; // rdx
  struct winrt::impl::hstring_header *v13; // rdx
  __int64 v14; // rcx
  const wchar_t *v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdi
  int v19; // r14d
  int v20; // r14d
  int v21; // eax
  int v22; // eax
  int v23; // eax
  bool v24; // al
  __int64 v25; // rdx
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 *v29; // r15
  int v30; // eax
  int v31; // eax
  HANDLE ProcessHeap; // rax
  int v33; // eax
  HANDLE v34; // rax
  int v35; // eax
  HANDLE v36; // rax
  __int64 **v37; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 v40; // rbx
  int v41; // eax
  __int64 *v42; // rdi
  __int64 v43; // rcx
  winrt::hresult *v45; // rax
  char v46; // [rsp+20h] [rbp-A9h]
  LPVOID pExceptionObject; // [rsp+28h] [rbp-A1h] BYREF
  LPVOID lpMem; // [rsp+30h] [rbp-99h]
  __int64 v49; // [rsp+38h] [rbp-91h]
  __int128 Buf2; // [rsp+40h] [rbp-89h] BYREF
  _QWORD v51[2]; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v52[2]; // [rsp+60h] [rbp-69h] BYREF
  _DWORD *v53; // [rsp+70h] [rbp-59h] BYREF
  _DWORD v54[4]; // [rsp+78h] [rbp-51h] BYREF
  const wchar_t *v55; // [rsp+88h] [rbp-41h]
  __int64 *v56; // [rsp+90h] [rbp-39h]
  _QWORD v57[4]; // [rsp+A0h] [rbp-29h] BYREF
  __int64 *v58; // [rsp+C0h] [rbp-9h] BYREF
  __int64 v59; // [rsp+C8h] [rbp-1h] BYREF
  __int64 v60; // [rsp+D0h] [rbp+7h] BYREF
  void *v61[2]; // [rsp+D8h] [rbp+Fh] BYREF

  v57[2] = a2;
  v58 = &qword_180059E98;
  _InterlockedIncrement64(&qword_180059E98);
  if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> )
  {
    _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(
      a1,
      a2,
      &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedDecrement64(&qword_180059E98);
  }
  else
  {
    _InterlockedDecrement64(&qword_180059E98);
    v58 = (__int64 *)_lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSet (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      a1,
      (__int64)a2,
      (void (__fastcall **)(__int64, __int64 *))&v58);
  }
  v6 = 3;
  v7 = 0;
  v46 = 0;
  v52[0] = L"WindowsWorkload.Manager.1_8wekyb3d8bbwe";
  v52[1] = 39;
  Buf2 = 0;
  if ( !memcmp(a3, &Buf2, 0x10u) || (Buf2 = *(_OWORD *)(a1 + 76), !memcmp(a3, &Buf2, 0x10u)) )
  {
    v40 = *(_QWORD *)(a1 + 96);
    v59 = v40;
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
    v58 = 0;
    v41 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v40 + 64LL))(v40, &v58);
    if ( v41 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v41);
    }
    v42 = v58;
    v51[0] = v58;
    if ( a2 == v51 )
    {
      if ( v58 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v51);
    }
    else
    {
      if ( *a2 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a2);
      *a2 = v42;
    }
    if ( v40 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v59);
  }
  else
  {
    *(_OWORD *)v61 = 0;
    winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::PackageFamiliesWithVectorSpaces(a1, v61);
    v9 = v61[0];
    v10 = *(__int64 **)v61[0];
    if ( !*(_BYTE *)(*(_QWORD *)v61[0] + 25LL) )
    {
      do
      {
        v11 = (volatile signed __int32 *)winrt::impl::duplicate_hstring((winrt::impl *)v10[4], v8);
        v57[3] = v11;
        pExceptionObject = winrt::impl::duplicate_hstring((winrt::impl *)v10[5], v12);
        lpMem = winrt::impl::duplicate_hstring((winrt::impl *)v10[6], v13);
        v49 = v10[7];
        if ( pExceptionObject )
        {
          v14 = *((unsigned int *)pExceptionObject + 1);
          v15 = (const wchar_t *)*((_QWORD *)pExceptionObject + 2);
        }
        else
        {
          v14 = 0;
          v15 = &Src;
        }
        v57[0] = v15;
        v57[1] = v14;
        winrt::guid::parse<std::wstring_view>(&Buf2, v57);
        if ( Buf2 == *a3 )
        {
          v46 = 1;
          v54[0] = 1;
          v54[1] = 17;
          v55 = L"C:\\temp\\temp.msix";
          v53 = v54;
          v58 = (__int64 *)&v53;
          v56 = &qword_180059E78;
          _InterlockedIncrement64(&qword_180059E78);
          if ( winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> )
          {
            v59 = 0;
            v16 = (*(__int64 (__fastcall **)(__int64, _DWORD *, __int64 *))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
                                                                          + 48LL))(
                    winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>,
                    v53,
                    &v59);
            if ( v16 < 0 )
            {
              _mm_lfence();
              winrt::throw_hresult((unsigned int)v16);
            }
            v18 = v59;
            v19 = v6 | 0x70;
            _InterlockedDecrement64(&qword_180059E78);
          }
          else
          {
            _InterlockedDecrement64(&qword_180059E78);
            winrt::impl::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::call<_lambda_0a61d549bec6c444b35123f4c9509ca7_ &>(
              0,
              &v59,
              &v58);
            v19 = v6 | 0x10;
            v18 = v59;
          }
          v56 = &qword_180059E58;
          _InterlockedIncrement64(&qword_180059E58);
          v20 = v19 | 0x80;
          if ( winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> )
          {
            _lambda_7594da771ace6cdf2aaf7146f13b50fc_::operator()(
              v17,
              &v60,
              &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>);
            _InterlockedDecrement64(&qword_180059E58);
          }
          else
          {
            _InterlockedDecrement64(&qword_180059E58);
            v58 = (__int64 *)_lambda_7594da771ace6cdf2aaf7146f13b50fc_::_lambda_invoker_cdecl_;
            winrt::impl::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
              v17,
              (__int64)&v60,
              (void (__fastcall **)(__int64, __int64 *))&v58);
          }
          v21 = (*(__int64 (__fastcall **)(__int64, volatile signed __int32 *))(*(_QWORD *)v60 + 72LL))(v60, v11);
          if ( v21 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v21);
          }
          v22 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 120LL))(v60, v18);
          if ( v22 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v22);
          }
          v23 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 88LL))(v60, v49);
          if ( v23 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v23);
          }
          v24 = IsRunningOnArm64();
          v25 = 4;
          if ( v24 )
            v25 = 16;
          v26 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v60 + 104LL))(v60, v25);
          if ( v26 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v26);
          }
          v27 = (*(__int64 (__fastcall **)(__int64 *, volatile signed __int32 *))(**a2 + 56))(*a2, v11);
          if ( v27 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v27);
          }
          v58 = 0;
          v28 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(**a2 + 80))(*a2, &v58);
          if ( v28 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v28);
          }
          v29 = v58;
          v6 = v20 | 8;
          v30 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v58 + 104))(v58, v60);
          if ( v30 < 0 )
          {
            _mm_lfence();
            winrt::throw_hresult((unsigned int)v30);
          }
          if ( v29 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v58);
          if ( v60 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v60);
          if ( v18 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v59);
        }
        if ( lpMem )
        {
          v31 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
          if ( v31 )
          {
            if ( v31 < 0 )
              goto LABEL_58;
          }
          else
          {
            ProcessHeap = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem);
          }
          lpMem = 0;
        }
        if ( pExceptionObject )
        {
          v33 = _InterlockedDecrement((volatile signed __int32 *)pExceptionObject + 6);
          if ( v33 )
          {
            if ( v33 < 0 )
LABEL_58:
              abort();
          }
          else
          {
            v34 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v34, 0, pExceptionObject);
          }
          pExceptionObject = 0;
        }
        if ( v11 )
        {
          v35 = _InterlockedDecrement(v11 + 6);
          if ( v35 )
          {
            if ( v35 < 0 )
              abort();
          }
          else
          {
            v36 = WINRT_IMPL_GetProcessHeap();
            WINRT_IMPL_HeapFree(v36, 0, (LPVOID)v11);
          }
        }
        v37 = (__int64 **)v10[2];
        if ( *((_BYTE *)v37 + 25) )
        {
          for ( i = (__int64 *)v10[1]; !*((_BYTE *)i + 25); i = (__int64 *)i[1] )
          {
            if ( v10 != (__int64 *)i[2] )
              break;
            v10 = i;
          }
          v10 = i;
        }
        else
        {
          v10 = (__int64 *)v10[2];
          for ( j = *v37; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v10 = j;
        }
      }
      while ( !*((_BYTE *)v10 + 25) );
      v9 = v61[0];
      v7 = v46;
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::implementation::VectorSpace>,void *>>>(
      v61,
      v61,
      v9[1]);
    operator delete(v61[0]);
    if ( !v7 )
    {
      winrt::param::hstring::hstring((winrt::param::hstring *)&v53, L"The vector space does not exist");
      v45 = winrt::hresult::hresult((winrt::hresult *)&v60, -2147023728);
      winrt::hresult_error::hresult_error(&pExceptionObject, *(unsigned int *)v45, &v53);
      throw (winrt::hresult_error *)&pExceptionObject;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57053679>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57053679>::GetImpl'::`2'::impl) )
    winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::RemovePackageFromPackageSetByFamilyName(v43, a2, v52);
  return a2;
}

```

## disassembly

```asm
0x180006110  mov     [rsp-8+arg_10], rbx
0x180006115  push    rbp
0x180006116  push    rsi
0x180006117  push    rdi
0x180006118  push    r12
0x18000611a  push    r13
0x18000611c  push    r14
0x18000611e  push    r15
0x180006120  lea     rbp, [rsp-27h]
0x180006125  sub     rsp, 0F0h
0x18000612c  mov     rax, cs:__security_cookie
0x180006133  xor     rax, rsp
0x180006136  mov     [rbp+57h+var_38], rax
0x18000613a  mov     r13, r8
0x18000613d  mov     r12, rdx
0x180006140  mov     rbx, rcx
0x180006143  mov     [rbp+57h+var_70], rdx
0x180006147  xor     r15d, r15d
0x18000614a  mov     [rsp+120h+var_FC], r15d
0x18000614f  lea     rax, qword_180059E98
0x180006156  mov     [rbp+57h+var_60], rax
0x18000615a  lock inc cs:qword_180059E98
0x180006162  cmp     cs:??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, r15; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180006169  jz      short loc_180006182
0x18000616b  lea     r8, ??$factory_cache_entry_v@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSet,winrt::Windows::Foundation::IActivationFactory>
0x180006172  call    ??R_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180006177  nop
0x180006178  lock dec cs:qword_180059E98
0x180006180  jmp     short loc_18000619E
0x180006182  lock dec cs:qword_180059E98
0x18000618a  lea     rax, ?_lambda_invoker_cdecl_@_lambda_bb8c2e763425c0def7fe7cd972841e7c_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_bb8c2e763425c0def7fe7cd972841e7c_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180006191  mov     [rbp+57h+var_60], rax
0x180006195  lea     r8, [rbp+57h+var_60]
0x180006199  call    ??$call@P6A?AUPackageSet@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSet@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSet@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x18000619e  mov     r14d, 3
0x1800061a4  mov     [rsp+120h+var_FC], r14d
0x1800061a9  xor     dil, dil
0x1800061ac  mov     [rsp+120h+var_100], dil
0x1800061b1  lea     rax, aWindowsworkloa; "WindowsWorkload.Manager.1_8wekyb3d8bbwe"
0x1800061b8  mov     qword ptr [rbp+57h+var_C0], rax
0x1800061bc  mov     qword ptr [rbp+57h+var_C0+8], 27h ; '''
0x1800061c4  xorps   xmm0, xmm0
0x1800061c7  movups  [rsp+120h+Buf2], xmm0
0x1800061cc  mov     esi, 10h
0x1800061d1  mov     r8d, esi; Size
0x1800061d4  lea     rdx, [rsp+120h+Buf2]; Buf2
0x1800061d9  mov     rcx, r13; Buf1
0x1800061dc  call    memcmp
0x1800061e1  test    eax, eax
0x1800061e3  jz      loc_18000662D
0x1800061e9  movups  xmm0, xmmword ptr [rbx+4Ch]
0x1800061ed  movups  [rsp+120h+Buf2], xmm0
0x1800061f2  mov     r8d, esi; Size
0x1800061f5  lea     rdx, [rsp+120h+Buf2]; Buf2
0x1800061fa  mov     rcx, r13; Buf1
0x1800061fd  call    memcmp
0x180006202  test    eax, eax
0x180006204  jz      loc_18000662D
0x18000620a  xorps   xmm0, xmm0
0x18000620d  movups  xmmword ptr [rbp+57h+var_48], xmm0
0x180006211  lea     rdx, [rbp+57h+var_48]
0x180006215  mov     rcx, rbx
0x180006218  call    ?PackageFamiliesWithVectorSpaces@ApiInfo@implementation@Workloads@Windows@Microsoft@winrt@@AEAA?AV?$map@Uhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UVectorSpace@implementation@Workloads@Windows@Microsoft@2@@std@@@9@@std@@XZ; winrt::Microsoft::Windows::Workloads::implementation::ApiInfo::PackageFamiliesWithVectorSpaces(void)
0x18000621d  nop
0x18000621e  mov     r8, [rbp+57h+var_48]
0x180006222  mov     rbx, [r8]
0x180006225  cmp     [rbx+19h], dil
0x180006229  jnz     loc_1800065F2
0x18000622f  lea     rdi, aCTempTempMsix; "C:\\temp\\temp.msix"
0x180006236  mov     rcx, [rbx+20h]; this
0x18000623a  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000623f  mov     rsi, rax
0x180006242  mov     [rbp+57h+var_68], rax
0x180006246  mov     rcx, [rbx+28h]; this
0x18000624a  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000624f  mov     [rsp+120h+pExceptionObject], rax
0x180006254  mov     rcx, [rbx+30h]; this
0x180006258  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000625d  mov     [rsp+120h+lpMem], rax
0x180006262  mov     rax, [rbx+38h]
0x180006266  mov     [rsp+120h+var_E8], rax
0x18000626b  mov     rax, [rsp+120h+pExceptionObject]
0x180006270  test    rax, rax
0x180006273  jz      short loc_18000627E
0x180006275  mov     ecx, [rax+4]
0x180006278  mov     rdx, [rax+10h]
0x18000627c  jmp     short loc_180006288
0x18000627e  mov     rcx, r15
0x180006281  lea     rdx, Src
0x180006288  mov     [rbp+57h+var_80], rdx
0x18000628c  mov     [rbp+57h+var_78], rcx
0x180006290  lea     rdx, [rbp+57h+var_80]
0x180006294  lea     rcx, [rsp+120h+Buf2]
0x180006299  call    ??$parse@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@guid@winrt@@CA?AU01@V?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::guid::parse<std::wstring_view>(std::wstring_view)
0x18000629e  mov     rax, qword ptr [rsp+120h+Buf2]
0x1800062a3  cmp     rax, [r13+0]
0x1800062a7  jnz     loc_1800064E4
0x1800062ad  mov     rax, qword ptr [rsp+120h+Buf2+8]
0x1800062b2  cmp     rax, [r13+8]
0x1800062b6  jnz     loc_1800064E4
0x1800062bc  mov     [rsp+120h+var_100], 1
0x1800062c1  mov     [rbp+57h+var_A8], 1
0x1800062c8  mov     [rbp+57h+var_A4], 11h
0x1800062cf  mov     [rbp+57h+var_98], rdi
0x1800062d3  lea     rax, [rbp+57h+var_A8]
0x1800062d7  mov     [rbp+57h+var_B0], rax
0x1800062db  lea     rax, [rbp+57h+var_B0]
0x1800062df  mov     [rbp+57h+var_60], rax
0x1800062e3  lea     rax, qword_180059E78
0x1800062ea  mov     [rbp+57h+var_90], rax
0x1800062ee  lock inc cs:qword_180059E78
0x1800062f6  mov     rcx, cs:??$factory_cache_entry_v@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@3U?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>::winrt::factory_cache_entry<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::Uri,winrt::Windows::Foundation::IUriRuntimeClassFactory>
0x1800062fd  test    rcx, rcx
0x180006300  jz      short loc_18000633E
0x180006302  mov     [rbp+57h+var_58], r15
0x180006306  mov     rax, [rcx]
0x180006309  lea     r8, [rbp+57h+var_58]
0x18000630d  mov     rdx, [rbp+57h+var_B0]
0x180006311  mov     rax, [rax+30h]
0x180006315  call    cs:__guard_dispatch_icall_fptr
0x18000631b  test    eax, eax
0x18000631d  js      loc_180006750
0x180006323  mov     rdi, [rbp+57h+var_58]
0x180006327  mov     [rbp+57h+var_58], rdi
0x18000632b  or      r14d, 70h
0x18000632f  mov     [rsp+120h+var_FC], r14d
0x180006334  lock dec cs:qword_180059E78
0x18000633c  jmp     short loc_180006360
0x18000633e  lock dec cs:qword_180059E78
0x180006346  lea     r8, [rbp+57h+var_60]
0x18000634a  lea     rdx, [rbp+57h+var_58]
0x18000634e  call    ??$call@AEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@?$factory_cache_entry@UUri@Foundation@Windows@winrt@@UIUriRuntimeClassFactory@234@@impl@winrt@@QEAA?A_PAEAV_lambda_0a61d549bec6c444b35123f4c9509ca7_@@@Z
0x180006353  or      r14d, 10h
0x180006357  mov     [rsp+120h+var_FC], r14d
0x18000635c  mov     rdi, [rbp+57h+var_58]
0x180006360  lea     rax, qword_180059E58
0x180006367  mov     [rbp+57h+var_90], rax
0x18000636b  lock inc cs:qword_180059E58
0x180006373  bts     r14d, 7
0x180006378  cmp     cs:??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A, 0; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x180006380  jz      short loc_1800063A1
0x180006382  lea     r8, ??$factory_cache_entry_v@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@3U?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@12@A; factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Windows::Management::Deployment::PackageSetItem,winrt::Windows::Foundation::IActivationFactory>
0x180006389  lea     rdx, [rbp+57h+var_50]
0x18000638d  call    ??R_lambda_7594da771ace6cdf2aaf7146f13b50fc_@@QEBA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_7594da771ace6cdf2aaf7146f13b50fc_::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180006392  mov     [rsp+120h+var_FC], r14d
0x180006397  lock dec cs:qword_180059E58
0x18000639f  jmp     short loc_1800063C6
0x1800063a1  lock dec cs:qword_180059E58
0x1800063a9  lea     rax, ?_lambda_invoker_cdecl_@_lambda_7594da771ace6cdf2aaf7146f13b50fc_@@CA@AEBUIActivationFactory@Foundation@Windows@winrt@@@Z; _lambda_7594da771ace6cdf2aaf7146f13b50fc_::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x1800063b0  mov     [rbp+57h+var_60], rax
0x1800063b4  lea     r8, [rbp+57h+var_60]
0x1800063b8  lea     rdx, [rbp+57h+var_50]
0x1800063bc  call    ??$call@P6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@AEBUIActivationFactory@Foundation@46@@Z@?$factory_cache_entry@UPackageSetItem@Deployment@Management@Windows@Microsoft@winrt@@UIActivationFactory@Foundation@46@@impl@winrt@@QEAA?A_P$$QEAP6A?AUPackageSetItem@Deployment@Management@Windows@Microsoft@2@AEBUIActivationFactory@Foundation@62@@Z@Z
0x1800063c1  mov     [rsp+120h+var_FC], r14d
0x1800063c6  mov     rcx, [rbp+57h+var_50]
0x1800063ca  mov     rax, [rcx]
0x1800063cd  mov     rdx, rsi
0x1800063d0  mov     rax, [rax+48h]
0x1800063d4  call    cs:__guard_dispatch_icall_fptr
0x1800063da  test    eax, eax
0x1800063dc  js      loc_18000679D
0x1800063e2  mov     rcx, [rbp+57h+var_50]
0x1800063e6  mov     rax, [rcx]
0x1800063e9  mov     rdx, rdi
0x1800063ec  mov     rax, [rax+78h]
0x1800063f0  call    cs:__guard_dispatch_icall_fptr
0x1800063f6  test    eax, eax
0x1800063f8  js      loc_180006792
0x1800063fe  mov     rcx, [rbp+57h+var_50]
0x180006402  mov     rax, [rcx]
0x180006405  mov     rdx, [rsp+120h+var_E8]
0x18000640a  mov     rax, [rax+58h]
0x18000640e  call    cs:__guard_dispatch_icall_fptr
0x180006414  test    eax, eax
0x180006416  js      loc_180006787
0x18000641c  call    ?IsRunningOnArm64@@YA_NXZ; IsRunningOnArm64(void)
0x180006421  mov     edx, 4
0x180006426  test    al, al
0x180006428  mov     eax, 10h
0x18000642d  cmovnz  edx, eax
0x180006430  mov     rcx, [rbp+57h+var_50]
0x180006434  mov     rax, [rcx]
0x180006437  mov     rax, [rax+68h]
0x18000643b  call    cs:__guard_dispatch_icall_fptr
0x180006441  test    eax, eax
0x180006443  js      loc_18000677C
0x180006449  mov     rcx, [r12]
0x18000644d  mov     rax, [rcx]
0x180006450  mov     rdx, rsi
0x180006453  mov     rax, [rax+38h]
0x180006457  call    cs:__guard_dispatch_icall_fptr
0x18000645d  test    eax, eax
0x18000645f  js      loc_180006771
0x180006465  mov     [rbp+57h+var_60], r15
0x180006469  mov     rcx, [r12]
0x18000646d  mov     rax, [rcx]
0x180006470  lea     rdx, [rbp+57h+var_60]
0x180006474  mov     rax, [rax+50h]
0x180006478  call    cs:__guard_dispatch_icall_fptr
0x18000647e  test    eax, eax
0x180006480  js      loc_180006766
0x180006486  mov     r15, [rbp+57h+var_60]
0x18000648a  mov     [rbp+57h+var_60], r15
0x18000648e  or      r14d, 8
0x180006492  mov     [rsp+120h+var_FC], r14d
0x180006497  mov     rax, [r15]
0x18000649a  mov     rdx, [rbp+57h+var_50]
0x18000649e  mov     rcx, r15
0x1800064a1  mov     rax, [rax+68h]
0x1800064a5  call    cs:__guard_dispatch_icall_fptr
0x1800064ab  test    eax, eax
0x1800064ad  js      loc_18000675B
0x1800064b3  test    r15, r15
0x1800064b6  jz      short loc_1800064C2
0x1800064b8  lea     rcx, [rbp+57h+var_60]
0x1800064bc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800064c1  nop
0x1800064c2  cmp     [rbp+57h+var_50], 0
0x1800064c7  jz      short loc_1800064D3
0x1800064c9  lea     rcx, [rbp+57h+var_50]
0x1800064cd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800064d2  nop
0x1800064d3  test    rdi, rdi
0x1800064d6  jz      short loc_1800064E1
0x1800064d8  lea     rcx, [rbp+57h+var_58]
0x1800064dc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800064e1  xor     r15d, r15d
0x1800064e4  mov     rdi, [rsp+120h+lpMem]
0x1800064e9  test    rdi, rdi
0x1800064ec  jz      short loc_18000651E
0x1800064ee  mov     eax, 0FFFFFFFFh
0x1800064f3  lock xadd [rdi+18h], eax
0x1800064f8  sub     eax, 1
0x1800064fb  jnz     short loc_180006511
0x1800064fd  call    WINRT_IMPL_GetProcessHeap
0x180006502  mov     rcx, rax; hHeap
0x180006505  mov     r8, rdi; lpMem
0x180006508  xor     edx, edx; dwFlags
0x18000650a  call    WINRT_IMPL_HeapFree
0x18000650f  jmp     short loc_180006519
0x180006511  test    eax, eax
0x180006513  js      loc_18000661F
0x180006519  mov     [rsp+120h+lpMem], r15
0x18000651e  mov     rdi, [rsp+120h+pExceptionObject]
0x180006523  test    rdi, rdi
0x180006526  jz      short loc_180006558
0x180006528  mov     eax, 0FFFFFFFFh
0x18000652d  lock xadd [rdi+18h], eax
0x180006532  sub     eax, 1
0x180006535  jnz     short loc_18000654B
0x180006537  call    WINRT_IMPL_GetProcessHeap
0x18000653c  mov     rcx, rax; hHeap
0x18000653f  mov     r8, rdi; lpMem
0x180006542  xor     edx, edx; dwFlags
0x180006544  call    WINRT_IMPL_HeapFree
0x180006549  jmp     short loc_180006553
0x18000654b  test    eax, eax
0x18000654d  js      loc_18000661F
0x180006553  mov     [rsp+120h+pExceptionObject], r15
0x180006558  test    rsi, rsi
0x18000655b  jz      short loc_180006588
0x18000655d  mov     eax, 0FFFFFFFFh
0x180006562  lock xadd [rsi+18h], eax
0x180006567  sub     eax, 1
0x18000656a  jnz     short loc_180006580
0x18000656c  call    WINRT_IMPL_GetProcessHeap
0x180006571  mov     rcx, rax; hHeap
0x180006574  mov     r8, rsi; lpMem
0x180006577  xor     edx, edx; dwFlags
0x180006579  call    WINRT_IMPL_HeapFree
0x18000657e  jmp     short loc_180006588
0x180006580  test    eax, eax
0x180006582  js      loc_180006626
0x180006588  mov     rcx, [rbx+10h]
0x18000658c  cmp     byte ptr [rcx+19h], 0
0x180006590  jz      short loc_1800065B8
0x180006592  mov     rax, [rbx+8]
0x180006596  cmp     byte ptr [rax+19h], 0
0x18000659a  jnz     short loc_1800065B3
0x18000659c  nop     dword ptr [rax+00h]
0x1800065a0  cmp     rbx, [rax+10h]
0x1800065a4  jnz     short loc_1800065B3
0x1800065a6  mov     rbx, rax
0x1800065a9  mov     rax, [rax+8]
0x1800065ad  cmp     byte ptr [rax+19h], 0
0x1800065b1  jz      short loc_1800065A0
0x1800065b3  mov     rbx, rax
0x1800065b6  jmp     short loc_1800065DF
0x1800065b8  mov     rbx, rcx
0x1800065bb  mov     rcx, [rcx]
0x1800065be  cmp     byte ptr [rcx+19h], 0
0x1800065c2  jnz     short loc_1800065DF
0x1800065c4  nop     dword ptr [rax+00h]
0x1800065c8  nop     dword ptr [rax+rax+00000000h]
0x1800065d0  mov     rbx, rcx
0x1800065d3  mov     rax, [rcx]
0x1800065d6  mov     rcx, rax
0x1800065d9  cmp     byte ptr [rax+19h], 0
0x1800065dd  jz      short loc_1800065D0
0x1800065df  cmp     byte ptr [rbx+19h], 0
  ... truncated ...
```
