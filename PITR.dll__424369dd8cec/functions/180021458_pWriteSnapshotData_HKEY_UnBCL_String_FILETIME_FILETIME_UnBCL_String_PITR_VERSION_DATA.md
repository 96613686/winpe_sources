# pWriteSnapshotData(HKEY__ *,UnBCL::String *,_FILETIME,_FILETIME,UnBCL::String *,PITR::_VERSION_DATA *)

- ea: `0x180021458`
- end: `0x180021b33`
- name: `?pWriteSnapshotData@@YAJPEAUHKEY__@@PEAVString@UnBCL@@U_FILETIME@@21PEAU_VERSION_DATA@PITR@@@Z`
- size: `1755`
- prototype: `__int64 __fastcall(HKEY hKey, struct UnBCL::String *, struct _FILETIME, struct _FILETIME, struct UnBCL::String *, struct PITR::_VERSION_DATA *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x18000a5f0`

## callees

- `0x180009e04`
- `0x18001def0`
- `0x180021458`
- `0x18003af54`
- `0x18003b040`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021577`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002162e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021577`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002162e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021581`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021638`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021581`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180021638`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002158b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002176f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002181b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002189d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800214e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002158b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800215a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002176f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002181b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002189d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800218b2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021932`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021947`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800219f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021a94`
- `WDSCORE!CurrentIP` at `0x1800214f1`
- `WDSCORE!CurrentIP` at `0x1800215a8`
- `WDSCORE!CurrentIP` at `0x18002165f`
- `WDSCORE!CurrentIP` at `0x1800216f5`
- `WDSCORE!CurrentIP` at `0x18002178c`
- `WDSCORE!CurrentIP` at `0x180021823`
- `WDSCORE!CurrentIP` at `0x1800218ba`
- `WDSCORE!CurrentIP` at `0x18002194f`
- `WDSCORE!CurrentIP` at `0x1800219f8`
- `WDSCORE!CurrentIP` at `0x180021a9c`
- `WDSCORE!CurrentIP` at `0x1800214f1`
- `WDSCORE!CurrentIP` at `0x1800215a8`
- `WDSCORE!CurrentIP` at `0x18002165f`
- `WDSCORE!CurrentIP` at `0x1800216f5`
- `WDSCORE!CurrentIP` at `0x18002178c`
- `WDSCORE!CurrentIP` at `0x180021823`
- `WDSCORE!CurrentIP` at `0x1800218ba`
- `WDSCORE!CurrentIP` at `0x18002194f`
- `WDSCORE!CurrentIP` at `0x1800219f8`
- `WDSCORE!CurrentIP` at `0x180021a9c`
- `WDSCORE!WdsSetupLogMessageW` at `0x180021b07`
- `WDSCORE!WdsSetupLogMessageW` at `0x180021b07`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800214b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800214fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800215b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002166b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021701`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021798`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002182f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800218c6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002195b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021a04`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021a5f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021aa8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800214b8`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800214fd`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800215b4`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002166b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021701`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021798`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002182f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x1800218c6`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x18002195b`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021a04`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021a5f`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180021aa8`

## string_xrefs

