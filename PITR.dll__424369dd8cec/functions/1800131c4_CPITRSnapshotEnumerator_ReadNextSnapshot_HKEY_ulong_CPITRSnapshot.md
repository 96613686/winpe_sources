# CPITRSnapshotEnumerator::ReadNextSnapshot(HKEY__ *,ulong,CPITRSnapshot * *)

- ea: `0x1800131c4`
- end: `0x18001376c`
- name: `?ReadNextSnapshot@CPITRSnapshotEnumerator@@IEAAJPEAUHKEY__@@KPEAPEAVCPITRSnapshot@@@Z`
- size: `1448`
- prototype: `__int64 __fastcall(CPITRSnapshotEnumerator *this, HKEY, DWORD, struct CPITRSnapshot **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180005614`

## callees

- `0x1800053e8`
- `0x180009e04`
- `0x1800131c4`
- `0x18001def0`
- `0x180021140`
- `0x18002125c`
- `0x1800212c0`
- `0x180039424`
- `0x1800399c8`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013702`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013702`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013710`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013628`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800133e5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013460`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013597`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013628`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001373a`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001373a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800132eb`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x1800132eb`
- `WDSCORE!CurrentIP` at `0x18001326b`
- `WDSCORE!CurrentIP` at `0x18001332d`
- `WDSCORE!CurrentIP` at `0x1800133ed`
- `WDSCORE!CurrentIP` at `0x180013468`
- `WDSCORE!CurrentIP` at `0x18001352a`
- `WDSCORE!CurrentIP` at `0x18001359f`
- `WDSCORE!CurrentIP` at `0x180013630`
- `WDSCORE!CurrentIP` at `0x18001326b`
- `WDSCORE!CurrentIP` at `0x18001332d`
- `WDSCORE!CurrentIP` at `0x1800133ed`
- `WDSCORE!CurrentIP` at `0x180013468`
- `WDSCORE!CurrentIP` at `0x18001352a`
- `WDSCORE!CurrentIP` at `0x18001359f`
- `WDSCORE!CurrentIP` at `0x180013630`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800132d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001339b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013450`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800134c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013589`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013692`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800132d1`
- `WDSCORE!WdsSetupLogMessageW` at `0x18001339b`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013450`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800134c8`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013589`
- `WDSCORE!WdsSetupLogMessageW` at `0x180013692`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800136a0`
- `unbcl!??2Object@UnBCL@@SAPEAX_K@Z` at `0x1800136a0`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800134df`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013604`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x1800134df`
- `unbcl!??0String@UnBCL@@QEAA@PEBG@Z` at `0x180013604`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800134f8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001361e`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x1800134f8`
- `unbcl!??1String@UnBCL@@UEAA@XZ` at `0x18001361e`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001371a`
- `VSSAPI!VssFreeSnapshotPropertiesInternal` at `0x18001371a`

## string_xrefs

