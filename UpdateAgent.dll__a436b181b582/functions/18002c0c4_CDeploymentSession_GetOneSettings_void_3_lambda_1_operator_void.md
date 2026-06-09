# `CDeploymentSession::GetOneSettings(void)'::`3'::_lambda_1_::operator()(void)

- ea: `0x18002c0c4`
- end: `0x18002cffb`
- name: `??R_lambda_1_@?2??GetOneSettings@CDeploymentSession@@QEAAJXZ@QEBAJXZ`
- size: `3895`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800621cc`

## callees

- `0x180006a18`
- `0x180008fbc`
- `0x18000afc8`
- `0x180012770`
- `0x180013998`
- `0x180023b20`
- `0x18002c0c4`
- `0x180034270`
- `0x18003557c`
- `0x180039f90`
- `0x18003c418`
- `0x1800408d0`
- `0x180040e80`
- `0x180045cd4`
- `0x18005e274`
- `0x18005f7f8`
- `0x180060fa8`
- `0x1800627f8`
- `0x180067684`
- `0x180077664`
- `0x180078b9c`
- `0x180090e44`
- `0x1800915f4`
- `0x1800948f8`
- `0x18009692c`
- `0x1800970bc`
- `0x18009d3c4`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c3d3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c3d3`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002c512`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18002c512`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002c4b2`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18002c4b2`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18002c497`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18002c497`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c316`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c316`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c32b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c32b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c4cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c52a`

## string_xrefs

- `0x18002c16e`: `Skipping GetOneSettings(). Session was created with OptionalSessionFlagsSuppressOneSettings flag set.`
- `0x18002c20d`: `OneSettingsPath`
- `0x18002c278`: `UAOneSettings.dll`
- `0x18002c50b`: `CreateOneSettingsHelperEx`
- `0x18002c8ac`: `USESUPPLEMENTALCOMPDB`
- `0x18002c91a`: `BACKGROUNDINSTALLCOUNT`
- `0x18002c951`: `CORRUPTIONDELETECOUNT`
- `0x18002c9f6`: `FORCERECREATECONTAINERBASEIMAGE`
- `0x18002cbc2`: `GetOneSettings: Wrote max log file size to registry.`
- `0x18002cc23`: `GetOneSettings: Cleared max log file size from registry.`
- `0x18002cd3c`: `GetOneSettings: Could not get file paths from list [0x%X]: [%s]`

## pseudocode

```c
__int64 __fastcall `CDeploymentSession::GetOneSettings'::`3'::_lambda_1_::operator()(__int64 *a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  const wchar_t *v4; // r8
  __int64 v5; // rcx
  int PackageCategoriesFromString; // eax
  signed int FilePathsFromString; // ebx
  __int64 v8; // rcx
  __int64 updated; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned int *v12; // rdx
  __int64 *v13; // rsi
  __int64 v14; // rbx
  HANDLE ProcessHeap; // rax
  void *v16; // rsi
  int Internal; // eax
  __int64 v18; // rdx
  BOOL *v19; // rbx
  DWORD FileAttributesW; // eax
  BOOL v21; // eax
  __int64 v22; // rcx
  __int64 v23; // rcx
  HMODULE Library; // rbx
  HMODULE *v25; // rsi
  HMODULE v26; // rcx
  signed int v27; // eax
  __int64 v28; // rcx
  FARPROC *v29; // rbx
  signed int LastError; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // rcx
  const wchar_t *v34; // r9
  int v35; // ecx
  void *v36; // rsi
  int StringCch; // eax
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  __int64 v42; // rcx
  struct CWatsonHelper *Instance; // r14
  char *v44; // r15
  char *v45; // rsi
  __int64 v46; // rcx
  int *v47; // rax
  __int64 v48; // rdx
  __int64 v49; // r14
  __int64 v50; // r15
  __int64 v51; // rsi
  unsigned int v52; // esi
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rax
  int *v56; // rsi
  int *v57; // r14
  int v58; // r8d
  __int64 v59; // rcx
  _DWORD *v60; // rdx
  __int64 v61; // rcx
  struct CWatsonHelper *v62; // rsi
  void *v63; // rcx
  size_t v64; // r8
  __int64 v65; // r9
  int *v66; // rax
  __int64 v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rcx
  __int64 v70; // rsi
  __int64 v71; // rdx
  struct CWatsonHelper *v72; // r14
  __int64 v73; // rcx
  const char *v74; // r9
  __int64 result; // rax
  int v76; // [rsp+20h] [rbp-78h]
  signed int v77; // [rsp+28h] [rbp-70h]
  _QWORD v78[2]; // [rsp+30h] [rbp-68h] BYREF
  _QWORD v79[11]; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v79[2] = -2;
  try
  {
    *(_DWORD *)(*a1 + 288) = 0;
    *(_DWORD *)(*a1 + 352) = 3;
    *(_DWORD *)(*a1 + 356) = 3;
    *(_DWORD *)(*a1 + 360) = 3;
    *(_DWORD *)(*a1 + 364) = 24576;
    *(_DWORD *)(*a1 + 368) = 2;
    *(_BYTE *)(*a1 + 328) = 0;
    *(_DWORD *)(*a1 + 300) = 1;
    *(_DWORD *)(*a1 + 304) = 1;
    v2 = *a1;
    if ( (*(_BYTE *)(v2 + 372) & 2) != 0 )
    {
      v3 = *(_QWORD *)(v2 + 600);
      if ( v3 )
      {
        v4 = L"Skipping GetOneSettings(). Session was created with OptionalSessionFlagsSuppressOneSettings flag set.";
LABEL_5:
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v3, 2, v4);
      }
      goto LABEL_187;
    }
    CArray<enum ActionList::PackageCategory,enum ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::SetSize(
      v2 + 384,
      0);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::GetImpl'::`2'::impl) )
    {
      PackageCategoriesFromString = CDeploymentSession::GetPackageCategoriesFromString(*a1, L"LCU;GDR", *a1 + 384);
      FilePathsFromString = PackageCategoriesFromString;
      if ( PackageCategoriesFromString < 0 )
      {
        v8 = *(_QWORD *)(*a1 + 600);
        if ( v8 )
        {
          updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                                    v8,
                                    4,
                                    L"%s(%d): Result = 0x%X",
                                    L"CDeploymentSession::GetOneSettings::<lambda_1>::operator ()",
                                    6208,
                                    PackageCategoriesFromString);
          goto LABEL_11;
        }
        goto LABEL_9;
      }
    }
    if ( (int)CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(v5, L"System\\Setup\\MoSetup", L"OneSettingsPath", a1[1]) >= 0 )
    {
      FilePathsFromString = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(a1[2], a1[1]);
      if ( FilePathsFromString < 0 )
      {
        v11 = *(_QWORD *)(*a1 + 600);
        if ( v11 )
        {
          v77 = FilePathsFromString;
          v76 = 6218;
          goto LABEL_18;
        }
LABEL_9:
        updated = 0;
        goto LABEL_13;
      }
    }
    FilePathsFromString = CMiscHelpersT<CEmptyType>::CombinePath(*(_QWORD *)(*a1 + 496), L"UAOneSettings.dll", 0, a1[3]);
    if ( FilePathsFromString < 0 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( v11 )
      {
        v77 = FilePathsFromString;
        v76 = 6223;
        goto LABEL_18;
      }
      goto LABEL_9;
    }
    FilePathsFromString = CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(a1[2], a1[3]);
    if ( FilePathsFromString < 0 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( v11 )
      {
        v77 = FilePathsFromString;
        v76 = 6224;
        goto LABEL_18;
      }
      goto LABEL_9;
    }
    *(_QWORD *)a1[4] = 0;
    for ( *(_DWORD *)a1[5] = 0; ; ++*(_DWORD *)a1[5] )
    {
      v12 = (unsigned int *)a1[5];
      if ( *v12 >= *(_DWORD *)(a1[2] + 4) )
        break;
      v13 = (__int64 *)a1[6];
      v14 = *v13;
      if ( *v13 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, (LPVOID)(v14 - 4));
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        *v13 = 0;
        v12 = (unsigned int *)a1[5];
      }
      v16 = *(void **)(*(_QWORD *)(a1[2] + 8) + 8LL * (int)*v12);
      if ( !v16 )
      {
        v16 = 0;
LABEL_32:
        Internal = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v16);
        FilePathsFromString = Internal;
        if ( Internal >= 0 )
          goto LABEL_34;
        goto LABEL_33;
      }
      LODWORD(v78[0]) = 0;
      Internal = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v16, v78);
      FilePathsFromString = Internal;
      if ( Internal >= 0 )
        goto LABEL_32;
