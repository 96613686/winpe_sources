# CSetupOneSetting::InitializeAndQuery(ushort const *,ushort const *)

- ea: `0x1804acad4`
- end: `0x1804adf3c`
- name: `?InitializeAndQuery@CSetupOneSetting@@QEAAJPEBG0@Z`
- size: `5224`
- prototype: `__int64 __fastcall(CSetupOneSetting *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1804aba5c`

## callees

- `0x180013810`
- `0x180057dec`
- `0x18009a39c`
- `0x1804050d4`
- `0x180406414`
- `0x18040c590`
- `0x1804aacec`
- `0x1804ab074`
- `0x1804ab2b4`
- `0x1804acad4`
- `0x1804ae16c`
- `0x1804af0d8`
- `0x1804b1060`
- `0x1804b2094`
- `0x1804bbf62`
- `0x1804bbfa0`
- `0x180509010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1804aceb8`
- `ADVAPI32!RegCloseKey` at `0x1804ad3dc`
- `ADVAPI32!RegCloseKey` at `0x1804ad5bc`
- `ADVAPI32!RegCloseKey` at `0x1804ad9d8`
- `ADVAPI32!RegCloseKey` at `0x1804adb10`
- `ADVAPI32!RegCloseKey` at `0x1804aceb8`
- `ADVAPI32!RegCloseKey` at `0x1804ad3dc`
- `ADVAPI32!RegCloseKey` at `0x1804ad5bc`
- `ADVAPI32!RegCloseKey` at `0x1804ad9d8`
- `ADVAPI32!RegCloseKey` at `0x1804adb10`
- `ADVAPI32!RegOpenKeyExW` at `0x1804acdc9`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad2e8`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad4d4`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad8f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1804adad2`
- `ADVAPI32!RegOpenKeyExW` at `0x1804acdc9`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad2e8`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad4d4`
- `ADVAPI32!RegOpenKeyExW` at `0x1804ad8f0`
- `ADVAPI32!RegOpenKeyExW` at `0x1804adad2`
- `ADVAPI32!RegQueryValueExW` at `0x1804ace09`
- `ADVAPI32!RegQueryValueExW` at `0x1804ace76`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad328`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad397`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad510`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad57b`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad92c`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad997`
- `ADVAPI32!RegQueryValueExW` at `0x1804adb04`
- `ADVAPI32!RegQueryValueExW` at `0x1804ace09`
- `ADVAPI32!RegQueryValueExW` at `0x1804ace76`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad328`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad397`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad510`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad57b`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad92c`
- `ADVAPI32!RegQueryValueExW` at `0x1804ad997`
- `ADVAPI32!RegQueryValueExW` at `0x1804adb04`
- `KERNEL32!VerSetConditionMask` at `0x1804acb67`
- `KERNEL32!VerSetConditionMask` at `0x1804acb7a`
- `KERNEL32!VerSetConditionMask` at `0x1804acb89`
- `KERNEL32!VerSetConditionMask` at `0x1804acb67`
- `KERNEL32!VerSetConditionMask` at `0x1804acb7a`
- `KERNEL32!VerSetConditionMask` at `0x1804acb89`
- `KERNEL32!GetProcessHeap` at `0x1804ace2f`
- `KERNEL32!GetProcessHeap` at `0x1804ace8f`
- `KERNEL32!GetProcessHeap` at `0x1804ad196`
- `KERNEL32!GetProcessHeap` at `0x1804ad1b3`
- `KERNEL32!GetProcessHeap` at `0x1804ad351`
- `KERNEL32!GetProcessHeap` at `0x1804ad3b3`
- `KERNEL32!GetProcessHeap` at `0x1804ad539`
- `KERNEL32!GetProcessHeap` at `0x1804ad597`
- `KERNEL32!GetProcessHeap` at `0x1804ad955`
- `KERNEL32!GetProcessHeap` at `0x1804ad9b3`
- `KERNEL32!GetProcessHeap` at `0x1804adcfc`
- `KERNEL32!GetProcessHeap` at `0x1804add21`
- `KERNEL32!GetProcessHeap` at `0x1804ade56`
- `KERNEL32!GetProcessHeap` at `0x1804adf23`
- `KERNEL32!GetProcessHeap` at `0x1804ace2f`
- `KERNEL32!GetProcessHeap` at `0x1804ace8f`
- `KERNEL32!GetProcessHeap` at `0x1804ad196`
- `KERNEL32!GetProcessHeap` at `0x1804ad1b3`
- `KERNEL32!GetProcessHeap` at `0x1804ad351`
- `KERNEL32!GetProcessHeap` at `0x1804ad3b3`
- `KERNEL32!GetProcessHeap` at `0x1804ad539`
- `KERNEL32!GetProcessHeap` at `0x1804ad597`
- `KERNEL32!GetProcessHeap` at `0x1804ad955`
- `KERNEL32!GetProcessHeap` at `0x1804ad9b3`
- `KERNEL32!GetProcessHeap` at `0x1804adcfc`
- `KERNEL32!GetProcessHeap` at `0x1804add21`
- `KERNEL32!GetProcessHeap` at `0x1804ade56`
- `KERNEL32!GetProcessHeap` at `0x1804adf23`
- `KERNEL32!HeapAlloc` at `0x1804ace40`
- `KERNEL32!HeapAlloc` at `0x1804ad362`
- `KERNEL32!HeapAlloc` at `0x1804ad54a`
- `KERNEL32!HeapAlloc` at `0x1804ad966`
- `KERNEL32!HeapAlloc` at `0x1804ace40`
- `KERNEL32!HeapAlloc` at `0x1804ad362`
- `KERNEL32!HeapAlloc` at `0x1804ad54a`
- `KERNEL32!HeapAlloc` at `0x1804ad966`
- `KERNEL32!HeapFree` at `0x1804ace9d`
- `KERNEL32!HeapFree` at `0x1804ad1a4`
- `KERNEL32!HeapFree` at `0x1804ad1c1`
- `KERNEL32!HeapFree` at `0x1804ad3c1`
- `KERNEL32!HeapFree` at `0x1804ad5a5`
- `KERNEL32!HeapFree` at `0x1804ad9c1`
- `KERNEL32!HeapFree` at `0x1804add0a`
- `KERNEL32!HeapFree` at `0x1804add2f`
- `KERNEL32!HeapFree` at `0x1804ade64`
- `KERNEL32!HeapFree` at `0x1804adf31`
- `KERNEL32!HeapFree` at `0x1804ace9d`
- `KERNEL32!HeapFree` at `0x1804ad1a4`
- `KERNEL32!HeapFree` at `0x1804ad1c1`
- `KERNEL32!HeapFree` at `0x1804ad3c1`
- `KERNEL32!HeapFree` at `0x1804ad5a5`
- `KERNEL32!HeapFree` at `0x1804ad9c1`
- `KERNEL32!HeapFree` at `0x1804add0a`
- `KERNEL32!HeapFree` at `0x1804add2f`
- `KERNEL32!HeapFree` at `0x1804ade64`
- `KERNEL32!HeapFree` at `0x1804adf31`
- `KERNEL32!GetLastError` at `0x1804acc1f`
- `KERNEL32!GetLastError` at `0x1804accb9`
- `KERNEL32!GetLastError` at `0x1804acd25`
- `KERNEL32!GetLastError` at `0x1804aceac`
- `KERNEL32!GetLastError` at `0x1804acf0e`
- `KERNEL32!GetLastError` at `0x1804acf90`
- `KERNEL32!GetLastError` at `0x1804acfa8`
- `KERNEL32!GetLastError` at `0x1804acfc0`
- `KERNEL32!GetLastError` at `0x1804ad05d`
- `KERNEL32!GetLastError` at `0x1804ad11d`
- `KERNEL32!GetLastError` at `0x1804ad255`
- `KERNEL32!GetLastError` at `0x1804ad3d0`
- `KERNEL32!GetLastError` at `0x1804ad42c`
- `KERNEL32!GetLastError` at `0x1804ad5b0`
- `KERNEL32!GetLastError` at `0x1804ad60e`
- `KERNEL32!GetLastError` at `0x1804ad6a6`
- `KERNEL32!GetLastError` at `0x1804ad6be`
- `KERNEL32!GetLastError` at `0x1804ad6d6`
- `KERNEL32!GetLastError` at `0x1804ad767`
- `KERNEL32!GetLastError` at `0x1804ad77f`
- `KERNEL32!GetLastError` at `0x1804ad797`
- `KERNEL32!GetLastError` at `0x1804ad80f`
- `KERNEL32!GetLastError` at `0x1804ad9cc`
- `KERNEL32!GetLastError` at `0x1804ada29`
- `KERNEL32!GetLastError` at `0x1804adb26`
- `KERNEL32!GetLastError` at `0x1804adbac`
- `KERNEL32!GetLastError` at `0x1804adc38`
- `KERNEL32!GetLastError` at `0x1804adc97`
- `KERNEL32!GetLastError` at `0x1804add3f`
- `KERNEL32!GetLastError` at `0x1804addaf`
- `KERNEL32!GetLastError` at `0x1804addc7`
- `KERNEL32!GetLastError` at `0x1804adddf`
- `KERNEL32!GetLastError` at `0x1804ade7a`
- `KERNEL32!GetLastError` at `0x1804ade92`
- `KERNEL32!GetLastError` at `0x1804adeaa`
- `KERNEL32!GetLastError` at `0x1804acc1f`
- `KERNEL32!GetLastError` at `0x1804accb9`
- `KERNEL32!GetLastError` at `0x1804acd25`
- `KERNEL32!GetLastError` at `0x1804aceac`
- `KERNEL32!GetLastError` at `0x1804acf0e`
- `KERNEL32!GetLastError` at `0x1804acf90`
- `KERNEL32!GetLastError` at `0x1804acfa8`
- `KERNEL32!GetLastError` at `0x1804acfc0`
- `KERNEL32!GetLastError` at `0x1804ad05d`
- `KERNEL32!GetLastError` at `0x1804ad11d`
- `KERNEL32!GetLastError` at `0x1804ad255`
- `KERNEL32!GetLastError` at `0x1804ad3d0`
- `KERNEL32!GetLastError` at `0x1804ad42c`
- `KERNEL32!GetLastError` at `0x1804ad5b0`
- `KERNEL32!GetLastError` at `0x1804ad60e`
- `KERNEL32!GetLastError` at `0x1804ad6a6`
- `KERNEL32!GetLastError` at `0x1804ad6be`
- `KERNEL32!GetLastError` at `0x1804ad6d6`
- `KERNEL32!GetLastError` at `0x1804ad767`
- `KERNEL32!GetLastError` at `0x1804ad77f`
- `KERNEL32!GetLastError` at `0x1804ad797`
- `KERNEL32!GetLastError` at `0x1804ad80f`
- `KERNEL32!GetLastError` at `0x1804ad9cc`
- `KERNEL32!GetLastError` at `0x1804ada29`
- `KERNEL32!GetLastError` at `0x1804adb26`
- `KERNEL32!GetLastError` at `0x1804adbac`
- `KERNEL32!GetLastError` at `0x1804adc38`
- `KERNEL32!GetLastError` at `0x1804adc97`
- `KERNEL32!GetLastError` at `0x1804add3f`
- `KERNEL32!GetLastError` at `0x1804addaf`
- `KERNEL32!GetLastError` at `0x1804addc7`
- `KERNEL32!GetLastError` at `0x1804adddf`
- `KERNEL32!GetLastError` at `0x1804ade7a`
- `KERNEL32!GetLastError` at `0x1804ade92`
- `KERNEL32!GetLastError` at `0x1804adeaa`
- `KERNEL32!GetProcAddress` at `0x1804acbe5`
- `KERNEL32!GetProcAddress` at `0x1804acbe5`
- `KERNEL32!SetLastError` at `0x1804acec0`
- `KERNEL32!SetLastError` at `0x1804acf86`
- `KERNEL32!SetLastError` at `0x1804ad3e4`
- `KERNEL32!SetLastError` at `0x1804ad5c4`
- `KERNEL32!SetLastError` at `0x1804ad9e0`
- `KERNEL32!SetLastError` at `0x1804adaa5`
- `KERNEL32!SetLastError` at `0x1804adb18`
- `KERNEL32!SetLastError` at `0x1804adba6`
- `KERNEL32!SetLastError` at `0x1804adda6`
- `KERNEL32!SetLastError` at `0x1804ade71`
- `KERNEL32!SetLastError` at `0x1804acec0`
- `KERNEL32!SetLastError` at `0x1804acf86`
- `KERNEL32!SetLastError` at `0x1804ad3e4`
- `KERNEL32!SetLastError` at `0x1804ad5c4`
- `KERNEL32!SetLastError` at `0x1804ad9e0`
- `KERNEL32!SetLastError` at `0x1804adaa5`
- `KERNEL32!SetLastError` at `0x1804adb18`
- `KERNEL32!SetLastError` at `0x1804adba6`
- `KERNEL32!SetLastError` at `0x1804adda6`
- `KERNEL32!SetLastError` at `0x1804ade71`
- `KERNEL32!FreeLibrary` at `0x1804acc03`
- `KERNEL32!FreeLibrary` at `0x1804acc03`
- `KERNEL32!LoadLibraryExW` at `0x1804acbcd`
- `KERNEL32!LoadLibraryExW` at `0x1804acbcd`
- `KERNEL32!VerifyVersionInfoW` at `0x1804acba8`
- `KERNEL32!VerifyVersionInfoW` at `0x1804acba8`
- `KERNEL32!GetProductInfo` at `0x1804ad759`
- `KERNEL32!GetProductInfo` at `0x1804ad759`