- `0x1800132ae`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180013378`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001342d`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800134a5`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180013566`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800135de`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001366f`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18001327e`: `%hs: Failed to initialize COM. Error: 0x%08X`
- `0x18001334d`: `Failed to open PITR snapshots key %s. Error: 0x%08X`
- `0x1800132a2`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x18001336c`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x180013421`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x180013499`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x18001355a`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x1800135d2`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x180013663`: `CPITRSnapshotEnumerator::ReadNextSnapshot`
- `0x180013277`: `CPITRSnapshotEnumerator::ReadNextSnapshot`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CPITRSnapshotEnumerator::ReadNextSnapshot(
        CPITRSnapshotEnumerator *this,
        HKEY a2,
        DWORD a3,
        struct CPITRSnapshot **a4)
{
  int SnapshotProp; // esi
  DWORD v9; // edi
  __int64 v10; // rbx
  struct tagLOG_PARTIAL_MSG *v11; // rax
  LSTATUS v12; // eax
  DWORD LastError; // edi
  __int64 v14; // rbx
  unsigned int v15; // ecx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  unsigned __int16 *v17; // r14
  DWORD v18; // edi
  __int64 v19; // rbx
  struct tagLOG_PARTIAL_MSG *v20; // rax
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  struct UnBCL::String *v24; // rax
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  int v28; // r15d
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  struct UnBCL::String *v32; // rax
  __int64 *v33; // r8
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  void *v37; // r10
  struct CPITRSnapshot *v38; // rax
  HANDLE ProcessHeap; // rax
  int v40; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  struct PITR::_VERSION_DATA *v42; // [rsp+70h] [rbp-90h] BYREF
  __int64 v43; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v44; // [rsp+80h] [rbp-80h] BYREF
  struct _FILETIME v45; // [rsp+88h] [rbp-78h] BYREF
  struct _FILETIME v46; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v47[24]; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+B0h] [rbp-50h] BYREF
  struct _VSS_SNAPSHOT_PROP v49; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[256]; // [rsp+140h] [rbp+40h] BYREF

  hKey = 0;
  lpMem = 0;
  v44 = 0;
  v46 = 0;
  v45 = 0;
  v43 = 0;
  v42 = 0;
  memset_0(&v49, 0, sizeof(v49));
  v40 = 0;
  if ( !a4 )
    return 2147942487LL;
  if ( !a2 )
    return 2147943568LL;
  SnapshotProp = pInitializeCOM(&v40);
  if ( SnapshotProp >= 0 )
  {
    v12 = RegEnumKeyW(a2, a3, Name, 0xFFu);
    SnapshotProp = v12;
    if ( v12 )
    {
      if ( v12 <= 0 )
        goto LABEL_36;
      SnapshotProp = (unsigned __int16)v12;
LABEL_10:
      SnapshotProp |= 0x80070000;
      goto LABEL_36;
    }
    SnapshotProp = pOpenRegKeyMaxAccess(a2, Name, &hKey);
    if ( SnapshotProp )
    {
      LastError = GetLastError();
      v14 = CurrentIP();
      v15 = 0x2000000;
      if ( SnapshotProp == 2 )
        v15 = 50331648;
      v16 = ConstructPartialMsgW(
              v15,
              "Failed to open PITR snapshots key %s. Error: 0x%08X",
              (const char *)Name,
              SnapshotProp);
      WdsSetupLogMessageW(
        v16,
        0,
        L"D",
        0,
        1977,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSnapshotEnumerator::ReadNextSnapshot",
        v14,
        LastError,
        0,
        0);
      if ( SnapshotProp <= 0 )
        goto LABEL_36;
      SnapshotProp = (unsigned __int16)SnapshotProp;
      goto LABEL_10;
    }
    SnapshotProp = pReadSnapshotData(
                     hKey,
                     (const unsigned __int16 **)&lpMem,
                     &v46,
                     &v45,
                     (const unsigned __int16 **)&v44,
                     &v42);
    v17 = (unsigned __int16 *)lpMem;
    if ( SnapshotProp < 0 )
    {
      v18 = GetLastError();
      v19 = CurrentIP();
      v20 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to get snapshot data for %s. Error: 0x%08X",
              (const char *)Name,
              SnapshotProp);
      WdsSetupLogMessageW(
        v20,
        0,
        L"D",
        0,
        1991,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSnapshotEnumerator::ReadNextSnapshot",
        v19,
        v18,
        0,
        0);
      goto LABEL_34;
    }
    if ( !lpMem )
    {
      v21 = GetLastError();
      v22 = CurrentIP();
      v23 = ConstructPartialMsgW(0x2000000u, "Invalid snapshot data for %s", (const char *)Name);
      WdsSetupLogMessageW(
        v23,
        0,
        L"D",
        0,
        2000,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSnapshotEnumerator::ReadNextSnapshot",
        v22,
        v21,
        0,
        0);
      SnapshotProp = -2147024883;
      goto LABEL_36;
    }
    v24 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v47, (const unsigned __int16 *)lpMem);
    SnapshotProp = VssGetSnapshotProp(v24, &v49);
    UnBCL::String::~String((UnBCL::String *)v47);
    if ( SnapshotProp >= 0 )
    {
      v28 = 1;
      v32 = (struct UnBCL::String *)UnBCL::String::String((UnBCL::String *)v47, v17);
      SnapshotProp = VssGetSnapshotSize(v32, &v43, v33);
      UnBCL::String::~String((UnBCL::String *)v47);
      if ( SnapshotProp >= 0 )
      {
LABEL_30:
        v37 = UnBCL::Object::operator new(0x70u);
        lpMem = v37;
        if ( v37 )
          v38 = CPITRSnapshot::CPITRSnapshot(
                  (CPITRSnapshot *)v37,
                  v17,
                  v28,
                  v46,
                  v45,
                  v44,
                  v43,
                  v42,
                  v49.m_pwszSnapshotDeviceObject);
        else
          v38 = 0;
        *a4 = v38;
LABEL_34:
        if ( v17 )
        {
          ProcessHeap = GetProcessHeap();
          HeapFree(ProcessHeap, 0, v17);
        }
        goto LABEL_36;
      }
      v34 = GetLastError();
      v35 = CurrentIP();
      v36 = ConstructPartialMsgW(
              0x2000000u,
              "Failed to get snapshot size for %s. Error: 0x%08X",
              (const char *)v17,
              SnapshotProp);
      WdsSetupLogMessageW(
        v36,
        0,
        L"D",
        0,
        2032,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"CPITRSnapshotEnumerator::ReadNextSnapshot",
        v35,
        v34,
        0,
        0);
    }
    else
    {
      if ( SnapshotProp != -2147212536 )
      {
        v29 = GetLastError();
        v30 = CurrentIP();
        v31 = ConstructPartialMsgW(
                0x2000000u,
                "Failed to get snapshot properties for %s. Error: 0x%08X",
                (const char *)v17,
                SnapshotProp);
        WdsSetupLogMessageW(
          v31,
          0,
          L"D",
          0,
          2021,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSnapshotEnumerator::ReadNextSnapshot",
          v30,
          v29,
          0,
          0);
        goto LABEL_34;
      }
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
      {
        v25 = GetLastError();
        v26 = CurrentIP();
        v27 = ConstructPartialMsgW(0x3000000u, "Snapshot %s is no longer present on the system", (const char *)v17);
        WdsSetupLogMessageW(
          v27,
          0,
          L"D",
          0,
          2014,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"CPITRSnapshotEnumerator::ReadNextSnapshot",
          v26,
          v25,
          0,
          0);
      }
      v28 = 0;
    }
    SnapshotProp = 0;
    goto LABEL_30;
  }
  v9 = GetLastError();
  v10 = CurrentIP();
  v11 = ConstructPartialMsgW(
          0x2000000u,
          "%hs: Failed to initialize COM. Error: 0x%08X",
          "CPITRSnapshotEnumerator::ReadNextSnapshot",
          SnapshotProp);
  WdsSetupLogMessageW(
    v11,
    0,
    L"D",
    0,
    1956,
    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
    L"CPITRSnapshotEnumerator::ReadNextSnapshot",
    v10,
    v9,
    0,
    0);
LABEL_36:
  VssFreeSnapshotPropertiesInternal(&v49);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v40 )
    CoUninitialize();
  return (unsigned int)SnapshotProp;
}

```