LABEL_33:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal, v18);
LABEL_34:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)FilePathsFromString);
      if ( FilePathsFromString < 0 )
      {
        v11 = *(_QWORD *)(*a1 + 600);
        if ( !v11 )
          goto LABEL_9;
        v77 = FilePathsFromString;
        v76 = 6232;
        goto LABEL_18;
      }
      v19 = (BOOL *)a1[7];
      FileAttributesW = GetFileAttributesW(*(LPCWSTR *)a1[6]);
      v21 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
      *v19 = v21;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      FilePathsFromString = 0;
      if ( *(_DWORD *)a1[7] )
      {
        v22 = *(_QWORD *)(*a1 + 600);
        if ( v22 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v22,
            2,
            L"GetOneSettings: Verifying signature of [%s]...",
            *(_QWORD *)a1[6]);
        FilePathsFromString = CGlobalMiscUtilsT<CEmptyType>::VerifySelfSignedImageFile(*(LPCWSTR *)a1[6]);
        v23 = *(_QWORD *)(*a1 + 600);
        if ( FilePathsFromString >= 0 )
        {
          if ( v23 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v23, 2, L"GetOneSettings: Loading [%s]...", *(_QWORD *)a1[6]);
          Library = LoadLibraryExW(*(LPCWSTR *)a1[6], 0, 0);
          v25 = (HMODULE *)a1[8];
          if ( *v25 )
            FreeLibrary(*v25);
          *v25 = Library;
          v26 = *(HMODULE *)a1[8];
          if ( v26 )
          {
            v29 = (FARPROC *)a1[4];
            *v29 = GetProcAddress(v26, "CreateOneSettingsHelperEx");
            if ( *(_QWORD *)a1[4] )
            {
              v32 = *(_QWORD *)(*a1 + 600);
              if ( v32 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v32,
                  2,
                  L"GetOneSettings: OneSettings module [%s] verified.",
                  *(_QWORD *)a1[6]);
              goto LABEL_63;
            }
            LastError = GetLastError();
            FilePathsFromString = LastError;
            if ( LastError > 0 )
              FilePathsFromString = (unsigned __int16)LastError | 0x80070000;
            v31 = *(_QWORD *)(*a1 + 600);
            if ( v31 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v31,
                2,
                L"GetOneSettings: Entrypoint not found. [0x%X]",
                (unsigned int)FilePathsFromString);
          }
          else
          {
            v27 = GetLastError();
            FilePathsFromString = v27;
            if ( v27 > 0 )
              FilePathsFromString = (unsigned __int16)v27 | 0x80070000;
            v28 = *(_QWORD *)(*a1 + 600);
            if ( v28 )
              CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                v28,
                2,
                L"GetOneSettings: Module failed to load. [0x%X]",
                (unsigned int)FilePathsFromString);
          }
        }
        else if ( v23 )
        {
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
            v23,
            2,
            L"GetOneSettings: Module not signed. [0x%X]",
            (unsigned int)FilePathsFromString);
        }
      }
    }
    if ( FilePathsFromString < 0 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( !v11 )
        goto LABEL_9;
      v77 = FilePathsFromString;
      v76 = 6271;
      goto LABEL_18;
    }
