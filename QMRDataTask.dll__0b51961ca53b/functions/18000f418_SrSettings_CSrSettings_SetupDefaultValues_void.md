# SrSettings::CSrSettings::SetupDefaultValues(void)

- ea: `0x18000f418`
- end: `0x1800103ec`
- name: `?SetupDefaultValues@CSrSettings@SrSettings@@AEAAJXZ`
- size: `4052`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000b290`

## callees

- `0x180002178`
- `0x18000687c`
- `0x18000b9a8`
- `0x18000f418`
- `0x180010a0c`
- `0x1800117a0`
- `0x180011980`
- `0x180011a20`
- `0x180011b60`
- `0x180011c80`
- `0x180011d54`
- `0x180012f30`
- `0x180013008`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000f72a`
- `msvcrt!_wcsicmp` at `0x18000f749`
- `msvcrt!_wcsicmp` at `0x18000f75d`
- `msvcrt!_wcsicmp` at `0x18000f771`
- `msvcrt!_wcsicmp` at `0x18000f81e`
- `msvcrt!_wcsicmp` at `0x18000f72a`
- `msvcrt!_wcsicmp` at `0x18000f749`
- `msvcrt!_wcsicmp` at `0x18000f75d`
- `msvcrt!_wcsicmp` at `0x18000f771`
- `msvcrt!_wcsicmp` at `0x18000f81e`
- `KERNEL32!GetLastError` at `0x18000f6d2`
- `KERNEL32!GetLastError` at `0x18000fc74`
- `KERNEL32!GetLastError` at `0x18000fc92`
- `KERNEL32!GetLastError` at `0x180010117`
- `KERNEL32!GetLastError` at `0x1800101b2`
- `KERNEL32!GetLastError` at `0x1800101e8`
- `KERNEL32!GetLastError` at `0x18000f6d2`
- `KERNEL32!GetLastError` at `0x18000fc74`
- `KERNEL32!GetLastError` at `0x18000fc92`
- `KERNEL32!GetLastError` at `0x180010117`
- `KERNEL32!GetLastError` at `0x1800101b2`
- `KERNEL32!GetLastError` at `0x1800101e8`
- `KERNEL32!GetProcAddress` at `0x18000fc27`
- `KERNEL32!GetProcAddress` at `0x18000ff78`
- `KERNEL32!GetProcAddress` at `0x18001006c`
- `KERNEL32!GetProcAddress` at `0x18001007f`
- `KERNEL32!GetProcAddress` at `0x180010092`
- `KERNEL32!GetProcAddress` at `0x18000fc27`
- `KERNEL32!GetProcAddress` at `0x18000ff78`
- `KERNEL32!GetProcAddress` at `0x18001006c`
- `KERNEL32!GetProcAddress` at `0x18001007f`
- `KERNEL32!GetProcAddress` at `0x180010092`
- `KERNEL32!FreeLibrary` at `0x18000fe89`
- `KERNEL32!FreeLibrary` at `0x1800101e0`
- `KERNEL32!FreeLibrary` at `0x180010259`
- `KERNEL32!FreeLibrary` at `0x18000fe89`
- `KERNEL32!FreeLibrary` at `0x1800101e0`
- `KERNEL32!FreeLibrary` at `0x180010259`
- `KERNEL32!LoadLibraryExW` at `0x180010050`
- `KERNEL32!LoadLibraryExW` at `0x180010050`
- `KERNEL32!GetProcessHeap` at `0x180010366`
- `KERNEL32!GetProcessHeap` at `0x180010366`
- `KERNEL32!LoadLibraryW` at `0x18000fc0f`
- `KERNEL32!LoadLibraryW` at `0x18000ff46`
- `KERNEL32!LoadLibraryW` at `0x18000fc0f`
- `KERNEL32!LoadLibraryW` at `0x18000ff46`
- `KERNEL32!HeapFree` at `0x180010374`
- `KERNEL32!HeapFree` at `0x180010374`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000feeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001038b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fa47`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fb1b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fdec`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fe99`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000fea9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000feeb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001038b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fe24`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000fe24`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000ff0b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800103a7`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x18000ff0b`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x1800103a7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f9f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000facb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fdc7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f9f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000facb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000fdc7`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000f5fe`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18000f5fe`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f658`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f9c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fa9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd89`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f566`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f658`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f9c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fa9b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fce7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000fd89`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f885`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18000f885`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f908`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000f908`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180010006`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x180010006`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001002d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaQueryInformationPolicy` at `0x18001002d`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001021b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18001021b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001024b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x18001024b`

## string_xrefs

- `0x18000f8a2`: `COM is already initialized in apartment-threaded mode`
- `0x18000f8b5`: `Failed to initialize COM. Err = 0x%08x`
- `0x18000f92c`: `DeferFeatureUpdatePeriodInDays`
- `0x18000f937`: `DeferQualityUpdatePeriodInDays`
- `0x18000f958`: `DeferFeatureUpdatesPeriodInDays`
- `0x18000f963`: `DeferQualityUpdatesPeriodInDays`
- `0x18000f979`: `UpdateServiceUrl`
- `0x18000f984`: `FeatureUpdateEnrolled`
- `0x18000f98f`: `QualityUpdateEnrolled`
- `0x18000f99a`: `DriverUpdateEnrolled`
- `0x18000f9bd`: `Microsoft\Windows\WindowsUpdate`
- `0x18000fa2c`: `Found registry key: [%s] under HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18000fa0d`: `Failed to find registry key: [%s] under HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate. Error: 0x%08x`
- `0x18000fa6d`: `WindowsUpdate key not found.`
- `0x18000fa5f`: `Failed to open HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate. Error: 0x%08x`
- `0x18000fa91`: `Microsoft\PolicyManager\current\device\Update`
- `0x18000fb00`: `Found registry key: [%s] under HKLM\Software\Microsoft\PolicyManager\current\device\Update`
- `0x18000fae1`: `Failed to find registry key: [%s] under HKLM\Software\Microsoft\PolicyManager\current\device\Update. Error: 0x%08x`
- `0x18000fb3e`: `Update key not found.`
- `0x18000fb30`: `Failed to open HKLM\Software\Microsoft\PolicyManager\current\device\Update. Error: 0x%08x`
- `0x18000ff3f`: `dsreg.dll`
- `0x1800101c7`: `Failed to load function from dsreg.dll. Error: 0x%08x`
- `0x1800101fd`: `Failed to load dsreg.dll for Entra joined detection. Error: 0x%08x`
- `0x180010012`: `Failed to open LSA policy. Status: 0x%08x`
- `0x180010049`: `offlinelsa.dll`
- `0x180010062`: `LsaOfflineOpenPolicy`
- `0x1800100be`: `Failed to open LSA policy handle offline. Status: 0x%08x`
- `0x18001012c`: `Failed to get function pointers from offlinelsa.dll. Error: 0x%08x`
- `0x18000fc08`: `MDMRegistration.dll`
- `0x18000fc89`: `Failed to get function pointer from MDMRegistration.dll. Error: 0x%08x`
- `0x18000fca4`: `Failed to load MDMRegistration.dll. Error: 0x%08x`
- `0x18000fcfb`: `Failed to open HKLM\Software\Microsoft\Provisioning\OMADM\Accounts. Error: 0x%08x`
- `0x18000fd35`: `Failed to open HKLM\Software\Microsoft\Enrollments. Error: 0x%08x`
- `0x18000f581`: `Failed to open Software hive. Error: 0x%08x`
- `0x18000f5c1`: `Failed to assign target OS path to software hive path. Error: 0x%08x`
- `0x18000f5ca`: `\System32\config\SOFTWARE`
- `0x18000f5e7`: `Failed to append SOFTWARE to software hive path. Error: 0x%08x`
- `0x18000f676`: `Failed to open loaded %s key. Error: 0x%08x`
- `0x18000f6e7`: `Failed to get Edition ID from registry. Error: 0x%08x`
- `0x18000fba8`: `Failed to detect Windows Update policy. Error: 0x%08x`
- `0x1800102b2`: `  Windows Update Policy: %s`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::SetupDefaultValues(SrSettings::CSrSettings *this)
{
  HMODULE v2; // r12
  const unsigned __int16 *v4; // rbx
  LSTATUS v5; // eax
  unsigned int v6; // edi
  const wchar_t *v7; // r8
  LSTATUS KeyW; // eax
  const WCHAR *v9; // r9
  const wchar_t *v10; // r8
  LSTATUS v11; // eax
  wchar_t *String; // r14
  signed int LastError; // eax
  char v14; // bl
  HKEY v15; // r13
  unsigned int v16; // ebx
  unsigned int v17; // eax
  int v18; // edi
  char v19; // r15
  const wchar_t *v20; // r9
  unsigned int v21; // eax
  int v22; // r15d
  const WCHAR *v23; // r12
  LSTATUS Value; // eax
  unsigned int v25; // eax
  int v26; // r15d
  const WCHAR *v27; // r12
  LSTATUS v28; // eax
  HKEY v29; // rdi
  bool v30; // r13
  HMODULE LibraryW; // rax
  HMODULE v32; // rdi
  FARPROC ProcAddress; // rax
  int v34; // eax
  signed int v35; // eax
  signed int v36; // eax
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  DWORD i; // edx
  int v40; // eax
  const wchar_t *v41; // r9
  void (*v42)(void); // rbx
  HMODULE v43; // rdi
  FARPROC v44; // rax
  int v45; // eax
  bool v46; // r13
  const wchar_t *v47; // r9
  NTSTATUS v48; // eax
  unsigned int v49; // ebx
  NTSTATUS InformationPolicy; // eax
  HMODULE Library; // rax
  FARPROC v52; // rbx
  FARPROC v53; // r13
  int v54; // eax
  signed int v55; // eax
  bool v56; // bl
  const wchar_t *v57; // r9
  signed int v58; // eax
  signed int v59; // eax
  char v60; // r12
  const wchar_t *v61; // rbx
  const wchar_t *v62; // r9
  const wchar_t *v63; // r9
  HANDLE ProcessHeap; // rax
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  char v68; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v69; // [rsp+40h] [rbp-C0h]
  unsigned __int8 v70; // [rsp+41h] [rbp-BFh]
  bool v71; // [rsp+41h] [rbp-BFh]
  char v72; // [rsp+42h] [rbp-BEh]
  char v73; // [rsp+43h] [rbp-BDh]
  bool v74; // [rsp+44h] [rbp-BCh]
  HKEY v75; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v76; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cchName[2]; // [rsp+68h] [rbp-98h] BYREF
  HKEY v80; // [rsp+70h] [rbp-90h] BYREF
  DWORD cbData[2]; // [rsp+78h] [rbp-88h] BYREF
  wchar_t *v82; // [rsp+80h] [rbp-80h]
  LPCWSTR lpFile[2]; // [rsp+88h] [rbp-78h] BYREF
  _WORD v84[8]; // [rsp+98h] [rbp-68h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES lpValueName; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR v86[7]; // [rsp+D8h] [rbp-28h]
  WCHAR SubKey[256]; // [rsp+110h] [rbp+10h] BYREF

  v2 = 0;
  hKey = 0;
  lpFile[0] = v84;
  lpFile[1] = v84;
  v84[0] = 0;
  if ( !*((_BYTE *)this + 3945) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"CSrSettings not initialized");
    if ( lpFile[0] != v84 )
      operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942421LL;
  }
  v72 = 0;
  v4 = L"0";
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetImpl'::`2'::impl) )
    v4 = L"30";
  utl::_Tree<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::less<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>> const,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>,0>::clear((char *)this + 168);
  SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"Off");
  SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"Off");
  SrSettings::CSrSettings::AddDefaultValue(this, L"HeadlessMode", L"Off");
  SrSettings::CSrSettings::AddDefaultValue(this, L"TotalWaitTime", L"180");
  SrSettings::CSrSettings::AddDefaultValue(this, L"WaitInterval", v4);
  if ( *((_BYTE *)this + 3946) )
  {
    v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      v7 = L"Failed to open Software hive. Error: 0x%08x";
LABEL_12:
      SrSettings::CSrSettings::Trace(this, 2, v7, v6);
      goto LABEL_205;
    }