- `0x180021539`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800215f0`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800216a7`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18002173d`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x1800217d4`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18002186b`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180021902`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180021997`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180021a40`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x180021ae4`: `base\diagnosis\srt\pitr\dll\src\pitr.cpp`
- `0x18002151f`: `pWriteSnapshotData`
- `0x1800215d6`: `pWriteSnapshotData`
- `0x18002168d`: `pWriteSnapshotData`
- `0x180021723`: `pWriteSnapshotData`
- `0x1800217ba`: `pWriteSnapshotData`
- `0x180021851`: `pWriteSnapshotData`
- `0x1800218e8`: `pWriteSnapshotData`
- `0x18002197d`: `pWriteSnapshotData`
- `0x180021a26`: `pWriteSnapshotData`
- `0x180021aca`: `pWriteSnapshotData`
- `0x180021506`: `Failed to write snapshot Id %s. Error: 0x%08X`
- `0x1800215bd`: `Failed to write snapshot time (UTC) for %s. Error: 0x%08X`
- `0x180021674`: `Failed to write snapshot time (Local) for %s. Error: 0x%08X`
- `0x18002170a`: `Failed to write OS major for %s. Error: 0x%08X`
- `0x1800217a1`: `Failed to write OS minor for %s. Error: 0x%08X`
- `0x180021838`: `Failed to write OS build for %s. Error: 0x%08X`
- `0x1800218cf`: `Failed to write OS revision for %s. Error: 0x%08X`
- `0x180021964`: `Failed to write OS branch for %s. Error: 0x%08X`
- `0x180021a0d`: `Failed to write OS edition ID for %s. Error: 0x%08X`
- `0x180021ab1`: `Failed to write time zone for %s. Error: 0x%08X`

## pseudocode

```c
__int64 __fastcall pWriteSnapshotData(
        HKEY hKey,
        struct UnBCL::String *a2,
        struct _FILETIME a3,
        struct _FILETIME a4,
        struct UnBCL::String *a5,
        struct PITR::_VERSION_DATA *a6)
{
  const unsigned __int16 *CString; // rax
  __int64 v9; // rdx
  signed int v10; // eax
  unsigned int v11; // esi
  DWORD v12; // edi
  __int64 v13; // rbx
  const char *v14; // rax
  struct tagLOG_PARTIAL_MSG *v15; // rax
  LSTATUS v16; // ebx
  signed int LastError; // eax
  DWORD v18; // edi
  __int64 v19; // rbx
  const char *v20; // rax
  struct tagLOG_PARTIAL_MSG *v21; // rax
  LSTATUS v22; // ebx
  signed int v23; // eax
  DWORD v24; // edi
  __int64 v25; // rbx
  const char *v26; // rax
  struct tagLOG_PARTIAL_MSG *v27; // rax
  signed int v28; // eax
  DWORD v29; // edi
  __int64 v30; // rbx
  const char *v31; // rax
  struct tagLOG_PARTIAL_MSG *v32; // rax
  signed int v33; // eax
  DWORD v34; // edi
  __int64 v35; // rbx
  const char *v36; // rax
  struct tagLOG_PARTIAL_MSG *v37; // rax
  signed int v38; // eax
  DWORD v39; // edi
  __int64 v40; // rbx
  const char *v41; // rax
  struct tagLOG_PARTIAL_MSG *v42; // rax
  __int64 v43; // rdx
  signed int v44; // eax
  DWORD v45; // edi
  __int64 v46; // rbx
  const char *v47; // rax
  struct tagLOG_PARTIAL_MSG *v48; // rax
  signed int v49; // eax
  DWORD v50; // edi
  __int64 v51; // rbx
  const char *v52; // rax
  struct tagLOG_PARTIAL_MSG *v53; // rax
  __int64 v54; // rdx
  signed int v55; // eax
  DWORD v56; // edi
  __int64 v57; // rbx
  const char *v58; // rax
  struct tagLOG_PARTIAL_MSG *v59; // rax
  const unsigned __int16 *v60; // rax
  __int64 v61; // rdx
  signed int v62; // eax
  DWORD v63; // edi
  __int64 v64; // rbx
  const char *v65; // rax
  struct tagLOG_PARTIAL_MSG *v66; // rax
  BYTE Data[8]; // [rsp+60h] [rbp-58h] BYREF
  BYTE lpData[8]; // [rsp+68h] [rbp-50h] BYREF

