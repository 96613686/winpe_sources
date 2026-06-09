# SrSettings::CSrSettings::SetupDefaultValues(void)

- ea: `0x18004afc8`
- end: `0x18004bf92`
- name: `?SetupDefaultValues@CSrSettings@SrSettings@@AEAAJXZ`
- size: `4042`
- prototype: `__int64 __fastcall(SrSettings::CSrSettings *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180049360`

## callees

- `0x1800075ec`
- `0x1800076d4`
- `0x18001efcc`
- `0x180046864`
- `0x180049a60`
- `0x18004afc8`
- `0x18004c0e8`
- `0x18004c44c`
- `0x18004c4b0`
- `0x18004c528`
- `0x18004c5c8`
- `0x18004c6c8`
- `0x18004c794`
- `0x18005cf30`
- `0x18005f010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004b2ce`
- `msvcrt!_wcsicmp` at `0x18004b2ed`
- `msvcrt!_wcsicmp` at `0x18004b305`
- `msvcrt!_wcsicmp` at `0x18004b319`
- `msvcrt!_wcsicmp` at `0x18004b3d4`
- `msvcrt!_wcsicmp` at `0x18004b2ce`
- `msvcrt!_wcsicmp` at `0x18004b2ed`
- `msvcrt!_wcsicmp` at `0x18004b305`
- `msvcrt!_wcsicmp` at `0x18004b319`
- `msvcrt!_wcsicmp` at `0x18004b3d4`
- `KERNEL32!GetLastError` at `0x18004b276`
- `KERNEL32!GetLastError` at `0x18004b82a`
- `KERNEL32!GetLastError` at `0x18004b848`
- `KERNEL32!GetLastError` at `0x18004bccd`
- `KERNEL32!GetLastError` at `0x18004bd68`
- `KERNEL32!GetLastError` at `0x18004bd9e`
- `KERNEL32!GetLastError` at `0x18004b276`
- `KERNEL32!GetLastError` at `0x18004b82a`
- `KERNEL32!GetLastError` at `0x18004b848`
- `KERNEL32!GetLastError` at `0x18004bccd`
- `KERNEL32!GetLastError` at `0x18004bd68`
- `KERNEL32!GetLastError` at `0x18004bd9e`
- `KERNEL32!HeapFree` at `0x18004bf2a`
- `KERNEL32!HeapFree` at `0x18004bf2a`
- `KERNEL32!GetProcAddress` at `0x18004b7dd`
- `KERNEL32!GetProcAddress` at `0x18004bb2e`
- `KERNEL32!GetProcAddress` at `0x18004bc22`
- `KERNEL32!GetProcAddress` at `0x18004bc35`
- `KERNEL32!GetProcAddress` at `0x18004bc48`
- `KERNEL32!GetProcAddress` at `0x18004b7dd`
- `KERNEL32!GetProcAddress` at `0x18004bb2e`
- `KERNEL32!GetProcAddress` at `0x18004bc22`
- `KERNEL32!GetProcAddress` at `0x18004bc35`
- `KERNEL32!GetProcAddress` at `0x18004bc48`
- `KERNEL32!GetProcessHeap` at `0x18004bf1c`
- `KERNEL32!GetProcessHeap` at `0x18004bf1c`
- `KERNEL32!FreeLibrary` at `0x18004ba3f`
- `KERNEL32!FreeLibrary` at `0x18004bd96`
- `KERNEL32!FreeLibrary` at `0x18004be0f`
- `KERNEL32!FreeLibrary` at `0x18004ba3f`
- `KERNEL32!FreeLibrary` at `0x18004bd96`
- `KERNEL32!FreeLibrary` at `0x18004be0f`
- `KERNEL32!LoadLibraryW` at `0x18004b7c5`
- `KERNEL32!LoadLibraryW` at `0x18004bafc`
- `KERNEL32!LoadLibraryW` at `0x18004b7c5`
- `KERNEL32!LoadLibraryW` at `0x18004bafc`
- `KERNEL32!LoadLibraryExW` at `0x18004bc06`
- `KERNEL32!LoadLibraryExW` at `0x18004bc06`
- `ADVAPI32!LsaFreeMemory` at `0x18004bdd1`
- `ADVAPI32!LsaFreeMemory` at `0x18004bdd1`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18004bbe3`
- `ADVAPI32!LsaQueryInformationPolicy` at `0x18004bbe3`
- `ADVAPI32!LsaOpenPolicy` at `0x18004bbbc`
- `ADVAPI32!LsaOpenPolicy` at `0x18004bbbc`
- `ADVAPI32!RegQueryValueExW` at `0x18004b5ad`
- `ADVAPI32!RegQueryValueExW` at `0x18004b681`
- `ADVAPI32!RegQueryValueExW` at `0x18004b97d`
- `ADVAPI32!RegQueryValueExW` at `0x18004b5ad`
- `ADVAPI32!RegQueryValueExW` at `0x18004b681`
- `ADVAPI32!RegQueryValueExW` at `0x18004b97d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b104`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b1fc`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b57d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b651`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b89d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b8d7`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b93f`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b104`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b1fc`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b57d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b651`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b89d`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b8d7`
- `ADVAPI32!RegOpenKeyExW` at `0x18004b93f`
- `ADVAPI32!RegEnumKeyExW` at `0x18004b9da`
- `ADVAPI32!RegEnumKeyExW` at `0x18004b9da`
- `ADVAPI32!RegCloseKey` at `0x18004b5fd`
- `ADVAPI32!RegCloseKey` at `0x18004b6d1`
- `ADVAPI32!RegCloseKey` at `0x18004b9a2`
- `ADVAPI32!RegCloseKey` at `0x18004ba08`
- `ADVAPI32!RegCloseKey` at `0x18004ba4f`
- `ADVAPI32!RegCloseKey` at `0x18004ba5f`
- `ADVAPI32!RegCloseKey` at `0x18004baa1`
- `ADVAPI32!RegCloseKey` at `0x18004bf41`
- `ADVAPI32!RegCloseKey` at `0x18004b5fd`
- `ADVAPI32!RegCloseKey` at `0x18004b6d1`
- `ADVAPI32!RegCloseKey` at `0x18004b9a2`
- `ADVAPI32!RegCloseKey` at `0x18004ba08`
- `ADVAPI32!RegCloseKey` at `0x18004ba4f`
- `ADVAPI32!RegCloseKey` at `0x18004ba5f`
- `ADVAPI32!RegCloseKey` at `0x18004baa1`
- `ADVAPI32!RegCloseKey` at `0x18004bf41`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004bac1`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004bf5d`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004bac1`
- `ADVAPI32!RegUnLoadKeyW` at `0x18004bf5d`
- `ADVAPI32!RegLoadKeyW` at `0x18004b1a2`
- `ADVAPI32!RegLoadKeyW` at `0x18004b1a2`
- `ADVAPI32!LsaClose` at `0x18004be01`
- `ADVAPI32!LsaClose` at `0x18004be01`
- `ole32!CoUninitialize` at `0x18004b4be`
- `ole32!CoUninitialize` at `0x18004b4be`
- `ole32!CoInitializeEx` at `0x18004b43b`
- `ole32!CoInitializeEx` at `0x18004b43b`

## string_xrefs

- `0x18004b458`: `COM is already initialized in apartment-threaded mode`
- `0x18004b46b`: `Failed to initialize COM. Err = 0x%08x`
- `0x18004b4e2`: `DeferFeatureUpdatePeriodInDays`
- `0x18004b4ed`: `DeferQualityUpdatePeriodInDays`
- `0x18004b50e`: `DeferFeatureUpdatesPeriodInDays`
- `0x18004b519`: `DeferQualityUpdatesPeriodInDays`
- `0x18004b52f`: `UpdateServiceUrl`
- `0x18004b53a`: `FeatureUpdateEnrolled`
- `0x18004b545`: `QualityUpdateEnrolled`
- `0x18004b550`: `DriverUpdateEnrolled`
- `0x18004b573`: `Microsoft\Windows\WindowsUpdate`
- `0x18004b5e2`: `Found registry key: [%s] under HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18004b5c3`: `Failed to find registry key: [%s] under HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate. Error: 0x%08x`
- `0x18004b623`: `WindowsUpdate key not found.`
- `0x18004b615`: `Failed to open HKLM\Software\Policies\Microsoft\Windows\WindowsUpdate. Error: 0x%08x`
- `0x18004b647`: `Microsoft\PolicyManager\current\device\Update`
- `0x18004b6b6`: `Found registry key: [%s] under HKLM\Software\Microsoft\PolicyManager\current\device\Update`
- `0x18004b697`: `Failed to find registry key: [%s] under HKLM\Software\Microsoft\PolicyManager\current\device\Update. Error: 0x%08x`
- `0x18004b6f4`: `Update key not found.`
- `0x18004b6e6`: `Failed to open HKLM\Software\Microsoft\PolicyManager\current\device\Update. Error: 0x%08x`
- `0x18004baf5`: `dsreg.dll`
- `0x18004bd7d`: `Failed to load function from dsreg.dll. Error: 0x%08x`
- `0x18004bdb3`: `Failed to load dsreg.dll for Entra joined detection. Error: 0x%08x`
- `0x18004bbc8`: `Failed to open LSA policy. Status: 0x%08x`
- `0x18004bbff`: `offlinelsa.dll`
- `0x18004bc18`: `LsaOfflineOpenPolicy`
- `0x18004bc74`: `Failed to open LSA policy handle offline. Status: 0x%08x`
- `0x18004bce2`: `Failed to get function pointers from offlinelsa.dll. Error: 0x%08x`
- `0x18004b7be`: `MDMRegistration.dll`
- `0x18004b83f`: `Failed to get function pointer from MDMRegistration.dll. Error: 0x%08x`
- `0x18004b85a`: `Failed to load MDMRegistration.dll. Error: 0x%08x`
- `0x18004b8b1`: `Failed to open HKLM\Software\Microsoft\Provisioning\OMADM\Accounts. Error: 0x%08x`
- `0x18004b8eb`: `Failed to open HKLM\Software\Microsoft\Enrollments. Error: 0x%08x`
- `0x18004b11f`: `Failed to open Software hive. Error: 0x%08x`
- `0x18004b15f`: `Failed to assign target OS path to software hive path. Error: 0x%08x`
- `0x18004b16e`: `\System32\config\SOFTWARE`
- `0x18004b18b`: `Failed to append SOFTWARE to software hive path. Error: 0x%08x`
- `0x18004b21a`: `Failed to open loaded %s key. Error: 0x%08x`
- `0x18004b28b`: `Failed to get Edition ID from registry. Error: 0x%08x`
- `0x18004b32a`: `Microsoft\PolicyManager\current\device\update`
- `0x18004b75e`: `Failed to detect Windows Update policy. Error: 0x%08x`
- `0x18004be68`: `  Windows Update Policy: %s`

## pseudocode

```c
__int64 __fastcall SrSettings::CSrSettings::SetupDefaultValues(SrSettings::CSrSettings *this)
{
  HMODULE v2; // r12
  unsigned int v3; // edi
  const unsigned __int16 *v4; // rbx
  LSTATUS v5; // eax
  const wchar_t *v6; // r8
  LSTATUS KeyW; // eax
  const WCHAR *v8; // r9
  const wchar_t *v9; // r8
  LSTATUS v10; // eax
  wchar_t *String; // r14
  signed int LastError; // eax
  char v13; // bl
  HKEY v14; // r13
  unsigned int v15; // ebx
  unsigned int v16; // eax
  int v17; // edi
  char v18; // r15
  const wchar_t *v19; // r9
  unsigned int v20; // eax
  int v21; // r15d
  const WCHAR *v22; // r12
  LSTATUS Value; // eax
  unsigned int v24; // eax
  int v25; // r15d
  const WCHAR *v26; // r12
  LSTATUS v27; // eax
  HKEY v28; // rdi
  bool v29; // r13
  HMODULE LibraryW; // rax
  HMODULE v31; // rdi
  FARPROC ProcAddress; // rax
  int v33; // eax
  signed int v34; // eax
  signed int v35; // eax
  LSTATUS v36; // eax
  LSTATUS v37; // eax
  DWORD i; // edx
  int v39; // eax
  const wchar_t *v40; // r9
  void (*v41)(void); // rbx
  HMODULE v42; // rdi
  FARPROC v43; // rax
  int v44; // eax
  bool v45; // r13
  const wchar_t *v46; // r9
  NTSTATUS v47; // eax
  unsigned int v48; // ebx
  NTSTATUS InformationPolicy; // eax
  HMODULE Library; // rax
  FARPROC v51; // rbx
  FARPROC v52; // r13
  int v53; // eax
  signed int v54; // eax
  bool v55; // bl
  const wchar_t *v56; // r9
  signed int v57; // eax
  signed int v58; // eax
  char v59; // r12
  const wchar_t *v60; // rbx
  const wchar_t *v61; // r9
  const wchar_t *v62; // r9
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
  LPCWSTR v86[9]; // [rsp+D8h] [rbp-28h]
  WCHAR SubKey[256]; // [rsp+120h] [rbp+20h] BYREF

  v86[7] = (LPCWSTR)-2LL;
  v2 = 0;
  hKey = 0;
  lpFile[0] = v84;
  lpFile[1] = v84;
  v84[0] = 0;
  if ( !*((_BYTE *)this + 3945) )
  {
    SrSettings::CSrSettings::Trace(this, 2, L"CSrSettings not initialized");
    v3 = -2147024875;
    goto LABEL_203;
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
  if ( !*((_BYTE *)this + 3946) )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             lpFile,
                             *((_QWORD *)this + 1),
                             (__int64)(*((_QWORD *)this + 2) - *((_QWORD *)this + 1)) >> 1) )
    {
      v3 = -2147024888;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to assign target OS path to software hive path. Error: 0x%08x",
        2147942408LL);
      goto LABEL_199;
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             lpFile,
                             L"\\System32\\config\\SOFTWARE",
                             25) )
    {
      v3 = -2147024888;
      SrSettings::CSrSettings::Trace(
        this,
        2,
        L"Failed to append SOFTWARE to software hive path. Error: 0x%08x",
        2147942408LL);
      goto LABEL_199;
    }
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"$OSHive$Software", lpFile[0]);
    v3 = KeyW;
    if ( KeyW )
    {
      if ( KeyW > 0 )
        v3 = (unsigned __int16)KeyW | 0x80070000;
      v8 = (const WCHAR *)*((_QWORD *)this + 1);
      v9 = L"Failed to load software hive from %s. Error: 0x%08x";
    }
    else
    {
      v72 = 1;
      v10 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"$OSHive$Software", 0, 0x20019u, &hKey);
      v3 = v10;
      if ( !v10 )
        goto LABEL_24;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      v8 = L"$OSHive$Software";
      v9 = L"Failed to open loaded %s key. Error: 0x%08x";
    }
    SrSettings::CSrSettings::Trace(this, 2, v9, v8, v3);
    goto LABEL_199;
  }
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software", 0, 0x20019u, &hKey);
  v3 = v5;
  if ( !v5 )
  {
LABEL_24:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl'::`2'::impl)
      && *((_DWORD *)this + 821) )
    {
      SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"Off");
      SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"Off");
    }
    String = (wchar_t *)RegGetStringEx(hKey);
    v82 = String;
    if ( !String )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v6 = L"Failed to get Edition ID from registry. Error: 0x%08x";
      goto LABEL_10;
    }
    v3 = 0;
    v13 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl) )
      SrSettings::CSrSettings::Trace(this, 0, L"Edition ID: %s", String);
    if ( _wcsicmp(String, L"Core")
      && _wcsicmp(String, L"CoreN")
      && _wcsicmp(String, L"CoreCountrySpecific")
      && _wcsicmp(String, L"CoreSingleLanguage") )
    {
      if ( (unsigned int)RegGetDword(
                           hKey,
                           L"Microsoft\\PolicyManager\\current\\device\\update",
                           L"QuickMachineRecoveryEnrolled") == 1 )
      {
        SrSettings::CSrSettings::Trace(
          this,
          0,
          L"Enable CloudRemediation and AutoRemediation by default for Autopatch policy");
        SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"On");
        SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"On");
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl) )
          v13 = 1;
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
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl'::`2'::impl)
      && !_wcsicmp(String, L"Professional") )
    {
      SrSettings::CSrSettings::Trace(this, 0, L"Pro device, detecting whether the device is managed");
      if ( !v13 )
      {
        v73 = 0;
        v14 = hKey;
        v15 = -2147024809;
        if ( !hKey )
        {
          SrSettings::CSrSettings::Trace(this, 2, L"Invalid argument. Error: 0x%08x", 2147942487LL);
          v17 = -2147024809;
LABEL_87:
          SrSettings::CSrSettings::Trace(
            this,
            2,
            L"Failed to detect Windows Update policy. Error: 0x%08x",
            (unsigned int)v17);
          v68 = 0;
LABEL_88:
          v76 = 0;
          v80 = 0;
          v28 = hKey;
          if ( !hKey )
          {
            SrSettings::CSrSettings::Trace(this, 2, L"Invalid argument. Error: 0x%08x", 2147942487LL);
            goto LABEL_131;
          }
          v29 = 0;
          v71 = 0;
          if ( *((_BYTE *)this + 3946) )
          {
            SrSettings::CSrSettings::Trace(this, 0, L"Detecting MDM managed status online.");
            cchName[0] = 0;
            LibraryW = LoadLibraryW(L"MDMRegistration.dll");
            v31 = LibraryW;
            if ( !LibraryW )
            {
              v35 = GetLastError();
              v15 = v35;
              if ( v35 > 0 )
                v15 = (unsigned __int16)v35 | 0x80070000;
              SrSettings::CSrSettings::Trace(this, 2, L"Failed to load MDMRegistration.dll. Error: 0x%08x", v15);
              goto LABEL_124;
            }
            ProcAddress = GetProcAddress(LibraryW, "IsDeviceRegisteredWithManagement");
            if ( !ProcAddress )
            {
              v34 = GetLastError();
              v15 = v34;
              if ( v34 > 0 )
                v15 = (unsigned __int16)v34 | 0x80070000;
              SrSettings::CSrSettings::Trace(
                this,
                2,
                L"Failed to get function pointer from MDMRegistration.dll. Error: 0x%08x",
                v15);
              goto LABEL_123;
            }
            v33 = ((__int64 (__fastcall *)(DWORD *, _QWORD, _QWORD))ProcAddress)(cchName, 0, 0);
            v15 = v33;
            if ( v33 < 0 )
            {
              SrSettings::CSrSettings::Trace(
                this,
                2,
                L"Failed to detect MDM managed status online. Error: 0x%08x",
                (unsigned int)v33);
LABEL_123:
              FreeLibrary(v31);
              goto LABEL_124;
            }
            v29 = cchName[0] != 0;
            v71 = cchName[0] != 0;
          }
          else
          {
            SrSettings::CSrSettings::Trace(this, 0, L"Detecting MDM managed status offline.");
            v36 = RegOpenKeyExW(v28, L"Microsoft\\Provisioning\\OMADM\\Accounts", 0, 0x20019u, &v76);
            v15 = v36;
            if ( v36 )
            {
              if ( v36 > 0 )
                v15 = (unsigned __int16)v36 | 0x80070000;
              SrSettings::CSrSettings::Trace(
                this,
                2,
                L"Failed to open HKLM\\Software\\Microsoft\\Provisioning\\OMADM\\Accounts. Error: 0x%08x",
                v15);
              goto LABEL_124;
            }
            v37 = RegOpenKeyExW(v28, L"Microsoft\\Enrollments", 0, 0x20019u, &v80);
            v15 = v37;
            if ( v37 )
            {
              if ( v37 > 0 )
                v15 = (unsigned __int16)v37 | 0x80070000;
              SrSettings::CSrSettings::Trace(
                this,
                2,
                L"Failed to open HKLM\\Software\\Microsoft\\Enrollments. Error: 0x%08x",
                v15);
              goto LABEL_124;
            }
            v31 = 0;
            v15 = 0;
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
                  v39 = 8289;
                  if ( _bittest(&v39, *(unsigned int *)Data) )
                  {
                    SrSettings::CSrSettings::Trace(this, 0, L"Found MDM enrollment type: %d");
                    v29 = 1;
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
          v40 = L"true";
          if ( !v29 )
            v40 = L"false";
          SrSettings::CSrSettings::Trace(this, 0, L"MDM managed status: %s", v40);
          if ( v31 )
            goto LABEL_123;
LABEL_124:
          if ( v76 )
            RegCloseKey(v76);
          if ( v80 )
            RegCloseKey(v80);
          if ( (v15 & 0x80000000) == 0 )
          {
LABEL_132:
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
            v41 = 0;
            v76 = 0;
            memset(&lpValueName, 0, sizeof(lpValueName));
            *(_DWORD *)Data = 0;
            v42 = LoadLibraryW(L"dsreg.dll");
            *(_QWORD *)cchName = v42;
            if ( !v42 )
            {
              v58 = GetLastError();
              v3 = v58;
              if ( v58 > 0 )
                v3 = (unsigned __int16)v58 | 0x80070000;
              SrSettings::CSrSettings::Trace(
                this,
                1,
                L"Failed to load dsreg.dll for Entra joined detection. Error: 0x%08x",
                v3);
              goto LABEL_174;
            }
            SrSettings::CSrSettings::Trace(this, 0, L"Detecting Entra joined status.");
            v43 = GetProcAddress(v42, "DsrIsDeviceJoined");
            if ( !v43 )
            {
              v57 = GetLastError();
              v3 = v57;
              if ( v57 > 0 )
                v3 = (unsigned __int16)v57 | 0x80070000;
              SrSettings::CSrSettings::Trace(this, 1, L"Failed to load function from dsreg.dll. Error: 0x%08x", v3);
              goto LABEL_170;
            }
            v44 = ((__int64 (__fastcall *)(BYTE *, _QWORD))v43)(Data, 0);
            v3 = v44;
            if ( v44 < 0 )
            {
              SrSettings::CSrSettings::Trace(
                this,
                1,
                L"Failed to call DsrIsDeviceJoined. Error: 0x%08x",
                (unsigned int)v44);
LABEL_170:
              FreeLibrary(*(HMODULE *)cchName);
LABEL_174:
              if ( v75 )
                LsaFreeMemory(v75);
              if ( v41 && *(_QWORD *)cbData )
              {
                v41();
                *(_QWORD *)cbData = 0;
              }
              if ( v80 )
                LsaClose(v80);
              if ( v2 )
                FreeLibrary(v2);
              if ( (v3 & 0x80000000) == 0 )
              {
                v59 = v73;
              }
              else
              {
                SrSettings::CSrSettings::Trace(this, 2, L"Failed to detect domain join status. Error: 0x%08x", v3);
                v3 = 0;
                v59 = 0;
              }
              SrSettings::CSrSettings::Trace(this, 0, L"Detected device management statuses:");
              v60 = L"Yes";
              v61 = L"Yes";
              if ( !v68 )
                v61 = L"No";
              SrSettings::CSrSettings::Trace(this, 0, L"  Windows Update Policy: %s", v61);
              v62 = L"Yes";
              if ( !v59 )
                v62 = L"No";
              SrSettings::CSrSettings::Trace(this, 0, L"  Domain Joined: %s", v62);
              if ( !v71 )
                v60 = L"No";
              SrSettings::CSrSettings::Trace(this, 0, L"  MDM Enrolled: %s", v60);
              if ( !v68 && !v59 && !v71 )
              {
                SrSettings::CSrSettings::Trace(this, 0, L"Device is unmanaged, setting QuickScan to On");
                SrSettings::CSrSettings::AddDefaultValue(this, L"CloudRemediation", L"On");
                SrSettings::CSrSettings::AddDefaultValue(this, L"AutoRemediation", L"On");
              }
              String = v82;
              goto LABEL_198;
            }
            v45 = *(_DWORD *)Data == 1;
            v74 = *(_DWORD *)Data == 1;
            v46 = L"true";
            if ( *(_DWORD *)Data != 1 )
              v46 = L"false";
            SrSettings::CSrSettings::Trace(this, 0, L"Entra joined status: %s", v46);
            if ( *((_BYTE *)this + 3946) )
            {
              SrSettings::CSrSettings::Trace(this, 0, L"Detecting AD join status for online OS.");
              v47 = LsaOpenPolicy(0, &lpValueName, 0x2000000u, (PLSA_HANDLE)&v80);
              v48 = v47;
              if ( v47 < 0 )
              {
                SrSettings::CSrSettings::Trace(this, 2, L"Failed to open LSA policy. Status: 0x%08x", (unsigned int)v47);
LABEL_153:
                SrSettings::CSrSettings::Trace(
                  this,
                  2,
                  L"Failed to query promary domain info from LSA policy. Status: 0x%08x",
                  v48);
                v3 = v48 | 0x10000000;
LABEL_166:
                v41 = (void (*)(void))v76;
                goto LABEL_170;
              }
              InformationPolicy = LsaQueryInformationPolicy(v80, PolicyPrimaryDomainInformation, (PVOID *)&v75);
            }
            else
            {
              SrSettings::CSrSettings::Trace(this, 0, L"Detecting AD join status for offline OS.");
              Library = LoadLibraryExW(L"offlinelsa.dll", 0, 0);
              v2 = Library;
              if ( !Library )
                goto LABEL_157;
              v51 = GetProcAddress(Library, "LsaOfflineOpenPolicy");
              v52 = GetProcAddress(v2, "LsaOfflineQueryInformationPolicy");
              v76 = (HKEY)GetProcAddress(v2, "LsaOfflineClose");
              if ( !v51 || !v52 )
              {
                v54 = GetLastError();
                v3 = v54;
                if ( v54 > 0 )
                  v3 = (unsigned __int16)v54 | 0x80070000;
                SrSettings::CSrSettings::Trace(
                  this,
                  2,
                  L"Failed to get function pointers from offlinelsa.dll. Error: 0x%08x",
                  v3);
                goto LABEL_166;
              }
              v53 = ((__int64 (__fastcall *)(_QWORD, DWORD *))v51)(*((_QWORD *)this + 1), cbData);
              v48 = v53;
              if ( v53 < 0 )
              {
                SrSettings::CSrSettings::Trace(
                  this,
                  2,
                  L"Failed to open LSA policy handle offline. Status: 0x%08x",
                  (unsigned int)v53);
                goto LABEL_153;
              }
              InformationPolicy = ((__int64 (__fastcall *)(_QWORD, __int64, HKEY *))v52)(*(_QWORD *)cbData, 3, &v75);
              v45 = v74;
            }
            v48 = InformationPolicy;
            if ( InformationPolicy < 0 )
              goto LABEL_153;
LABEL_157:
            v55 = v75 && *((_QWORD *)v75 + 2);
            v56 = L"true";
            if ( !v55 )
              v56 = L"false";
            SrSettings::CSrSettings::Trace(this, 0, L"AD joined status: %s", v56);
            LODWORD(phkResult) = v55;
            SrSettings::CSrSettings::Trace(
              this,
              0,
              L"Detecting domain join status. Entra joined: %d, AD joined: %d",
              v45,
              phkResult);
            if ( v45 || (v73 = 0, v55) )
              v73 = 1;
            goto LABEL_166;
          }
LABEL_131:
          SrSettings::CSrSettings::Trace(this, 2, L"Failed to detect MDM enrollment status. Error: 0x%08x", v15);
          v71 = 0;
          goto LABEL_132;
        }
        if ( *((_BYTE *)this + 3946) )
        {
          SrSettings::CSrSettings::Trace(this, 0, L"Detecting WU policy for online OS");
          v16 = CoInitializeEx(0, 0);
          v17 = v16;
          if ( v16 <= 1 )
          {
            v18 = 1;
          }
          else
          {
            v18 = 0;
            if ( v16 == -2147417850 )
            {
              v17 = 0;
              SrSettings::CSrSettings::Trace(this, 0, L"COM is already initialized in apartment-threaded mode");
            }
            else
            {
              SrSettings::CSrSettings::Trace(this, 1, L"Failed to initialize COM. Err = 0x%08x", v16);
              v17 = 0;
            }
          }
          v68 = IsEnterprisePolicyConfigured();
          v19 = L"true";
          if ( !v68 )
            v19 = L"false";
          SrSettings::CSrSettings::Trace(this, 0, L"WU policy: %s", v19);
          v2 = 0;
          if ( v18 )
            CoUninitialize();
        }
        else
        {
          v17 = 0;
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
          v20 = RegOpenKeyExW(v14, L"Microsoft\\Windows\\WindowsUpdate", 0, 0x20019u, &v76);
          if ( v20 )
          {
            if ( v20 - 2 <= 1 )
              SrSettings::CSrSettings::Trace(this, 0, L"WindowsUpdate key not found.", v20);
            else
              SrSettings::CSrSettings::Trace(
                this,
                0,
                L"Failed to open HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate. Error: 0x%08x",
                v20);
          }
          else
          {
            v21 = 0;
            while ( 1 )
            {
              v22 = (const WCHAR *)*((_QWORD *)&lpValueName.Length + v21);
              Value = RegQueryValueExW(v76, v22, 0, 0, 0, 0);
              if ( !Value )
                break;
              if ( Value != 2 )
              {
                LODWORD(phkResulta) = Value;
                SrSettings::CSrSettings::Trace(
                  this,
                  0,
                  L"Failed to find registry key: [%s] under HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate. Error: 0x%08x",
                  v22,
                  phkResulta);
              }
              if ( (unsigned int)++v21 >= 4 )
                goto LABEL_63;
            }
            SrSettings::CSrSettings::Trace(
              this,
              0,
              L"Found registry key: [%s] under HKLM\\Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
              v22);
            v69 = 1;
LABEL_63:
            RegCloseKey(v76);
          }
          v75 = 0;
          v24 = RegOpenKeyExW(v14, L"Microsoft\\PolicyManager\\current\\device\\Update", 0, 0x20019u, &v75);
          if ( v24 )
          {
            if ( v24 - 2 <= 1 )
              SrSettings::CSrSettings::Trace(this, 0, L"Update key not found.", v24);
            else
              SrSettings::CSrSettings::Trace(
                this,
                0,
                L"Failed to open HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Update. Error: 0x%08x",
                v24);
          }
          else
          {
            v25 = 0;
            while ( 1 )
            {
              v26 = v86[v25];
              v27 = RegQueryValueExW(v75, v26, 0, 0, 0, 0);
              if ( !v27 )
                break;
              if ( v27 != 2 )
              {
                LODWORD(phkResultb) = v27;
                SrSettings::CSrSettings::Trace(
                  this,
                  0,
                  L"Failed to find registry key: [%s] under HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Upd"
                   "ate. Error: 0x%08x",
                  v26,
                  phkResultb);
              }
              if ( (unsigned int)++v25 >= 7 )
                goto LABEL_75;
            }
            SrSettings::CSrSettings::Trace(
              this,
              0,
              L"Found registry key: [%s] under HKLM\\Software\\Microsoft\\PolicyManager\\current\\device\\Update",
              v26);
            v70 = 1;
LABEL_75:
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
              goto LABEL_84;
            }
          }
          v68 = 1;
        }
LABEL_84:
        if ( v17 >= 0 )
          goto LABEL_88;
        goto LABEL_87;
      }
      SrSettings::CSrSettings::Trace(this, 0, L"Device is managed by Autopatch policy, skip the detection");
    }
LABEL_198:
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, String);
    goto LABEL_199;
  }
  if ( v5 > 0 )
    v3 = (unsigned __int16)v5 | 0x80070000;
  v6 = L"Failed to open Software hive. Error: 0x%08x";
