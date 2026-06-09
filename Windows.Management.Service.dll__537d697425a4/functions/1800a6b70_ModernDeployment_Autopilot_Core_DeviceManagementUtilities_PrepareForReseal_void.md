# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForReseal(void)

- ea: `0x1800a6b70`
- end: `0x1800a6f78`
- name: `?PrepareForReseal@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJXZ`
- size: `1032`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077d0c`
- `0x180077de0`
- `0x180077e54`
- `0x180080984`
- `0x180080bac`
- `0x180084574`
- `0x180084d5c`
- `0x180084d80`
- `0x18008a454`
- `0x18008ed78`
- `0x1800a4fcc`
- `0x1800a5314`
- `0x1800a5b60`
- `0x1800a5efc`
- `0x1800a6b70`
- `0x1800a988c`
- `0x1800e2668`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a6e3e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a6e3e`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a6c2b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a6e23`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a6c2b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a6e23`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c41`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c6d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c83`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6caf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6cc5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6ea9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c41`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c57`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c6d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c83`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6c99`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6caf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6cc5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a6ea9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a6d7e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a6d7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6e05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6e8e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6e05`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a6e8e`

## string_xrefs

- `0x1800a6bb9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a6ef2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

## pseudocode

```c
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForReseal(
        ModernDeployment::Autopilot::Core::DeviceManagementUtilities *this)
{
  int EnrollmentId; // eax
  unsigned int v2; // ebx
  unsigned __int16 *v3; // rbx
  int FirstSyncKey; // eax
  HKEY v5; // rdi
  bool v6; // al
  const wchar_t *v7; // rsi
  const wchar_t *v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  const WCHAR *v11; // rax
  LSTATUS v12; // edi
  __int64 v13; // rax
  __int64 v14; // rax
  const WCHAR *v15; // rax
  LSTATUS v16; // eax
  const WCHAR *v17; // rax
  const WCHAR *v18; // rax
  int v19; // eax
  int dwOptions; // [rsp+20h] [rbp-A9h]
  int dwOptionsa; // [rsp+20h] [rbp-A9h]
  HKEY hKey; // [rsp+50h] [rbp-79h] BYREF
  HKEY v24; // [rsp+58h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-69h] BYREF
  HKEY hKeyDest; // [rsp+68h] [rbp-61h] BYREF
  HKEY hKeySrc; // [rsp+70h] [rbp-59h] BYREF
  unsigned __int16 *v28; // [rsp+78h] [rbp-51h] BYREF
  _BYTE v29[32]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v30[32]; // [rsp+A0h] [rbp-29h] BYREF
  _BYTE v31[32]; // [rsp+C0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+5Fh]

  v28 = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v28,
    0);
  EnrollmentId = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(&v28);
  v2 = EnrollmentId;
  if ( EnrollmentId >= 0 )
  {
    hKeySrc = 0;
    hKeyDest = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKeySrc,
      0);
    v3 = v28;
    FirstSyncKey = ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetFirstSyncKey(v28, 0, &hKeySrc);
    v5 = hKeySrc;
    if ( FirstSyncKey >= 0 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hKeyDest,
        0);
      if ( (int)ModernDeployment::Autopilot::Core::DeviceManagementUtilities::CreateBackupFirstSyncKey(v3, &hKeyDest) >= 0 )
        RegCopyTreeW(v5, 0, hKeyDest);
    }
    RegDeleteValueW(v5, L"IsSyncDone");
    RegDeleteValueW(v5, L"IsServerProvisioningDone");
    RegDeleteValueW(v5, L"ProvisioningStatus");
    RegDeleteValueW(v5, L"ApplicationsDuration");
    RegDeleteValueW(v5, L"CertificatesDuration");
    RegDeleteValueW(v5, L"NetworkingDuration");
    RegDeleteValueW(v5, L"PolicyDuration");
    phkResult = 0;
    v6 = ZTPIsStateSeparationEnabled();
    v7 = L"OSData\\SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    v8 = L"OSData\\SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    if ( !v6 )
      v8 = L"SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    std::wstring::wstring(v30, v8);
    v9 = std::wstring::append(v30, L"\\");
    v10 = std::wstring::append(v9, L"Device");
    std::wstring::append(v10, L"\\WhiteGlove_PreReseal_Backup_Setup");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v30);
    v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v11, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    v24 = 0;
    if ( !ZTPIsStateSeparationEnabled() )
      v7 = L"SOFTWARE\\Microsoft\\Windows\\Autopilot\\EnrollmentStatusTracking";
    std::wstring::wstring(v29, v7);
    v13 = std::wstring::append(v29, L"\\");
    v14 = std::wstring::append(v13, L"Device");
    std::wstring::append(v14, L"\\Setup");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v24,
      0);
    v15 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    v16 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v15, 0, 0x20019u, &v24);
    if ( !v12 && !v16 )
      RegCopyTreeW(v24, 0, phkResult);
    v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v29);
    RegDeleteTreeW(HKEY_LOCAL_MACHINE, v17);
    hKey = 0;
    std::wstring::wstring(v31, L"Software\\Microsoft\\Provisioning\\AutopilotSettings");
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v18, 0, 0xF003Fu, &hKey) )
      RegDeleteValueW(hKey, L"DeviceSetupCategory.Status");
    ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(v3);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl'::`2'::impl) )
    {
      v19 = ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(
              L"WindowsAutopilot.Telemetry.EarlyBoot.WhiteGlove.Reseal",
              1,
              0,
              0,
              0);
      if ( v19 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1B2,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
          (const char *)(unsigned int)v19,
          dwOptionsa);
    }
    std::wstring::_Tidy_deallocate(v31);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    std::wstring::_Tidy_deallocate(v29);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v24);
    std::wstring::_Tidy_deallocate(v30);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeySrc);
    v2 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x162,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
      (const char *)(unsigned int)EnrollmentId,
      dwOptions);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  return v2;
}

