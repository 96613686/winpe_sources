# Windows::Networking::UX::NetworkUXManager::GetAdapter(_GUID,Windows::Networking::UX::IAdapter * *)

- ea: `0x18002b210`
- end: `0x18002b8e9`
- name: `?GetAdapter@NetworkUXManager@UX@Networking@Windows@@UEAAJU_GUID@@PEAPEAUIAdapter@234@@Z`
- size: `1753`
- prototype: `int(Windows::Networking::UX::NetworkUXManager *__hidden this, struct _GUID *__struct_ptr, struct Windows::Networking::UX::IAdapter **)`
- caller_count: `0`
- callee_count: `14`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002520`
- `0x18000955c`
- `0x18000c78c`
- `0x18000e768`
- `0x18000f054`
- `0x18000f0b0`
- `0x18000f108`
- `0x180021ed0`
- `0x180023d1c`
- `0x180028524`
- `0x18002b210`
- `0x180035dc0`
- `0x180037bc8`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b3ac`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18002b3ac`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b2a2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002b2a2`
- `RPCRT4!UuidToStringW` at `0x18002b409`
- `RPCRT4!UuidToStringW` at `0x18002b409`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall Windows::Networking::UX::NetworkUXManager::GetAdapter(
        Windows::Networking::UX::NetworkUXManager *this,
        struct _GUID *a2,
        struct Windows::Networking::UX::IAdapter **a3)
{
  HRESULT v5; // eax
  unsigned int v6; // ebx
  LPVOID v8; // rdi
  __int64 (__fastcall *v9)(LPVOID, __int64, _QWORD, _QWORD); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  HRESULT v12; // eax
  unsigned int v13; // ebx
  RPC_STATUS v14; // ebx
  int v15; // ebx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rax
  IUnknown *v19; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  int v21; // eax
  unsigned int v22; // ebx
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, __int64, __int64, __int64 *); // rbx
  int v25; // eax
  unsigned int v26; // ebx
  int v27; // eax
  unsigned int v28; // ebx
  struct Windows::Networking::UX::IAdapter *v29; // rcx
  int ppv; // [rsp+20h] [rbp-C8h]
  int ppva; // [rsp+20h] [rbp-C8h]
  IUnknown *pProxy; // [rsp+50h] [rbp-98h] BYREF
  LPVOID v33; // [rsp+58h] [rbp-90h] BYREF
  int v34; // [rsp+60h] [rbp-88h] BYREF
  __int64 v35; // [rsp+68h] [rbp-80h] BYREF
  __int64 v36; // [rsp+70h] [rbp-78h] BYREF
  RPC_WSTR StringUuid; // [rsp+78h] [rbp-70h] BYREF
  __int64 v38; // [rsp+80h] [rbp-68h] BYREF
  __int64 v39; // [rsp+88h] [rbp-60h] BYREF
  __int64 v40; // [rsp+90h] [rbp-58h] BYREF
  struct Windows::Networking::UX::IAdapter *v41; // [rsp+98h] [rbp-50h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-48h] BYREF
  _BYTE v43[32]; // [rsp+A8h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_5fed7179ccee37279b073b10dffdff26_Traceguids, a2);
  *a3 = 0;
  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &GUID_dc12a687_737f_11cf_884d_00aa004b2e24, &v33);
  v6 = v5;
  if ( v5 >= 0 )
  {
    pProxy = 0;
    wil::make_bstr(&v35, L"root\\StandardCimv2");
    v8 = v33;
    v9 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD))(*(_QWORD *)v33 + 24LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
    v10 = v9(v8, v35, 0, 0);
    v11 = v10;
    if ( v10 >= 0 )
    {
      v12 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
      v13 = v12;
      if ( v12 >= 0 )
      {
        StringUuid = 0;
        v14 = UuidToStringW(a2, &StringUuid);
        if ( v14 )
        {
          v15 = v14 | 0x10000000;
          if ( v15 < 0 )
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x415,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
              (const char *)(unsigned int)v15,
              ppva);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          return (unsigned int)v15;
        }
        else
        {
          std::wstring::wstring(v43);
          std::wstring::append(v43, StringUuid);
          std::wstring::append(v43, L"}'");
          wil::make_bstr(&v40, L"WQL");
          v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43, v16, v17);
          wil::make_bstr(&v39, v18);
          v36 = 0;
          v19 = pProxy;
          Release = pProxy->lpVtbl[6].Release;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
          v21 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64))Release)(v19, v40, v39, 48);
          v22 = v21;
          if ( v21 >= 0 )
          {
            v34 = 0;
            v38 = 0;
            v23 = v36;
            v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v36 + 32LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
            v25 = v24(v23, 0xFFFFFFFFLL, 1, &v38);
            v26 = v25;
            if ( v25 >= 0 )
            {
              if ( v34 )
              {
                v41 = 0;
                v42 = v38;
                v27 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Networking::UX::Internal::CAdapter,Windows::Networking::UX::IAdapter,IWbemClassObject *>(
                        (__int64)&v41,
                        (__int64)&v42);
                v28 = v27;
                if ( v27 >= 0 )
                {
                  v29 = v41;
                  if ( v41 )
                  {
                    (*(void (__fastcall **)(struct Windows::Networking::UX::IAdapter *))(*(_QWORD *)v41 + 8LL))(v41);
                    v29 = v41;
                  }
                  *a3 = v29;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                  std::wstring::_Tidy_deallocate(v43);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                  return 0;
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x42A,
                    (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                    (const char *)(unsigned int)v27,
                    (int)&v34);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                  std::wstring::_Tidy_deallocate(v43);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
                  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                  return v28;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x427,
                  (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                  (const char *)0x80070490LL,
                  (int)&v34);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
                std::wstring::_Tidy_deallocate(v43);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                return 2147943568LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x425,
                (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
                (const char *)(unsigned int)v25,
                (int)&v34);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
              std::wstring::_Tidy_deallocate(v43);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
              return v26;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x420,
              (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
              (const char *)(unsigned int)v21,
              0);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v39);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v40);
            std::wstring::_Tidy_deallocate(v43);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void wil::details::WpRpcStringFree(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringUuid);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            return v22;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x411,
          (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
          (const char *)(unsigned int)v12,
          ppva);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
        return v13;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x405,
        (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
        (const char *)(unsigned int)v10,
        0);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v35);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pProxy);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F7,
      (unsigned int)"onecoreuap\\net\\ux\\uxmanager\\lib\\networkuxmanager.cpp",
      (const char *)(unsigned int)v5,
      ppv);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    return v6;
  }
}

