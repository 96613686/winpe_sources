# UpdateAppFromStore(wil::basic_zstring_view<wchar_t>,std::chrono::duration<__int64,std::ratio<1,1>>)

- ea: `0x1800120a0`
- end: `0x180012a5d`
- name: `?UpdateAppFromStore@@YA?AUAppInstallResult@@V?$basic_zstring_view@_W@wil@@V?$duration@_JU?$ratio@$00$00@std@@@chrono@std@@@Z`
- size: `2493`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013688`

## callees

- `0x18000c3c8`
- `0x18000c4a4`
- `0x18000c808`
- `0x180011a18`
- `0x1800120a0`
- `0x180012a64`
- `0x1800185bc`
- `0x180018778`
- `0x18001a7fc`
- `0x18002d1a4`
- `0x180035384`
- `0x180035a50`
- `0x180036d78`
- `0x180036ed8`
- `0x18003a7dc`
- `0x18003aa20`
- `0x18003ac98`
- `0x180056119`
- `0x18005616d`
- `0x1800563c8`
- `0x180056500`
- `0x180056524`
- `0x18005c5e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001277f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012828`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001277f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180012828`

## string_xrefs

- `0x180012225`: `UsoClientUpdateAppFromStore`
- `0x180012174`: `WindowsUdk.ApplicationModel.Store.Preview.InstallControl.InstallContract`

## pseudocode

