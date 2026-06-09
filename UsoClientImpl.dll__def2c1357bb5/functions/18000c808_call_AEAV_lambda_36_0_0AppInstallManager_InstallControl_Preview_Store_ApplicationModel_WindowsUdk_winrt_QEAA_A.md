# ??$call@AEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@QEAA@AEBU23456Windows@8@AEBUhstring@param@8@@Z@@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@2@QEAA@AEBU45678Windows@2@AEBUhstring@param@2@@Z@@Z

- ea: `0x18000c808`
- end: `0x18000c9d8`
- name: `??$call@AEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@QEAA@AEBU23456Windows@8@AEBUhstring@param@8@@Z@@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@2@QEAA@AEBU45678Windows@2@AEBUhstring@param@2@@Z@@Z`
- size: `464`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800120a0`

## callees

- `0x18000c808`
- `0x18002d1a4`
- `0x18002d6a4`
- `0x180035a50`
- `0x1800563c8`
- `0x180056500`
- `0x18005c27a`
- `0x18005c5e0`

## string_xrefs

- `0x18000c857`: `WindowsUdk.ApplicationModel.Store.Preview.InstallControl.AppInstallManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_QWORD *__fastcall ___call_AEAV_lambda_36____0___0AppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_winrt__QEAA_AEBU23456Windows_8_AEBUhstring_param_8__Z____factory_cache_entry_UAppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_winrt__UIAppInstallManagerFactory2_234567__impl_winrt__QEAA_A_PAEAV_lambda_36____0___0AppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_2_QEAA_AEBU45678Windows_2_AEBUhstring_param_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rdi
  int v6; // eax
  int v7; // eax
  unsigned int v9[4]; // [rsp+30h] [rbp-50h] BYREF
  _DWORD *v10; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v11[4]; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v12; // [rsp+58h] [rbp-28h]
  __int64 *v13; // [rsp+60h] [rbp-20h]
  _QWORD *v14; // [rsp+68h] [rbp-18h] BYREF
  void (__fastcall ***v15)(_QWORD, __int64 *, _QWORD **); // [rsp+70h] [rbp-10h] BYREF

  v14 = a2;
  if ( aWindowsudkAppl[74] )
    abort();
  v11[0] = 1;
  v11[1] = 74;
  v12 = L"WindowsUdk.ApplicationModel.Store.Preview.InstallControl.AppInstallManager";
  v10 = v11;
  v15 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    v9,
    &v10,
    (__int64)winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>,
    (__int64)&v15);
  if ( (v9[0] & 0x80000000) != 0 )
    winrt::throw_hresult(v9[0]);
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v15;
  *(_QWORD *)v9 = v15;
  if ( !v15 || (v14 = 0, (**v15)(v15, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v14), !v14) )
  {
    v14 = 0;
    v7 = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD, _QWORD, _QWORD **))(*v5)[6])(
           v5,
           **a3,
           *a3[1],
           &v14);
    if ( v7 < 0 )
      winrt::throw_hresult((unsigned int)v7);
    *a2 = v14;
    goto LABEL_12;
  }
  winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v14);
  v13 = &qword_18009F7A8;
  _InterlockedIncrement64(&qword_18009F7A8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>,
          (signed __int64)v15,
          0) )
  {
    *(_QWORD *)v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_18009F7B0);
    v5 = 0;
  }
  v14 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
                                                                     + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>,
         **a3,
         *a3[1],
         &v14);
  if ( v6 < 0 )
    winrt::throw_hresult((unsigned int)v6);
  *a2 = v14;
  _InterlockedDecrement64(&qword_18009F7A8);
  if ( v5 )
LABEL_12:
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v9);
  return a2;
}

