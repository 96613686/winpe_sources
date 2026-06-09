# FirstSync::EnrollmentStatusTracking::UpdateTrackingStatus(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus)

- ea: `0x1800a7c04`
- end: `0x1800a8485`
- name: `?UpdateTrackingStatus@EnrollmentStatusTracking@FirstSync@@SAJPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4ResourceTrackingStatus@12@@Z`
- size: `2177`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a1dcc`
- `0x1800a22d8`

## callees

- `0x180004d50`
- `0x18000a2a4`
- `0x18000cfdc`
- `0x18000d724`
- `0x180015720`
- `0x180015e4c`
- `0x180015f70`
- `0x1800168d0`
- `0x1800169b8`
- `0x180022334`
- `0x18003446c`
- `0x180092c8c`
- `0x1800a597c`
- `0x1800a6278`
- `0x1800a6368`
- `0x1800a68dc`
- `0x1800a6cbc`
- `0x1800a6d6c`
- `0x1800a6ddc`
- `0x1800a70b8`
- `0x1800a762c`
- `0x1800a7b4c`
- `0x1800a7c04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7f2e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a7f2e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a7f59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a838c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a7f59`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a838c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7d7e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a7d7e`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall FirstSync::EnrollmentStatusTracking::UpdateTrackingStatus(
        __int64 a1,
        __int64 a2,
        const unsigned __int16 *a3,
        int a4)
{
  int ResourceTypeObject; // eax
  unsigned int v6; // ebx
  __int64 result; // rax
  const unsigned __int16 *v8; // rsi
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // rax
  const WCHAR *v12; // rax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // ebx
  int ResourceName; // eax
  unsigned int v19; // ebx
  const unsigned __int16 *v20; // rdi
  const WCHAR *v21; // rax
  unsigned int ValueW; // eax
  unsigned int v23; // eax
  int v24; // ecx
  unsigned int v25; // ebx
  const unsigned __int16 *v26; // rbx
  unsigned int v27; // ebx
  int ResourceTrackingStatusObject; // eax
  unsigned int v29; // r12d
  int v30; // eax
  __int64 v31; // rdx
  unsigned int v32; // r12d
  int v33; // ecx
  __int64 *v34; // rdx
  unsigned int v35; // eax
  unsigned int v36; // ebx
  int dwOptions; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-2C8h]
  HKEY hKey; // [rsp+50h] [rbp-298h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-290h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-288h] BYREF
  unsigned int pvData; // [rsp+64h] [rbp-284h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-280h] BYREF
  _BYTE v46[24]; // [rsp+70h] [rbp-278h] BYREF
  unsigned __int16 *v47[2]; // [rsp+88h] [rbp-260h] BYREF
  unsigned __int16 *v48[2]; // [rsp+98h] [rbp-250h] BYREF
  const unsigned __int16 *v49; // [rsp+A8h] [rbp-240h] BYREF
  __int64 v50; // [rsp+B0h] [rbp-238h]
  _BYTE v51[32]; // [rsp+B8h] [rbp-230h] BYREF
  _BYTE v52[32]; // [rsp+D8h] [rbp-210h] BYREF
  _OWORD v53[2]; // [rsp+F8h] [rbp-1F0h] BYREF
  unsigned __int16 *v54[2]; // [rsp+118h] [rbp-1D0h] BYREF
  _BYTE v55[40]; // [rsp+138h] [rbp-1B0h] BYREF
  _BYTE v56[336]; // [rsp+160h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v50 = a2;
  *(_DWORD *)Data = a4;
  *(_OWORD *)v47 = 0;
  *(_OWORD *)v48 = 0;
  ResourceTypeObject = FirstSync::EnrollmentStatusTracking::GetResourceTypeObject(
                         a3,
                         (struct FirstSync::EnrollmentStatusTracking::ResourceTypeMap *)v47);
  v6 = ResourceTypeObject;
  if ( ResourceTypeObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
      (const char *)(unsigned int)ResourceTypeObject,
      dwOptions);
    std::wstring::~wstring(a2);
    return v6;
  }
  try
  {
    hKey = 0;
    v8 = v48[0];
    v9 = std::wstring::wstring(v55, v48[0]);
    v10 = std::wstring::wstring(
            v53,
            L"SOFTWARE\\Microsoft\\Provisioning\\Diagnostics\\AutoPilot\\WindowsAutopilotDiagnostics");
    v11 = std::operator+<unsigned short>(v54, v10, L"\\");
    std::operator+<unsigned short>(v51, v11, v9);
    std::wstring::~wstring(v54);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v55);
    dwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( v13 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x10F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
              (const char *)v13,
              dwOptionsa);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v14;
    }
    std::wstring::wstring(v52);
    std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(v46);
    v16 = FirstSync::EnrollmentStatusTracking::TokenizeLocUri(a2, v46);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)v16,
        dwOptionsa);
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v17;
    }
    ResourceName = FirstSync::EnrollmentStatusTracking::GetResourceName(v46, v52);
    v19 = ResourceName;
    if ( ResourceName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)ResourceName,
        dwOptionsa);
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v19;
    }
    v20 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v52);
    v49 = v20;
    pvData = -1;
    pcbData = 4;
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v21, v20, 0x10u, 0, &pvData, &pcbData);
    if ( ValueW == 2 )
    {
      v23 = RegSetValueExW(hKey, v20, 0, 4u, Data, 4u);
      if ( v23 )
      {
        v25 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x12D,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
                (const char *)v23,
                dwOptionsb);
        std::vector<std::wstring>::_Tidy(v46);
        std::wstring::~wstring(v52);
        std::wstring::~wstring(v51);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(a2);
        return v25;
      }
      v26 = v47[0];
      if ( (byte_1800FB142 & 1) != 0 )
        McTemplateU0zzz_EventWriteTransfer(
          v24,
          (unsigned int)EnterpriseDiagnosticsResourceProvisioningTrackingStarted,
          (_DWORD)v8,
          (_DWORD)v20,
          (__int64)v47[0]);
    }
    else
    {
      if ( ValueW )
      {
        v27 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x132,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
                (const char *)ValueW,
                dwOptionsb);
        std::vector<std::wstring>::_Tidy(v46);
        std::wstring::~wstring(v52);
        std::wstring::~wstring(v51);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(a2);
        return v27;
      }
      v26 = v47[0];
    }
    v53[0] = 0;
    *(_OWORD *)v54 = 0;
    ResourceTrackingStatusObject = FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(pvData, v53);
    v29 = ResourceTrackingStatusObject;
    if ( ResourceTrackingStatusObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)ResourceTrackingStatusObject,
        dwOptionsb);
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v29;
    }
    v30 = FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(*(unsigned int *)Data, v54);
    v32 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)v30,
        dwOptionsb);
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v32;
    }
    if ( pvData == *(_DWORD *)Data || pvData == -1 )
    {
LABEL_65:
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return 0;
    }
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::UpdateResourceProvisioningTrackingStatusTelemetry(
      (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v56,
      v31,
      &v49,
      (const unsigned __int16 **)v53 + 1,
      (const unsigned __int16 **)v47,
      (const unsigned __int16 **)v48);
    v33 = *(_DWORD *)Data;
    if ( *(int *)Data > 6 )
    {
      v33 = *(_DWORD *)Data - 7;
      if ( *(_DWORD *)Data == 7 )
      {
        if ( (byte_1800FB142 & 1) != 0 )
        {
          v34 = EnterpriseDiagnosticsResourceProvisioningInstalling;
          goto LABEL_61;
        }
      }
      else
      {
        v33 = *(_DWORD *)Data - 8;
        if ( *(_DWORD *)Data == 8 )
        {
          if ( (byte_1800FB142 & 1) != 0 )
          {
            v34 = EnterpriseDiagnosticsResourceProvisioningPendingInstallationRetry;
            goto LABEL_61;
          }
        }
        else
        {
          v33 = *(_DWORD *)Data - 9;
          if ( *(_DWORD *)Data == 9 )
          {
            if ( (byte_1800FB142 & 2) != 0 )
            {
              v34 = EnterpriseDiagnosticsResourceProvisioningInstallationFailed;
              goto LABEL_61;
            }
          }
          else
          {
            v33 = *(_DWORD *)Data - 10;
            if ( *(_DWORD *)Data != 10 )
            {
              if ( *(_DWORD *)Data == 11 )
              {
                if ( (byte_1800FB142 & 4) != 0 )
                  McTemplateU0zzz_EventWriteTransfer(
                    1,
                    (unsigned int)EnterpriseDiagnosticsResourceProvisioningStatusUnknown,
                    (_DWORD)v8,
                    (_DWORD)v20,
                    (__int64)v26);
                FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::LogResourceTrackingStatusUnknown(
                  (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v56,
                  v20,
                  v26,
                  v8);
              }
              goto LABEL_62;
            }
            if ( (byte_1800FB142 & 1) != 0 )
            {
              v34 = EnterpriseDiagnosticsResourceProvisioningInstallationComplete;
              goto LABEL_61;
            }
          }
        }
      }
    }
    else if ( *(_DWORD *)Data == 6 )
    {
      if ( (byte_1800FB142 & 1) != 0 )
      {
        v34 = EnterpriseDiagnosticsResourceProvisioningPendingUserSession;
        goto LABEL_61;
      }
    }
    else if ( *(_DWORD *)Data )
    {
      v33 = *(_DWORD *)Data - 1;
      if ( *(_DWORD *)Data == 1 )
      {
        if ( (byte_1800FB142 & 1) != 0 )
        {
          v34 = EnterpriseDiagnosticsResourceProvisioningInitializing;
          goto LABEL_61;
        }
      }
      else
      {
        v33 = *(_DWORD *)Data - 2;
        if ( *(_DWORD *)Data == 2 )
        {
          if ( (byte_1800FB142 & 1) != 0 )
          {
            v34 = EnterpriseDiagnosticsResourceProvisioningDownloading;
            goto LABEL_61;
          }
        }
        else
        {
          v33 = *(_DWORD *)Data - 3;
          if ( *(_DWORD *)Data == 3 )
          {
            if ( (byte_1800FB142 & 1) != 0 )
            {
              v34 = EnterpriseDiagnosticsResourceProvisioningPendingDownloadRetry;
              goto LABEL_61;
            }
          }
          else
          {
            v33 = *(_DWORD *)Data - 4;
            if ( *(_DWORD *)Data != 4 )
            {
              if ( *(_DWORD *)Data != 5 || (byte_1800FB142 & 1) == 0 )
                goto LABEL_62;
              v34 = EnterpriseDiagnosticsResourceProvisioningDownloadCompleted;
              goto LABEL_61;
            }
            if ( (byte_1800FB142 & 2) != 0 )
            {
              v34 = EnterpriseDiagnosticsResourceProvisioningDownloadFailed;
LABEL_61:
              McTemplateU0zzz_EventWriteTransfer(v33, (_DWORD)v34, (_DWORD)v8, (_DWORD)v20, (__int64)v26);
            }
          }
        }
      }
    }
    else if ( (byte_1800FB142 & 1) != 0 )
    {
      v34 = EnterpriseDiagnosticsResourceProvisioningTrackingStarted;
      goto LABEL_61;
    }
LABEL_62:
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::Stop(
      (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v56,
      v20,
      v54[1],
      v26,
      v8);
    v35 = RegSetValueExW(hKey, v20, 0, 4u, Data, 4u);
    if ( v35 )
    {
      v36 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
              (const char *)v35,
              dwOptionsc);
      FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::~UpdateResourceProvisioningTrackingStatusTelemetry((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v56);
      std::vector<std::wstring>::_Tidy(v46);
      std::wstring::~wstring(v52);
      std::wstring::~wstring(v51);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v36;
    }
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::~UpdateResourceProvisioningTrackingStatusTelemetry((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v56);
    goto LABEL_65;
  }
  catch ( ... )
  {
    pcbData = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x180,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
                v15);
    std::wstring::~wstring(v50);
    return pcbData;
  }
  return result;
}

```

## disassembly

```asm
0x1800a7c04  mov     [rsp+arg_0], rbx
0x1800a7c09  push    rsi
0x1800a7c0a  push    rdi
0x1800a7c0b  push    r12
0x1800a7c0d  push    r14
0x1800a7c0f  push    r15
0x1800a7c11  sub     rsp, 2C0h
0x1800a7c18  mov     rax, cs:__security_cookie
0x1800a7c1f  xor     rax, rsp
0x1800a7c22  mov     [rsp+2E8h+var_38], rax
0x1800a7c2a  mov     r14, rdx
0x1800a7c2d  mov     [rsp+2E8h+var_238], rdx
0x1800a7c35  mov     dword ptr [rsp+2E8h+Data], r9d
0x1800a7c3a  xorps   xmm0, xmm0
0x1800a7c3d  movups  xmmword ptr [rsp+2E8h+var_260], xmm0
0x1800a7c45  movups  xmmword ptr [rsp+2E8h+var_250], xmm0
0x1800a7c4d  lea     rdx, [rsp+2E8h+var_260]; struct FirstSync::EnrollmentStatusTracking::ResourceTypeMap *
0x1800a7c55  mov     rcx, r8; unsigned __int16 *
0x1800a7c58  call    ?GetResourceTypeObject@EnrollmentStatusTracking@FirstSync@@CAJPEBGPEAUResourceTypeMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTypeObject(ushort const *,FirstSync::EnrollmentStatusTracking::ResourceTypeMap *)
0x1800a7c5d  mov     ebx, eax
0x1800a7c5f  test    eax, eax
0x1800a7c61  jns     short loc_1800A7C8F
0x1800a7c63  mov     rcx, [rsp+2E8h]; this
0x1800a7c6b  mov     r9d, eax; char *
0x1800a7c6e  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7c75  mov     edx, 0FFh; void *
0x1800a7c7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7c7f  nop
0x1800a7c80  mov     rcx, r14
0x1800a7c83  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7c88  mov     eax, ebx
0x1800a7c8a  jmp     loc_1800A845D
0x1800a7c8f  mov     [rsp+2E8h+hKey], 0
0x1800a7c98  mov     rsi, [rsp+2E8h+var_250]
0x1800a7ca0  mov     rdx, rsi
0x1800a7ca3  lea     rcx, [rsp+2E8h+var_1B0]
0x1800a7cab  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7cb0  mov     rbx, rax
0x1800a7cb3  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Provisioning\\Diag"...
0x1800a7cba  lea     rcx, [rsp+2E8h+var_1F0]
0x1800a7cc2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a7cc7  nop
0x1800a7cc8  lea     r8, asc_1800D9938; "\\"
0x1800a7ccf  mov     rdx, rax
0x1800a7cd2  lea     rcx, [rsp+2E8h+var_1D0]
0x1800a7cda  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800a7cdf  nop
0x1800a7ce0  mov     r8, rbx
0x1800a7ce3  mov     rdx, rax
0x1800a7ce6  lea     rcx, [rsp+2E8h+var_230]
0x1800a7cee  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800a7cf3  nop
0x1800a7cf4  lea     rcx, [rsp+2E8h+var_1D0]
0x1800a7cfc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7d01  nop
0x1800a7d02  lea     rcx, [rsp+2E8h+var_1F0]
0x1800a7d0a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7d0f  nop
0x1800a7d10  lea     rcx, [rsp+2E8h+var_1B0]
0x1800a7d18  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7d1d  mov     [rsp+2E8h+dwDisposition], 0
0x1800a7d25  xor     edx, edx
0x1800a7d27  lea     rcx, [rsp+2E8h+hKey]
0x1800a7d2c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a7d31  lea     rcx, [rsp+2E8h+var_230]
0x1800a7d39  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7d3e  mov     rdx, rax; lpSubKey
0x1800a7d41  lea     rax, [rsp+2E8h+dwDisposition]
0x1800a7d46  mov     [rsp+2E8h+lpdwDisposition], rax; lpdwDisposition
0x1800a7d4b  lea     rax, [rsp+2E8h+hKey]
0x1800a7d50  mov     [rsp+2E8h+phkResult], rax; phkResult
0x1800a7d55  mov     [rsp+2E8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a7d5e  mov     [rsp+2E8h+samDesired], 0F003Fh; samDesired
0x1800a7d66  mov     [rsp+2E8h+dwOptions], 0; int
0x1800a7d6e  xor     r9d, r9d; lpClass
0x1800a7d71  xor     r8d, r8d; Reserved
0x1800a7d74  mov     r15, 0FFFFFFFF80000002h
0x1800a7d7b  mov     rcx, r15; hKey
0x1800a7d7e  call    cs:__imp_RegCreateKeyExW
0x1800a7d84  test    eax, eax
0x1800a7d86  jz      short loc_1800A7DCE
0x1800a7d88  mov     rcx, [rsp+2E8h]; this
0x1800a7d90  mov     r9d, eax; char *
0x1800a7d93  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7d9a  mov     edx, 10Fh; void *
0x1800a7d9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a7da4  mov     ebx, eax
0x1800a7da6  lea     rcx, [rsp+2E8h+var_230]
0x1800a7dae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7db3  nop
0x1800a7db4  lea     rcx, [rsp+2E8h+hKey]
0x1800a7db9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a7dbe  nop
0x1800a7dbf  mov     rcx, r14
0x1800a7dc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7dc7  mov     eax, ebx
0x1800a7dc9  jmp     loc_1800A845D
0x1800a7dce  lea     rcx, [rsp+2E8h+var_210]
0x1800a7dd6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a7ddb  nop
0x1800a7ddc  lea     rcx, [rsp+2E8h+var_278]
0x1800a7de1  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800a7de6  nop
0x1800a7de7  lea     rdx, [rsp+2E8h+var_278]
0x1800a7dec  mov     rcx, r14
0x1800a7def  call    ?TokenizeLocUri@EnrollmentStatusTracking@FirstSync@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; FirstSync::EnrollmentStatusTracking::TokenizeLocUri(std::wstring const &,std::vector<std::wstring> &)
0x1800a7df4  mov     ebx, eax
0x1800a7df6  test    eax, eax
0x1800a7df8  jns     short loc_1800A7E58
0x1800a7dfa  mov     rcx, [rsp+2E8h]; this
0x1800a7e02  mov     r9d, eax; char *
0x1800a7e05  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7e0c  mov     edx, 114h; void *
0x1800a7e11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7e16  nop
0x1800a7e17  lea     rcx, [rsp+2E8h+var_278]
0x1800a7e1c  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a7e21  nop
0x1800a7e22  lea     rcx, [rsp+2E8h+var_210]
0x1800a7e2a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7e2f  nop
0x1800a7e30  lea     rcx, [rsp+2E8h+var_230]
0x1800a7e38  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7e3d  nop
0x1800a7e3e  lea     rcx, [rsp+2E8h+hKey]
0x1800a7e43  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a7e48  nop
0x1800a7e49  mov     rcx, r14
0x1800a7e4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7e51  mov     eax, ebx
0x1800a7e53  jmp     loc_1800A845D
0x1800a7e58  lea     rdx, [rsp+2E8h+var_210]
0x1800a7e60  lea     rcx, [rsp+2E8h+var_278]
0x1800a7e65  call    ?GetResourceName@EnrollmentStatusTracking@FirstSync@@CAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; FirstSync::EnrollmentStatusTracking::GetResourceName(std::vector<std::wstring> &,std::wstring &)
0x1800a7e6a  mov     ebx, eax
0x1800a7e6c  test    eax, eax
0x1800a7e6e  jns     short loc_1800A7ECE
0x1800a7e70  mov     rcx, [rsp+2E8h]; this
0x1800a7e78  mov     r9d, eax; char *
0x1800a7e7b  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7e82  mov     edx, 115h; void *
0x1800a7e87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a7e8c  nop
0x1800a7e8d  lea     rcx, [rsp+2E8h+var_278]
0x1800a7e92  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a7e97  nop
0x1800a7e98  lea     rcx, [rsp+2E8h+var_210]
0x1800a7ea0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7ea5  nop
0x1800a7ea6  lea     rcx, [rsp+2E8h+var_230]
0x1800a7eae  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7eb3  nop
0x1800a7eb4  lea     rcx, [rsp+2E8h+hKey]
0x1800a7eb9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a7ebe  nop
0x1800a7ebf  mov     rcx, r14
0x1800a7ec2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7ec7  mov     eax, ebx
0x1800a7ec9  jmp     loc_1800A845D
0x1800a7ece  lea     rcx, [rsp+2E8h+var_210]
0x1800a7ed6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7edb  mov     rdi, rax
0x1800a7ede  mov     [rsp+2E8h+var_240], rax
0x1800a7ee6  mov     [rsp+2E8h+pvData], 0FFFFFFFFh
0x1800a7eee  mov     ebx, 4
0x1800a7ef3  mov     [rsp+2E8h+pcbData], ebx
0x1800a7ef7  lea     rcx, [rsp+2E8h+var_230]
0x1800a7eff  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a7f04  mov     rdx, rax; lpSubKey
0x1800a7f07  lea     rax, [rsp+2E8h+pcbData]
0x1800a7f0c  mov     [rsp+2E8h+lpSecurityAttributes], rax; pcbData
0x1800a7f11  lea     rax, [rsp+2E8h+pvData]
0x1800a7f16  mov     qword ptr [rsp+2E8h+samDesired], rax; pvData
0x1800a7f1b  mov     qword ptr [rsp+2E8h+dwOptions], 0; int
0x1800a7f24  lea     r9d, [rbx+0Ch]; dwFlags
0x1800a7f28  mov     r8, rdi; lpValue
0x1800a7f2b  mov     rcx, r15; hkey
0x1800a7f2e  call    cs:__imp_RegGetValueW
0x1800a7f34  cmp     eax, 2
0x1800a7f37  jnz     loc_1800A7FF3
0x1800a7f3d  mov     [rsp+2E8h+samDesired], ebx; cbData
0x1800a7f41  lea     rax, [rsp+2E8h+Data]
0x1800a7f46  mov     qword ptr [rsp+2E8h+dwOptions], rax; unsigned int
0x1800a7f4b  mov     r9d, ebx; dwType
0x1800a7f4e  xor     r8d, r8d; Reserved
0x1800a7f51  mov     rdx, rdi; lpValueName
0x1800a7f54  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800a7f59  call    cs:__imp_RegSetValueExW
0x1800a7f5f  test    eax, eax
0x1800a7f61  jz      short loc_1800A7FC2
0x1800a7f63  mov     rcx, [rsp+2E8h]; this
0x1800a7f6b  mov     r9d, eax; char *
0x1800a7f6e  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a7f75  mov     edx, 12Dh; void *
0x1800a7f7a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a7f7f  mov     ebx, eax
0x1800a7f81  lea     rcx, [rsp+2E8h+var_278]
0x1800a7f86  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a7f8b  nop
0x1800a7f8c  lea     rcx, [rsp+2E8h+var_210]
0x1800a7f94  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7f99  nop
0x1800a7f9a  lea     rcx, [rsp+2E8h+var_230]
0x1800a7fa2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7fa7  nop
0x1800a7fa8  lea     rcx, [rsp+2E8h+hKey]
0x1800a7fad  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a7fb2  nop
0x1800a7fb3  mov     rcx, r14
0x1800a7fb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a7fbb  mov     eax, ebx
0x1800a7fbd  jmp     loc_1800A845D
0x1800a7fc2  mov     r15b, 1
0x1800a7fc5  mov     rbx, [rsp+2E8h+var_260]
0x1800a7fcd  test    cs:byte_1800FB142, r15b
0x1800a7fd4  jz      loc_1800A8061
0x1800a7fda  mov     qword ptr [rsp+2E8h+dwOptions], rbx
0x1800a7fdf  mov     r9, rdi
0x1800a7fe2  mov     r8, rsi
0x1800a7fe5  lea     rdx, EnterpriseDiagnosticsResourceProvisioningTrackingStarted
0x1800a7fec  call    McTemplateU0zzz_EventWriteTransfer
0x1800a7ff1  jmp     short loc_1800A8061
0x1800a7ff3  test    eax, eax
0x1800a7ff5  jz      short loc_1800A8056
0x1800a7ff7  mov     rcx, [rsp+2E8h]; this
0x1800a7fff  mov     r9d, eax; char *
0x1800a8002  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a8009  mov     edx, 132h; void *
0x1800a800e  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a8013  mov     ebx, eax
0x1800a8015  lea     rcx, [rsp+2E8h+var_278]
0x1800a801a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a801f  nop
0x1800a8020  lea     rcx, [rsp+2E8h+var_210]
0x1800a8028  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a802d  nop
0x1800a802e  lea     rcx, [rsp+2E8h+var_230]
0x1800a8036  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a803b  nop
0x1800a803c  lea     rcx, [rsp+2E8h+hKey]
0x1800a8041  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a8046  nop
0x1800a8047  mov     rcx, r14
0x1800a804a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a804f  mov     eax, ebx
0x1800a8051  jmp     loc_1800A845D
0x1800a8056  mov     r15b, 1
0x1800a8059  mov     rbx, [rsp+2E8h+var_260]
0x1800a8061  xorps   xmm0, xmm0
0x1800a8064  movups  [rsp+2E8h+var_1F0], xmm0
0x1800a806c  xorps   xmm1, xmm1
0x1800a806f  movups  xmmword ptr [rsp+2E8h+var_1D0], xmm1
0x1800a8077  lea     rdx, [rsp+2E8h+var_1F0]
0x1800a807f  mov     ecx, [rsp+2E8h+pvData]
0x1800a8083  call    ?GetResourceTrackingStatusObject@EnrollmentStatusTracking@FirstSync@@CAJW4ResourceTrackingStatus@12@PEAUResourceTrackingStatusMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatusMap *)
0x1800a8088  mov     r12d, eax
0x1800a808b  test    eax, eax
0x1800a808d  jns     short loc_1800A80EE
0x1800a808f  mov     rcx, [rsp+2E8h]; this
0x1800a8097  mov     r9d, eax; char *
0x1800a809a  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a80a1  mov     edx, 136h; void *
0x1800a80a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a80ab  nop
0x1800a80ac  lea     rcx, [rsp+2E8h+var_278]
0x1800a80b1  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a80b6  nop
0x1800a80b7  lea     rcx, [rsp+2E8h+var_210]
0x1800a80bf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a80c4  nop
0x1800a80c5  lea     rcx, [rsp+2E8h+var_230]
0x1800a80cd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a80d2  nop
0x1800a80d3  lea     rcx, [rsp+2E8h+hKey]
0x1800a80d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a80dd  nop
0x1800a80de  mov     rcx, r14
0x1800a80e1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a80e6  mov     eax, r12d
0x1800a80e9  jmp     loc_1800A845D
0x1800a80ee  lea     rdx, [rsp+2E8h+var_1D0]
0x1800a80f6  mov     ecx, dword ptr [rsp+2E8h+Data]
0x1800a80fa  call    ?GetResourceTrackingStatusObject@EnrollmentStatusTracking@FirstSync@@CAJW4ResourceTrackingStatus@12@PEAUResourceTrackingStatusMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatusMap *)
0x1800a80ff  mov     r12d, eax
0x1800a8102  test    eax, eax
0x1800a8104  jns     short loc_1800A8165
0x1800a8106  mov     rcx, [rsp+2E8h]; this
0x1800a810e  mov     r9d, eax; char *
0x1800a8111  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a8118  mov     edx, 137h; void *
0x1800a811d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a8122  nop
0x1800a8123  lea     rcx, [rsp+2E8h+var_278]
0x1800a8128  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800a812d  nop
0x1800a812e  lea     rcx, [rsp+2E8h+var_210]
0x1800a8136  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800a813b  nop
0x1800a813c  lea     rcx, [rsp+2E8h+var_230]
0x1800a8144  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