  *(struct _FILETIME *)Data = a3;
  *(struct _FILETIME *)lpData = a4;
  if ( !hKey || !a2 || !a5 )
    return 2147942487LL;
  CString = UnBCL::String::get_CString(a2);
  if ( (unsigned int)RegSetString(hKey, v9, L"Id", CString) )
  {
    v16 = RegSetValueExW(hKey, L"TimeUTC", 0, 3u, Data, 8u);
    SetLastError(v16);
    if ( v16 )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      v18 = GetLastError();
      v19 = CurrentIP();
      v20 = (const char *)UnBCL::String::get_CString(a2);
      v21 = ConstructPartialMsgW(0x2000000u, "Failed to write snapshot time (UTC) for %s. Error: 0x%08X", v20, v11);
      WdsSetupLogMessageW(
        v21,
        0,
        L"D",
        0,
        685,
        L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
        L"pWriteSnapshotData",
        v19,
        v18,
        0,
        0);
    }
    else
    {
      v22 = RegSetValueExW(hKey, L"TimeLocal", 0, 3u, lpData, 8u);
      SetLastError(v22);
      if ( v22 )
      {
        v23 = GetLastError();
        v11 = v23;
        if ( v23 > 0 )
          v11 = (unsigned __int16)v23 | 0x80070000;
        v24 = GetLastError();
        v25 = CurrentIP();
        v26 = (const char *)UnBCL::String::get_CString(a2);
        v27 = ConstructPartialMsgW(0x2000000u, "Failed to write snapshot time (Local) for %s. Error: 0x%08X", v26, v11);
        WdsSetupLogMessageW(
          v27,
          0,
          L"D",
          0,
          691,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"pWriteSnapshotData",
          v25,
          v24,
          0,
          0);
      }
      else if ( RegSetDword(hKey, 0, L"OSMajor", *(_DWORD *)a6) )
      {
        if ( RegSetDword(hKey, 0, L"OSMinor", *((_DWORD *)a6 + 1)) )
        {
          if ( RegSetDword(hKey, 0, L"Build", *((_DWORD *)a6 + 2)) )
          {
            if ( RegSetDword(hKey, 0, L"Revision", *((_DWORD *)a6 + 3)) )
            {
              if ( (unsigned int)RegSetString(hKey, v43, L"Branch", *((_QWORD *)a6 + 2)) )
              {
                if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl)
                  || (unsigned int)RegSetString(hKey, v54, L"EditionID", *((_QWORD *)a6 + 3)) )
                {
                  v11 = 0;
                  v60 = UnBCL::String::get_CString(a5);
                  if ( !(unsigned int)RegSetString(hKey, v61, L"TimeZone", v60) )
                  {
                    v62 = GetLastError();
                    v11 = v62;
                    if ( v62 > 0 )
                      v11 = (unsigned __int16)v62 | 0x80070000;
                    v63 = GetLastError();
                    v64 = CurrentIP();
                    v65 = (const char *)UnBCL::String::get_CString(a2);
                    v66 = ConstructPartialMsgW(0x2000000u, "Failed to write time zone for %s. Error: 0x%08X", v65, v11);
                    WdsSetupLogMessageW(
                      v66,
                      0,
                      L"D",
                      0,
                      736,
                      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                      L"pWriteSnapshotData",
                      v64,
                      v63,
                      0,
                      0);
                  }
                }
                else
                {
                  v55 = GetLastError();
                  v11 = v55;
                  if ( v55 > 0 )
                    v11 = (unsigned __int16)v55 | 0x80070000;
                  v56 = GetLastError();
                  v57 = CurrentIP();
                  v58 = (const char *)UnBCL::String::get_CString(a2);
                  v59 = ConstructPartialMsgW(
                          0x2000000u,
                          "Failed to write OS edition ID for %s. Error: 0x%08X",
                          v58,
                          v11);
                  WdsSetupLogMessageW(
                    v59,
                    0,
                    L"D",
                    0,
                    729,
                    L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                    L"pWriteSnapshotData",
                    v57,
                    v56,
                    0,
                    0);
                }
              }
              else
              {
                v49 = GetLastError();
                v11 = v49;
                if ( v49 > 0 )
                  v11 = (unsigned __int16)v49 | 0x80070000;
                v50 = GetLastError();
                v51 = CurrentIP();
                v52 = (const char *)UnBCL::String::get_CString(a2);
                v53 = ConstructPartialMsgW(0x2000000u, "Failed to write OS branch for %s. Error: 0x%08X", v52, v11);
                WdsSetupLogMessageW(
                  v53,
                  0,
                  L"D",
                  0,
                  721,
                  L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                  L"pWriteSnapshotData",
                  v51,
                  v50,
                  0,
                  0);
              }
            }
            else
            {
              v44 = GetLastError();
              v11 = v44;
              if ( v44 > 0 )
                v11 = (unsigned __int16)v44 | 0x80070000;
              v45 = GetLastError();
              v46 = CurrentIP();
              v47 = (const char *)UnBCL::String::get_CString(a2);
              v48 = ConstructPartialMsgW(0x2000000u, "Failed to write OS revision for %s. Error: 0x%08X", v47, v11);
              WdsSetupLogMessageW(
                v48,
                0,
                L"D",
                0,
                715,
                L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
                L"pWriteSnapshotData",
                v46,
                v45,
                0,
                0);
            }
          }
          else
          {
            v38 = GetLastError();
            v11 = v38;
            if ( v38 > 0 )
              v11 = (unsigned __int16)v38 | 0x80070000;
            v39 = GetLastError();
            v40 = CurrentIP();
            v41 = (const char *)UnBCL::String::get_CString(a2);
            v42 = ConstructPartialMsgW(0x2000000u, "Failed to write OS build for %s. Error: 0x%08X", v41, v11);
            WdsSetupLogMessageW(
              v42,
              0,
              L"D",
              0,
              709,
              L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
              L"pWriteSnapshotData",
              v40,
              v39,
              0,
              0);
          }
        }
        else
        {
          v33 = GetLastError();
          v11 = v33;
          if ( v33 > 0 )
            v11 = (unsigned __int16)v33 | 0x80070000;
          v34 = GetLastError();
          v35 = CurrentIP();
          v36 = (const char *)UnBCL::String::get_CString(a2);
          v37 = ConstructPartialMsgW(0x2000000u, "Failed to write OS minor for %s. Error: 0x%08X", v36, v11);
          WdsSetupLogMessageW(
            v37,
            0,
            L"D",
            0,
            703,
            L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
            L"pWriteSnapshotData",
            v35,
            v34,
            0,
            0);
        }
      }
      else
      {
        v28 = GetLastError();
        v11 = v28;
        if ( v28 > 0 )
          v11 = (unsigned __int16)v28 | 0x80070000;
        v29 = GetLastError();
        v30 = CurrentIP();
        v31 = (const char *)UnBCL::String::get_CString(a2);
        v32 = ConstructPartialMsgW(0x2000000u, "Failed to write OS major for %s. Error: 0x%08X", v31, v11);
        WdsSetupLogMessageW(
          v32,
          0,
          L"D",
          0,
          697,
          L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
          L"pWriteSnapshotData",
          v30,
          v29,
          0,
          0);
      }
    }
  }
  else
  {
    v10 = GetLastError();
    v11 = v10;
    if ( v10 > 0 )
      v11 = (unsigned __int16)v10 | 0x80070000;
    v12 = GetLastError();
    v13 = CurrentIP();
    v14 = (const char *)UnBCL::String::get_CString(a2);
    v15 = ConstructPartialMsgW(0x2000000u, "Failed to write snapshot Id %s. Error: 0x%08X", v14, v11);
    WdsSetupLogMessageW(
      v15,
      0,
      L"D",
      0,
      679,
      L"base\\diagnosis\\srt\\pitr\\dll\\src\\pitr.cpp",
      L"pWriteSnapshotData",
      v13,
      v12,
      0,
      0);
  }
  return v11;
}

