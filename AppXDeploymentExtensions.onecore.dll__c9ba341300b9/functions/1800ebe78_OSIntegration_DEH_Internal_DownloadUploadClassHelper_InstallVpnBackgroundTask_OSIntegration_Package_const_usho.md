# OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask(OSIntegration::Package const *,ushort const *,_VPN_PLUGIN_MANIFEST *)

- ea: `0x1800ebe78`
- end: `0x1800ec2f0`
- name: `?InstallVpnBackgroundTask@DownloadUploadClassHelper@Internal@DEH@OSIntegration@@SAJPEBVPackage@4@PEBGPEAU_VPN_PLUGIN_MANIFEST@@@Z`
- size: `1144`
- prototype: `__int64 __fastcall(const struct OSIntegration::Package *, const BYTE *, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005f418`

## callees

- `0x180012964`
- `0x18004f3c4`
- `0x180067050`
- `0x180070b78`
- `0x180080b84`
- `0x1800853cc`
- `0x180087238`
- `0x18009aff4`
- `0x1800cc418`
- `0x1800ebe78`
- `0x1800f0260`
- `0x180139a48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ebfd9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ec199`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ebfd9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800ec199`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ec219`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ec26b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ec219`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800ec26b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ec03a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800ec03a`
- `Windows.Networking.Vpn!VpnClientPluginInstall` at `0x1800ec29c`
- `Windows.Networking.Vpn!VpnClientPluginInstall` at `0x1800ec29c`

## string_xrefs