LABEL_63:
    if ( !*(_QWORD *)a1[4] )
    {
      v3 = *(_QWORD *)(*a1 + 600);
      if ( !v3 )
        goto LABEL_187;
      v4 = L"GetOneSettings: No OneSettings modules found.";
      goto LABEL_5;
    }
    *(_DWORD *)a1[9] = 1;
    v33 = *(_QWORD *)(*a1 + 600);
    if ( v33 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v33, 2, L"GetOneSettings: Creating OneSettings helper...");
    FilePathsFromString = (*(__int64 (__fastcall **)(__int64, __int64))a1[4])(3, a1[10]);
    v11 = *(_QWORD *)(*a1 + 600);
    if ( FilePathsFromString < 0 )
    {
      if ( !v11 )
        goto LABEL_9;
      v77 = FilePathsFromString;
      v76 = 6282;
      goto LABEL_18;
    }
    if ( v11 )
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v11, 2, L"GetOneSettings: Initializing settings...");
    *(_DWORD *)a1[11] = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)a1[10] + 72LL))(
                          *(_QWORD *)a1[10],
                          *(unsigned int *)(*a1 + 456),
                          *(_QWORD *)(*a1 + 600),
                          a1[12]);
    FilePathsFromString = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)a1[10] + 56LL))(
                            *(_QWORD *)a1[10],
                            a1[13]);
    if ( (int)(FilePathsFromString + 0x80000000) >= 0 && FilePathsFromString != -2147483638 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( !v11 )
        goto LABEL_9;
      v77 = FilePathsFromString;
      v76 = 6288;
      goto LABEL_18;
    }
    FilePathsFromString = *(_DWORD *)a1[11];
    v11 = *(_QWORD *)(*a1 + 600);
    if ( FilePathsFromString < 0 )
    {
      if ( !v11 )
        goto LABEL_9;
      v77 = *(_DWORD *)a1[11];
      v76 = 6289;
      goto LABEL_18;
    }
    if ( v11 )
    {
      v34 = L"Yes";
      if ( !*(_DWORD *)a1[12] )
        v34 = L"No";
      CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v11, 2, L"GetOneSettings: Initialized -> [%s]", v34);
    }
    if ( !*(_DWORD *)a1[12] )
      goto LABEL_188;
    FilePathsFromString = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)a1[10] + 48LL))(
                            *(_QWORD *)a1[10],
                            a1[14]);
    if ( FilePathsFromString < 0 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( !v11 )
        goto LABEL_9;
      v77 = FilePathsFromString;
      v76 = 6298;
      goto LABEL_18;
    }
    FilePathsFromString = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)a1[10] + 64LL))(
                            *(_QWORD *)a1[10],
                            a1[15]);
    if ( FilePathsFromString < 0 )
    {
      v11 = *(_QWORD *)(*a1 + 600);
      if ( !v11 )
        goto LABEL_9;
      v77 = FilePathsFromString;
      v76 = 6299;
      goto LABEL_18;
    }
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"FORCECANONICALPACKAGES",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 288) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"SUPPRESSWINRESERVICING",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 292) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"SUPPRESSSETUPSERVICING",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 296) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"USESERVICINGFORUPGRADE",
           a1[16]) >= 0 )
      *(_BYTE *)(*a1 + 328) = *(_DWORD *)a1[16] != 0;
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"USESUPPLEMENTALCOMPDB",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 300) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"UNUSEDLPTRIMMINGALLOWED",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 304) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
           *(_QWORD *)a1[10],
           L"BACKGROUNDINSTALLCOUNT",
           a1[17]) >= 0 )
      *(_DWORD *)(*a1 + 352) = *(_DWORD *)a1[17];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
           *(_QWORD *)a1[10],
           L"CORRUPTIONDELETECOUNT",
           a1[17]) >= 0 )
      *(_DWORD *)(*a1 + 356) = *(_DWORD *)a1[17];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
           *(_QWORD *)a1[10],
           L"EXPRESSDOWNLOADCOUNT",
           a1[17]) >= 0 )
      *(_DWORD *)(*a1 + 360) = *(_DWORD *)a1[17];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
           *(_QWORD *)a1[10],
           L"EXPRESSFREEDISKSPACEMB",
           a1[17]) >= 0 )
      *(_DWORD *)(*a1 + 364) = *(_DWORD *)a1[17];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 32LL))(
           *(_QWORD *)a1[10],
           L"FORCERECREATECONTAINERBASEIMAGE",
           a1[16]) >= 0 )
      *(_DWORD *)(*a1 + 588) = *(_DWORD *)a1[16];
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
           *(_QWORD *)a1[10],
           L"EXPRESSPRIORITYLEVEL",
           a1[17]) >= 0 )
    {
      v35 = *(_DWORD *)a1[17];
      if ( (unsigned int)(v35 - 1) <= 4 )
        *(_DWORD *)(*a1 + 368) = v35;
    }
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 24LL))(
           *(_QWORD *)a1[10],
           L"OPTIONALPKGCATEGORIES",
           a1[18]) >= 0
      && (int)CDeploymentSession::GetPackageCategoriesFromString(*a1, *(void **)a1[18], a1[19]) >= 0 )
    {
      CArray<enum ActionList::PackageCategory,enum ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::Swap(
        *a1 + 384,
        a1[19]);
    }
    if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 24LL))(
           *(_QWORD *)a1[10],
           L"ERRORSFORCINGCANONICAL",
           a1[20]) < 0 )
      goto LABEL_133;
    v36 = *(void **)a1[20];
    if ( !v36 )
    {
      v36 = 0;
      goto LABEL_126;
    }
    LODWORD(v78[0]) = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(v36, v78);
    FilePathsFromString = StringCch;
    if ( StringCch < 0 )
    {
LABEL_127:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch, v38);
    }
    else
    {
LABEL_126:
      StringCch = CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(v36);
      FilePathsFromString = StringCch;
      if ( StringCch < 0 )
        goto LABEL_127;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)FilePathsFromString);
    if ( FilePathsFromString >= 0 )
    {
LABEL_133:
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 40LL))(
             *(_QWORD *)a1[10],
             L"UAMAXLOGFILESIZE",
             a1[17]) < 0
        || (int)CRegUtilT<unsigned long,CRegType,0,1>::CreateOrOpenKey(v39, L"SYSTEM\\Setup\\MoSetup") < 0
        || (int)CRegUtilT<unsigned long,CRegType,0,1>::SetValue(
                  v39,
                  L"SYSTEM\\Setup\\MoSetup",
                  L"UAMaxLogFileSize",
                  *(unsigned int *)a1[17]) < 0 )
      {
        if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::ValueExists(
                    v39,
                    L"SYSTEM\\Setup\\MoSetup",
                    L"UAMaxLogFileSize",
                    a1[21]) >= 0 )
        {
          if ( *(_DWORD *)a1[21] )
          {
            if ( (int)CRegUtilT<CEmptyType,CRegType,0,1>::DeleteValueIfExists(
                        v41,
                        L"SYSTEM\\Setup\\MoSetup",
                        L"UAMaxLogFileSize") >= 0 )
            {
              v42 = *(_QWORD *)(*a1 + 600);
              if ( v42 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v42,
                  2,
                  L"GetOneSettings: Cleared max log file size from registry.");
            }
          }
        }
      }
      else
      {
        v40 = *(_QWORD *)(*a1 + 600);
        if ( v40 )
          CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(v40, 2, L"GetOneSettings: Wrote max log file size to registry.");
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 24LL))(
             *(_QWORD *)a1[10],
             L"UAWATSONFILES",
             a1[22]) >= 0 )
      {
        FilePathsFromString = CDeploymentSession::GetFilePathsFromString(*a1, *(_QWORD *)a1[22], a1[23]);
        if ( FilePathsFromString < 0 )
        {
          v53 = *(_QWORD *)(*a1 + 600);
          if ( v53 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v53,
              3,
              L"GetOneSettings: Could not get file paths from list [0x%X]: [%s]",
              (unsigned int)FilePathsFromString,
              *(_QWORD *)a1[22]);
          FilePathsFromString = 0;
        }
        else if ( *(int *)(a1[23] + 4) > 0 )
        {
          Instance = CWatsonHelper::GetInstance();
          v44 = (char *)*((_QWORD *)Instance + 6);
          v45 = (char *)*((_QWORD *)Instance + 5);
          if ( v45 != v44 )
          {
            do
            {
              std::wstring::~wstring(v45);
              v45 += 32;
            }
            while ( v45 != v44 );
            *((_QWORD *)Instance + 6) = *((_QWORD *)Instance + 5);
          }
          for ( *(_DWORD *)a1[5] = 0; ; ++*(_DWORD *)a1[5] )
          {
            v46 = a1[23];
            v47 = (int *)a1[5];
            v48 = *v47;
            if ( (unsigned int)v48 >= *(_DWORD *)(v46 + 4) )
              break;
            _mm_lfence();
            v49 = *(_QWORD *)(v46 + 8);
            v50 = *v47;
            v51 = *(_QWORD *)(v49 + 8 * v48);
            if ( v51 )
              v52 = *(_DWORD *)(v51 - 4);
            else
              v52 = 0;
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            v79[0] = *(_QWORD *)(v49 + 8 * v50);
            v79[1] = v52;
            CWatsonHelper::AddFile(v79);
          }
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 24LL))(
             *(_QWORD *)a1[10],
             L"UAWATSONNONERRORS",
             a1[24]) >= 0 )
      {
        if ( (int)CDeploymentSession::GetNumbersFromString(*a1, *(_QWORD *)a1[24], a1[25]) < 0 )
        {
          v61 = *(_QWORD *)(*a1 + 600);
          if ( v61 )
            CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
              v61,
              3,
              L"GetOneSettings: Could not get error codes from list [0x%X]: [%s]",
              (unsigned int)FilePathsFromString,
              *(_QWORD *)a1[24]);
        }
        else if ( *(int *)(a1[25] + 4) > 0 )
        {
          v54 = *(_QWORD *)(*a1 + 672);
          if ( v54 != *(_QWORD *)(*a1 + 680) )
            *(_QWORD *)(*a1 + 680) = v54;
          v55 = a1[25];
          v56 = *(int **)(v55 + 8);
          v57 = &v56[*(int *)(v55 + 4)];
          while ( v56 != v57 )
          {
            v58 = *v56;
            LODWORD(v78[0]) = *v56;
            v59 = *a1 + 672;
            v60 = *(_DWORD **)(*a1 + 680);
            if ( v60 == *(_DWORD **)(*a1 + 688) )
            {
              std::vector<long>::_Emplace_reallocate<long const &>(v59, v60, v78);
            }
            else
            {
              *v60 = v58;
              *(_QWORD *)(v59 + 8) += 4LL;
            }
            ++v56;
          }
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, __int64))(**(_QWORD **)a1[10] + 24LL))(
             *(_QWORD *)a1[10],
             L"UAWATSONMUTEPARAMS",
             a1[26]) < 0 )
        goto LABEL_188;
      FilePathsFromString = CDeploymentSession::GetNumbersFromString(*a1, *(_QWORD *)a1[26], a1[27]);
      if ( FilePathsFromString >= 0 )
      {
        if ( *(int *)(a1[27] + 4) > 0 )
        {
          v62 = CWatsonHelper::GetInstance();
          v78[0] = L"OFF";
          LogAdapter::TraceInfo<wchar_t const *>("WatsonHelper: Mute for all parameters: [{}]", v78);
          v63 = (void *)*((_QWORD *)v62 + 8);
          v64 = *((_QWORD *)v62 + 9) - (_QWORD)v63;
          if ( (unsigned __int64)v63 > *((_QWORD *)v62 + 9) )
            v64 = 0;
          if ( v64 )
            memset_0(v63, 0, v64);
          for ( *(_DWORD *)a1[5] = 0; ; ++*(_DWORD *)a1[5] )
          {
            v65 = a1[27];
            v66 = (int *)a1[5];
            v67 = *v66;
            if ( (unsigned int)v67 >= *(_DWORD *)(v65 + 4) )
              break;
            v68 = *(_QWORD *)(v65 + 8);
            if ( *(_DWORD *)(v68 + 4 * v67) < 0xAu )
            {
              v70 = *(unsigned int *)(v68 + 4 * v67);
              v72 = CWatsonHelper::GetInstance();
              v79[0] = L"ON";
              LODWORD(v78[0]) = v70;
              if ( *(_QWORD *)&LogAdapter::g_Logger )
              {
                LOBYTE(v71) = 1;
                LogAdapter::Logger::LogNumObjects<unsigned long,wchar_t const *>(
                  *(_QWORD *)&LogAdapter::g_Logger,
                  v71,
                  1,
                  "WatsonHelper: Bucket parameter [{}] mute: [{}]");
              }
              *(_BYTE *)(v70 + *((_QWORD *)v72 + 8)) = 1;
            }
            else
            {
              v69 = *(_QWORD *)(*a1 + 600);
              if ( v69 )
                CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                  v69,
                  3,
                  L"GetOneSettings: Invalid Watson parameter number to mute [%d]: [%s]",
                  *(unsigned int *)(v68 + 4LL * *v66),
                  *(_QWORD *)a1[26]);
            }
          }
        }
        goto LABEL_188;
      }
      v73 = *(_QWORD *)(*a1 + 600);
      if ( v73 )
        CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
          v73,
          3,
          L"GetOneSettings: Could not get Watson parameter numbers from list [0x%X]: [%s]",
          (unsigned int)FilePathsFromString,
          *(_QWORD *)a1[26]);