LABEL_27:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl'::`2'::impl)
      && *((_DWORD *)this + 821) )
    {
      SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"Off");
      SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"Off");
    }
    String = (wchar_t *)RegGetString(hKey);
    v82 = String;
    if ( !String )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
      v7 = L"Failed to get Edition ID from registry. Error: 0x%08x";
      goto LABEL_12;
    }
    v6 = 0;
    v14 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl) )
      SrSettings::CSrSettings::Trace(this, 0, L"Edition ID: %s", String);
    if ( _wcsicmp(String, L"Core")
      && _wcsicmp(String, L"CoreN")
      && _wcsicmp(String, L"CoreCountrySpecific")
      && _wcsicmp(String, L"CoreSingleLanguage") )
    {
      if ( (unsigned int)RegGetDword(hKey) == 1 )
      {
        SrSettings::CSrSettings::Trace(
          this,
          0,
          L"Enable CloudRemediation and AutoRemediation by default for Autopatch policy");
        SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"On");
        SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"On");
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl) )
          v14 = 1;
      }
    }
    else
    {
      SrSettings::CSrSettings::Trace(
        this,
        0,
        L"Enable CloudRemediation and AutoRemediation by default for Home edition");
      SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"On");
      SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"On");
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl)
      || _wcsicmp(String, L"Professional") )
    {
      goto LABEL_204;
    }
    SrSettings::CSrSettings::Trace(this, 0, L"Pro device, detecting whether the device is managed");
    if ( v14 )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Device is managed by Autopatch policy, skip the detection");
