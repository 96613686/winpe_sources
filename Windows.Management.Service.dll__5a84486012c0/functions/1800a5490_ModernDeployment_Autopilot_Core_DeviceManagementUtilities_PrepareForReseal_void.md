# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::PrepareForReseal(void)

- ea: `0x1800a5490`
- end: `0x1800a5843`
- name: `?PrepareForReseal@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@UEAAJXZ`
- size: `947`
- prototype: `__int64 __fastcall(ModernDeployment::Autopilot::Core::DeviceManagementUtilities *__hidden this)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007748c`
- `0x18007755c`
- `0x1800775c4`
- `0x18007ff90`
- `0x18008019c`
- `0x1800839bc`
- `0x1800841e8`
- `0x180084208`
- `0x180089614`
- `0x18008dc94`
- `0x1800a397c`
- `0x1800a3ca4`
- `0x1800a44c4`
- `0x1800a4854`
- `0x1800a5490`
- `0x1800a8084`
- `0x1800dfdf0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a571c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a571c`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a554b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a5707`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a554b`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800a5707`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a555b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a556b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a557b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a558b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a559b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a55ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a55bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a577b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a555b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a556b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a557b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a558b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a559b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a55ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a55bb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800a577b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a566e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a566e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a56ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5766`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a56ef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a5766`

## string_xrefs

- `0x1800a54d9`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a57be`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`

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
0x1800a5490  push    rbp
0x1800a5492  push    rbx
0x1800a5493  push    rsi
0x1800a5494  push    rdi
0x1800a5495  push    r12
0x1800a5497  push    r14
0x1800a5499  lea     rbp, [rsp-2Fh]
0x1800a549e  sub     rsp, 0F8h
0x1800a54a5  mov     rax, cs:__security_cookie
0x1800a54ac  xor     rax, rsp
0x1800a54af  mov     [rbp+57h+var_40], rax
0x1800a54b3  xor     edx, edx
0x1800a54b5  mov     [rbp+57h+var_A8], 0
0x1800a54bd  lea     rcx, [rbp+57h+var_A8]
0x1800a54c1  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a54c6  lea     rcx, [rbp+57h+var_A8]; unsigned __int16 **
0x1800a54ca  call    ?GetEnrollmentId@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@SAJPEAPEAG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetEnrollmentId(ushort * *)
0x1800a54cf  mov     ebx, eax
0x1800a54d1  test    eax, eax
0x1800a54d3  jns     short loc_1800A54F2
0x1800a54d5  mov     rcx, [rbp+5Fh]; this
0x1800a54d9  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a54e0  mov     r9d, eax; char *
0x1800a54e3  mov     edx, 162h; void *
0x1800a54e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a54ed  jmp     loc_1800A581C
0x1800a54f2  xor     edx, edx
0x1800a54f4  mov     [rbp+57h+hKeySrc], 0
0x1800a54fc  lea     rcx, [rbp+57h+hKeySrc]
0x1800a5500  mov     [rbp+57h+hKeyDest], 0
0x1800a5508  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a550d  mov     rbx, [rbp+57h+var_A8]
0x1800a5511  lea     r8, [rbp+57h+hKeySrc]; HKEY *
0x1800a5515  mov     rcx, rbx; unsigned __int16 *
0x1800a5518  xor     edx, edx; unsigned __int16 *
0x1800a551a  call    ?GetFirstSyncKey@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG0PEAPEAUHKEY__@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::GetFirstSyncKey(ushort const * const,ushort const * const,HKEY__ * *)
0x1800a551f  mov     rdi, [rbp+57h+hKeySrc]
0x1800a5523  test    eax, eax
0x1800a5525  js      short loc_1800A5551
0x1800a5527  xor     edx, edx
0x1800a5529  lea     rcx, [rbp+57h+hKeyDest]
0x1800a552d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a5532  lea     rdx, [rbp+57h+hKeyDest]; HKEY *
0x1800a5536  mov     rcx, rbx; unsigned __int16 *
0x1800a5539  call    ?CreateBackupFirstSyncKey@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBGPEAPEAUHKEY__@@@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::CreateBackupFirstSyncKey(ushort const * const,HKEY__ * *)
0x1800a553e  test    eax, eax
0x1800a5540  js      short loc_1800A5551
0x1800a5542  mov     r8, [rbp+57h+hKeyDest]; hKeyDest
0x1800a5546  xor     edx, edx; lpSubKey
0x1800a5548  mov     rcx, rdi; hKeySrc
0x1800a554b  call    cs:__imp_RegCopyTreeW
0x1800a5551  lea     rdx, aIssyncdone; "IsSyncDone"
0x1800a5558  mov     rcx, rdi; hKey
0x1800a555b  call    cs:__imp_RegDeleteValueW
0x1800a5561  lea     rdx, aIsserverprovis; "IsServerProvisioningDone"
0x1800a5568  mov     rcx, rdi; hKey
0x1800a556b  call    cs:__imp_RegDeleteValueW
0x1800a5571  lea     rdx, aProvisioningst; "ProvisioningStatus"
0x1800a5578  mov     rcx, rdi; hKey
0x1800a557b  call    cs:__imp_RegDeleteValueW
0x1800a5581  lea     rdx, aApplicationsdu; "ApplicationsDuration"
0x1800a5588  mov     rcx, rdi; hKey
0x1800a558b  call    cs:__imp_RegDeleteValueW
0x1800a5591  lea     rdx, aCertificatesdu; "CertificatesDuration"
0x1800a5598  mov     rcx, rdi; hKey
0x1800a559b  call    cs:__imp_RegDeleteValueW
0x1800a55a1  lea     rdx, aNetworkingdura; "NetworkingDuration"
0x1800a55a8  mov     rcx, rdi; hKey
0x1800a55ab  call    cs:__imp_RegDeleteValueW
0x1800a55b1  lea     rdx, aPolicyduration; "PolicyDuration"
0x1800a55b8  mov     rcx, rdi; hKey
0x1800a55bb  call    cs:__imp_RegDeleteValueW
0x1800a55c1  mov     [rbp+57h+var_C0], 0
0x1800a55c9  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800a55ce  test    al, al
0x1800a55d0  lea     rsi, aOsdataSoftware_10; "OSData\\SOFTWARE\\Microsoft\\Windows\\A"...
0x1800a55d7  mov     rdx, rsi
0x1800a55da  lea     r14, aSoftwareMicros_13; "SOFTWARE\\Microsoft\\Windows\\Autopilot"...
0x1800a55e1  cmovz   rdx, r14
0x1800a55e5  lea     rcx, [rbp+57h+var_80]
0x1800a55e9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a55ee  lea     rdx, SubBlock; "\\"
0x1800a55f5  lea     rcx, [rbp+57h+var_80]
0x1800a55f9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a55fe  lea     rdx, aDevice_0; "Device"
0x1800a5605  mov     rcx, rax
0x1800a5608  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a560d  lea     rdx, aWhiteglovePrer_0; "\\WhiteGlove_PreReseal_Backup_Setup"
0x1800a5614  mov     rcx, rax
0x1800a5617  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a561c  xor     edx, edx
0x1800a561e  lea     rcx, [rbp+57h+var_C0]
0x1800a5622  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a5627  lea     rcx, [rbp+57h+var_80]
0x1800a562b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5630  mov     [rsp+120h+lpdwDisposition], 0; lpdwDisposition
0x1800a5639  mov     rdx, rax; lpSubKey
0x1800a563c  lea     rax, [rbp+57h+var_C0]
0x1800a5640  mov     r12, 0FFFFFFFF80000002h
0x1800a5647  mov     [rsp+120h+phkResult], rax; phkResult
0x1800a564c  xor     r9d, r9d; lpClass
0x1800a564f  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800a5658  xor     r8d, r8d; Reserved
0x1800a565b  mov     [rsp+120h+samDesired], 0F003Fh; samDesired
0x1800a5663  mov     rcx, r12; hKey
0x1800a5666  mov     [rsp+120h+dwOptions], 0; dwOptions
0x1800a566e  call    cs:__imp_RegCreateKeyExW
0x1800a5674  mov     edi, eax
0x1800a5676  mov     [rbp+57h+var_C8], 0
0x1800a567e  call    ?ZTPIsStateSeparationEnabled@@YA_NXZ; ZTPIsStateSeparationEnabled(void)
0x1800a5683  test    al, al
0x1800a5685  lea     rcx, [rbp+57h+var_A0]
0x1800a5689  cmovz   rsi, r14
0x1800a568d  mov     rdx, rsi
0x1800a5690  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a5695  lea     rdx, SubBlock; "\\"
0x1800a569c  lea     rcx, [rbp+57h+var_A0]
0x1800a56a0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a56a5  lea     rdx, aDevice_0; "Device"
0x1800a56ac  mov     rcx, rax
0x1800a56af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a56b4  lea     rdx, aSetup_0; "\\Setup"
0x1800a56bb  mov     rcx, rax
0x1800a56be  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a56c3  xor     edx, edx
0x1800a56c5  lea     rcx, [rbp+57h+var_C8]
0x1800a56c9  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a56ce  lea     rcx, [rbp+57h+var_A0]
0x1800a56d2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a56d7  mov     rdx, rax; lpSubKey
0x1800a56da  lea     rax, [rbp+57h+var_C8]
0x1800a56de  mov     qword ptr [rsp+120h+dwOptions], rax; phkResult
0x1800a56e3  mov     r9d, 20019h; samDesired
0x1800a56e9  xor     r8d, r8d; ulOptions
0x1800a56ec  mov     rcx, r12; hKey
0x1800a56ef  call    cs:__imp_RegOpenKeyExW
0x1800a56f5  test    edi, edi
0x1800a56f7  jnz     short loc_1800A570D
0x1800a56f9  test    eax, eax
0x1800a56fb  jnz     short loc_1800A570D
0x1800a56fd  mov     r8, [rbp+57h+var_C0]; hKeyDest
0x1800a5701  xor     edx, edx; lpSubKey
0x1800a5703  mov     rcx, [rbp+57h+var_C8]; hKeySrc
0x1800a5707  call    cs:__imp_RegCopyTreeW
0x1800a570d  lea     rcx, [rbp+57h+var_A0]
0x1800a5711  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5716  mov     rdx, rax; lpSubKey
0x1800a5719  mov     rcx, r12; hKey
0x1800a571c  call    cs:__imp_RegDeleteTreeW
0x1800a5722  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800a5729  mov     [rbp+57h+hKey], 0
0x1800a5731  lea     rcx, [rbp+57h+var_60]
0x1800a5735  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a573a  xor     edx, edx
0x1800a573c  lea     rcx, [rbp+57h+hKey]
0x1800a5740  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a5745  lea     rcx, [rbp+57h+var_60]
0x1800a5749  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a574e  mov     rdx, rax; lpSubKey
0x1800a5751  mov     r9d, 0F003Fh; samDesired
0x1800a5757  lea     rax, [rbp+57h+hKey]
0x1800a575b  xor     r8d, r8d; ulOptions
0x1800a575e  mov     rcx, r12; hKey
0x1800a5761  mov     qword ptr [rsp+120h+dwOptions], rax; phkResult
0x1800a5766  call    cs:__imp_RegOpenKeyExW
0x1800a576c  test    eax, eax
0x1800a576e  jnz     short loc_1800A5781
0x1800a5770  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a5774  lea     rdx, aDevicesetupcat; "DeviceSetupCategory.Status"
0x1800a577b  call    cs:__imp_RegDeleteValueW
0x1800a5781  mov     rcx, rbx; unsigned __int16 *
0x1800a5784  call    ?BackUpAndDeleteDMClientCspTrackingFiles@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG@Z; ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(ushort const * const)
0x1800a5789  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry> `wil::Feature<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::GetImpl(void)'::`2'::impl
0x1800a5790  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotFastWindowsTelemetry>::__private_IsEnabled(void)
0x1800a5795  test    al, al
0x1800a5797  jz      short loc_1800A57D2
0x1800a5799  xor     r9d, r9d; __int64
0x1800a579c  mov     qword ptr [rsp+120h+dwOptions], 0; int
0x1800a57a5  xor     r8d, r8d; int
0x1800a57a8  lea     rcx, aWindowsautopil_22; "WindowsAutopilot.Telemetry.EarlyBoot.Wh"...
0x1800a57af  mov     dl, 1; bool
0x1800a57b1  call    ?ReportEventW@FwtReportHelper@Core@Autopilot@ModernDeployment@@SAJPEBG_NJ_J0@Z; ModernDeployment::Autopilot::Core::FwtReportHelper::ReportEventW(ushort const *,bool,long,__int64,ushort const *)
0x1800a57b6  test    eax, eax
0x1800a57b8  jns     short loc_1800A57D2
0x1800a57ba  mov     rcx, [rbp+5Fh]; this
0x1800a57be  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a57c5  mov     r9d, eax; char *
0x1800a57c8  mov     edx, 1B2h; void *
0x1800a57cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a57d2  lea     rcx, [rbp+57h+var_60]
0x1800a57d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a57db  lea     rcx, [rbp+57h+hKey]
0x1800a57df  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a57e4  lea     rcx, [rbp+57h+var_A0]
0x1800a57e8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a57ed  lea     rcx, [rbp+57h+var_C8]
0x1800a57f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a57f6  lea     rcx, [rbp+57h+var_80]
0x1800a57fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a57ff  lea     rcx, [rbp+57h+var_C0]
0x1800a5803  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a5808  lea     rcx, [rbp+57h+hKeyDest]
0x1800a580c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a5811  lea     rcx, [rbp+57h+hKeySrc]
0x1800a5815  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a581a  xor     ebx, ebx
0x1800a581c  lea     rcx, [rbp+57h+var_A8]
0x1800a5820  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a5825  mov     eax, ebx
0x1800a5827  mov     rcx, [rbp+57h+var_40]
0x1800a582b  xor     rcx, rsp; StackCookie
0x1800a582e  call    __security_check_cookie
0x1800a5833  add     rsp, 0F8h
0x1800a583a  pop     r14
0x1800a583c  pop     r12
0x1800a583e  pop     rdi
0x1800a583f  pop     rsi
0x1800a5840  pop     rbx
0x1800a5841  pop     rbp
0x1800a5842  retn
```