LABEL_187:
      FilePathsFromString = 0;
      goto LABEL_188;
    }
    v11 = *(_QWORD *)(*a1 + 600);
    if ( !v11 )
      goto LABEL_9;
    v77 = FilePathsFromString;
    v76 = 6358;
LABEL_18:
    updated = (unsigned int)CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(
                              v11,
                              4,
                              L"%s(%d): Result = 0x%X",
                              L"CDeploymentSession::GetOneSettings::<lambda_1>::operator ()",
                              v76,
                              v77);
LABEL_11:
    if ( (int)updated < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(updated, v10);
LABEL_13:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(updated);
LABEL_188:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)FilePathsFromString);
    result = (unsigned int)FilePathsFromString;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1932,
                           (unsigned int)"onecore\\base\\ntsetup\\conx\\mosetup\\updateagent\\src\\DeploymentSessionImpl.h",
                           v74);
  }
  return result;
}

```

## disassembly

```asm
0x18002c0c4  push    rbx
0x18002c0c6  push    rsi
0x18002c0c7  push    rdi
0x18002c0c8  push    r12
0x18002c0ca  push    r14
0x18002c0cc  push    r15
0x18002c0ce  sub     rsp, 68h
0x18002c0d2  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x18002c0db  mov     rdi, rcx
0x18002c0de  mov     rax, [rcx]
0x18002c0e1  xor     r12d, r12d
0x18002c0e4  mov     [rax+120h], r12d
0x18002c0eb  mov     rax, [rcx]
0x18002c0ee  mov     dword ptr [rax+160h], 3
0x18002c0f8  mov     rax, [rcx]
0x18002c0fb  mov     dword ptr [rax+164h], 3
0x18002c105  mov     rax, [rcx]
0x18002c108  mov     dword ptr [rax+168h], 3
0x18002c112  mov     rax, [rcx]
0x18002c115  mov     dword ptr [rax+16Ch], 6000h
0x18002c11f  mov     rax, [rcx]
0x18002c122  lea     r15d, [r12+2]
0x18002c127  mov     [rax+170h], r15d
0x18002c12e  mov     rax, [rcx]
0x18002c131  mov     [rax+148h], r12b
0x18002c138  mov     rax, [rcx]
0x18002c13b  mov     dword ptr [rax+12Ch], 1
0x18002c145  mov     rax, [rcx]
0x18002c148  mov     dword ptr [rax+130h], 1
0x18002c152  mov     rcx, [rcx]
0x18002c155  test    [rcx+174h], r15b
0x18002c15c  jz      short loc_18002C182
0x18002c15e  mov     rcx, [rcx+258h]
0x18002c165  test    rcx, rcx
0x18002c168  jz      loc_18002CFDA
0x18002c16e  lea     r8, aSkippingGetone; "Skipping GetOneSettings(). Session was "...
0x18002c175  mov     edx, r15d
0x18002c178  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c17d  jmp     loc_18002CFDA
0x18002c182  add     rcx, 180h
0x18002c189  xor     edx, edx
0x18002c18b  call    ?SetSize@?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJH@Z; CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault>::SetSize(int)
0x18002c190  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace> `wil::Feature<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::GetImpl(void)'::`2'::impl
0x18002c197  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_SetupImproveLowDiskSpace>::__private_IsEnabled(void)
0x18002c19c  test    al, al
0x18002c19e  jnz     short loc_18002C209
0x18002c1a0  mov     rcx, [rdi]
0x18002c1a3  lea     r8, [rcx+180h]
0x18002c1aa  lea     rdx, aLcuGdr; "LCU;GDR"
0x18002c1b1  call    ?GetPackageCategoriesFromString@CDeploymentSession@@QEAAJPEB_WPEAV?$CArray@W4PackageCategory@ActionList@@W412@VCAdaptorDefault@@VCPoliciesDefault@@@@@Z; CDeploymentSession::GetPackageCategoriesFromString(wchar_t const *,CArray<ActionList::PackageCategory,ActionList::PackageCategory,CAdaptorDefault,CPoliciesDefault> *)
0x18002c1b6  mov     ebx, eax
0x18002c1b8  test    eax, eax
0x18002c1ba  jns     short loc_18002C209
0x18002c1bc  mov     rcx, [rdi]
0x18002c1bf  mov     rcx, [rcx+258h]
0x18002c1c6  test    rcx, rcx
0x18002c1c9  jnz     short loc_18002C1D0
0x18002c1cb  mov     ecx, r12d
0x18002c1ce  jmp     short loc_18002C1FF
0x18002c1d0  mov     dword ptr [rsp+98h+var_70], eax
0x18002c1d4  mov     dword ptr [rsp+98h+var_78], 1840h
0x18002c1dc  lea     r9, aCdeploymentses_42; "CDeploymentSession::GetOneSettings::<la"...
0x18002c1e3  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002c1ea  mov     edx, 4
0x18002c1ef  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c1f4  mov     ecx, eax
0x18002c1f6  test    ecx, ecx
0x18002c1f8  jns     short loc_18002C1FF
0x18002c1fa  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002c1ff  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c204  jmp     loc_18002CFDD
0x18002c209  mov     r9, [rdi+8]
0x18002c20d  lea     r8, aOnesettingspat; "OneSettingsPath"
0x18002c214  lea     rdx, aSystemSetupMos_1; "System\\Setup\\MoSetup"
0x18002c21b  call    ?GetValue@?$CRegUtilT@PEA_WUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAPEA_WPEAK@Z; CRegUtilT<wchar_t *,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t * *,ulong *)
0x18002c220  test    eax, eax
0x18002c222  js      short loc_18002C26E
0x18002c224  mov     rdx, [rdi+8]
0x18002c228  mov     rcx, [rdi+10h]
0x18002c22c  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x18002c231  mov     ebx, eax
0x18002c233  test    eax, eax
0x18002c235  jns     short loc_18002C26E
0x18002c237  mov     rax, [rdi]
0x18002c23a  mov     rcx, [rax+258h]
0x18002c241  test    rcx, rcx
0x18002c244  jz      short loc_18002C1CB
0x18002c246  mov     dword ptr [rsp+98h+var_70], ebx
0x18002c24a  mov     dword ptr [rsp+98h+var_78], 184Ah
0x18002c252  lea     r9, aCdeploymentses_42; "CDeploymentSession::GetOneSettings::<la"...
0x18002c259  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x18002c260  mov     edx, 4
0x18002c265  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c26a  mov     ecx, eax
0x18002c26c  jmp     short loc_18002C1F6
0x18002c26e  mov     rax, [rdi]
0x18002c271  mov     r9, [rdi+18h]
0x18002c275  xor     r8d, r8d
0x18002c278  lea     rdx, aUaonesettingsD; "UAOneSettings.dll"
0x18002c27f  mov     rcx, [rax+1F0h]
0x18002c286  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18002c28b  mov     ebx, eax
0x18002c28d  test    eax, eax
0x18002c28f  jns     short loc_18002C2B2
0x18002c291  mov     rax, [rdi]
0x18002c294  mov     rcx, [rax+258h]
0x18002c29b  test    rcx, rcx
0x18002c29e  jz      loc_18002C1CB
0x18002c2a4  mov     dword ptr [rsp+98h+var_70], ebx
0x18002c2a8  mov     dword ptr [rsp+98h+var_78], 184Fh
0x18002c2b0  jmp     short loc_18002C252
0x18002c2b2  mov     rdx, [rdi+18h]
0x18002c2b6  mov     rcx, [rdi+10h]
0x18002c2ba  call    ?Append@?$CArray@VDH_SSTRING@@V1@VCAdaptorDefault@@VCPoliciesDefault@@@@QEAAJAEBVDH_SSTRING@@@Z; CArray<DH_SSTRING,DH_SSTRING,CAdaptorDefault,CPoliciesDefault>::Append(DH_SSTRING const &)
0x18002c2bf  mov     ebx, eax
0x18002c2c1  test    eax, eax
0x18002c2c3  jns     short loc_18002C2E9
0x18002c2c5  mov     rax, [rdi]
0x18002c2c8  mov     rcx, [rax+258h]
0x18002c2cf  test    rcx, rcx
0x18002c2d2  jz      loc_18002C1CB
0x18002c2d8  mov     dword ptr [rsp+98h+var_70], ebx
0x18002c2dc  mov     dword ptr [rsp+98h+var_78], 1850h
0x18002c2e4  jmp     loc_18002C252
0x18002c2e9  mov     rax, [rdi+20h]
0x18002c2ed  mov     [rax], r12
0x18002c2f0  mov     rax, [rdi+28h]
0x18002c2f4  mov     [rax], r12d
0x18002c2f7  mov     rdx, [rdi+28h]
0x18002c2fb  mov     rax, [rdi+10h]
0x18002c2ff  mov     ecx, [rax+4]
0x18002c302  cmp     [rdx], ecx
0x18002c304  jnb     loc_18002C5B1
0x18002c30a  mov     rsi, [rdi+30h]
0x18002c30e  mov     rbx, [rsi]
0x18002c311  test    rbx, rbx
0x18002c314  jz      short loc_18002C345
0x18002c316  call    cs:__imp_GetProcessHeap
0x18002c31d  nop     dword ptr [rax+rax+00h]
0x18002c322  mov     rcx, rax; hHeap
0x18002c325  lea     r8, [rbx-4]; lpMem
0x18002c329  xor     edx, edx; dwFlags
0x18002c32b  call    cs:__imp_HeapFree
0x18002c332  nop     dword ptr [rax+rax+00h]
0x18002c337  xor     ecx, ecx
0x18002c339  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c33e  mov     [rsi], r12
0x18002c341  mov     rdx, [rdi+28h]
0x18002c345  mov     r14, [rdi+30h]
0x18002c349  mov     rax, [rdi+10h]
0x18002c34d  mov     rcx, [rax+8]
0x18002c351  movsxd  rax, dword ptr [rdx]
0x18002c354  mov     rsi, [rcx+rax*8]
0x18002c358  test    rsi, rsi
0x18002c35b  jnz     short loc_18002C365
0x18002c35d  mov     rsi, r12
0x18002c360  mov     edx, r12d
0x18002c363  jmp     short loc_18002C381
0x18002c365  mov     dword ptr [rsp+98h+var_68], r12d
0x18002c36a  lea     rdx, [rsp+98h+var_68]
0x18002c36f  mov     rcx, rsi
0x18002c372  call    ??$GetStringCchLength@K@?$CGlobalHelpersT@VCEmptyType@@@@SAJPEB_WPEAKK@Z; CGlobalHelpersT<CEmptyType>::GetStringCchLength<ulong>(wchar_t const *,ulong *,ulong)
0x18002c377  mov     ebx, eax
0x18002c379  test    eax, eax
0x18002c37b  js      short loc_18002C392
0x18002c37d  mov     edx, dword ptr [rsp+98h+var_68]
0x18002c381  mov     r8, r14
0x18002c384  mov     rcx, rsi; Src
0x18002c387  call    ?CreateInternal@?$CImmutableStringsT@_WVCImmutableStringsPolicyDefault@@@@KAJPEB_WKPEAPEA_W@Z; CImmutableStringsT<wchar_t,CImmutableStringsPolicyDefault>::CreateInternal(wchar_t const *,ulong,wchar_t * *)
0x18002c38c  mov     ebx, eax
0x18002c38e  test    eax, eax
0x18002c390  jns     short loc_18002C399
0x18002c392  mov     ecx, eax
0x18002c394  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18002c399  mov     ecx, ebx
0x18002c39b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c3a0  test    ebx, ebx
0x18002c3a2  jns     short loc_18002C3C8
0x18002c3a4  mov     rax, [rdi]
0x18002c3a7  mov     rcx, [rax+258h]
0x18002c3ae  test    rcx, rcx
0x18002c3b1  jz      loc_18002C1CB
0x18002c3b7  mov     dword ptr [rsp+98h+var_70], ebx
0x18002c3bb  mov     dword ptr [rsp+98h+var_78], 1858h
0x18002c3c3  jmp     loc_18002C252
0x18002c3c8  mov     rbx, [rdi+38h]
0x18002c3cc  mov     rax, [rdi+30h]
0x18002c3d0  mov     rcx, [rax]; lpFileName
0x18002c3d3  call    cs:__imp_GetFileAttributesW
0x18002c3da  nop     dword ptr [rax+rax+00h]
0x18002c3df  cmp     eax, 0FFFFFFFFh
0x18002c3e2  jz      short loc_18002C3EE
0x18002c3e4  shr     eax, 4
0x18002c3e7  not     eax
0x18002c3e9  and     eax, 1
0x18002c3ec  jmp     short loc_18002C3F1
0x18002c3ee  mov     eax, r12d
0x18002c3f1  mov     [rbx], eax
0x18002c3f3  xor     ecx, ecx
0x18002c3f5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c3fa  xor     ecx, ecx
0x18002c3fc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18002c401  mov     ebx, r12d
0x18002c404  mov     rax, [rdi+38h]
0x18002c408  cmp     [rax], r12d
0x18002c40b  jz      short loc_18002C465
0x18002c40d  mov     rax, [rdi]
0x18002c410  mov     rcx, [rax+258h]
0x18002c417  test    rcx, rcx
0x18002c41a  jz      short loc_18002C432
0x18002c41c  mov     rax, [rdi+30h]
0x18002c420  mov     r9, [rax]
0x18002c423  lea     r8, aGetonesettings_4; "GetOneSettings: Verifying signature of "...
0x18002c42a  mov     edx, r15d
0x18002c42d  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c432  mov     rax, [rdi+30h]
0x18002c436  mov     rcx, [rax]; lpSrc
0x18002c439  call    ?VerifySelfSignedImageFile@?$CGlobalMiscUtilsT@VCEmptyType@@@@SAJPEB_WHHH@Z; CGlobalMiscUtilsT<CEmptyType>::VerifySelfSignedImageFile(wchar_t const *,int,int,int)
0x18002c43e  mov     ebx, eax
0x18002c440  mov     rax, [rdi]
0x18002c443  mov     rcx, [rax+258h]
0x18002c44a  test    ebx, ebx
0x18002c44c  jns     short loc_18002C470
0x18002c44e  test    rcx, rcx
0x18002c451  jz      short loc_18002C465
0x18002c453  lea     r8, aGetonesettings_11; "GetOneSettings: Module not signed. [0x%"...
0x18002c45a  mov     r9d, ebx
0x18002c45d  mov     edx, r15d
0x18002c460  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c465  mov     rax, [rdi+28h]
0x18002c469  inc     dword ptr [rax]
0x18002c46b  jmp     loc_18002C2F7
0x18002c470  test    rcx, rcx
0x18002c473  jz      short loc_18002C48B
0x18002c475  mov     rax, [rdi+30h]
0x18002c479  mov     r9, [rax]
0x18002c47c  lea     r8, aGetonesettings_14; "GetOneSettings: Loading [%s]..."
0x18002c483  mov     edx, r15d
0x18002c486  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
0x18002c48b  mov     rax, [rdi+30h]
0x18002c48f  xor     r8d, r8d; dwFlags
0x18002c492  xor     edx, edx; hFile
0x18002c494  mov     rcx, [rax]; lpLibFileName
0x18002c497  call    cs:__imp_LoadLibraryExW
0x18002c49e  nop     dword ptr [rax+rax+00h]
0x18002c4a3  mov     rbx, rax
0x18002c4a6  mov     rsi, [rdi+40h]
0x18002c4aa  mov     rcx, [rsi]; hLibModule
0x18002c4ad  test    rcx, rcx
0x18002c4b0  jz      short loc_18002C4BE
0x18002c4b2  call    cs:__imp_FreeLibrary
0x18002c4b9  nop     dword ptr [rax+rax+00h]
0x18002c4be  mov     [rsi], rbx
0x18002c4c1  mov     rax, [rdi+40h]
0x18002c4c5  mov     rcx, [rax]; hModule
0x18002c4c8  test    rcx, rcx
0x18002c4cb  jnz     short loc_18002C507
0x18002c4cd  call    cs:__imp_GetLastError
0x18002c4d4  nop     dword ptr [rax+rax+00h]
0x18002c4d9  mov     ebx, eax
0x18002c4db  test    eax, eax
0x18002c4dd  jle     short loc_18002C4E8
0x18002c4df  movzx   ebx, ax
0x18002c4e2  or      ebx, 80070000h
0x18002c4e8  mov     rax, [rdi]
0x18002c4eb  mov     rcx, [rax+258h]
0x18002c4f2  test    rcx, rcx
0x18002c4f5  jz      loc_18002C465
0x18002c4fb  lea     r8, aGetonesettings_13; "GetOneSettings: Module failed to load. "...
0x18002c502  jmp     loc_18002C45A
0x18002c507  mov     rbx, [rdi+20h]
0x18002c50b  lea     rdx, aCreateonesetti; "CreateOneSettingsHelperEx"
0x18002c512  call    cs:__imp_GetProcAddress
0x18002c519  nop     dword ptr [rax+rax+00h]
0x18002c51e  mov     [rbx], rax
0x18002c521  mov     rax, [rdi+20h]
0x18002c525  cmp     [rax], r12
0x18002c528  jnz     short loc_18002C564
0x18002c52a  call    cs:__imp_GetLastError
0x18002c531  nop     dword ptr [rax+rax+00h]
0x18002c536  mov     ebx, eax
0x18002c538  test    eax, eax
0x18002c53a  jle     short loc_18002C545
0x18002c53c  movzx   ebx, ax
0x18002c53f  or      ebx, 80070000h
0x18002c545  mov     rax, [rdi]
0x18002c548  mov     rcx, [rax+258h]
0x18002c54f  test    rcx, rcx
0x18002c552  jz      loc_18002C465
0x18002c558  lea     r8, aGetonesettings_5; "GetOneSettings: Entrypoint not found. ["...
0x18002c55f  jmp     loc_18002C45A
0x18002c564  mov     rax, [rdi]
0x18002c567  mov     rcx, [rax+258h]
0x18002c56e  test    rcx, rcx
0x18002c571  jz      short loc_18002C589
0x18002c573  mov     rax, [rdi+30h]
0x18002c577  mov     r9, [rax]
0x18002c57a  lea     r8, aGetonesettings_10; "GetOneSettings: OneSettings module [%s]"...
0x18002c581  mov     edx, r15d
0x18002c584  call    ?MoUpdateLogFormat@?$CMoUpdateLogT@VCEmptyType@@@@SAJPEAVIUpdateDiagnostics@@W4MOUPDATE_LOGLEVEL@@PEB_WZZ; CMoUpdateLogT<CEmptyType>::MoUpdateLogFormat(IUpdateDiagnostics *,MOUPDATE_LOGLEVEL,wchar_t const *,...)
  ... truncated ...
```