LABEL_204:
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, String);
      goto LABEL_205;
    }
    v73 = 0;
    v15 = hKey;
    v16 = -2147024809;
    if ( !hKey )
    {
      SrSettings::CSrSettings::Trace(this, 2, L"Invalid argument. Error: 0x%08x", 2147942487LL);
      v18 = -2147024809;
LABEL_90:
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to detect Windows Update policy. Error: 0x%08x",
        (unsigned int)v18);
      v68 = 0;
LABEL_91:
      v76 = 0;
      v80 = 0;
      v29 = hKey;
      if ( !hKey )
      {
        SrSettings::CSrSettings::Trace(this, 2, L"Invalid argument. Error: 0x%08x", 2147942487LL);
        goto LABEL_136;
      }
      v30 = 0;
      v71 = 0;
      if ( *((_BYTE *)this + 3946) )
      {
        SrSettings::CSrSettings::Trace(this, 0, L"Detecting MDM managed status online.");
        cchName[0] = 0;
        LibraryW = LoadLibraryW(L"MDMRegistration.dll");
        v32 = LibraryW;
        if ( !LibraryW )
        {
          v36 = GetLastError();
          v16 = v36;
          if ( v36 > 0 )
            v16 = (unsigned __int16)v36 | 0x80070000;
          SrSettings::CSrSettings::Trace(this, 2, L"Failed to load MDMRegistration.dll. Error: 0x%08x", v16);
          goto LABEL_129;
        }
        ProcAddress = GetProcAddress(LibraryW, "IsDeviceRegisteredWithManagement");
        if ( !ProcAddress )
        {
          v35 = GetLastError();
          v16 = v35;
          if ( v35 > 0 )
            v16 = (unsigned __int16)v35 | 0x80070000;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to get function pointer from MDMRegistration.dll. Error: 0x%08x",
            v16);
          goto LABEL_128;
        }
        v34 = ((__int64 (__fastcall *)(DWORD *, _QWORD, _QWORD))ProcAddress)(cchName, 0, 0);
        v16 = v34;
        if ( v34 < 0 )
        {
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to detect MDM managed status online. Error: 0x%08x",
            (unsigned int)v34);
LABEL_128:
          FreeLibrary(v32);
          goto LABEL_129;
        }
        v30 = cchName[0] != 0;
        v71 = cchName[0] != 0;
      }
      else
      {
        SrSettings::CSrSettings::Trace(this, 0, L"Detecting MDM managed status offline.");
        v37 = RegOpenKeyExW(v29, L"Microsoft\\Provisioning\\OMADM\\Accounts", 0, 0x20019u, &v76);
        v16 = v37;
        if ( v37 )
        {
          if ( v37 > 0 )
            v16 = (unsigned __int16)v37 | 0x80070000;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to open HKLM\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts. Error: 0x%08x",
            v16);
          goto LABEL_129;
        }
        v38 = RegOpenKeyExW(v29, L"Microsoft\\Enrollments", 0, 0x20019u, &v80);
        v16 = v38;
        if ( v38 )
        {
          if ( v38 > 0 )
            v16 = (unsigned __int16)v38 | 0x80070000;
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to open HKLM\\Software\\Microsoft\\Enrollments. Error: 0x%08x",
            v16);
          goto LABEL_129;
        }
        v32 = 0;
        v16 = 0;
        for ( i = 0; ; i = (unsigned int)v2 )
        {
          cchName[0] = 256;
          if ( RegEnumKeyExW(v76, i, SubKey, cchName, 0, 0, 0, 0) )
            break;
          v75 = 0;
          if ( !RegOpenKeyExW(v80, SubKey, 0, 0x20019u, &v75) )
          {
            *(_DWORD *)Data = 0;
            cbData[0] = 4;
            if ( !RegQueryValueExW(v75, L"enrollmentType", 0, 0, Data, cbData) && *(_DWORD *)Data <= 0xDu )
            {
              v40 = 8289;
              if ( _bittest(&v40, *(unsigned int *)Data) )
              {
                SrSettings::CSrSettings::Trace(this, 0, L"Found MDM enrollment type: %d");
                v30 = 1;
                v71 = 1;
                RegCloseKey(v75);
                break;
              }
            }
            RegCloseKey(v75);
          }
          LODWORD(v2) = (_DWORD)v2 + 1;
        }
        v2 = 0;
      }
      v41 = L"true";
      if ( !v30 )
        v41 = L"false";
      SrSettings::CSrSettings::Trace(this, 0, L"MDM managed status: %s", v41);
      if ( v32 )
        goto LABEL_128;
