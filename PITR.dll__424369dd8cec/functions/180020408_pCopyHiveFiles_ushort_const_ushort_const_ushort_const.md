# pCopyHiveFiles(ushort const *,ushort const *,ushort const *)

- ea: `0x180020408`
- end: `0x180020a09`
- name: `?pCopyHiveFiles@@YAJPEBG00@Z`
- size: `1537`
- prototype: `__int64 __fastcall(const char *, const char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x1800170f0`

## callees

- `0x180009e04`
- `0x180020408`
- `0x1800502c2`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800209ba`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800209ba`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020479`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020479`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002057a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18002057a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800207f0`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800207f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002080d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002087a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002094a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020487`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800204aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800205a4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020766`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002080d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020862`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002087a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002094a`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180020755`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180020755`
- `WDSCORE!CurrentIP` at `0x1800204b2`
- `WDSCORE!CurrentIP` at `0x1800205ac`
- `WDSCORE!CurrentIP` at `0x180020631`
- `WDSCORE!CurrentIP` at `0x18002076e`
- `WDSCORE!CurrentIP` at `0x180020815`
- `WDSCORE!CurrentIP` at `0x18002089e`
- `WDSCORE!CurrentIP` at `0x180020952`
- `WDSCORE!CurrentIP` at `0x1800204b2`
- `WDSCORE!CurrentIP` at `0x1800205ac`
- `WDSCORE!CurrentIP` at `0x180020631`
- `WDSCORE!CurrentIP` at `0x18002076e`
- `WDSCORE!CurrentIP` at `0x180020815`
- `WDSCORE!CurrentIP` at `0x18002089e`
- `WDSCORE!CurrentIP` at `0x180020952`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020514`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002061e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800206a6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800207c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020928`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800209af`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020514`
- `WDSCORE!WdsSetupLogMessageW` at `0x18002061e`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800206a6`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800207c7`
- `WDSCORE!WdsSetupLogMessageW` at `0x180020928`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800209af`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002056d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800205c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180020647`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002072f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180020746`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800208b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800208cb`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002056d`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800205c2`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180020647`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002072f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180020746`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800208b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800208cb`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180020530`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800206eb`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18002070e`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x180020530`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x1800206eb`
- `unbcl!?Format@String@UnBCL@@SAPEAV12@PEBGZZ` at `0x18002070e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18002053e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800206f9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18002071b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18002053e`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x1800206f9`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x18002071b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180020458`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180020458`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18002055a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800207d2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800207de`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180020933`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18002093f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800209c5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800209d4`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18002055a`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800207d2`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800207de`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180020933`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x18002093f`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800209c5`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1800209d4`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18002054e`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x18002054e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180020564`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800205b9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18002063e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180020726`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18002073d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800208ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800208c2`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180020564`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800205b9`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18002063e`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180020726`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18002073d`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800208ab`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x1800208c2`

## string_xrefs

- `0x1800204f1`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800205fb`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180020683`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800206cc`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800204e5`: `pCopyHiveFiles`
- `0x1800205ef`: `pCopyHiveFiles`
- `0x180020677`: `pCopyHiveFiles`
- `0x1800206c5`: `pCopyHiveFiles`
- `0x1800204c1`: `Failed to create directory %s. Error: 0x%08X`
- `0x1800208dc`: `Failed to copy %s to %s. Error: 0x%08X`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall pCopyHiveFiles(const char *a1, const char *a2, const unsigned __int16 *a3)
{
  const char *v4; // rbx
  int v5; // r13d
  signed int LastError; // eax
  signed int v7; // r14d
  DWORD v8; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  struct UnBCL::String *v11; // rax
  UnBCL::String *v12; // rax
  const WCHAR *CString; // rax
  HANDLE FirstFileW; // r14
  DWORD v15; // edi
  __int64 v16; // rbx
  UnBCL::String *v17; // rax
  const char *v18; // rax
  struct tagLOG_PARTIAL_MSG *v19; // rax
  DWORD v20; // edi
  __int64 v21; // rbx
  UnBCL::String *v22; // rax
  const char *v23; // rax
  struct tagLOG_PARTIAL_MSG *v24; // rax
  struct UnBCL::String *v25; // rax
  struct UnBCL::String *v26; // rax
  UnBCL::String *v27; // rax
  const WCHAR *v28; // rbx
  UnBCL::String *v29; // rax
  const WCHAR *v30; // rax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  DWORD v34; // edi
  __int64 v35; // rbx
  struct tagLOG_PARTIAL_MSG *v36; // rax
  signed int v37; // eax
  bool v38; // sf
  signed int v39; // eax
  DWORD v40; // esi
  __int64 v41; // rdi
  UnBCL::String *v42; // rax
  const char *v43; // rbx
  UnBCL::String *v44; // rax
  const char *v45; // rax
  struct tagLOG_PARTIAL_MSG *v46; // rax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  HANDLE hFindFile; // [rsp+68h] [rbp-98h]
  _BYTE v53[16]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v54[16]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v55[16]; // [rsp+90h] [rbp-70h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+A0h] [rbp-60h] BYREF

  v4 = a1;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v54);
  v5 = 0;
  if ( v4 && a2 )
  {
    if ( !CreateDirectoryW((LPCWSTR)a2, 0) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 183 )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        v8 = GetLastError();
        v9 = CurrentIP();
        v10 = ConstructPartialMsgW(0x2000000, "Failed to create directory %s. Error: 0x%08X", a2, v7);
        WdsSetupLogMessageW(
          v10,
          0,
          L"D",
          0,
          964,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"pCopyHiveFiles",
          v9,
          v8,
          0,
          0);
        goto LABEL_28;
      }
    }
    v11 = UnBCL::String::Format(L"%s\\%s*", v4, L"SOFTWARE");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v53, v11);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v54, v53);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v53);
    v12 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v54);
    CString = UnBCL::String::get_CString(v12);
    FirstFileW = FindFirstFileW(CString, &FindFileData);
    hFindFile = FirstFileW;
    if ( FirstFileW != (HANDLE)-1LL )
    {
      while ( 1 )
      {
        if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
        {
          v25 = UnBCL::String::Format(L"%s\\%s", v4, FindFileData.cFileName);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v53, v25);
          v26 = UnBCL::String::Format(L"%s\\%s", a2, FindFileData.cFileName);
          UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v55, v26);
          v27 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v55);
          v28 = UnBCL::String::get_CString(v27);
          v29 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v53);
          v30 = UnBCL::String::get_CString(v29);
          if ( !CopyFileW(v30, v28, 0) )
          {
            v37 = GetLastError();
            v38 = v37 < 0;
            if ( v37 > 0 )
              v38 = 1;
            if ( v38 )
            {
              v39 = GetLastError();
              v7 = v39;
              if ( v39 > 0 )
                v7 = (unsigned __int16)v39 | 0x80070000;
            }
            else
            {
              v7 = -2147467259;
            }
            v40 = GetLastError();
            v41 = CurrentIP();
            v42 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v55);
            v43 = (const char *)UnBCL::String::get_CString(v42);
            v44 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v53);
            v45 = (const char *)UnBCL::String::get_CString(v44);
            v46 = ConstructPartialMsgW(0x2000000, "Failed to copy %s to %s. Error: 0x%08X", v45, v43, v7);
            WdsSetupLogMessageW(
              v46,
              0,
              L"D",
              0,
              999,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"pCopyHiveFiles",
              v41,
              v40,
              0,
              0);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v55);
            UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v53);
LABEL_27:
            FindClose(hFindFile);
            goto LABEL_28;
          }
          ++v5;
          v31 = GetLastError();
          v32 = CurrentIP();
          v33 = ConstructPartialMsgW(0x4000000, "Copied %s", (const char *)FindFileData.cFileName);
          WdsSetupLogMessageW(
            v33,
            0,
            L"D",
            0,
            1003,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"pCopyHiveFiles",
            v32,
            v31,
            0,
            0);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v55);
          UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v53);
          v4 = a1;
        }
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
        {
          if ( v5 )
          {
            v7 = 0;
            v47 = GetLastError();
            v48 = CurrentIP();
            v49 = ConstructPartialMsgW(
                    0x4000000,
                    "Successfully copied %d %s hive file(s) to %s",
                    v5,
                    (const char *)L"SOFTWARE",
                    a2);
            WdsSetupLogMessageW(
              v49,
              0,
              L"D",
              0,
              1014,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"pCopyHiveFiles",
              v48,
              v47,
              0,
              0);
          }
          else
          {
            v7 = -2147024894;
            v34 = GetLastError();
            v35 = CurrentIP();
            v36 = ConstructPartialMsgW(50331648, "No files were copied from %s", a1);
            WdsSetupLogMessageW(
              v36,
              0,
              L"D",
              0,
              1010,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"pCopyHiveFiles",
              v35,
              v34,
              0,
              0);
          }
          goto LABEL_27;
        }
      }
    }
    v7 = GetLastError();
    if ( v7 == 2 )
    {
      v15 = GetLastError();
      v16 = CurrentIP();
      v17 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v54);
      v18 = (const char *)UnBCL::String::get_CString(v17);
      v19 = ConstructPartialMsgW(50331648, "No files matching %s found", v18);
      WdsSetupLogMessageW(
        v19,
        0,
        L"D",
        0,
        977,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"pCopyHiveFiles",
        v16,
        v15,
        0,
        0);
    }
    else
    {
      v20 = GetLastError();
      v21 = CurrentIP();
      v22 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v54);
      v23 = (const char *)UnBCL::String::get_CString(v22);
      v24 = ConstructPartialMsgW(0x2000000, "FindFirstFile failed for %s. Error: 0x%08X", v23, v7);
      WdsSetupLogMessageW(
        v24,
        0,
        L"D",
        0,
        981,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"pCopyHiveFiles",
        v21,
        v20,
        0,
        0);
      if ( v7 <= 0 )
        goto LABEL_28;
    }
    v7 = (unsigned __int16)v7 | 0x80070000;
LABEL_28:
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v54);
    return (unsigned int)v7;
  }
  else
  {
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v54);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180020408  mov     [rsp-8+arg_10], rbx
0x18002040d  push    rbp
0x18002040e  push    rsi
0x18002040f  push    rdi
0x180020410  push    r12
0x180020412  push    r13
0x180020414  push    r14
0x180020416  push    r15
0x180020418  lea     rbp, [rsp-200h]
0x180020420  sub     rsp, 300h
0x180020427  mov     rax, cs:__security_cookie
0x18002042e  xor     rax, rsp
0x180020431  mov     [rbp+230h+var_40], rax
0x180020438  mov     rsi, rdx
0x18002043b  mov     rbx, rcx
0x18002043e  mov     [rsp+330h+var_2D0], rcx
0x180020443  xor     edx, edx; Val
0x180020445  mov     r8d, 250h; Size
0x18002044b  lea     rcx, [rbp+230h+FindFileData]; void *
0x18002044f  call    memset_0
0x180020454  lea     rcx, [rbp+230h+var_2B0]
0x180020458  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x18002045e  nop
0x18002045f  xor     r13d, r13d
0x180020462  test    rbx, rbx
0x180020465  jz      loc_1800209D0
0x18002046b  test    rsi, rsi
0x18002046e  jz      loc_1800209D0
0x180020474  xor     edx, edx; lpSecurityAttributes
0x180020476  mov     rcx, rsi; lpPathName
0x180020479  call    cs:__imp_CreateDirectoryW
0x18002047f  test    eax, eax
0x180020481  jnz     loc_18002051F
0x180020487  call    cs:__imp_GetLastError
0x18002048d  mov     r14d, eax
0x180020490  cmp     eax, 0B7h
0x180020495  jz      loc_18002051F
0x18002049b  test    eax, eax
0x18002049d  jle     short loc_1800204AA
0x18002049f  movzx   r14d, ax
0x1800204a3  or      r14d, 80070000h
0x1800204aa  call    cs:__imp_GetLastError
0x1800204b0  mov     edi, eax
0x1800204b2  call    cs:__imp_CurrentIP
0x1800204b8  mov     rbx, rax
0x1800204bb  mov     r9d, r14d
0x1800204be  mov     r8, rsi
0x1800204c1  lea     rdx, aFailedToCreate_1; "Failed to create directory %s. Error: 0"...
0x1800204c8  mov     ecx, 2000000h; unsigned int
0x1800204cd  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800204d2  mov     [rsp+330h+var_2E0], r13d
0x1800204d7  mov     [rsp+330h+var_2E8], r13
0x1800204dc  mov     [rsp+330h+var_2F0], edi
0x1800204e0  mov     [rsp+330h+var_2F8], rbx
0x1800204e5  lea     r15, aPcopyhivefiles; "pCopyHiveFiles"
0x1800204ec  mov     [rsp+330h+var_300], r15
0x1800204f1  lea     r12, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800204f8  mov     [rsp+330h+var_308], r12
0x1800204fd  mov     dword ptr [rsp+330h+var_310], 3C4h
0x180020505  xor     r9d, r9d
0x180020508  lea     r8, aD; "D"
0x18002050f  xor     edx, edx
0x180020511  mov     rcx, rax
0x180020514  call    cs:__imp_WdsSetupLogMessageW
0x18002051a  jmp     loc_1800209C1
0x18002051f  lea     r8, aSoftware; "SOFTWARE"
0x180020526  mov     rdx, rbx
0x180020529  lea     rcx, aSS_1; "%s\\%s*"
0x180020530  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180020536  mov     rdx, rax
0x180020539  lea     rcx, [rsp+330h+var_2C0]
0x18002053e  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180020544  nop
0x180020545  lea     rdx, [rsp+330h+var_2C0]
0x18002054a  lea     rcx, [rbp+230h+var_2B0]
0x18002054e  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180020554  nop
0x180020555  lea     rcx, [rsp+330h+var_2C0]
0x18002055a  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180020560  lea     rcx, [rbp+230h+var_2B0]
0x180020564  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18002056a  mov     rcx, rax
0x18002056d  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180020573  mov     rcx, rax; lpFileName
0x180020576  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x18002057a  call    cs:__imp_FindFirstFileW
0x180020580  mov     r14, rax
0x180020583  mov     [rsp+330h+hFindFile], rax
0x180020588  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002058c  jnz     loc_1800206C5
0x180020592  call    cs:__imp_GetLastError
0x180020598  mov     r14d, eax
0x18002059b  cmp     eax, 2
0x18002059e  jnz     loc_180020629
0x1800205a4  call    cs:__imp_GetLastError
0x1800205aa  mov     edi, eax
0x1800205ac  call    cs:__imp_CurrentIP
0x1800205b2  mov     rbx, rax
0x1800205b5  lea     rcx, [rbp+230h+var_2B0]
0x1800205b9  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800205bf  mov     rcx, rax
0x1800205c2  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800205c8  mov     r8, rax
0x1800205cb  lea     rdx, aNoFilesMatchin; "No files matching %s found"
0x1800205d2  mov     ecx, 3000000h; unsigned int
0x1800205d7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800205dc  mov     [rsp+330h+var_2E0], r13d
0x1800205e1  mov     [rsp+330h+var_2E8], r13
0x1800205e6  mov     [rsp+330h+var_2F0], edi
0x1800205ea  mov     [rsp+330h+var_2F8], rbx
0x1800205ef  lea     r15, aPcopyhivefiles; "pCopyHiveFiles"
0x1800205f6  mov     [rsp+330h+var_300], r15
0x1800205fb  lea     r12, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180020602  mov     [rsp+330h+var_308], r12
0x180020607  mov     dword ptr [rsp+330h+var_310], 3D1h
0x18002060f  xor     r9d, r9d
0x180020612  lea     r8, aD; "D"
0x180020619  xor     edx, edx
0x18002061b  mov     rcx, rax
0x18002061e  call    cs:__imp_WdsSetupLogMessageW
0x180020624  jmp     loc_1800206B5
0x180020629  call    cs:__imp_GetLastError
0x18002062f  mov     edi, eax
0x180020631  call    cs:__imp_CurrentIP
0x180020637  mov     rbx, rax
0x18002063a  lea     rcx, [rbp+230h+var_2B0]
0x18002063e  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180020644  mov     rcx, rax
0x180020647  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002064d  mov     r8, rax
0x180020650  mov     r9d, r14d
0x180020653  lea     rdx, aFindfirstfileF; "FindFirstFile failed for %s. Error: 0x%"...
0x18002065a  mov     ecx, 2000000h; unsigned int
0x18002065f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180020664  mov     [rsp+330h+var_2E0], r13d
0x180020669  mov     [rsp+330h+var_2E8], r13
0x18002066e  mov     [rsp+330h+var_2F0], edi
0x180020672  mov     [rsp+330h+var_2F8], rbx
0x180020677  lea     r15, aPcopyhivefiles; "pCopyHiveFiles"
0x18002067e  mov     [rsp+330h+var_300], r15
0x180020683  lea     r12, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x18002068a  mov     [rsp+330h+var_308], r12
0x18002068f  mov     dword ptr [rsp+330h+var_310], 3D5h
0x180020697  xor     r9d, r9d
0x18002069a  lea     r8, aD; "D"
0x1800206a1  xor     edx, edx
0x1800206a3  mov     rcx, rax
0x1800206a6  call    cs:__imp_WdsSetupLogMessageW
0x1800206ac  test    r14d, r14d
0x1800206af  jle     loc_1800209C1
0x1800206b5  movzx   r14d, r14w
0x1800206b9  or      r14d, 80070000h
0x1800206c0  jmp     loc_1800209C1
0x1800206c5  lea     r15, aPcopyhivefiles; "pCopyHiveFiles"
0x1800206cc  lea     r12, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800206d3  test    byte ptr [rbp+230h+FindFileData.dwFileAttributes], 10h
0x1800206d7  jnz     loc_1800207E9
0x1800206dd  lea     r8, [rbp+230h+FindFileData.cFileName]
0x1800206e1  mov     rdx, rbx
0x1800206e4  lea     rcx, aSS; "%s\\%s"
0x1800206eb  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x1800206f1  mov     rdx, rax
0x1800206f4  lea     rcx, [rsp+330h+var_2C0]
0x1800206f9  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x1800206ff  nop
0x180020700  lea     r8, [rbp+230h+FindFileData.cFileName]
0x180020704  mov     rdx, rsi
0x180020707  lea     rcx, aSS; "%s\\%s"
0x18002070e  call    cs:__imp_?Format@String@UnBCL@@SAPEAV12@PEBGZZ; UnBCL::String::Format(ushort const *,...)
0x180020714  mov     rdx, rax
0x180020717  lea     rcx, [rbp+230h+var_2A0]
0x18002071b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180020721  nop
0x180020722  lea     rcx, [rbp+230h+var_2A0]
0x180020726  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x18002072c  mov     rcx, rax
0x18002072f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180020735  mov     rbx, rax
0x180020738  lea     rcx, [rsp+330h+var_2C0]
0x18002073d  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180020743  mov     rcx, rax
0x180020746  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002074c  xor     r8d, r8d; bFailIfExists
0x18002074f  mov     rdx, rbx; lpNewFileName
0x180020752  mov     rcx, rax; lpExistingFileName
0x180020755  call    cs:__imp_CopyFileW
0x18002075b  test    eax, eax
0x18002075d  jz      loc_180020862
0x180020763  inc     r13d
0x180020766  call    cs:__imp_GetLastError
0x18002076c  mov     edi, eax
0x18002076e  call    cs:__imp_CurrentIP
0x180020774  mov     rbx, rax
0x180020777  lea     r8, [rbp+230h+FindFileData.cFileName]
0x18002077b  lea     rdx, aCopiedS; "Copied %s"
0x180020782  mov     ecx, 4000000h; unsigned int
0x180020787  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002078c  mov     [rsp+330h+var_2E0], 0
0x180020794  mov     [rsp+330h+var_2E8], 0
0x18002079d  mov     [rsp+330h+var_2F0], edi
0x1800207a1  mov     [rsp+330h+var_2F8], rbx
0x1800207a6  mov     [rsp+330h+var_300], r15
0x1800207ab  mov     [rsp+330h+var_308], r12
0x1800207b0  mov     dword ptr [rsp+330h+var_310], 3EBh
0x1800207b8  xor     r9d, r9d
0x1800207bb  lea     r8, aD; "D"
0x1800207c2  xor     edx, edx
0x1800207c4  mov     rcx, rax
0x1800207c7  call    cs:__imp_WdsSetupLogMessageW
0x1800207cd  nop
0x1800207ce  lea     rcx, [rbp+230h+var_2A0]
0x1800207d2  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800207d8  nop
0x1800207d9  lea     rcx, [rsp+330h+var_2C0]
0x1800207de  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x1800207e4  mov     rbx, [rsp+330h+var_2D0]
0x1800207e9  lea     rdx, [rbp+230h+FindFileData]; lpFindFileData
0x1800207ed  mov     rcx, r14; hFindFile
0x1800207f0  call    cs:__imp_FindNextFileW
0x1800207f6  test    eax, eax
0x1800207f8  jnz     loc_1800206D3
0x1800207fe  test    r13d, r13d
0x180020801  jnz     loc_180020947
0x180020807  mov     r14d, 80070002h
0x18002080d  call    cs:__imp_GetLastError
0x180020813  mov     edi, eax
0x180020815  call    cs:__imp_CurrentIP
0x18002081b  mov     rbx, rax
0x18002081e  mov     r8, [rsp+330h+var_2D0]
0x180020823  lea     rdx, aNoFilesWereCop; "No files were copied from %s"
0x18002082a  mov     ecx, 3000000h; unsigned int
0x18002082f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180020834  mov     [rsp+330h+var_2E0], r13d
0x180020839  mov     [rsp+330h+var_2E8], 0
0x180020842  mov     [rsp+330h+var_2F0], edi
0x180020846  mov     [rsp+330h+var_2F8], rbx
0x18002084b  mov     [rsp+330h+var_300], r15
0x180020850  mov     [rsp+330h+var_308], r12
0x180020855  mov     dword ptr [rsp+330h+var_310], 3F2h
0x18002085d  jmp     loc_1800209A0
0x180020862  call    cs:__imp_GetLastError
0x180020868  mov     ebx, 80070000h
0x18002086d  test    eax, eax
0x18002086f  jle     short loc_180020878
0x180020871  movzx   eax, ax
0x180020874  or      eax, ebx
0x180020876  test    eax, eax
0x180020878  jns     short loc_180020890
0x18002087a  call    cs:__imp_GetLastError
0x180020880  mov     r14d, eax
0x180020883  test    eax, eax
0x180020885  jle     short loc_180020896
0x180020887  movzx   r14d, ax
0x18002088b  or      r14d, ebx
0x18002088e  jmp     short loc_180020896
0x180020890  mov     r14d, 80004005h
0x180020896  call    cs:__imp_GetLastError
0x18002089c  mov     esi, eax
0x18002089e  call    cs:__imp_CurrentIP
0x1800208a4  mov     rdi, rax
0x1800208a7  lea     rcx, [rbp+230h+var_2A0]
0x1800208ab  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800208b1  mov     rcx, rax
0x1800208b4  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800208ba  mov     rbx, rax
0x1800208bd  lea     rcx, [rsp+330h+var_2C0]
0x1800208c2  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x1800208c8  mov     rcx, rax
0x1800208cb  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800208d1  mov     dword ptr [rsp+330h+var_310], r14d
0x1800208d6  mov     r9, rbx
0x1800208d9  mov     r8, rax
0x1800208dc  lea     rdx, aFailedToCopyST; "Failed to copy %s to %s. Error: 0x%08X"
0x1800208e3  mov     ecx, 2000000h; unsigned int
0x1800208e8  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800208ed  mov     [rsp+330h+var_2E0], 0
0x1800208f5  mov     [rsp+330h+var_2E8], 0
0x1800208fe  mov     [rsp+330h+var_2F0], esi
0x180020902  mov     [rsp+330h+var_2F8], rdi
0x180020907  mov     [rsp+330h+var_300], r15
0x18002090c  mov     [rsp+330h+var_308], r12
0x180020911  mov     dword ptr [rsp+330h+var_310], 3E7h
0x180020919  xor     r9d, r9d
0x18002091c  lea     r8, aD; "D"
0x180020923  xor     edx, edx
0x180020925  mov     rcx, rax
0x180020928  call    cs:__imp_WdsSetupLogMessageW
0x18002092e  nop
0x18002092f  lea     rcx, [rbp+230h+var_2A0]
0x180020933  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180020939  nop
0x18002093a  lea     rcx, [rsp+330h+var_2C0]
0x18002093f  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180020945  jmp     short loc_1800209B5
0x180020947  xor     r14d, r14d
0x18002094a  call    cs:__imp_GetLastError
0x180020950  mov     edi, eax
0x180020952  call    cs:__imp_CurrentIP
0x180020958  mov     rbx, rax
0x18002095b  mov     [rsp+330h+var_310], rsi
  ... truncated ...
```