- `0x1800ec04d`: `!(wil::verify_bool(ConvertSidToStringSidW(package->GetVisibleUser(), &userSidString)))`
- `0x1800ebf51`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask`
- `0x1800ebffe`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask`
- `0x1800ec060`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask`
- `0x1800ec11d`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask`
- `0x1800ec1ba`: `OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask`
- `0x1800ebeef`: `Windows.Networking.Vpn.PluginBT.ClassId`
- `0x1800ec087`: `Windows.Networking.Vpn.PluginBT.ClassId`
- `0x1800ebf39`: `StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L"%s\\%s\\%s\\%s", L"OSDATA", BTC_REGKEY, package->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)`
- `0x1800ebf94`: `StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L"%s\\%s\\%s", BTC_REGKEY, package->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)`
- `0x1800ebedb`: `Common::StateSeparation::GetIsStateSeparationEnabled(&isStateSeparated)`
- `0x1800ec1ae`: `RegCreateKeyEx(HKEY_USERS, capabilitiesKeyPath, 0, NULL, REG_OPTION_NON_VOLATILE, KEY_READ | KEY_WRITE, &sa, &hKey, nullptr)`
- `0x1800ec227`: `RegSetValueEx(hKey.get(), BTC_REGVALUE_CAPABILITIES, 0, REG_DWORD, reinterpret_cast<const BYTE*>(&acidCapabilities), sizeof(DWORD))`
- `0x1800ec279`: `RegSetValueEx(hKey.get(), BTC_REGVALUE_AUMID, 0, REG_SZ, reinterpret_cast<const BYTE*>(appUserModelId), (DWORD)((wcslen(appUserModelId) + 1)*sizeof(WCHAR)))`
- `0x1800ebfeb`: `RegCreateKeyEx(HKEY_LOCAL_MACHINE, capabilitiesKeyPath, 0, NULL, REG_OPTION_NON_VOLATILE, KEY_READ | KEY_WRITE, NULL, &hKey, nullptr)`
- `0x1800ec0cf`: `StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L"%s\\%s\\%s\\%s", userSidString.get(), BTC_REGKEY, package->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)`
- `0x1800ec111`: `GetBackgroundTaskRegkeySD(userSidString.get(), &securityDescriptor)`
- `0x1800ec2aa`: `VpnClientPluginInstall( vpnPluginManifest->backgroundTaskAcid, package->GetPackageMoniker(), package->GetVisibleUser() )`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask(
        const struct OSIntegration::Package *a1,
        const BYTE *a2,
        const unsigned __int16 **a3)
{
  int IsStateSeparationEnabled; // eax
  unsigned int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  int v12; // eax
  HKEY *phkResult; // rax
  LSTATUS Key; // eax
  const char *v15; // rax
  __int64 v16; // rdx
  const char *v17; // rax
  __int64 v18; // rdx
  int v19; // eax
  int BackgroundTaskRegkeySD; // eax
  HKEY *v21; // rax
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  __int64 v24; // rax
  LSTATUS v25; // eax
  unsigned int v26; // eax
  const char *samDesired; // [rsp+28h] [rbp-D8h]
  const char *samDesireda; // [rsp+28h] [rbp-D8h]
  const char *samDesiredb; // [rsp+28h] [rbp-D8h]
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+30h] [rbp-D0h]
  unsigned int lpSecurityAttributesa; // [rsp+30h] [rbp-D0h]
  bool v33; // [rsp+50h] [rbp-B0h] BYREF
  LPWSTR StringSid; // [rsp+58h] [rbp-A8h] BYREF
  void *v35; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[8]; // [rsp+70h] [rbp-90h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SubKey[784]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+6E8h] [rbp+5E8h]

  hKey = 0;
  if ( !*((_BYTE *)a1 + 406) )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    if ( ConvertSidToStringSidW(*((PSID *)a1 + 98), &StringSid) )
    {
      lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)L"Windows.Networking.Vpn.PluginBT.ClassId";
      v19 = StringCchPrintfW(
              SubKey,
              0x30Cu,
              L"%s\\%s\\%s\\%s",
              StringSid,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability",
              *((_QWORD *)a1 + 89));
      v7 = v19;
      if ( v19 >= 0 )
      {
        v35 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &v35,
          0);
        BackgroundTaskRegkeySD = OSIntegration::DEH::Internal::DownloadUploadClassHelper::GetBackgroundTaskRegkeySD(
                                   StringSid,
                                   &v35);
        v7 = BackgroundTaskRegkeySD;
        if ( BackgroundTaskRegkeySD >= 0 )
        {
          *(_QWORD *)&SecurityAttributes.nLength = 24;
          *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
          SecurityAttributes.lpSecurityDescriptor = v35;
          v21 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
          v22 = RegCreateKeyExW(HKEY_USERS, SubKey, 0, 0, 0, 0x2001Fu, &SecurityAttributes, v21, 0);
          if ( !v22 )
          {
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v35);
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
            goto LABEL_25;
          }
          LODWORD(samDesiredb) = v22;
          v7 = wil::details::in1diag5::Return_Win32(
                 retaddr,
                 (void *)0xA6,
                 (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
                 "OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask",
                 "RegCreateKeyEx(HKEY_USERS, capabilitiesKeyPath, 0, NULL, REG_OPTION_NON_VOLATILE, KEY_READ | KEY_WRITE,"
                 " &sa, &hKey, nullptr)",
                 samDesiredb,
                 lpSecurityAttributesa);
        }
        else
        {
          LODWORD(samDesired) = BackgroundTaskRegkeySD;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x9A,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
            "OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask",
            "GetBackgroundTaskRegkeySD(userSidString.get(), &securityDescriptor)",
            samDesired,
            (int)L"Windows.Networking.Vpn.PluginBT.ClassId");
        }
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v35);
LABEL_16:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&StringSid);
        goto LABEL_34;
      }
      LODWORD(samDesired) = v19;
      v17 = "StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L\"%s\\\\%s\\\\%s\\\\%s\", userSidStrin"
            "g.get(), BTC_REGKEY, package->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)";
      v18 = 151;
    }
    else
    {
      v7 = -2147024882;
      LODWORD(samDesired) = -2147024882;
      v17 = "!(wil::verify_bool(ConvertSidToStringSidW(package->GetVisibleUser(), &userSidString)))";
      v18 = 143;
    }
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
      "OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask",
      v17,
      samDesired,
      (int)lpSecurityAttributes);
    goto LABEL_16;
  }
  v33 = 0;
  IsStateSeparationEnabled = Common::StateSeparation::GetIsStateSeparationEnabled(&v33);
  v7 = IsStateSeparationEnabled;
  if ( IsStateSeparationEnabled >= 0 )
  {
    v10 = *((_QWORD *)a1 + 89);
    if ( v33 )
    {
      lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)L"Windows.Networking.Vpn.PluginBT.ClassId";
      v11 = StringCchPrintfW(
              SubKey,
              0x30Cu,
              L"%s\\%s\\%s\\%s",
              L"OSDATA",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability",
              v10);
      v7 = v11;
      if ( v11 < 0 )
      {
        LODWORD(samDesired) = v11;
        v8 = "StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L\"%s\\\\%s\\\\%s\\\\%s\", L\"OSDATA\""
             ", BTC_REGKEY, package->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)";
        v9 = 117;
        goto LABEL_7;
      }
    }
    else
    {
      v12 = StringCchPrintfW(
              SubKey,
              0x30Cu,
              L"%s\\%s\\%s",
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Authentication\\LogonUI\\Notifications\\BackgroundCapability",
              v10,
              L"Windows.Networking.Vpn.PluginBT.ClassId");
      v7 = v12;
      if ( v12 < 0 )
      {
        LODWORD(samDesired) = v12;
        v8 = "StringCchPrintf(capabilitiesKeyPath, ARRAYSIZE(capabilitiesKeyPath), L\"%s\\\\%s\\\\%s\", BTC_REGKEY, packa"
             "ge->GetPackageSidString(), DownloadUploadClassConstants::vpnPluginbackgroundTaskClassId)";
        v9 = 126;
        goto LABEL_7;
      }
    }
    phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&hKey);
    Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0x2001Fu, 0, phkResult, 0);
    if ( Key )
    {
      LODWORD(samDesireda) = Key;
      v15 = "RegCreateKeyEx(HKEY_LOCAL_MACHINE, capabilitiesKeyPath, 0, NULL, REG_OPTION_NON_VOLATILE, KEY_READ | KEY_WRI"
            "TE, NULL, &hKey, nullptr)";
      v16 = 137;
LABEL_12:
      v7 = wil::details::in1diag5::Return_Win32(
             retaddr,
             (void *)v16,
             (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
             "OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask",
             v15,
             samDesireda,
             lpSecurityAttributesa);
      goto LABEL_34;
    }
LABEL_25:
    *(_DWORD *)Data = 34;
    v23 = RegSetValueExW(hKey, L"Capabilities", 0, 4u, Data, 4u);
    if ( v23 )
    {
      LODWORD(samDesireda) = v23;
      v15 = "RegSetValueEx(hKey.get(), BTC_REGVALUE_CAPABILITIES, 0, REG_DWORD, reinterpret_cast<const BYTE*>(&acidCapabi"
            "lities), sizeof(DWORD))";
      v16 = 175;
    }
    else
    {
      v24 = -1;
      do
        ++v24;
      while ( *(_WORD *)&a2[2 * v24] );
      v25 = RegSetValueExW(hKey, L"AppUserModelId", 0, 1u, a2, 2 * v24 + 2);
      if ( v25 )
      {
        LODWORD(samDesireda) = v25;
        v15 = "RegSetValueEx(hKey.get(), BTC_REGVALUE_AUMID, 0, REG_SZ, reinterpret_cast<const BYTE*>(appUserModelId), (D"
              "WORD)((wcslen(appUserModelId) + 1)*sizeof(WCHAR)))";
        v16 = 182;
      }
      else
      {
        v26 = VpnClientPluginInstall(a3[2], *((const unsigned __int16 **)a1 + 28), *((void **)a1 + 98));
        if ( !v26 )
        {
          v7 = 0;
          goto LABEL_34;
        }
        LODWORD(samDesireda) = v26;
        v15 = "VpnClientPluginInstall( vpnPluginManifest->backgroundTaskAcid, package->GetPackageMoniker(), package->GetVisibleUser() )";
        v16 = 188;
      }
    }
    goto LABEL_12;
  }
  LODWORD(samDesired) = IsStateSeparationEnabled;
  v8 = "Common::StateSeparation::GetIsStateSeparationEnabled(&isStateSeparated)";
  v9 = 106;