LABEL_129:
      if ( v76 )
        RegCloseKey(v76);
      if ( v80 )
        RegCloseKey(v80);
      if ( (v16 & 0x80000000) == 0 )
      {
LABEL_137:
        if ( hKey )
        {
          RegCloseKey(hKey);
          hKey = 0;
        }
        if ( v72 )
        {
          RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"$OSHive$Software");
          v72 = 0;
        }
        v80 = 0;
        *(_QWORD *)cbData = 0;
        v75 = 0;
        v42 = 0;
        v76 = 0;
        memset(&lpValueName, 0, sizeof(lpValueName));
        *(_DWORD *)Data = 0;
        v43 = LoadLibraryW(L"dsreg.dll");
        *(_QWORD *)cchName = v43;
        if ( !v43 )
        {
          v59 = GetLastError();
          v6 = v59;
          if ( v59 > 0 )
            v6 = (unsigned __int16)v59 | 0x80070000;
          SrSettings::CSrSettings::Trace(
            this,
            1,
            L"Failed to load dsreg.dll for Entra joined detection. Error: 0x%08x",
            v6);
          goto LABEL_180;
        }
        SrSettings::CSrSettings::Trace(this, 0, L"Detecting Entra joined status.");
        v44 = GetProcAddress(v43, "DsrIsDeviceJoined");
        if ( !v44 )
        {
          v58 = GetLastError();
          v6 = v58;
          if ( v58 > 0 )
            v6 = (unsigned __int16)v58 | 0x80070000;
          SrSettings::CSrSettings::Trace(this, 1, L"Failed to load function from dsreg.dll. Error: 0x%08x", v6);
          goto LABEL_176;
        }
        v45 = ((__int64 (__fastcall *)(BYTE *, _QWORD))v44)(Data, 0);
        v6 = v45;
        if ( v45 < 0 )
        {
          SrSettings::CSrSettings::Trace(this, 1, L"Failed to call DsrIsDeviceJoined. Error: 0x%08x", (unsigned int)v45);
LABEL_176:
          FreeLibrary(*(HMODULE *)cchName);
LABEL_180:
          if ( v75 )
            LsaFreeMemory(v75);
          if ( v42 && *(_QWORD *)cbData )
          {
            v42();
            *(_QWORD *)cbData = 0;
          }
          if ( v80 )
            LsaClose(v80);
          if ( v2 )
            FreeLibrary(v2);
          if ( (v6 & 0x80000000) == 0 )
          {
            v60 = v73;
          }
          else
          {
            SrSettings::CSrSettings::Trace(this, 2, L"Failed to detect domain join status. Error: 0x%08x", v6);
            v6 = 0;
            v60 = 0;
          }
          SrSettings::CSrSettings::Trace(this, 0, L"Detected device management statuses:");
          v61 = L"Yes";
          v62 = L"Yes";
          if ( !v68 )
            v62 = L"No";
          SrSettings::CSrSettings::Trace(this, 0, L"  Windows Update Policy: %s", v62);
          v63 = L"Yes";
          if ( !v60 )
            v63 = L"No";
          SrSettings::CSrSettings::Trace(this, 0, L"  Domain Joined: %s", v63);
          if ( !v71 )
            v61 = L"No";
          SrSettings::CSrSettings::Trace(this, 0, L"  MDM Enrolled: %s", v61);
          if ( !v68 && !v60 && !v71 )
          {
            SrSettings::CSrSettings::Trace(this, 0, L"Device is unmanaged, setting QuickScan to On");
            SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"On");
            SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"On");
          }
          String = v82;
          goto LABEL_204;
        }
        v46 = *(_DWORD *)Data == 1;
        v74 = *(_DWORD *)Data == 1;
        v47 = L"true";
        if ( *(_DWORD *)Data != 1 )
          v47 = L"false";
        SrSettings::CSrSettings::Trace(this, 0, L"Entra joined status: %s", v47);
        if ( *((_BYTE *)this + 3946) )
        {
          SrSettings::CSrSettings::Trace(this, 0, L"Detecting AD join status for online OS.");
          v48 = LsaOpenPolicy(0, &lpValueName, 0x2000000u, (PLSA_HANDLE)&v80);
          v49 = v48;
          if ( v48 < 0 )
          {
            SrSettings::CSrSettings::Trace(this, 2, L"Failed to open LSA policy. Status: 0x%08x", (unsigned int)v48);
LABEL_159:
            SrSettings::CSrSettings::Trace(
              this,
              2,
              L"Failed to query promary domain info from LSA policy. Status: 0x%08x",
              v49);
            v6 = v49 | 0x10000000;
LABEL_172:
            v42 = (void (*)(void))v76;
            goto LABEL_176;
          }
          InformationPolicy = LsaQueryInformationPolicy(v80, PolicyPrimaryDomainInformation, (PVOID *)&v75);
        }
        else
        {
          SrSettings::CSrSettings::Trace(this, 0, L"Detecting AD join status for offline OS.");
          Library = LoadLibraryExW(L"offlinelsa.dll", 0, 0);
          v2 = Library;
          if ( !Library )
            goto LABEL_163;
          v52 = GetProcAddress(Library, "LsaOfflineOpenPolicy");
          v53 = GetProcAddress(v2, "LsaOfflineQueryInformationPolicy");
          v76 = (HKEY)GetProcAddress(v2, "LsaOfflineClose");
          if ( !v52 || !v53 )
          {
            v55 = GetLastError();
            v6 = v55;
            if ( v55 > 0 )
              v6 = (unsigned __int16)v55 | 0x80070000;
            SrSettings::CSrSettings::Trace(
              this,
              2,
              L"Failed to get function pointers from offlinelsa.dll. Error: 0x%08x",
              v6);
            goto LABEL_172;
          }
          v54 = ((__int64 (__fastcall *)(_QWORD, DWORD *))v52)(*((_QWORD *)this + 1), cbData);
          v49 = v54;
          if ( v54 < 0 )
          {
            SrSettings::CSrSettings::Trace(
              this,
              2,
              L"Failed to open LSA policy handle offline. Status: 0x%08x",
              (unsigned int)v54);
            goto LABEL_159;
          }
          InformationPolicy = ((__int64 (__fastcall *)(_QWORD, __int64, HKEY *))v53)(*(_QWORD *)cbData, 3, &v75);
          v46 = v74;
        }
        v49 = InformationPolicy;
        if ( InformationPolicy < 0 )
          goto LABEL_159;
