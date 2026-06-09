# FirstSync::EnrollmentStatusTracking::UpdateTrackingStatus(ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,ushort const *,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus)

- ea: `0x1800ab0bc`
- end: `0x1800ab956`
- name: `?UpdateTrackingStatus@EnrollmentStatusTracking@FirstSync@@SAJPEBGV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0W4ResourceTrackingStatus@12@@Z`
- size: `2202`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800a50ac`
- `0x1800a55d4`

## callees

- `0x180004eb0`
- `0x18000a5c4`
- `0x18000d50c`
- `0x18000dc18`
- `0x180015e44`
- `0x18001656c`
- `0x180016698`
- `0x180017024`
- `0x180017118`
- `0x180020970`
- `0x180033500`
- `0x1800953ec`
- `0x1800a8d98`
- `0x1800a96bc`
- `0x1800a97ac`
- `0x1800a9d50`
- `0x1800aa144`
- `0x1800aa1f4`
- `0x1800aa264`
- `0x1800aa55c`
- `0x1800aaae0`
- `0x1800ab000`
- `0x1800ab0bc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab3ec`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800ab3ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab41d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab856`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab41d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ab856`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab236`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ab236`

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
  const WCHAR *v20; // rdi
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
  unsigned int v31; // r12d
  int v32; // ecx
  __int64 *v33; // rdx
  unsigned int v34; // eax
  unsigned int v35; // ebx
  int dwOptions; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-2C8h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-2C8h]
  HKEY hKey; // [rsp+50h] [rbp-298h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-290h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-288h] BYREF
  unsigned int pvData; // [rsp+64h] [rbp-284h] BYREF
  DWORD dwDisposition; // [rsp+68h] [rbp-280h] BYREF
  _BYTE v45[24]; // [rsp+70h] [rbp-278h] BYREF
  unsigned __int16 *v46[2]; // [rsp+88h] [rbp-260h] BYREF
  unsigned __int16 *v47[2]; // [rsp+98h] [rbp-250h] BYREF
  const WCHAR *v48; // [rsp+A8h] [rbp-240h]
  __int64 v49; // [rsp+B0h] [rbp-238h]
  _BYTE v50[32]; // [rsp+B8h] [rbp-230h] BYREF
  _BYTE v51[32]; // [rsp+D8h] [rbp-210h] BYREF
  _OWORD v52[2]; // [rsp+F8h] [rbp-1F0h] BYREF
  unsigned __int16 *v53[2]; // [rsp+118h] [rbp-1D0h] BYREF
  _BYTE v54[40]; // [rsp+138h] [rbp-1B0h] BYREF
  _BYTE v55[336]; // [rsp+160h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E8h] [rbp+0h]

  v49 = a2;
  *(_DWORD *)Data = a4;
  *(_OWORD *)v46 = 0;
  *(_OWORD *)v47 = 0;
  ResourceTypeObject = FirstSync::EnrollmentStatusTracking::GetResourceTypeObject(
                         a3,
                         (struct FirstSync::EnrollmentStatusTracking::ResourceTypeMap *)v46);
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
    v8 = v47[0];
    v9 = std::wstring::wstring(v54, v47[0]);
    v10 = std::wstring::wstring(
            v52,
            L"SOFTWARE\\Microsoft\\Provisioning\\Diagnostics\\AutoPilot\\WindowsAutopilotDiagnostics");
    v11 = std::operator+<unsigned short>(v53, v10, L"\\");
    std::operator+<unsigned short>(v50, v11, v9);
    std::wstring::~wstring(v53);
    std::wstring::~wstring(v52);
    std::wstring::~wstring(v54);
    dwDisposition = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
    v13 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
    if ( v13 )
    {
      v14 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x10F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
              (const char *)v13,
              dwOptionsa);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v14;
    }
    std::wstring::wstring(v51);
    std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(v45);
    v16 = FirstSync::EnrollmentStatusTracking::TokenizeLocUri(a2, v45);
    v17 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x114,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)v16,
        dwOptionsa);
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v17;
    }
    ResourceName = FirstSync::EnrollmentStatusTracking::GetResourceName(v45, v51);
    v19 = ResourceName;
    if ( ResourceName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x115,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)ResourceName,
        dwOptionsa);
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v19;
    }
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51);
    v48 = v20;
    pvData = -1;
    pcbData = 4;
    v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v50);
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
        std::vector<std::wstring>::_Tidy(v45);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(v50);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(a2);
        return v25;
      }
      v26 = v46[0];
      if ( (byte_1800FF242 & 1) != 0 )
        McTemplateU0zzz_EventWriteTransfer(
          v24,
          (unsigned int)EnterpriseDiagnosticsResourceProvisioningTrackingStarted,
          (_DWORD)v8,
          (_DWORD)v20,
          (__int64)v46[0]);
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
        std::vector<std::wstring>::_Tidy(v45);
        std::wstring::~wstring(v51);
        std::wstring::~wstring(v50);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        std::wstring::~wstring(a2);
        return v27;
      }
      v26 = v46[0];
    }
    v52[0] = 0;
    *(_OWORD *)v53 = 0;
    ResourceTrackingStatusObject = FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(pvData, v52);
    v29 = ResourceTrackingStatusObject;
    if ( ResourceTrackingStatusObject < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)ResourceTrackingStatusObject,
        dwOptionsb);
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v29;
    }
    v30 = FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(*(unsigned int *)Data, v53);
    v31 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x137,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
        (const char *)(unsigned int)v30,
        dwOptionsb);
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v31;
    }
    if ( pvData == *(_DWORD *)Data || pvData == -1 )
    {
LABEL_65:
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return 0;
    }
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::UpdateResourceProvisioningTrackingStatusTelemetry(
      (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v55,
      (__int64)v46,
      (__int64)v47);
    v32 = *(_DWORD *)Data;
    if ( *(int *)Data > 6 )
    {
      v32 = *(_DWORD *)Data - 7;
      if ( *(_DWORD *)Data == 7 )
      {
        if ( (byte_1800FF242 & 1) != 0 )
        {
          v33 = EnterpriseDiagnosticsResourceProvisioningInstalling;
          goto LABEL_61;
        }
      }
      else
      {
        v32 = *(_DWORD *)Data - 8;
        if ( *(_DWORD *)Data == 8 )
        {
          if ( (byte_1800FF242 & 1) != 0 )
          {
            v33 = EnterpriseDiagnosticsResourceProvisioningPendingInstallationRetry;
            goto LABEL_61;
          }
        }
        else
        {
          v32 = *(_DWORD *)Data - 9;
          if ( *(_DWORD *)Data == 9 )
          {
            if ( (byte_1800FF242 & 2) != 0 )
            {
              v33 = EnterpriseDiagnosticsResourceProvisioningInstallationFailed;
              goto LABEL_61;
            }
          }
          else
          {
            v32 = *(_DWORD *)Data - 10;
            if ( *(_DWORD *)Data != 10 )
            {
              if ( *(_DWORD *)Data == 11 )
              {
                if ( (byte_1800FF242 & 4) != 0 )
                  McTemplateU0zzz_EventWriteTransfer(
                    1,
                    (unsigned int)EnterpriseDiagnosticsResourceProvisioningStatusUnknown,
                    (_DWORD)v8,
                    (_DWORD)v20,
                    (__int64)v26);
                FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::LogResourceTrackingStatusUnknown(
                  (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v55,
                  v20,
                  v26,
                  v8);
              }
              goto LABEL_62;
            }
            if ( (byte_1800FF242 & 1) != 0 )
            {
              v33 = EnterpriseDiagnosticsResourceProvisioningInstallationComplete;
              goto LABEL_61;
            }
          }
        }
      }
    }
    else if ( *(_DWORD *)Data == 6 )
    {
      if ( (byte_1800FF242 & 1) != 0 )
      {
        v33 = EnterpriseDiagnosticsResourceProvisioningPendingUserSession;
        goto LABEL_61;
      }
    }
    else if ( *(_DWORD *)Data )
    {
      v32 = *(_DWORD *)Data - 1;
      if ( *(_DWORD *)Data == 1 )
      {
        if ( (byte_1800FF242 & 1) != 0 )
        {
          v33 = EnterpriseDiagnosticsResourceProvisioningInitializing;
          goto LABEL_61;
        }
      }
      else
      {
        v32 = *(_DWORD *)Data - 2;
        if ( *(_DWORD *)Data == 2 )
        {
          if ( (byte_1800FF242 & 1) != 0 )
          {
            v33 = EnterpriseDiagnosticsResourceProvisioningDownloading;
            goto LABEL_61;
          }
        }
        else
        {
          v32 = *(_DWORD *)Data - 3;
          if ( *(_DWORD *)Data == 3 )
          {
            if ( (byte_1800FF242 & 1) != 0 )
            {
              v33 = EnterpriseDiagnosticsResourceProvisioningPendingDownloadRetry;
              goto LABEL_61;
            }
          }
          else
          {
            v32 = *(_DWORD *)Data - 4;
            if ( *(_DWORD *)Data != 4 )
            {
              if ( *(_DWORD *)Data != 5 || (byte_1800FF242 & 1) == 0 )
                goto LABEL_62;
              v33 = EnterpriseDiagnosticsResourceProvisioningDownloadCompleted;
              goto LABEL_61;
            }
            if ( (byte_1800FF242 & 2) != 0 )
            {
              v33 = EnterpriseDiagnosticsResourceProvisioningDownloadFailed;
LABEL_61:
              McTemplateU0zzz_EventWriteTransfer(v32, (_DWORD)v33, (_DWORD)v8, (_DWORD)v20, (__int64)v26);
            }
          }
        }
      }
    }
    else if ( (byte_1800FF242 & 1) != 0 )
    {
      v33 = EnterpriseDiagnosticsResourceProvisioningTrackingStarted;
      goto LABEL_61;
    }
LABEL_62:
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::Stop(
      (FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v55,
      v20,
      v53[1],
      v26,
      v8);
    v34 = RegSetValueExW(hKey, v20, 0, 4u, Data, 4u);
    if ( v34 )
    {
      v35 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
              (const char *)v34,
              dwOptionsc);
      FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::~UpdateResourceProvisioningTrackingStatusTelemetry((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v55);
      std::vector<std::wstring>::_Tidy(v45);
      std::wstring::~wstring(v51);
      std::wstring::~wstring(v50);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      std::wstring::~wstring(a2);
      return v35;
    }
    FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry::~UpdateResourceProvisioningTrackingStatusTelemetry((FirstSyncStatusProvider::UpdateResourceProvisioningTrackingStatusTelemetry *)v55);
    goto LABEL_65;
  }
  catch ( ... )
  {
    pcbData = wil::details::in1diag3::Return_CaughtException(
                retaddr,
                (void *)0x180,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\enrollmentstatustracking.cpp",
                v15);
    std::wstring::~wstring(v49);
    return pcbData;
  }
  return result;
}

```