```

## disassembly

```asm
0x180021458  push    rbx
0x18002145a  push    rbp
0x18002145b  push    rsi
0x18002145c  push    rdi
0x18002145d  push    r14
0x18002145f  push    r15
0x180021461  sub     rsp, 88h
0x180021468  mov     rax, cs:__security_cookie
0x18002146f  xor     rax, rsp
0x180021472  mov     [rsp+0B8h+var_48], rax
0x180021477  mov     rsi, [rsp+0B8h+arg_28]
0x18002147f  xor     r15d, r15d
0x180021482  mov     r14, [rsp+0B8h+arg_20]
0x18002148a  mov     rbp, rdx
0x18002148d  mov     qword ptr [rsp+0B8h+Data], r8
0x180021492  mov     rdi, rcx
0x180021495  mov     qword ptr [rsp+0B8h+var_50], r9
0x18002149a  test    rcx, rcx
0x18002149d  jz      loc_180021B11
0x1800214a3  test    rdx, rdx
0x1800214a6  jz      loc_180021B11
0x1800214ac  test    r14, r14
0x1800214af  jz      loc_180021B11
0x1800214b5  mov     rcx, rdx
0x1800214b8  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800214be  lea     r8, aId; "Id"
0x1800214c5  mov     rcx, rdi
0x1800214c8  mov     r9, rax
0x1800214cb  call    RegSetString
0x1800214d0  test    eax, eax
0x1800214d2  jnz     short loc_180021552
0x1800214d4  call    cs:__imp_GetLastError
0x1800214da  mov     esi, eax
0x1800214dc  test    eax, eax
0x1800214de  jle     short loc_1800214E9
0x1800214e0  movzx   esi, ax
0x1800214e3  or      esi, 80070000h
0x1800214e9  call    cs:__imp_GetLastError
0x1800214ef  mov     edi, eax
0x1800214f1  call    cs:__imp_CurrentIP
0x1800214f7  mov     rcx, rbp
0x1800214fa  mov     rbx, rax
0x1800214fd  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180021503  mov     r9d, esi
0x180021506  lea     rdx, aFailedToWriteS_2; "Failed to write snapshot Id %s. Error: "...
0x18002150d  mov     r8, rax
0x180021510  mov     ecx, 2000000h; unsigned int
0x180021515  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002151a  mov     [rsp+0B8h+var_68], r15d
0x18002151f  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x180021526  mov     [rsp+0B8h+var_70], r15
0x18002152b  mov     [rsp+0B8h+var_78], edi
0x18002152f  mov     [rsp+0B8h+var_80], rbx
0x180021534  mov     [rsp+0B8h+var_88], rcx
0x180021539  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180021540  mov     qword ptr [rsp+0B8h+cbData], rcx
0x180021545  mov     dword ptr [rsp+0B8h+lpData], 2A7h
0x18002154d  jmp     loc_180021AF8
0x180021552  lea     rax, [rsp+0B8h+Data]
0x180021557  mov     [rsp+0B8h+cbData], 8; cbData
0x18002155f  mov     r9d, 3; dwType
0x180021565  mov     [rsp+0B8h+lpData], rax; lpData
0x18002156a  xor     r8d, r8d; Reserved
0x18002156d  lea     rdx, aTimeutc; "TimeUTC"
0x180021574  mov     rcx, rdi; hKey
0x180021577  call    cs:__imp_RegSetValueExW
0x18002157d  mov     ecx, eax; dwErrCode
0x18002157f  mov     ebx, eax
0x180021581  call    cs:__imp_SetLastError
0x180021587  test    ebx, ebx
0x180021589  jz      short loc_180021609
0x18002158b  call    cs:__imp_GetLastError
0x180021591  mov     esi, eax
0x180021593  test    eax, eax
0x180021595  jle     short loc_1800215A0
0x180021597  movzx   esi, ax
0x18002159a  or      esi, 80070000h
0x1800215a0  call    cs:__imp_GetLastError
0x1800215a6  mov     edi, eax
0x1800215a8  call    cs:__imp_CurrentIP
0x1800215ae  mov     rcx, rbp
0x1800215b1  mov     rbx, rax
0x1800215b4  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800215ba  mov     r9d, esi
0x1800215bd  lea     rdx, aFailedToWriteS_1; "Failed to write snapshot time (UTC) for"...
0x1800215c4  mov     r8, rax
0x1800215c7  mov     ecx, 2000000h; unsigned int
0x1800215cc  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800215d1  mov     [rsp+0B8h+var_68], r15d
0x1800215d6  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x1800215dd  mov     [rsp+0B8h+var_70], r15
0x1800215e2  mov     [rsp+0B8h+var_78], edi
0x1800215e6  mov     [rsp+0B8h+var_80], rbx
0x1800215eb  mov     [rsp+0B8h+var_88], rcx
0x1800215f0  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800215f7  mov     qword ptr [rsp+0B8h+cbData], rcx
0x1800215fc  mov     dword ptr [rsp+0B8h+lpData], 2ADh
0x180021604  jmp     loc_180021AF8
0x180021609  lea     rax, [rsp+0B8h+var_50]
0x18002160e  mov     [rsp+0B8h+cbData], 8; cbData
0x180021616  mov     r9d, 3; dwType
0x18002161c  mov     [rsp+0B8h+lpData], rax; lpData
0x180021621  xor     r8d, r8d; Reserved
0x180021624  lea     rdx, aTimelocal; "TimeLocal"
0x18002162b  mov     rcx, rdi; hKey
0x18002162e  call    cs:__imp_RegSetValueExW
0x180021634  mov     ecx, eax; dwErrCode
0x180021636  mov     ebx, eax
0x180021638  call    cs:__imp_SetLastError
0x18002163e  test    ebx, ebx
0x180021640  jz      short loc_1800216C0
0x180021642  call    cs:__imp_GetLastError
0x180021648  mov     esi, eax
0x18002164a  test    eax, eax
0x18002164c  jle     short loc_180021657
0x18002164e  movzx   esi, ax
0x180021651  or      esi, 80070000h
0x180021657  call    cs:__imp_GetLastError
0x18002165d  mov     edi, eax
0x18002165f  call    cs:__imp_CurrentIP
0x180021665  mov     rcx, rbp
0x180021668  mov     rbx, rax
0x18002166b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180021671  mov     r9d, esi
0x180021674  lea     rdx, aFailedToWriteS_0; "Failed to write snapshot time (Local) f"...
0x18002167b  mov     r8, rax
0x18002167e  mov     ecx, 2000000h; unsigned int
0x180021683  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180021688  mov     [rsp+0B8h+var_68], r15d
0x18002168d  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x180021694  mov     [rsp+0B8h+var_70], r15
0x180021699  mov     [rsp+0B8h+var_78], edi
0x18002169d  mov     [rsp+0B8h+var_80], rbx
0x1800216a2  mov     [rsp+0B8h+var_88], rcx
0x1800216a7  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800216ae  mov     qword ptr [rsp+0B8h+cbData], rcx
0x1800216b3  mov     dword ptr [rsp+0B8h+lpData], 2B3h
0x1800216bb  jmp     loc_180021AF8
0x1800216c0  mov     r9d, [rsi]
0x1800216c3  lea     r8, aOsmajor; "OSMajor"
0x1800216ca  xor     edx, edx
0x1800216cc  mov     rcx, rdi
0x1800216cf  call    RegSetDword
0x1800216d4  test    eax, eax
0x1800216d6  jnz     short loc_180021756
0x1800216d8  call    cs:__imp_GetLastError
0x1800216de  mov     esi, eax
0x1800216e0  test    eax, eax
0x1800216e2  jle     short loc_1800216ED
0x1800216e4  movzx   esi, ax
0x1800216e7  or      esi, 80070000h
0x1800216ed  call    cs:__imp_GetLastError
0x1800216f3  mov     edi, eax
0x1800216f5  call    cs:__imp_CurrentIP
0x1800216fb  mov     rcx, rbp
0x1800216fe  mov     rbx, rax
0x180021701  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180021707  mov     r9d, esi
0x18002170a  lea     rdx, aFailedToWriteO_0; "Failed to write OS major for %s. Error:"...
0x180021711  mov     r8, rax
0x180021714  mov     ecx, 2000000h; unsigned int
0x180021719  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002171e  mov     [rsp+0B8h+var_68], r15d
0x180021723  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x18002172a  mov     [rsp+0B8h+var_70], r15
0x18002172f  mov     [rsp+0B8h+var_78], edi
0x180021733  mov     [rsp+0B8h+var_80], rbx
0x180021738  mov     [rsp+0B8h+var_88], rcx
0x18002173d  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180021744  mov     qword ptr [rsp+0B8h+cbData], rcx
0x180021749  mov     dword ptr [rsp+0B8h+lpData], 2B9h
0x180021751  jmp     loc_180021AF8
0x180021756  mov     r9d, [rsi+4]
0x18002175a  lea     r8, aOsminor; "OSMinor"
0x180021761  xor     edx, edx
0x180021763  mov     rcx, rdi
0x180021766  call    RegSetDword
0x18002176b  test    eax, eax
0x18002176d  jnz     short loc_1800217ED
0x18002176f  call    cs:__imp_GetLastError
0x180021775  mov     esi, eax
0x180021777  test    eax, eax
0x180021779  jle     short loc_180021784
0x18002177b  movzx   esi, ax
0x18002177e  or      esi, 80070000h
0x180021784  call    cs:__imp_GetLastError
0x18002178a  mov     edi, eax
0x18002178c  call    cs:__imp_CurrentIP
0x180021792  mov     rcx, rbp
0x180021795  mov     rbx, rax
0x180021798  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x18002179e  mov     r9d, esi
0x1800217a1  lea     rdx, aFailedToWriteO_4; "Failed to write OS minor for %s. Error:"...
0x1800217a8  mov     r8, rax
0x1800217ab  mov     ecx, 2000000h; unsigned int
0x1800217b0  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800217b5  mov     [rsp+0B8h+var_68], r15d
0x1800217ba  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x1800217c1  mov     [rsp+0B8h+var_70], r15
0x1800217c6  mov     [rsp+0B8h+var_78], edi
0x1800217ca  mov     [rsp+0B8h+var_80], rbx
0x1800217cf  mov     [rsp+0B8h+var_88], rcx
0x1800217d4  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x1800217db  mov     qword ptr [rsp+0B8h+cbData], rcx
0x1800217e0  mov     dword ptr [rsp+0B8h+lpData], 2BFh
0x1800217e8  jmp     loc_180021AF8
0x1800217ed  mov     r9d, [rsi+8]
0x1800217f1  lea     r8, aBuild; "Build"
0x1800217f8  xor     edx, edx
0x1800217fa  mov     rcx, rdi
0x1800217fd  call    RegSetDword
0x180021802  test    eax, eax
0x180021804  jnz     short loc_180021884
0x180021806  call    cs:__imp_GetLastError
0x18002180c  mov     esi, eax
0x18002180e  test    eax, eax
0x180021810  jle     short loc_18002181B
0x180021812  movzx   esi, ax
0x180021815  or      esi, 80070000h
0x18002181b  call    cs:__imp_GetLastError
0x180021821  mov     edi, eax
0x180021823  call    cs:__imp_CurrentIP
0x180021829  mov     rcx, rbp
0x18002182c  mov     rbx, rax
0x18002182f  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180021835  mov     r9d, esi
0x180021838  lea     rdx, aFailedToWriteO_1; "Failed to write OS build for %s. Error:"...
0x18002183f  mov     r8, rax
0x180021842  mov     ecx, 2000000h; unsigned int
0x180021847  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18002184c  mov     [rsp+0B8h+var_68], r15d
0x180021851  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x180021858  mov     [rsp+0B8h+var_70], r15
0x18002185d  mov     [rsp+0B8h+var_78], edi
0x180021861  mov     [rsp+0B8h+var_80], rbx
0x180021866  mov     [rsp+0B8h+var_88], rcx
0x18002186b  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180021872  mov     qword ptr [rsp+0B8h+cbData], rcx
0x180021877  mov     dword ptr [rsp+0B8h+lpData], 2C5h
0x18002187f  jmp     loc_180021AF8
0x180021884  mov     r9d, [rsi+0Ch]
0x180021888  lea     r8, aRevision; "Revision"
0x18002188f  xor     edx, edx
0x180021891  mov     rcx, rdi
0x180021894  call    RegSetDword
0x180021899  test    eax, eax
0x18002189b  jnz     short loc_18002191B
0x18002189d  call    cs:__imp_GetLastError
0x1800218a3  mov     esi, eax
0x1800218a5  test    eax, eax
0x1800218a7  jle     short loc_1800218B2
0x1800218a9  movzx   esi, ax
0x1800218ac  or      esi, 80070000h
0x1800218b2  call    cs:__imp_GetLastError
0x1800218b8  mov     edi, eax
0x1800218ba  call    cs:__imp_CurrentIP
0x1800218c0  mov     rcx, rbp
0x1800218c3  mov     rbx, rax
0x1800218c6  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x1800218cc  mov     r9d, esi
0x1800218cf  lea     rdx, aFailedToWriteO_3; "Failed to write OS revision for %s. Err"...
0x1800218d6  mov     r8, rax
0x1800218d9  mov     ecx, 2000000h; unsigned int
0x1800218de  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800218e3  mov     [rsp+0B8h+var_68], r15d
0x1800218e8  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x1800218ef  mov     [rsp+0B8h+var_70], r15
0x1800218f4  mov     [rsp+0B8h+var_78], edi
0x1800218f8  mov     [rsp+0B8h+var_80], rbx
0x1800218fd  mov     [rsp+0B8h+var_88], rcx
0x180021902  lea     rcx, aBaseDiagnosisS_1; "base\\diagnosis\\srt\\pitr\\dll\\src\\p"...
0x180021909  mov     qword ptr [rsp+0B8h+cbData], rcx
0x18002190e  mov     dword ptr [rsp+0B8h+lpData], 2CBh
0x180021916  jmp     loc_180021AF8
0x18002191b  mov     r9, [rsi+10h]
0x18002191f  lea     r8, aBranch; "Branch"
0x180021926  mov     rcx, rdi
0x180021929  call    RegSetString
0x18002192e  test    eax, eax
0x180021930  jnz     short loc_1800219B0
0x180021932  call    cs:__imp_GetLastError
0x180021938  mov     esi, eax
0x18002193a  test    eax, eax
0x18002193c  jle     short loc_180021947
0x18002193e  movzx   esi, ax
0x180021941  or      esi, 80070000h
0x180021947  call    cs:__imp_GetLastError
0x18002194d  mov     edi, eax
0x18002194f  call    cs:__imp_CurrentIP
0x180021955  mov     rcx, rbp
0x180021958  mov     rbx, rax
0x18002195b  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180021961  mov     r9d, esi
0x180021964  lea     rdx, aFailedToWriteO_2; "Failed to write OS branch for %s. Error"...
0x18002196b  mov     r8, rax
0x18002196e  mov     ecx, 2000000h; unsigned int
0x180021973  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180021978  mov     [rsp+0B8h+var_68], r15d
0x18002197d  lea     rcx, aPwritesnapshot; "pWriteSnapshotData"
0x180021984  mov     [rsp+0B8h+var_70], r15
  ... truncated ...
```