LABEL_163:
        v56 = v75 && *((_QWORD *)v75 + 2);
        v57 = L"true";
        if ( !v56 )
          v57 = L"false";
        SrSettings::CSrSettings::Trace(this, 0, L"AD joined status: %s", v57);
        LODWORD(phkResult) = v56;
        SrSettings::CSrSettings::Trace(
          this,
          0,
          L"Detecting domain join status. Entra joined: %d, AD joined: %d",
          v46,
          phkResult);
        if ( v46 || (v73 = 0, v56) )
          v73 = 1;
        goto LABEL_172;
      }
LABEL_136:
      SrSettings::CSrSettings::Trace(this, 2, L"Failed to detect MDM enrollment status. Error: 0x%08x", v16);
      v71 = 0;
      goto LABEL_137;
    }
    if ( *((_BYTE *)this + 3946) )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Detecting WU policy for online OS");
      v17 = CoInitializeEx(0, 0);
      v18 = v17;
      if ( v17 <= 1 )
      {
        v19 = 1;
      }
      else
      {
        v19 = 0;
        if ( v17 == -2147417850 )
        {
          v18 = 0;
          SrSettings::CSrSettings::Trace(this, 0, L"COM is already initialized in apartment-threaded mode");
        }
        else
        {
          SrSettings::CSrSettings::Trace(this, 1, L"Failed to initialize COM. Err = 0x%08x", v17);
          v18 = 0;
        }
      }
      v68 = IsEnterprisePolicyConfigured();
      v20 = L"true";
      if ( !v68 )
        v20 = L"false";
      SrSettings::CSrSettings::Trace(this, 0, L"WU policy: %s", v20);
      v2 = 0;
      if ( v19 )
        CoUninitialize();
    }
    else
    {
      v18 = 0;
      SrSettings::CSrSettings::Trace(this, 0, L"Detecting WU policy for offline OS");
      v69 = 0;
      v70 = 0;
      *(_QWORD *)&lpValueName.Length = L"DeferFeatureUpdatePeriodInDays";
      lpValueName.RootDirectory = L"DeferQualityUpdatePeriodInDays";
      lpValueName.ObjectName = (PLSA_UNICODE_STRING)L"TargetReleaseVersionInfo";
      *(_QWORD *)&lpValueName.Attributes = L"WUServer";
      v86[0] = L"DeferFeatureUpdatesPeriodInDays";
      v86[1] = L"DeferQualityUpdatesPeriodInDays";
      v86[2] = L"TargetReleaseVersion";
      v86[3] = L"UpdateServiceUrl";
      v86[4] = L"FeatureUpdateEnrolled";
      v86[5] = L"QualityUpdateEnrolled";
      v86[6] = L"DriverUpdateEnrolled";
      v76 = 0;
      v21 = RegOpenKeyExW(v15, L"Microsoft\\Windows\\WindowsUpdate", 0, 0x20019u, &v76);
      if ( v21 )
      {
        if ( v21 - 2 <= 1 )
          SrSettings::CSrSettings::Trace(this, 0, L"WindowsUpdate key not found.", v21);
        else
          SrSettings::CSrSettings::Trace(
            this,
            0,
            L"Failed to open HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate. Error: 0x%08x",
            v21);
      }
      else
      {
        v22 = 0;
        while ( 1 )
        {
          v23 = (const WCHAR *)*((_QWORD *)&lpValueName.Length + v22);
          Value = RegQueryValueExW(v76, v23, 0, 0, 0, 0);
          if ( !Value )
            break;
          if ( Value != 2 )
          {
            LODWORD(phkResulta) = Value;
            SrSettings::CSrSettings::Trace(
              this,
              0,
              L"Failed to find registry key: [%s] under HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate. Error: 0x%08x",
              v23,
              phkResulta);
          }
          if ( (unsigned int)++v22 >= 4 )
            goto LABEL_66;
        }
        SrSettings::CSrSettings::Trace(
          this,
          0,
          L"Found registry key: [%s] under HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
          v23);
        v69 = 1;
LABEL_66:
        RegCloseKey(v76);
      }
      v75 = 0;
      v25 = RegOpenKeyExW(v15, L"Microsoft\\PolicyManager\\current\\device\\Update", 0, 0x20019u, &v75);
      if ( v25 )
      {
        if ( v25 - 2 <= 1 )
          SrSettings::CSrSettings::Trace(this, 0, L"Update key not found.", v25);
        else
          SrSettings::CSrSettings::Trace(
            this,
            0,
            L"Failed to open HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Update. Error: 0x%08x",
            v25);
      }
      else
      {
        v26 = 0;
        while ( 1 )
        {
          v27 = v86[v26];
          v28 = RegQueryValueExW(v75, v27, 0, 0, 0, 0);
          if ( !v28 )
            break;
          if ( v28 != 2 )
          {
            LODWORD(phkResultb) = v28;
            SrSettings::CSrSettings::Trace(
              this,
              0,
              L"Failed to find registry key: [%s] under HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Update. Error: 0x%08x",
              v27,
              phkResultb);
          }
          if ( (unsigned int)++v26 >= 7 )
            goto LABEL_78;
        }
        SrSettings::CSrSettings::Trace(
          this,
          0,
          L"Found registry key: [%s] under HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Update",
          v27);
        v70 = 1;
LABEL_78:
        RegCloseKey(v75);
      }
      LODWORD(phkResultb) = v70;
      SrSettings::CSrSettings::Trace(
        this,
        0,
        L"Detecting WU policy for offline OS. GPManaged: %d, MDMManaged: %d",
        v69,
        phkResultb);
      if ( v69 )
      {
        v2 = 0;
      }
      else
      {
        v2 = 0;
        if ( !v70 )
        {
          v68 = 0;
          goto LABEL_87;
        }
      }
      v68 = 1;
    }