## disassembly

```asm
0x1800ab0bc  mov     [rsp+arg_0], rbx
0x1800ab0c1  push    rsi
0x1800ab0c2  push    rdi
0x1800ab0c3  push    r12
0x1800ab0c5  push    r14
0x1800ab0c7  push    r15
0x1800ab0c9  sub     rsp, 2C0h
0x1800ab0d0  mov     rax, cs:__security_cookie
0x1800ab0d7  xor     rax, rsp
0x1800ab0da  mov     [rsp+2E8h+var_38], rax
0x1800ab0e2  mov     r14, rdx
0x1800ab0e5  mov     [rsp+2E8h+var_238], rdx
0x1800ab0ed  mov     dword ptr [rsp+2E8h+Data], r9d
0x1800ab0f2  xorps   xmm0, xmm0
0x1800ab0f5  movups  xmmword ptr [rsp+2E8h+var_260], xmm0
0x1800ab0fd  movups  xmmword ptr [rsp+2E8h+var_250], xmm0
0x1800ab105  lea     rdx, [rsp+2E8h+var_260]; struct FirstSync::EnrollmentStatusTracking::ResourceTypeMap *
0x1800ab10d  mov     rcx, r8; unsigned __int16 *
0x1800ab110  call    ?GetResourceTypeObject@EnrollmentStatusTracking@FirstSync@@CAJPEBGPEAUResourceTypeMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTypeObject(ushort const *,FirstSync::EnrollmentStatusTracking::ResourceTypeMap *)
0x1800ab115  mov     ebx, eax
0x1800ab117  test    eax, eax
0x1800ab119  jns     short loc_1800AB147
0x1800ab11b  mov     rcx, [rsp+2E8h]; this
0x1800ab123  mov     r9d, eax; char *
0x1800ab126  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab12d  mov     edx, 0FFh; void *
0x1800ab132  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab137  nop
0x1800ab138  mov     rcx, r14
0x1800ab13b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab140  mov     eax, ebx
0x1800ab142  jmp     loc_1800AB92D
0x1800ab147  mov     [rsp+2E8h+hKey], 0
0x1800ab150  mov     rsi, [rsp+2E8h+var_250]
0x1800ab158  mov     rdx, rsi
0x1800ab15b  lea     rcx, [rsp+2E8h+var_1B0]
0x1800ab163  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab168  mov     rbx, rax
0x1800ab16b  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Provisioning\\Diag"...
0x1800ab172  lea     rcx, [rsp+2E8h+var_1F0]
0x1800ab17a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ab17f  nop
0x1800ab180  lea     r8, asc_1800DD8B8; "\\"
0x1800ab187  mov     rdx, rax
0x1800ab18a  lea     rcx, [rsp+2E8h+var_1D0]
0x1800ab192  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800ab197  nop
0x1800ab198  mov     r8, rbx
0x1800ab19b  mov     rdx, rax
0x1800ab19e  lea     rcx, [rsp+2E8h+var_230]
0x1800ab1a6  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x1800ab1ab  nop
0x1800ab1ac  lea     rcx, [rsp+2E8h+var_1D0]
0x1800ab1b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab1b9  nop
0x1800ab1ba  lea     rcx, [rsp+2E8h+var_1F0]
0x1800ab1c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab1c7  nop
0x1800ab1c8  lea     rcx, [rsp+2E8h+var_1B0]
0x1800ab1d0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab1d5  mov     [rsp+2E8h+dwDisposition], 0
0x1800ab1dd  xor     edx, edx
0x1800ab1df  lea     rcx, [rsp+2E8h+hKey]
0x1800ab1e4  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800ab1e9  lea     rcx, [rsp+2E8h+var_230]
0x1800ab1f1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab1f6  mov     rdx, rax; lpSubKey
0x1800ab1f9  lea     rax, [rsp+2E8h+dwDisposition]
0x1800ab1fe  mov     [rsp+2E8h+lpdwDisposition], rax; lpdwDisposition
0x1800ab203  lea     rax, [rsp+2E8h+hKey]
0x1800ab208  mov     [rsp+2E8h+phkResult], rax; phkResult
0x1800ab20d  mov     [rsp+2E8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800ab216  mov     [rsp+2E8h+samDesired], 0F003Fh; samDesired
0x1800ab21e  mov     [rsp+2E8h+dwOptions], 0; int
0x1800ab226  xor     r9d, r9d; lpClass
0x1800ab229  xor     r8d, r8d; Reserved
0x1800ab22c  mov     r15, 0FFFFFFFF80000002h
0x1800ab233  mov     rcx, r15; hKey
0x1800ab236  call    cs:__imp_RegCreateKeyExW
0x1800ab23d  nop     dword ptr [rax+rax+00h]
0x1800ab242  test    eax, eax
0x1800ab244  jz      short loc_1800AB28C
0x1800ab246  mov     rcx, [rsp+2E8h]; this
0x1800ab24e  mov     r9d, eax; char *
0x1800ab251  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab258  mov     edx, 10Fh; void *
0x1800ab25d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ab262  mov     ebx, eax
0x1800ab264  lea     rcx, [rsp+2E8h+var_230]
0x1800ab26c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab271  nop
0x1800ab272  lea     rcx, [rsp+2E8h+hKey]
0x1800ab277  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab27c  nop
0x1800ab27d  mov     rcx, r14
0x1800ab280  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab285  mov     eax, ebx
0x1800ab287  jmp     loc_1800AB92D
0x1800ab28c  lea     rcx, [rsp+2E8h+var_210]
0x1800ab294  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800ab299  nop
0x1800ab29a  lea     rcx, [rsp+2E8h+var_278]
0x1800ab29f  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800ab2a4  nop
0x1800ab2a5  lea     rdx, [rsp+2E8h+var_278]
0x1800ab2aa  mov     rcx, r14
0x1800ab2ad  call    ?TokenizeLocUri@EnrollmentStatusTracking@FirstSync@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@4@@Z; FirstSync::EnrollmentStatusTracking::TokenizeLocUri(std::wstring const &,std::vector<std::wstring> &)
0x1800ab2b2  mov     ebx, eax
0x1800ab2b4  test    eax, eax
0x1800ab2b6  jns     short loc_1800AB316
0x1800ab2b8  mov     rcx, [rsp+2E8h]; this
0x1800ab2c0  mov     r9d, eax; char *
0x1800ab2c3  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab2ca  mov     edx, 114h; void *
0x1800ab2cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab2d4  nop
0x1800ab2d5  lea     rcx, [rsp+2E8h+var_278]
0x1800ab2da  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab2df  nop
0x1800ab2e0  lea     rcx, [rsp+2E8h+var_210]
0x1800ab2e8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab2ed  nop
0x1800ab2ee  lea     rcx, [rsp+2E8h+var_230]
0x1800ab2f6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab2fb  nop
0x1800ab2fc  lea     rcx, [rsp+2E8h+hKey]
0x1800ab301  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab306  nop
0x1800ab307  mov     rcx, r14
0x1800ab30a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab30f  mov     eax, ebx
0x1800ab311  jmp     loc_1800AB92D
0x1800ab316  lea     rdx, [rsp+2E8h+var_210]
0x1800ab31e  lea     rcx, [rsp+2E8h+var_278]
0x1800ab323  call    ?GetResourceName@EnrollmentStatusTracking@FirstSync@@CAJAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@@Z; FirstSync::EnrollmentStatusTracking::GetResourceName(std::vector<std::wstring> &,std::wstring &)
0x1800ab328  mov     ebx, eax
0x1800ab32a  test    eax, eax
0x1800ab32c  jns     short loc_1800AB38C
0x1800ab32e  mov     rcx, [rsp+2E8h]; this
0x1800ab336  mov     r9d, eax; char *
0x1800ab339  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab340  mov     edx, 115h; void *
0x1800ab345  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab34a  nop
0x1800ab34b  lea     rcx, [rsp+2E8h+var_278]
0x1800ab350  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab355  nop
0x1800ab356  lea     rcx, [rsp+2E8h+var_210]
0x1800ab35e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab363  nop
0x1800ab364  lea     rcx, [rsp+2E8h+var_230]
0x1800ab36c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab371  nop
0x1800ab372  lea     rcx, [rsp+2E8h+hKey]
0x1800ab377  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab37c  nop
0x1800ab37d  mov     rcx, r14
0x1800ab380  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab385  mov     eax, ebx
0x1800ab387  jmp     loc_1800AB92D
0x1800ab38c  lea     rcx, [rsp+2E8h+var_210]
0x1800ab394  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab399  mov     rdi, rax
0x1800ab39c  mov     [rsp+2E8h+var_240], rax
0x1800ab3a4  mov     [rsp+2E8h+pvData], 0FFFFFFFFh
0x1800ab3ac  mov     ebx, 4
0x1800ab3b1  mov     [rsp+2E8h+pcbData], ebx
0x1800ab3b5  lea     rcx, [rsp+2E8h+var_230]
0x1800ab3bd  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800ab3c2  mov     rdx, rax; lpSubKey
0x1800ab3c5  lea     rax, [rsp+2E8h+pcbData]
0x1800ab3ca  mov     [rsp+2E8h+lpSecurityAttributes], rax; pcbData
0x1800ab3cf  lea     rax, [rsp+2E8h+pvData]
0x1800ab3d4  mov     qword ptr [rsp+2E8h+samDesired], rax; pvData
0x1800ab3d9  mov     qword ptr [rsp+2E8h+dwOptions], 0; int
0x1800ab3e2  lea     r9d, [rbx+0Ch]; dwFlags
0x1800ab3e6  mov     r8, rdi; lpValue
0x1800ab3e9  mov     rcx, r15; hkey
0x1800ab3ec  call    cs:__imp_RegGetValueW
0x1800ab3f3  nop     dword ptr [rax+rax+00h]
0x1800ab3f8  cmp     eax, 2
0x1800ab3fb  jnz     loc_1800AB4BD
0x1800ab401  mov     [rsp+2E8h+samDesired], ebx; cbData
0x1800ab405  lea     rax, [rsp+2E8h+Data]
0x1800ab40a  mov     qword ptr [rsp+2E8h+dwOptions], rax; unsigned int
0x1800ab40f  mov     r9d, ebx; dwType
0x1800ab412  xor     r8d, r8d; Reserved
0x1800ab415  mov     rdx, rdi; lpValueName
0x1800ab418  mov     rcx, [rsp+2E8h+hKey]; hKey
0x1800ab41d  call    cs:__imp_RegSetValueExW
0x1800ab424  nop     dword ptr [rax+rax+00h]
0x1800ab429  test    eax, eax
0x1800ab42b  jz      short loc_1800AB48C
0x1800ab42d  mov     rcx, [rsp+2E8h]; this
0x1800ab435  mov     r9d, eax; char *
0x1800ab438  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab43f  mov     edx, 12Dh; void *
0x1800ab444  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ab449  mov     ebx, eax
0x1800ab44b  lea     rcx, [rsp+2E8h+var_278]
0x1800ab450  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab455  nop
0x1800ab456  lea     rcx, [rsp+2E8h+var_210]
0x1800ab45e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab463  nop
0x1800ab464  lea     rcx, [rsp+2E8h+var_230]
0x1800ab46c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab471  nop
0x1800ab472  lea     rcx, [rsp+2E8h+hKey]
0x1800ab477  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab47c  nop
0x1800ab47d  mov     rcx, r14
0x1800ab480  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab485  mov     eax, ebx
0x1800ab487  jmp     loc_1800AB92D
0x1800ab48c  mov     r15b, 1
0x1800ab48f  mov     rbx, [rsp+2E8h+var_260]
0x1800ab497  test    cs:byte_1800FF242, r15b
0x1800ab49e  jz      loc_1800AB52B
0x1800ab4a4  mov     qword ptr [rsp+2E8h+dwOptions], rbx
0x1800ab4a9  mov     r9, rdi
0x1800ab4ac  mov     r8, rsi
0x1800ab4af  lea     rdx, EnterpriseDiagnosticsResourceProvisioningTrackingStarted
0x1800ab4b6  call    McTemplateU0zzz_EventWriteTransfer
0x1800ab4bb  jmp     short loc_1800AB52B
0x1800ab4bd  test    eax, eax
0x1800ab4bf  jz      short loc_1800AB520
0x1800ab4c1  mov     rcx, [rsp+2E8h]; this
0x1800ab4c9  mov     r9d, eax; char *
0x1800ab4cc  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab4d3  mov     edx, 132h; void *
0x1800ab4d8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800ab4dd  mov     ebx, eax
0x1800ab4df  lea     rcx, [rsp+2E8h+var_278]
0x1800ab4e4  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab4e9  nop
0x1800ab4ea  lea     rcx, [rsp+2E8h+var_210]
0x1800ab4f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab4f7  nop
0x1800ab4f8  lea     rcx, [rsp+2E8h+var_230]
0x1800ab500  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab505  nop
0x1800ab506  lea     rcx, [rsp+2E8h+hKey]
0x1800ab50b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab510  nop
0x1800ab511  mov     rcx, r14
0x1800ab514  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab519  mov     eax, ebx
0x1800ab51b  jmp     loc_1800AB92D
0x1800ab520  mov     r15b, 1
0x1800ab523  mov     rbx, [rsp+2E8h+var_260]
0x1800ab52b  xorps   xmm0, xmm0
0x1800ab52e  movups  [rsp+2E8h+var_1F0], xmm0
0x1800ab536  xorps   xmm1, xmm1
0x1800ab539  movups  xmmword ptr [rsp+2E8h+var_1D0], xmm1
0x1800ab541  lea     rdx, [rsp+2E8h+var_1F0]
0x1800ab549  mov     ecx, [rsp+2E8h+pvData]
0x1800ab54d  call    ?GetResourceTrackingStatusObject@EnrollmentStatusTracking@FirstSync@@CAJW4ResourceTrackingStatus@12@PEAUResourceTrackingStatusMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatusMap *)
0x1800ab552  mov     r12d, eax
0x1800ab555  test    eax, eax
0x1800ab557  jns     short loc_1800AB5B8
0x1800ab559  mov     rcx, [rsp+2E8h]; this
0x1800ab561  mov     r9d, eax; char *
0x1800ab564  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab56b  mov     edx, 136h; void *
0x1800ab570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab575  nop
0x1800ab576  lea     rcx, [rsp+2E8h+var_278]
0x1800ab57b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab580  nop
0x1800ab581  lea     rcx, [rsp+2E8h+var_210]
0x1800ab589  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab58e  nop
0x1800ab58f  lea     rcx, [rsp+2E8h+var_230]
0x1800ab597  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab59c  nop
0x1800ab59d  lea     rcx, [rsp+2E8h+hKey]
0x1800ab5a2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ab5a7  nop
0x1800ab5a8  mov     rcx, r14
0x1800ab5ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800ab5b0  mov     eax, r12d
0x1800ab5b3  jmp     loc_1800AB92D
0x1800ab5b8  lea     rdx, [rsp+2E8h+var_1D0]
0x1800ab5c0  mov     ecx, dword ptr [rsp+2E8h+Data]
0x1800ab5c4  call    ?GetResourceTrackingStatusObject@EnrollmentStatusTracking@FirstSync@@CAJW4ResourceTrackingStatus@12@PEAUResourceTrackingStatusMap@12@@Z; FirstSync::EnrollmentStatusTracking::GetResourceTrackingStatusObject(FirstSync::EnrollmentStatusTracking::ResourceTrackingStatus,FirstSync::EnrollmentStatusTracking::ResourceTrackingStatusMap *)
0x1800ab5c9  mov     r12d, eax
0x1800ab5cc  test    eax, eax
0x1800ab5ce  jns     short loc_1800AB62F
0x1800ab5d0  mov     rcx, [rsp+2E8h]; this
0x1800ab5d8  mov     r9d, eax; char *
0x1800ab5db  lea     r8, aOnecoreuapAdmi_16; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800ab5e2  mov     edx, 137h; void *
0x1800ab5e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ab5ec  nop
0x1800ab5ed  lea     rcx, [rsp+2E8h+var_278]
0x1800ab5f2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800ab5f7  nop
0x1800ab5f8  lea     rcx, [rsp+2E8h+var_210]
0x1800ab600  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
