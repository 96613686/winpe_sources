# ??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z

- ea: `0x180004c70`
- end: `0x180004e35`
- name: `??$call@AEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@QEAA?A_PAEAV_lambda_cb41fde99ba74c6248b3ce76f09f9615_@@@Z`
- size: `453`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800058e0`
- `0x180008c60`

## callees

- `0x1800040a0`
- `0x180004810`
- `0x180004c70`
- `0x180013ed0`
- `0x180034ef0`
- `0x180039709`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004caa`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x180004caa`

## string_xrefs

- `0x180004cbf`: `Windows.ApplicationModel.PackageExtensions.PackageExtensionCatalog`

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
  v13 = &qword_180059EC8;
  _InterlockedIncrement64(&qword_180059EC8);
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
  _InterlockedDecrement64(&qword_180059EC8);
  if ( v5 )
LABEL_13:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x180004c70  mov     [rsp-18h+arg_0], rbx
0x180004c75  mov     [rsp-18h+arg_18], rsi
0x180004c7a  push    rbp
0x180004c7b  push    rdi
0x180004c7c  push    r14
0x180004c7e  mov     rbp, rsp
0x180004c81  sub     rsp, 70h
0x180004c85  mov     rax, cs:__security_cookie
0x180004c8c  xor     rax, rsp
0x180004c8f  mov     [rbp+var_8], rax
0x180004c93  mov     rsi, r8
0x180004c96  mov     rdi, rdx
0x180004c99  mov     [rbp+var_18], rdx
0x180004c9d  xor     r14d, r14d
0x180004ca0  cmp     word ptr cs:aWindowsApplica+84h, r14w; ""
0x180004ca8  jz      short loc_180004CB1
0x180004caa  call    cs:__imp_abort
0x180004cb1  mov     [rbp+var_38], 1
0x180004cb8  mov     [rbp+var_34], 42h ; 'B'
0x180004cbf  lea     rax, aWindowsApplica; "Windows.ApplicationModel.PackageExtensi"...
0x180004cc6  mov     [rbp+var_28], rax
0x180004cca  lea     rax, [rbp+var_38]
0x180004cce  mov     [rbp+var_40], rax
0x180004cd2  mov     [rbp+var_10], r14
0x180004cd6  lea     r9, [rbp+var_10]
0x180004cda  lea     r8, ??$guid_v@UIPackageExtensionCatalogStatics@PackageExtensions@ApplicationModel@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004ce1  lea     rdx, [rbp+var_40]
0x180004ce5  lea     rcx, [rbp+var_50]
0x180004ce9  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180004cee  mov     ecx, [rbp+var_50]
0x180004cf1  test    ecx, ecx
0x180004cf3  js      loc_180004E21
0x180004cf9  mov     rbx, [rbp+var_10]
0x180004cfd  mov     qword ptr [rbp+var_50], rbx
0x180004d01  test    rbx, rbx
0x180004d04  jz      loc_180004DC0
0x180004d0a  mov     [rbp+var_18], r14
0x180004d0e  mov     rax, [rbx]
0x180004d11  lea     r8, [rbp+var_18]
0x180004d15  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180004d1c  mov     rcx, rbx
0x180004d1f  mov     rax, [rax]
0x180004d22  call    cs:__guard_dispatch_icall_fptr
0x180004d28  mov     rax, [rbp+var_18]
0x180004d2c  mov     [rbp+var_18], rax
0x180004d30  test    rax, rax
0x180004d33  jz      loc_180004DC0
0x180004d39  lea     rcx, [rbp+var_18]
0x180004d3d  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004d42  lea     rax, qword_180059EC8
0x180004d49  mov     [rbp+var_20], rax
0x180004d4d  lock inc cs:qword_180059EC8
0x180004d55  mov     rcx, [rbp+var_10]
0x180004d59  xor     eax, eax
0x180004d5b  lock cmpxchg cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A, rcx; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004d64  jnz     short loc_180004D80
0x180004d66  mov     qword ptr [rbp+var_50], r14
0x180004d6a  lea     rdx, ListEntry; ListEntry
0x180004d71  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180004d78  call    WINRT_IMPL_InterlockedPushEntrySList
0x180004d7d  mov     rbx, r14
0x180004d80  mov     [rbp+var_18], r14
0x180004d84  mov     rcx, cs:??$factory_cache_entry_v@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@impl@winrt@@3U?$factory_cache_entry@UPackageExtensionCatalog@PackageExtensions@ApplicationModel@Windows@winrt@@UIPackageExtensionCatalogStatics@2345@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::PackageExtensions::PackageExtensionCatalog,winrt::Windows::ApplicationModel::PackageExtensions::IPackageExtensionCatalogStatics>
0x180004d8b  mov     rdx, [rsi]
0x180004d8e  mov     rax, [rcx]
0x180004d91  lea     r8, [rbp+var_18]
0x180004d95  mov     rdx, [rdx]
0x180004d98  mov     rax, [rax+30h]
0x180004d9c  call    cs:__guard_dispatch_icall_fptr
0x180004da2  test    eax, eax
0x180004da4  js      loc_180004E2A
0x180004daa  mov     rcx, [rbp+var_18]
0x180004dae  mov     [rdi], rcx
0x180004db1  lock dec cs:qword_180059EC8
0x180004db9  test    rbx, rbx
0x180004dbc  jz      short loc_180004DF2
0x180004dbe  jmp     short loc_180004DE9
0x180004dc0  mov     [rbp+var_18], r14
0x180004dc4  mov     rdx, [rsi]
0x180004dc7  mov     rax, [rbx]
0x180004dca  lea     r8, [rbp+var_18]
0x180004dce  mov     rdx, [rdx]
0x180004dd1  mov     rcx, rbx
0x180004dd4  mov     rax, [rax+30h]
0x180004dd8  call    cs:__guard_dispatch_icall_fptr
0x180004dde  test    eax, eax
0x180004de0  js      short loc_180004E16
0x180004de2  mov     rax, [rbp+var_18]
0x180004de6  mov     [rdi], rax
0x180004de9  lea     rcx, [rbp+var_50]
0x180004ded  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180004df2  mov     rax, rdi
0x180004df5  mov     rcx, [rbp+var_8]
0x180004df9  xor     rcx, rsp; StackCookie
0x180004dfc  call    __security_check_cookie
0x180004e01  lea     r11, [rsp+70h+var_s0]
0x180004e06  mov     rbx, [r11+20h]
0x180004e0a  mov     rsi, [r11+38h]
0x180004e0e  mov     rsp, r11
0x180004e11  pop     r14
0x180004e13  pop     rdi
0x180004e14  pop     rbp
0x180004e15  retn
0x180004e16  lfence
0x180004e19  mov     ecx, eax
0x180004e1b  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180004e21  lfence
0x180004e24  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x180004e2a  lfence
0x180004e2d  mov     ecx, eax
0x180004e2f  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
