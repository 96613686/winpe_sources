# EnsureLogonTasksCreated(void)

- ea: `0x14002f60c`
- end: `0x1400300ce`
- name: `?EnsureLogonTasksCreated@@YAJXZ`
- size: `2754`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140019a6c`

## callees

- `0x1400042f0`
- `0x14000715c`
- `0x1400095b4`
- `0x140009fc4`
- `0x14001ef94`
- `0x14002f60c`
- `0x140032a08`
- `0x14005d010`

## import_xrefs

- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14002f781`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x14002f781`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002f991`
- `ntdll!RtlIsStateSeparationEnabled` at `0x14002f991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ff68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f6df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002f93f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002ff68`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f8fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f952`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002ff7b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f688`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f6f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f8fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002f952`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002ff7b`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f8f6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f94a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fbe6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fbf7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fc29`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fc3a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fcbb`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fccc`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd4d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd5e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fddf`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fdf0`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe71`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe82`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ff03`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f8f6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002f94a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fbe6`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fbf7`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fc29`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fc3a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fcbb`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fccc`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd4d`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fd5e`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fddf`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fdf0`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe71`
- `OLEAUT32!__imp_SysFreeString` at `0x14002fe82`
- `OLEAUT32!__imp_SysFreeString` at `0x14002ff03`
- `OLEAUT32!__imp_VariantInit` at `0x14002facf`
- `OLEAUT32!__imp_VariantInit` at `0x14002fae4`
- `OLEAUT32!__imp_VariantInit` at `0x14002faf9`
- `OLEAUT32!__imp_VariantInit` at `0x14002fb0c`
- `OLEAUT32!__imp_VariantInit` at `0x14002facf`
- `OLEAUT32!__imp_VariantInit` at `0x14002fae4`
- `OLEAUT32!__imp_VariantInit` at `0x14002faf9`
- `OLEAUT32!__imp_VariantInit` at `0x14002fb0c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002fa98`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14002fa98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f6ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f718`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f6ba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14002f718`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f6ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f801`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fc89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fd1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fdad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fe3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002ff52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002ff73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003002c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030080`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f680`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f6ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f769`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f801`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002f8a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fc89`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fd1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fdad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fe3f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002fed1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002ff52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14002ff73`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x14003002c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140030080`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002ffbc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x14002ffbc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002f830`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14002f830`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f7f0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f88f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fc78`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fd0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fd9c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fe2e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fec0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002ff41`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003001b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003006f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f7f0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002f88f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fc78`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fd0a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fd9c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fe2e`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002fec0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002ff41`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003001b`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14003006f`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002f737`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x14002f737`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 EnsureLogonTasksCreated(void)
{
  LSTATUS v0; // eax
  bool v1; // sf
  HKEY v2; // rdi
  DWORD LastError; // ebx
  LSTATUS v4; // eax
  bool v5; // sf
  HRESULT v6; // eax
  unsigned int v7; // ebx
  __int64 DatabaseManagerInstance; // rax
  int v10; // eax
  HRESULT v11; // eax
  __int64 (__fastcall *v12)(__int64, BSTR *); // r14
  int v13; // eax
  __int64 (__fastcall *v14)(__int64, BSTR *); // r14
  int v15; // eax
  const unsigned __int16 *v16; // rdi
  __int64 v17; // rbx
  char IsStateSeparationEnabled; // al
  const wchar_t *v19; // rcx
  __int64 v20; // rdx
  WCHAR *v21; // r9
  wchar_t v22; // ax
  WCHAR *v23; // rcx
  LSTATUS ValueW; // eax
  LPVOID v25; // rdi
  __int64 (__fastcall *v26)(LPVOID, VARIANTARG *, __int128 *, __int128 *); // rbx
  __int128 v27; // xmm10
  IRecordInfo *pRecInfo; // xmm11_8
  __int128 v29; // xmm8
  IRecordInfo *v30; // xmm9_8
  __int128 v31; // xmm6
  IRecordInfo *v32; // xmm7_8
  int updated; // eax
  int v34; // eax
  HKEY v35; // rdi
  DWORD v36; // ebx
  LSTATUS v37; // eax
  int phkResult; // [rsp+28h] [rbp-E0h]
  int *phkResulta; // [rsp+28h] [rbp-E0h]
  int phkResultb; // [rsp+28h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-B0h] BYREF
  BSTR bstrString; // [rsp+60h] [rbp-A8h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v44; // [rsp+70h] [rbp-98h] BYREF
  __int64 v45; // [rsp+78h] [rbp-90h] BYREF
  BSTR v46; // [rsp+80h] [rbp-88h] BYREF
  int pvData; // [rsp+88h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+8Ch] [rbp-7Ch] BYREF
  DWORD pdwType; // [rsp+90h] [rbp-78h] BYREF
  DWORD dwDisposition; // [rsp+94h] [rbp-74h] BYREF
  VARIANTARG v51; // [rsp+98h] [rbp-70h] BYREF
  VARIANTARG v52; // [rsp+B0h] [rbp-58h] BYREF
  VARIANTARG v53; // [rsp+C8h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-28h] BYREF
  int v55[4]; // [rsp+F8h] [rbp-10h] BYREF
  IRecordInfo *v56; // [rsp+108h] [rbp+0h]
  __int128 v57; // [rsp+118h] [rbp+10h] BYREF
  IRecordInfo *v58; // [rsp+128h] [rbp+20h]
  __int128 v59; // [rsp+138h] [rbp+30h] BYREF
  IRecordInfo *v60; // [rsp+148h] [rbp+40h]
  VARIANTARG v61; // [rsp+158h] [rbp+50h] BYREF
  WCHAR SubKey[88]; // [rsp+178h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2E0h] [rbp+1D8h]

  dwDisposition = 0;
  hKey = 0;
  v0 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey);
  v1 = v0 < 0;
  if ( v0 > 0 )
    v1 = 1;
  if ( v1 )
  {
    v2 = hKey;
    if ( hKey )
    {
      LastError = GetLastError();
      RegCloseKey(v2);
      SetLastError(LastError);
    }
    hKey = 0;
    v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, c_szEnrollmentDB, 0, 0x20019u, &hKey);
    v5 = v4 < 0;
    if ( v4 > 0 )
      v5 = 1;
    if ( !v5 )
    {
      v6 = CoInitializeEx(0, 0);
      v7 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFB,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v6,
          phkResult);
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      v45 = 0;
      v44 = 0;
      DatabaseManagerInstance = GetDatabaseManagerInstance();
      v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)DatabaseManagerInstance + 32LL))(
              DatabaseManagerInstance,
              222306401,
              &v45);
      v7 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v10,
          phkResult);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        CoUninitialize();
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      ppv = 0;
      v11 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &ppv);
      v7 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x102,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v11,
          (int)phkResulta);
        wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        CoUninitialize();
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v45 + 24LL))(v45, &v44) )
      {
        bstrString = 0;
        v12 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v44 + 32LL);
        bstrString = 0;
        v13 = v12(v44, &bstrString);
        v7 = v13;
        if ( v13 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x109,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)v13,
            (int)phkResulta);
          if ( bstrString )
            SysFreeString(bstrString);
          wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          if ( v45 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          CoUninitialize();
          if ( hKey )
            RegCloseKey(hKey);
          return v7;
        }
        v46 = 0;
        v14 = *(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v44 + 112LL);
        v46 = 0;
        v15 = v14(v44, &v46);
        v7 = v15;
        if ( v15 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x10E,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)v15,
            (int)phkResulta);
          if ( v46 )
            SysFreeString(v46);
          if ( bstrString )
            SysFreeString(bstrString);
          wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          if ( v45 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          CoUninitialize();
          if ( hKey )
            RegCloseKey(hKey);
          return v7;
        }
        pdwType = 0;
        pvData = 0;
        pcbData = 4;
        v16 = bstrString;
        v17 = 2147483646;
        IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
        v19 = L"OSData\\";
        if ( !IsStateSeparationEnabled )
          v19 = &::SubKey;
        v20 = 85;
        v21 = SubKey;
        do
        {
          if ( !v17 )
            break;
          v22 = *v19;
          if ( !*v19 )
            break;
          ++v19;
          *v21++ = v22;
          --v17;
          --v20;
        }
        while ( v20 );
        v7 = v20 == 0 ? 0x8007007A : 0;
        v23 = v21 - 1;
        if ( v20 )
          v23 = v21;
        *v23 = 0;
        if ( !v20 )
          goto LABEL_93;
        v7 = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDB);
        if ( (v7 & 0x80000000) != 0 )
          goto LABEL_93;
        v7 = StringCchCatW(SubKey, 0x55u, v16);
        if ( (v7 & 0x80000000) != 0 )
          goto LABEL_93;
        v7 = StringCchCatW(SubKey, 0x55u, L"\\");
        if ( (v7 & 0x80000000) != 0 )
          goto LABEL_93;
        v7 = StringCchCatW(SubKey, 0x55u, c_szEnrollmentsDBPoll);
        if ( (v7 & 0x80000000) != 0 )
          goto LABEL_93;
        ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, L"PollOnLogin", 0x10u, &pdwType, &pvData, &pcbData);
        v7 = ValueW;
        if ( ValueW > 0 )
          v7 = (unsigned __int16)ValueW | 0x80070000;
        if ( (v7 & 0x80000000) != 0 )
        {
LABEL_93:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x112,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)v7,
            (int)phkResulta);
          if ( v46 )
            SysFreeString(v46);
          if ( bstrString )
            SysFreeString(bstrString);
          wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          if ( v45 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
          CoUninitialize();
          if ( hKey )
            RegCloseKey(hKey);
          return v7;
        }
        if ( pvData )
        {
          v25 = ppv;
          v26 = *(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int128 *, __int128 *))(*(_QWORD *)ppv + 80LL);
          VariantInit(&pvarg);
          v27 = *(_OWORD *)&pvarg.vt;
          pRecInfo = pvarg.pRecInfo;
          VariantInit(&v53);
          v29 = *(_OWORD *)&v53.vt;
          v30 = v53.pRecInfo;
          VariantInit(&v52);
          v31 = *(_OWORD *)&v52.vt;
          v32 = v52.pRecInfo;
          VariantInit(&v51);
          *(_OWORD *)v55 = v27;
          v56 = pRecInfo;
          v57 = v29;
          v58 = v30;
          v59 = v31;
          v60 = v32;
          v61 = v51;
          phkResulta = v55;
          v7 = v26(v25, &v61, &v59, &v57);
          _variant_t::~_variant_t(&v51);
          _variant_t::~_variant_t(&v52);
          _variant_t::~_variant_t(&v53);
          _variant_t::~_variant_t(&pvarg);
          if ( (v7 & 0x80000000) != 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x117,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)v7,
              (int)v55);
            if ( v46 )
              SysFreeString(v46);
            if ( bstrString )
              SysFreeString(bstrString);
            wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            if ( v45 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            CoUninitialize();
            if ( hKey )
              RegCloseKey(hKey);
            return v7;
          }
          updated = UpdateLogonTask(bstrString, v46, &ppv);
          v7 = updated;
          if ( updated < 0 && (unsigned int)(updated + 2147024894) > 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11B,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)(unsigned int)updated,
              (int)v55);
            if ( v46 )
              SysFreeString(v46);
            if ( bstrString )
              SysFreeString(bstrString);
            wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            if ( v45 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            CoUninitialize();
            if ( hKey )
              RegCloseKey(hKey);
            return v7;
          }
          v34 = UpdateLogonTask(bstrString, 0, &ppv);
          v7 = v34;
          if ( v34 < 0 && (unsigned int)(v34 + 2147024894) > 1 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x11F,
              (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
              (const char *)(unsigned int)v34,
              (int)v55);
            if ( v46 )
              SysFreeString(v46);
            if ( bstrString )
              SysFreeString(bstrString);
            wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
            if ( v45 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
            CoUninitialize();
            if ( hKey )
              RegCloseKey(hKey);
            return v7;
          }
        }
        if ( v46 )
          SysFreeString(v46);
        if ( bstrString )
          SysFreeString(bstrString);
      }
      v35 = hKey;
      if ( hKey )
      {
        v36 = GetLastError();
        RegCloseKey(v35);
        SetLastError(v36);
      }
      hKey = 0;
      v37 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0xF013Fu, 0, &hKey, &dwDisposition);
      v7 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x12C,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)v37,
          phkResultb);
        wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
        if ( v44 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
        if ( v45 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
        CoUninitialize();
        if ( hKey )
          RegCloseKey(hKey);
        return v7;
      }
      wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>((__int64 *)&ppv);
      if ( v44 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      if ( v45 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      CoUninitialize();
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x14002f60c  mov     rax, rsp
0x14002f60f  push    rbp
0x14002f610  push    rbx
0x14002f611  push    rsi
0x14002f612  push    rdi
0x14002f613  push    r12
0x14002f615  push    r13
0x14002f617  push    r14
0x14002f619  push    r15
0x14002f61b  lea     rbp, [rax-1D8h]
0x14002f622  sub     rsp, 298h
0x14002f629  movaps  xmmword ptr [rax-58h], xmm6
0x14002f62d  movaps  xmmword ptr [rax-68h], xmm7
0x14002f631  movaps  xmmword ptr [rax-78h], xmm8
0x14002f636  movaps  xmmword ptr [rax-88h], xmm9
0x14002f63e  movaps  xmmword ptr [rax-98h], xmm10
0x14002f646  movaps  xmmword ptr [rax-0A8h], xmm11
0x14002f64e  mov     rax, cs:__security_cookie
0x14002f655  xor     rax, rsp
0x14002f658  mov     [rbp+1D0h+var_B0], rax
0x14002f65f  xor     r15d, r15d
0x14002f662  mov     [rsp+2D0h+hKey], r15
0x14002f667  mov     [rbp+1D0h+dwDisposition], r15d
0x14002f66b  mov     rdi, [rsp+2D0h+hKey]
0x14002f670  test    rdi, rdi
0x14002f673  jz      short loc_14002F68F
0x14002f675  call    cs:__imp_GetLastError
0x14002f67b  mov     ebx, eax
0x14002f67d  mov     rcx, rdi; hKey
0x14002f680  call    cs:__imp_RegCloseKey
0x14002f686  mov     ecx, ebx; dwErrCode
0x14002f688  call    cs:__imp_SetLastError
0x14002f68e  nop
0x14002f68f  mov     [rsp+2D0h+hKey], r15
0x14002f694  lea     rax, [rsp+2D0h+hKey]
0x14002f699  mov     [rsp+2D0h+phkResult], rax; phkResult
0x14002f69e  mov     esi, 20019h
0x14002f6a3  mov     r9d, esi; samDesired
0x14002f6a6  xor     r8d, r8d; ulOptions
0x14002f6a9  mov     rdx, cs:lpSubKey; lpSubKey
0x14002f6b0  mov     r13, 0FFFFFFFF80000002h
0x14002f6b7  mov     rcx, r13; hKey
0x14002f6ba  call    cs:__imp_RegOpenKeyExW
0x14002f6c0  test    eax, eax
0x14002f6c2  jle     short loc_14002F6CE
0x14002f6c4  movzx   eax, ax
0x14002f6c7  or      eax, 80070000h
0x14002f6cc  test    eax, eax
0x14002f6ce  js      short loc_14002F6D5
0x14002f6d0  jmp     loc_140030076
0x14002f6d5  mov     rdi, [rsp+2D0h+hKey]
0x14002f6da  test    rdi, rdi
0x14002f6dd  jz      short loc_14002F6F9
0x14002f6df  call    cs:__imp_GetLastError
0x14002f6e5  mov     ebx, eax
0x14002f6e7  mov     rcx, rdi; hKey
0x14002f6ea  call    cs:__imp_RegCloseKey
0x14002f6f0  mov     ecx, ebx; dwErrCode
0x14002f6f2  call    cs:__imp_SetLastError
0x14002f6f8  nop
0x14002f6f9  mov     [rsp+2D0h+hKey], r15
0x14002f6fe  lea     rax, [rsp+2D0h+hKey]
0x14002f703  mov     [rsp+2D0h+phkResult], rax; int
0x14002f708  mov     r9d, esi; samDesired
0x14002f70b  xor     r8d, r8d; ulOptions
0x14002f70e  mov     rdx, cs:?c_szEnrollmentDB@@3PEBGEB; lpSubKey
0x14002f715  mov     rcx, r13; hKey
0x14002f718  call    cs:__imp_RegOpenKeyExW
0x14002f71e  test    eax, eax
0x14002f720  jle     short loc_14002F72C
0x14002f722  movzx   eax, ax
0x14002f725  or      eax, 80070000h
0x14002f72a  test    eax, eax
0x14002f72c  jns     short loc_14002F733
0x14002f72e  jmp     loc_140030076
0x14002f733  xor     edx, edx; dwCoInit
0x14002f735  xor     ecx, ecx; pvReserved
0x14002f737  call    cs:__imp_CoInitializeEx
0x14002f73d  mov     ebx, eax
0x14002f73f  test    eax, eax
0x14002f741  jns     short loc_14002F777
0x14002f743  mov     rcx, [rbp+1D8h]; this
0x14002f74a  mov     r9d, eax; char *
0x14002f74d  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002f754  mov     edx, 0FBh; void *
0x14002f759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f75e  nop
0x14002f75f  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14002f764  test    rcx, rcx
0x14002f767  jz      short loc_14002F770
0x14002f769  call    cs:__imp_RegCloseKey
0x14002f76f  nop
0x14002f770  mov     eax, ebx
0x14002f772  jmp     loc_140030089
0x14002f777  mov     [rsp+2D0h+var_260], r15
0x14002f77c  mov     [rsp+2D0h+var_268], r15
0x14002f781  call    cs:__imp_GetDatabaseManagerInstance
0x14002f787  mov     r9, rax
0x14002f78a  mov     rcx, [rax]
0x14002f78d  mov     rax, [rcx+20h]
0x14002f791  lea     r8, [rsp+2D0h+var_260]
0x14002f796  mov     edx, 0D402061h
0x14002f79b  mov     rcx, r9
0x14002f79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7a3  mov     ebx, eax
0x14002f7a5  test    eax, eax
0x14002f7a7  jns     short loc_14002F80D
0x14002f7a9  mov     rcx, [rbp+1D8h]; this
0x14002f7b0  mov     r9d, eax; char *
0x14002f7b3  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002f7ba  mov     edx, 0FFh; void *
0x14002f7bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f7c4  mov     rcx, [rsp+2D0h+var_268]
0x14002f7c9  test    rcx, rcx
0x14002f7cc  jz      short loc_14002F7DA
0x14002f7ce  mov     rdx, [rcx]
0x14002f7d1  mov     rax, [rdx+10h]
0x14002f7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7da  mov     rcx, [rsp+2D0h+var_260]
0x14002f7df  test    rcx, rcx
0x14002f7e2  jz      short loc_14002F7F0
0x14002f7e4  mov     rax, [rcx]
0x14002f7e7  mov     rax, [rax+10h]
0x14002f7eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f7f0  call    cs:__imp_CoUninitialize
0x14002f7f6  nop
0x14002f7f7  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14002f7fc  test    rcx, rcx
0x14002f7ff  jz      short loc_14002F808
0x14002f801  call    cs:__imp_RegCloseKey
0x14002f807  nop
0x14002f808  jmp     loc_14002F770
0x14002f80d  mov     [rsp+2D0h+ppv], r15
0x14002f812  lea     rax, [rsp+2D0h+ppv]
0x14002f817  mov     [rsp+2D0h+phkResult], rax; int
0x14002f81c  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x14002f823  xor     edx, edx; pUnkOuter
0x14002f825  lea     r8d, [rdx+1]; dwClsContext
0x14002f829  lea     rcx, CLSID_TaskScheduler; rclsid
0x14002f830  call    cs:__imp_CoCreateInstance
0x14002f836  mov     ebx, eax
0x14002f838  test    eax, eax
0x14002f83a  jns     short loc_14002F8AC
0x14002f83c  mov     rcx, [rbp+1D8h]; this
0x14002f843  mov     r9d, eax; char *
0x14002f846  lea     r8, aOnecoreuapAdmi_22; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x14002f84d  mov     edx, 102h; void *
0x14002f852  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002f857  nop
0x14002f858  lea     rcx, [rsp+2D0h+ppv]
0x14002f85d  call    ??1?$com_ptr_t@UIEnrollment@Enrollment@Management@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::Management::Enrollment::IEnrollment,wil::err_returncode_policy>(void)
0x14002f862  nop
0x14002f863  mov     rcx, [rsp+2D0h+var_268]
0x14002f868  test    rcx, rcx
0x14002f86b  jz      short loc_14002F879
0x14002f86d  mov     rax, [rcx]
0x14002f870  mov     rax, [rax+10h]
0x14002f874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f879  mov     rcx, [rsp+2D0h+var_260]
0x14002f87e  test    rcx, rcx
0x14002f881  jz      short loc_14002F88F
0x14002f883  mov     rax, [rcx]
0x14002f886  mov     rax, [rax+10h]
0x14002f88a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f88f  call    cs:__imp_CoUninitialize
0x14002f895  nop
0x14002f896  mov     rcx, [rsp+2D0h+hKey]; hKey
0x14002f89b  test    rcx, rcx
0x14002f89e  jz      short loc_14002F8A7
0x14002f8a0  call    cs:__imp_RegCloseKey
0x14002f8a6  nop
0x14002f8a7  jmp     loc_14002F770
0x14002f8ac  mov     r12d, 55h ; 'U'
0x14002f8b2  mov     rcx, [rsp+2D0h+var_260]
0x14002f8b7  mov     rax, [rcx]
0x14002f8ba  lea     rdx, [rsp+2D0h+var_268]
0x14002f8bf  mov     rax, [rax+18h]
0x14002f8c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f8c8  test    eax, eax
0x14002f8ca  jnz     loc_14002FF5E
0x14002f8d0  mov     [rsp+2D0h+bstrString], r15
0x14002f8d5  mov     rsi, [rsp+2D0h+var_268]
0x14002f8da  mov     rax, [rsi]
0x14002f8dd  mov     r14, [rax+20h]
0x14002f8e1  mov     rdi, [rsp+2D0h+bstrString]
0x14002f8e6  test    rdi, rdi
0x14002f8e9  jz      short loc_14002F905
0x14002f8eb  call    cs:__imp_GetLastError
0x14002f8f1  mov     ebx, eax
0x14002f8f3  mov     rcx, rdi; bstrString
0x14002f8f6  call    cs:__imp_SysFreeString
0x14002f8fc  mov     ecx, ebx; dwErrCode
0x14002f8fe  call    cs:__imp_SetLastError
0x14002f904  nop
0x14002f905  mov     [rsp+2D0h+bstrString], r15
0x14002f90a  lea     rdx, [rsp+2D0h+bstrString]
0x14002f90f  mov     rcx, rsi
0x14002f912  mov     rax, r14
0x14002f915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f91a  mov     ebx, eax
0x14002f91c  test    eax, eax
0x14002f91e  js      loc_14002FEDD
0x14002f924  mov     [rsp+2D0h+var_258], r15
0x14002f929  mov     rsi, [rsp+2D0h+var_268]
0x14002f92e  mov     rax, [rsi]
0x14002f931  mov     r14, [rax+70h]
0x14002f935  mov     rdi, [rsp+2D0h+var_258]
0x14002f93a  test    rdi, rdi
0x14002f93d  jz      short loc_14002F959
0x14002f93f  call    cs:__imp_GetLastError
0x14002f945  mov     ebx, eax
0x14002f947  mov     rcx, rdi; bstrString
0x14002f94a  call    cs:__imp_SysFreeString
0x14002f950  mov     ecx, ebx; dwErrCode
0x14002f952  call    cs:__imp_SetLastError
0x14002f958  nop
0x14002f959  mov     [rsp+2D0h+var_258], r15
0x14002f95e  lea     rdx, [rsp+2D0h+var_258]
0x14002f963  mov     rcx, rsi
0x14002f966  mov     rax, r14
0x14002f969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002f96e  mov     ebx, eax
0x14002f970  test    eax, eax
0x14002f972  js      loc_14002FE4B
0x14002f978  mov     [rbp+1D0h+pdwType], r15d
0x14002f97c  mov     [rbp+1D0h+var_250], r15d
0x14002f980  mov     [rbp+1D0h+var_24C], 4
0x14002f987  mov     rdi, [rsp+2D0h+bstrString]
0x14002f98c  mov     ebx, 7FFFFFFEh
0x14002f991  call    cs:__imp_RtlIsStateSeparationEnabled
0x14002f997  lea     rdx, SubKey
0x14002f99e  lea     rcx, aOsdata; "OSData\\"
0x14002f9a5  test    al, al
0x14002f9a7  cmovz   rcx, rdx
0x14002f9ab  mov     rdx, r12
0x14002f9ae  lea     r9, [rbp+1D0h+SubKey]
0x14002f9b2  test    rbx, rbx
0x14002f9b5  jz      short loc_14002F9D4
0x14002f9b7  movzx   eax, word ptr [rcx]
0x14002f9ba  test    ax, ax
0x14002f9bd  jz      short loc_14002F9D4
0x14002f9bf  add     rcx, 2
0x14002f9c3  mov     [r9], ax
0x14002f9c7  add     r9, 2
0x14002f9cb  dec     rbx
0x14002f9ce  sub     rdx, 1
0x14002f9d2  jnz     short loc_14002F9B2
0x14002f9d4  mov     rax, rdx
0x14002f9d7  neg     rax
0x14002f9da  sbb     ebx, ebx
0x14002f9dc  not     ebx
0x14002f9de  and     ebx, 8007007Ah
0x14002f9e4  lea     rcx, [r9-2]
0x14002f9e8  test    rdx, rdx
0x14002f9eb  cmovnz  rcx, r9
0x14002f9ef  mov     [rcx], r15w
0x14002f9f3  jz      loc_14002FDB9
0x14002f9f9  lea     r8, ?c_szEnrollmentsDB@@3PAGA; "Software\\Microsoft\\Enrollments\\"
0x14002fa00  mov     rdx, r12; unsigned __int64
0x14002fa03  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x14002fa07  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002fa0c  mov     ebx, eax
0x14002fa0e  test    eax, eax
0x14002fa10  js      loc_14002FDB9
0x14002fa16  mov     r8, rdi; unsigned __int16 *
0x14002fa19  mov     rdx, r12; unsigned __int64
0x14002fa1c  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x14002fa20  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002fa25  mov     ebx, eax
0x14002fa27  test    eax, eax
0x14002fa29  js      loc_14002FDB9
0x14002fa2f  lea     r8, asc_140061150; "\\"
0x14002fa36  mov     rdx, r12; unsigned __int64
0x14002fa39  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x14002fa3d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002fa42  mov     ebx, eax
0x14002fa44  test    eax, eax
0x14002fa46  js      loc_14002FDB9
0x14002fa4c  lea     r8, ?c_szEnrollmentsDBPoll@@3PAGA; "Poll"
0x14002fa53  mov     rdx, r12; unsigned __int64
0x14002fa56  lea     rcx, [rbp+1D0h+SubKey]; unsigned __int16 *
0x14002fa5a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14002fa5f  mov     ebx, eax
0x14002fa61  test    eax, eax
0x14002fa63  js      loc_14002FDB9
0x14002fa69  lea     rax, [rbp+1D0h+var_24C]
0x14002fa6d  mov     [rsp+2D0h+pcbData], rax; pcbData
0x14002fa72  lea     rax, [rbp+1D0h+var_250]
0x14002fa76  mov     [rsp+2D0h+pvData], rax; pvData
0x14002fa7b  lea     rax, [rbp+1D0h+pdwType]
0x14002fa7f  mov     [rsp+2D0h+phkResult], rax; pdwType
0x14002fa84  mov     r9d, 10h; dwFlags
0x14002fa8a  lea     r8, aPollonlogin; "PollOnLogin"
0x14002fa91  lea     rdx, [rbp+1D0h+SubKey]; lpSubKey
0x14002fa95  mov     rcx, r13; hkey
0x14002fa98  call    cs:__imp_RegGetValueW
0x14002fa9e  mov     ebx, eax
0x14002faa0  test    eax, eax
0x14002faa2  jle     short loc_14002FAAD
0x14002faa4  movzx   ebx, ax
  ... truncated ...
```