## string_xrefs

- `0x1804acbbd`: `ntdll.dll`
- `0x1804ad31e`: `InstallationType`
- `0x1804ad377`: `InstallationType`
- `0x1804adb34`: `settings-win-ppe.data.microsoft.com`
- `0x1804adb98`: `settings-win-ppe.data.microsoft.com`
- `0x1804acfd1`: `Onesettings: Failed to get DeviceId from registry: 0x%x`
- `0x1804adbba`: `settings-win.data.microsoft.com`
- `0x1804adc1e`: `settings-win.data.microsoft.com`
- `0x1804adebb`: `Onesettings: Failed to get InstallationType from registry: 0x%x`
- `0x1804ad410`: `platformInstallationType`
- `0x1804ad43d`: `platformInstallationType`
- `0x1804addf0`: `Onesettings: Failed to get EditionId from registry: 0x%x`

## pseudocode

```c
__int64 __fastcall CSetupOneSetting::InitializeAndQuery(
        CSetupOneSetting *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  void *v3; // rdi
  ULONGLONG v5; // rax
  ULONGLONG v6; // rax
  DWORDLONG v7; // rax
  char IsWin10TelemetryTypeAllowed; // bl
  HMODULE Library; // rax
  HMODULE v10; // rdi
  FARPROC ProcAddress; // rax
  signed int AppVersionInfo; // esi
  DWORD LastError; // edi
  __int64 v14; // rbx
  struct tagLOG_PARTIAL_MSG *v15; // rax
  OneCore::Base::Telemetry::OneSettingsQuery *v16; // rax
  const unsigned __int16 *v17; // rdx
  const unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // r9
  OneCore::Base::Telemetry::OneSettingsQuery *v20; // rax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  DWORD v24; // edi
  __int64 v25; // rbx
  struct tagLOG_PARTIAL_MSG *v26; // rax
  __int64 v27; // r14
  LSTATUS v28; // eax
  DWORD v29; // ebx
  DWORD v30; // ebx
  HANDLE ProcessHeap; // rax
  _WORD *v32; // rax
  HANDLE v33; // rax
  __int64 v34; // rax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  void *v38; // rbx
  signed int v39; // eax
  bool v40; // sf
  signed int v41; // eax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  __int64 v48; // rbx
  __int64 v49; // rax
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  void *v53; // rbx
  HANDLE v54; // rax
  HANDLE v55; // rax
  __int64 v57; // rax
  DWORD v58; // edi
  __int64 v59; // rbx
  struct tagLOG_PARTIAL_MSG *v60; // rax
  LSTATUS v61; // eax
  BYTE *v62; // r12
  DWORD v63; // ebx
  DWORD v64; // ebx
  HANDLE v65; // rax
  BYTE *v66; // rax
  HANDLE v67; // rax
  __int64 v68; // rax
  DWORD v69; // edi
  __int64 v70; // rbx
  struct tagLOG_PARTIAL_MSG *v71; // rax
  LSTATUS v72; // eax
  BYTE *v73; // r13
  DWORD v74; // ebx
  DWORD v75; // ebx
  HANDLE v76; // rax
  BYTE *v77; // rax
  HANDLE v78; // rax
  __int64 v79; // rax
  DWORD v80; // edi
  __int64 v81; // rbx
  struct tagLOG_PARTIAL_MSG *v82; // rax
  signed int v83; // eax
  bool v84; // sf
  signed int v85; // eax
  DWORD v86; // edi
  __int64 v87; // rbx
  struct tagLOG_PARTIAL_MSG *v88; // rax
  signed int v89; // eax
  bool v90; // sf
  signed int v91; // eax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  DWORD v95; // edi
  __int64 v96; // rbx
  struct tagLOG_PARTIAL_MSG *v97; // rax
  __int64 v98; // rax
  LSTATUS v99; // eax
  BYTE *v100; // r12
  DWORD v101; // ebx
  DWORD v102; // ebx
  HANDLE v103; // rax
  BYTE *v104; // rax
  HANDLE v105; // rax
  DWORD v106; // edi
  __int64 v107; // rbx
  struct tagLOG_PARTIAL_MSG *v108; // rax
  LSTATUS Value; // ebx
  DWORD v110; // edi
  __int64 v111; // rbx
  struct tagLOG_PARTIAL_MSG *v112; // rax
  bool v113; // r8
  const unsigned __int16 *v114; // r9
  wchar_t *v115; // rdx
  DWORD v116; // edi
  __int64 v117; // rbx
  struct tagLOG_PARTIAL_MSG *v118; // rax
  CSetupOneSetting *v119; // rbx
  DWORD v120; // edi
  __int64 v121; // rbx
  struct tagLOG_PARTIAL_MSG *v122; // rax
  DWORD v123; // edi
  __int64 v124; // rbx
  struct tagLOG_PARTIAL_MSG *v125; // rax
  HANDLE v126; // rax
  unsigned __int16 *v127; // rbx
  HANDLE v128; // rax
  DWORD v129; // edi
  __int64 v130; // rbx
  struct tagLOG_PARTIAL_MSG *v131; // rax
  signed int v132; // eax
  bool v133; // sf
  signed int v134; // eax
  DWORD v135; // edi
  __int64 v136; // rbx
  struct tagLOG_PARTIAL_MSG *v137; // rax
  HANDLE v138; // rax
  signed int v139; // eax
  bool v140; // sf
  signed int v141; // eax
  DWORD v142; // edi
  __int64 v143; // rbx
  struct tagLOG_PARTIAL_MSG *v144; // rax
  HANDLE v145; // rax
  const unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *phkResultb; // [rsp+20h] [rbp-E0h]
  LPDWORD lpcbData; // [rsp+28h] [rbp-D8h]
  DWORD v150; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v151; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD v152; // [rsp+68h] [rbp-98h] BYREF
  DWORD v153; // [rsp+6Ch] [rbp-94h] BYREF
  DWORD cbData; // [rsp+70h] [rbp-90h] BYREF
  DWORD Type; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD v156; // [rsp+78h] [rbp-88h] BYREF
  DWORD v157; // [rsp+7Ch] [rbp-84h] BYREF
  LPVOID v158; // [rsp+80h] [rbp-80h]
  DWORD pdwReturnedProductType; // [rsp+88h] [rbp-78h] BYREF
  BYTE *v160; // [rsp+90h] [rbp-70h]
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  HKEY v162; // [rsp+A0h] [rbp-60h] BYREF
  HKEY v163; // [rsp+A8h] [rbp-58h] BYREF
  HKEY v164; // [rsp+B0h] [rbp-50h] BYREF
  HKEY v165; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v166; // [rsp+C0h] [rbp-40h] BYREF
  LPVOID lpMem; // [rsp+C8h] [rbp-38h] BYREF
  CSetupOneSetting *v168; // [rsp+D0h] [rbp-30h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+E0h] [rbp-20h] BYREF
  int v170; // [rsp+200h] [rbp+100h] BYREF
  DWORD dwOSMajorVersion[68]; // [rsp+204h] [rbp+104h] BYREF
  unsigned __int16 v172; // [rsp+314h] [rbp+214h]
  unsigned __int16 v173; // [rsp+316h] [rbp+216h]
  unsigned __int16 v174[48]; // [rsp+320h] [rbp+220h] BYREF

  v3 = 0;
  v168 = this;
  v150 = 0;
  v151 = 0;
  v152 = 0;
  v153 = 0;
  lpMem = 0;
  memset_0(dwOSMajorVersion, 0, 0x118u);
  pdwReturnedProductType = 0;
  v166 = 0;
  VersionInformation.dwOSVersionInfoSize = 284;
  *(_OWORD *)&VersionInformation.dwMajorVersion = 0;
  memset_0(VersionInformation.szCSDVersion, 0, sizeof(VersionInformation.szCSDVersion));
  *(_QWORD *)&VersionInformation.wServicePackMajor = 0;
  v5 = VerSetConditionMask(0, 2u, 3u);
  v6 = VerSetConditionMask(v5, 1u, 3u);
  v7 = VerSetConditionMask(v6, 0x20u, 3u);
  *(_QWORD *)&VersionInformation.dwMajorVersion = 10;
  VersionInformation.wServicePackMajor = 0;
  if ( VerifyVersionInfoW(&VersionInformation, 0x23u, v7) )
  {
    IsWin10TelemetryTypeAllowed = TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed();
  }
  else
  {
    IsWin10TelemetryTypeAllowed = 0;
    Library = LoadLibraryExW(L"ntdll.dll", 0, 0x800u);
    v10 = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "WinSqmIsOptedInEx");
      if ( ProcAddress )
        IsWin10TelemetryTypeAllowed = ((unsigned int (__fastcall *)(__int64))ProcAddress)(4) == 1;
      FreeLibrary(v10);
    }
    v3 = 0;
  }
  `TelemetryPermissionsDownlevel::IsOptedIntoCore'::`2'::IsOptedIn = IsWin10TelemetryTypeAllowed;
  `TelemetryPermissionsDownlevel::IsOptedIntoCore'::`2'::AlreadyChecked = 1;
  if ( !IsWin10TelemetryTypeAllowed )
  {
    AppVersionInfo = 1;
    LastError = GetLastError();
    v14 = CurrentIP();
    v15 = ConstructPartialMsgW(0x3000000u, "Onesettings: Core telemetry is not allowed; skipping");
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      305,
      L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
      L"CSetupOneSetting::InitializeAndQuery",
      v14,
      LastError,
      0,
      0);
    return (unsigned int)AppVersionInfo;
  }
  v16 = (OneCore::Base::Telemetry::OneSettingsQuery *)operator new(0x750u);
  if ( v16 )
    v20 = (OneCore::Base::Telemetry::OneSettingsQuery *)OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(
                                                          v16,
                                                          v17,
                                                          v18,
                                                          v19,
                                                          phkResult);
  else
    v20 = 0;
  *((_QWORD *)this + 1) = v20;
  if ( v20 )
  {
    AppVersionInfo = OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(v20, (bool)v17);
    if ( AppVersionInfo < 0 )
    {
      v24 = GetLastError();
      v25 = CurrentIP();
      v26 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to AddParameterOsVer: 0x%x", AppVersionInfo);
      WdsSetupLogMessageW(
        v26,
        0,
        L"D",
        0,
        330,
        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
        L"CSetupOneSetting::InitializeAndQuery",
        v25,
        v24,
        0,
        0);
      return (unsigned int)AppVersionInfo;
    }
    v158 = 0;
    v27 = -1;
    if ( (unsigned int)IsWindowsPE() )
      goto LABEL_45;
    hKey = 0;
    cbData = 0;
    Type = 0;
    v28 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\SQMClient", 0, 0x20019u, &hKey);
    if ( v28 || !hKey )
    {
      SetLastError(v28);
      v158 = 0;
      goto LABEL_38;
    }
    v158 = 0;
    v29 = RegQueryValueExW(hKey, L"MachineId", 0, &Type, 0, &cbData);
    if ( !v29 )
    {
      if ( Type - 1 > 1 )
      {
        v29 = 13;
        goto LABEL_30;
      }
      v30 = cbData;
      ProcessHeap = GetProcessHeap();
      v32 = HeapAlloc(ProcessHeap, 8u, v30);
      v158 = v32;
      v3 = v32;
      if ( v32 )
      {
        *v32 = 0;
        v29 = RegQueryValueExW(hKey, L"MachineId", 0, 0, (LPBYTE)v32, &cbData);
        if ( !v29 )
        {
          if ( Type - 1 <= 1 )
            goto LABEL_30;
          v29 = 13;
        }
        v33 = GetProcessHeap();
        HeapFree(v33, 0, v3);
        v3 = 0;
        v158 = 0;
      }
      else
      {
        v29 = GetLastError();
      }
    }
LABEL_30:
    RegCloseKey(hKey);
    SetLastError(v29);
    if ( v3 )
    {
      v34 = -1;
      do
        ++v34;
      while ( *((_WORD *)v3 + v34) );
      if ( !v34 )
      {
        AppVersionInfo = -2147024809;
LABEL_36:
        v35 = GetLastError();
        v36 = CurrentIP();
        v37 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to AddParameterDeviceId: 0x%x", AppVersionInfo);
        WdsSetupLogMessageW(
          v37,
          0,
          L"D",
          0,
          351,
          L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
          L"CSetupOneSetting::InitializeAndQuery",
          v36,
          v35,
          0,
          0);
        v38 = v158;
        goto LABEL_56;
      }
      AppVersionInfo = RtlNameValueArray::Append(
                         (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                         L"deviceid",
                         (const unsigned __int16 *)v3);
      if ( AppVersionInfo < 0 )
        goto LABEL_36;
LABEL_45:
      AppVersionInfo = pGetAppVersionInfo(&v150, &v151, &v152, &v153, (unsigned __int16 **)&lpMem);
      if ( AppVersionInfo < 0 )
      {
        v45 = GetLastError();
        v46 = CurrentIP();
        v47 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to get app version info: 0x%x", AppVersionInfo);
        WdsSetupLogMessageW(
          v47,
          0,
          L"D",
          0,
          362,
          L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
          L"CSetupOneSetting::InitializeAndQuery",
          v46,
          v45,
          0,
          0);
        goto LABEL_53;
      }
      v48 = *((_QWORD *)this + 1);
      LODWORD(lpcbData) = v152;
      LODWORD(phkResulta) = v151;
      AppVersionInfo = StringCchPrintfW(v174, 0x2Cu, L"%d.%d.%d.%d", v150, phkResulta, lpcbData, v153);
      if ( AppVersionInfo < 0 )
        goto LABEL_52;
      v49 = -1;
      do
        ++v49;
      while ( v174[v49] );
      if ( !v49 )
      {
        AppVersionInfo = -2147024809;
LABEL_52:
        v50 = GetLastError();
        v51 = CurrentIP();
        v52 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to AddParameterAppVer: 0x%x", AppVersionInfo);
        WdsSetupLogMessageW(
          v52,
          0,
          L"D",
          0,
          369,
          L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
          L"CSetupOneSetting::InitializeAndQuery",
          v51,
          v50,
          0,
          0);
        goto LABEL_53;
      }
      AppVersionInfo = RtlNameValueArray::Append((RtlNameValueArray *)(v48 + 1656), L"appver", v174);
      if ( AppVersionInfo < 0 )
        goto LABEL_52;
      if ( lpMem )
      {
        v57 = -1;
        do
          ++v57;
        while ( *((_WORD *)lpMem + v57) );
        if ( !v57 )
        {
          AppVersionInfo = -2147024809;
LABEL_66:
          v58 = GetLastError();
          v59 = CurrentIP();
          v60 = ConstructPartialMsgW(
                  0x3000000u,
                  "Onesettings: Failed to AddParameter(%s): 0x%x",
                  (const char *)L"appBuildLab",
                  AppVersionInfo);
          WdsSetupLogMessageW(
            v60,
            0,
            L"D",
            0,
            378,
            L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
            L"CSetupOneSetting::InitializeAndQuery",
            v59,
            v58,
            0,
            0);
          goto LABEL_53;
        }
        AppVersionInfo = RtlNameValueArray::Append(
                           (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                           L"appBuildLab",
                           (const unsigned __int16 *)lpMem);
        if ( AppVersionInfo < 0 )
          goto LABEL_66;
      }
      v162 = 0;
      v156 = 0;
      v157 = 0;
      v61 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &v162);
      if ( v61 || !v162 )
      {
        SetLastError(v61);
        goto LABEL_173;
      }
      v160 = 0;
      v62 = 0;
      v63 = RegQueryValueExW(v162, L"InstallationType", 0, &v157, 0, &v156);
      if ( !v63 )
      {
        if ( v157 - 1 > 1 )
        {
          v63 = 13;
          goto LABEL_78;
        }
        v64 = v156;
        v65 = GetProcessHeap();
        v66 = (BYTE *)HeapAlloc(v65, 8u, v64);
        v160 = v66;
        v62 = v66;
        if ( v66 )
        {
          *(_WORD *)v66 = 0;
          v63 = RegQueryValueExW(v162, L"InstallationType", 0, 0, v66, &v156);
          if ( !v63 )
          {
            if ( v157 - 1 <= 1 )
              goto LABEL_78;
            v63 = 13;
          }
          v67 = GetProcessHeap();
          HeapFree(v67, 0, v62);
          v62 = 0;
          v160 = 0;
        }
        else
        {
          v63 = GetLastError();
        }
      }
LABEL_78:
      RegCloseKey(v162);
      SetLastError(v63);
      if ( v62 )
      {
        v68 = -1;
        do
          ++v68;
        while ( *(_WORD *)&v62[2 * v68] );
        if ( !v68 )
        {
          AppVersionInfo = -2147024809;
LABEL_84:
          v69 = GetLastError();
          v70 = CurrentIP();
          v71 = ConstructPartialMsgW(
                  0x3000000u,
                  "Onesettings: Failed to AddParameter(%s): 0x%x",
                  (const char *)L"platformInstallationType",
                  AppVersionInfo);
          WdsSetupLogMessageW(
            v71,
            0,
            L"D",
            0,
            397,
            L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
            L"CSetupOneSetting::InitializeAndQuery",
            v70,
            v69,
            0,
            0);
LABEL_180:
          v145 = GetProcessHeap();
          HeapFree(v145, 0, v62);
LABEL_53:
          v53 = lpMem;
          if ( lpMem )
          {
            v54 = GetProcessHeap();
            HeapFree(v54, 0, v53);
          }
          goto LABEL_55;
        }
        AppVersionInfo = RtlNameValueArray::Append(
                           (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                           L"platformInstallationType",
                           (const unsigned __int16 *)v62);
        if ( AppVersionInfo < 0 )
          goto LABEL_84;
        v163 = 0;
        v150 = 0;
        v151 = 0;
        v72 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion", 0, 0x20019u, &v163);
        if ( v72 || !v163 )
        {
          SetLastError(v72);
          goto LABEL_164;
        }
        v73 = 0;
        v74 = RegQueryValueExW(v163, L"EditionId", 0, &v151, 0, &v150);
        if ( !v74 )
        {
          if ( v151 - 1 > 1 )
          {
            v74 = 13;
            goto LABEL_96;
          }
          v75 = v150;
          v76 = GetProcessHeap();
          v77 = (BYTE *)HeapAlloc(v76, 8u, v75);
          v73 = v77;
          if ( v77 )
          {
            *(_WORD *)v77 = 0;
            v74 = RegQueryValueExW(v163, L"EditionId", 0, 0, v77, &v150);
            if ( !v74 )
            {
              if ( v151 - 1 <= 1 )
                goto LABEL_96;
              v74 = 13;
            }
            v78 = GetProcessHeap();
            HeapFree(v78, 0, v73);
            v73 = 0;
          }
          else
          {
            v74 = GetLastError();
          }
        }
LABEL_96:
        RegCloseKey(v163);
        SetLastError(v74);
        if ( v73 )
        {
          v79 = -1;
          do
            ++v79;
          while ( *(_WORD *)&v73[2 * v79] );
          if ( !v79 )
          {
            AppVersionInfo = -2147024809;
LABEL_102:
            v80 = GetLastError();
            v81 = CurrentIP();
            v82 = ConstructPartialMsgW(
                    0x3000000u,
                    "Onesettings: Failed to AddParameter(%s): 0x%x",
                    (const char *)L"platformEdition",
                    AppVersionInfo);
            WdsSetupLogMessageW(
              v82,
              0,
              L"D",
              0,
              415,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v81,
              v80,
              0,
              0);
LABEL_171:
            v138 = GetProcessHeap();
            HeapFree(v138, 0, v73);
            goto LABEL_180;
          }
          AppVersionInfo = RtlNameValueArray::Append(
                             (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                             L"platformEdition",
                             (const unsigned __int16 *)v73);
          if ( AppVersionInfo < 0 )
            goto LABEL_102;
          v170 = 284;
          if ( !(unsigned int)WdsGetVersionEx(&v170) )
          {
            v83 = GetLastError();
            v84 = v83 < 0;
            if ( v83 > 0 )
              v84 = 1;
            if ( v84 )
            {
              v85 = GetLastError();
              AppVersionInfo = v85;
              if ( v85 > 0 )
                AppVersionInfo = (unsigned __int16)v85 | 0x80070000;
            }
            else
            {
              AppVersionInfo = -2147467259;
            }
            v86 = GetLastError();
            v87 = CurrentIP();
            v88 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to get OS version: 0x%x", AppVersionInfo);
            WdsSetupLogMessageW(
              v88,
              0,
              L"D",
              0,
              426,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v87,
              v86,
              0,
              0);
            goto LABEL_171;
          }
          if ( !GetProductInfo(dwOSMajorVersion[0], dwOSMajorVersion[1], v172, v173, &pdwReturnedProductType) )
          {
            v89 = GetLastError();
            v90 = v89 < 0;
            if ( v89 > 0 )
              v90 = 1;
            if ( v90 )
            {
              v91 = GetLastError();
              AppVersionInfo = v91;
              if ( v91 > 0 )
                AppVersionInfo = (unsigned __int16)v91 | 0x80070000;
            }
            else
            {
              AppVersionInfo = -2147467259;
            }
            v92 = GetLastError();
            v93 = CurrentIP();
            v94 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to get OS product type: 0x%x", AppVersionInfo);
            WdsSetupLogMessageW(
              v94,
              0,
              L"D",
              0,
              433,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v93,
              v92,
              0,
              0);
            goto LABEL_171;
          }
          AppVersionInfo = StrAllocatingPrintf(&v166, L"%u", pdwReturnedProductType);
          if ( AppVersionInfo < 0 )
          {
            v95 = GetLastError();
            v96 = CurrentIP();
            v97 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to build SKU string: 0x%x", AppVersionInfo);
            WdsSetupLogMessageW(
              v97,
              0,
              L"D",
              0,
              440,
              L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
              L"CSetupOneSetting::InitializeAndQuery",
              v96,
              v95,
              0,
              0);
LABEL_159:
            v127 = v166;
            if ( v166 )
            {
              v128 = GetProcessHeap();
              HeapFree(v128, 0, v127);
            }
            goto LABEL_171;
          }
          if ( !v166 )
            goto LABEL_161;
          v98 = -1;
          do
            ++v98;
          while ( v166[v98] );
          if ( v98 )
          {
            AppVersionInfo = RtlNameValueArray::Append(
                               (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                               L"sku",
                               v166);
            if ( AppVersionInfo >= 0 )
            {
              v164 = 0;
              v152 = 0;
              v153 = 0;
              v99 = RegOpenKeyExW(
                      HKEY_LOCAL_MACHINE,
                      L"SOFTWARE\\Microsoft\\WindowsSelfHost\\Applicability",
                      0,
                      0x20019u,
                      &v164);
              if ( v99 || !v164 )
              {
                SetLastError(v99);
                v100 = 0;
                goto LABEL_146;
              }
              v100 = 0;
              v101 = RegQueryValueExW(v164, L"Ring", 0, &v153, 0, &v152);
              if ( !v101 )
              {
                if ( v153 - 1 > 1 )
                {
                  v101 = 13;
                  goto LABEL_139;
                }
                v102 = v152;
                v103 = GetProcessHeap();
                v104 = (BYTE *)HeapAlloc(v103, 8u, v102);
                v100 = v104;
                if ( v104 )
                {
                  *(_WORD *)v104 = 0;
                  v101 = RegQueryValueExW(v164, L"Ring", 0, 0, v104, &v152);
                  if ( !v101 )
                  {
                    if ( v153 - 1 <= 1 )
                      goto LABEL_139;
                    v101 = 13;
                  }
                  v105 = GetProcessHeap();
                  HeapFree(v105, 0, v100);
                  v100 = 0;
                }
                else
                {
                  v101 = GetLastError();
                }
              }
LABEL_139:
              RegCloseKey(v164);
              SetLastError(v101);
              if ( v100 )
              {
                do
                  ++v27;
                while ( *(_WORD *)&v100[2 * v27] );
                if ( !v27 )
                {
                  AppVersionInfo = -2147024809;
LABEL_144:
                  v106 = GetLastError();
                  v107 = CurrentIP();
                  v108 = ConstructPartialMsgW(
                           0x3000000u,
                           "Onesettings: Failed to AddParameter(%s): 0x%x",
                           (const char *)L"ring",
                           AppVersionInfo);
                  WdsSetupLogMessageW(
                    v108,
                    0,
                    L"D",
                    0,
                    464,
                    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                    L"CSetupOneSetting::InitializeAndQuery",
                    v107,
                    v106,
                    0,
                    0);
LABEL_157:
                  v126 = GetProcessHeap();
                  HeapFree(v126, 0, v100);
LABEL_158:
                  v62 = v160;
                  goto LABEL_159;
                }
                AppVersionInfo = RtlNameValueArray::Append(
                                   (RtlNameValueArray *)(*((_QWORD *)this + 1) + 1656LL),
                                   L"ring",
                                   (const unsigned __int16 *)v100);
                if ( AppVersionInfo < 0 )
                  goto LABEL_144;
              }
LABEL_146:
              v165 = 0;
              if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", 0, 0x20019u, &v165) || !v165 )
              {
                SetLastError(0);
              }
              else
              {
                Value = RegQueryValueExW(v165, L"UseOneSettingsTestServer", 0, 0, 0, 0);
                RegCloseKey(v165);
                SetLastError(0);
                if ( !Value )
                {
                  v110 = GetLastError();
                  v111 = CurrentIP();
                  v112 = ConstructPartialMsgW(
                           0x4000000u,
                           "Onesettings: Querying PPE server %s",
                           (const char *)L"settings-win-ppe.data.microsoft.com");
                  WdsSetupLogMessageW(
                    v112,
                    0,
                    L"D",
                    0,
                    472,
                    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                    L"CSetupOneSetting::InitializeAndQuery",
                    v111,
                    v110,
                    0,
                    0);
                  v115 = (wchar_t *)L"settings-win-ppe.data.microsoft.com";
                  goto LABEL_152;
                }
              }
              v116 = GetLastError();
              v117 = CurrentIP();
              v118 = ConstructPartialMsgW(
                       0x4000000u,
                       "Onesettings: Querying Prod server %s",
                       (const char *)L"settings-win.data.microsoft.com");
              WdsSetupLogMessageW(
                v118,
                0,
                L"D",
                0,
                477,
                L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                L"CSetupOneSetting::InitializeAndQuery",
                v117,
                v116,
                0,
                0);
              v115 = (wchar_t *)L"settings-win.data.microsoft.com";
LABEL_152:
              v119 = v168;
              AppVersionInfo = OneCore::Base::Telemetry::OneSettingsQuery::Query(
                                 *((OneCore::Base::Telemetry::OneSettingsQuery **)v168 + 1),
                                 v115,
                                 v113,
                                 v114,
                                 phkResultb);
              if ( AppVersionInfo >= 0 )
              {
                if ( !OneCore::Base::Telemetry::OneSettingsQuery::SettingsFresh(*((OneCore::Base::Telemetry::OneSettingsQuery **)v119
                                                                                + 1)) )
                {
                  AppVersionInfo = -2147221136;
                  v123 = GetLastError();
                  v124 = CurrentIP();
                  v125 = ConstructPartialMsgW(
                           0x3000000u,
                           "Onesettings: Settings not fresh after query: 0x%x",
                           -2147221136);
                  WdsSetupLogMessageW(
                    v125,
                    0,
                    L"D",
                    0,
                    489,
                    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                    L"CSetupOneSetting::InitializeAndQuery",
                    v124,
                    v123,
                    0,
                    0);
                }
              }
              else
              {
                v120 = GetLastError();
                v121 = CurrentIP();
                v122 = ConstructPartialMsgW(
                         0x3000000u,
                         "Onesettings: Failed to Query Onesettings: 0x%x",
                         AppVersionInfo);
                WdsSetupLogMessageW(
                  v122,
                  0,
                  L"D",
                  0,
                  482,
                  L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
                  L"CSetupOneSetting::InitializeAndQuery",
                  v121,
                  v120,
                  0,
                  0);
              }
              if ( !v100 )
                goto LABEL_158;
              goto LABEL_157;
            }
          }
          else
          {
LABEL_161:
            AppVersionInfo = -2147024809;
          }
          v129 = GetLastError();
          v130 = CurrentIP();
          v131 = ConstructPartialMsgW(
                   0x3000000u,
                   "Onesettings: Failed to AddParameter(%s): 0x%x",
                   (const char *)L"sku",
                   AppVersionInfo);
          WdsSetupLogMessageW(
            v131,
            0,
            L"D",
            0,
            447,
            L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
            L"CSetupOneSetting::InitializeAndQuery",
            v130,
            v129,
            0,
            0);
          goto LABEL_159;
        }
LABEL_164:
        v132 = GetLastError();
        v133 = v132 < 0;
        if ( v132 > 0 )
          v133 = 1;
        if ( v133 )
        {
          v134 = GetLastError();
          AppVersionInfo = v134;
          if ( v134 > 0 )
            AppVersionInfo = (unsigned __int16)v134 | 0x80070000;
        }
        else
        {
          AppVersionInfo = -2147467259;
        }
        v135 = GetLastError();
        v136 = CurrentIP();
        v137 = ConstructPartialMsgW(
                 0x3000000u,
                 "Onesettings: Failed to get EditionId from registry: 0x%x",
                 AppVersionInfo);
        WdsSetupLogMessageW(
          v137,
          0,
          L"D",
          0,
          408,
          L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
          L"CSetupOneSetting::InitializeAndQuery",
          v136,
          v135,
          0,
          0);
        goto LABEL_180;
      }
LABEL_173:
      v139 = GetLastError();
      v140 = v139 < 0;
      if ( v139 > 0 )
        v140 = 1;
      if ( v140 )
      {
        v141 = GetLastError();
        AppVersionInfo = v141;
        if ( v141 > 0 )
          AppVersionInfo = (unsigned __int16)v141 | 0x80070000;
      }
      else
      {
        AppVersionInfo = -2147467259;
      }
      v142 = GetLastError();
      v143 = CurrentIP();
      v144 = ConstructPartialMsgW(
               0x3000000u,
               "Onesettings: Failed to get InstallationType from registry: 0x%x",
               AppVersionInfo);
      WdsSetupLogMessageW(
        v144,
        0,
        L"D",
        0,
        390,
        L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
        L"CSetupOneSetting::InitializeAndQuery",
        v143,
        v142,
        0,
        0);
      goto LABEL_53;
    }
LABEL_38:
    v39 = GetLastError();
    v40 = v39 < 0;
    if ( v39 > 0 )
      v40 = 1;
    if ( v40 )
    {
      v41 = GetLastError();
      AppVersionInfo = v41;
      if ( v41 > 0 )
        AppVersionInfo = (unsigned __int16)v41 | 0x80070000;
    }
    else
    {
      AppVersionInfo = -2147467259;
    }
    v42 = GetLastError();
    v43 = CurrentIP();
    v44 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to get DeviceId from registry: 0x%x", AppVersionInfo);
    WdsSetupLogMessageW(
      v44,
      0,
      L"D",
      0,
      344,
      L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
      L"CSetupOneSetting::InitializeAndQuery",
      v43,
      v42,
      0,
      0);
LABEL_55:
    v38 = v158;
    if ( !v158 )
      return (unsigned int)AppVersionInfo;
LABEL_56:
    v55 = GetProcessHeap();
    HeapFree(v55, 0, v38);
    return (unsigned int)AppVersionInfo;
  }
  AppVersionInfo = -2147024882;
  v21 = GetLastError();
  v22 = CurrentIP();
  v23 = ConstructPartialMsgW(0x3000000u, "Onesettings: Failed to initialize onesettings: 0x%x", -2147024882);
  WdsSetupLogMessageW(
    v23,
    0,
    L"D",
    0,
    313,
    L"base\\ntsetup\\lib\\onesettings\\src\\onesettings.cpp",
    L"CSetupOneSetting::InitializeAndQuery",
    v22,
    v21,
    0,
    0);
  return (unsigned int)AppVersionInfo;
}

```

## disassembly

```asm
0x1804acad4  push    rbp
0x1804acad6  push    rbx
0x1804acad7  push    rsi
0x1804acad8  push    rdi
0x1804acad9  push    r12
0x1804acadb  push    r13
0x1804acadd  push    r14
0x1804acadf  push    r15
0x1804acae1  lea     rbp, [rsp-298h]
0x1804acae9  sub     rsp, 398h
0x1804acaf0  mov     rax, cs:__security_cookie
0x1804acaf7  xor     rax, rsp
0x1804acafa  mov     [rbp+2D0h+var_50], rax
0x1804acb01  xor     edi, edi
0x1804acb03  mov     [rbp+2D0h+var_300], rcx
0x1804acb07  mov     r15, rcx
0x1804acb0a  mov     [rsp+3D0h+var_370], edi
0x1804acb0e  lea     rcx, [rbp+2D0h+dwOSMajorVersion]; void *
0x1804acb15  mov     [rsp+3D0h+var_36C], edi
0x1804acb19  xor     edx, edx; Val
0x1804acb1b  mov     [rsp+3D0h+var_368], edi
0x1804acb1f  mov     r8d, 118h; Size
0x1804acb25  mov     [rsp+3D0h+var_364], edi
0x1804acb29  mov     [rbp+2D0h+lpMem], rdi
0x1804acb2d  call    memset_0
0x1804acb32  xorps   xmm0, xmm0
0x1804acb35  mov     [rbp+2D0h+pdwReturnedProductType], edi
0x1804acb38  xor     edx, edx; Val
0x1804acb3a  mov     [rbp+2D0h+var_310], rdi
0x1804acb3e  mov     r8d, 100h; Size
0x1804acb44  mov     [rbp+2D0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1804acb4b  lea     rcx, [rbp+2D0h+VersionInformation.szCSDVersion]; void *
0x1804acb4f  movups  xmmword ptr [rbp+2D0h+VersionInformation.dwMajorVersion], xmm0
0x1804acb53  call    memset_0
0x1804acb58  mov     r8b, 3; Condition
0x1804acb5b  mov     qword ptr [rbp+2D0h+VersionInformation.wServicePackMajor], rdi
0x1804acb62  lea     edx, [rdi+2]; TypeMask
0x1804acb65  xor     ecx, ecx; ConditionMask
0x1804acb67  call    cs:__imp_VerSetConditionMask
0x1804acb6d  lea     r13d, [rdi+1]
0x1804acb71  mov     r8b, 3; Condition
0x1804acb74  mov     rcx, rax; ConditionMask
0x1804acb77  mov     edx, r13d; TypeMask
0x1804acb7a  call    cs:__imp_VerSetConditionMask
0x1804acb80  mov     r8b, 3; Condition
0x1804acb83  lea     edx, [rdi+20h]; TypeMask
0x1804acb86  mov     rcx, rax; ConditionMask
0x1804acb89  call    cs:__imp_VerSetConditionMask
0x1804acb8f  lea     edx, [rdi+23h]; dwTypeMask
0x1804acb92  mov     qword ptr [rbp+2D0h+VersionInformation.dwMajorVersion], 0Ah
0x1804acb9a  mov     r8, rax; dwlConditionMask
0x1804acb9d  mov     [rbp+2D0h+VersionInformation.wServicePackMajor], di
0x1804acba4  lea     rcx, [rbp+2D0h+VersionInformation]; lpVersionInformation
0x1804acba8  call    cs:__imp_VerifyVersionInfoW
0x1804acbae  test    eax, eax
0x1804acbb0  jz      short loc_1804ACBBB
0x1804acbb2  call    ?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z; TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)
0x1804acbb7  mov     bl, al
0x1804acbb9  jmp     short loc_1804ACC0B
0x1804acbbb  xor     edx, edx; hFile
0x1804acbbd  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x1804acbc4  mov     r8d, 800h; dwFlags
0x1804acbca  mov     bl, dil
0x1804acbcd  call    cs:__imp_LoadLibraryExW
0x1804acbd3  mov     rdi, rax
0x1804acbd6  test    rax, rax
0x1804acbd9  jz      short loc_1804ACC09
0x1804acbdb  lea     rdx, aWinsqmisoptedi; "WinSqmIsOptedInEx"
0x1804acbe2  mov     rcx, rax; hModule
0x1804acbe5  call    cs:__imp_GetProcAddress
0x1804acbeb  test    rax, rax
0x1804acbee  jz      short loc_1804ACC00
0x1804acbf0  mov     ecx, 4
0x1804acbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1804acbfa  cmp     eax, r13d
0x1804acbfd  setz    bl
0x1804acc00  mov     rcx, rdi; hLibModule
0x1804acc03  call    cs:__imp_FreeLibrary
0x1804acc09  xor     edi, edi
0x1804acc0b  mov     cs:?IsOptedIn@?1??IsOptedIntoCore@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, bl; bool `TelemetryPermissionsDownlevel::IsOptedIntoCore(bool)'::`2'::IsOptedIn
0x1804acc11  mov     cs:?AlreadyChecked@?1??IsOptedIntoCore@TelemetryPermissionsDownlevel@@SA_N_N@Z@4_NA, r13b; bool `TelemetryPermissionsDownlevel::IsOptedIntoCore(bool)'::`2'::AlreadyChecked
0x1804acc18  test    bl, bl
0x1804acc1a  jnz     short loc_1804ACC8F
0x1804acc1c  mov     esi, r13d
0x1804acc1f  call    cs:__imp_GetLastError
0x1804acc25  mov     edi, eax
0x1804acc27  call    cs:__imp_CurrentIP
0x1804acc2d  lea     rdx, aOnesettingsCor; "Onesettings: Core telemetry is not allo"...
0x1804acc34  mov     ecx, 3000000h; unsigned int
0x1804acc39  mov     rbx, rax
0x1804acc3c  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1804acc41  xor     ecx, ecx
0x1804acc43  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1804acc4a  mov     [rsp+3D0h+var_380], ecx
0x1804acc4e  lea     r15, aBaseNtsetupLib_7; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1804acc55  mov     [rsp+3D0h+var_388], rcx
0x1804acc5a  mov     [rsp+3D0h+var_390], edi
0x1804acc5e  mov     [rsp+3D0h+var_398], rbx
0x1804acc63  mov     [rsp+3D0h+var_3A0], r14
0x1804acc68  mov     [rsp+3D0h+lpcbData], r15
0x1804acc6d  mov     dword ptr [rsp+3D0h+phkResult], 131h
0x1804acc75  xor     r9d, r9d
0x1804acc78  lea     r8, aD_0; "D"
0x1804acc7f  xor     edx, edx
0x1804acc81  mov     rcx, rax
0x1804acc84  call    cs:__imp_WdsSetupLogMessageW
0x1804acc8a  jmp     loc_1804AD1C7
0x1804acc8f  mov     ecx, 750h; Size
0x1804acc94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804acc99  test    rax, rax
0x1804acc9c  jz      short loc_1804ACCA8
0x1804acc9e  mov     rcx, rax; this
0x1804acca1  call    ??0OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@PEBG000@Z; OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(ushort const *,ushort const *,ushort const *,ushort const *)
0x1804acca6  jmp     short loc_1804ACCAB
0x1804acca8  mov     rax, rdi
0x1804accab  mov     [r15+8], rax
0x1804accaf  test    rax, rax
0x1804accb2  jnz     short loc_1804ACD17
0x1804accb4  mov     esi, 8007000Eh
0x1804accb9  call    cs:__imp_GetLastError
0x1804accbf  mov     edi, eax
0x1804accc1  call    cs:__imp_CurrentIP
0x1804accc7  mov     r8d, esi
0x1804accca  lea     rdx, aOnesettingsFai_2; "Onesettings: Failed to initialize onese"...
0x1804accd1  mov     ecx, 3000000h; unsigned int
0x1804accd6  mov     rbx, rax
0x1804accd9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1804accde  xor     ecx, ecx
0x1804acce0  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1804acce7  mov     [rsp+3D0h+var_380], ecx
0x1804acceb  lea     r15, aBaseNtsetupLib_7; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1804accf2  mov     [rsp+3D0h+var_388], rcx
0x1804accf7  mov     [rsp+3D0h+var_390], edi
0x1804accfb  mov     [rsp+3D0h+var_398], rbx
0x1804acd00  mov     [rsp+3D0h+var_3A0], r14
0x1804acd05  mov     [rsp+3D0h+lpcbData], r15
0x1804acd0a  mov     dword ptr [rsp+3D0h+phkResult], 139h
0x1804acd12  jmp     loc_1804ACC75
0x1804acd17  mov     rcx, rax; this
0x1804acd1a  call    ?AddParameterOsVer@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJ_N@Z; OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(bool)
0x1804acd1f  mov     esi, eax
0x1804acd21  test    eax, eax
0x1804acd23  jns     short loc_1804ACD83
0x1804acd25  call    cs:__imp_GetLastError
0x1804acd2b  mov     edi, eax
0x1804acd2d  call    cs:__imp_CurrentIP
0x1804acd33  mov     r8d, esi
0x1804acd36  lea     rdx, aOnesettingsFai_14; "Onesettings: Failed to AddParameterOsVe"...
0x1804acd3d  mov     ecx, 3000000h; unsigned int
0x1804acd42  mov     rbx, rax
0x1804acd45  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1804acd4a  xor     ecx, ecx
0x1804acd4c  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1804acd53  mov     [rsp+3D0h+var_380], ecx
0x1804acd57  lea     r15, aBaseNtsetupLib_7; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1804acd5e  mov     [rsp+3D0h+var_388], rcx
0x1804acd63  mov     [rsp+3D0h+var_390], edi
0x1804acd67  mov     [rsp+3D0h+var_398], rbx
0x1804acd6c  mov     [rsp+3D0h+var_3A0], r14
0x1804acd71  mov     [rsp+3D0h+lpcbData], r15
0x1804acd76  mov     dword ptr [rsp+3D0h+phkResult], 14Ah
0x1804acd7e  jmp     loc_1804ACC75
0x1804acd83  mov     [rbp+2D0h+var_350], rdi
0x1804acd87  call    IsWindowsPE
0x1804acd8c  or      r14, 0FFFFFFFFFFFFFFFFh
0x1804acd90  mov     esi, 0Dh
0x1804acd95  test    eax, eax
0x1804acd97  jnz     loc_1804AD035
0x1804acd9d  lea     rax, [rbp+2D0h+hKey]
0x1804acda1  mov     [rbp+2D0h+hKey], rdi
0x1804acda5  mov     r9d, 20019h; samDesired
0x1804acdab  mov     [rsp+3D0h+phkResult], rax; phkResult
0x1804acdb0  xor     r8d, r8d; ulOptions
0x1804acdb3  mov     [rsp+3D0h+cbData], edi
0x1804acdb7  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\SQMClient"
0x1804acdbe  mov     [rsp+3D0h+Type], edi
0x1804acdc2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1804acdc9  call    cs:__imp_RegOpenKeyExW
0x1804acdcf  test    eax, eax
0x1804acdd1  jnz     loc_1804ACF84
0x1804acdd7  mov     rcx, [rbp+2D0h+hKey]; hKey
0x1804acddb  test    rcx, rcx
0x1804acdde  jz      loc_1804ACF84
0x1804acde4  lea     rax, [rsp+3D0h+cbData]
0x1804acde9  mov     [rbp+2D0h+var_350], rdi
0x1804acded  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x1804acdf2  lea     r9, [rsp+3D0h+Type]; lpType
0x1804acdf7  xor     r12d, r12d
0x1804acdfa  lea     rdx, aMachineid; "MachineId"
0x1804ace01  xor     r8d, r8d; lpReserved
0x1804ace04  mov     [rsp+3D0h+phkResult], r12; lpData
0x1804ace09  call    cs:__imp_RegQueryValueExW
0x1804ace0f  mov     ebx, eax
0x1804ace11  test    eax, eax
0x1804ace13  jnz     loc_1804ACEB4
0x1804ace19  mov     eax, [rsp+3D0h+Type]
0x1804ace1d  dec     eax
0x1804ace1f  cmp     eax, r13d
0x1804ace22  jbe     short loc_1804ACE2B
0x1804ace24  mov     ebx, esi
0x1804ace26  jmp     loc_1804ACEB4
0x1804ace2b  mov     ebx, [rsp+3D0h+cbData]
0x1804ace2f  call    cs:__imp_GetProcessHeap
0x1804ace35  mov     r8d, ebx; dwBytes
0x1804ace38  mov     edx, 8; dwFlags
0x1804ace3d  mov     rcx, rax; hHeap
0x1804ace40  call    cs:__imp_HeapAlloc
0x1804ace46  mov     [rbp+2D0h+var_350], rax
0x1804ace4a  mov     rdi, rax
0x1804ace4d  test    rax, rax
0x1804ace50  jz      short loc_1804ACEAC
0x1804ace52  mov     [rax], r12w
0x1804ace56  lea     rdx, aMachineid; "MachineId"
0x1804ace5d  mov     rcx, [rbp+2D0h+hKey]; hKey
0x1804ace61  lea     rax, [rsp+3D0h+cbData]
0x1804ace66  mov     [rsp+3D0h+lpcbData], rax; lpcbData
0x1804ace6b  xor     r9d, r9d; lpType
0x1804ace6e  xor     r8d, r8d; lpReserved
0x1804ace71  mov     [rsp+3D0h+phkResult], rdi; lpData
0x1804ace76  call    cs:__imp_RegQueryValueExW
0x1804ace7c  mov     ebx, eax
0x1804ace7e  test    eax, eax
0x1804ace80  jnz     short loc_1804ACE8F
0x1804ace82  mov     eax, [rsp+3D0h+Type]
0x1804ace86  dec     eax
0x1804ace88  cmp     eax, r13d
0x1804ace8b  jbe     short loc_1804ACEB4
0x1804ace8d  mov     ebx, esi
0x1804ace8f  call    cs:__imp_GetProcessHeap
0x1804ace95  mov     r8, rdi; lpMem
0x1804ace98  xor     edx, edx; dwFlags
0x1804ace9a  mov     rcx, rax; hHeap
0x1804ace9d  call    cs:__imp_HeapFree
0x1804acea3  mov     rdi, r12
0x1804acea6  mov     [rbp+2D0h+var_350], r12
0x1804aceaa  jmp     short loc_1804ACEB4
0x1804aceac  call    cs:__imp_GetLastError
0x1804aceb2  mov     ebx, eax
0x1804aceb4  mov     rcx, [rbp+2D0h+hKey]; hKey
0x1804aceb8  call    cs:__imp_RegCloseKey
0x1804acebe  mov     ecx, ebx; dwErrCode
0x1804acec0  call    cs:__imp_SetLastError
0x1804acec6  test    rdi, rdi
0x1804acec9  jz      loc_1804ACF90
0x1804acecf  mov     rax, r14
0x1804aced2  inc     rax
0x1804aced5  cmp     [rdi+rax*2], r12w
0x1804aceda  jnz     short loc_1804ACED2
0x1804acedc  test    rax, rax
0x1804acedf  jnz     short loc_1804ACEE8
0x1804acee1  mov     esi, 80070057h
0x1804acee6  jmp     short loc_1804ACF0E
0x1804acee8  mov     rcx, [r15+8]
0x1804aceec  lea     rdx, aDeviceid; "deviceid"
0x1804acef3  add     rcx, 678h; this
0x1804acefa  mov     r8, rdi; unsigned __int16 *
0x1804acefd  call    ?Append@RtlNameValueArray@@QEAAJPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x1804acf02  xor     edi, edi
0x1804acf04  mov     esi, eax
0x1804acf06  test    eax, eax
0x1804acf08  jns     loc_1804AD035
0x1804acf0e  call    cs:__imp_GetLastError
0x1804acf14  mov     edi, eax
0x1804acf16  call    cs:__imp_CurrentIP
0x1804acf1c  mov     r8d, esi
0x1804acf1f  lea     rdx, aOnesettingsFai_8; "Onesettings: Failed to AddParameterDevi"...
0x1804acf26  mov     ecx, 3000000h; unsigned int
0x1804acf2b  mov     rbx, rax
0x1804acf2e  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1804acf33  mov     [rsp+3D0h+var_380], r12d
0x1804acf38  lea     r14, aCsetuponesetti; "CSetupOneSetting::InitializeAndQuery"
0x1804acf3f  mov     [rsp+3D0h+var_388], r12
0x1804acf44  lea     r15, aBaseNtsetupLib_7; "base\\ntsetup\\lib\\onesettings\\src\\o"...
0x1804acf4b  mov     [rsp+3D0h+var_390], edi
0x1804acf4f  lea     r8, aD_0; "D"
0x1804acf56  mov     [rsp+3D0h+var_398], rbx
0x1804acf5b  xor     r9d, r9d
0x1804acf5e  mov     [rsp+3D0h+var_3A0], r14
0x1804acf63  xor     edx, edx
0x1804acf65  mov     [rsp+3D0h+lpcbData], r15
0x1804acf6a  mov     rcx, rax
0x1804acf6d  mov     dword ptr [rsp+3D0h+phkResult], 15Fh
0x1804acf75  call    cs:__imp_WdsSetupLogMessageW
0x1804acf7b  mov     rbx, [rbp+2D0h+var_350]
0x1804acf7f  jmp     loc_1804AD1B3
0x1804acf84  mov     ecx, eax; dwErrCode
0x1804acf86  call    cs:__imp_SetLastError
0x1804acf8c  mov     [rbp+2D0h+var_350], rdi
0x1804acf90  call    cs:__imp_GetLastError
0x1804acf96  mov     ebx, 80070000h
0x1804acf9b  test    eax, eax
0x1804acf9d  jle     short loc_1804ACFA6
0x1804acf9f  movzx   eax, ax
0x1804acfa2  or      eax, ebx
0x1804acfa4  test    eax, eax
0x1804acfa6  jns     short loc_1804ACFBB
0x1804acfa8  call    cs:__imp_GetLastError
0x1804acfae  mov     esi, eax
0x1804acfb0  test    eax, eax
0x1804acfb2  jle     short loc_1804ACFC0
  ... truncated ...
```