## disassembly

```asm
0x1800131c4  mov     [rsp-8+arg_0], rbx
0x1800131c9  push    rbp
0x1800131ca  push    rsi
0x1800131cb  push    rdi
0x1800131cc  push    r12
0x1800131ce  push    r13
0x1800131d0  push    r14
0x1800131d2  push    r15
0x1800131d4  lea     rbp, [rsp-250h]
0x1800131dc  sub     rsp, 350h
0x1800131e3  mov     rax, cs:__security_cookie
0x1800131ea  xor     rax, rsp
0x1800131ed  mov     [rbp+280h+var_40], rax
0x1800131f4  mov     r12, r9
0x1800131f7  mov     edi, r8d
0x1800131fa  mov     rbx, rdx
0x1800131fd  xor     r13d, r13d
0x180013200  mov     [rbp+280h+hKey], r13
0x180013204  mov     [rsp+380h+lpMem], r13
0x180013209  mov     [rbp+280h+var_300], r13
0x18001320d  mov     qword ptr [rbp+280h+var_2F0.dwLowDateTime], r13
0x180013211  mov     qword ptr [rbp+280h+var_2F8.dwLowDateTime], r13
0x180013215  mov     [rsp+380h+var_308], r13
0x18001321a  mov     [rsp+380h+var_310], r13
0x18001321f  xor     edx, edx; Val
0x180013221  mov     r8d, 80h; Size
0x180013227  lea     rcx, [rbp+280h+var_2C0]; void *
0x18001322b  call    memset_0
0x180013230  mov     [rsp+380h+var_320], r13d
0x180013235  test    r12, r12
0x180013238  jnz     short loc_180013244
0x18001323a  mov     eax, 80070057h
0x18001323f  jmp     loc_180013742
0x180013244  test    rbx, rbx
0x180013247  jnz     short loc_180013253
0x180013249  mov     eax, 80070490h
0x18001324e  jmp     loc_180013742
0x180013253  lea     rcx, [rsp+380h+var_320]; int *
0x180013258  call    ?pInitializeCOM@@YAJAEAH@Z; pInitializeCOM(int &)
0x18001325d  mov     esi, eax
0x18001325f  test    eax, eax
0x180013261  jns     short loc_1800132DC
0x180013263  call    cs:__imp_GetLastError
0x180013269  mov     edi, eax
0x18001326b  call    cs:__imp_CurrentIP
0x180013271  mov     rbx, rax
0x180013274  mov     r9d, esi
0x180013277  lea     r8, aCpitrsnapshote; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x18001327e  lea     rdx, aHsFailedToInit; "%hs: Failed to initialize COM. Error: 0"...
0x180013285  mov     ecx, 2000000h; unsigned int
0x18001328a  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001328f  mov     [rsp+380h+var_330], r13d
0x180013294  mov     [rsp+380h+var_338], r13
0x180013299  mov     dword ptr [rsp+380h+var_340], edi
0x18001329d  mov     [rsp+380h+var_348], rbx
0x1800132a2  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x1800132a9  mov     [rsp+380h+var_350], rcx
0x1800132ae  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800132b5  mov     [rsp+380h+var_358], rcx
0x1800132ba  mov     [rsp+380h+var_360.dwLowDateTime], 7A4h
0x1800132c2  xor     r9d, r9d
0x1800132c5  lea     r8, aD; "D"
0x1800132cc  xor     edx, edx
0x1800132ce  mov     rcx, rax
0x1800132d1  call    cs:__imp_WdsSetupLogMessageW
0x1800132d7  jmp     loc_180013716
0x1800132dc  mov     r9d, 0FFh; cchName
0x1800132e2  lea     r8, [rbp+280h+Name]; lpName
0x1800132e6  mov     edx, edi; dwIndex
0x1800132e8  mov     rcx, rbx; hKey
0x1800132eb  call    cs:__imp_RegEnumKeyW
0x1800132f1  mov     esi, eax
0x1800132f3  test    eax, eax
0x1800132f5  jz      short loc_18001330B
0x1800132f7  jle     loc_180013716
0x1800132fd  movzx   esi, ax
0x180013300  or      esi, 80070000h
0x180013306  jmp     loc_180013716
0x18001330b  lea     r8, [rbp+280h+hKey]; phkResult
0x18001330f  lea     rdx, [rbp+280h+Name]; lpSubKey
0x180013313  mov     rcx, rbx; hKey
0x180013316  call    ?pOpenRegKeyMaxAccess@@YAKPEAUHKEY__@@PEBGPEAPEAU1@@Z; pOpenRegKeyMaxAccess(HKEY__ *,ushort const *,HKEY__ * *)
0x18001331b  mov     esi, eax
0x18001331d  test    eax, eax
0x18001331f  jz      loc_1800133B1
0x180013325  call    cs:__imp_GetLastError
0x18001332b  mov     edi, eax
0x18001332d  call    cs:__imp_CurrentIP
0x180013333  mov     rbx, rax
0x180013336  mov     ecx, 2000000h
0x18001333b  mov     eax, 3000000h
0x180013340  cmp     esi, 2
0x180013343  cmovz   ecx, eax; unsigned int
0x180013346  mov     r9d, esi
0x180013349  lea     r8, [rbp+280h+Name]
0x18001334d  lea     rdx, aFailedToOpenPi_0; "Failed to open PITR snapshots key %s. E"...
0x180013354  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180013359  mov     [rsp+380h+var_330], r13d
0x18001335e  mov     [rsp+380h+var_338], r13
0x180013363  mov     dword ptr [rsp+380h+var_340], edi
0x180013367  mov     [rsp+380h+var_348], rbx
0x18001336c  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x180013373  mov     [rsp+380h+var_350], rcx
0x180013378  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001337f  mov     [rsp+380h+var_358], rcx
0x180013384  mov     [rsp+380h+var_360.dwLowDateTime], 7B9h
0x18001338c  xor     r9d, r9d
0x18001338f  lea     r8, aD; "D"
0x180013396  xor     edx, edx
0x180013398  mov     rcx, rax
0x18001339b  call    cs:__imp_WdsSetupLogMessageW
0x1800133a1  test    esi, esi
0x1800133a3  jle     loc_180013716
0x1800133a9  movzx   esi, si
0x1800133ac  jmp     loc_180013300
0x1800133b1  lea     rax, [rsp+380h+var_310]
0x1800133b6  mov     [rsp+380h+var_358], rax; struct PITR::_VERSION_DATA **
0x1800133bb  lea     rax, [rbp+280h+var_300]
0x1800133bf  mov     qword ptr [rsp+380h+var_360.dwLowDateTime], rax; unsigned __int16 **
0x1800133c4  lea     r9, [rbp+280h+var_2F8]; struct _FILETIME *
0x1800133c8  lea     r8, [rbp+280h+var_2F0]; struct _FILETIME *
0x1800133cc  lea     rdx, [rsp+380h+lpMem]; unsigned __int16 **
0x1800133d1  mov     rcx, [rbp+280h+hKey]; hKey
0x1800133d5  call    ?pReadSnapshotData@@YAJPEAUHKEY__@@PEAPEBGPEAU_FILETIME@@21PEAPEAU_VERSION_DATA@PITR@@@Z; pReadSnapshotData(HKEY__ *,ushort const * *,_FILETIME *,_FILETIME *,ushort const * *,PITR::_VERSION_DATA * *)
0x1800133da  mov     esi, eax
0x1800133dc  mov     r14, [rsp+380h+lpMem]
0x1800133e1  test    eax, eax
0x1800133e3  jns     short loc_18001345B
0x1800133e5  call    cs:__imp_GetLastError
0x1800133eb  mov     edi, eax
0x1800133ed  call    cs:__imp_CurrentIP
0x1800133f3  mov     rbx, rax
0x1800133f6  mov     r9d, esi
0x1800133f9  lea     r8, [rbp+280h+Name]
0x1800133fd  lea     rdx, aFailedToGetSna_0; "Failed to get snapshot data for %s. Err"...
0x180013404  mov     ecx, 2000000h; unsigned int
0x180013409  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18001340e  mov     [rsp+380h+var_330], r13d
0x180013413  mov     [rsp+380h+var_338], r13
0x180013418  mov     dword ptr [rsp+380h+var_340], edi
0x18001341c  mov     [rsp+380h+var_348], rbx
0x180013421  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x180013428  mov     [rsp+380h+var_350], rcx
0x18001342d  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180013434  mov     [rsp+380h+var_358], rcx
0x180013439  mov     [rsp+380h+var_360.dwLowDateTime], 7C7h
0x180013441  xor     r9d, r9d
0x180013444  lea     r8, aD; "D"
0x18001344b  xor     edx, edx
0x18001344d  mov     rcx, rax
0x180013450  call    cs:__imp_WdsSetupLogMessageW
0x180013456  jmp     loc_1800136FD
0x18001345b  test    r14, r14
0x18001345e  jnz     short loc_1800134D8
0x180013460  call    cs:__imp_GetLastError
0x180013466  mov     edi, eax
0x180013468  call    cs:__imp_CurrentIP
0x18001346e  mov     rbx, rax
0x180013471  lea     r8, [rbp+280h+Name]
0x180013475  lea     rdx, aInvalidSnapsho; "Invalid snapshot data for %s"
0x18001347c  mov     ecx, 2000000h; unsigned int
0x180013481  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180013486  mov     [rsp+380h+var_330], r13d
0x18001348b  mov     [rsp+380h+var_338], r13
0x180013490  mov     dword ptr [rsp+380h+var_340], edi
0x180013494  mov     [rsp+380h+var_348], rbx
0x180013499  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x1800134a0  mov     [rsp+380h+var_350], rcx
0x1800134a5  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800134ac  mov     [rsp+380h+var_358], rcx
0x1800134b1  mov     [rsp+380h+var_360.dwLowDateTime], 7D0h
0x1800134b9  xor     r9d, r9d
0x1800134bc  lea     r8, aD; "D"
0x1800134c3  xor     edx, edx
0x1800134c5  mov     rcx, rax
0x1800134c8  call    cs:__imp_WdsSetupLogMessageW
0x1800134ce  mov     esi, 8007000Dh
0x1800134d3  jmp     loc_180013716
0x1800134d8  mov     rdx, r14
0x1800134db  lea     rcx, [rbp+280h+var_2E8]
0x1800134df  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x1800134e5  nop
0x1800134e6  lea     rdx, [rbp+280h+var_2C0]; struct _VSS_SNAPSHOT_PROP *
0x1800134ea  mov     rcx, rax; struct UnBCL::String *
0x1800134ed  call    ?VssGetSnapshotProp@@YAJPEAVString@UnBCL@@PEAU_VSS_SNAPSHOT_PROP@@@Z; VssGetSnapshotProp(UnBCL::String *,_VSS_SNAPSHOT_PROP *)
0x1800134f2  mov     esi, eax
0x1800134f4  lea     rcx, [rbp+280h+var_2E8]
0x1800134f8  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x1800134fe  test    esi, esi
0x180013500  jns     loc_1800135F7
0x180013506  cmp     esi, 80042308h
0x18001350c  jnz     loc_180013597
0x180013512  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180013519  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x18001351e  test    al, al
0x180013520  jnz     short loc_18001358F
0x180013522  call    cs:__imp_GetLastError
0x180013528  mov     edi, eax
0x18001352a  call    cs:__imp_CurrentIP
0x180013530  mov     rbx, rax
0x180013533  mov     r8, r14
0x180013536  lea     rdx, aSnapshotSIsNoL; "Snapshot %s is no longer present on the"...
0x18001353d  mov     ecx, 3000000h; unsigned int
0x180013542  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180013547  mov     [rsp+380h+var_330], r13d
0x18001354c  mov     [rsp+380h+var_338], r13
0x180013551  mov     dword ptr [rsp+380h+var_340], edi
0x180013555  mov     [rsp+380h+var_348], rbx
0x18001355a  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x180013561  mov     [rsp+380h+var_350], rcx
0x180013566  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18001356d  mov     [rsp+380h+var_358], rcx
0x180013572  mov     [rsp+380h+var_360.dwLowDateTime], 7DEh
0x18001357a  xor     r9d, r9d
0x18001357d  lea     r8, aD; "D"
0x180013584  xor     edx, edx
0x180013586  mov     rcx, rax
0x180013589  call    cs:__imp_WdsSetupLogMessageW
0x18001358f  mov     r15d, r13d
0x180013592  jmp     loc_180013698
0x180013597  call    cs:__imp_GetLastError
0x18001359d  mov     edi, eax
0x18001359f  call    cs:__imp_CurrentIP
0x1800135a5  mov     rbx, rax
0x1800135a8  mov     r9d, esi
0x1800135ab  mov     r8, r14
0x1800135ae  lea     rdx, aFailedToGetSna_2; "Failed to get snapshot properties for %"...
0x1800135b5  mov     ecx, 2000000h; unsigned int
0x1800135ba  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800135bf  mov     [rsp+380h+var_330], r13d
0x1800135c4  mov     [rsp+380h+var_338], r13
0x1800135c9  mov     dword ptr [rsp+380h+var_340], edi
0x1800135cd  mov     [rsp+380h+var_348], rbx
0x1800135d2  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x1800135d9  mov     [rsp+380h+var_350], rcx
0x1800135de  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800135e5  mov     [rsp+380h+var_358], rcx
0x1800135ea  mov     [rsp+380h+var_360.dwLowDateTime], 7E5h
0x1800135f2  jmp     loc_180013441
0x1800135f7  mov     r15d, 1
0x1800135fd  mov     rdx, r14
0x180013600  lea     rcx, [rbp+280h+var_2E8]
0x180013604  call    cs:__imp_??0String@UnBCL@@QEAA@PEBG@Z; UnBCL::String::String(ushort const *)
0x18001360a  nop
0x18001360b  lea     rdx, [rsp+380h+var_308]; __int64 *
0x180013610  mov     rcx, rax; struct UnBCL::String *
0x180013613  call    ?VssGetSnapshotSize@@YAJPEAVString@UnBCL@@PEA_J1@Z; VssGetSnapshotSize(UnBCL::String *,__int64 *,__int64 *)
0x180013618  mov     esi, eax
0x18001361a  lea     rcx, [rbp+280h+var_2E8]
0x18001361e  call    cs:__imp_??1String@UnBCL@@UEAA@XZ; UnBCL::String::~String(void)
0x180013624  test    esi, esi
0x180013626  jns     short loc_18001369B
0x180013628  call    cs:__imp_GetLastError
0x18001362e  mov     edi, eax
0x180013630  call    cs:__imp_CurrentIP
0x180013636  mov     rbx, rax
0x180013639  mov     r9d, esi
0x18001363c  mov     r8, r14
0x18001363f  lea     rdx, aFailedToGetSna; "Failed to get snapshot size for %s. Err"...
0x180013646  mov     ecx, 2000000h; unsigned int
0x18001364b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180013650  mov     [rsp+380h+var_330], r13d
0x180013655  mov     [rsp+380h+var_338], r13
0x18001365a  mov     dword ptr [rsp+380h+var_340], edi
0x18001365e  mov     [rsp+380h+var_348], rbx
0x180013663  lea     rcx, aCpitrsnapshote_0; "CPITRSnapshotEnumerator::ReadNextSnapsh"...
0x18001366a  mov     [rsp+380h+var_350], rcx
0x18001366f  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180013676  mov     [rsp+380h+var_358], rcx
0x18001367b  mov     [rsp+380h+var_360.dwLowDateTime], 7F0h
0x180013683  xor     r9d, r9d
0x180013686  lea     r8, aD; "D"
0x18001368d  xor     edx, edx
0x18001368f  mov     rcx, rax
0x180013692  call    cs:__imp_WdsSetupLogMessageW
0x180013698  mov     esi, r13d
0x18001369b  mov     ecx, 70h ; 'p'
0x1800136a0  call    cs:__imp_??2Object@UnBCL@@SAPEAX_K@Z; UnBCL::Object::operator new(unsigned __int64)
0x1800136a6  mov     r10, rax
0x1800136a9  mov     [rsp+380h+lpMem], rax
0x1800136ae  test    rax, rax
0x1800136b1  jz      short loc_1800136F6
0x1800136b3  mov     rcx, [rbp+280h+var_2C0.m_pwszSnapshotDeviceObject]
0x1800136b7  mov     [rsp+380h+var_340], rcx; unsigned __int16 *
0x1800136bc  mov     rcx, [rsp+380h+var_310]
0x1800136c1  mov     [rsp+380h+var_348], rcx; struct PITR::_VERSION_DATA *
0x1800136c6  mov     rcx, [rsp+380h+var_308]
0x1800136cb  mov     [rsp+380h+var_350], rcx; __int64
0x1800136d0  mov     rcx, [rbp+280h+var_300]
0x1800136d4  mov     [rsp+380h+var_358], rcx; unsigned __int16 *
0x1800136d9  mov     rax, qword ptr [rbp+280h+var_2F8.dwLowDateTime]
0x1800136dd  mov     qword ptr [rsp+380h+var_360.dwLowDateTime], rax; struct _FILETIME
0x1800136e2  mov     r9, qword ptr [rbp+280h+var_2F0.dwLowDateTime]; struct _FILETIME
0x1800136e6  mov     r8d, r15d; int
0x1800136e9  mov     rdx, r14; unsigned __int16 *
0x1800136ec  mov     rcx, r10; this
0x1800136ef  call    ??0CPITRSnapshot@@QEAA@PEBGHU_FILETIME@@10_JPEAU_VERSION_DATA@PITR@@0@Z; CPITRSnapshot::CPITRSnapshot(ushort const *,int,_FILETIME,_FILETIME,ushort const *,__int64,PITR::_VERSION_DATA *,ushort const *)
0x1800136f4  jmp     short loc_1800136F9
0x1800136f6  mov     rax, r13
0x1800136f9  mov     [r12], rax
  ... truncated ...
```
