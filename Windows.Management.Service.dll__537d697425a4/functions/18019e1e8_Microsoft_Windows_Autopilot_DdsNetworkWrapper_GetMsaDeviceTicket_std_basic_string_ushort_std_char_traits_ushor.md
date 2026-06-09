# Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18019e1e8`
- end: `0x18019ee97`
- name: `?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z`
- size: `3247`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18019d6fc`

## callees

- `0x18000b8f0`
- `0x180063fa3`
- `0x180067398`
- `0x180067e54`
- `0x180080bac`
- `0x1800810f0`
- `0x1800829ec`
- `0x180086044`
- `0x18008bf28`
- `0x18008d290`
- `0x18019d1a8`
- `0x18019e118`
- `0x18019e1e8`
- `0x180200010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019ed96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18019ed96`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019eaaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ebbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ec88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ecd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019edb3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e313`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e43c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e581`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e798`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e8bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019e9a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019eaaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ebbd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ec88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019ecd5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019edb3`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18019e27e`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18019e27e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18019e404`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18019e404`

## string_xrefs

- `0x18019e2fc`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e425`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e56a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e680`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e781`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e98c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ea98`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019eba6`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019ecbe`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019e3df`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x18019e24f`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`

## pseudocode

```c
// Hidden C++ exception states: #wind=15 #try_helpers=1
__int64 __fastcall Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rcx
  int ActivationFactory; // eax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  _QWORD *v18; // rcx
  __int64 v19; // rsi
  __int64 (__fastcall *v20)(__int64, _QWORD, __int64, __int64 *); // rdi
  __int64 v21; // rbx
  __int64 v22; // rax
  int v23; // eax
  Microsoft::Windows::Autopilot::DdsNetworkWrapper *v24; // rcx
  unsigned int v25; // ebx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  _QWORD *v30; // rcx
  _QWORD *v31; // rdi
  __int64 (__fastcall *v32)(_QWORD *, int *); // rbx
  int v33; // eax
  unsigned int v34; // ebx
  __int64 v35; // rcx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rcx
  _QWORD *v39; // rcx
  int v40; // eax
  unsigned int v41; // ebx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  _QWORD *v46; // rcx
  __int64 v47; // rdi
  __int64 v48; // rcx
  int v49; // ebx
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  _QWORD *v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  _QWORD *v60; // rcx
  __int64 v61; // rdi
  __int64 (__fastcall *v62)(__int64, __int64 *); // rbx
  int v63; // eax
  unsigned int v64; // ebx
  __int64 v65; // rcx
  __int64 v66; // rcx
  __int64 v67; // rcx
  __int64 v68; // rcx
  _QWORD *v69; // rcx
  __int64 v70; // rdi
  __int64 (__fastcall *v71)(__int64, _QWORD, __int64 *); // rbx
  int v72; // eax
  unsigned int v73; // ebx
  __int64 v74; // rcx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  _QWORD *v78; // rcx
  __int64 v79; // rdi
  __int64 (__fastcall *v80)(__int64, HSTRING *); // rbx
  int v81; // eax
  unsigned int v82; // ebx
  __int64 v83; // rcx
  __int64 v84; // rcx
  __int64 v85; // rcx
  __int64 v86; // rcx
  _QWORD *v87; // rcx
  PCWSTR StringRawBuffer; // rdx
  __int64 v89; // rcx
  __int64 v90; // rcx
  __int64 v91; // rcx
  __int64 v92; // rcx
  _QWORD *v93; // rcx
  int *v94; // [rsp+20h] [rbp-D8h]
  _QWORD *v95; // [rsp+30h] [rbp-C8h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C0h] BYREF
  __int64 v97; // [rsp+40h] [rbp-B8h] BYREF
  __int64 v98; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v99; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v100; // [rsp+58h] [rbp-A0h] BYREF
  __int64 v101; // [rsp+60h] [rbp-98h] BYREF
  __int64 v102; // [rsp+68h] [rbp-90h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+70h] [rbp-88h] BYREF
  __int64 v104; // [rsp+88h] [rbp-70h]
  char v105[32]; // [rsp+90h] [rbp-68h] BYREF
  int v106[4]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v100 = 0;
  v99 = 0;
  v98 = 0;
  v97 = 0;
  v102 = 0;
  v101 = 0;
  string = 0;
  v104 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.WebAuthentication.AuthenticationManager",
    0x42u,
    0x41u);
  v95 = 0;
  *(_QWORD *)v106 = 0;
  v5 = RoActivateInstance(v104, v106);
  if ( v5 >= 0 )
  {
    if ( !memcmp_0(&GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v95 = *(_QWORD **)v106;
    }
    else
    {
      v5 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, _QWORD **))v106)(
             *(_QWORD *)v106,
             &GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb,
             &v95);
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v106 + 16LL))(*(_QWORD *)v106);
    }
  }
  if ( v5 >= 0 )
  {
    v104 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest",
      0x46u,
      0x45u);
    ActivationFactory = RoGetActivationFactory(v104, &GUID_bebb0a08_9e73_4077_9614_08614c0bc245, &v99);
    v13 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v19 = v99;
      v20 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v99 + 48LL);
      v21 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_18021C8D8) + 24);
      *(_QWORD *)v106 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      v22 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v105, v106);
      v23 = v20(v19, *(_QWORD *)(v22 + 24), v21, &v100);
      v25 = v23;
      if ( v23 >= 0 )
      {
        v31 = v95;
        v32 = *(__int64 (__fastcall **)(_QWORD *, int *))(*v95 + 72LL);
        *(struct _GUID *)v106 = *Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaApplicationId(v24);
        v33 = v32(v31, v106);
        v34 = v33;
        if ( v33 >= 0 )
        {
          v40 = (*(__int64 (__fastcall **)(_QWORD *, __int64, __int64 *))(*v95 + 56LL))(v95, v100, &v98);
          v41 = v40;
          if ( v40 >= 0 )
          {
            v47 = v98;
            v49 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>,Windows::Foundation::IAsyncOperation<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>>(v98);
            if ( v49 >= 0 )
              v49 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v47 + 64LL))(v47, &v97);
            if ( v49 == -2138701823 && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
            {
              v94 = v106;
              McGenEventWrite_EventWriteTransfer(v48, MsaEnvironmentApplicationMismatch, v50, 1);
            }
            if ( Microsoft::Windows::Autopilot::AutoPilotStateUtils::IsExpectedAcquireError(v49) )
            {
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
              v51 = v97;
              if ( v97 )
              {
                v97 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
              }
              v52 = v98;
              if ( v98 )
              {
                v98 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
              }
              v53 = v99;
              if ( v99 )
              {
                v99 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v53 + 16LL))(v53);
              }
              v54 = v100;
              if ( v100 )
              {
                v100 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v54 + 16LL))(v54);
              }
              v55 = v95;
              if ( v95 )
              {
                v95 = 0;
                (*(void (__fastcall **)(_QWORD *, _QWORD))(*v55 + 16LL))(v55, *v55);
              }
              return (unsigned int)v49;
            }
            else if ( v49 >= 0 )
            {
              v61 = v97;
              v62 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v97 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
              v63 = v62(v61, &v102);
              v64 = v63;
              if ( v63 >= 0 )
              {
                v70 = v102;
                v71 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v102 + 48LL);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
                v72 = v71(v70, 0, &v101);
                v73 = v72;
                if ( v72 >= 0 )
                {
                  v79 = v101;
                  v80 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v101 + 48LL);
                  WindowsDeleteString(string);
                  string = 0;
                  v81 = v80(v79, &string);
                  v82 = v81;
                  if ( v81 >= 0 )
                  {
                    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
                    std::wstring::assign(a3, StringRawBuffer);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
                    v89 = v97;
                    if ( v97 )
                    {
                      v97 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v89 + 16LL))(v89);
                    }
                    v90 = v98;
                    if ( v98 )
                    {
                      v98 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v90 + 16LL))(v90);
                    }
                    v91 = v99;
                    if ( v99 )
                    {
                      v99 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
                    }
                    v92 = v100;
                    if ( v100 )
                    {
                      v100 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v92 + 16LL))(v92);
                    }
                    v93 = v95;
                    if ( v95 )
                    {
                      v95 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v93 + 16LL))(v93);
                    }
                    return 0;
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x31C,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                      (const char *)(unsigned int)v81,
                      (int)v94);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
                    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
                    v83 = v97;
                    if ( v97 )
                    {
                      v97 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v83 + 16LL))(v83);
                    }
                    v84 = v98;
                    if ( v98 )
                    {
                      v98 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v84 + 16LL))(v84);
                    }
                    v85 = v99;
                    if ( v99 )
                    {
                      v99 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v85 + 16LL))(v85);
                    }
                    v86 = v100;
                    if ( v100 )
                    {
                      v100 = 0;
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
                    }
                    v87 = v95;
                    if ( v95 )
                    {
                      v95 = 0;
                      (*(void (__fastcall **)(_QWORD *))(*v87 + 16LL))(v87);
                    }
                    return v82;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x31B,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                    (const char *)(unsigned int)v72,
                    (int)v94);
                  WindowsDeleteString(string);
                  string = 0;
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
                  v74 = v97;
                  if ( v97 )
                  {
                    v97 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
                  }
                  v75 = v98;
                  if ( v98 )
                  {
                    v98 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
                  }
                  v76 = v99;
                  if ( v99 )
                  {
                    v99 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
                  }
                  v77 = v100;
                  if ( v100 )
                  {
                    v100 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v77 + 16LL))(v77);
                  }
                  v78 = v95;
                  if ( v95 )
                  {
                    v95 = 0;
                    (*(void (__fastcall **)(_QWORD *))(*v78 + 16LL))(v78);
                  }
                  return v73;
                }
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x31A,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                  (const char *)(unsigned int)v63,
                  (int)v94);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
                v65 = v97;
                if ( v97 )
                {
                  v97 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
                }
                v66 = v98;
                if ( v98 )
                {
                  v98 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v66 + 16LL))(v66);
                }
                v67 = v99;
                if ( v99 )
                {
                  v99 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
                }
                v68 = v100;
                if ( v100 )
                {
                  v100 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
                }
                v69 = v95;
                if ( v95 )
                {
                  v95 = 0;
                  (*(void (__fastcall **)(_QWORD *))(*v69 + 16LL))(v69);
                }
                return v64;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x318,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
                (const char *)(unsigned int)v49,
                (int)v94);
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
              v56 = v97;
              if ( v97 )
              {
                v97 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v56 + 16LL))(v56);
              }
              v57 = v98;
              if ( v98 )
              {
                v98 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
              }
              v58 = v99;
              if ( v99 )
              {
                v99 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v58 + 16LL))(v58);
              }
              v59 = v100;
              if ( v100 )
              {
                v100 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
              }
              v60 = v95;
              if ( v95 )
              {
                v95 = 0;
                (*(void (__fastcall **)(_QWORD *))(*v60 + 16LL))(v60);
              }
              return (unsigned int)v49;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x310,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
              (const char *)(unsigned int)v40,
              (int)v94);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
            v42 = v97;
            if ( v97 )
            {
              v97 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            }
            v43 = v98;
            if ( v98 )
            {
              v98 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
            }
            v44 = v99;
            if ( v99 )
            {
              v99 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            }
            v45 = v100;
            if ( v100 )
            {
              v100 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            }
            v46 = v95;
            if ( v95 )
            {
              v95 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v46 + 16LL))(v46);
            }
            return v41;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x30F,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
            (const char *)(unsigned int)v33,
            (int)v94);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
          v35 = v97;
          if ( v97 )
          {
            v97 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
          }
          v36 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
          }
          v37 = v99;
          if ( v99 )
          {
            v99 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
          }
          v38 = v100;
          if ( v100 )
          {
            v100 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
          }
          v39 = v95;
          if ( v95 )
          {
            v95 = 0;
            (*(void (__fastcall **)(_QWORD *))(*v39 + 16LL))(v39);
          }
          return v34;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x30D,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
          (const char *)(unsigned int)v23,
          (int)v94);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
        v26 = v97;
        if ( v97 )
        {
          v97 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        }
        v27 = v98;
        if ( v98 )
        {
          v98 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
        }
        v28 = v99;
        if ( v99 )
        {
          v99 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
        }
        v29 = v100;
        if ( v100 )
        {
          v100 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        }
        v30 = v95;
        if ( v95 )
        {
          v95 = 0;
          (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
        }
        return v25;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x308,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
        (const char *)(unsigned int)ActivationFactory,
        (int)v94);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
      v14 = v97;
      if ( v97 )
      {
        v97 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      }
      v15 = v98;
      if ( v98 )
      {
        v98 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      }
      v16 = v99;
      if ( v99 )
      {
        v99 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      }
      v17 = v100;
      if ( v100 )
      {
        v100 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      v18 = v95;
      if ( v95 )
      {
        v95 = 0;
        (*(void (__fastcall **)(_QWORD *))(*v18 + 16LL))(v18);
      }
      return v13;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\ddsnetworkwrapper.cpp",
      (const char *)(unsigned int)v5,
      (int)v94);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v101);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v102);
    v6 = v97;
    if ( v97 )
    {
      v97 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = v98;
    if ( v98 )
    {
      v98 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v99;
    if ( v99 )
    {
      v99 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = v100;
    if ( v100 )
    {
      v100 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = v95;
    if ( v95 )
    {
      v95 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v10 + 16LL))(v10);
    }
    return (unsigned int)v5;
  }
}