LABEL_87:
    if ( v18 >= 0 )
      goto LABEL_91;
    goto LABEL_90;
  }
  if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                          lpFile,
                          *((_QWORD *)this + 1)) )
  {
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                            lpFile,
                            L"\\System32\\config\\SOFTWARE") )
    {
      KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"$OSHive$Software", lpFile[0]);
      v6 = KeyW;
      if ( KeyW )
      {
        if ( KeyW > 0 )
          v6 = (unsigned __int16)KeyW | 0x80070000;
        v9 = (const WCHAR *)*((_QWORD *)this + 1);
        v10 = L"Failed to load software hive from %s. Error: 0x%08x";
      }
      else
      {
        v72 = 1;
        v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"$OSHive$Software", 0, 0x20019u, &hKey);
        v6 = v11;
        if ( !v11 )
          goto LABEL_27;
        if ( v11 > 0 )
          v6 = (unsigned __int16)v11 | 0x80070000;
        v9 = L"$OSHive$Software";
        v10 = L"Failed to open loaded %s key. Error: 0x%08x";
      }
      LODWORD(phkResult) = v6;
      SrSettings::CSrSettings::Trace(this, 2, v10, v9, phkResult);
    }
    else
    {
      v6 = -2147024888;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to append SOFTWARE to software hive path. Error: 0x%08x",
        2147942408LL);
    }
  }
  else
  {
    v6 = -2147024888;
    SrSettings::CSrSettings::Trace(
      this,
      2,
      L"Failed to assign target OS path to software hive path. Error: 0x%08x",
      2147942408LL);
  }
LABEL_205:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v72 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"$OSHive$Software");
  if ( lpFile[0] != v84 )
    operator delete((void *)lpFile[0], (const struct std::nothrow_t *)&std::nothrow);
  return v6;
}