```

## disassembly

```asm
0x18002b210  mov     [rsp+arg_0], rbx
0x18002b215  mov     [rsp+arg_18], rsi
0x18002b21a  push    rdi
0x18002b21b  push    r14
0x18002b21d  push    r15
0x18002b21f  sub     rsp, 0D0h
0x18002b226  mov     rax, cs:__security_cookie
0x18002b22d  xor     rax, rsp
0x18002b230  mov     [rsp+0E8h+var_20], rax
0x18002b238  mov     r14, r8
0x18002b23b  mov     rsi, rdx
0x18002b23e  lea     rax, WPP_GLOBAL_Control
0x18002b245  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b24c  cmp     rcx, rax
0x18002b24f  jz      short loc_18002B26F
0x18002b251  test    byte ptr [rcx+1Ch], 8
0x18002b255  jz      short loc_18002B26F
0x18002b257  mov     edx, 34h ; '4'
0x18002b25c  mov     r9, rsi
0x18002b25f  lea     r8, WPP_5fed7179ccee37279b073b10dffdff26_Traceguids
0x18002b266  mov     rcx, [rcx+10h]
0x18002b26a  call    WPP_SF__guid_
0x18002b26f  xor     r15d, r15d
0x18002b272  mov     [r14], r15
0x18002b275  mov     [rsp+0E8h+var_90], r15
0x18002b27a  lea     rcx, [rsp+0E8h+var_90]
0x18002b27f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b284  lea     rax, [rsp+0E8h+var_90]
0x18002b289  mov     [rsp+0E8h+ppv], rax; int
0x18002b28e  lea     r9, _GUID_dc12a687_737f_11cf_884d_00aa004b2e24; riid
0x18002b295  xor     edx, edx; pUnkOuter
0x18002b297  lea     r8d, [r15+1]; dwClsContext
0x18002b29b  lea     rcx, CLSID_WbemLocator; rclsid
0x18002b2a2  call    cs:__imp_CoCreateInstance
0x18002b2a8  mov     ebx, eax
0x18002b2aa  test    eax, eax
0x18002b2ac  jns     short loc_18002B2DC
0x18002b2ae  mov     rcx, [rsp+0E8h]; this
0x18002b2b6  mov     r9d, eax; char *
0x18002b2b9  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b2c0  mov     edx, 3F7h; void *
0x18002b2c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b2ca  nop
0x18002b2cb  lea     rcx, [rsp+0E8h+var_90]
0x18002b2d0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b2d5  mov     eax, ebx
0x18002b2d7  jmp     loc_18002B8BF
0x18002b2dc  mov     [rsp+0E8h+pProxy], r15
0x18002b2e1  lea     rdx, aRootStandardci; "root\\StandardCimv2"
0x18002b2e8  lea     rcx, [rsp+0E8h+var_80]
0x18002b2ed  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002b2f2  nop
0x18002b2f3  mov     rdi, [rsp+0E8h+var_90]
0x18002b2f8  mov     rax, [rdi]
0x18002b2fb  mov     rbx, [rax+18h]
0x18002b2ff  lea     rcx, [rsp+0E8h+pProxy]
0x18002b304  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b309  lea     rax, [rsp+0E8h+pProxy]
0x18002b30e  mov     [rsp+0E8h+var_A8], rax
0x18002b313  mov     qword ptr [rsp+0E8h+dwCapabilities], r15
0x18002b318  mov     [rsp+0E8h+pAuthInfo], r15
0x18002b31d  mov     [rsp+0E8h+dwImpLevel], r15d
0x18002b322  mov     [rsp+0E8h+ppv], r15; int
0x18002b327  xor     r9d, r9d
0x18002b32a  xor     r8d, r8d
0x18002b32d  mov     rdx, [rsp+0E8h+var_80]
0x18002b332  mov     rcx, rdi
0x18002b335  mov     rax, rbx
0x18002b338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b33d  mov     ebx, eax
0x18002b33f  test    eax, eax
0x18002b341  jns     short loc_18002B387
0x18002b343  mov     rcx, [rsp+0E8h]; this
0x18002b34b  mov     r9d, eax; char *
0x18002b34e  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b355  mov     edx, 405h; void *
0x18002b35a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b35f  nop
0x18002b360  lea     rcx, [rsp+0E8h+var_80]
0x18002b365  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b36a  nop
0x18002b36b  lea     rcx, [rsp+0E8h+pProxy]
0x18002b370  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b375  nop
0x18002b376  lea     rcx, [rsp+0E8h+var_90]
0x18002b37b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b380  mov     eax, ebx
0x18002b382  jmp     loc_18002B8BF
0x18002b387  mov     [rsp+0E8h+dwCapabilities], r15d; dwCapabilities
0x18002b38c  mov     [rsp+0E8h+pAuthInfo], r15; pAuthInfo
0x18002b391  mov     eax, 3
0x18002b396  mov     [rsp+0E8h+dwImpLevel], eax; dwImpLevel
0x18002b39a  mov     dword ptr [rsp+0E8h+ppv], eax; int
0x18002b39e  xor     r9d, r9d; pServerPrincName
0x18002b3a1  xor     r8d, r8d; dwAuthzSvc
0x18002b3a4  lea     edx, [rax+7]; dwAuthnSvc
0x18002b3a7  mov     rcx, [rsp+0E8h+pProxy]; pProxy
0x18002b3ac  call    cs:__imp_CoSetProxyBlanket
0x18002b3b2  mov     ebx, eax
0x18002b3b4  test    eax, eax
0x18002b3b6  jns     short loc_18002B3FC
0x18002b3b8  mov     rcx, [rsp+0E8h]; this
0x18002b3c0  mov     r9d, eax; char *
0x18002b3c3  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b3ca  mov     edx, 411h; void *
0x18002b3cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b3d4  nop
0x18002b3d5  lea     rcx, [rsp+0E8h+var_80]
0x18002b3da  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b3df  nop
0x18002b3e0  lea     rcx, [rsp+0E8h+pProxy]
0x18002b3e5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b3ea  nop
0x18002b3eb  lea     rcx, [rsp+0E8h+var_90]
0x18002b3f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b3f5  mov     eax, ebx
0x18002b3f7  jmp     loc_18002B8BF
0x18002b3fc  mov     [rsp+0E8h+StringUuid], r15
0x18002b401  lea     rdx, [rsp+0E8h+StringUuid]; StringUuid
0x18002b406  mov     rcx, rsi; Uuid
0x18002b409  call    cs:__imp_UuidToStringW
0x18002b40f  mov     ebx, eax
0x18002b411  test    eax, eax
0x18002b413  jz      short loc_18002B46C
0x18002b415  or      ebx, 10000000h
0x18002b41b  jge     short loc_18002B43A
0x18002b41d  mov     rcx, [rsp+0E8h]; this
0x18002b425  mov     r9d, ebx; char *
0x18002b428  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b42f  mov     edx, 415h; void *
0x18002b434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b439  nop
0x18002b43a  lea     rcx, [rsp+0E8h+StringUuid]
0x18002b43f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b444  nop
0x18002b445  lea     rcx, [rsp+0E8h+var_80]
0x18002b44a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b44f  nop
0x18002b450  lea     rcx, [rsp+0E8h+pProxy]
0x18002b455  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b45a  nop
0x18002b45b  lea     rcx, [rsp+0E8h+var_90]
0x18002b460  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b465  mov     eax, ebx
0x18002b467  jmp     loc_18002B8BF
0x18002b46c  lea     rdx, aSelectFromMsft; "SELECT * FROM MSFT_NetAdapter WHERE Int"...
0x18002b473  lea     rcx, [rsp+0E8h+var_40]
0x18002b47b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002b480  nop
0x18002b481  mov     rdx, [rsp+0E8h+StringUuid]
0x18002b486  lea     rcx, [rsp+0E8h+var_40]
0x18002b48e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b493  lea     rdx, asc_180069EFC; "}'"
0x18002b49a  lea     rcx, [rsp+0E8h+var_40]
0x18002b4a2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002b4a7  lea     rdx, aWql; "WQL"
0x18002b4ae  lea     rcx, [rsp+0E8h+var_58]
0x18002b4b6  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002b4bb  nop
0x18002b4bc  lea     rcx, [rsp+0E8h+var_40]
0x18002b4c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002b4c9  mov     rdx, rax
0x18002b4cc  lea     rcx, [rsp+0E8h+var_60]
0x18002b4d4  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18002b4d9  nop
0x18002b4da  mov     [rsp+0E8h+var_78], r15
0x18002b4df  mov     rdi, [rsp+0E8h+pProxy]
0x18002b4e4  mov     rax, [rdi]
0x18002b4e7  mov     rbx, [rax+0A0h]
0x18002b4ee  lea     rcx, [rsp+0E8h+var_78]
0x18002b4f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b4f8  lea     rax, [rsp+0E8h+var_78]
0x18002b4fd  mov     qword ptr [rsp+0E8h+dwImpLevel], rax
0x18002b502  mov     [rsp+0E8h+ppv], r15; int
0x18002b507  mov     r9d, 30h ; '0'
0x18002b50d  mov     r8, [rsp+0E8h+var_60]
0x18002b515  mov     rdx, [rsp+0E8h+var_58]
0x18002b51d  mov     rcx, rdi
0x18002b520  mov     rax, rbx
0x18002b523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b528  mov     ebx, eax
0x18002b52a  test    eax, eax
0x18002b52c  jns     loc_18002B5B6
0x18002b532  mov     rcx, [rsp+0E8h]; this
0x18002b53a  mov     r9d, eax; char *
0x18002b53d  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b544  mov     edx, 420h; void *
0x18002b549  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b54e  nop
0x18002b54f  lea     rcx, [rsp+0E8h+var_78]
0x18002b554  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b559  nop
0x18002b55a  lea     rcx, [rsp+0E8h+var_60]
0x18002b562  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b567  nop
0x18002b568  lea     rcx, [rsp+0E8h+var_58]
0x18002b570  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b575  nop
0x18002b576  lea     rcx, [rsp+0E8h+var_40]
0x18002b57e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b583  nop
0x18002b584  lea     rcx, [rsp+0E8h+StringUuid]
0x18002b589  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b58e  nop
0x18002b58f  lea     rcx, [rsp+0E8h+var_80]
0x18002b594  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b599  nop
0x18002b59a  lea     rcx, [rsp+0E8h+pProxy]
0x18002b59f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b5a4  nop
0x18002b5a5  lea     rcx, [rsp+0E8h+var_90]
0x18002b5aa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b5af  mov     eax, ebx
0x18002b5b1  jmp     loc_18002B8BF
0x18002b5b6  mov     [rsp+0E8h+var_88], r15d
0x18002b5bb  mov     [rsp+0E8h+var_68], r15
0x18002b5c3  mov     rdi, [rsp+0E8h+var_78]
0x18002b5c8  mov     rax, [rdi]
0x18002b5cb  mov     rbx, [rax+20h]
0x18002b5cf  lea     rcx, [rsp+0E8h+var_68]
0x18002b5d7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b5dc  lea     rax, [rsp+0E8h+var_88]
0x18002b5e1  mov     [rsp+0E8h+ppv], rax; int
0x18002b5e6  lea     r9, [rsp+0E8h+var_68]
0x18002b5ee  mov     r8d, 1
0x18002b5f4  or      edx, 0FFFFFFFFh
0x18002b5f7  mov     rcx, rdi
0x18002b5fa  mov     rax, rbx
0x18002b5fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b602  mov     ebx, eax
0x18002b604  test    eax, eax
0x18002b606  jns     loc_18002B69E
0x18002b60c  mov     rcx, [rsp+0E8h]; this
0x18002b614  mov     r9d, eax; char *
0x18002b617  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b61e  mov     edx, 425h; void *
0x18002b623  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b628  nop
0x18002b629  lea     rcx, [rsp+0E8h+var_68]
0x18002b631  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b636  nop
0x18002b637  lea     rcx, [rsp+0E8h+var_78]
0x18002b63c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b641  nop
0x18002b642  lea     rcx, [rsp+0E8h+var_60]
0x18002b64a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b64f  nop
0x18002b650  lea     rcx, [rsp+0E8h+var_58]
0x18002b658  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b65d  nop
0x18002b65e  lea     rcx, [rsp+0E8h+var_40]
0x18002b666  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b66b  nop
0x18002b66c  lea     rcx, [rsp+0E8h+StringUuid]
0x18002b671  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b676  nop
0x18002b677  lea     rcx, [rsp+0E8h+var_80]
0x18002b67c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b681  nop
0x18002b682  lea     rcx, [rsp+0E8h+pProxy]
0x18002b687  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b68c  nop
0x18002b68d  lea     rcx, [rsp+0E8h+var_90]
0x18002b692  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b697  mov     eax, ebx
0x18002b699  jmp     loc_18002B8BF
0x18002b69e  cmp     [rsp+0E8h+var_88], r15d
0x18002b6a3  jnz     loc_18002B740
0x18002b6a9  mov     rcx, [rsp+0E8h]; this
0x18002b6b1  mov     ebx, 80070490h
0x18002b6b6  mov     r9d, ebx; char *
0x18002b6b9  lea     r8, aOnecoreuapNetU_5; "onecoreuap\\net\\ux\\uxmanager\\lib\\ne"...
0x18002b6c0  mov     edx, 427h; void *
0x18002b6c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b6ca  nop
0x18002b6cb  lea     rcx, [rsp+0E8h+var_68]
0x18002b6d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6d8  nop
0x18002b6d9  lea     rcx, [rsp+0E8h+var_78]
0x18002b6de  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b6e3  nop
0x18002b6e4  lea     rcx, [rsp+0E8h+var_60]
0x18002b6ec  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b6f1  nop
0x18002b6f2  lea     rcx, [rsp+0E8h+var_58]
0x18002b6fa  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b6ff  nop
0x18002b700  lea     rcx, [rsp+0E8h+var_40]
0x18002b708  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002b70d  nop
0x18002b70e  lea     rcx, [rsp+0E8h+StringUuid]
0x18002b713  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?WpRpcStringFree@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&wil::details::WpRpcStringFree(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b718  nop
0x18002b719  lea     rcx, [rsp+0E8h+var_80]
0x18002b71e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002b723  nop
0x18002b724  lea     rcx, [rsp+0E8h+pProxy]
0x18002b729  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002b72e  nop
0x18002b72f  lea     rcx, [rsp+0E8h+var_90]
  ... truncated ...
```