LABEL_7:
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\downloaduploaddeh\\downloaduploadclasshelper.cpp",
    "OSIntegration::DEH::Internal::DownloadUploadClassHelper::InstallVpnBackgroundTask",
    v8,
    samDesired,
    (int)lpSecurityAttributes);
LABEL_34:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v7;
}

```

## disassembly

```asm
0x1800ebe78  mov     [rsp-8+arg_18], rbx
0x1800ebe7d  push    rbp
0x1800ebe7e  push    rsi
0x1800ebe7f  push    rdi
0x1800ebe80  push    r14
0x1800ebe82  push    r15
0x1800ebe84  lea     rbp, [rsp-5C0h]
0x1800ebe8c  sub     rsp, 6C0h
0x1800ebe93  mov     rax, cs:__security_cookie
0x1800ebe9a  xor     rax, rsp
0x1800ebe9d  mov     [rbp+5E0h+var_30], rax
0x1800ebea4  mov     r14, r8
0x1800ebea7  mov     rsi, rdx
0x1800ebeaa  mov     rdi, rcx
0x1800ebead  xor     r15d, r15d
0x1800ebeb0  mov     [rsp+6E0h+hKey], r15
0x1800ebeb5  cmp     [rcx+196h], r15b
0x1800ebebc  jz      loc_1800EC01D
0x1800ebec2  mov     [rsp+6E0h+var_690], r15b
0x1800ebec7  lea     rcx, [rsp+6E0h+var_690]; bool *
0x1800ebecc  call    ?GetIsStateSeparationEnabled@StateSeparation@Common@@SAJPEA_N@Z; Common::StateSeparation::GetIsStateSeparationEnabled(bool *)
0x1800ebed1  mov     ebx, eax
0x1800ebed3  test    eax, eax
0x1800ebed5  jns     short loc_1800EBEE8
0x1800ebed7  mov     [rsp+6E0h+samDesired], eax
0x1800ebedb  lea     rax, aCommonStatesep; "Common::StateSeparation::GetIsStateSepa"...
0x1800ebee2  lea     edx, [r15+6Ah]
0x1800ebee6  jmp     short loc_1800EBF45
0x1800ebee8  mov     rcx, [rdi+2C8h]
0x1800ebeef  lea     rax, aWindowsNetwork_1; "Windows.Networking.Vpn.PluginBT.ClassId"
0x1800ebef6  mov     edx, 30Ch; unsigned __int64
0x1800ebefb  cmp     [rsp+6E0h+var_690], r15b
0x1800ebf00  jz      short loc_1800EBF69
0x1800ebf02  mov     [rsp+6E0h+lpSecurityAttributes], rax; int
0x1800ebf07  mov     qword ptr [rsp+6E0h+samDesired], rcx
0x1800ebf0c  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ebf13  mov     qword ptr [rsp+6E0h+dwOptions], rax
0x1800ebf18  lea     r9, aOsdata; "OSDATA"
0x1800ebf1f  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800ebf26  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x1800ebf2a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ebf2f  mov     ebx, eax
0x1800ebf31  test    eax, eax
0x1800ebf33  jns     short loc_1800EBFA2
0x1800ebf35  mov     [rsp+6E0h+samDesired], eax; char *
0x1800ebf39  lea     rax, aStringcchprint_32; "StringCchPrintf(capabilitiesKeyPath, AR"...
0x1800ebf40  mov     edx, 75h ; 'u'; void *
0x1800ebf45  mov     rcx, [rbp+5E8h]; this
0x1800ebf4c  mov     qword ptr [rsp+6E0h+dwOptions], rax; char *
0x1800ebf51  lea     r9, aOsintegrationD_424; "OSIntegration::DEH::Internal::DownloadU"...
0x1800ebf58  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ebf5f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800ebf64  jmp     loc_1800EC2BE
0x1800ebf69  mov     qword ptr [rsp+6E0h+samDesired], rax
0x1800ebf6e  mov     qword ptr [rsp+6E0h+dwOptions], rcx
0x1800ebf73  lea     r9, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ebf7a  lea     r8, aSSS; "%s\\%s\\%s"
0x1800ebf81  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x1800ebf85  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ebf8a  mov     ebx, eax
0x1800ebf8c  test    eax, eax
0x1800ebf8e  jns     short loc_1800EBFA2
0x1800ebf90  mov     [rsp+6E0h+samDesired], eax
0x1800ebf94  lea     rax, aStringcchprint_14; "StringCchPrintf(capabilitiesKeyPath, AR"...
0x1800ebf9b  mov     edx, 7Eh ; '~'
0x1800ebfa0  jmp     short loc_1800EBF45
0x1800ebfa2  lea     rcx, [rsp+6E0h+hKey]
0x1800ebfa7  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800ebfac  mov     [rsp+6E0h+lpdwDisposition], r15; lpdwDisposition
0x1800ebfb1  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1800ebfb6  mov     [rsp+6E0h+lpSecurityAttributes], r15; unsigned int
0x1800ebfbb  mov     [rsp+6E0h+samDesired], 2001Fh; samDesired
0x1800ebfc3  mov     [rsp+6E0h+dwOptions], r15d; dwOptions
0x1800ebfc8  xor     r9d, r9d; lpClass
0x1800ebfcb  xor     r8d, r8d; Reserved
0x1800ebfce  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x1800ebfd2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ebfd9  call    cs:__imp_RegCreateKeyExW
0x1800ebfdf  test    eax, eax
0x1800ebfe1  jz      loc_1800EC1ED
0x1800ebfe7  mov     [rsp+6E0h+samDesired], eax; char *
0x1800ebfeb  lea     rax, aRegcreatekeyex_1; "RegCreateKeyEx(HKEY_LOCAL_MACHINE, capa"...
0x1800ebff2  mov     edx, 89h; void *
0x1800ebff7  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ebffe  lea     r9, aOsintegrationD_424; "OSIntegration::DEH::Internal::DownloadU"...
0x1800ec005  mov     qword ptr [rsp+6E0h+dwOptions], rax; char *
0x1800ec00a  mov     rcx, [rbp+5E8h]; this
0x1800ec011  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800ec016  mov     ebx, eax
0x1800ec018  jmp     loc_1800EC2BE
0x1800ec01d  mov     [rsp+6E0h+StringSid], r15
0x1800ec022  xor     edx, edx
0x1800ec024  lea     rcx, [rsp+6E0h+StringSid]
0x1800ec029  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800ec02e  lea     rdx, [rsp+6E0h+StringSid]; StringSid
0x1800ec033  mov     rcx, [rdi+310h]; Sid
0x1800ec03a  call    cs:__imp_ConvertSidToStringSidW
0x1800ec040  test    eax, eax
0x1800ec042  jnz     short loc_1800EC087
0x1800ec044  mov     ebx, 8007000Eh
0x1800ec049  mov     [rsp+6E0h+samDesired], ebx; char *
0x1800ec04d  lea     rax, aWilVerifyBoolC; "!(wil::verify_bool(ConvertSidToStringSi"...
0x1800ec054  mov     edx, 8Fh; void *
0x1800ec059  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ec060  lea     r9, aOsintegrationD_424; "OSIntegration::DEH::Internal::DownloadU"...
0x1800ec067  mov     qword ptr [rsp+6E0h+dwOptions], rax; char *
0x1800ec06c  mov     rcx, [rbp+5E8h]; this
0x1800ec073  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800ec078  lea     rcx, [rsp+6E0h+StringSid]
0x1800ec07d  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ec082  jmp     loc_1800EC2BE
0x1800ec087  lea     rax, aWindowsNetwork_1; "Windows.Networking.Vpn.PluginBT.ClassId"
0x1800ec08e  mov     [rsp+6E0h+lpSecurityAttributes], rax; int
0x1800ec093  mov     rax, [rdi+2C8h]
0x1800ec09a  mov     qword ptr [rsp+6E0h+samDesired], rax
0x1800ec09f  lea     rax, aSoftwareMicros_25; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800ec0a6  mov     qword ptr [rsp+6E0h+dwOptions], rax
0x1800ec0ab  mov     r9, [rsp+6E0h+StringSid]
0x1800ec0b0  lea     r8, aSSSS; "%s\\%s\\%s\\%s"
0x1800ec0b7  mov     edx, 30Ch; unsigned __int64
0x1800ec0bc  lea     rcx, [rbp+5E0h+SubKey]; Buffer
0x1800ec0c0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800ec0c5  mov     ebx, eax
0x1800ec0c7  test    eax, eax
0x1800ec0c9  jns     short loc_1800EC0E0
0x1800ec0cb  mov     [rsp+6E0h+samDesired], eax
0x1800ec0cf  lea     rax, aStringcchprint_24; "StringCchPrintf(capabilitiesKeyPath, AR"...
0x1800ec0d6  mov     edx, 97h
0x1800ec0db  jmp     loc_1800EC059
0x1800ec0e0  mov     [rsp+6E0h+var_680], r15
0x1800ec0e5  xor     edx, edx
0x1800ec0e7  lea     rcx, [rsp+6E0h+var_680]
0x1800ec0ec  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800ec0f1  lea     rdx, [rsp+6E0h+var_680]; void **
0x1800ec0f6  mov     rcx, [rsp+6E0h+StringSid]; unsigned __int16 *
0x1800ec0fb  call    ?GetBackgroundTaskRegkeySD@DownloadUploadClassHelper@Internal@DEH@OSIntegration@@CAJPEBGPEAPEAX@Z; OSIntegration::DEH::Internal::DownloadUploadClassHelper::GetBackgroundTaskRegkeySD(ushort const *,void * *)
0x1800ec100  mov     ebx, eax
0x1800ec102  test    eax, eax
0x1800ec104  jns     short loc_1800EC144
0x1800ec106  mov     rcx, [rbp+5E8h]; this
0x1800ec10d  mov     [rsp+6E0h+samDesired], eax; char *
0x1800ec111  lea     rax, aGetbackgroundt_0; "GetBackgroundTaskRegkeySD(userSidString"...
0x1800ec118  mov     qword ptr [rsp+6E0h+dwOptions], rax; char *
0x1800ec11d  lea     r9, aOsintegrationD_424; "OSIntegration::DEH::Internal::DownloadU"...
0x1800ec124  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ec12b  mov     edx, 9Ah; void *
0x1800ec130  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x1800ec135  lea     rcx, [rsp+6E0h+var_680]
0x1800ec13a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ec13f  jmp     loc_1800EC078
0x1800ec144  mov     qword ptr [rsp+6E0h+SecurityAttributes.nLength], 18h
0x1800ec14d  xorps   xmm0, xmm0
0x1800ec150  movups  xmmword ptr [rbp+5E0h+SecurityAttributes.lpSecurityDescriptor], xmm0
0x1800ec154  mov     rax, [rsp+6E0h+var_680]
0x1800ec159  mov     [rbp+5E0h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800ec15d  lea     rcx, [rsp+6E0h+hKey]
0x1800ec162  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x1800ec167  mov     [rsp+6E0h+lpdwDisposition], r15; lpdwDisposition
0x1800ec16c  mov     [rsp+6E0h+phkResult], rax; phkResult
0x1800ec171  lea     rax, [rsp+6E0h+SecurityAttributes]
0x1800ec176  mov     [rsp+6E0h+lpSecurityAttributes], rax; unsigned int
0x1800ec17b  mov     [rsp+6E0h+samDesired], 2001Fh; samDesired
0x1800ec183  mov     [rsp+6E0h+dwOptions], r15d; dwOptions
0x1800ec188  xor     r9d, r9d; lpClass
0x1800ec18b  xor     r8d, r8d; Reserved
0x1800ec18e  lea     rdx, [rbp+5E0h+SubKey]; lpSubKey
0x1800ec192  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800ec199  call    cs:__imp_RegCreateKeyExW
0x1800ec19f  test    eax, eax
0x1800ec1a1  jz      short loc_1800EC1D9
0x1800ec1a3  mov     rcx, [rbp+5E8h]; this
0x1800ec1aa  mov     [rsp+6E0h+samDesired], eax; char *
0x1800ec1ae  lea     rax, aRegcreatekeyex_0; "RegCreateKeyEx(HKEY_USERS, capabilities"...
0x1800ec1b5  mov     qword ptr [rsp+6E0h+dwOptions], rax; char *
0x1800ec1ba  lea     r9, aOsintegrationD_424; "OSIntegration::DEH::Internal::DownloadU"...
0x1800ec1c1  lea     r8, aOnecoreAdminAp_114; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800ec1c8  mov     edx, 0A6h; void *
0x1800ec1cd  call    ?Return_Win32@in1diag5@details@wil@@YAJPEAXIPEBD11K@Z; wil::details::in1diag5::Return_Win32(void *,uint,char const *,char const *,char const *,ulong)
0x1800ec1d2  mov     ebx, eax
0x1800ec1d4  jmp     loc_1800EC135
0x1800ec1d9  lea     rcx, [rsp+6E0h+var_680]
0x1800ec1de  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ec1e3  lea     rcx, [rsp+6E0h+StringSid]
0x1800ec1e8  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800ec1ed  mov     dword ptr [rsp+6E0h+Data], 22h ; '"'
0x1800ec1f5  mov     r9d, 4; dwType
0x1800ec1fb  mov     [rsp+6E0h+samDesired], r9d; cbData
0x1800ec200  lea     rax, [rsp+6E0h+Data]
0x1800ec205  mov     qword ptr [rsp+6E0h+dwOptions], rax; lpData
0x1800ec20a  xor     r8d, r8d; Reserved
0x1800ec20d  lea     rdx, aCapabilities; "Capabilities"
0x1800ec214  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800ec219  call    cs:__imp_RegSetValueExW
0x1800ec21f  test    eax, eax
0x1800ec221  jz      short loc_1800EC238
0x1800ec223  mov     [rsp+6E0h+samDesired], eax
0x1800ec227  lea     rax, aRegsetvalueexH_0; "RegSetValueEx(hKey.get(), BTC_REGVALUE_"...
0x1800ec22e  mov     edx, 0AFh
0x1800ec233  jmp     loc_1800EBFF7
0x1800ec238  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ec23c  inc     rax
0x1800ec23f  cmp     [rsi+rax*2], r15w
0x1800ec244  jnz     short loc_1800EC23C
0x1800ec246  lea     eax, ds:2[rax*2]
0x1800ec24d  mov     [rsp+6E0h+samDesired], eax; cbData
0x1800ec251  mov     qword ptr [rsp+6E0h+dwOptions], rsi; lpData
0x1800ec256  mov     r9d, 1; dwType
0x1800ec25c  xor     r8d, r8d; Reserved
0x1800ec25f  lea     rdx, aAppusermodelid_1; "AppUserModelId"
0x1800ec266  mov     rcx, [rsp+6E0h+hKey]; hKey
0x1800ec26b  call    cs:__imp_RegSetValueExW
0x1800ec271  test    eax, eax
0x1800ec273  jz      short loc_1800EC28A
0x1800ec275  mov     [rsp+6E0h+samDesired], eax
0x1800ec279  lea     rax, aRegsetvalueexH; "RegSetValueEx(hKey.get(), BTC_REGVALUE_"...
0x1800ec280  mov     edx, 0B6h
0x1800ec285  jmp     loc_1800EBFF7
0x1800ec28a  mov     r8, [rdi+310h]
0x1800ec291  mov     rdx, [rdi+0E0h]
0x1800ec298  mov     rcx, [r14+10h]
0x1800ec29c  call    cs:__imp_?VpnClientPluginInstall@@YAKPEBG0PEAX@Z; VpnClientPluginInstall(ushort const *,ushort const *,void *)
0x1800ec2a2  test    eax, eax
0x1800ec2a4  jz      short loc_1800EC2BB
0x1800ec2a6  mov     [rsp+6E0h+samDesired], eax
0x1800ec2aa  lea     rax, aVpnclientplugi_2; "VpnClientPluginInstall( vpnPluginManife"...
0x1800ec2b1  mov     edx, 0BCh
0x1800ec2b6  jmp     loc_1800EBFF7
0x1800ec2bb  mov     ebx, r15d
0x1800ec2be  lea     rcx, [rsp+6E0h+hKey]
0x1800ec2c3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800ec2c8  mov     eax, ebx
0x1800ec2ca  mov     rcx, [rbp+5E0h+var_30]
0x1800ec2d1  xor     rcx, rsp; StackCookie
0x1800ec2d4  call    __security_check_cookie
0x1800ec2d9  mov     rbx, [rsp+6E0h+arg_18]
0x1800ec2e1  add     rsp, 6C0h
0x1800ec2e8  pop     r15
0x1800ec2ea  pop     r14
0x1800ec2ec  pop     rdi
0x1800ec2ed  pop     rsi
0x1800ec2ee  pop     rbp
0x1800ec2ef  retn
```