```c
__int64 __fastcall UpdateAppFromStore(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  volatile signed __int32 *v8; // rdi
  int v9; // eax
  void (__fastcall ***v10)(_QWORD, __int64 *, LPVOID *); // rbx
  int v11; // eax
  HANDLE ProcessHeap; // rax
  void *v13; // rcx
  int v14; // eax
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v17; // rbx
  const wchar_t *v18; // rdx
  __int64 v19; // rcx
  char *v20; // rdx
  int v21; // eax
  volatile signed __int32 *v22; // rbx
  __int128 v23; // xmm0
  char *v24; // rbx
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rbx
  __int64 v28; // rdi
  __int64 v29; // r12
  bool v30; // zf
  volatile signed __int32 *v31; // rbx
  int v32; // ecx
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  _QWORD v35[2]; // [rsp+30h] [rbp-F8h] BYREF
  __int128 v36; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v37; // [rsp+50h] [rbp-D8h]
  __int128 v38; // [rsp+60h] [rbp-C8h] BYREF
  const wchar_t *v39; // [rsp+78h] [rbp-B0h]
  __int64 v40; // [rsp+80h] [rbp-A8h]
  __int64 (__fastcall *v41)(); // [rsp+A0h] [rbp-88h] BYREF
  LPVOID lpMem; // [rsp+A8h] [rbp-80h] BYREF
  char v43[8]; // [rsp+B0h] [rbp-78h] BYREF
  __int64 v44; // [rsp+B8h] [rbp-70h] BYREF
  _QWORD v45[2]; // [rsp+C0h] [rbp-68h] BYREF
  __int128 v46; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v47; // [rsp+140h] [rbp+18h] BYREF

  v47 = a3;
  v37 = a1;
  v40 = a2;
  v46 = 0;
  std::make_shared<AppInstallResultWrapper,>(&v46);
  v35[0] = &qword_18009F7E8;
  _InterlockedAdd64(&qword_18009F7E8, 1u);
  if ( winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> )
  {
    `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager'::`1'::_lambda_32__::operator()(
      v5,
      &v44,
      &winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>);
    _InterlockedAdd64(&qword_18009F7E8, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    _InterlockedAdd64(&qword_18009F7E8, 0xFFFFFFFFFFFFFFFFuLL);
    v41 = `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager'::`1'::_lambda_32__::_lambda_invoker_cdecl_;
    winrt::impl::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::call<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager (*)(winrt::Windows::Foundation::IActivationFactory const &)>(
      v5,
      &v44,
      &v41);
  }
  if ( !(unsigned __int8)Windows::UdkVersionChecker::_anonymous_namespace_::IsUdkSupported() )
    goto LABEL_130;
  v6 = -1;
  do
    ++v6;
  while ( winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::InstallContractName[v6] );
  if ( (_DWORD)v6 )
  {
    if ( winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::InstallContractName[(unsigned int)v6] )
      abort();
    DWORD2(v38) = 1;
    HIDWORD(v38) = v6;
    v39 = L"WindowsUdk.ApplicationModel.Store.Preview.InstallControl.InstallContract";
    *(_QWORD *)&v38 = (char *)&v38 + 8;
  }
  else
  {
    *(_QWORD *)&v38 = 0;
  }
  if ( (unsigned __int8)winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(
                          (const struct winrt::param::hstring *)&v38,
                          1u,
                          2u) )
    goto LABEL_19;
  v7 = -1;
  do
    ++v7;
  while ( winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::InstallContractName[v7] );
  if ( (_DWORD)v7 )
  {
    if ( winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::InstallContractName[(unsigned int)v7] )
      abort();
    DWORD2(v38) = 1;
    HIDWORD(v38) = v7;
    v39 = L"WindowsUdk.ApplicationModel.Store.Preview.InstallControl.InstallContract";
    *(_QWORD *)&v38 = (char *)&v38 + 8;
  }
  else
  {
    *(_QWORD *)&v38 = 0;
  }
  if ( (unsigned __int8)winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(
                          (const struct winrt::param::hstring *)&v38,
                          2u) )
  {
LABEL_19:
    winrt::hstring::hstring((winrt::hstring *)&lpMem, L"UsoClientUpdateAppFromStore", 0x1Bu);
    v8 = (volatile signed __int32 *)lpMem;
    *(_QWORD *)&v38 = lpMem;
    *(_QWORD *)&v36 = &v44;
    *((_QWORD *)&v36 + 1) = &v38;
    v35[0] = &qword_18009F7A8;
    _InterlockedAdd64(&qword_18009F7A8, 1u);
    if ( winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2> )
    {
      v41 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 (__fastcall **)()))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
                                                                                          + 48LL))(
             winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>,
             v44,
             v38,
             &v41);
      if ( v9 < 0 )
        winrt::throw_hresult((unsigned int)v9);
      v10 = (void (__fastcall ***)(_QWORD, __int64 *, LPVOID *))v41;
      _InterlockedAdd64(&qword_18009F7A8, 0xFFFFFFFFFFFFFFFFuLL);
    }
    else
    {
      _InterlockedAdd64(&qword_18009F7A8, 0xFFFFFFFFFFFFFFFFuLL);
      ___call_AEAV_lambda_36____0___0AppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_winrt__QEAA_AEBU23456Windows_8_AEBUhstring_param_8__Z____factory_cache_entry_UAppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_winrt__UIAppInstallManagerFactory2_234567__impl_winrt__QEAA_A_PAEAV_lambda_36____0___0AppInstallManager_InstallControl_Preview_Store_ApplicationModel_WindowsUdk_2_QEAA_AEBU45678Windows_2_AEBUhstring_param_2__Z__Z(
        0,
        &v41,
        &v36);
      v10 = (void (__fastcall ***)(_QWORD, __int64 *, LPVOID *))v41;
    }
    if ( v8 )
    {
      v11 = _InterlockedDecrement(v8 + 6);
      if ( v11 )
      {
        if ( v11 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, (LPVOID)v8);
      }
    }
    v43[0] = 0;
    if ( v10 )
    {
      lpMem = 0;
      (**v10)(
        v10,
        winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager3>,
        &lpMem);
      v13 = lpMem;
    }
    else
    {
      v13 = 0;
    }
    lpMem = v13;
    v14 = (*(__int64 (__fastcall **)(void *, char *))(*(_QWORD *)v13 + 72LL))(v13, v43);
    if ( v14 < 0 )
      winrt::throw_hresult((unsigned int)v14);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&lpMem);
    if ( !v43[0] )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_QWORD *)(a1 + 16) = 1;
      if ( v10 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
      if ( v44 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
      v15 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1)
        && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
      return a1;
    }
    if ( v10 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
  }
  else
  {
LABEL_130:
    if ( !IsStoreAutoUpdateEnabled() )
    {
      *(_QWORD *)a1 = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_QWORD *)(a1 + 16) = 1;
      if ( v44 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
      v17 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      return a1;
    }
  }
  v18 = *(const wchar_t **)a2;
  v19 = *(unsigned int *)(a2 + 8);
  if ( (_DWORD)v19 )
  {
    if ( v18[v19] )
      abort();
    DWORD2(v38) = 1;
    HIDWORD(v38) = v19;
    v39 = v18;
    v20 = (char *)&v38 + 8;
  }
  else
  {
    v20 = 0;
  }
  *(_QWORD *)&v38 = v20;
  v41 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, char *, __int64 (__fastcall **)()))(*(_QWORD *)v44 + 160LL))(v44, v20, &v41);
  if ( v21 < 0 )
    winrt::throw_hresult((unsigned int)v21);
  winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::get(
    &v41,
    v45);
  if ( v45[0] )
  {
    v23 = 0;
    if ( *((_QWORD *)&v46 + 1) )
    {
      v23 = v46;
      _InterlockedAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 12LL), 1u);
    }
    v36 = v23;
    v38 = 0;
    v24 = (char *)operator new(0x20u);
    *(_OWORD *)(v24 + 8) = v36;
    v36 = 0;
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    *((_DWORD *)v24 + 6) = 1;
    *(_QWORD *)v24 = off_180066440;
    v35[0] = v24;
    v25 = *((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v36 + 1) + 12LL), 0xFFFFFFFF) == 1 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 8LL))(v25);
    }
    lpMem = 0;
    v26 = (*(__int64 (__fastcall **)(_QWORD, char *, LPVOID *))(*(_QWORD *)v45[0] + 128LL))(v45[0], v24, &lpMem);
    if ( v26 < 0 )
      winrt::throw_hresult((unsigned int)v26);
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v35);
    v27 = v46 + 80;
    v36 = (unsigned __int64)(v46 + 80);
    if ( (unsigned int)mtx_do_lock(v46 + 80) )
      std::_Throw_Cpp_error(5);
    if ( *(_DWORD *)(v27 + 76) == 0x7FFFFFFF )
    {
      *(_DWORD *)(v27 + 76) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    BYTE8(v36) = 1;
    v28 = v46;
    v29 = std::_To_absolute_time<__int64,std::ratio<1,1>>(v35, &v47);
    if ( *(_BYTE *)v46 )
      goto LABEL_93;
    while ( (unsigned int)std::condition_variable::wait_until<std::chrono::steady_clock,std::chrono::duration<__int64,std::ratio<1,1000000000>>>(
                            v28 + 8,
                            &v36,
                            v29) != 1 )
    {
      if ( *(_BYTE *)v46 )
        goto LABEL_93;
    }
    if ( *(_BYTE *)v46 )
    {
LABEL_93:
      v30 = (*(_DWORD *)(v27 + 76))-- == 1;
      if ( v30 )
      {
        *(_DWORD *)(v27 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v27 + 16));
      }
      v32 = *(_DWORD *)(v46 + 4);
      if ( v32 >= 0 )
      {
        if ( v45[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v45);
        if ( v41 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
        if ( v44 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = 0;
        *(_DWORD *)(a1 + 20) = 256;
        v34 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
        if ( *((_QWORD *)&v46 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
            if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
          }
        }
        return a1;
      }
      else
      {
        *(_DWORD *)a1 = v32;
        *(_DWORD *)(a1 + 4) = 0;
        *(_QWORD *)(a1 + 8) = 0;
        *(_DWORD *)(a1 + 16) = 2;
        *(_DWORD *)(a1 + 20) = 1;
        if ( v45[0] )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v45);
        if ( v41 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
        if ( v44 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
        v33 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
        if ( *((_QWORD *)&v46 + 1) )
        {
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
            if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
          }
        }
        return a1;
      }
    }
    else
    {
      *(_DWORD *)a1 = -2145082834;
      *(_DWORD *)(a1 + 4) = 0;
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 16) = 6;
      *(_DWORD *)(a1 + 20) = 1;
      v30 = (*(_DWORD *)(v27 + 76))-- == 1;
      if ( v30 )
      {
        *(_DWORD *)(v27 + 72) = -1;
        ReleaseSRWLockExclusive((PSRWLOCK)(v27 + 16));
      }
      if ( v45[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v45);
      if ( v41 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
      if ( v44 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
      v31 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
      if ( *((_QWORD *)&v46 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
          if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
        }
      }
      return a1;
    }
  }
  else
  {
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)(a1 + 16) = 10;
    *(_DWORD *)(a1 + 20) = 256;
    if ( v41 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v41);
    if ( v44 )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v44);
    v22 = (volatile signed __int32 *)*((_QWORD *)&v46 + 1);
    if ( *((_QWORD *)&v46 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v46 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
        if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
      }
    }
    return a1;
  }
}

```

## disassembly

```asm
0x1800120a0  mov     r11, rsp
0x1800120a3  mov     [r11+18h], r8
0x1800120a7  push    rbx
0x1800120a8  push    rsi
0x1800120a9  push    rdi
0x1800120aa  push    r12
0x1800120ac  push    r13
0x1800120ae  push    r14
0x1800120b0  push    r15
0x1800120b2  sub     rsp, 0F0h
0x1800120b9  mov     rax, cs:__security_cookie
0x1800120c0  xor     rax, rsp
0x1800120c3  mov     [rsp+128h+var_48], rax
0x1800120cb  mov     r12, rdx
0x1800120ce  mov     r15, rcx
0x1800120d1  mov     [rsp+128h+var_D8], rcx
0x1800120d6  mov     [rsp+128h+var_A8], rdx
0x1800120de  xor     esi, esi
0x1800120e0  xorps   xmm0, xmm0
0x1800120e3  movups  xmmword ptr [r11-58h], xmm0
0x1800120e8  lea     rcx, [r11-58h]
0x1800120ec  call    ??$make_shared@UAppInstallResultWrapper@@$$V@std@@YA?AV?$shared_ptr@UAppInstallResultWrapper@@@0@XZ; std::make_shared<AppInstallResultWrapper,>(void)
0x1800120f1  nop
0x1800120f2  lea     rax, qword_18009F7E8
0x1800120f9  mov     [rsp+128h+var_F8], rax
0x1800120fe  lea     r13d, [rsi+1]
0x180012102  lock add cs:qword_18009F7E8, r13
0x18001210a  cmp     cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A, rsi; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x180012111  jz      short loc_180012136
0x180012113  lea     r8, ??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@12@A; factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>::winrt::factory_cache_entry<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory> winrt::impl::factory_cache_entry_v<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::Windows::Foundation::IActivationFactory>
0x18001211a  lea     rdx, [rsp+128h+var_70]
0x180012122  call    ??R_lambda_32__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@QEBA@AEBUIActivationFactory@Foundation@67@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)'::`1'::_lambda_32__::operator()(winrt::Windows::Foundation::IActivationFactory const &)
0x180012127  nop
0x180012128  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001212c  lock add cs:qword_18009F7E8, r14
0x180012134  jmp     short loc_180012167
0x180012136  or      r14, 0FFFFFFFFFFFFFFFFh
0x18001213a  lock add cs:qword_18009F7E8, r14
0x180012142  lea     rax, ?_lambda_invoker_cdecl_@_lambda_32__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@QEAA@XZ@SA@AEBUIActivationFactory@Foundation@78@@Z; `winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallManager::AppInstallManager(void)'::`1'::_lambda_32__::_lambda_invoker_cdecl_(winrt::Windows::Foundation::IActivationFactory const &)
0x180012149  mov     [rsp+128h+var_88], rax
0x180012151  lea     r8, [rsp+128h+var_88]
0x180012159  lea     rdx, [rsp+128h+var_70]
0x180012161  call    ??$call@P6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@AEBUIActivationFactory@Foundation@67@@Z@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@UIActivationFactory@Foundation@67@@impl@winrt@@QEAA?A_P$$QEAP6A?AUAppInstallManager@InstallControl@Preview@Store@ApplicationModel@Windows@2@AEBUIActivationFactory@Foundation@82@@Z@Z
0x180012166  nop
0x180012167  call    Windows__UdkVersionChecker___anonymous_namespace___IsUdkSupported
0x18001216c  test    al, al
0x18001216e  jz      loc_180012436
0x180012174  lea     rbx, ?InstallContractName@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@3QB_WB; "WindowsUdk.ApplicationModel.Store.Previ"...
0x18001217b  mov     rcx, r14
0x18001217e  inc     rcx
0x180012181  cmp     [rbx+rcx*2], si
0x180012185  jnz     short loc_18001217E
0x180012187  test    ecx, ecx
0x180012189  jnz     short loc_180012192
0x18001218b  mov     qword ptr [rsp+128h+var_C8], rsi
0x180012190  jmp     short loc_1800121B6
0x180012192  mov     eax, ecx
0x180012194  cmp     [rbx+rax*2], si
0x180012198  jnz     loc_180012A0A
0x18001219e  mov     dword ptr [rsp+128h+var_C8+8], r13d
0x1800121a3  mov     dword ptr [rsp+128h+var_C8+0Ch], ecx
0x1800121a7  mov     [rsp+128h+var_B0], rbx
0x1800121ac  lea     rax, [rsp+128h+var_C8+8]
0x1800121b1  mov     qword ptr [rsp+128h+var_C8], rax
0x1800121b6  mov     r8d, 2; unsigned __int16
0x1800121bc  mov     edx, r13d; unsigned __int16
0x1800121bf  lea     rcx, [rsp+128h+var_C8]; struct winrt::param::hstring *
0x1800121c4  call    ?IsApiContractPresent@ApiInformation@Metadata@Foundation@WindowsUdk@winrt@@SA@AEBUhstring@param@5@GG@Z; winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(winrt::param::hstring const &,ushort,ushort)
0x1800121c9  test    al, al
0x1800121cb  jnz     short loc_18001221F
0x1800121cd  mov     rcx, r14
0x1800121d0  inc     rcx
0x1800121d3  cmp     [rbx+rcx*2], si
0x1800121d7  jnz     short loc_1800121D0
0x1800121d9  test    ecx, ecx
0x1800121db  jnz     short loc_1800121E4
0x1800121dd  mov     qword ptr [rsp+128h+var_C8], rsi
0x1800121e2  jmp     short loc_180012208
0x1800121e4  mov     eax, ecx
0x1800121e6  cmp     [rbx+rax*2], si
0x1800121ea  jnz     loc_180012A10
0x1800121f0  mov     dword ptr [rsp+128h+var_C8+8], r13d
0x1800121f5  mov     dword ptr [rsp+128h+var_C8+0Ch], ecx
0x1800121f9  mov     [rsp+128h+var_B0], rbx
0x1800121fe  lea     rax, [rsp+128h+var_C8+8]
0x180012203  mov     qword ptr [rsp+128h+var_C8], rax
0x180012208  mov     edx, 2; unsigned __int16
0x18001220d  lea     rcx, [rsp+128h+var_C8]; struct winrt::param::hstring *
0x180012212  call    ?IsApiContractPresent@ApiInformation@Metadata@Foundation@WindowsUdk@winrt@@SA@AEBUhstring@param@5@G@Z; winrt::WindowsUdk::Foundation::Metadata::ApiInformation::IsApiContractPresent(winrt::param::hstring const &,ushort)
0x180012217  test    al, al
0x180012219  jz      loc_180012436
0x18001221f  mov     r8d, 1Bh; unsigned int
0x180012225  lea     rdx, aUsoclientupdat; "UsoClientUpdateAppFromStore"
0x18001222c  lea     rcx, [rsp+128h+lpMem]; this
0x180012234  call    ??0hstring@winrt@@QEAA@PEB_WI@Z; winrt::hstring::hstring(wchar_t const *,uint)
0x180012239  nop
0x18001223a  mov     rdi, [rsp+128h+lpMem]
0x180012242  mov     qword ptr [rsp+128h+var_C8], rdi
0x180012247  lea     rax, [rsp+128h+var_70]
0x18001224f  mov     qword ptr [rsp+128h+var_E8], rax
0x180012254  lea     rax, [rsp+128h+var_C8]
0x180012259  mov     qword ptr [rsp+128h+var_E8+8], rax
0x18001225e  lea     rax, qword_18009F7A8
0x180012265  mov     [rsp+128h+var_F8], rax
0x18001226a  lock add cs:qword_18009F7A8, r13
0x180012272  mov     rcx, cs:??$factory_cache_entry_v@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@12@A; factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>::winrt::factory_cache_entry<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2> winrt::impl::factory_cache_entry_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::AppInstallManager,winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManagerFactory2>
0x180012279  test    rcx, rcx
0x18001227c  jz      short loc_1800122C9
0x18001227e  mov     [rsp+128h+var_88], rsi
0x180012286  mov     rax, [rcx]
0x180012289  lea     r9, [rsp+128h+var_88]
0x180012291  mov     r8, qword ptr [rsp+128h+var_C8]
0x180012296  mov     rdx, [rsp+128h+var_70]
0x18001229e  mov     rax, [rax+30h]
0x1800122a2  call    _guard_dispatch_icall
0x1800122a7  test    eax, eax
0x1800122a9  js      loc_180012A16
0x1800122af  mov     rbx, [rsp+128h+var_88]
0x1800122b7  mov     [rsp+128h+var_88], rbx
0x1800122bf  lock add cs:qword_18009F7A8, r14
0x1800122c7  jmp     short loc_1800122EB
0x1800122c9  lock add cs:qword_18009F7A8, r14
0x1800122d1  lea     r8, [rsp+128h+var_E8]
0x1800122d6  lea     rdx, [rsp+128h+var_88]
0x1800122de  call    ??$call@AEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@QEAA@AEBU23456Windows@8@AEBUhstring@param@8@@Z@@?$factory_cache_entry@UAppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@UIAppInstallManagerFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_36__@?0???0AppInstallManager@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@2@QEAA@AEBU45678Windows@2@AEBUhstring@param@2@@Z@@Z
0x1800122e3  mov     rbx, [rsp+128h+var_88]
0x1800122eb  test    rdi, rdi
0x1800122ee  jz      short loc_180012310
0x1800122f0  mov     eax, r14d
0x1800122f3  lock xadd [rdi+18h], eax
0x1800122f8  sub     eax, 1
0x1800122fb  jnz     short loc_180012322
0x1800122fd  nop
0x1800122fe  call    WINRT_IMPL_GetProcessHeap
0x180012303  mov     rcx, rax; hHeap
0x180012306  mov     r8, rdi; lpMem
0x180012309  xor     edx, edx; dwFlags
0x18001230b  call    WINRT_IMPL_HeapFree
0x180012310  mov     [rsp+128h+var_78], sil
0x180012318  test    rbx, rbx
0x18001231b  jnz     short loc_18001232C
0x18001231d  mov     rcx, rsi
0x180012320  jmp     short loc_180012359
0x180012322  test    eax, eax
0x180012324  js      loc_180012A1E
0x18001232a  jmp     short loc_180012310
0x18001232c  mov     [rsp+128h+lpMem], rsi
0x180012334  mov     rax, [rbx]
0x180012337  lea     r8, [rsp+128h+lpMem]
0x18001233f  lea     rdx, ??$guid_v@UIAppInstallManager3@InstallControl@Preview@Store@ApplicationModel@WindowsUdk@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::WindowsUdk::ApplicationModel::Store::Preview::InstallControl::IAppInstallManager3>
0x180012346  mov     rcx, rbx
0x180012349  mov     rax, [rax]
0x18001234c  call    _guard_dispatch_icall
0x180012351  mov     rcx, [rsp+128h+lpMem]
0x180012359  mov     [rsp+128h+lpMem], rcx
0x180012361  mov     rax, [rcx]
0x180012364  lea     rdx, [rsp+128h+var_78]
0x18001236c  mov     rax, [rax+48h]
0x180012370  call    _guard_dispatch_icall
0x180012375  test    eax, eax
0x180012377  js      loc_180012A24
0x18001237d  lea     rcx, [rsp+128h+lpMem]
0x180012385  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001238a  cmp     [rsp+128h+var_78], sil
0x180012392  jnz     loc_18001241E
0x180012398  mov     [r15], rsi
0x18001239b  mov     [r15+8], rsi
0x18001239f  mov     qword ptr [r15+10h], 1
0x1800123a7  test    rbx, rbx
0x1800123aa  jz      short loc_1800123BA
0x1800123ac  lea     rcx, [rsp+128h+var_88]
0x1800123b4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800123b9  nop
0x1800123ba  cmp     [rsp+128h+var_70], rsi
0x1800123c2  jz      short loc_1800123D2
0x1800123c4  lea     rcx, [rsp+128h+var_70]
0x1800123cc  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800123d1  nop
0x1800123d2  mov     rbx, [rsp+128h+var_50]
0x1800123da  test    rbx, rbx
0x1800123dd  jz      short loc_180012416
0x1800123df  mov     eax, r14d
0x1800123e2  lock xadd [rbx+8], eax
0x1800123e7  add     eax, r14d
0x1800123ea  jnz     short loc_180012416
0x1800123ec  mov     rax, [rbx]
0x1800123ef  mov     rcx, rbx
0x1800123f2  mov     rax, [rax]
0x1800123f5  call    _guard_dispatch_icall
0x1800123fa  mov     edx, r14d
0x1800123fd  lock xadd [rbx+0Ch], edx
0x180012402  add     edx, r14d
0x180012405  jnz     short loc_180012416
0x180012407  mov     rdx, [rbx]
0x18001240a  mov     rcx, rbx
0x18001240d  mov     rax, [rdx+8]
0x180012411  call    _guard_dispatch_icall
0x180012416  mov     rax, r15
0x180012419  jmp     loc_1800129E7
0x18001241e  test    rbx, rbx
0x180012421  jz      loc_1800124B2
0x180012427  lea     rcx, [rsp+128h+var_88]
0x18001242f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012434  jmp     short loc_1800124B2
0x180012436  call    ?IsStoreAutoUpdateEnabled@@YA_NXZ; IsStoreAutoUpdateEnabled(void)
0x18001243b  test    al, al
0x18001243d  jnz     short loc_1800124B2
0x18001243f  mov     [r15], rsi
0x180012442  mov     [r15+8], rsi
0x180012446  mov     qword ptr [r15+10h], 1
0x18001244e  cmp     [rsp+128h+var_70], rsi
0x180012456  jz      short loc_180012466
0x180012458  lea     rcx, [rsp+128h+var_70]
0x180012460  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012465  nop
0x180012466  mov     rbx, [rsp+128h+var_50]
0x18001246e  test    rbx, rbx
0x180012471  jz      short loc_1800124AA
0x180012473  mov     eax, r14d
0x180012476  lock xadd [rbx+8], eax
0x18001247b  add     eax, r14d
0x18001247e  jnz     short loc_1800124AA
0x180012480  mov     rax, [rbx]
0x180012483  mov     rcx, rbx
0x180012486  mov     rax, [rax]
0x180012489  call    _guard_dispatch_icall
0x18001248e  mov     eax, r14d
0x180012491  lock xadd [rbx+0Ch], eax
0x180012496  add     eax, r14d
0x180012499  jnz     short loc_1800124AA
0x18001249b  mov     rax, [rbx]
0x18001249e  mov     rcx, rbx
0x1800124a1  mov     rax, [rax+8]
0x1800124a5  call    _guard_dispatch_icall
0x1800124aa  mov     rax, r15
0x1800124ad  jmp     loc_1800129E7
0x1800124b2  mov     rdx, [r12]
0x1800124b6  mov     ecx, [r12+8]
0x1800124bb  test    ecx, ecx
0x1800124bd  jnz     short loc_1800124C4
0x1800124bf  mov     rdx, rsi
0x1800124c2  jmp     short loc_1800124E1
0x1800124c4  cmp     [rdx+rcx*2], si
0x1800124c8  jnz     loc_180012A2C
0x1800124ce  mov     dword ptr [rsp+128h+var_C8+8], r13d
0x1800124d3  mov     dword ptr [rsp+128h+var_C8+0Ch], ecx
0x1800124d7  mov     [rsp+128h+var_B0], rdx
0x1800124dc  lea     rdx, [rsp+128h+var_C8+8]
0x1800124e1  mov     qword ptr [rsp+128h+var_C8], rdx
0x1800124e6  mov     [rsp+128h+var_88], rsi
0x1800124ee  mov     rcx, [rsp+128h+var_70]
0x1800124f6  mov     rax, [rcx]
0x1800124f9  lea     r8, [rsp+128h+var_88]
0x180012501  mov     rax, [rax+0A0h]
0x180012508  call    _guard_dispatch_icall
0x18001250d  test    eax, eax
0x18001250f  js      loc_180012A32
0x180012515  mov     rax, [rsp+128h+var_88]
0x18001251d  mov     [rsp+128h+var_88], rax
0x180012525  lea     rdx, [rsp+128h+var_68]
0x18001252d  lea     rcx, [rsp+128h+var_88]
0x180012535  call    ?get@?$consume_Windows_Foundation_IAsyncOperation@U?$IAsyncOperation@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@Foundation@Windows@winrt@@UAppInstallItem@InstallControl@Preview@Store@ApplicationModel@34@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_IAsyncOperation<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>,winrt::Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem>::get(void)
0x18001253a  nop
0x18001253b  cmp     [rsp+128h+var_68], rsi
0x180012543  jnz     loc_1800125DC
0x180012549  mov     [r15], rsi
0x18001254c  mov     [r15+8], rsi
0x180012550  mov     dword ptr [r15+10h], 0Ah
0x180012558  mov     dword ptr [r15+14h], 100h
0x180012560  cmp     [rsp+128h+var_88], rsi
0x180012568  jz      short loc_180012578
0x18001256a  lea     rcx, [rsp+128h+var_88]
0x180012572  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180012577  nop
0x180012578  cmp     [rsp+128h+var_70], rsi
0x180012580  jz      short loc_180012590
0x180012582  lea     rcx, [rsp+128h+var_70]
0x18001258a  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001258f  nop
0x180012590  mov     rbx, [rsp+128h+var_50]
0x180012598  test    rbx, rbx
0x18001259b  jz      short loc_1800125D4
0x18001259d  mov     eax, r14d
0x1800125a0  lock xadd [rbx+8], eax
0x1800125a5  add     eax, r14d
0x1800125a8  jnz     short loc_1800125D4
0x1800125aa  mov     rax, [rbx]
0x1800125ad  mov     rcx, rbx
0x1800125b0  mov     rax, [rax]
0x1800125b3  call    _guard_dispatch_icall
0x1800125b8  mov     eax, r14d
0x1800125bb  lock xadd [rbx+0Ch], eax
0x1800125c0  add     eax, r14d
0x1800125c3  jnz     short loc_1800125D4
0x1800125c5  mov     rax, [rbx]
0x1800125c8  mov     rcx, rbx
0x1800125cb  mov     rax, [rax+8]
0x1800125cf  call    _guard_dispatch_icall
0x1800125d4  mov     rax, r15
0x1800125d7  jmp     loc_1800129E7
  ... truncated ...
```
