# Windows::Networking::UX::Internal::NlmClient::Start(Windows::Networking::UX::Internal::INlmListener *)

- ea: `0x18001c378`
- end: `0x18001cadc`
- name: `?Start@NlmClient@Internal@UX@Networking@Windows@@QEAAJPEAVINlmListener@2345@@Z`
- size: `1892`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::NlmClient *__hidden this, struct Windows::Networking::UX::Internal::INlmListener *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001c0cc`

## callees

- `0x180002150`
- `0x180005be0`
- `0x180005c80`
- `0x18000653c`
- `0x1800162d8`
- `0x180017fa8`
- `0x18001c378`
- `0x18001caf0`
- `0x18001cb10`
- `0x18001d0a4`
- `0x18001d0d0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3c3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001c3c3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c406`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c4e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c77d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c817`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001caba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c406`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c4e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c57c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c618`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c6e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c77d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c817`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c8b6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001c970`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ca2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001caba`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c71c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c848`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c71c`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18001c848`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c527`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001c527`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001c5c3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001c8fe`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001c5c3`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001c8fe`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Windows::Networking::UX::Internal::NlmClient::Start(
        Windows::Networking::UX::Internal::NlmClient *this,
        struct Windows::Networking::UX::Internal::INlmListener *a2)
{
  __int64 result; // rax
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  const char *v9; // r9
  int v10; // eax
  unsigned int v11; // ebx
  HRESULT v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rax
  _QWORD *v15; // rbx
  LPVOID v16; // rdi
  int AgileReference; // eax
  unsigned int v18; // ebx
  LPVOID v19; // rbx
  __int64 (__fastcall *v20)(LPVOID, GUID *, IUnknown **); // rdi
  int v21; // eax
  unsigned int v22; // ebx
  HRESULT v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  unsigned int v26; // ebx
  HRESULT v27; // eax
  unsigned int v28; // ebx
  _QWORD *v29; // rax
  _QWORD *v30; // rbx
  IUnknown *v31; // rdi
  int v32; // eax
  unsigned int v33; // ebx
  int v34; // eax
  unsigned int v35; // ebx
  int ppv; // [rsp+20h] [rbp-88h]
  int ppva; // [rsp+20h] [rbp-88h]
  int ppvb; // [rsp+20h] [rbp-88h]
  int ppvc; // [rsp+20h] [rbp-88h]
  __int64 v40; // [rsp+40h] [rbp-68h] BYREF
  struct Windows::Networking::UX::Internal::INlmListener *v41; // [rsp+48h] [rbp-60h] BYREF
  IUnknown *v42; // [rsp+50h] [rbp-58h] BYREF
  char *v43; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v44[9]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v46; // [rsp+B0h] [rbp+8h] BYREF
  LPVOID v47; // [rsp+C0h] [rbp+18h] BYREF
  IUnknown *pProxy; // [rsp+C8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v44[1] = (char *)this + 48;
  if ( *((_BYTE *)this + 24) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids);
    if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    return 1;
  }
  try
  {
    v41 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct Windows::Networking::UX::Internal::INlmListener *))(*(_QWORD *)a2 + 8LL))(a2);
    v40 = (__int64)this + 16;
    v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v40);
    v6 = Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::INlmListener>(a2, v5);
    v8 = v6;
    if ( v6 >= 0 )
    {
      v40 = -1;
      v10 = wil::impersonate_token_nothrow(v7, (void **)&v40);
      v11 = v10;
      if ( v10 >= 0 )
      {
        v47 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
        v12 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v47);
        v13 = v12;
        if ( v12 >= 0 )
        {
          v43 = (char *)this + 32;
          v14 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v43);
          v15 = v14;
          v16 = v47;
          if ( v47 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v14);
            AgileReference = RoGetAgileReference(0, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, v16, v15);
            v18 = AgileReference;
            if ( AgileReference < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x30,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                (const char *)(unsigned int)AgileReference,
                ppva);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              return v18;
            }
          }
          else
          {
            v44[0] = 0;
            v43 = (char *)*v14;
            *v14 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
          }
          pProxy = 0;
          v19 = v47;
          v20 = **(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))v47;
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
          v21 = v20(v19, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &pProxy);
          v22 = v21;
          if ( v21 >= 0 )
          {
            v23 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
            v24 = v23;
            if ( v23 >= 0 )
            {
              v42 = 0;
              v25 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
                      pProxy,
                      &GUID_733b7764_5c0c_4ad6_bb4b_d0585e993e0f,
                      &v42);
              v26 = v25;
              if ( v25 >= 0 )
              {
                v27 = CoSetProxyBlanket(v42, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
                v28 = v27;
                if ( v27 >= 0 )
                {
                  v44[0] = (char *)this + 40;
                  v29 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(v44);
                  v30 = v29;
                  v31 = v42;
                  if ( v42 )
                  {
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v29);
                    v32 = RoGetAgileReference(0, &GUID_b196b286_bab4_101a_b69c_00aa00341d07, v31, v30);
                    v33 = v32;
                    if ( v32 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x4B,
                        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                        (const char *)(unsigned int)v32,
                        ppvc);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                      if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                      return v33;
                    }
                  }
                  else
                  {
                    v43 = 0;
                    v44[0] = *v29;
                    *v29 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v44);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v43);
                  }
                  v46 = 0;
                  v34 = ((__int64 (__fastcall *)(IUnknown *, Windows::Networking::UX::Internal::NlmClient *, int *))v42->lpVtbl[1].Release)(
                          v42,
                          this,
                          &v46);
                  v35 = v34;
                  if ( v34 >= 0 )
                  {
                    *((_DWORD *)this + 22) = v46;
                    *((_BYTE *)this + 24) = 1;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids,
                        0);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                    if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x4E,
                      (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                      (const char *)(unsigned int)v34,
                      ppvc);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                    if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                    return v35;
                  }
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x49,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                  (const char *)(unsigned int)v27,
                  ppvc);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                result = v28;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x40,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                  (const char *)(unsigned int)v25,
                  ppvb);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v42);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
                Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
                if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                result = v26;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3C,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                (const char *)(unsigned int)v23,
                ppvb);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
              Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
              if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              result = v24;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x33,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
              (const char *)(unsigned int)v21,
              ppva);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
            if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
            result = v22;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
            (const char *)(unsigned int)v12,
            ppva);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v47);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
          if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
          result = v13;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
          (const char *)(unsigned int)v10,
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v40);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
        if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        result = v11;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x29,
        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
        (const char *)(unsigned int)v6,
        ppv);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v41);
      if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      result = v8;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x18001c378  push    rbx
0x18001c37a  push    rsi
0x18001c37b  push    rdi
0x18001c37c  push    r12
0x18001c37e  push    r13
0x18001c380  push    r14
0x18001c382  push    r15
0x18001c384  sub     rsp, 70h
0x18001c388  mov     rbx, rdx
0x18001c38b  mov     r14, rcx
0x18001c38e  lea     r12, WPP_GLOBAL_Control
0x18001c395  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c39c  cmp     rcx, r12
0x18001c39f  jz      short loc_18001C3BC
0x18001c3a1  test    byte ptr [rcx+1Ch], 40h
0x18001c3a5  jz      short loc_18001C3BC
0x18001c3a7  mov     edx, 0Dh
0x18001c3ac  lea     r8, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids
0x18001c3b3  mov     rcx, [rcx+10h]
0x18001c3b7  call    WPP_SF_
0x18001c3bc  lea     rsi, [r14+30h]
0x18001c3c0  mov     rcx, rsi; lpCriticalSection
0x18001c3c3  call    cs:__imp_EnterCriticalSection
0x18001c3c9  mov     [rsp+0A8h+var_40], rsi
0x18001c3ce  xor     r15d, r15d
0x18001c3d1  cmp     [r14+18h], r15b
0x18001c3d5  jz      short loc_18001C416
0x18001c3d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3de  cmp     rcx, r12
0x18001c3e1  jz      short loc_18001C3FE
0x18001c3e3  test    byte ptr [rcx+1Ch], 4
0x18001c3e7  jz      short loc_18001C3FE
0x18001c3e9  lea     edx, [r15+0Eh]
0x18001c3ed  lea     r8, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids
0x18001c3f4  mov     rcx, [rcx+10h]
0x18001c3f8  call    WPP_SF_
0x18001c3fd  nop
0x18001c3fe  test    rsi, rsi
0x18001c401  jz      short loc_18001C40C
0x18001c403  mov     rcx, rsi; lpCriticalSection
0x18001c406  call    cs:__imp_LeaveCriticalSection
0x18001c40c  mov     eax, 1
0x18001c411  jmp     loc_18001CACB
0x18001c416  mov     [rsp+0A8h+var_60], rbx
0x18001c41b  test    rbx, rbx
0x18001c41e  jz      short loc_18001C430
0x18001c420  mov     rax, [rbx]
0x18001c423  mov     rcx, rbx
0x18001c426  mov     rax, [rax+8]
0x18001c42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c42f  nop
0x18001c430  lea     rax, [r14+10h]
0x18001c434  mov     [rsp+0A8h+var_68], rax
0x18001c439  lea     rcx, [rsp+0A8h+var_68]
0x18001c43e  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18001c443  mov     rdx, rax
0x18001c446  mov     rcx, rbx
0x18001c449  call    ??$AsWeak@VINlmListener@Internal@UX@Networking@Windows@@@WRL@Microsoft@@YAJPEAVINlmListener@Internal@UX@Networking@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::INlmListener>(Windows::Networking::UX::Internal::INlmListener *,Microsoft::WRL::WeakRef *)
0x18001c44e  mov     ebx, eax
0x18001c450  test    eax, eax
0x18001c452  jns     short loc_18001C491
0x18001c454  mov     rcx, [rsp+0A8h]; this
0x18001c45c  mov     r9d, eax; char *
0x18001c45f  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c466  mov     edx, 29h ; ')'; void *
0x18001c46b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c470  nop
0x18001c471  lea     rcx, [rsp+0A8h+var_60]
0x18001c476  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c47b  nop
0x18001c47c  test    rsi, rsi
0x18001c47f  jz      short loc_18001C48A
0x18001c481  mov     rcx, rsi; lpCriticalSection
0x18001c484  call    cs:__imp_LeaveCriticalSection
0x18001c48a  mov     eax, ebx
0x18001c48c  jmp     loc_18001CACB
0x18001c491  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001c495  mov     [rsp+0A8h+var_68], r13
0x18001c49a  lea     rdx, [rsp+0A8h+var_68]
0x18001c49f  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18001c4a4  mov     ebx, eax
0x18001c4a6  test    eax, eax
0x18001c4a8  jns     short loc_18001C4F1
0x18001c4aa  mov     rcx, [rsp+0A8h]; this
0x18001c4b2  mov     r9d, eax; char *
0x18001c4b5  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c4bc  lea     edx, [r13+2Dh]; void *
0x18001c4c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c4c5  nop
0x18001c4c6  lea     rcx, [rsp+0A8h+var_68]
0x18001c4cb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c4d0  nop
0x18001c4d1  lea     rcx, [rsp+0A8h+var_60]
0x18001c4d6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c4db  nop
0x18001c4dc  test    rsi, rsi
0x18001c4df  jz      short loc_18001C4EA
0x18001c4e1  mov     rcx, rsi; lpCriticalSection
0x18001c4e4  call    cs:__imp_LeaveCriticalSection
0x18001c4ea  mov     eax, ebx
0x18001c4ec  jmp     loc_18001CACB
0x18001c4f1  mov     [rsp+0A8h+arg_10], r15
0x18001c4f9  lea     rcx, [rsp+0A8h+arg_10]
0x18001c501  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c506  lea     rax, [rsp+0A8h+arg_10]
0x18001c50e  mov     [rsp+0A8h+ppv], rax; int
0x18001c513  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18001c51a  xor     edx, edx; pUnkOuter
0x18001c51c  lea     r8d, [rdx+17h]; dwClsContext
0x18001c520  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18001c527  call    cs:__imp_CoCreateInstance
0x18001c52d  mov     ebx, eax
0x18001c52f  test    eax, eax
0x18001c531  jns     short loc_18001C589
0x18001c533  mov     rcx, [rsp+0A8h]; this
0x18001c53b  mov     r9d, eax; char *
0x18001c53e  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c545  mov     edx, 2Fh ; '/'; void *
0x18001c54a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c54f  nop
0x18001c550  lea     rcx, [rsp+0A8h+arg_10]
0x18001c558  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c55d  nop
0x18001c55e  lea     rcx, [rsp+0A8h+var_68]
0x18001c563  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c568  nop
0x18001c569  lea     rcx, [rsp+0A8h+var_60]
0x18001c56e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c573  nop
0x18001c574  test    rsi, rsi
0x18001c577  jz      short loc_18001C582
0x18001c579  mov     rcx, rsi; lpCriticalSection
0x18001c57c  call    cs:__imp_LeaveCriticalSection
0x18001c582  mov     eax, ebx
0x18001c584  jmp     loc_18001CACB
0x18001c589  lea     rax, [r14+20h]
0x18001c58d  mov     [rsp+0A8h+var_50], rax
0x18001c592  lea     rcx, [rsp+0A8h+var_50]
0x18001c597  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001c59c  mov     rbx, rax
0x18001c59f  mov     rdi, [rsp+0A8h+arg_10]
0x18001c5a7  test    rdi, rdi
0x18001c5aa  jz      short loc_18001C625
0x18001c5ac  mov     rcx, rax
0x18001c5af  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001c5b4  mov     r9, rbx
0x18001c5b7  mov     r8, rdi
0x18001c5ba  lea     rdx, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x18001c5c1  xor     ecx, ecx
0x18001c5c3  call    cs:__imp_RoGetAgileReference
0x18001c5c9  mov     ebx, eax
0x18001c5cb  test    eax, eax
0x18001c5cd  jns     short loc_18001C649
0x18001c5cf  mov     rcx, [rsp+0A8h]; this
0x18001c5d7  mov     r9d, eax; char *
0x18001c5da  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c5e1  mov     edx, 30h ; '0'; void *
0x18001c5e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c5eb  nop
0x18001c5ec  lea     rcx, [rsp+0A8h+arg_10]
0x18001c5f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c5f9  nop
0x18001c5fa  lea     rcx, [rsp+0A8h+var_68]
0x18001c5ff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c604  nop
0x18001c605  lea     rcx, [rsp+0A8h+var_60]
0x18001c60a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c60f  nop
0x18001c610  test    rsi, rsi
0x18001c613  jz      short loc_18001C61E
0x18001c615  mov     rcx, rsi; lpCriticalSection
0x18001c618  call    cs:__imp_LeaveCriticalSection
0x18001c61e  mov     eax, ebx
0x18001c620  jmp     loc_18001CACB
0x18001c625  mov     [rsp+0A8h+var_48], r15
0x18001c62a  mov     rax, [rax]
0x18001c62d  mov     [rsp+0A8h+var_50], rax
0x18001c632  mov     [rbx], r15
0x18001c635  lea     rcx, [rsp+0A8h+var_50]
0x18001c63a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001c63f  lea     rcx, [rsp+0A8h+var_48]
0x18001c644  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001c649  mov     [rsp+0A8h+pProxy], r15
0x18001c651  mov     rbx, [rsp+0A8h+arg_10]
0x18001c659  mov     rax, [rbx]
0x18001c65c  mov     rdi, [rax]
0x18001c65f  lea     rcx, [rsp+0A8h+pProxy]
0x18001c667  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c66c  lea     r8, [rsp+0A8h+pProxy]
0x18001c674  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18001c67b  mov     rcx, rbx
0x18001c67e  mov     rax, rdi
0x18001c681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c686  mov     ebx, eax
0x18001c688  test    eax, eax
0x18001c68a  jns     short loc_18001C6F0
0x18001c68c  mov     rcx, [rsp+0A8h]; this
0x18001c694  mov     r9d, eax; char *
0x18001c697  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c69e  mov     edx, 33h ; '3'; void *
0x18001c6a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c6a8  nop
0x18001c6a9  lea     rcx, [rsp+0A8h+pProxy]
0x18001c6b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c6b6  nop
0x18001c6b7  lea     rcx, [rsp+0A8h+arg_10]
0x18001c6bf  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c6c4  nop
0x18001c6c5  lea     rcx, [rsp+0A8h+var_68]
0x18001c6ca  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c6cf  nop
0x18001c6d0  lea     rcx, [rsp+0A8h+var_60]
0x18001c6d5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c6da  nop
0x18001c6db  test    rsi, rsi
0x18001c6de  jz      short loc_18001C6E9
0x18001c6e0  mov     rcx, rsi; lpCriticalSection
0x18001c6e3  call    cs:__imp_LeaveCriticalSection
0x18001c6e9  mov     eax, ebx
0x18001c6eb  jmp     loc_18001CACB
0x18001c6f0  mov     edi, 20h ; ' '
0x18001c6f5  mov     [rsp+0A8h+dwCapabilities], edi; dwCapabilities
0x18001c6f9  mov     [rsp+0A8h+pAuthInfo], r15; pAuthInfo
0x18001c6fe  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x18001c706  mov     dword ptr [rsp+0A8h+ppv], r15d; int
0x18001c70b  mov     r9, r13; pServerPrincName
0x18001c70e  xor     r8d, r8d; dwAuthzSvc
0x18001c711  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18001c714  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x18001c71c  call    cs:__imp_CoSetProxyBlanket
0x18001c722  mov     ebx, eax
0x18001c724  test    eax, eax
0x18001c726  jns     short loc_18001C78A
0x18001c728  mov     rcx, [rsp+0A8h]; this
0x18001c730  mov     r9d, eax; char *
0x18001c733  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c73a  lea     edx, [rdi+1Ch]; void *
0x18001c73d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c742  nop
0x18001c743  lea     rcx, [rsp+0A8h+pProxy]
0x18001c74b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c750  nop
0x18001c751  lea     rcx, [rsp+0A8h+arg_10]
0x18001c759  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c75e  nop
0x18001c75f  lea     rcx, [rsp+0A8h+var_68]
0x18001c764  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c769  nop
0x18001c76a  lea     rcx, [rsp+0A8h+var_60]
0x18001c76f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c774  nop
0x18001c775  test    rsi, rsi
0x18001c778  jz      short loc_18001C783
0x18001c77a  mov     rcx, rsi; lpCriticalSection
0x18001c77d  call    cs:__imp_LeaveCriticalSection
0x18001c783  mov     eax, ebx
0x18001c785  jmp     loc_18001CACB
0x18001c78a  mov     [rsp+0A8h+var_58], r15
0x18001c78f  mov     rcx, [rsp+0A8h+pProxy]
0x18001c797  mov     rax, [rcx]
0x18001c79a  lea     r8, [rsp+0A8h+var_58]
0x18001c79f  lea     rdx, _GUID_733b7764_5c0c_4ad6_bb4b_d0585e993e0f
0x18001c7a6  mov     rax, [rax+20h]
0x18001c7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7af  mov     ebx, eax
0x18001c7b1  test    eax, eax
0x18001c7b3  jns     short loc_18001C824
0x18001c7b5  mov     rcx, [rsp+0A8h]; this
0x18001c7bd  mov     r9d, eax; char *
0x18001c7c0  lea     r8, aOnecoreuapNetU_0; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18001c7c7  mov     edx, 40h ; '@'; void *
0x18001c7cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001c7d1  nop
0x18001c7d2  lea     rcx, [rsp+0A8h+var_58]
0x18001c7d7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c7dc  nop
0x18001c7dd  lea     rcx, [rsp+0A8h+pProxy]
0x18001c7e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c7ea  nop
0x18001c7eb  lea     rcx, [rsp+0A8h+arg_10]
0x18001c7f3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c7f8  nop
0x18001c7f9  lea     rcx, [rsp+0A8h+var_68]
0x18001c7fe  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18001c803  nop
0x18001c804  lea     rcx, [rsp+0A8h+var_60]
0x18001c809  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001c80e  nop
0x18001c80f  test    rsi, rsi
0x18001c812  jz      short loc_18001C81D
0x18001c814  mov     rcx, rsi; lpCriticalSection
0x18001c817  call    cs:__imp_LeaveCriticalSection
0x18001c81d  mov     eax, ebx
0x18001c81f  jmp     loc_18001CACB
0x18001c824  mov     [rsp+0A8h+dwCapabilities], edi; dwCapabilities
0x18001c828  mov     [rsp+0A8h+pAuthInfo], r15; pAuthInfo
0x18001c82d  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x18001c835  mov     dword ptr [rsp+0A8h+ppv], r15d; int
0x18001c83a  mov     r9, r13; pServerPrincName
0x18001c83d  xor     r8d, r8d; dwAuthzSvc
  ... truncated ...
```