```

## disassembly

```asm
0x1800a6b70  push    rbp
0x1800a6b72  push    rbx
0x1800a6b73  push    rsi
0x1800a6b74  push    rdi
0x1800a6b75  push    r12
0x1800a6b77  push    r14
0x1800a6b79  lea     rbp, [rsp-2Fh]
0x1800a6b7e  sub     rsp, 0F8h
0x1800a6b85  mov     rax, cs:__security_cookie
0x1800a6b8c  xor     rax, rsp
0x1800a6b8f  mov     [rbp+57h+var_40], rax
0x1800a6b93  xor     edx, edx
0x1800a6b95  mov     [rbp+57h+var_A8], 0
0x1800a6b9d  lea     rcx, [rbp+57h+var_A8]
0x1800a6ba1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a6ba6  lea     rcx, [rbp+57h+var_A8]; unsigned __int16 **
0x1800a6baa  call    ?GetEnrollmentId@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJPEAPEAG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(ushort * *)
0x1800a6baf  mov     ebx, eax
0x1800a6bb1  test    eax, eax
0x1800a6bb3  jns     short loc_1800A6BD2
0x1800a6bb5  mov     rcx, [rbp+5Fh]; this
0x1800a6bb9  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a6bc0  mov     r9d, eax; char *
0x1800a6bc3  mov     edx, 162h; void *
0x1800a6bc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a6bcd  jmp     loc_1800A6F50
0x1800a6bd2  xor     edx, edx
0x1800a6bd4  mov     [rbp+57h+hKeySrc], 0
0x1800a6bdc  lea     rcx, [rbp+57h+hKeySrc]
0x1800a6be0  mov     [rbp+57h+hKeyDest], 0
0x1800a6be8  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6bed  mov     rbx, [rbp+57h+var_A8]
0x1800a6bf1  lea     r8, [rbp+57h+hKeySrc]; HKEY *
0x1800a6bf5  mov     rcx, rbx; unsigned __int16 *
0x1800a6bf8  xor     edx, edx; unsigned __int16 *
0x1800a6bfa  call    ?GetFirstSyncKey@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0PEAPEAUHKEY__@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetFirstSyncKey(ushort const * const,ushort const * const,HKEY__ * *)
0x1800a6bff  mov     rdi, [rbp+57h+hKeySrc]
0x1800a6c03  test    eax, eax
0x1800a6c05  js      short loc_1800A6C37
0x1800a6c07  xor     edx, edx
0x1800a6c09  lea     rcx, [rbp+57h+hKeyDest]
0x1800a6c0d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6c12  lea     rdx, [rbp+57h+hKeyDest]; HKEY *
0x1800a6c16  mov     rcx, rbx; unsigned __int16 *
0x1800a6c19  call    ?CreateBackupFirstSyncKey@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBGPEAPEAUHKEY__@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::CreateBackupFirstSyncKey(ushort const * const,HKEY__ * *)
0x1800a6c1e  test    eax, eax
0x1800a6c20  js      short loc_1800A6C37
0x1800a6c22  mov     r8, [rbp+57h+hKeyDest]; hKeyDest
0x1800a6c26  xor     edx, edx; lpSubKey
0x1800a6c28  mov     rcx, rdi; hKeySrc
0x1800a6c2b  call    cs:__imp_RegCopyTreeW
0x1800a6c32  nop     dword ptr [rax+rax+00h]
0x1800a6c37  lea     rdx, aIssyncdone; "IsSyncDone"
0x1800a6c3e  mov     rcx, rdi; hKey
0x1800a6c41  call    cs:__imp_RegDeleteValueW
0x1800a6c48  nop     dword ptr [rax+rax+00h]
0x1800a6c4d  lea     rdx, aIsserverprovis; "IsServerProvisioningDone"
0x1800a6c54  mov     rcx, rdi; hKey
0x1800a6c57  call    cs:__imp_RegDeleteValueW
0x1800a6c5e  nop     dword ptr [rax+rax+00h]
0x1800a6c63  lea     rdx, aProvisioningst; "ProvisioningStatus"
0x1800a6c6a  mov     rcx, rdi; hKey
0x1800a6c6d  call    cs:__imp_RegDeleteValueW
0x1800a6c74  nop     dword ptr [rax+rax+00h]
0x1800a6c79  lea     rdx, aApplicationsdu; "ApplicationsDuration"
0x1800a6c80  mov     rcx, rdi; hKey
0x1800a6c83  call    cs:__imp_RegDeleteValueW
0x1800a6c8a  nop     dword ptr [rax+rax+00h]
0x1800a6c8f  lea     rdx, aCertificatesdu; "CertificatesDuration"
0x1800a6c96  mov     rcx, rdi; hKey
0x1800a6c99  call    cs:__imp_RegDeleteValueW
0x1800a6ca0  nop     dword ptr [rax+rax+00h]
0x1800a6ca5  lea     rdx, aNetworkingdura; "NetworkingDuration"
0x1800a6cac  mov     rcx, rdi; hKey
0x1800a6caf  call    cs:__imp_RegDeleteValueW
0x1800a6cb6  nop     dword ptr [rax+rax+00h]
0x1800a6cbb  lea     rdx, aPolicyduration; "PolicyDuration"
0x1800a6cc2  mov     rcx, rdi; hKey
0x1800a6cc5  call    cs:__imp_RegDeleteValueW
0x1800a6ccc  nop     dword ptr [rax+rax+00h]
0x1800a6cd1  mov     [rbp+57h+var_C0], 0
0x1800a6cd9  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800a6cde  test    al, al
0x1800a6ce0  lea     rsi, aOsdataSoftware_10; "OSData\\SOFTWARE\\Microsoft\\Windows\\A"...
0x1800a6ce7  mov     rdx, rsi
0x1800a6cea  lea     r14, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x1800a6cf1  cmovz   rdx, r14
0x1800a6cf5  lea     rcx, [rbp+57h+var_80]
0x1800a6cf9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a6cfe  lea     rdx, SubBlock; "\\"
0x1800a6d05  lea     rcx, [rbp+57h+var_80]
0x1800a6d09  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6d0e  lea     rdx, aDevice_0; "Device"
0x1800a6d15  mov     rcx, rax
0x1800a6d18  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6d1d  lea     rdx, aWhiteglovePrer_0; "\\WhiteGlove_PreReseal_Backup_Setup"
0x1800a6d24  mov     rcx, rax
0x1800a6d27  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6d2c  xor     edx, edx
0x1800a6d2e  lea     rcx, [rbp+57h+var_C0]
0x1800a6d32  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6d37  lea     rcx, [rbp+57h+var_80]
0x1800a6d3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a6d40  mov     [rsp+120h+lpdwDisposition], 0; lpdwDisposition
0x1800a6d49  mov     rdx, rax; lpSubKey
0x1800a6d4c  lea     rax, [rbp+57h+var_C0]
0x1800a6d50  mov     r12, 0FFFFFFFF80000002h
0x1800a6d57  mov     [rsp+120h+phkResult], rax; phkResult
0x1800a6d5c  xor     r9d, r9d; lpClass
0x1800a6d5f  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a6d68  xor     r8d, r8d; Reserved
0x1800a6d6b  mov     [rsp+120h+samDesired], 0F003Fh; samDesired
0x1800a6d73  mov     rcx, r12; hKey
0x1800a6d76  mov     [rsp+120h+dwOptions], 0; dwOptions
0x1800a6d7e  call    cs:__imp_RegCreateKeyExW
0x1800a6d85  nop     dword ptr [rax+rax+00h]
0x1800a6d8a  mov     edi, eax
0x1800a6d8c  mov     [rbp+57h+var_C8], 0
0x1800a6d94  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800a6d99  test    al, al
0x1800a6d9b  lea     rcx, [rbp+57h+var_A0]
0x1800a6d9f  cmovz   rsi, r14
0x1800a6da3  mov     rdx, rsi
0x1800a6da6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a6dab  lea     rdx, SubBlock; "\\"
0x1800a6db2  lea     rcx, [rbp+57h+var_A0]
0x1800a6db6  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6dbb  lea     rdx, aDevice_0; "Device"
0x1800a6dc2  mov     rcx, rax
0x1800a6dc5  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6dca  lea     rdx, aSetup_0; "\\Setup"
0x1800a6dd1  mov     rcx, rax
0x1800a6dd4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a6dd9  xor     edx, edx
0x1800a6ddb  lea     rcx, [rbp+57h+var_C8]
0x1800a6ddf  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6de4  lea     rcx, [rbp+57h+var_A0]
0x1800a6de8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a6ded  mov     rdx, rax; lpSubKey
0x1800a6df0  lea     rax, [rbp+57h+var_C8]
0x1800a6df4  mov     qword ptr [rsp+120h+dwOptions], rax; phkResult
0x1800a6df9  mov     r9d, 20019h; samDesired
0x1800a6dff  xor     r8d, r8d; ulOptions
0x1800a6e02  mov     rcx, r12; hKey
0x1800a6e05  call    cs:__imp_RegOpenKeyExW
0x1800a6e0c  nop     dword ptr [rax+rax+00h]
0x1800a6e11  test    edi, edi
0x1800a6e13  jnz     short loc_1800A6E2F
0x1800a6e15  test    eax, eax
0x1800a6e17  jnz     short loc_1800A6E2F
0x1800a6e19  mov     r8, [rbp+57h+var_C0]; hKeyDest
0x1800a6e1d  xor     edx, edx; lpSubKey
0x1800a6e1f  mov     rcx, [rbp+57h+var_C8]; hKeySrc
0x1800a6e23  call    cs:__imp_RegCopyTreeW
0x1800a6e2a  nop     dword ptr [rax+rax+00h]
0x1800a6e2f  lea     rcx, [rbp+57h+var_A0]
0x1800a6e33  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a6e38  mov     rdx, rax; lpSubKey
0x1800a6e3b  mov     rcx, r12; hKey
0x1800a6e3e  call    cs:__imp_RegDeleteTreeW
0x1800a6e45  nop     dword ptr [rax+rax+00h]
0x1800a6e4a  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800a6e51  mov     [rbp+57h+hKey], 0
0x1800a6e59  lea     rcx, [rbp+57h+var_60]
0x1800a6e5d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a6e62  xor     edx, edx
0x1800a6e64  lea     rcx, [rbp+57h+hKey]
0x1800a6e68  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a6e6d  lea     rcx, [rbp+57h+var_60]
0x1800a6e71  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a6e76  mov     rdx, rax; lpSubKey
0x1800a6e79  mov     r9d, 0F003Fh; samDesired
0x1800a6e7f  lea     rax, [rbp+57h+hKey]
0x1800a6e83  xor     r8d, r8d; ulOptions
0x1800a6e86  mov     rcx, r12; hKey
0x1800a6e89  mov     qword ptr [rsp+120h+dwOptions], rax; phkResult
0x1800a6e8e  call    cs:__imp_RegOpenKeyExW
0x1800a6e95  nop     dword ptr [rax+rax+00h]
0x1800a6e9a  test    eax, eax
0x1800a6e9c  jnz     short loc_1800A6EB5
0x1800a6e9e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a6ea2  lea     rdx, aDevicesetupcat; "DeviceSetupCategory.Status"
0x1800a6ea9  call    cs:__imp_RegDeleteValueW
0x1800a6eb0  nop     dword ptr [rax+rax+00h]
0x1800a6eb5  mov     rcx, rbx; unsigned __int16 *
0x1800a6eb8  call    ?BackUpAndDeleteDMClientCspTrackingFiles@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(ushort const * const)
0x1800a6ebd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800a6ec4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800a6ec9  test    al, al
0x1800a6ecb  jz      short loc_1800A6F06
0x1800a6ecd  xor     r9d, r9d; __int64
0x1800a6ed0  mov     qword ptr [rsp+120h+dwOptions], 0; int
0x1800a6ed9  xor     r8d, r8d; int
0x1800a6edc  lea     rcx, aWindowsautopil_22; "WindowsAutopilot.Telemetry.EarlyBoot.Wh"...
0x1800a6ee3  mov     dl, 1; bool
0x1800a6ee5  call    ?ReportEventW@FwtReportHelper@Core@Autopilot@ModernDeployment@@SAJPEBG_NJ_J0@Z; ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(ushort const *,bool,long,__int64,ushort const *)
0x1800a6eea  test    eax, eax
0x1800a6eec  jns     short loc_1800A6F06
0x1800a6eee  mov     rcx, [rbp+5Fh]; this
0x1800a6ef2  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a6ef9  mov     r9d, eax; char *
0x1800a6efc  mov     edx, 1B2h; void *
0x1800a6f01  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a6f06  lea     rcx, [rbp+57h+var_60]
0x1800a6f0a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6f0f  lea     rcx, [rbp+57h+hKey]
0x1800a6f13  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6f18  lea     rcx, [rbp+57h+var_A0]
0x1800a6f1c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6f21  lea     rcx, [rbp+57h+var_C8]
0x1800a6f25  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6f2a  lea     rcx, [rbp+57h+var_80]
0x1800a6f2e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a6f33  lea     rcx, [rbp+57h+var_C0]
0x1800a6f37  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6f3c  lea     rcx, [rbp+57h+hKeyDest]
0x1800a6f40  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6f45  lea     rcx, [rbp+57h+hKeySrc]
0x1800a6f49  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a6f4e  xor     ebx, ebx
0x1800a6f50  lea     rcx, [rbp+57h+var_A8]
0x1800a6f54  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6f59  mov     eax, ebx
0x1800a6f5b  mov     rcx, [rbp+57h+var_40]
0x1800a6f5f  xor     rcx, rsp; StackCookie
0x1800a6f62  call    __security_check_cookie
0x1800a6f67  add     rsp, 0F8h
0x1800a6f6e  pop     r14
0x1800a6f70  pop     r12
0x1800a6f72  pop     rdi
0x1800a6f73  pop     rsi
0x1800a6f74  pop     rbx
0x1800a6f75  pop     rbp
0x1800a6f76  retn
```
