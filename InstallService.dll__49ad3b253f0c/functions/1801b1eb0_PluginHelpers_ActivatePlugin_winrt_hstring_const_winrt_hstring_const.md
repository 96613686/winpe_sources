# PluginHelpers::ActivatePlugin(winrt::hstring const &,winrt::hstring const &)

- ea: `0x1801b1eb0`
- end: `0x1801b2566`
- name: `?ActivatePlugin@PluginHelpers@@YA?AUIInstallServicePlugin@Plugin@InstallService@Internal@Windows@winrt@@AEBUhstring@7@0@Z`
- size: `1718`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, const struct winrt::hstring *)`
- caller_count: `13`
- callee_count: `43`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18015a614`
- `0x18015c8e4`
- `0x18015db2c`
- `0x180165b6c`
- `0x1801661dc`
- `0x18016f6b0`
- `0x180174800`
- `0x1801765a8`
- `0x180179094`
- `0x1801964ac`
- `0x1801b2624`
- `0x1801b63e0`
- `0x1801b81f4`

## callees

- `0x180009ea0`
- `0x18000ab24`
- `0x18000ad3c`
- `0x180020868`
- `0x180022298`
- `0x180037200`
- `0x18003e9e0`
- `0x1800453a0`
- `0x1800453bc`
- `0x180045588`
- `0x180047e04`
- `0x18006c92c`
- `0x18006cb88`
- `0x18006cc00`
- `0x18006cdd8`
- `0x18006cf2c`
- `0x18006e440`
- `0x18006f4e4`
- `0x180094c14`
- `0x180095b2c`
- `0x180095b68`
- `0x1800994a0`
- `0x1800d3130`
- `0x1800d32d0`
- `0x1801020b4`
- `0x180102114`
- `0x180102208`
- `0x180138ec8`
- `0x180154b78`
- `0x180192adc`
- `0x1801b128c`
- `0x1801b17cc`
- `0x1801b1b64`
- `0x1801b1cc8`
- `0x1801b1eb0`
- `0x1801b27cc`
- `0x1801b2d4c`
- `0x1801b3144`
- `0x1801b32b4`
- `0x1801b33d8`
- `0x1801b5918`
- `0x1801c247c`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801b2471`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801b2471`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b1f40`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x1801b1f40`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801b2446`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1801b2446`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801b20aa`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1801b20aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b20e4`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801b20e4`

## string_xrefs

- `0x1801b1efe`: `Microsoft.GamingServices_8wekyb3d8bbwe`
- `0x1801b21de`: `PluginId`
- `0x1801b21f1`: `Attempting to find plugin `
- `0x1801b2410`: `\InstallServicePlugin.dll`
- `0x1801b1f84`: `onecoreuap\enduser\winstore\installservice\libqueue2\pluginhelpers.cpp`
- `0x1801b2215`: `onecoreuap\enduser\winstore\installservice\libqueue2\pluginhelpers.cpp`
- `0x1801b2195`: `Windows.Xbox.System.Internal.Deployment.XVCInstallWorkFactory`
- `0x1801b1f60`: `Gaming service support on ARM is not enabled in OneSettings`
- `0x1801b1f73`: `PluginHelpers::ActivatePlugin`
- `0x1801b2204`: `PluginHelpers::ActivatePlugin`
- `0x1801b2467`: `ActivatePlugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall PluginHelpers::ActivatePlugin(_QWORD *a1, __int64 *a2, const struct winrt::hstring *a3)
{
  _QWORD *v5; // rax
  __int64 v6; // r9
  _QWORD *v7; // r9
  __int64 v8; // r8
  const OLECHAR *v9; // rax
  unsigned int v10; // eax
  void *v11; // r8
  __int64 v12; // rax
  const unsigned __int16 *v13; // rax
  __int64 v14; // rax
  const struct winrt::hstring *v15; // rdx
  __int64 v16; // rax
  __int64 v17; // rbx
  int v18; // eax
  __int64 PackagesForUserWithPackageTypes; // rax
  __int64 *v20; // rax
  char v21; // bl
  __int64 v22; // rax
  __int64 PackagesWithPackageTypes; // rax
  __int64 v24; // rax
  __int64 v25; // rsi
  unsigned int v26; // eax
  __int64 v27; // rax
  const WCHAR *v28; // rax
  HMODULE LibraryW; // rax
  const struct winrt::impl::slim_source_location *v30; // rdx
  const struct winrt::impl::slim_source_location *v31; // rdx
  FARPROC ProcAddress; // rbx
  void **v33; // rax
  unsigned int v34; // eax
  const struct winrt::hstring *v35; // rdx
  const struct winrt::hstring *v36; // rdx
  __int64 v38; // [rsp+40h] [rbp-C0h] BYREF
  int v39; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  struct IUnknown *ppv; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v42[8]; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h]
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  __int64 v45; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v46[8]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v47[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v48[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v49[8]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v50[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v51[8]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v52[8]; // [rsp+B0h] [rbp-50h] BYREF
  GUID iid; // [rsp+B8h] [rbp-48h] BYREF
  __int64 pExceptionObject; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v55; // [rsp+D0h] [rbp-30h]
  __int64 *v56; // [rsp+E8h] [rbp-18h] BYREF
  __int128 v57; // [rsp+F0h] [rbp-10h]
  _QWORD v58[5]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v59[256]; // [rsp+130h] [rbp+30h] BYREF

  *(_QWORD *)&iid.Data1 = a1;
  v43 = 0;
  winrt::hstring::hstring((winrt::hstring *)&v38, a3);
  if ( (unsigned __int8)winrt::operator==(&v38, L"Microsoft.GamingServices_8wekyb3d8bbwe")
    || (unsigned __int8)winrt::operator==(&v38, L"ChainedWork") )
  {
    InitOnceExecuteOnce(&InitOnce, InitializeInstallServiceConfiguration, 0, 0);
    if ( dword_1802E4F64 )
    {
      if ( !GetMsixvcArmSupportEnabledFromOneSettings() )
      {
        *(_QWORD *)&iid.Data1 = L"Gaming service support on ARM is not enabled in OneSettings";
        *(_QWORD *)iid.Data4 = 59;
        std::string::string(&v56, "PluginHelpers::ActivatePlugin");
        std::string::string(
          &pExceptionObject,
          "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\pluginhelpers.cpp");
        Logging::Log<>((unsigned int)&pExceptionObject, 55, (unsigned int)&v56, 3, (__int64)&iid);
        std::string::~string(&pExceptionObject);
        std::string::~string(&v56);
        LODWORD(v56) = 0;
        v57 = 0;
        winrt::hresult_error::hresult_error(&pExceptionObject, 3225399315LL, &v56);
        throw (winrt::hresult_error *)&pExceptionObject;
      }
    }
  }
  if ( !(unsigned __int8)winrt::operator==(&v38, L"WU") )
  {
    if ( (unsigned __int8)winrt::operator==(&v38, L"ChainedWork") )
    {
      v5 = operator new(0x18u);
      *(_OWORD *)v5 = 0;
      v5[2] = 0;
      winrt::impl::producers_base<ChainedWorkPlugin,std::tuple<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>>::producers_base<ChainedWorkPlugin,std::tuple<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>>(v5 + 2);
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      std::atomic<unsigned __int64>::atomic<unsigned __int64>(v6 + 8);
      *v7 = &winrt::impl::heap_implements<ChainedWorkPlugin>::`vftable';
      *a1 = v8;
      goto LABEL_39;
    }
    PluginHelpers::GetPluginFromStaticMap(&v44, &v38);
    if ( v44 )
    {
      iid = 0;
      v9 = winrt::hstring::c_str((winrt::hstring *)&v44);
      if ( IIDFromString(v9, &iid) >= 0 )
      {
        ppv = 0;
        LODWORD(v56) = 0;
        v57 = 0;
        v10 = CoCreateInstance(&iid, 0, 1u, &GUID_42dfa3dd_f369_478e_b764_0079881e8d8d, (LPVOID *)&ppv);
        winrt::check_hresult(&v39, v10, &v56);
        v40 = 0;
        winrt::copy_from_abi((winrt *)&v40, ppv, v11);
        v12 = v40;
        v40 = 0;
        *a1 = v12;
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v40);
        if ( ppv )
          winrt::com_ptr<IInspectable>::unconditional_release_ref(&ppv);
        goto LABEL_38;
      }
      v13 = winrt::hstring::c_str((winrt::hstring *)&v44);
      winrt::param::hstring::hstring((winrt::param::hstring *)v58, v13);
      v14 = winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(v42, v58);
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>(
        v14,
        a1);
    }
    else
    {
      if ( !(unsigned __int8)winrt::operator==(&v38, L"XVC") )
      {
        PluginHelpers::IncrementPluginActivationCount((PluginHelpers *)&v38, v15);
        v56 = &v38;
        LOBYTE(v57) = 1;
        v17 = std::make_pair<unsigned short const (&)[9],winrt::hstring &>(v51, L"PluginId", &v38);
        *(_QWORD *)&iid.Data1 = L"Attempting to find plugin ";
        *(_QWORD *)iid.Data4 = 26;
        std::string::string(v58, "PluginHelpers::ActivatePlugin");
        std::string::string(
          &pExceptionObject,
          "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\pluginhelpers.cpp");
        Logging::TraceActivity_std::pair_unsigned_short_const___winrt::hstring___(
          (unsigned int)v59,
          (unsigned int)&pExceptionObject,
          106,
          (unsigned int)v58,
          3,
          (__int64)&iid,
          v17);
        std::string::~string(&pExceptionObject);
        std::string::~string(v58);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v52);
        v18 = winrt::Windows::Management::Deployment::PackageManager::PackageManager((winrt::Windows::Management::Deployment::PackageManager *)&v40);
        v39 = 1;
        v58[0] = v38;
        pExceptionObject = *a2;
        PackagesForUserWithPackageTypes = winrt::impl::consume_Windows_Management_Deployment_IPackageManager2<winrt::Windows::Management::Deployment::PackageManager>::FindPackagesForUserWithPackageTypes(
                                            v18,
                                            (unsigned int)v42,
                                            (unsigned int)&pExceptionObject,
                                            (unsigned int)v58,
                                            (__int64)&v39);
        winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
          PackagesForUserWithPackageTypes,
          &ppv);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v42);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v40);
        if ( (unsigned __int8)winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceScanForUpdateProperties<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceScanForUpdateProperties>::IsInteractive(&ppv) )
        {
          v20 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::StateRepository::Package>,winrt::Windows::Internal::StateRepository::Package>::Current(
                             &ppv,
                             v50);
          v21 = 2;
        }
        else
        {
          v22 = winrt::Windows::Management::Deployment::PackageManager::PackageManager((winrt::Windows::Management::Deployment::PackageManager *)v49);
          v43 = 4;
          v39 = 1;
          v58[0] = v38;
          PackagesWithPackageTypes = winrt::impl::consume_Windows_Management_Deployment_IPackageManager2<winrt::Windows::Management::Deployment::PackageManager>::FindPackagesWithPackageTypes(
                                       v22,
                                       v48,
                                       v58,
                                       &v39);
          v43 = 12;
          v24 = winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(
                  PackagesWithPackageTypes,
                  v47);
          v43 = 28;
          v20 = (__int64 *)winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::StateRepository::Package>,winrt::Windows::Internal::StateRepository::Package>::Current(
                             v24,
                             v46);
          v21 = 60;
        }
        v25 = *v20;
        *v20 = 0;
        *(_QWORD *)&iid.Data1 = v25;
        if ( (v21 & 0x20) != 0 )
        {
          v21 &= ~0x20u;
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v46);
        }
        if ( (v21 & 0x10) != 0 )
        {
          v21 &= ~0x10u;
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v47);
        }
        if ( (v21 & 8) != 0 )
        {
          v21 &= ~8u;
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v48);
        }
        if ( (v21 & 4) != 0 )
        {
          v21 &= ~4u;
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v49);
        }
        if ( (v21 & 2) != 0 )
          winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v50);
        v40 = 0;
        LODWORD(pExceptionObject) = 0;
        v55 = 0;
        v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v25 + 56LL))(v25, &v40);
        winrt::check_hresult(&v39, v26, &pExceptionObject);
        v27 = winrt::impl::consume_Windows_Storage_IStorageItem<winrt::Windows::Storage::IStorageFolder>::Path(
                &v40,
                v51);
        winrt::operator+(v42, v27, L"\\InstallServicePlugin.dll");
        winrt::handle_type<winrt::impl::hstring_traits>::close(v51);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&v40);
        v28 = winrt::hstring::c_str((winrt::hstring *)v42);
        LibraryW = LoadLibraryW(v28);
        LODWORD(pExceptionObject) = 0;
        v55 = 0;
        if ( !LibraryW )
          winrt::throw_last_error((winrt *)&pExceptionObject, v30);
        ProcAddress = GetProcAddress(LibraryW, "ActivatePlugin");
        LODWORD(pExceptionObject) = 0;
        v55 = 0;
        if ( !ProcAddress )
          winrt::throw_last_error((winrt *)&pExceptionObject, v31);
        v45 = 0;
        LODWORD(pExceptionObject) = 0;
        v55 = 0;
        v33 = winrt::put_abi((winrt *)&v45, (struct IUnknown *)v31);
        v34 = ((__int64 (__fastcall *)(void **))ProcAddress)(v33);
        winrt::check_hresult(&v39, v34, &pExceptionObject);
        PluginHelpers::TryRegisterPlugin((PluginHelpers *)&v38, v35);
        winrt::Windows::Foundation::IUnknown::as<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>(
          &v45,
          a1);
        if ( v45 )
          winrt::com_ptr<winrt::impl::IBufferByteAccess>::unconditional_release_ref(&v45);
        winrt::handle_type<winrt::impl::hstring_traits>::close(v42);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&iid);
        winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(&ppv);
        Logging::ActivityScope<std::pair<unsigned short const *,winrt::hstring>>::~ActivityScope<std::pair<unsigned short const *,winrt::hstring>>((Logging::Context *)v59);
        PluginHelpers::ResetPluginActivationCount((PluginHelpers *)&v38, v36);
        goto LABEL_38;
      }
      winrt::param::hstring::hstring(
        (winrt::param::hstring *)v58,
        L"Windows.Xbox.System.Internal.Deployment.XVCInstallWorkFactory");
      v16 = winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(v42, v58);
      winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>(
        v16,
        a1);
    }
    winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(v42);
LABEL_38:
    winrt::handle_type<winrt::impl::hstring_traits>::close(&v44);
    goto LABEL_39;
  }
  CreateUWAPlugin(a1);
LABEL_39:
  winrt::handle_type<winrt::impl::hstring_traits>::close(&v38);
  return a1;
}

```

## disassembly

```asm
0x1801b1eb0  mov     [rsp-8+arg_8], rbx
0x1801b1eb5  mov     [rsp-8+arg_18], rsi
0x1801b1eba  push    rbp
0x1801b1ebb  push    rdi
0x1801b1ebc  push    r14
0x1801b1ebe  lea     rbp, [rsp-140h]
0x1801b1ec6  sub     rsp, 240h
0x1801b1ecd  mov     rax, cs:__security_cookie
0x1801b1ed4  xor     rax, rsp
0x1801b1ed7  mov     [rbp+150h+var_20], rax
0x1801b1ede  mov     rsi, rdx
0x1801b1ee1  mov     rdi, rcx
0x1801b1ee4  mov     qword ptr [rbp+150h+iid.Data1], rcx
0x1801b1ee8  xor     r14d, r14d
0x1801b1eeb  mov     [rsp+250h+var_1E8], r14d
0x1801b1ef0  mov     rdx, r8; struct winrt::hstring *
0x1801b1ef3  lea     rcx, [rsp+250h+var_210]; this
0x1801b1ef8  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801b1efd  nop
0x1801b1efe  lea     rdx, aMicrosoftGamin; "Microsoft.GamingServices_8wekyb3d8bbwe"
0x1801b1f05  lea     rcx, [rsp+250h+var_210]
0x1801b1f0a  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801b1f0f  test    al, al
0x1801b1f11  jnz     short loc_1801B1F2C
0x1801b1f13  lea     rdx, aChainedwork; "ChainedWork"
0x1801b1f1a  lea     rcx, [rsp+250h+var_210]
0x1801b1f1f  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801b1f24  test    al, al
0x1801b1f26  jz      loc_1801B1FF8
0x1801b1f2c  xor     r9d, r9d; Context
0x1801b1f2f  xor     r8d, r8d; Parameter
0x1801b1f32  lea     rdx, InitializeInstallServiceConfiguration; InitFn
0x1801b1f39  lea     rcx, InitOnce; InitOnce
0x1801b1f40  call    cs:__imp_InitOnceExecuteOnce
0x1801b1f46  cmp     cs:dword_1802E4F64, r14d
0x1801b1f4d  jz      loc_1801B1FF8
0x1801b1f53  call    ?GetMsixvcArmSupportEnabledFromOneSettings@@YA_NXZ; GetMsixvcArmSupportEnabledFromOneSettings(void)
0x1801b1f58  test    al, al
0x1801b1f5a  jnz     loc_1801B1FF8
0x1801b1f60  lea     rax, aGamingServiceS; "Gaming service support on ARM is not en"...
0x1801b1f67  mov     qword ptr [rbp+150h+iid.Data1], rax
0x1801b1f6b  mov     qword ptr [rbp+150h+iid.Data4], 3Bh ; ';'
0x1801b1f73  lea     rdx, aPluginhelpersA; "PluginHelpers::ActivatePlugin"
0x1801b1f7a  lea     rcx, [rbp+150h+var_168]
0x1801b1f7e  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801b1f83  nop
0x1801b1f84  lea     rdx, aOnecoreuapEndu_37; "onecoreuap\\enduser\\winstore\\installs"...
0x1801b1f8b  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b1f8f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801b1f94  nop
0x1801b1f95  lea     rax, [rbp+150h+iid]
0x1801b1f99  mov     [rsp+250h+ppv], rax
0x1801b1f9e  mov     r9d, 3
0x1801b1fa4  lea     r8, [rbp+150h+var_168]
0x1801b1fa8  lea     edx, [r9+34h]
0x1801b1fac  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b1fb0  call    ??$Log@$$V@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@@Z; Logging::Log<>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &)
0x1801b1fb5  nop
0x1801b1fb6  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b1fba  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801b1fbf  nop
0x1801b1fc0  lea     rcx, [rbp+150h+var_168]
0x1801b1fc4  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801b1fc9  mov     dword ptr [rbp+150h+var_168], r14d
0x1801b1fcd  xorps   xmm0, xmm0
0x1801b1fd0  movdqu  [rbp+150h+var_160], xmm0
0x1801b1fd5  lea     r8, [rbp+150h+var_168]
0x1801b1fd9  mov     edx, 0C03FB013h
0x1801b1fde  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b1fe2  call    ??0hresult_error@winrt@@QEAA@Uhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_error::hresult_error(winrt::hresult,winrt::impl::slim_source_location const &)
0x1801b1fe7  lea     rdx, _TI1?AUhresult_error@winrt@@; pThrowInfo
0x1801b1fee  lea     rcx, [rbp+150h+pExceptionObject]; pExceptionObject
0x1801b1ff2  call    _CxxThrowException_0
0x1801b1ff8  lea     rdx, aWu; "WU"
0x1801b1fff  lea     rcx, [rsp+250h+var_210]
0x1801b2004  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801b2009  test    al, al
0x1801b200b  jz      short loc_1801B201A
0x1801b200d  mov     rcx, rdi
0x1801b2010  call    ?CreateUWAPlugin@@YA?AUIInstallServicePlugin@Plugin@InstallService@Internal@Windows@winrt@@XZ; CreateUWAPlugin(void)
0x1801b2015  jmp     loc_1801B2532
0x1801b201a  lea     rdx, aChainedwork; "ChainedWork"
0x1801b2021  lea     rcx, [rsp+250h+var_210]
0x1801b2026  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801b202b  test    al, al
0x1801b202d  jz      short loc_1801B2077
0x1801b202f  mov     ecx, 18h; Size
0x1801b2034  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801b2039  mov     r9, rax
0x1801b203c  xorps   xmm0, xmm0
0x1801b203f  xor     eax, eax
0x1801b2041  movups  xmmword ptr [r9], xmm0
0x1801b2045  mov     [r9+10h], rax
0x1801b2049  lea     r8, [r9+10h]
0x1801b204d  mov     rcx, r8
0x1801b2050  call    ??0?$producers_base@UChainedWorkPlugin@@V?$tuple@UIInstallServicePlugin@Plugin@InstallService@Internal@Windows@winrt@@@std@@@impl@winrt@@QEAA@XZ; winrt::impl::producers_base<ChainedWorkPlugin,std::tuple<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>>::producers_base<ChainedWorkPlugin,std::tuple<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>>(void)
0x1801b2055  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1801b205c  lea     rcx, [r9+8]
0x1801b2060  call    ??0?$atomic@_K@std@@QEAA@_K@Z; std::atomic<unsigned __int64>::atomic<unsigned __int64>(unsigned __int64)
0x1801b2065  lea     rcx, ??_7?$heap_implements@UChainedWorkPlugin@@@impl@winrt@@6B@; const winrt::impl::heap_implements<ChainedWorkPlugin>::`vftable'
0x1801b206c  mov     [r9], rcx
0x1801b206f  mov     [rdi], r8
0x1801b2072  jmp     loc_1801B2532
0x1801b2077  lea     rdx, [rsp+250h+var_210]
0x1801b207c  lea     rcx, [rsp+250h+var_1E0]
0x1801b2081  call    ?GetPluginFromStaticMap@PluginHelpers@@YA?AUhstring@winrt@@AEBU23@@Z; PluginHelpers::GetPluginFromStaticMap(winrt::hstring const &)
0x1801b2086  nop
0x1801b2087  cmp     [rsp+250h+var_1E0], r14
0x1801b208c  jz      loc_1801B2180
0x1801b2092  xorps   xmm0, xmm0
0x1801b2095  movups  xmmword ptr [rbp+150h+iid.Data1], xmm0
0x1801b2099  lea     rcx, [rsp+250h+var_1E0]; this
0x1801b209e  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801b20a3  mov     rcx, rax; lpsz
0x1801b20a6  lea     rdx, [rbp+150h+iid]; lpiid
0x1801b20aa  call    cs:__imp_IIDFromString
0x1801b20b0  test    eax, eax
0x1801b20b2  js      loc_1801B2140
0x1801b20b8  mov     [rsp+250h+var_1F8], r14
0x1801b20bd  mov     dword ptr [rbp+150h+var_168], r14d
0x1801b20c1  xorps   xmm0, xmm0
0x1801b20c4  movdqu  [rbp+150h+var_160], xmm0
0x1801b20c9  lea     rax, [rsp+250h+var_1F8]
0x1801b20ce  mov     [rsp+250h+ppv], rax; ppv
0x1801b20d3  lea     r9, _GUID_42dfa3dd_f369_478e_b764_0079881e8d8d; riid
0x1801b20da  xor     edx, edx; pUnkOuter
0x1801b20dc  lea     r8d, [rdx+1]; dwClsContext
0x1801b20e0  lea     rcx, [rbp+150h+iid]; rclsid
0x1801b20e4  call    cs:__imp_CoCreateInstance
0x1801b20ea  lea     r8, [rbp+150h+var_168]
0x1801b20ee  mov     edx, eax
0x1801b20f0  lea     rcx, [rsp+250h+var_208]
0x1801b20f5  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1801b20fa  mov     [rsp+250h+var_200], r14
0x1801b20ff  mov     rdx, [rsp+250h+var_1F8]; struct IUnknown *
0x1801b2104  lea     rcx, [rsp+250h+var_200]; this
0x1801b2109  call    ?copy_from_abi@winrt@@YAXAEAUIUnknown@Foundation@Windows@1@PEAX@Z; winrt::copy_from_abi(winrt::Windows::Foundation::IUnknown &,void *)
0x1801b210e  mov     rax, [rsp+250h+var_200]
0x1801b2113  mov     [rsp+250h+var_200], r14
0x1801b2118  mov     [rdi], rax
0x1801b211b  lea     rcx, [rsp+250h+var_200]; void *
0x1801b2120  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b2125  nop
0x1801b2126  cmp     [rsp+250h+var_1F8], r14
0x1801b212b  jz      loc_1801B2527
0x1801b2131  lea     rcx, [rsp+250h+var_1F8]
0x1801b2136  call    ?unconditional_release_ref@?$com_ptr@UIInspectable@@@winrt@@AEAAXXZ; winrt::com_ptr<IInspectable>::unconditional_release_ref(void)
0x1801b213b  jmp     loc_1801B2527
0x1801b2140  lea     rcx, [rsp+250h+var_1E0]; this
0x1801b2145  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801b214a  mov     rdx, rax; unsigned __int16 *
0x1801b214d  lea     rcx, [rbp+150h+var_148]; this
0x1801b2151  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801b2156  lea     rdx, [rbp+150h+var_148]
0x1801b215a  lea     rcx, [rsp+250h+var_1F0]
0x1801b215f  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x1801b2164  nop
0x1801b2165  mov     rdx, rdi
0x1801b2168  mov     rcx, rax
0x1801b216b  call    ??$ActivateInstance@UIInstallServicePlugin@Plugin@InstallService@Internal@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUIInstallServicePlugin@Plugin@InstallService@Internal@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>(void)
0x1801b2170  nop
0x1801b2171  lea     rcx, [rsp+250h+var_1F0]; void *
0x1801b2176  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b217b  jmp     loc_1801B2527
0x1801b2180  lea     rdx, aXvc; "XVC"
0x1801b2187  lea     rcx, [rsp+250h+var_210]
0x1801b218c  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801b2191  test    al, al
0x1801b2193  jz      short loc_1801B21C2
0x1801b2195  lea     rdx, aWindowsXboxSys; "Windows.Xbox.System.Internal.Deployment"...
0x1801b219c  lea     rcx, [rbp+150h+var_148]; this
0x1801b21a0  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801b21a5  lea     rdx, [rbp+150h+var_148]
0x1801b21a9  lea     rcx, [rsp+250h+var_1F0]
0x1801b21ae  call    ??$get_activation_factory@UIActivationFactory@Foundation@Windows@winrt@@@winrt@@YA?AUIActivationFactory@Foundation@Windows@0@AEBUhstring@param@0@@Z; winrt::get_activation_factory<winrt::Windows::Foundation::IActivationFactory>(winrt::param::hstring const &)
0x1801b21b3  nop
0x1801b21b4  mov     rdx, rdi
0x1801b21b7  mov     rcx, rax
0x1801b21ba  call    ??$ActivateInstance@UIInstallServicePlugin@Plugin@InstallService@Internal@Windows@winrt@@@IActivationFactory@Foundation@Windows@winrt@@QEBA?AUIInstallServicePlugin@Plugin@InstallService@Internal@23@XZ; winrt::Windows::Foundation::IActivationFactory::ActivateInstance<winrt::Windows::Internal::InstallService::Plugin::IInstallServicePlugin>(void)
0x1801b21bf  nop
0x1801b21c0  jmp     short loc_1801B2171
0x1801b21c2  lea     rcx, [rsp+250h+var_210]; this
0x1801b21c7  call    ?IncrementPluginActivationCount@PluginHelpers@@YAXAEBUhstring@winrt@@@Z; PluginHelpers::IncrementPluginActivationCount(winrt::hstring const &)
0x1801b21cc  lea     rax, [rsp+250h+var_210]
0x1801b21d1  mov     [rbp+150h+var_168], rax
0x1801b21d5  mov     byte ptr [rbp+150h+var_160], 1
0x1801b21d9  lea     r8, [rsp+250h+var_210]
0x1801b21de  lea     rdx, aPluginid_0; "PluginId"
0x1801b21e5  lea     rcx, [rbp+150h+var_1A8]
0x1801b21e9  call    ??$make_pair@AEAY08$$CBGAEAUhstring@winrt@@@std@@YA?AU?$pair@PEBGUhstring@winrt@@@0@AEAY08$$CBGAEAUhstring@winrt@@@Z; std::make_pair<ushort const (&)[9],winrt::hstring &>(ushort const (&)[9],winrt::hstring &)
0x1801b21ee  mov     rbx, rax
0x1801b21f1  lea     rax, aAttemptingToFi; "Attempting to find plugin "
0x1801b21f8  mov     qword ptr [rbp+150h+iid.Data1], rax
0x1801b21fc  mov     qword ptr [rbp+150h+iid.Data4], 1Ah
0x1801b2204  lea     rdx, aPluginhelpersA; "PluginHelpers::ActivatePlugin"
0x1801b220b  lea     rcx, [rbp+150h+var_148]
0x1801b220f  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801b2214  nop
0x1801b2215  lea     rdx, aOnecoreuapEndu_37; "onecoreuap\\enduser\\winstore\\installs"...
0x1801b221c  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b2220  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801b2225  nop
0x1801b2226  mov     [rsp+250h+var_220], rbx
0x1801b222b  lea     rax, [rbp+150h+iid]
0x1801b222f  mov     [rsp+250h+var_228], rax
0x1801b2234  mov     dword ptr [rsp+250h+ppv], 3
0x1801b223c  lea     r9, [rbp+150h+var_148]
0x1801b2240  mov     r8d, 6Ah ; 'j'
0x1801b2246  lea     rdx, [rbp+150h+pExceptionObject]
0x1801b224a  lea     rcx, [rbp+150h+var_120]
0x1801b224e  call    Logging__TraceActivity_std__pair_unsigned_short_const___winrt__hstring___
0x1801b2253  nop
0x1801b2254  lea     rcx, [rbp+150h+pExceptionObject]
0x1801b2258  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801b225d  nop
0x1801b225e  lea     rcx, [rbp+150h+var_148]
0x1801b2262  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801b2267  nop
0x1801b2268  lea     rcx, [rbp+150h+var_1A0]
0x1801b226c  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801b2271  lea     rcx, [rsp+250h+var_200]; this
0x1801b2276  call    ??0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)
0x1801b227b  nop
0x1801b227c  mov     [rsp+250h+var_208], 1
0x1801b2284  mov     rcx, [rsp+250h+var_210]
0x1801b2289  mov     [rbp+150h+var_148], rcx
0x1801b228d  mov     rcx, [rsi]
0x1801b2290  mov     [rbp+150h+pExceptionObject], rcx
0x1801b2294  lea     rcx, [rsp+250h+var_208]
0x1801b2299  mov     [rsp+250h+ppv], rcx
0x1801b229e  lea     r9, [rbp+150h+var_148]
0x1801b22a2  lea     r8, [rbp+150h+pExceptionObject]
0x1801b22a6  lea     rdx, [rsp+250h+var_1F0]
0x1801b22ab  mov     rcx, rax
0x1801b22ae  call    ?FindPackagesForUserWithPackageTypes@?$consume_Windows_Management_Deployment_IPackageManager2@UPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0AEBW4PackageTypes@Deployment@Management@Windows@3@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager2<winrt::Windows::Management::Deployment::PackageManager>::FindPackagesForUserWithPackageTypes(winrt::param::hstring const &,winrt::param::hstring const &,winrt::Windows::Management::Deployment::PackageTypes const &)
0x1801b22b3  nop
0x1801b22b4  lea     rdx, [rsp+250h+var_1F8]
0x1801b22b9  mov     rcx, rax
0x1801b22bc  call    ?OemId@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo@UIOEMHardwareInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(void)
0x1801b22c1  nop
0x1801b22c2  lea     rcx, [rsp+250h+var_1F0]; void *
0x1801b22c7  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b22cc  nop
0x1801b22cd  lea     rcx, [rsp+250h+var_200]; void *
0x1801b22d2  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b22d7  lea     rcx, [rsp+250h+var_1F8]
0x1801b22dc  call    ?IsInteractive@?$consume_Windows_Internal_InstallService_Plugin_IInstallServiceScanForUpdateProperties@UIInstallServiceScanForUpdateProperties@Plugin@InstallService@Internal@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Internal_InstallService_Plugin_IInstallServiceScanForUpdateProperties<winrt::Windows::Internal::InstallService::Plugin::IInstallServiceScanForUpdateProperties>::IsInteractive(void)
0x1801b22e1  test    al, al
0x1801b22e3  jz      short loc_1801B22FB
0x1801b22e5  lea     rdx, [rbp+150h+var_1B0]
0x1801b22e9  lea     rcx, [rsp+250h+var_1F8]
0x1801b22ee  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UPackage@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::StateRepository::Package>,winrt::Windows::Internal::StateRepository::Package>::Current(void)
0x1801b22f3  nop
0x1801b22f4  mov     ebx, 2
0x1801b22f9  jmp     short loc_1801B2362
0x1801b22fb  lea     rcx, [rbp+150h+var_1B8]; this
0x1801b22ff  call    ??0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)
0x1801b2304  nop
0x1801b2305  mov     [rsp+250h+var_1E8], 4
0x1801b230d  mov     [rsp+250h+var_208], 1
0x1801b2315  mov     rcx, [rsp+250h+var_210]
0x1801b231a  mov     [rbp+150h+var_148], rcx
0x1801b231e  lea     r9, [rsp+250h+var_208]
0x1801b2323  lea     r8, [rbp+150h+var_148]
0x1801b2327  lea     rdx, [rbp+150h+var_1C0]
0x1801b232b  mov     rcx, rax
0x1801b232e  call    ?FindPackagesWithPackageTypes@?$consume_Windows_Management_Deployment_IPackageManager2@UPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@AEBW4PackageTypes@Deployment@Management@Windows@3@@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager2<winrt::Windows::Management::Deployment::PackageManager>::FindPackagesWithPackageTypes(winrt::param::hstring const &,winrt::Windows::Management::Deployment::PackageTypes const &)
0x1801b2333  nop
0x1801b2334  mov     [rsp+250h+var_1E8], 0Ch
0x1801b233c  lea     rdx, [rbp+150h+var_1C8]
0x1801b2340  mov     rcx, rax
0x1801b2343  call    ?OemId@?$consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo@UIOEMHardwareInfo@Internal@InstallControl@Preview@Store@ApplicationModel@Windows@winrt@@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_ApplicationModel_Store_Preview_InstallControl_Internal_IOEMHardwareInfo<winrt::Windows::ApplicationModel::Store::Preview::InstallControl::Internal::IOEMHardwareInfo>::OemId(void)
0x1801b2348  nop
0x1801b2349  mov     [rsp+250h+var_1E8], 1Ch
0x1801b2351  lea     rdx, [rbp+150h+var_1D0]
0x1801b2355  mov     rcx, rax
0x1801b2358  call    ?Current@?$consume_Windows_Foundation_Collections_IIterator@U?$IIterator@UPackage@StateRepository@Internal@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@StateRepository@Internal@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterator<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Internal::StateRepository::Package>,winrt::Windows::Internal::StateRepository::Package>::Current(void)
0x1801b235d  mov     ebx, 3Ch ; '<'
0x1801b2362  mov     rsi, [rax]
0x1801b2365  mov     [rax], r14
0x1801b2368  mov     qword ptr [rbp+150h+iid.Data1], rsi
0x1801b236c  test    bl, 20h
0x1801b236f  jz      short loc_1801B237E
0x1801b2371  and     ebx, 0FFFFFFDFh
0x1801b2374  lea     rcx, [rbp+150h+var_1D0]; void *
0x1801b2378  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b237d  nop
0x1801b237e  test    bl, 10h
0x1801b2381  jz      short loc_1801B2390
0x1801b2383  and     ebx, 0FFFFFFEFh
0x1801b2386  lea     rcx, [rbp+150h+var_1C8]; void *
0x1801b238a  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b238f  nop
0x1801b2390  test    bl, 8
0x1801b2393  jz      short loc_1801B23A2
0x1801b2395  and     ebx, 0FFFFFFF7h
0x1801b2398  lea     rcx, [rbp+150h+var_1C0]; void *
0x1801b239c  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801b23a1  nop
0x1801b23a2  test    bl, 4
  ... truncated ...
```
