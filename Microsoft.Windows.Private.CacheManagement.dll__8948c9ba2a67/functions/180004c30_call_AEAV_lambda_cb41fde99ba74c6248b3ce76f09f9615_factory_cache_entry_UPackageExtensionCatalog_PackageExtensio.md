# ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z

- ea: `0x180004c30`
- end: `0x180004df5`
- name: `??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z`
- size: `453`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800060e0`
- `0x180006750`

## callees

- `0x180003840`
- `0x180003ee0`
- `0x180004c30`
- `0x18000ec30`
- `0x1800181b0`
- `0x18001c567`
- `0x18001cdf0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004c6a`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004c6a`

## string_xrefs

- `0x180004c7f`: `Windows.ApplicationModel.PackageExtensions.PackageExtensionCatalog`

## pseudocode

```c
_QWORD *__fastcall winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::call<_lambda_cb41fde99ba74c6248b3ce76f09f9615_ &>(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  int v6; // eax
  int v7; // eax
  unsigned int v9[4]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v10; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v11[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+48h] [rbp-28h]
  __int64 *v13; // [rsp+50h] [rbp-20h]
  _QWORD *v14; // [rsp+58h] [rbp-18h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64 *, _QWORD **); // [rsp+60h] [rbp-10h] BYREF

  v14 = a2;
  if ( aWindowsApplica[66] )
    abort();
  v11[0] = 1;
  v11[1] = 66;
  v12 = L"Windows.ApplicationModel.PackageExtensions.PackageExtensionCatalog";
  v10 = v11;
  v15 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    v9,
    &v10,
    winrt::impl::guid_v<winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
    &v15);
  if ( (v9[0] & 0x80000000) != 0 )
  {
    _mm_lfence();
    winrt::throw_hresult(v9[0]);
  }
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  *(_QWORD *)v9 = v15;
  if ( !v15 || (v14 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14), !v14) )
  {
    v14 = 0;
    v7 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD **))(*v5)[6])(v5, **a3, &v14);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7);
    }
    *a2 = v14;
    goto LABEL_13;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_18002E748;
  _InterlockedIncrement64(&qword_18002E748);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
          (signed __int64)v15,
          0) )
  {
    *(_QWORD *)v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
    v5 = 0;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>,
         **a3,
         &v14);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6);
  }
  *a2 = v14;
  _InterlockedDecrement64(&qword_18002E748);
  if ( v5 )
LABEL_13:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x180004c30  mov     [rsp-18h+arg_0], rbx
0x180004c35  mov     [rsp-18h+arg_18], rsi
0x180004c3a  push    rbp
0x180004c3b  push    rdi
0x180004c3c  push    r14
0x180004c3e  mov     rbp, rsp
0x180004c41  sub     rsp, 70h
0x180004c45  mov     rax, cs:__security_cookie
0x180004c4c  xor     rax, rsp
0x180004c4f  mov     [rbp+var_8], rax
0x180004c53  mov     rsi, r8
0x180004c56  mov     rdi, rdx
0x180004c59  mov     [rbp+var_18], rdx
0x180004c5d  xor     r14d, r14d
0x180004c60  cmp     word ptr cs:aWindowsApplica+84h, r14w; ""
0x180004c68  jz      short loc_180004C71
0x180004c6a  call    cs:__imp_abort
0x180004c71  mov     [rbp+var_38], 1
0x180004c78  mov     [rbp+var_34], 42h ; 'B'
0x180004c7f  lea     rax, aWindowsApplica; "Windows.ApplicationModel.PackageExtensi"...
0x180004c86  mov     [rbp+var_28], rax
0x180004c8a  lea     rax, [rbp+var_38]
0x180004c8e  mov     [rbp+var_40], rax
0x180004c92  mov     [rbp+var_10], r14
0x180004c96  lea     r9, [rbp+var_10]
0x180004c9a  lea     r8, ??$guid_v@UIPackageExtensionCatalogStatics@PackageExtensions@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004ca1  lea     rdx, [rbp+var_40]
0x180004ca5  lea     rcx, [rbp+var_50]
0x180004ca9  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180004cae  mov     ecx, [rbp+var_50]
0x180004cb1  test    ecx, ecx
0x180004cb3  js      loc_180004DE1
0x180004cb9  mov     rbx, [rbp+var_10]
0x180004cbd  mov     qword ptr [rbp+var_50], rbx
0x180004cc1  test    rbx, rbx
0x180004cc4  jz      loc_180004D80
0x180004cca  mov     [rbp+var_18], r14
0x180004cce  mov     rax, [rbx]
0x180004cd1  lea     r8, [rbp+var_18]
0x180004cd5  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180004cdc  mov     rcx, rbx
0x180004cdf  mov     rax, [rax]
0x180004ce2  call    cs:__guard_dispatch_icall_fptr
0x180004ce8  mov     rax, [rbp+var_18]
0x180004cec  mov     [rbp+var_18], rax
0x180004cf0  test    rax, rax
0x180004cf3  jz      loc_180004D80
0x180004cf9  lea     rcx, [rbp+var_18]
0x180004cfd  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004d02  lea     rax, qword_18002E748
0x180004d09  mov     [rbp+var_20], rax
0x180004d0d  lock inc cs:qword_18002E748
0x180004d15  mov     rcx, [rbp+var_10]
0x180004d19  xor     eax, eax
0x180004d1b  lock cmpxchg cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004d24  jnz     short loc_180004D40
0x180004d26  mov     qword ptr [rbp+var_50], r14
0x180004d2a  lea     rdx, ListEntry; ListEntry
0x180004d31  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180004d38  call    WINRT_IMPL_InterlockedPushEntrySList
0x180004d3d  mov     rbx, r14
0x180004d40  mov     [rbp+var_18], r14
0x180004d44  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004d4b  mov     rdx, [rsi]
0x180004d4e  mov     rax, [rcx]
0x180004d51  lea     r8, [rbp+var_18]
0x180004d55  mov     rdx, [rdx]
0x180004d58  mov     rax, [rax+30h]
0x180004d5c  call    cs:__guard_dispatch_icall_fptr
0x180004d62  test    eax, eax
0x180004d64  js      loc_180004DEA
0x180004d6a  mov     rcx, [rbp+var_18]
0x180004d6e  mov     [rdi], rcx
0x180004d71  lock dec cs:qword_18002E748
0x180004d79  test    rbx, rbx
0x180004d7c  jz      short loc_180004DB2
0x180004d7e  jmp     short loc_180004DA9
0x180004d80  mov     [rbp+var_18], r14
0x180004d84  mov     rdx, [rsi]
0x180004d87  mov     rax, [rbx]
0x180004d8a  lea     r8, [rbp+var_18]
0x180004d8e  mov     rdx, [rdx]
0x180004d91  mov     rcx, rbx
0x180004d94  mov     rax, [rax+30h]
0x180004d98  call    cs:__guard_dispatch_icall_fptr
0x180004d9e  test    eax, eax
0x180004da0  js      short loc_180004DD6
0x180004da2  mov     rax, [rbp+var_18]
0x180004da6  mov     [rdi], rax
0x180004da9  lea     rcx, [rbp+var_50]
0x180004dad  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004db2  mov     rax, rdi
0x180004db5  mov     rcx, [rbp+var_8]
0x180004db9  xor     rcx, rsp; StackCookie
0x180004dbc  call    __security_check_cookie
0x180004dc1  lea     r11, [rsp+70h+var_s0]
0x180004dc6  mov     rbx, [r11+20h]
0x180004dca  mov     rsi, [r11+38h]
0x180004dce  mov     rsp, r11
0x180004dd1  pop     r14
0x180004dd3  pop     rdi
0x180004dd4  pop     rbp
0x180004dd5  retn
0x180004dd6  lfence
0x180004dd9  mov     ecx, eax
0x180004ddb  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180004de1  lfence
0x180004de4  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180004dea  lfence
0x180004ded  mov     ecx, eax
0x180004def  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