```

## disassembly

```asm
0x18019e1e8  mov     r11, rsp
0x18019e1eb  mov     [r11+8], rbx
0x18019e1ef  push    rsi
0x18019e1f0  push    rdi
0x18019e1f1  push    r12
0x18019e1f3  push    r14
0x18019e1f5  push    r15
0x18019e1f7  sub     rsp, 0D0h
0x18019e1fe  mov     rax, cs:__security_cookie
0x18019e205  xor     rax, rsp
0x18019e208  mov     [rsp+0F8h+var_38], rax
0x18019e210  mov     r15, r8
0x18019e213  mov     r14, rdx
0x18019e216  xor     r12d, r12d
0x18019e219  mov     [rsp+0F8h+var_C8], r12
0x18019e21e  mov     [rsp+0F8h+var_A0], r12
0x18019e223  mov     [rsp+0F8h+var_A8], r12
0x18019e228  mov     [rsp+0F8h+var_B0], r12
0x18019e22d  mov     [rsp+0F8h+var_B8], r12
0x18019e232  mov     [rsp+0F8h+var_90], r12
0x18019e237  mov     [rsp+0F8h+var_98], r12
0x18019e23c  mov     [rsp+0F8h+string], r12
0x18019e241  mov     [r11-70h], r12
0x18019e245  lea     r9d, [r12+41h]; unsigned int
0x18019e24a  lea     r8d, [r12+42h]; unsigned int
0x18019e24f  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x18019e256  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x18019e25b  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18019e260  nop
0x18019e261  mov     [rsp+0F8h+var_C8], r12
0x18019e266  mov     qword ptr [rsp+0F8h+var_48], r12
0x18019e26e  lea     rdx, [rsp+0F8h+var_48]
0x18019e276  mov     rcx, [rsp+0F8h+var_70]
0x18019e27e  call    cs:__imp_RoActivateInstance
0x18019e285  nop     dword ptr [rax+rax+00h]
0x18019e28a  mov     ebx, eax
0x18019e28c  test    eax, eax
0x18019e28e  js      short loc_18019E2E9
0x18019e290  lea     r8d, [r12+10h]; Size
0x18019e295  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x18019e29c  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x18019e2a3  call    memcmp_0
0x18019e2a8  mov     rcx, qword ptr [rsp+0F8h+var_48]
0x18019e2b0  test    eax, eax
0x18019e2b2  jnz     short loc_18019E2BB
0x18019e2b4  mov     [rsp+0F8h+var_C8], rcx
0x18019e2b9  jmp     short loc_18019E2E9
0x18019e2bb  mov     rax, [rcx]
0x18019e2be  lea     r8, [rsp+0F8h+var_C8]
0x18019e2c3  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x18019e2ca  mov     rax, [rax]
0x18019e2cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e2d2  mov     ebx, eax
0x18019e2d4  mov     rcx, qword ptr [rsp+0F8h+var_48]
0x18019e2dc  mov     rax, [rcx]
0x18019e2df  mov     rax, [rax+10h]
0x18019e2e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e2e8  nop
0x18019e2e9  test    ebx, ebx
0x18019e2eb  jns     loc_18019E3CD
0x18019e2f1  mov     rcx, [rsp+0F8h]; this
0x18019e2f9  mov     r9d, ebx; char *
0x18019e2fc  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019e303  mov     edx, 306h; void *
0x18019e308  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e30d  nop
0x18019e30e  mov     rcx, [rsp+0F8h+string]; string
0x18019e313  call    cs:__imp_WindowsDeleteString
0x18019e31a  nop     dword ptr [rax+rax+00h]
0x18019e31f  mov     [rsp+0F8h+string], r12
0x18019e324  lea     rcx, [rsp+0F8h+var_98]
0x18019e329  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e32e  nop
0x18019e32f  lea     rcx, [rsp+0F8h+var_90]
0x18019e334  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e339  nop
0x18019e33a  mov     rcx, [rsp+0F8h+var_B8]
0x18019e33f  test    rcx, rcx
0x18019e342  jz      short loc_18019E356
0x18019e344  mov     [rsp+0F8h+var_B8], r12
0x18019e349  mov     rax, [rcx]
0x18019e34c  mov     rax, [rax+10h]
0x18019e350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e355  nop
0x18019e356  mov     rcx, [rsp+0F8h+var_B0]
0x18019e35b  test    rcx, rcx
0x18019e35e  jz      short loc_18019E372
0x18019e360  mov     [rsp+0F8h+var_B0], r12
0x18019e365  mov     rax, [rcx]
0x18019e368  mov     rax, [rax+10h]
0x18019e36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e371  nop
0x18019e372  mov     rcx, [rsp+0F8h+var_A8]
0x18019e377  test    rcx, rcx
0x18019e37a  jz      short loc_18019E38E
0x18019e37c  mov     [rsp+0F8h+var_A8], r12
0x18019e381  mov     rax, [rcx]
0x18019e384  mov     rax, [rax+10h]
0x18019e388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e38d  nop
0x18019e38e  mov     rcx, [rsp+0F8h+var_A0]
0x18019e393  test    rcx, rcx
0x18019e396  jz      short loc_18019E3AA
0x18019e398  mov     [rsp+0F8h+var_A0], r12
0x18019e39d  mov     rax, [rcx]
0x18019e3a0  mov     rax, [rax+10h]
0x18019e3a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e3a9  nop
0x18019e3aa  mov     rcx, [rsp+0F8h+var_C8]
0x18019e3af  test    rcx, rcx
0x18019e3b2  jz      short loc_18019E3C6
0x18019e3b4  mov     [rsp+0F8h+var_C8], r12
0x18019e3b9  mov     rax, [rcx]
0x18019e3bc  mov     rax, [rax+10h]
0x18019e3c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e3c5  nop
0x18019e3c6  mov     eax, ebx
0x18019e3c8  jmp     loc_18019EE6E
0x18019e3cd  mov     [rsp+0F8h+var_70], r12
0x18019e3d5  mov     r9d, 45h ; 'E'; unsigned int
0x18019e3db  lea     r8d, [r9+1]; unsigned int
0x18019e3df  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x18019e3e6  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x18019e3eb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18019e3f0  lea     r8, [rsp+0F8h+var_A8]
0x18019e3f5  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x18019e3fc  mov     rcx, [rsp+0F8h+var_70]
0x18019e404  call    cs:__imp_RoGetActivationFactory
0x18019e40b  nop     dword ptr [rax+rax+00h]
0x18019e410  mov     ebx, eax
0x18019e412  test    eax, eax
0x18019e414  jns     loc_18019E4F6
0x18019e41a  mov     rcx, [rsp+0F8h]; this
0x18019e422  mov     r9d, eax; char *
0x18019e425  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019e42c  mov     edx, 308h; void *
0x18019e431  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e436  nop
0x18019e437  mov     rcx, [rsp+0F8h+string]; string
0x18019e43c  call    cs:__imp_WindowsDeleteString
0x18019e443  nop     dword ptr [rax+rax+00h]
0x18019e448  mov     [rsp+0F8h+string], r12
0x18019e44d  lea     rcx, [rsp+0F8h+var_98]
0x18019e452  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e457  nop
0x18019e458  lea     rcx, [rsp+0F8h+var_90]
0x18019e45d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e462  nop
0x18019e463  mov     rcx, [rsp+0F8h+var_B8]
0x18019e468  test    rcx, rcx
0x18019e46b  jz      short loc_18019E47F
0x18019e46d  mov     [rsp+0F8h+var_B8], r12
0x18019e472  mov     rax, [rcx]
0x18019e475  mov     rax, [rax+10h]
0x18019e479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e47e  nop
0x18019e47f  mov     rcx, [rsp+0F8h+var_B0]
0x18019e484  test    rcx, rcx
0x18019e487  jz      short loc_18019E49B
0x18019e489  mov     [rsp+0F8h+var_B0], r12
0x18019e48e  mov     rax, [rcx]
0x18019e491  mov     rax, [rax+10h]
0x18019e495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e49a  nop
0x18019e49b  mov     rcx, [rsp+0F8h+var_A8]
0x18019e4a0  test    rcx, rcx
0x18019e4a3  jz      short loc_18019E4B7
0x18019e4a5  mov     [rsp+0F8h+var_A8], r12
0x18019e4aa  mov     rax, [rcx]
0x18019e4ad  mov     rax, [rax+10h]
0x18019e4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e4b6  nop
0x18019e4b7  mov     rcx, [rsp+0F8h+var_A0]
0x18019e4bc  test    rcx, rcx
0x18019e4bf  jz      short loc_18019E4D3
0x18019e4c1  mov     [rsp+0F8h+var_A0], r12
0x18019e4c6  mov     rax, [rcx]
0x18019e4c9  mov     rax, [rax+10h]
0x18019e4cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e4d2  nop
0x18019e4d3  mov     rcx, [rsp+0F8h+var_C8]
0x18019e4d8  test    rcx, rcx
0x18019e4db  jz      short loc_18019E4EF
0x18019e4dd  mov     [rsp+0F8h+var_C8], r12
0x18019e4e2  mov     rax, [rcx]
0x18019e4e5  mov     rax, [rax+10h]
0x18019e4e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e4ee  nop
0x18019e4ef  mov     eax, ebx
0x18019e4f1  jmp     loc_18019EE6E
0x18019e4f6  mov     rsi, [rsp+0F8h+var_A8]
0x18019e4fb  mov     rax, [rsi]
0x18019e4fe  mov     rdi, [rax+30h]
0x18019e502  lea     rdx, off_18021C8D8; "MBI_SSL"
0x18019e509  lea     rcx, [rsp+0F8h+hstringHeader]
0x18019e50e  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18019e513  nop
0x18019e514  mov     rbx, [rax+18h]
0x18019e518  mov     rcx, r14
0x18019e51b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18019e520  mov     qword ptr [rsp+0F8h+var_48], rax
0x18019e528  lea     rdx, [rsp+0F8h+var_48]
0x18019e530  lea     rcx, [rsp+0F8h+var_68]
0x18019e538  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18019e53d  nop
0x18019e53e  lea     r9, [rsp+0F8h+var_A0]
0x18019e543  mov     r8, rbx
0x18019e546  mov     rdx, [rax+18h]
0x18019e54a  mov     rcx, rsi
0x18019e54d  mov     rax, rdi
0x18019e550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e555  mov     ebx, eax
0x18019e557  test    eax, eax
0x18019e559  jns     loc_18019E63B
0x18019e55f  mov     rcx, [rsp+0F8h]; this
0x18019e567  mov     r9d, eax; char *
0x18019e56a  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019e571  mov     edx, 30Dh; void *
0x18019e576  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e57b  nop
0x18019e57c  mov     rcx, [rsp+0F8h+string]; string
0x18019e581  call    cs:__imp_WindowsDeleteString
0x18019e588  nop     dword ptr [rax+rax+00h]
0x18019e58d  mov     [rsp+0F8h+string], r12
0x18019e592  lea     rcx, [rsp+0F8h+var_98]
0x18019e597  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e59c  nop
0x18019e59d  lea     rcx, [rsp+0F8h+var_90]
0x18019e5a2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e5a7  nop
0x18019e5a8  mov     rcx, [rsp+0F8h+var_B8]
0x18019e5ad  test    rcx, rcx
0x18019e5b0  jz      short loc_18019E5C4
0x18019e5b2  mov     [rsp+0F8h+var_B8], r12
0x18019e5b7  mov     rax, [rcx]
0x18019e5ba  mov     rax, [rax+10h]
0x18019e5be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e5c3  nop
0x18019e5c4  mov     rcx, [rsp+0F8h+var_B0]
0x18019e5c9  test    rcx, rcx
0x18019e5cc  jz      short loc_18019E5E0
0x18019e5ce  mov     [rsp+0F8h+var_B0], r12
0x18019e5d3  mov     rax, [rcx]
0x18019e5d6  mov     rax, [rax+10h]
0x18019e5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e5df  nop
0x18019e5e0  mov     rcx, [rsp+0F8h+var_A8]
0x18019e5e5  test    rcx, rcx
0x18019e5e8  jz      short loc_18019E5FC
0x18019e5ea  mov     [rsp+0F8h+var_A8], r12
0x18019e5ef  mov     rax, [rcx]
0x18019e5f2  mov     rax, [rax+10h]
0x18019e5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e5fb  nop
0x18019e5fc  mov     rcx, [rsp+0F8h+var_A0]
0x18019e601  test    rcx, rcx
0x18019e604  jz      short loc_18019E618
0x18019e606  mov     [rsp+0F8h+var_A0], r12
0x18019e60b  mov     rax, [rcx]
0x18019e60e  mov     rax, [rax+10h]
0x18019e612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e617  nop
0x18019e618  mov     rcx, [rsp+0F8h+var_C8]
0x18019e61d  test    rcx, rcx
0x18019e620  jz      short loc_18019E634
0x18019e622  mov     [rsp+0F8h+var_C8], r12
0x18019e627  mov     rax, [rcx]
0x18019e62a  mov     rax, [rax+10h]
0x18019e62e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e633  nop
0x18019e634  mov     eax, ebx
0x18019e636  jmp     loc_18019EE6E
0x18019e63b  mov     rdi, [rsp+0F8h+var_C8]
0x18019e640  mov     rax, [rdi]
0x18019e643  mov     rbx, [rax+48h]
0x18019e647  call    ?GetMsaApplicationId@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAAEBU_GUID@@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaApplicationId(void)
0x18019e64c  movups  xmm0, xmmword ptr [rax]
0x18019e64f  movdqu  xmmword ptr [rsp+0F8h+var_48], xmm0
0x18019e658  lea     rdx, [rsp+0F8h+var_48]
0x18019e660  mov     rcx, rdi
0x18019e663  mov     rax, rbx
0x18019e666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019e66b  mov     ebx, eax
0x18019e66d  test    eax, eax
0x18019e66f  jns     loc_18019E751
0x18019e675  mov     rcx, [rsp+0F8h]; this
0x18019e67d  mov     r9d, eax; char *
0x18019e680  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019e687  mov     edx, 30Fh; void *
0x18019e68c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019e691  nop
0x18019e692  mov     rcx, [rsp+0F8h+string]; string
0x18019e697  call    cs:__imp_WindowsDeleteString
0x18019e69e  nop     dword ptr [rax+rax+00h]
0x18019e6a3  mov     [rsp+0F8h+string], r12
0x18019e6a8  lea     rcx, [rsp+0F8h+var_98]
0x18019e6ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019e6b2  nop
0x18019e6b3  lea     rcx, [rsp+0F8h+var_90]
0x18019e6b8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