```

## disassembly

```asm
0x18000c808  mov     [rsp-18h+arg_0], rbx
0x18000c80d  mov     [rsp-18h+arg_18], rsi
0x18000c812  push    rbp
0x18000c813  push    rdi
0x18000c814  push    r14
0x18000c816  mov     rbp, rsp
0x18000c819  sub     rsp, 80h
0x18000c820  mov     rax, cs:__security_cookie
0x18000c827  xor     rax, rsp
0x18000c82a  mov     [rbp+var_8], rax
0x18000c82e  mov     rsi, r8
0x18000c831  mov     rbx, rdx
0x18000c834  mov     [rbp+var_18], rdx
0x18000c838  xor     r14d, r14d
0x18000c83b  cmp     word ptr cs:aWindowsudkAppl+94h, r14w; ""
0x18000c843  jnz     loc_18000C9C4
0x18000c849  mov     [rbp+var_38], 1
0x18000c850  mov     [rbp+var_34], 4Ah ; 'J'
0x18000c857  lea     rax, aWindowsudkAppl; "WindowsUdk.ApplicationModel.Store.Previ"...
0x18000c85e  mov     [rbp+var_28], rax
0x18000c862  lea     rax, [rbp+var_38]
0x18000c866  mov     [rbp+var_40], rax
0x18000c86a  mov     [rbp+var_10], r14
0x18000c86e  lea     r9, [rbp+var_10]
0x18000c872  lea     r8, ??$guid_v@UIAppInstallManagerFactory2@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
0x18000c879  lea     rdx, [rbp+var_40]
0x18000c87d  lea     rcx, [rbp+var_50]
0x18000c881  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18000c886  mov     ecx, [rbp+var_50]
0x18000c889  test    ecx, ecx
0x18000c88b  js      loc_18000C9CA
0x18000c891  mov     rdi, [rbp+var_10]
0x18000c895  mov     qword ptr [rbp+var_50], rdi
0x18000c899  test    rdi, rdi
0x18000c89c  jz      loc_18000C95D
0x18000c8a2  mov     [rbp+var_18], r14
0x18000c8a6  mov     rax, [rdi]
0x18000c8a9  lea     r8, [rbp+var_18]
0x18000c8ad  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18000c8b4  mov     rcx, rdi
0x18000c8b7  mov     rax, [rax]
0x18000c8ba  call    _guard_dispatch_icall
0x18000c8bf  mov     rax, [rbp+var_18]
0x18000c8c3  mov     [rbp+var_18], rax
0x18000c8c7  test    rax, rax
0x18000c8ca  jz      loc_18000C95D
0x18000c8d0  lea     rcx, [rbp+var_18]
0x18000c8d4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c8d9  lea     rax, qword_18009F7A8
0x18000c8e0  mov     [rbp+var_20], rax
0x18000c8e4  lock inc cs:qword_18009F7A8
0x18000c8ec  mov     rcx, [rbp+var_10]
0x18000c8f0  xor     eax, eax
0x18000c8f2  lock cmpxchg cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@12@A, rcx; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
0x18000c8fb  jnz     short loc_18000C917
0x18000c8fd  mov     qword ptr [rbp+var_50], r14
0x18000c901  lea     rdx, stru_18009F7B0; ListEntry
0x18000c908  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18000c90f  call    WINRT_IMPL_InterlockedPushEntrySList
0x18000c914  mov     edi, r14d
0x18000c917  mov     [rbp+var_18], r14
0x18000c91b  mov     rcx, cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
0x18000c922  mov     r8, [rsi+8]
0x18000c926  mov     rdx, [rsi]
0x18000c929  mov     rax, [rcx]
0x18000c92c  lea     r9, [rbp+var_18]
0x18000c930  mov     r8, [r8]
0x18000c933  mov     rdx, [rdx]
0x18000c936  mov     rax, [rax+30h]
0x18000c93a  call    _guard_dispatch_icall
0x18000c93f  test    eax, eax
0x18000c941  js      loc_18000C9D0
0x18000c947  mov     rcx, [rbp+var_18]
0x18000c94b  mov     [rbx], rcx
0x18000c94e  lock dec cs:qword_18009F7A8
0x18000c956  test    rdi, rdi
0x18000c959  jz      short loc_18000C995
0x18000c95b  jmp     short loc_18000C98C
0x18000c95d  mov     [rbp+var_18], r14
0x18000c961  mov     r8, [rsi+8]
0x18000c965  mov     rdx, [rsi]
0x18000c968  mov     rax, [rdi]
0x18000c96b  lea     r9, [rbp+var_18]
0x18000c96f  mov     r8, [r8]
0x18000c972  mov     rdx, [rdx]
0x18000c975  mov     rcx, rdi
0x18000c978  mov     rax, [rax+30h]
0x18000c97c  call    _guard_dispatch_icall
0x18000c981  test    eax, eax
0x18000c983  js      short loc_18000C9BC
0x18000c985  mov     rax, [rbp+var_18]
0x18000c989  mov     [rbx], rax
0x18000c98c  lea     rcx, [rbp+var_50]
0x18000c990  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000c995  mov     rax, rbx
0x18000c998  mov     rcx, [rbp+var_8]
0x18000c99c  xor     rcx, rsp; StackCookie
0x18000c99f  call    __security_check_cookie
0x18000c9a4  lea     r11, [rsp+80h+var_s0]
0x18000c9ac  mov     rbx, [r11+20h]
0x18000c9b0  mov     rsi, [r11+38h]
0x18000c9b4  mov     rsp, r11
0x18000c9b7  pop     r14
0x18000c9b9  pop     rdi
0x18000c9ba  pop     rbp
0x18000c9bb  retn
0x18000c9bc  mov     ecx, eax
0x18000c9be  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000c9c4  call    abort
0x18000c9ca  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
0x18000c9d0  mov     ecx, eax
0x18000c9d2  call    ?throw_hresult@winrt@@YAXUhresult@1@@Z; winrt::throw_hresult(winrt::hresult)
```