```

## disassembly

```asm
0x18000f418  push    rbp
0x18000f41a  push    rbx
0x18000f41b  push    rsi
0x18000f41c  push    rdi
0x18000f41d  push    r12
0x18000f41f  push    r13
0x18000f421  push    r14
0x18000f423  push    r15
0x18000f425  lea     rbp, [rsp-228h]
0x18000f42d  sub     rsp, 328h
0x18000f434  mov     rax, cs:__security_cookie
0x18000f43b  xor     rax, rsp
0x18000f43e  mov     [rbp+260h+var_50], rax
0x18000f445  mov     rsi, rcx
0x18000f448  xor     r12d, r12d
0x18000f44b  mov     [rsp+360h+hKey], r12
0x18000f450  lea     rax, [rbp+260h+var_2C8]
0x18000f454  mov     [rbp+260h+lpFile], rax
0x18000f458  lea     rax, [rbp+260h+var_2C8]
0x18000f45c  mov     [rbp+260h+var_2D0], rax
0x18000f460  mov     [rbp+260h+var_2C8], r12w
0x18000f465  cmp     [rcx+0F69h], r12b
0x18000f46c  jnz     short loc_18000F4A3
0x18000f46e  lea     r8, aCsrsettingsNot; "CSrSettings not initialized"
0x18000f475  lea     edx, [r12+2]
0x18000f47a  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f47f  nop
0x18000f480  lea     rax, [rbp+260h+var_2C8]
0x18000f484  mov     rcx, [rbp+260h+lpFile]; void *
0x18000f488  cmp     rcx, rax
0x18000f48b  jz      short loc_18000F499
0x18000f48d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f494  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000f499  mov     eax, 80070015h
0x18000f49e  jmp     loc_1800103C9
0x18000f4a3  mov     [rsp+360h+var_31E], r12b
0x18000f4a8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetImpl(void)'::`2'::impl
0x18000f4af  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::__private_IsEnabled(void)
0x18000f4b4  lea     rcx, a30; "30"
0x18000f4bb  lea     rbx, a0; "0"
0x18000f4c2  test    al, al
0x18000f4c4  cmovz   rbx, rcx
0x18000f4c8  lea     rcx, [rsi+0A8h]
0x18000f4cf  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x18000f4d4  lea     r14, aOff; "Off"
0x18000f4db  mov     r8, r14; unsigned __int16 *
0x18000f4de  lea     rdx, aCloudremediati; "CloudRemediation"
0x18000f4e5  mov     rcx, rsi; this
0x18000f4e8  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f4ed  mov     r8, r14; unsigned __int16 *
0x18000f4f0  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18000f4f7  mov     rcx, rsi; this
0x18000f4fa  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f4ff  mov     r8, r14; unsigned __int16 *
0x18000f502  lea     rdx, aHeadlessmode; "HeadlessMode"
0x18000f509  mov     rcx, rsi; this
0x18000f50c  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f511  lea     r8, a180; "180"
0x18000f518  lea     rdx, aTotalwaittime; "TotalWaitTime"
0x18000f51f  mov     rcx, rsi; this
0x18000f522  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f527  mov     r8, rbx; unsigned __int16 *
0x18000f52a  lea     rdx, aWaitinterval; "WaitInterval"
0x18000f531  mov     rcx, rsi; this
0x18000f534  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f539  mov     rbx, 0FFFFFFFF80000002h
0x18000f540  cmp     [rsi+0F6Ah], r12b
0x18000f547  jz      short loc_18000F59D
0x18000f549  lea     rax, [rsp+360h+hKey]
0x18000f54e  mov     [rsp+360h+phkResult], rax; phkResult
0x18000f553  mov     r9d, 20019h; samDesired
0x18000f559  xor     r8d, r8d; ulOptions
0x18000f55c  lea     rdx, aSoftware_1; "Software"
0x18000f563  mov     rcx, rbx; hKey
0x18000f566  call    cs:__imp_RegOpenKeyExW
0x18000f56c  mov     edi, eax
0x18000f56e  test    eax, eax
0x18000f570  jz      loc_18000F67F
0x18000f576  jle     short loc_18000F581
0x18000f578  movzx   edi, ax
0x18000f57b  or      edi, 80070000h
0x18000f581  lea     r8, aFailedToOpenSo; "Failed to open Software hive. Error: 0x"...
0x18000f588  mov     r9d, edi
0x18000f58b  mov     edx, 2
0x18000f590  mov     rcx, rsi
0x18000f593  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f598  jmp     loc_180010381
0x18000f59d  mov     rdx, [rsi+8]
0x18000f5a1  mov     r8, [rsi+10h]
0x18000f5a5  sub     r8, rdx
0x18000f5a8  sar     r8, 1
0x18000f5ab  lea     rcx, [rbp+260h+lpFile]
0x18000f5af  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18000f5b4  test    al, al
0x18000f5b6  jnz     short loc_18000F5CA
0x18000f5b8  mov     r9d, 80070008h
0x18000f5be  mov     edi, r9d
0x18000f5c1  lea     r8, aFailedToAssign_11; "Failed to assign target OS path to soft"...
0x18000f5c8  jmp     short loc_18000F58B
0x18000f5ca  lea     rdx, aSystem32Config; "\\System32\\config\\SOFTWARE"
0x18000f5d1  lea     rcx, [rbp+260h+lpFile]
0x18000f5d5  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *)
0x18000f5da  test    al, al
0x18000f5dc  jnz     short loc_18000F5F0
0x18000f5de  mov     r9d, 80070008h
0x18000f5e4  mov     edi, r9d
0x18000f5e7  lea     r8, aFailedToAppend_4; "Failed to append SOFTWARE to software h"...
0x18000f5ee  jmp     short loc_18000F58B
0x18000f5f0  mov     r8, [rbp+260h+lpFile]; lpFile
0x18000f5f4  lea     rdx, aOshiveSoftware; "$OSHive$Software"
0x18000f5fb  mov     rcx, rbx; hKey
0x18000f5fe  call    cs:__imp_RegLoadKeyW
0x18000f604  mov     edi, eax
0x18000f606  test    eax, eax
0x18000f608  jz      short loc_18000F636
0x18000f60a  jle     short loc_18000F615
0x18000f60c  movzx   edi, ax
0x18000f60f  or      edi, 80070000h
0x18000f615  mov     r9, [rsi+8]
0x18000f619  lea     r8, aFailedToLoadSo; "Failed to load software hive from %s. E"...
0x18000f620  mov     dword ptr [rsp+360h+phkResult], edi
0x18000f624  mov     edx, 2
0x18000f629  mov     rcx, rsi
0x18000f62c  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f631  jmp     loc_180010381
0x18000f636  mov     [rsp+360h+var_31E], 1
0x18000f63b  lea     rax, [rsp+360h+hKey]
0x18000f640  mov     [rsp+360h+phkResult], rax; phkResult
0x18000f645  mov     r9d, 20019h; samDesired
0x18000f64b  xor     r8d, r8d; ulOptions
0x18000f64e  lea     rdx, aOshiveSoftware; "$OSHive$Software"
0x18000f655  mov     rcx, rbx; hKey
0x18000f658  call    cs:__imp_RegOpenKeyExW
0x18000f65e  mov     edi, eax
0x18000f660  test    eax, eax
0x18000f662  jz      short loc_18000F67F
0x18000f664  jle     short loc_18000F66F
0x18000f666  movzx   edi, ax
0x18000f669  or      edi, 80070000h
0x18000f66f  lea     r9, aOshiveSoftware; "$OSHive$Software"
0x18000f676  lea     r8, aFailedToOpenLo; "Failed to open loaded %s key. Error: 0x"...
0x18000f67d  jmp     short loc_18000F620
0x18000f67f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl(void)'::`2'::impl
0x18000f686  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)
0x18000f68b  test    al, al
0x18000f68d  jz      short loc_18000F6BC
0x18000f68f  cmp     [rsi+0CD4h], r12d
0x18000f696  jz      short loc_18000F6BC
0x18000f698  mov     r8, r14; unsigned __int16 *
0x18000f69b  lea     rdx, aCloudremediati; "CloudRemediation"
0x18000f6a2  mov     rcx, rsi; this
0x18000f6a5  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f6aa  mov     r8, r14; unsigned __int16 *
0x18000f6ad  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18000f6b4  mov     rcx, rsi; this
0x18000f6b7  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f6bc  mov     rcx, [rsp+360h+hKey]
0x18000f6c1  call    RegGetString
0x18000f6c6  mov     r14, rax
0x18000f6c9  mov     [rbp+260h+var_2E0], rax
0x18000f6cd  test    rax, rax
0x18000f6d0  jnz     short loc_18000F6F3
0x18000f6d2  call    cs:__imp_GetLastError
0x18000f6d8  mov     edi, eax
0x18000f6da  test    eax, eax
0x18000f6dc  jle     short loc_18000F6E7
0x18000f6de  movzx   edi, ax
0x18000f6e1  or      edi, 80070000h
0x18000f6e7  lea     r8, aFailedToGetEdi; "Failed to get Edition ID from registry."...
0x18000f6ee  jmp     loc_18000F588
0x18000f6f3  mov     edi, r12d
0x18000f6f6  mov     bl, r12b
0x18000f6f9  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl(void)'::`2'::impl
0x18000f700  mov     rcx, r15
0x18000f703  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18000f708  test    al, al
0x18000f70a  jz      short loc_18000F720
0x18000f70c  mov     r9, r14
0x18000f70f  lea     r8, aEditionIdS; "Edition ID: %s"
0x18000f716  xor     edx, edx
0x18000f718  mov     rcx, rsi
0x18000f71b  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f720  lea     rdx, aCore; "Core"
0x18000f727  mov     rcx, r14; String1
0x18000f72a  call    cs:__imp__wcsicmp
0x18000f730  lea     r13, aOn; "On"
0x18000f737  test    eax, eax
0x18000f739  jz      loc_18000F7CF
0x18000f73f  lea     rdx, aCoren; "CoreN"
0x18000f746  mov     rcx, r14; String1
0x18000f749  call    cs:__imp__wcsicmp
0x18000f74f  test    eax, eax
0x18000f751  jz      short loc_18000F7CF
0x18000f753  lea     rdx, aCorecountryspe; "CoreCountrySpecific"
0x18000f75a  mov     rcx, r14; String1
0x18000f75d  call    cs:__imp__wcsicmp
0x18000f763  test    eax, eax
0x18000f765  jz      short loc_18000F7CF
0x18000f767  lea     rdx, aCoresinglelang; "CoreSingleLanguage"
0x18000f76e  mov     rcx, r14; String1
0x18000f771  call    cs:__imp__wcsicmp
0x18000f777  test    eax, eax
0x18000f779  jz      short loc_18000F7CF
0x18000f77b  mov     rcx, [rsp+360h+hKey]
0x18000f780  call    RegGetDword
0x18000f785  cmp     eax, 1
0x18000f788  jnz     short loc_18000F804
0x18000f78a  lea     r8, aEnableCloudrem; "Enable CloudRemediation and AutoRemedia"...
0x18000f791  xor     edx, edx
0x18000f793  mov     rcx, rsi
0x18000f796  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f79b  mov     r8, r13; unsigned __int16 *
0x18000f79e  lea     rdx, aCloudremediati; "CloudRemediation"
0x18000f7a5  mov     rcx, rsi; this
0x18000f7a8  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f7ad  mov     r8, r13; unsigned __int16 *
0x18000f7b0  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18000f7b7  mov     rcx, rsi; this
0x18000f7ba  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f7bf  mov     rcx, r15
0x18000f7c2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18000f7c7  test    al, al
0x18000f7c9  jz      short loc_18000F804
0x18000f7cb  mov     bl, 1
0x18000f7cd  jmp     short loc_18000F804
0x18000f7cf  lea     r8, aEnableCloudrem_0; "Enable CloudRemediation and AutoRemedia"...
0x18000f7d6  xor     edx, edx
0x18000f7d8  mov     rcx, rsi
0x18000f7db  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f7e0  mov     r8, r13; unsigned __int16 *
0x18000f7e3  lea     rdx, aCloudremediati; "CloudRemediation"
0x18000f7ea  mov     rcx, rsi; this
0x18000f7ed  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f7f2  mov     r8, r13; unsigned __int16 *
0x18000f7f5  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18000f7fc  mov     rcx, rsi; this
0x18000f7ff  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18000f804  mov     rcx, r15
0x18000f807  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18000f80c  test    al, al
0x18000f80e  jz      loc_180010366
0x18000f814  lea     rdx, aProfessional; "Professional"
0x18000f81b  mov     rcx, r14; String1
0x18000f81e  call    cs:__imp__wcsicmp
0x18000f824  test    eax, eax
0x18000f826  jnz     loc_180010366
0x18000f82c  lea     r8, aProDeviceDetec; "Pro device, detecting whether the devic"...
0x18000f833  xor     edx, edx
0x18000f835  mov     rcx, rsi
0x18000f838  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f83d  mov     rcx, rsi
0x18000f840  test    bl, bl
0x18000f842  jnz     loc_18001034F
0x18000f848  mov     [rsp+360h+var_31D], r12b
0x18000f84d  mov     r13, [rsp+360h+hKey]
0x18000f852  mov     ebx, 80070057h
0x18000f857  mov     r14d, 2
0x18000f85d  test    r13, r13
0x18000f860  jz      loc_18000FB91
0x18000f866  xor     edx, edx
0x18000f868  cmp     [rsi+0F6Ah], r12b
0x18000f86f  jz      loc_18000F913
0x18000f875  lea     r8, aDetectingWuPol_0; "Detecting WU policy for online OS"
0x18000f87c  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f881  xor     edx, edx; dwCoInit
0x18000f883  xor     ecx, ecx; pvReserved
0x18000f885  call    cs:__imp_CoInitializeEx
0x18000f88b  mov     edi, eax
0x18000f88d  cmp     eax, 1
0x18000f890  jbe     short loc_18000F8CB
0x18000f892  mov     r15b, r12b
0x18000f895  mov     rcx, rsi
0x18000f898  cmp     eax, 80010106h
0x18000f89d  jnz     short loc_18000F8B2
0x18000f89f  mov     edi, r12d
0x18000f8a2  lea     r8, aComIsAlreadyIn; "COM is already initialized in apartment"...
0x18000f8a9  xor     edx, edx
0x18000f8ab  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f8b0  jmp     short loc_18000F8CE
0x18000f8b2  mov     r9d, eax
0x18000f8b5  lea     r8, aFailedToInitia_0; "Failed to initialize COM. Err = 0x%08x"
0x18000f8bc  mov     edx, 1
0x18000f8c1  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f8c6  mov     edi, r12d
0x18000f8c9  jmp     short loc_18000F8CE
0x18000f8cb  mov     r15b, 1
0x18000f8ce  call    IsEnterprisePolicyConfigured
0x18000f8d3  mov     [rsp+360h+var_320], al
0x18000f8d7  lea     r9, aTrue; "true"
0x18000f8de  test    al, al
0x18000f8e0  lea     rcx, aFalse; "false"
0x18000f8e7  cmovz   r9, rcx
0x18000f8eb  lea     r8, aWuPolicyS; "WU policy: %s"
0x18000f8f2  xor     edx, edx
0x18000f8f4  mov     rcx, rsi
0x18000f8f7  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18000f8fc  xor     r12d, r12d
0x18000f8ff  test    r15b, r15b
0x18000f902  jz      loc_18000FB8B
0x18000f908  call    cs:__imp_CoUninitialize
  ... truncated ...
```
