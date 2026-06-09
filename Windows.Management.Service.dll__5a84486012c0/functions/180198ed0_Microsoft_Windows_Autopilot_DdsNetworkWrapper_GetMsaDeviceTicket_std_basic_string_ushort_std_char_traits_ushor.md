# Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaDeviceTicket(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180198ed0`
- end: `0x180199b25`
- name: `?GetMsaDeviceTicket@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@@Z`
- size: `3157`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1801984ac`

## callees

- `0x18000b820`
- `0x180063dc3`
- `0x180067008`
- `0x180067a54`
- `0x18008019c`
- `0x1800806b0`
- `0x180081f1c`
- `0x1800853a0`
- `0x18008afec`
- `0x18008c244`
- `0x180197f78`
- `0x180198e08`
- `0x180198ed0`
- `0x1801fa010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180199a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180199a30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180198ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019945c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019957d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019965b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019992e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199a47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180198ff5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199112`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199251`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019945c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019957d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019965b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199869`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18019992e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199975`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180199a47`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180198f66`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180198f66`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801990e0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801990e0`

## string_xrefs

- `0x180198fde`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801990fb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019923a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019934a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180199445`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180199644`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019974a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x180199852`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x18019995e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\ddsnetworkwrapper.cpp`
- `0x1801990bb`: `Windows.Security.Authentication.OnlineId.OnlineIdServiceTicketRequest`
- `0x180198f37`: `Windows.Internal.Security.WebAuthentication.AuthenticationManager`

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
  int v94; // [rsp+20h] [rbp-D8h]
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
      v21 = *(_QWORD *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, off_1802168E0) + 24);
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
              McGenEventWrite_EventWriteTransfer(v48, MsaEnvironmentApplicationMismatch, v50, 1, v106);
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
                      v94);
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
                    v94);
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
                  v94);
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
                v94);
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
              v94);
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
            v94);
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
          v94);
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
        v94);
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
      v94);
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
0x180198ed0  mov     r11, rsp
0x180198ed3  mov     [r11+8], rbx
0x180198ed7  push    rsi
0x180198ed8  push    rdi
0x180198ed9  push    r12
0x180198edb  push    r14
0x180198edd  push    r15
0x180198edf  sub     rsp, 0D0h
0x180198ee6  mov     rax, cs:__security_cookie
0x180198eed  xor     rax, rsp
0x180198ef0  mov     [rsp+0F8h+var_38], rax
0x180198ef8  mov     r15, r8
0x180198efb  mov     r14, rdx
0x180198efe  xor     r12d, r12d
0x180198f01  mov     [rsp+0F8h+var_C8], r12
0x180198f06  mov     [rsp+0F8h+var_A0], r12
0x180198f0b  mov     [rsp+0F8h+var_A8], r12
0x180198f10  mov     [rsp+0F8h+var_B0], r12
0x180198f15  mov     [rsp+0F8h+var_B8], r12
0x180198f1a  mov     [rsp+0F8h+var_90], r12
0x180198f1f  mov     [rsp+0F8h+var_98], r12
0x180198f24  mov     [rsp+0F8h+string], r12
0x180198f29  mov     [r11-70h], r12
0x180198f2d  lea     r9d, [r12+41h]; unsigned int
0x180198f32  lea     r8d, [r12+42h]; unsigned int
0x180198f37  lea     rdx, ?RuntimeClass_Windows_Internal_Security_WebAuthentication_AuthenticationManager@@3QBGB; "Windows.Internal.Security.WebAuthentica"...
0x180198f3e  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x180198f43  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180198f48  nop
0x180198f49  mov     [rsp+0F8h+var_C8], r12
0x180198f4e  mov     qword ptr [rsp+0F8h+var_48], r12
0x180198f56  lea     rdx, [rsp+0F8h+var_48]
0x180198f5e  mov     rcx, [rsp+0F8h+var_70]
0x180198f66  call    cs:__imp_RoActivateInstance
0x180198f6c  mov     ebx, eax
0x180198f6e  test    eax, eax
0x180198f70  js      short loc_180198FCB
0x180198f72  lea     r8d, [r12+10h]; Size
0x180198f77  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180198f7e  lea     rcx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb; Buf1
0x180198f85  call    memcmp_0
0x180198f8a  mov     rcx, qword ptr [rsp+0F8h+var_48]
0x180198f92  test    eax, eax
0x180198f94  jnz     short loc_180198F9D
0x180198f96  mov     [rsp+0F8h+var_C8], rcx
0x180198f9b  jmp     short loc_180198FCB
0x180198f9d  mov     rax, [rcx]
0x180198fa0  lea     r8, [rsp+0F8h+var_C8]
0x180198fa5  lea     rdx, _GUID_eb2c0c45_76f9_4a0a_bb73_fcf47d73a4eb
0x180198fac  mov     rax, [rax]
0x180198faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198fb4  mov     ebx, eax
0x180198fb6  mov     rcx, qword ptr [rsp+0F8h+var_48]
0x180198fbe  mov     rax, [rcx]
0x180198fc1  mov     rax, [rax+10h]
0x180198fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180198fca  nop
0x180198fcb  test    ebx, ebx
0x180198fcd  jns     loc_1801990A9
0x180198fd3  mov     rcx, [rsp+0F8h]; this
0x180198fdb  mov     r9d, ebx; char *
0x180198fde  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180198fe5  mov     edx, 306h; void *
0x180198fea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180198fef  nop
0x180198ff0  mov     rcx, [rsp+0F8h+string]; string
0x180198ff5  call    cs:__imp_WindowsDeleteString
0x180198ffb  mov     [rsp+0F8h+string], r12
0x180199000  lea     rcx, [rsp+0F8h+var_98]
0x180199005  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18019900a  nop
0x18019900b  lea     rcx, [rsp+0F8h+var_90]
0x180199010  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199015  nop
0x180199016  mov     rcx, [rsp+0F8h+var_B8]
0x18019901b  test    rcx, rcx
0x18019901e  jz      short loc_180199032
0x180199020  mov     [rsp+0F8h+var_B8], r12
0x180199025  mov     rax, [rcx]
0x180199028  mov     rax, [rax+10h]
0x18019902c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199031  nop
0x180199032  mov     rcx, [rsp+0F8h+var_B0]
0x180199037  test    rcx, rcx
0x18019903a  jz      short loc_18019904E
0x18019903c  mov     [rsp+0F8h+var_B0], r12
0x180199041  mov     rax, [rcx]
0x180199044  mov     rax, [rax+10h]
0x180199048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019904d  nop
0x18019904e  mov     rcx, [rsp+0F8h+var_A8]
0x180199053  test    rcx, rcx
0x180199056  jz      short loc_18019906A
0x180199058  mov     [rsp+0F8h+var_A8], r12
0x18019905d  mov     rax, [rcx]
0x180199060  mov     rax, [rax+10h]
0x180199064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199069  nop
0x18019906a  mov     rcx, [rsp+0F8h+var_A0]
0x18019906f  test    rcx, rcx
0x180199072  jz      short loc_180199086
0x180199074  mov     [rsp+0F8h+var_A0], r12
0x180199079  mov     rax, [rcx]
0x18019907c  mov     rax, [rax+10h]
0x180199080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199085  nop
0x180199086  mov     rcx, [rsp+0F8h+var_C8]
0x18019908b  test    rcx, rcx
0x18019908e  jz      short loc_1801990A2
0x180199090  mov     [rsp+0F8h+var_C8], r12
0x180199095  mov     rax, [rcx]
0x180199098  mov     rax, [rax+10h]
0x18019909c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801990a1  nop
0x1801990a2  mov     eax, ebx
0x1801990a4  jmp     loc_180199AFC
0x1801990a9  mov     [rsp+0F8h+var_70], r12
0x1801990b1  mov     r9d, 45h ; 'E'; unsigned int
0x1801990b7  lea     r8d, [r9+1]; unsigned int
0x1801990bb  lea     rdx, ?RuntimeClass_Windows_Security_Authentication_OnlineId_OnlineIdServiceTicketRequest@@3QBGB; "Windows.Security.Authentication.OnlineI"...
0x1801990c2  lea     rcx, [rsp+0F8h+hstringHeader]; hstringHeader
0x1801990c7  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801990cc  lea     r8, [rsp+0F8h+var_A8]
0x1801990d1  lea     rdx, _GUID_bebb0a08_9e73_4077_9614_08614c0bc245
0x1801990d8  mov     rcx, [rsp+0F8h+var_70]
0x1801990e0  call    cs:__imp_RoGetActivationFactory
0x1801990e6  mov     ebx, eax
0x1801990e8  test    eax, eax
0x1801990ea  jns     loc_1801991C6
0x1801990f0  mov     rcx, [rsp+0F8h]; this
0x1801990f8  mov     r9d, eax; char *
0x1801990fb  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199102  mov     edx, 308h; void *
0x180199107  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019910c  nop
0x18019910d  mov     rcx, [rsp+0F8h+string]; string
0x180199112  call    cs:__imp_WindowsDeleteString
0x180199118  mov     [rsp+0F8h+string], r12
0x18019911d  lea     rcx, [rsp+0F8h+var_98]
0x180199122  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199127  nop
0x180199128  lea     rcx, [rsp+0F8h+var_90]
0x18019912d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199132  nop
0x180199133  mov     rcx, [rsp+0F8h+var_B8]
0x180199138  test    rcx, rcx
0x18019913b  jz      short loc_18019914F
0x18019913d  mov     [rsp+0F8h+var_B8], r12
0x180199142  mov     rax, [rcx]
0x180199145  mov     rax, [rax+10h]
0x180199149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019914e  nop
0x18019914f  mov     rcx, [rsp+0F8h+var_B0]
0x180199154  test    rcx, rcx
0x180199157  jz      short loc_18019916B
0x180199159  mov     [rsp+0F8h+var_B0], r12
0x18019915e  mov     rax, [rcx]
0x180199161  mov     rax, [rax+10h]
0x180199165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019916a  nop
0x18019916b  mov     rcx, [rsp+0F8h+var_A8]
0x180199170  test    rcx, rcx
0x180199173  jz      short loc_180199187
0x180199175  mov     [rsp+0F8h+var_A8], r12
0x18019917a  mov     rax, [rcx]
0x18019917d  mov     rax, [rax+10h]
0x180199181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199186  nop
0x180199187  mov     rcx, [rsp+0F8h+var_A0]
0x18019918c  test    rcx, rcx
0x18019918f  jz      short loc_1801991A3
0x180199191  mov     [rsp+0F8h+var_A0], r12
0x180199196  mov     rax, [rcx]
0x180199199  mov     rax, [rax+10h]
0x18019919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801991a2  nop
0x1801991a3  mov     rcx, [rsp+0F8h+var_C8]
0x1801991a8  test    rcx, rcx
0x1801991ab  jz      short loc_1801991BF
0x1801991ad  mov     [rsp+0F8h+var_C8], r12
0x1801991b2  mov     rax, [rcx]
0x1801991b5  mov     rax, [rax+10h]
0x1801991b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801991be  nop
0x1801991bf  mov     eax, ebx
0x1801991c1  jmp     loc_180199AFC
0x1801991c6  mov     rsi, [rsp+0F8h+var_A8]
0x1801991cb  mov     rax, [rsi]
0x1801991ce  mov     rdi, [rax+30h]
0x1801991d2  lea     rdx, off_1802168E0; "MBI_SSL"
0x1801991d9  lea     rcx, [rsp+0F8h+hstringHeader]
0x1801991de  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1801991e3  nop
0x1801991e4  mov     rbx, [rax+18h]
0x1801991e8  mov     rcx, r14
0x1801991eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801991f0  mov     qword ptr [rsp+0F8h+var_48], rax
0x1801991f8  lea     rdx, [rsp+0F8h+var_48]
0x180199200  lea     rcx, [rsp+0F8h+var_68]
0x180199208  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18019920d  nop
0x18019920e  lea     r9, [rsp+0F8h+var_A0]
0x180199213  mov     r8, rbx
0x180199216  mov     rdx, [rax+18h]
0x18019921a  mov     rcx, rsi
0x18019921d  mov     rax, rdi
0x180199220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199225  mov     ebx, eax
0x180199227  test    eax, eax
0x180199229  jns     loc_180199305
0x18019922f  mov     rcx, [rsp+0F8h]; this
0x180199237  mov     r9d, eax; char *
0x18019923a  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199241  mov     edx, 30Dh; void *
0x180199246  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019924b  nop
0x18019924c  mov     rcx, [rsp+0F8h+string]; string
0x180199251  call    cs:__imp_WindowsDeleteString
0x180199257  mov     [rsp+0F8h+string], r12
0x18019925c  lea     rcx, [rsp+0F8h+var_98]
0x180199261  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199266  nop
0x180199267  lea     rcx, [rsp+0F8h+var_90]
0x18019926c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199271  nop
0x180199272  mov     rcx, [rsp+0F8h+var_B8]
0x180199277  test    rcx, rcx
0x18019927a  jz      short loc_18019928E
0x18019927c  mov     [rsp+0F8h+var_B8], r12
0x180199281  mov     rax, [rcx]
0x180199284  mov     rax, [rax+10h]
0x180199288  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019928d  nop
0x18019928e  mov     rcx, [rsp+0F8h+var_B0]
0x180199293  test    rcx, rcx
0x180199296  jz      short loc_1801992AA
0x180199298  mov     [rsp+0F8h+var_B0], r12
0x18019929d  mov     rax, [rcx]
0x1801992a0  mov     rax, [rax+10h]
0x1801992a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801992a9  nop
0x1801992aa  mov     rcx, [rsp+0F8h+var_A8]
0x1801992af  test    rcx, rcx
0x1801992b2  jz      short loc_1801992C6
0x1801992b4  mov     [rsp+0F8h+var_A8], r12
0x1801992b9  mov     rax, [rcx]
0x1801992bc  mov     rax, [rax+10h]
0x1801992c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801992c5  nop
0x1801992c6  mov     rcx, [rsp+0F8h+var_A0]
0x1801992cb  test    rcx, rcx
0x1801992ce  jz      short loc_1801992E2
0x1801992d0  mov     [rsp+0F8h+var_A0], r12
0x1801992d5  mov     rax, [rcx]
0x1801992d8  mov     rax, [rax+10h]
0x1801992dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801992e1  nop
0x1801992e2  mov     rcx, [rsp+0F8h+var_C8]
0x1801992e7  test    rcx, rcx
0x1801992ea  jz      short loc_1801992FE
0x1801992ec  mov     [rsp+0F8h+var_C8], r12
0x1801992f1  mov     rax, [rcx]
0x1801992f4  mov     rax, [rax+10h]
0x1801992f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801992fd  nop
0x1801992fe  mov     eax, ebx
0x180199300  jmp     loc_180199AFC
0x180199305  mov     rdi, [rsp+0F8h+var_C8]
0x18019930a  mov     rax, [rdi]
0x18019930d  mov     rbx, [rax+48h]
0x180199311  call    ?GetMsaApplicationId@DdsNetworkWrapper@Autopilot@Windows@Microsoft@@AEAAAEBU_GUID@@XZ; Microsoft::Windows::Autopilot::DdsNetworkWrapper::GetMsaApplicationId(void)
0x180199316  movups  xmm0, xmmword ptr [rax]
0x180199319  movdqu  xmmword ptr [rsp+0F8h+var_48], xmm0
0x180199322  lea     rdx, [rsp+0F8h+var_48]
0x18019932a  mov     rcx, rdi
0x18019932d  mov     rax, rbx
0x180199330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180199335  mov     ebx, eax
0x180199337  test    eax, eax
0x180199339  jns     loc_180199415
0x18019933f  mov     rcx, [rsp+0F8h]; this
0x180199347  mov     r9d, eax; char *
0x18019934a  lea     r8, aOnecoreuapAdmi_133; "onecoreuap\\admin\\moderndeployment\\au"...
0x180199351  mov     edx, 30Fh; void *
0x180199356  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019935b  nop
0x18019935c  mov     rcx, [rsp+0F8h+string]; string
0x180199361  call    cs:__imp_WindowsDeleteString
0x180199367  mov     [rsp+0F8h+string], r12
0x18019936c  lea     rcx, [rsp+0F8h+var_98]
0x180199371  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199376  nop
0x180199377  lea     rcx, [rsp+0F8h+var_90]
0x18019937c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180199381  nop
0x180199382  mov     rcx, [rsp+0F8h+var_B8]
0x180199387  test    rcx, rcx
0x18019938a  jz      short loc_18019939E
0x18019938c  mov     [rsp+0F8h+var_B8], r12
0x180199391  mov     rax, [rcx]
  ... truncated ...
```