LABEL_10:
  SrSettings::CSrSettings::Trace(this, 2, v6, v3);
LABEL_199:
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v72 )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"$OSHive$Software");
LABEL_203:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(lpFile);
  return v3;
}

```

## disassembly

```asm
0x18004afc8  push    rbp
0x18004afca  push    rbx
0x18004afcb  push    rsi
0x18004afcc  push    rdi
0x18004afcd  push    r12
0x18004afcf  push    r13
0x18004afd1  push    r14
0x18004afd3  push    r15
0x18004afd5  lea     rbp, [rsp-238h]
0x18004afdd  sub     rsp, 338h
0x18004afe4  mov     [rbp+270h+var_260], 0FFFFFFFFFFFFFFFEh
0x18004afec  mov     rax, cs:__security_cookie
0x18004aff3  xor     rax, rsp
0x18004aff6  mov     [rbp+270h+var_50], rax
0x18004affd  mov     rsi, rcx
0x18004b000  xor     r12d, r12d
0x18004b003  mov     [rsp+370h+hKey], r12
0x18004b008  lea     rax, [rbp+270h+var_2D8]
0x18004b00c  mov     [rbp+270h+lpFile], rax
0x18004b010  lea     rax, [rbp+270h+var_2D8]
0x18004b014  mov     [rbp+270h+var_2E0], rax
0x18004b018  mov     [rbp+270h+var_2D8], r12w
0x18004b01d  cmp     [rcx+0F69h], r12b
0x18004b024  jnz     short loc_18004B041
0x18004b026  lea     r8, aCsrsettingsNot; "CSrSettings not initialized"
0x18004b02d  lea     edx, [r12+2]
0x18004b032  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b037  mov     edi, 80070015h
0x18004b03c  jmp     loc_18004BF64
0x18004b041  mov     [rsp+370h+var_32E], r12b
0x18004b046  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::GetImpl(void)'::`2'::impl
0x18004b04d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMR_UX_Update@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMR_UX_Update>::__private_IsEnabled(void)
0x18004b052  lea     rcx, a30; "30"
0x18004b059  lea     rbx, a0; "0"
0x18004b060  test    al, al
0x18004b062  cmovz   rbx, rcx
0x18004b066  lea     rcx, [rsi+0A8h]
0x18004b06d  call    ?clear@?$_Tree@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@2@U?$less@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V12@@utl@@@2@$0A@@utl@@QEAAXXZ; utl::_Tree<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::less<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>,utl::allocator<utl::pair<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>,0>::clear(void)
0x18004b072  lea     r14, aOff; "Off"
0x18004b079  mov     r8, r14; unsigned __int16 *
0x18004b07c  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x18004b083  mov     rcx, rsi; this
0x18004b086  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b08b  mov     r8, r14; unsigned __int16 *
0x18004b08e  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18004b095  mov     rcx, rsi; this
0x18004b098  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b09d  mov     r8, r14; unsigned __int16 *
0x18004b0a0  lea     rdx, aHeadlessmode; "HeadlessMode"
0x18004b0a7  mov     rcx, rsi; this
0x18004b0aa  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b0af  lea     r8, a180; "180"
0x18004b0b6  lea     rdx, aTotalwaittime_0; "TotalWaitTime"
0x18004b0bd  mov     rcx, rsi; this
0x18004b0c0  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b0c5  mov     r8, rbx; unsigned __int16 *
0x18004b0c8  lea     rdx, aWaitinterval; "WaitInterval"
0x18004b0cf  mov     rcx, rsi; this
0x18004b0d2  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b0d7  mov     rbx, 0FFFFFFFF80000002h
0x18004b0de  cmp     [rsi+0F6Ah], r12b
0x18004b0e5  jz      short loc_18004B13B
0x18004b0e7  lea     rax, [rsp+370h+hKey]
0x18004b0ec  mov     [rsp+370h+phkResult], rax; phkResult
0x18004b0f1  mov     r9d, 20019h; samDesired
0x18004b0f7  xor     r8d, r8d; ulOptions
0x18004b0fa  lea     rdx, aSoftware_1; "Software"
0x18004b101  mov     rcx, rbx; hKey
0x18004b104  call    cs:__imp_RegOpenKeyExW
0x18004b10a  mov     edi, eax
0x18004b10c  test    eax, eax
0x18004b10e  jz      loc_18004B223
0x18004b114  jle     short loc_18004B11F
0x18004b116  movzx   edi, ax
0x18004b119  or      edi, 80070000h
0x18004b11f  lea     r8, aFailedToOpenSo; "Failed to open Software hive. Error: 0x"...
0x18004b126  mov     r9d, edi
0x18004b129  mov     edx, 2
0x18004b12e  mov     rcx, rsi
0x18004b131  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b136  jmp     loc_18004BF37
0x18004b13b  mov     rdx, [rsi+8]
0x18004b13f  mov     r8, [rsi+10h]
0x18004b143  sub     r8, rdx
0x18004b146  sar     r8, 1
0x18004b149  lea     rcx, [rbp+270h+lpFile]
0x18004b14d  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18004b152  test    al, al
0x18004b154  jnz     short loc_18004B168
0x18004b156  mov     r9d, 80070008h
0x18004b15c  mov     edi, r9d
0x18004b15f  lea     r8, aFailedToAssign_11; "Failed to assign target OS path to soft"...
0x18004b166  jmp     short loc_18004B129
0x18004b168  mov     r8d, 19h
0x18004b16e  lea     rdx, aSystem32Config_1; "\\System32\\config\\SOFTWARE"
0x18004b175  lea     rcx, [rbp+270h+lpFile]
0x18004b179  call    ?append@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::append(ushort const *,unsigned __int64)
0x18004b17e  test    al, al
0x18004b180  jnz     short loc_18004B194
0x18004b182  mov     r9d, 80070008h
0x18004b188  mov     edi, r9d
0x18004b18b  lea     r8, aFailedToAppend_6; "Failed to append SOFTWARE to software h"...
0x18004b192  jmp     short loc_18004B129
0x18004b194  mov     r8, [rbp+270h+lpFile]; lpFile
0x18004b198  lea     rdx, aOshiveSoftware; "$OSHive$Software"
0x18004b19f  mov     rcx, rbx; hKey
0x18004b1a2  call    cs:__imp_RegLoadKeyW
0x18004b1a8  mov     edi, eax
0x18004b1aa  test    eax, eax
0x18004b1ac  jz      short loc_18004B1DA
0x18004b1ae  jle     short loc_18004B1B9
0x18004b1b0  movzx   edi, ax
0x18004b1b3  or      edi, 80070000h
0x18004b1b9  mov     r9, [rsi+8]
0x18004b1bd  lea     r8, aFailedToLoadSo; "Failed to load software hive from %s. E"...
0x18004b1c4  mov     dword ptr [rsp+370h+phkResult], edi
0x18004b1c8  mov     edx, 2
0x18004b1cd  mov     rcx, rsi
0x18004b1d0  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b1d5  jmp     loc_18004BF37
0x18004b1da  mov     [rsp+370h+var_32E], 1
0x18004b1df  lea     rax, [rsp+370h+hKey]
0x18004b1e4  mov     [rsp+370h+phkResult], rax; phkResult
0x18004b1e9  mov     r9d, 20019h; samDesired
0x18004b1ef  xor     r8d, r8d; ulOptions
0x18004b1f2  lea     rdx, aOshiveSoftware; "$OSHive$Software"
0x18004b1f9  mov     rcx, rbx; hKey
0x18004b1fc  call    cs:__imp_RegOpenKeyExW
0x18004b202  mov     edi, eax
0x18004b204  test    eax, eax
0x18004b206  jz      short loc_18004B223
0x18004b208  jle     short loc_18004B213
0x18004b20a  movzx   edi, ax
0x18004b20d  or      edi, 80070000h
0x18004b213  lea     r9, aOshiveSoftware; "$OSHive$Software"
0x18004b21a  lea     r8, aFailedToOpenLo; "Failed to open loaded %s key. Error: 0x"...
0x18004b221  jmp     short loc_18004B1C4
0x18004b223  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer> `wil::Feature<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::GetImpl(void)'::`2'::impl
0x18004b22a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_EnableSrtOnServer>::__private_IsEnabled(void)
0x18004b22f  test    al, al
0x18004b231  jz      short loc_18004B260
0x18004b233  cmp     [rsi+0CD4h], r12d
0x18004b23a  jz      short loc_18004B260
0x18004b23c  mov     r8, r14; unsigned __int16 *
0x18004b23f  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x18004b246  mov     rcx, rsi; this
0x18004b249  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b24e  mov     r8, r14; unsigned __int16 *
0x18004b251  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18004b258  mov     rcx, rsi; this
0x18004b25b  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b260  mov     rcx, [rsp+370h+hKey]
0x18004b265  call    RegGetStringEx
0x18004b26a  mov     r14, rax
0x18004b26d  mov     [rbp+270h+var_2F0], rax
0x18004b271  test    rax, rax
0x18004b274  jnz     short loc_18004B297
0x18004b276  call    cs:__imp_GetLastError
0x18004b27c  mov     edi, eax
0x18004b27e  test    eax, eax
0x18004b280  jle     short loc_18004B28B
0x18004b282  movzx   edi, ax
0x18004b285  or      edi, 80070000h
0x18004b28b  lea     r8, aFailedToGetEdi; "Failed to get Edition ID from registry."...
0x18004b292  jmp     loc_18004B126
0x18004b297  mov     edi, r12d
0x18004b29a  mov     bl, r12b
0x18004b29d  lea     r15, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices> `wil::Feature<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::GetImpl(void)'::`2'::impl
0x18004b2a4  mov     rcx, r15
0x18004b2a7  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18004b2ac  test    al, al
0x18004b2ae  jz      short loc_18004B2C4
0x18004b2b0  mov     r9, r14
0x18004b2b3  lea     r8, aEditionIdS; "Edition ID: %s"
0x18004b2ba  xor     edx, edx
0x18004b2bc  mov     rcx, rsi
0x18004b2bf  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b2c4  lea     rdx, aCore; "Core"
0x18004b2cb  mov     rcx, r14; String1
0x18004b2ce  call    cs:__imp__wcsicmp
0x18004b2d4  lea     r13, aOn; "On"
0x18004b2db  test    eax, eax
0x18004b2dd  jz      loc_18004B385
0x18004b2e3  lea     rdx, aCoren; "CoreN"
0x18004b2ea  mov     rcx, r14; String1
0x18004b2ed  call    cs:__imp__wcsicmp
0x18004b2f3  test    eax, eax
0x18004b2f5  jz      loc_18004B385
0x18004b2fb  lea     rdx, aCorecountryspe; "CoreCountrySpecific"
0x18004b302  mov     rcx, r14; String1
0x18004b305  call    cs:__imp__wcsicmp
0x18004b30b  test    eax, eax
0x18004b30d  jz      short loc_18004B385
0x18004b30f  lea     rdx, aCoresinglelang; "CoreSingleLanguage"
0x18004b316  mov     rcx, r14; String1
0x18004b319  call    cs:__imp__wcsicmp
0x18004b31f  test    eax, eax
0x18004b321  jz      short loc_18004B385
0x18004b323  lea     r8, aQuickmachinere; "QuickMachineRecoveryEnrolled"
0x18004b32a  lea     rdx, aMicrosoftPolic_0; "Microsoft\\PolicyManager\\current\\devi"...
0x18004b331  mov     rcx, [rsp+370h+hKey]
0x18004b336  call    RegGetDword
0x18004b33b  cmp     eax, 1
0x18004b33e  jnz     short loc_18004B3BA
0x18004b340  lea     r8, aEnableCloudrem; "Enable CloudRemediation and AutoRemedia"...
0x18004b347  xor     edx, edx
0x18004b349  mov     rcx, rsi
0x18004b34c  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b351  mov     r8, r13; unsigned __int16 *
0x18004b354  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x18004b35b  mov     rcx, rsi; this
0x18004b35e  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b363  mov     r8, r13; unsigned __int16 *
0x18004b366  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18004b36d  mov     rcx, rsi; this
0x18004b370  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b375  mov     rcx, r15
0x18004b378  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18004b37d  test    al, al
0x18004b37f  jz      short loc_18004B3BA
0x18004b381  mov     bl, 1
0x18004b383  jmp     short loc_18004B3BA
0x18004b385  lea     r8, aEnableCloudrem_0; "Enable CloudRemediation and AutoRemedia"...
0x18004b38c  xor     edx, edx
0x18004b38e  mov     rcx, rsi
0x18004b391  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b396  mov     r8, r13; unsigned __int16 *
0x18004b399  lea     rdx, aCloudremediati_0; "CloudRemediation"
0x18004b3a0  mov     rcx, rsi; this
0x18004b3a3  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b3a8  mov     r8, r13; unsigned __int16 *
0x18004b3ab  lea     rdx, aAutoremediatio; "AutoRemediation"
0x18004b3b2  mov     rcx, rsi; this
0x18004b3b5  call    ?AddDefaultValue@CSrSettings@SrSettings@@AEAAJPEBG0@Z; SrSettings::CSrSettings::AddDefaultValue(ushort const *,ushort const *)
0x18004b3ba  mov     rcx, r15
0x18004b3bd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRDefaultValueForUnmanagedDevices>::__private_IsEnabled(void)
0x18004b3c2  test    al, al
0x18004b3c4  jz      loc_18004BF1C
0x18004b3ca  lea     rdx, aProfessional; "Professional"
0x18004b3d1  mov     rcx, r14; String1
0x18004b3d4  call    cs:__imp__wcsicmp
0x18004b3da  test    eax, eax
0x18004b3dc  jnz     loc_18004BF1C
0x18004b3e2  lea     r8, aProDeviceDetec; "Pro device, detecting whether the devic"...
0x18004b3e9  xor     edx, edx
0x18004b3eb  mov     rcx, rsi
0x18004b3ee  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b3f3  mov     rcx, rsi
0x18004b3f6  test    bl, bl
0x18004b3f8  jnz     loc_18004BF05
0x18004b3fe  mov     [rsp+370h+var_32D], r12b
0x18004b403  mov     r13, [rsp+370h+hKey]
0x18004b408  mov     ebx, 80070057h
0x18004b40d  mov     r14d, 2
0x18004b413  test    r13, r13
0x18004b416  jz      loc_18004B747
0x18004b41c  xor     edx, edx
0x18004b41e  cmp     [rsi+0F6Ah], r12b
0x18004b425  jz      loc_18004B4C9
0x18004b42b  lea     r8, aDetectingWuPol_0; "Detecting WU policy for online OS"
0x18004b432  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b437  xor     edx, edx; dwCoInit
0x18004b439  xor     ecx, ecx; pvReserved
0x18004b43b  call    cs:__imp_CoInitializeEx
0x18004b441  mov     edi, eax
0x18004b443  cmp     eax, 1
0x18004b446  jbe     short loc_18004B481
0x18004b448  mov     r15b, r12b
0x18004b44b  mov     rcx, rsi
0x18004b44e  cmp     eax, 80010106h
0x18004b453  jnz     short loc_18004B468
0x18004b455  mov     edi, r12d
0x18004b458  lea     r8, aComIsAlreadyIn; "COM is already initialized in apartment"...
0x18004b45f  xor     edx, edx
0x18004b461  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b466  jmp     short loc_18004B484
0x18004b468  mov     r9d, eax
0x18004b46b  lea     r8, aFailedToInitia_4; "Failed to initialize COM. Err = 0x%08x"
0x18004b472  mov     edx, 1
0x18004b477  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b47c  mov     edi, r12d
0x18004b47f  jmp     short loc_18004B484
0x18004b481  mov     r15b, 1
0x18004b484  call    IsEnterprisePolicyConfigured
0x18004b489  mov     [rsp+370h+var_330], al
0x18004b48d  lea     r9, aTrue; "true"
0x18004b494  test    al, al
0x18004b496  lea     rcx, aFalse; "false"
0x18004b49d  cmovz   r9, rcx
0x18004b4a1  lea     r8, aWuPolicyS; "WU policy: %s"
0x18004b4a8  xor     edx, edx
0x18004b4aa  mov     rcx, rsi
0x18004b4ad  call    ?Trace@CSrSettings@SrSettings@@AEAAXW4SRT_LOG_SEVERITY@SrtUtil@@PEBGZZ; SrSettings::CSrSettings::Trace(SrtUtil::SRT_LOG_SEVERITY,ushort const *,...)
0x18004b4b2  xor     r12d, r12d
0x18004b4b5  test    r15b, r15b
0x18004b4b8  jz      loc_18004B741
0x18004b4be  call    cs:__imp_CoUninitialize
0x18004b4c4  jmp     loc_18004B741
0x18004b4c9  mov     edi, r12d
0x18004b4cc  lea     r8, aDetectingWuPol; "Detecting WU policy for offline OS"
  ... truncated ...
```
