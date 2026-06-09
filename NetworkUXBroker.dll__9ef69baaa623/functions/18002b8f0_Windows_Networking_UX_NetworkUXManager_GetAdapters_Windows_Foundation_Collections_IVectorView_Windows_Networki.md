# Windows::Networking::UX::NetworkUXManager::GetAdapters(Windows::Foundation::Collections::IVectorView<Windows::Networking::UX::IAdapter *> * *)

- ea: `0x18002b8f0`
- end: `0x18002c06f`
- name: `?GetAdapters@NetworkUXManager@UX@Networking@Windows@@UEAAJPEAPEAU?$IVectorView@PEAUIAdapter@UX@Networking@Windows@@@Collections@Foundation@4@@Z`
- size: `1919`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x18000955c`
- `0x18000a6e4`
- `0x18000e768`
- `0x180021ed0`
- `0x18002321c`
- `0x180023d1c`
- `0x18002b8f0`
- `0x180035dc0`
- `0x18003cecc`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002bae3`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002bae3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b9bd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b9bd`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::GetAdapters(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 result; // rax
  HRESULT v7; // eax
  unsigned int v8; // ebx
  LPVOID v9; // rdi
  __int64 (__fastcall *v10)(LPVOID, __int64, _QWORD, _QWORD); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  const char *v13; // r9
  HRESULT v14; // eax
  unsigned int v15; // ebx
  IUnknown *v16; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  int v18; // eax
  unsigned int v19; // ebx
  __int64 v20; // rbx
  __int64 (__fastcall *v21)(__int64, __int64, __int64, struct IWbemClassObject **); // rdi
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // ebx
  int IsHidden; // eax
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  int v30; // eax
  unsigned int v31; // ebx
  int ppv; // [rsp+20h] [rbp-88h]
  int ppva; // [rsp+20h] [rbp-88h]
  int ppvb; // [rsp+20h] [rbp-88h]
  int *ppvc; // [rsp+20h] [rbp-88h]
  IUnknown *pProxy; // [rsp+50h] [rbp-58h] BYREF
  LPVOID v37; // [rsp+58h] [rbp-50h] BYREF
  struct IWbemClassObject *v38; // [rsp+60h] [rbp-48h] BYREF
  __int64 v39; // [rsp+68h] [rbp-40h] BYREF
  __int64 v40; // [rsp+70h] [rbp-38h] BYREF
  __int64 v41; // [rsp+78h] [rbp-30h] BYREF
  __int64 v42; // [rsp+80h] [rbp-28h] BYREF
  struct IWbemClassObject *v43; // [rsp+88h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  __int64 v45; // [rsp+B8h] [rbp+10h] BYREF
  int v46; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v47; // [rsp+C8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids);
  *a2 = 0;
  v47 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
  v4 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAdapter,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAdapter *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAdapter *>>>(
         v3,
         &v47);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v37 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
    v7 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v37);
    v8 = v7;
    if ( v7 >= 0 )
    {
      pProxy = 0;
      try
      {
        wil::make_bstr(&v40, L"root\\StandardCimv2");
        v9 = v37;
        v10 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v37 + 24LL);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
        v11 = v10(v9, v40, 0, 0);
        v12 = v11;
        if ( v11 >= 0 )
        {
          v14 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
          v15 = v14;
          if ( v14 >= 0 )
          {
            wil::make_bstr(&v42, L"WQL");
            wil::make_bstr(&v41, L"SELECT * FROM MSFT_NetAdapter");
            v39 = 0;
            v16 = pProxy;
            Release = pProxy->lpVtbl[6].Release;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
            LODWORD(ppvc) = 0;
            v18 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64))Release)(v16, v42, v41, 48);
            v19 = v18;
            if ( v18 >= 0 )
            {
              v46 = 0;
              while ( 1 )
              {
                v20 = v39;
                if ( !v39 )
                  break;
                v38 = 0;
                v21 = *(__int64 (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **))(*(_QWORD *)v39 + 32LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                ppvc = &v46;
                v22 = v21(v20, 0xFFFFFFFFLL, 1, &v38);
                v23 = v22;
                if ( v22 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3D9,
                    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                    (const char *)(unsigned int)v22,
                    (int)&v46);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  result = v23;
                  goto LABEL_37;
                }
                if ( !v46 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  break;
                }
                LOBYTE(v45) = 0;
                IsHidden = Windows::Networking::UX::Internal::CAdapter::IsHidden(v38, (bool *)&v45);
                v27 = IsHidden;
                if ( IsHidden < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x3E1,
                    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                    (const char *)(unsigned int)IsHidden,
                    (int)&v46);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                  result = v27;
                  goto LABEL_37;
                }
                if ( !(_BYTE)v45 )
                {
                  v45 = 0;
                  v43 = v38;
                  v28 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CAdapter,Windows::Networking::UX::IAdapter,IWbemClassObject *>(
                          (__int64)&v45,
                          (__int64)&v43);
                  v29 = v28;
                  if ( v28 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x3E6,
                      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                      (const char *)(unsigned int)v28,
                      (int)&v46);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                    result = v29;
                    goto LABEL_37;
                  }
                  v30 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v47 + 104LL))(v47, v45);
                  v31 = v30;
                  if ( v30 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x3E7,
                      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                      (const char *)(unsigned int)v30,
                      (int)&v46);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                    result = v31;
                    goto LABEL_37;
                  }
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45);
                }
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
              }
              v24 = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v47 + 64LL))(v47, a2);
              v25 = v24;
              if ( v24 >= 0 )
              {
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                result = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x3EB,
                  (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                  (const char *)(unsigned int)v24,
                  (int)ppvc);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
                result = v25;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3D3,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                (const char *)(unsigned int)v18,
                0);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v42);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
              result = v19;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3CD,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
              (const char *)(unsigned int)v14,
              ppvb);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
            result = v15;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3C1,
            (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
            (const char *)(unsigned int)v11,
            0);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
          result = v12;
        }
      }
      catch ( ... )
      {
        result = (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x3EE,
                                 (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                                 v13);
      }
LABEL_37:
      ;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3B3,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
        (const char *)(unsigned int)v7,
        ppva);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
      return v8;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
      (const char *)(unsigned int)v4,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v47);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18002b8f0  mov     [rsp+arg_0], rbx
0x18002b8f5  push    rsi
0x18002b8f6  push    rdi
0x18002b8f7  push    r14
0x18002b8f9  sub     rsp, 90h
0x18002b900  mov     rsi, rdx
0x18002b903  lea     rax, WPP_GLOBAL_Control
0x18002b90a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b911  cmp     rcx, rax
0x18002b914  jz      short loc_18002B931
0x18002b916  test    byte ptr [rcx+1Ch], 8
0x18002b91a  jz      short loc_18002B931
0x18002b91c  mov     edx, 33h ; '3'
0x18002b921  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18002b928  mov     rcx, [rcx+10h]
0x18002b92c  call    WPP_SF_
0x18002b931  xor     r14d, r14d
0x18002b934  mov     [rsi], r14
0x18002b937  mov     [rsp+0A8h+arg_18], r14
0x18002b93f  lea     rcx, [rsp+0A8h+arg_18]
0x18002b947  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b94c  lea     rdx, [rsp+0A8h+arg_18]
0x18002b954  call    ??$CreateExternalObjectVector@UIAdapter@UX@Networking@Windows@@V?$Vector@PEAUIAdapter@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAdapter@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAdapter@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAdapter@UX@Networking@Windows@@@6784@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$Vector@PEAUIAdapter@UX@Networking@Windows@@U?$DefaultEqualityPredicate@PEAUIAdapter@UX@Networking@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAUIAdapter@UX@Networking@Windows@@@6784@U?$DefaultVectorOptions@PEAUIAdapter@UX@Networking@Windows@@@6784@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Networking::UX::IAdapter,Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAdapter *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAdapter *>>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::Vector<Windows::Networking::UX::IAdapter *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Networking::UX::IAdapter *>,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Networking::UX::IAdapter *>> * *)
0x18002b959  mov     ebx, eax
0x18002b95b  test    eax, eax
0x18002b95d  jns     short loc_18002B990
0x18002b95f  mov     rcx, [rsp+0A8h]; this
0x18002b967  mov     r9d, eax; char *
0x18002b96a  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b971  mov     edx, 3B0h; void *
0x18002b976  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b97b  nop
0x18002b97c  lea     rcx, [rsp+0A8h+arg_18]
0x18002b984  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b989  mov     eax, ebx
0x18002b98b  jmp     loc_18002BE11
0x18002b990  mov     [rsp+0A8h+var_50], r14
0x18002b995  lea     rcx, [rsp+0A8h+var_50]
0x18002b99a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b99f  lea     rax, [rsp+0A8h+var_50]
0x18002b9a4  mov     [rsp+0A8h+ppv], rax; int
0x18002b9a9  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18002b9b0  xor     edx, edx; pUnkOuter
0x18002b9b2  lea     r8d, [rdx+1]; dwClsContext
0x18002b9b6  lea     rcx, CLSID_WbemLocator; rclsid
0x18002b9bd  call    cs:__imp_CoCreateInstance
0x18002b9c3  mov     ebx, eax
0x18002b9c5  test    eax, eax
0x18002b9c7  jns     short loc_18002BA05
0x18002b9c9  mov     rcx, [rsp+0A8h]; this
0x18002b9d1  mov     r9d, eax; char *
0x18002b9d4  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b9db  mov     edx, 3B3h; void *
0x18002b9e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b9e5  nop
0x18002b9e6  lea     rcx, [rsp+0A8h+var_50]
0x18002b9eb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b9f0  nop
0x18002b9f1  lea     rcx, [rsp+0A8h+arg_18]
0x18002b9f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b9fe  mov     eax, ebx
0x18002ba00  jmp     loc_18002BE11
0x18002ba05  mov     [rsp+0A8h+pProxy], r14
0x18002ba0a  lea     rdx, aRootStandardci; "root\\StandardCimv2"
0x18002ba11  lea     rcx, [rsp+0A8h+var_38]
0x18002ba16  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002ba1b  nop
0x18002ba1c  mov     rdi, [rsp+0A8h+var_50]
0x18002ba21  mov     rax, [rdi]
0x18002ba24  mov     rbx, [rax+18h]
0x18002ba28  lea     rcx, [rsp+0A8h+pProxy]
0x18002ba2d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba32  lea     rax, [rsp+0A8h+pProxy]
0x18002ba37  mov     [rsp+0A8h+var_68], rax
0x18002ba3c  mov     qword ptr [rsp+0A8h+dwCapabilities], r14
0x18002ba41  mov     [rsp+0A8h+pAuthInfo], r14
0x18002ba46  mov     [rsp+0A8h+dwImpLevel], r14d
0x18002ba4b  mov     [rsp+0A8h+ppv], r14; int
0x18002ba50  xor     r9d, r9d
0x18002ba53  xor     r8d, r8d
0x18002ba56  mov     rdx, [rsp+0A8h+var_38]
0x18002ba5b  mov     rcx, rdi
0x18002ba5e  mov     rax, rbx
0x18002ba61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba66  mov     ebx, eax
0x18002ba68  test    eax, eax
0x18002ba6a  jns     short loc_18002BABE
0x18002ba6c  mov     rcx, [rsp+0A8h]; this
0x18002ba74  mov     r9d, eax; char *
0x18002ba77  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002ba7e  mov     edx, 3C1h; void *
0x18002ba83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ba88  nop
0x18002ba89  lea     rcx, [rsp+0A8h+var_38]
0x18002ba8e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002ba93  nop
0x18002ba94  lea     rcx, [rsp+0A8h+pProxy]
0x18002ba99  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002ba9e  nop
0x18002ba9f  lea     rcx, [rsp+0A8h+var_50]
0x18002baa4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002baa9  nop
0x18002baaa  lea     rcx, [rsp+0A8h+arg_18]
0x18002bab2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bab7  mov     eax, ebx
0x18002bab9  jmp     loc_18002BE11
0x18002babe  mov     [rsp+0A8h+dwCapabilities], r14d; dwCapabilities
0x18002bac3  mov     [rsp+0A8h+pAuthInfo], r14; pAuthInfo
0x18002bac8  mov     eax, 3
0x18002bacd  mov     [rsp+0A8h+dwImpLevel], eax; dwImpLevel
0x18002bad1  mov     dword ptr [rsp+0A8h+ppv], eax; int
0x18002bad5  xor     r9d, r9d; pServerPrincName
0x18002bad8  xor     r8d, r8d; dwAuthzSvc
0x18002badb  lea     edx, [rax+7]; dwAuthnSvc
0x18002bade  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x18002bae3  call    cs:__imp_CoSetProxyBlanket
0x18002bae9  mov     ebx, eax
0x18002baeb  test    eax, eax
0x18002baed  jns     short loc_18002BB41
0x18002baef  mov     rcx, [rsp+0A8h]; this
0x18002baf7  mov     r9d, eax; char *
0x18002bafa  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002bb01  mov     edx, 3CDh; void *
0x18002bb06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bb0b  nop
0x18002bb0c  lea     rcx, [rsp+0A8h+var_38]
0x18002bb11  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bb16  nop
0x18002bb17  lea     rcx, [rsp+0A8h+pProxy]
0x18002bb1c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb21  nop
0x18002bb22  lea     rcx, [rsp+0A8h+var_50]
0x18002bb27  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb2c  nop
0x18002bb2d  lea     rcx, [rsp+0A8h+arg_18]
0x18002bb35  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb3a  mov     eax, ebx
0x18002bb3c  jmp     loc_18002BE11
0x18002bb41  lea     rdx, aWql; "WQL"
0x18002bb48  lea     rcx, [rsp+0A8h+var_28]
0x18002bb50  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002bb55  nop
0x18002bb56  lea     rdx, aSelectFromMsft_0; "SELECT * FROM MSFT_NetAdapter"
0x18002bb5d  lea     rcx, [rsp+0A8h+var_30]
0x18002bb62  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002bb67  nop
0x18002bb68  mov     [rsp+0A8h+var_40], r14
0x18002bb6d  mov     rdi, [rsp+0A8h+pProxy]
0x18002bb72  mov     rax, [rdi]
0x18002bb75  mov     rbx, [rax+0A0h]
0x18002bb7c  lea     rcx, [rsp+0A8h+var_40]
0x18002bb81  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bb86  lea     rax, [rsp+0A8h+var_40]
0x18002bb8b  mov     qword ptr [rsp+0A8h+dwImpLevel], rax
0x18002bb90  mov     [rsp+0A8h+ppv], r14; int
0x18002bb95  mov     r9d, 30h ; '0'
0x18002bb9b  mov     r8, [rsp+0A8h+var_30]
0x18002bba0  mov     rdx, [rsp+0A8h+var_28]
0x18002bba8  mov     rcx, rdi
0x18002bbab  mov     rax, rbx
0x18002bbae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bbb3  mov     ebx, eax
0x18002bbb5  test    eax, eax
0x18002bbb7  jns     short loc_18002BC2F
0x18002bbb9  mov     rcx, [rsp+0A8h]; this
0x18002bbc1  mov     r9d, eax; char *
0x18002bbc4  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002bbcb  mov     edx, 3D3h; void *
0x18002bbd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bbd5  nop
0x18002bbd6  lea     rcx, [rsp+0A8h+var_40]
0x18002bbdb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bbe0  nop
0x18002bbe1  lea     rcx, [rsp+0A8h+var_30]
0x18002bbe6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bbeb  nop
0x18002bbec  lea     rcx, [rsp+0A8h+var_28]
0x18002bbf4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bbf9  nop
0x18002bbfa  lea     rcx, [rsp+0A8h+var_38]
0x18002bbff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bc04  nop
0x18002bc05  lea     rcx, [rsp+0A8h+pProxy]
0x18002bc0a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc0f  nop
0x18002bc10  lea     rcx, [rsp+0A8h+var_50]
0x18002bc15  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc1a  nop
0x18002bc1b  lea     rcx, [rsp+0A8h+arg_18]
0x18002bc23  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc28  mov     eax, ebx
0x18002bc2a  jmp     loc_18002BE11
0x18002bc2f  mov     [rsp+0A8h+arg_10], r14d
0x18002bc37  mov     rbx, [rsp+0A8h+var_40]
0x18002bc3c  test    rbx, rbx
0x18002bc3f  jz      loc_18002BD24
0x18002bc45  mov     [rsp+0A8h+var_48], r14
0x18002bc4a  mov     rax, [rbx]
0x18002bc4d  mov     rdi, [rax+20h]
0x18002bc51  lea     rcx, [rsp+0A8h+var_48]
0x18002bc56  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bc5b  lea     rax, [rsp+0A8h+arg_10]
0x18002bc63  mov     [rsp+0A8h+ppv], rax; int
0x18002bc68  lea     r9, [rsp+0A8h+var_48]
0x18002bc6d  mov     r8d, 1
0x18002bc73  or      edx, 0FFFFFFFFh
0x18002bc76  mov     rcx, rbx
0x18002bc79  mov     rax, rdi
0x18002bc7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc81  mov     ebx, eax
0x18002bc83  test    eax, eax
0x18002bc85  jns     loc_18002BD0C
0x18002bc8b  mov     rcx, [rsp+0A8h]; this
0x18002bc93  mov     r9d, eax; char *
0x18002bc96  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002bc9d  mov     edx, 3D9h; void *
0x18002bca2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bca7  nop
0x18002bca8  lea     rcx, [rsp+0A8h+var_48]
0x18002bcad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bcb2  nop
0x18002bcb3  lea     rcx, [rsp+0A8h+var_40]
0x18002bcb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bcbd  nop
0x18002bcbe  lea     rcx, [rsp+0A8h+var_30]
0x18002bcc3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bcc8  nop
0x18002bcc9  lea     rcx, [rsp+0A8h+var_28]
0x18002bcd1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bcd6  nop
0x18002bcd7  lea     rcx, [rsp+0A8h+var_38]
0x18002bcdc  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bce1  nop
0x18002bce2  lea     rcx, [rsp+0A8h+pProxy]
0x18002bce7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bcec  nop
0x18002bced  lea     rcx, [rsp+0A8h+var_50]
0x18002bcf2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bcf7  nop
0x18002bcf8  lea     rcx, [rsp+0A8h+arg_18]
0x18002bd00  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bd05  mov     eax, ebx
0x18002bd07  jmp     loc_18002BE11
0x18002bd0c  cmp     [rsp+0A8h+arg_10], r14d
0x18002bd14  jnz     loc_18002BE25
0x18002bd1a  lea     rcx, [rsp+0A8h+var_48]
0x18002bd1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bd24  mov     rcx, [rsp+0A8h+arg_18]
0x18002bd2c  mov     rax, [rcx]
0x18002bd2f  mov     rdx, rsi
0x18002bd32  mov     rax, [rax+40h]
0x18002bd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bd3b  mov     ebx, eax
0x18002bd3d  test    eax, eax
0x18002bd3f  jns     short loc_18002BDB4
0x18002bd41  mov     rcx, [rsp+0A8h]; this
0x18002bd49  mov     r9d, eax; char *
0x18002bd4c  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002bd53  mov     edx, 3EBh; void *
0x18002bd58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002bd5d  nop
0x18002bd5e  lea     rcx, [rsp+0A8h+var_40]
0x18002bd63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bd68  nop
0x18002bd69  lea     rcx, [rsp+0A8h+var_30]
0x18002bd6e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bd73  nop
0x18002bd74  lea     rcx, [rsp+0A8h+var_28]
0x18002bd7c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bd81  nop
0x18002bd82  lea     rcx, [rsp+0A8h+var_38]
0x18002bd87  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bd8c  nop
0x18002bd8d  lea     rcx, [rsp+0A8h+pProxy]
0x18002bd92  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bd97  nop
0x18002bd98  lea     rcx, [rsp+0A8h+var_50]
0x18002bd9d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bda2  nop
0x18002bda3  lea     rcx, [rsp+0A8h+arg_18]
0x18002bdab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bdb0  mov     eax, ebx
0x18002bdb2  jmp     short loc_18002BE11
0x18002bdb4  lea     rcx, [rsp+0A8h+var_40]
0x18002bdb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bdbe  nop
0x18002bdbf  lea     rcx, [rsp+0A8h+var_30]
0x18002bdc4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bdc9  nop
0x18002bdca  lea     rcx, [rsp+0A8h+var_28]
0x18002bdd2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bdd7  nop
0x18002bdd8  lea     rcx, [rsp+0A8h+var_38]
0x18002bddd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002bde2  nop
0x18002bde3  lea     rcx, [rsp+0A8h+pProxy]
0x18002bde8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002bded  nop
0x18002bdee  lea     rcx, [rsp+0A8h+var_50]
0x18002bdf3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
