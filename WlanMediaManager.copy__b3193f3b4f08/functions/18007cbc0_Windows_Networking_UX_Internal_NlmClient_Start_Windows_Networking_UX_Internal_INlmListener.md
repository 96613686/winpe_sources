# Windows::Networking::UX::Internal::NlmClient::Start(Windows::Networking::UX::Internal::INlmListener *)

- ea: `0x18007cbc0`
- end: `0x18007d326`
- name: `?Start@NlmClient@Internal@UX@Networking@Windows@@QEAAJPEAVINlmListener@2345@@Z`
- size: `1894`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::NlmClient *__hidden this, struct Windows::Networking::UX::Internal::INlmListener *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180025a10`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x180012228`
- `0x1800127d8`
- `0x18001d4d4`
- `0x180028800`
- `0x18007c770`
- `0x18007cbc0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cdc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cfc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d061`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d1ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d304`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cc4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cccc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cd2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cdc6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007ce62`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cf2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007cfc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d061`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d100`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d1ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d277`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007d304`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc0b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18007cc0b`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007cf66`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007d092`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007cf66`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18007d092`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007cd71`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18007cd71`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18007ce0d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18007d148`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18007ce0d`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18007d148`

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
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  const char *v10; // r9
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // r8
  HRESULT v17; // eax
  unsigned int v18; // ebx
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rdx
  __int64 v22; // r8
  _QWORD *v23; // rax
  __int64 v24; // rdx
  __int64 v25; // r8
  _QWORD *v26; // rbx
  LPVOID v27; // rdi
  int AgileReference; // eax
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned int v31; // ebx
  __int64 v32; // rdx
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rdx
  __int64 v37; // r8
  LPVOID v38; // rbx
  __int64 (__fastcall *v39)(LPVOID, GUID *, IUnknown **); // rdi
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // r8
  __int64 v46; // rdx
  __int64 v47; // r8
  HRESULT v48; // eax
  unsigned int v49; // ebx
  __int64 v50; // rdx
  __int64 v51; // r8
  __int64 v52; // rdx
  __int64 v53; // r8
  __int64 v54; // rdx
  __int64 v55; // r8
  int v56; // eax
  unsigned int v57; // ebx
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // rdx
  __int64 v61; // r8
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // rdx
  __int64 v65; // r8
  HRESULT v66; // eax
  unsigned int v67; // ebx
  __int64 v68; // rdx
  __int64 v69; // r8
  __int64 v70; // rdx
  __int64 v71; // r8
  __int64 v72; // rdx
  __int64 v73; // r8
  __int64 v74; // rdx
  __int64 v75; // r8
  _QWORD *v76; // rax
  __int64 v77; // rdx
  __int64 v78; // r8
  _QWORD *v79; // rbx
  IUnknown *v80; // rdi
  int v81; // eax
  unsigned int v82; // ebx
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // rdx
  __int64 v86; // r8
  __int64 v87; // rdx
  __int64 v88; // r8
  __int64 v89; // rdx
  __int64 v90; // r8
  __int64 v91; // rdx
  __int64 v92; // r8
  int v93; // eax
  __int64 v94; // rdx
  __int64 v95; // r8
  unsigned int v96; // ebx
  __int64 v97; // rdx
  __int64 v98; // r8
  __int64 v99; // rdx
  __int64 v100; // r8
  __int64 v101; // rdx
  __int64 v102; // r8
  __int64 v103; // rdx
  __int64 v104; // r8
  __int64 v105; // rdx
  __int64 v106; // r8
  __int64 v107; // rdx
  __int64 v108; // r8
  __int64 v109; // rdx
  __int64 v110; // r8
  int ppv; // [rsp+20h] [rbp-88h]
  int ppva; // [rsp+20h] [rbp-88h]
  int ppvb; // [rsp+20h] [rbp-88h]
  int ppvc; // [rsp+20h] [rbp-88h]
  __int64 v115; // [rsp+40h] [rbp-68h] BYREF
  struct Windows::Networking::UX::Internal::INlmListener *v116; // [rsp+48h] [rbp-60h] BYREF
  IUnknown *v117; // [rsp+50h] [rbp-58h] BYREF
  char *v118; // [rsp+58h] [rbp-50h] BYREF
  _QWORD v119[9]; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v121; // [rsp+B0h] [rbp+8h] BYREF
  LPVOID v122; // [rsp+C0h] [rbp+18h] BYREF
  IUnknown *pProxy; // [rsp+C8h] [rbp+20h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  v119[1] = (char *)this + 48;
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
    v116 = a2;
    if ( a2 )
      (*(void (__fastcall **)(struct Windows::Networking::UX::Internal::INlmListener *))(*(_QWORD *)a2 + 8LL))(a2);
    v115 = (__int64)this + 16;
    v5 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v115);
    v6 = Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::INlmListener>(a2, v5);
    v7 = v6;
    if ( v6 >= 0 )
    {
      v115 = -1;
      v11 = wil::impersonate_token_nothrow(0, (void **)&v115);
      v14 = v11;
      if ( v11 >= 0 )
      {
        v122 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v122, v12, v13);
        v17 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v122);
        v18 = v17;
        if ( v17 >= 0 )
        {
          v118 = (char *)this + 32;
          v23 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v118);
          v26 = v23;
          v27 = v122;
          if ( v122 )
          {
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              v23,
              v24,
              v25);
            AgileReference = RoGetAgileReference(0, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, v27, v26);
            v31 = AgileReference;
            if ( AgileReference < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x30,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                (const char *)(unsigned int)AgileReference,
                ppva);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v122,
                v32,
                v33);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v116,
                v34,
                v35);
              if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              return v31;
            }
          }
          else
          {
            v119[0] = 0;
            v118 = (char *)*v23;
            *v23 = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v118,
              v24,
              v25);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              v119,
              v36,
              v37);
          }
          pProxy = 0;
          v38 = v122;
          v39 = **(__int64 (__fastcall ***)(LPVOID, GUID *, IUnknown **))v122;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &pProxy,
            v29,
            v30);
          v40 = v39(v38, &GUID_b196b284_bab4_101a_b69c_00aa00341d07, &pProxy);
          v41 = v40;
          if ( v40 >= 0 )
          {
            v48 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
            v49 = v48;
            if ( v48 >= 0 )
            {
              v117 = 0;
              v56 = ((__int64 (__fastcall *)(IUnknown *, GUID *, IUnknown **))pProxy->lpVtbl[1].AddRef)(
                      pProxy,
                      &GUID_733b7764_5c0c_4ad6_bb4b_d0585e993e0f,
                      &v117);
              v57 = v56;
              if ( v56 >= 0 )
              {
                v66 = CoSetProxyBlanket(v117, 0xFFFFFFFF, 0, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
                v67 = v66;
                if ( v66 >= 0 )
                {
                  v119[0] = (char *)this + 40;
                  v76 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(v119);
                  v79 = v76;
                  v80 = v117;
                  if ( v117 )
                  {
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      v76,
                      v77,
                      v78);
                    v81 = RoGetAgileReference(0, &GUID_b196b286_bab4_101a_b69c_00aa00341d07, v80, v79);
                    v82 = v81;
                    if ( v81 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x4B,
                        (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                        (const char *)(unsigned int)v81,
                        ppvc);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                        &v117,
                        v83,
                        v84);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                        &pProxy,
                        v85,
                        v86);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                        &v122,
                        v87,
                        v88);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
                      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                        &v116,
                        v89,
                        v90);
                      if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                      return v82;
                    }
                  }
                  else
                  {
                    v118 = 0;
                    v119[0] = *v76;
                    *v76 = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      v119,
                      v77,
                      v78);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v118,
                      v91,
                      v92);
                  }
                  v121 = 0;
                  v93 = ((__int64 (__fastcall *)(IUnknown *, Windows::Networking::UX::Internal::NlmClient *, int *))v117->lpVtbl[1].Release)(
                          v117,
                          this,
                          &v121);
                  v96 = v93;
                  if ( v93 >= 0 )
                  {
                    *((_DWORD *)this + 22) = v121;
                    *((_BYTE *)this + 24) = 1;
                    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
                      WPP_SF_d(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        15,
                        WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids,
                        0);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v117,
                      v94,
                      v95);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &pProxy,
                      v105,
                      v106);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v122,
                      v107,
                      v108);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v116,
                      v109,
                      v110);
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
                      (const char *)(unsigned int)v93,
                      ppvc);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v117,
                      v97,
                      v98);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &pProxy,
                      v99,
                      v100);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v122,
                      v101,
                      v102);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                      &v116,
                      v103,
                      v104);
                    if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                    return v96;
                  }
                }
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x49,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                  (const char *)(unsigned int)v66,
                  ppvc);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v117,
                  v68,
                  v69);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &pProxy,
                  v70,
                  v71);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v122,
                  v72,
                  v73);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v116,
                  v74,
                  v75);
                if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                result = v67;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x40,
                  (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                  (const char *)(unsigned int)v56,
                  ppvb);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v117,
                  v58,
                  v59);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &pProxy,
                  v60,
                  v61);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v122,
                  v62,
                  v63);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                  &v116,
                  v64,
                  v65);
                if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
                result = v57;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x3C,
                (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                (const char *)(unsigned int)v48,
                ppvb);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &pProxy,
                v50,
                v51);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v122,
                v52,
                v53);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
                &v116,
                v54,
                v55);
              if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
              result = v49;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x33,
              (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
              (const char *)(unsigned int)v40,
              ppva);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &pProxy,
              v42,
              v43);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v122,
              v44,
              v45);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
              &v116,
              v46,
              v47);
            if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
              LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
            result = v41;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x2F,
            (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
            (const char *)(unsigned int)v17,
            ppva);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v122,
            v19,
            v20);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(
            &v116,
            v21,
            v22);
          if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
          result = v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2C,
          (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
          (const char *)(unsigned int)v11,
          ppv);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v115);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v116, v15, v16);
        if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        result = v14;
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
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v116, v8, v9);
      if ( this != (Windows::Networking::UX::Internal::NlmClient *)-48LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      result = v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55,
                           (unsigned int)"onecoreuap\\net\\ux\\mediamanagerbase\\lib\\nlmclient.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18007cbc0  push    rbx
0x18007cbc2  push    rsi
0x18007cbc3  push    rdi
0x18007cbc4  push    r12
0x18007cbc6  push    r13
0x18007cbc8  push    r14
0x18007cbca  push    r15
0x18007cbcc  sub     rsp, 70h
0x18007cbd0  mov     rbx, rdx
0x18007cbd3  mov     r14, rcx
0x18007cbd6  lea     r12, WPP_GLOBAL_Control
0x18007cbdd  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cbe4  cmp     rcx, r12
0x18007cbe7  jz      short loc_18007CC04
0x18007cbe9  test    byte ptr [rcx+1Ch], 40h
0x18007cbed  jz      short loc_18007CC04
0x18007cbef  mov     edx, 0Dh
0x18007cbf4  lea     r8, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids
0x18007cbfb  mov     rcx, [rcx+10h]
0x18007cbff  call    WPP_SF_
0x18007cc04  lea     rsi, [r14+30h]
0x18007cc08  mov     rcx, rsi; lpCriticalSection
0x18007cc0b  call    cs:__imp_EnterCriticalSection
0x18007cc11  mov     [rsp+0A8h+var_40], rsi
0x18007cc16  xor     r15d, r15d
0x18007cc19  cmp     [r14+18h], r15b
0x18007cc1d  jz      short loc_18007CC5E
0x18007cc1f  mov     rcx, cs:WPP_GLOBAL_Control
0x18007cc26  cmp     rcx, r12
0x18007cc29  jz      short loc_18007CC46
0x18007cc2b  test    byte ptr [rcx+1Ch], 4
0x18007cc2f  jz      short loc_18007CC46
0x18007cc31  lea     edx, [r15+0Eh]
0x18007cc35  lea     r8, WPP_25c4bd416a6e3932573f50bc374283fe_Traceguids
0x18007cc3c  mov     rcx, [rcx+10h]
0x18007cc40  call    WPP_SF_
0x18007cc45  nop
0x18007cc46  test    rsi, rsi
0x18007cc49  jz      short loc_18007CC54
0x18007cc4b  mov     rcx, rsi; lpCriticalSection
0x18007cc4e  call    cs:__imp_LeaveCriticalSection
0x18007cc54  mov     eax, 1
0x18007cc59  jmp     loc_18007D315
0x18007cc5e  mov     [rsp+0A8h+var_60], rbx
0x18007cc63  test    rbx, rbx
0x18007cc66  jz      short loc_18007CC78
0x18007cc68  mov     rax, [rbx]
0x18007cc6b  mov     rcx, rbx
0x18007cc6e  mov     rax, [rax+8]
0x18007cc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cc77  nop
0x18007cc78  lea     rax, [r14+10h]
0x18007cc7c  mov     [rsp+0A8h+var_68], rax
0x18007cc81  lea     rcx, [rsp+0A8h+var_68]
0x18007cc86  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007cc8b  mov     rdx, rax
0x18007cc8e  mov     rcx, rbx
0x18007cc91  call    ??$AsWeak@VINlmListener@Internal@UX@Networking@Windows@@@WRL@Microsoft@@YAJPEAVINlmListener@Internal@UX@Networking@Windows@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<Windows::Networking::UX::Internal::INlmListener>(Windows::Networking::UX::Internal::INlmListener *,Microsoft::WRL::WeakRef *)
0x18007cc96  mov     ebx, eax
0x18007cc98  test    eax, eax
0x18007cc9a  jns     short loc_18007CCD9
0x18007cc9c  mov     rcx, [rsp+0A8h]; this
0x18007cca4  mov     r9d, eax; char *
0x18007cca7  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ccae  mov     edx, 29h ; ')'; void *
0x18007ccb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ccb8  nop
0x18007ccb9  lea     rcx, [rsp+0A8h+var_60]
0x18007ccbe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ccc3  nop
0x18007ccc4  test    rsi, rsi
0x18007ccc7  jz      short loc_18007CCD2
0x18007ccc9  mov     rcx, rsi; lpCriticalSection
0x18007cccc  call    cs:__imp_LeaveCriticalSection
0x18007ccd2  mov     eax, ebx
0x18007ccd4  jmp     loc_18007D315
0x18007ccd9  or      r13, 0FFFFFFFFFFFFFFFFh
0x18007ccdd  mov     [rsp+0A8h+var_68], r13
0x18007cce2  lea     rdx, [rsp+0A8h+var_68]
0x18007cce7  xor     ecx, ecx; Token
0x18007cce9  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x18007ccee  mov     ebx, eax
0x18007ccf0  test    eax, eax
0x18007ccf2  jns     short loc_18007CD3B
0x18007ccf4  mov     rcx, [rsp+0A8h]; this
0x18007ccfc  mov     r9d, eax; char *
0x18007ccff  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007cd06  lea     edx, [r13+2Dh]; void *
0x18007cd0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd0f  nop
0x18007cd10  lea     rcx, [rsp+0A8h+var_68]
0x18007cd15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007cd1a  nop
0x18007cd1b  lea     rcx, [rsp+0A8h+var_60]
0x18007cd20  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cd25  nop
0x18007cd26  test    rsi, rsi
0x18007cd29  jz      short loc_18007CD34
0x18007cd2b  mov     rcx, rsi; lpCriticalSection
0x18007cd2e  call    cs:__imp_LeaveCriticalSection
0x18007cd34  mov     eax, ebx
0x18007cd36  jmp     loc_18007D315
0x18007cd3b  mov     [rsp+0A8h+arg_10], r15
0x18007cd43  lea     rcx, [rsp+0A8h+arg_10]
0x18007cd4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cd50  lea     rax, [rsp+0A8h+arg_10]
0x18007cd58  mov     [rsp+0A8h+ppv], rax; int
0x18007cd5d  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x18007cd64  xor     edx, edx; pUnkOuter
0x18007cd66  lea     r8d, [rdx+17h]; dwClsContext
0x18007cd6a  lea     rcx, CLSID_CNetworkListManager; rclsid
0x18007cd71  call    cs:__imp_CoCreateInstance
0x18007cd77  mov     ebx, eax
0x18007cd79  test    eax, eax
0x18007cd7b  jns     short loc_18007CDD3
0x18007cd7d  mov     rcx, [rsp+0A8h]; this
0x18007cd85  mov     r9d, eax; char *
0x18007cd88  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007cd8f  mov     edx, 2Fh ; '/'; void *
0x18007cd94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cd99  nop
0x18007cd9a  lea     rcx, [rsp+0A8h+arg_10]
0x18007cda2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cda7  nop
0x18007cda8  lea     rcx, [rsp+0A8h+var_68]
0x18007cdad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007cdb2  nop
0x18007cdb3  lea     rcx, [rsp+0A8h+var_60]
0x18007cdb8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cdbd  nop
0x18007cdbe  test    rsi, rsi
0x18007cdc1  jz      short loc_18007CDCC
0x18007cdc3  mov     rcx, rsi; lpCriticalSection
0x18007cdc6  call    cs:__imp_LeaveCriticalSection
0x18007cdcc  mov     eax, ebx
0x18007cdce  jmp     loc_18007D315
0x18007cdd3  lea     rax, [r14+20h]
0x18007cdd7  mov     [rsp+0A8h+var_50], rax
0x18007cddc  lea     rcx, [rsp+0A8h+var_50]
0x18007cde1  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x18007cde6  mov     rbx, rax
0x18007cde9  mov     rdi, [rsp+0A8h+arg_10]
0x18007cdf1  test    rdi, rdi
0x18007cdf4  jz      short loc_18007CE6F
0x18007cdf6  mov     rcx, rax
0x18007cdf9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cdfe  mov     r9, rbx
0x18007ce01  mov     r8, rdi
0x18007ce04  lea     rdx, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x18007ce0b  xor     ecx, ecx
0x18007ce0d  call    cs:__imp_RoGetAgileReference
0x18007ce13  mov     ebx, eax
0x18007ce15  test    eax, eax
0x18007ce17  jns     short loc_18007CE93
0x18007ce19  mov     rcx, [rsp+0A8h]; this
0x18007ce21  mov     r9d, eax; char *
0x18007ce24  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007ce2b  mov     edx, 30h ; '0'; void *
0x18007ce30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007ce35  nop
0x18007ce36  lea     rcx, [rsp+0A8h+arg_10]
0x18007ce3e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ce43  nop
0x18007ce44  lea     rcx, [rsp+0A8h+var_68]
0x18007ce49  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007ce4e  nop
0x18007ce4f  lea     rcx, [rsp+0A8h+var_60]
0x18007ce54  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ce59  nop
0x18007ce5a  test    rsi, rsi
0x18007ce5d  jz      short loc_18007CE68
0x18007ce5f  mov     rcx, rsi; lpCriticalSection
0x18007ce62  call    cs:__imp_LeaveCriticalSection
0x18007ce68  mov     eax, ebx
0x18007ce6a  jmp     loc_18007D315
0x18007ce6f  mov     [rsp+0A8h+var_48], r15
0x18007ce74  mov     rax, [rax]
0x18007ce77  mov     [rsp+0A8h+var_50], rax
0x18007ce7c  mov     [rbx], r15
0x18007ce7f  lea     rcx, [rsp+0A8h+var_50]
0x18007ce84  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ce89  lea     rcx, [rsp+0A8h+var_48]
0x18007ce8e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ce93  mov     [rsp+0A8h+pProxy], r15
0x18007ce9b  mov     rbx, [rsp+0A8h+arg_10]
0x18007cea3  mov     rax, [rbx]
0x18007cea6  mov     rdi, [rax]
0x18007cea9  lea     rcx, [rsp+0A8h+pProxy]
0x18007ceb1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007ceb6  lea     r8, [rsp+0A8h+pProxy]
0x18007cebe  lea     rdx, _GUID_b196b284_bab4_101a_b69c_00aa00341d07
0x18007cec5  mov     rcx, rbx
0x18007cec8  mov     rax, rdi
0x18007cecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ced0  mov     ebx, eax
0x18007ced2  test    eax, eax
0x18007ced4  jns     short loc_18007CF3A
0x18007ced6  mov     rcx, [rsp+0A8h]; this
0x18007cede  mov     r9d, eax; char *
0x18007cee1  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007cee8  mov     edx, 33h ; '3'; void *
0x18007ceed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cef2  nop
0x18007cef3  lea     rcx, [rsp+0A8h+pProxy]
0x18007cefb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cf00  nop
0x18007cf01  lea     rcx, [rsp+0A8h+arg_10]
0x18007cf09  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cf0e  nop
0x18007cf0f  lea     rcx, [rsp+0A8h+var_68]
0x18007cf14  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007cf19  nop
0x18007cf1a  lea     rcx, [rsp+0A8h+var_60]
0x18007cf1f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cf24  nop
0x18007cf25  test    rsi, rsi
0x18007cf28  jz      short loc_18007CF33
0x18007cf2a  mov     rcx, rsi; lpCriticalSection
0x18007cf2d  call    cs:__imp_LeaveCriticalSection
0x18007cf33  mov     eax, ebx
0x18007cf35  jmp     loc_18007D315
0x18007cf3a  mov     edi, 20h ; ' '
0x18007cf3f  mov     [rsp+0A8h+dwCapabilities], edi; dwCapabilities
0x18007cf43  mov     [rsp+0A8h+pAuthInfo], r15; pAuthInfo
0x18007cf48  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x18007cf50  mov     dword ptr [rsp+0A8h+ppv], r15d; int
0x18007cf55  mov     r9, r13; pServerPrincName
0x18007cf58  xor     r8d, r8d; dwAuthzSvc
0x18007cf5b  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18007cf5e  mov     rcx, [rsp+0A8h+pProxy]; pProxy
0x18007cf66  call    cs:__imp_CoSetProxyBlanket
0x18007cf6c  mov     ebx, eax
0x18007cf6e  test    eax, eax
0x18007cf70  jns     short loc_18007CFD4
0x18007cf72  mov     rcx, [rsp+0A8h]; this
0x18007cf7a  mov     r9d, eax; char *
0x18007cf7d  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007cf84  lea     edx, [rdi+1Ch]; void *
0x18007cf87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007cf8c  nop
0x18007cf8d  lea     rcx, [rsp+0A8h+pProxy]
0x18007cf95  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cf9a  nop
0x18007cf9b  lea     rcx, [rsp+0A8h+arg_10]
0x18007cfa3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cfa8  nop
0x18007cfa9  lea     rcx, [rsp+0A8h+var_68]
0x18007cfae  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007cfb3  nop
0x18007cfb4  lea     rcx, [rsp+0A8h+var_60]
0x18007cfb9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007cfbe  nop
0x18007cfbf  test    rsi, rsi
0x18007cfc2  jz      short loc_18007CFCD
0x18007cfc4  mov     rcx, rsi; lpCriticalSection
0x18007cfc7  call    cs:__imp_LeaveCriticalSection
0x18007cfcd  mov     eax, ebx
0x18007cfcf  jmp     loc_18007D315
0x18007cfd4  mov     [rsp+0A8h+var_58], r15
0x18007cfd9  mov     rcx, [rsp+0A8h+pProxy]
0x18007cfe1  mov     rax, [rcx]
0x18007cfe4  lea     r8, [rsp+0A8h+var_58]
0x18007cfe9  lea     rdx, _GUID_733b7764_5c0c_4ad6_bb4b_d0585e993e0f
0x18007cff0  mov     rax, [rax+20h]
0x18007cff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007cff9  mov     ebx, eax
0x18007cffb  test    eax, eax
0x18007cffd  jns     short loc_18007D06E
0x18007cfff  mov     rcx, [rsp+0A8h]; this
0x18007d007  mov     r9d, eax; char *
0x18007d00a  lea     r8, aOnecoreuapNetU_1; "onecoreuap\\net\\ux\\mediamanagerbase\\"...
0x18007d011  mov     edx, 40h ; '@'; void *
0x18007d016  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007d01b  nop
0x18007d01c  lea     rcx, [rsp+0A8h+var_58]
0x18007d021  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d026  nop
0x18007d027  lea     rcx, [rsp+0A8h+pProxy]
0x18007d02f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d034  nop
0x18007d035  lea     rcx, [rsp+0A8h+arg_10]
0x18007d03d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d042  nop
0x18007d043  lea     rcx, [rsp+0A8h+var_68]
0x18007d048  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18007d04d  nop
0x18007d04e  lea     rcx, [rsp+0A8h+var_60]
0x18007d053  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18007d058  nop
0x18007d059  test    rsi, rsi
0x18007d05c  jz      short loc_18007D067
0x18007d05e  mov     rcx, rsi; lpCriticalSection
0x18007d061  call    cs:__imp_LeaveCriticalSection
0x18007d067  mov     eax, ebx
0x18007d069  jmp     loc_18007D315
0x18007d06e  mov     [rsp+0A8h+dwCapabilities], edi; dwCapabilities
0x18007d072  mov     [rsp+0A8h+pAuthInfo], r15; pAuthInfo
0x18007d077  mov     [rsp+0A8h+dwImpLevel], 3; dwImpLevel
0x18007d07f  mov     dword ptr [rsp+0A8h+ppv], r15d; int
0x18007d084  mov     r9, r13; pServerPrincName
  ... truncated ...
```
