# SPEnableGlobalLoggerSession(HKEY__ *,ushort const *,int,int,int,ulong,ulong,_LOGGER_SETTINGS const *)

- ea: `0x180377bcc`
- end: `0x1803788cf`
- name: `?SPEnableGlobalLoggerSession@@YAJPEAUHKEY__@@PEBGHHHKKPEBU_LOGGER_SETTINGS@@@Z`
- size: `3331`
- prototype: `__int64 __usercall@<rax>(HKEY@<rcx>, BYTE *lpData@<rdx>, int@<r8d>, int@<r9d>, int, unsigned int, unsigned int, const struct _LOGGER_SETTINGS *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x18022b040`

## callees

- `0x180057dec`
- `0x180377bcc`
- `0x18037d8bc`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180378623`
- `ADVAPI32!RegCloseKey` at `0x1803788a1`
- `ADVAPI32!RegCloseKey` at `0x180378623`
- `ADVAPI32!RegCloseKey` at `0x1803788a1`
- `ADVAPI32!RegSetValueExW` at `0x180377ef9`
- `ADVAPI32!RegSetValueExW` at `0x180377fdc`
- `ADVAPI32!RegSetValueExW` at `0x18037808d`
- `ADVAPI32!RegSetValueExW` at `0x180378153`
- `ADVAPI32!RegSetValueExW` at `0x1803781f5`
- `ADVAPI32!RegSetValueExW` at `0x180378298`
- `ADVAPI32!RegSetValueExW` at `0x18037833b`
- `ADVAPI32!RegSetValueExW` at `0x1803783df`
- `ADVAPI32!RegSetValueExW` at `0x1803784fc`
- `ADVAPI32!RegSetValueExW` at `0x180378591`
- `ADVAPI32!RegSetValueExW` at `0x180378812`
- `ADVAPI32!RegSetValueExW` at `0x180377ef9`
- `ADVAPI32!RegSetValueExW` at `0x180377fdc`
- `ADVAPI32!RegSetValueExW` at `0x18037808d`
- `ADVAPI32!RegSetValueExW` at `0x180378153`
- `ADVAPI32!RegSetValueExW` at `0x1803781f5`
- `ADVAPI32!RegSetValueExW` at `0x180378298`
- `ADVAPI32!RegSetValueExW` at `0x18037833b`
- `ADVAPI32!RegSetValueExW` at `0x1803783df`
- `ADVAPI32!RegSetValueExW` at `0x1803784fc`
- `ADVAPI32!RegSetValueExW` at `0x180378591`
- `ADVAPI32!RegSetValueExW` at `0x180378812`
- `ADVAPI32!RegCreateKeyExW` at `0x180377e4d`
- `ADVAPI32!RegCreateKeyExW` at `0x180378747`
- `ADVAPI32!RegCreateKeyExW` at `0x180377e4d`
- `ADVAPI32!RegCreateKeyExW` at `0x180378747`
- `KERNEL32!GetLastError` at `0x180377c1a`
- `KERNEL32!GetLastError` at `0x180377d7d`
- `KERNEL32!GetLastError` at `0x180377d96`
- `KERNEL32!GetLastError` at `0x180377db2`
- `KERNEL32!GetLastError` at `0x180377e64`
- `KERNEL32!GetLastError` at `0x180377f15`
- `KERNEL32!GetLastError` at `0x180377ff6`
- `KERNEL32!GetLastError` at `0x1803780a4`
- `KERNEL32!GetLastError` at `0x18037816a`
- `KERNEL32!GetLastError` at `0x18037820c`
- `KERNEL32!GetLastError` at `0x1803782af`
- `KERNEL32!GetLastError` at `0x180378352`
- `KERNEL32!GetLastError` at `0x1803783fb`
- `KERNEL32!GetLastError` at `0x180378458`
- `KERNEL32!GetLastError` at `0x180378513`
- `KERNEL32!GetLastError` at `0x1803785a8`
- `KERNEL32!GetLastError` at `0x180378679`
- `KERNEL32!GetLastError` at `0x18037868f`
- `KERNEL32!GetLastError` at `0x1803786ab`
- `KERNEL32!GetLastError` at `0x180378768`
- `KERNEL32!GetLastError` at `0x18037882b`
- `KERNEL32!GetLastError` at `0x180377c1a`
- `KERNEL32!GetLastError` at `0x180377d7d`
- `KERNEL32!GetLastError` at `0x180377d96`
- `KERNEL32!GetLastError` at `0x180377db2`
- `KERNEL32!GetLastError` at `0x180377e64`
- `KERNEL32!GetLastError` at `0x180377f15`
- `KERNEL32!GetLastError` at `0x180377ff6`
- `KERNEL32!GetLastError` at `0x1803780a4`
- `KERNEL32!GetLastError` at `0x18037816a`
- `KERNEL32!GetLastError` at `0x18037820c`
- `KERNEL32!GetLastError` at `0x1803782af`
- `KERNEL32!GetLastError` at `0x180378352`
- `KERNEL32!GetLastError` at `0x1803783fb`
- `KERNEL32!GetLastError` at `0x180378458`
- `KERNEL32!GetLastError` at `0x180378513`
- `KERNEL32!GetLastError` at `0x1803785a8`
- `KERNEL32!GetLastError` at `0x180378679`
- `KERNEL32!GetLastError` at `0x18037868f`
- `KERNEL32!GetLastError` at `0x1803786ab`
- `KERNEL32!GetLastError` at `0x180378768`
- `KERNEL32!GetLastError` at `0x18037882b`
- `unbcl!??7?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBA_NXZ` at `0x180377d6f`
- `unbcl!??7?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBA_NXZ` at `0x18037866b`
- `unbcl!??7?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBA_NXZ` at `0x180377d6f`
- `unbcl!??7?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBA_NXZ` at `0x18037866b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180377c05`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ` at `0x180377c05`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180377d5a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180378656`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180377d5a`
- `unbcl!??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z` at `0x180378656`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180377e13`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037870c`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x180377e13`
- `unbcl!??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ` at `0x18037870c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180377e1c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180378715`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180377e1c`
- `unbcl!?get_CString@String@UnBCL@@QEBAPEBGXZ` at `0x180378715`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180377d65`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180378661`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803788ac`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180377d65`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x180378661`
- `unbcl!??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ` at `0x1803788ac`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180377d4b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180378647`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180377d4b`
- `unbcl!??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z` at `0x180378647`
- `WDSCORE!WdsSetupLogMessageW` at `0x180377c7e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180377ecc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803784c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803787cf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180378892`
- `WDSCORE!WdsSetupLogMessageW` at `0x180377c7e`
- `WDSCORE!WdsSetupLogMessageW` at `0x180377ecc`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803784c2`
- `WDSCORE!WdsSetupLogMessageW` at `0x1803787cf`
- `WDSCORE!WdsSetupLogMessageW` at `0x180378892`
- `WDSCORE!CurrentIP` at `0x180377c22`
- `WDSCORE!CurrentIP` at `0x180377dba`
- `WDSCORE!CurrentIP` at `0x180377e6c`
- `WDSCORE!CurrentIP` at `0x180377f1d`
- `WDSCORE!CurrentIP` at `0x180377ffe`
- `WDSCORE!CurrentIP` at `0x1803780ac`
- `WDSCORE!CurrentIP` at `0x180378172`
- `WDSCORE!CurrentIP` at `0x180378214`
- `WDSCORE!CurrentIP` at `0x1803782b7`
- `WDSCORE!CurrentIP` at `0x18037835a`
- `WDSCORE!CurrentIP` at `0x180378403`
- `WDSCORE!CurrentIP` at `0x180378460`
- `WDSCORE!CurrentIP` at `0x18037851b`
- `WDSCORE!CurrentIP` at `0x1803785b0`
- `WDSCORE!CurrentIP` at `0x1803786b3`
- `WDSCORE!CurrentIP` at `0x180378770`
- `WDSCORE!CurrentIP` at `0x180378833`
- `WDSCORE!CurrentIP` at `0x180377c22`
- `WDSCORE!CurrentIP` at `0x180377dba`
- `WDSCORE!CurrentIP` at `0x180377e6c`
- `WDSCORE!CurrentIP` at `0x180377f1d`
- `WDSCORE!CurrentIP` at `0x180377ffe`
- `WDSCORE!CurrentIP` at `0x1803780ac`
- `WDSCORE!CurrentIP` at `0x180378172`
- `WDSCORE!CurrentIP` at `0x180378214`
- `WDSCORE!CurrentIP` at `0x1803782b7`
- `WDSCORE!CurrentIP` at `0x18037835a`
- `WDSCORE!CurrentIP` at `0x180378403`
- `WDSCORE!CurrentIP` at `0x180378460`
- `WDSCORE!CurrentIP` at `0x18037851b`
- `WDSCORE!CurrentIP` at `0x1803785b0`
- `WDSCORE!CurrentIP` at `0x1803786b3`
- `WDSCORE!CurrentIP` at `0x180378770`
- `WDSCORE!CurrentIP` at `0x180378833`

## string_xrefs

- `0x180377e78`: `Create reg key failed: 0x%x`
- `0x18037877c`: `Create reg key failed: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SPEnableGlobalLoggerSession(
        HKEY a1,
        BYTE *lpData,
        int a3,
        int a4,
        int a5,
        unsigned int a6,
        char a7,
        BYTE *lpDataa)
{
  DWORD LastError; // edi
  __int64 v13; // rbx
  struct tagLOG_PARTIAL_MSG *v14; // rax
  int v15; // eax
  int v16; // r12d
  int v17; // ecx
  int v18; // eax
  const BYTE *v19; // rbx
  struct UnBCL::String *CurrentControlSetKeyPath; // rax
  signed int v21; // eax
  bool v22; // sf
  signed int v23; // eax
  unsigned int v24; // esi
  DWORD v25; // edi
  __int64 v26; // rbx
  struct tagLOG_PARTIAL_MSG *v27; // rax
  UnBCL::String *v28; // rax
  const WCHAR *CString; // rax
  LSTATUS Key; // eax
  DWORD v31; // edi
  __int64 v32; // rbx
  struct tagLOG_PARTIAL_MSG *v33; // rax
  LSTATUS v34; // eax
  DWORD v35; // edi
  __int64 v36; // rbx
  struct tagLOG_PARTIAL_MSG *v37; // rax
  __int64 v38; // rax
  BYTE *v39; // r14
  __int64 v40; // rcx
  LSTATUS v41; // eax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // eax
  LSTATUS v46; // eax
  DWORD v47; // edi
  __int64 v48; // rbx
  struct tagLOG_PARTIAL_MSG *v49; // rax
  DWORD v50; // eax
  const BYTE *v51; // rcx
  LSTATUS v52; // eax
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  const BYTE *v56; // rax
  LSTATUS v57; // eax
  DWORD v58; // edi
  __int64 v59; // rbx
  struct tagLOG_PARTIAL_MSG *v60; // rax
  const BYTE *v61; // rax
  LSTATUS v62; // eax
  DWORD v63; // edi
  __int64 v64; // rbx
  struct tagLOG_PARTIAL_MSG *v65; // rax
  const BYTE *v66; // rax
  LSTATUS v67; // eax
  DWORD v68; // edi
  __int64 v69; // rbx
  struct tagLOG_PARTIAL_MSG *v70; // rax
  const BYTE *v71; // r15
  LSTATUS v72; // eax
  DWORD v73; // edi
  __int64 v74; // rbx
  struct tagLOG_PARTIAL_MSG *v75; // rax
  DWORD v76; // edi
  __int64 v77; // rbx
  struct tagLOG_PARTIAL_MSG *v78; // rax
  const BYTE *v79; // rax
  LSTATUS v80; // eax
  DWORD v81; // edi
  __int64 v82; // rbx
  struct tagLOG_PARTIAL_MSG *v83; // rax
  LSTATUS v84; // eax
  DWORD v85; // edi
  __int64 v86; // rbx
  struct tagLOG_PARTIAL_MSG *v87; // rax
  struct UnBCL::String *v88; // rax
  signed int v89; // eax
  bool v90; // sf
  signed int v91; // eax
  DWORD v92; // edi
  __int64 v93; // rbx
  struct tagLOG_PARTIAL_MSG *v94; // rax
  UnBCL::String *v95; // rax
  const WCHAR *v96; // rax
  LSTATUS v97; // eax
  unsigned int v98; // r15d
  DWORD v99; // edi
  __int64 v100; // rbx
  struct tagLOG_PARTIAL_MSG *v101; // rax
  const BYTE *v102; // r14
  LSTATUS v103; // eax
  DWORD v104; // edi
  __int64 v105; // rbx
  struct tagLOG_PARTIAL_MSG *v106; // rax
  HKEY hKey[2]; // [rsp+68h] [rbp-29h] BYREF
  _BYTE v109[16]; // [rsp+78h] [rbp-19h] BYREF
  _BYTE v110[64]; // [rsp+88h] [rbp-9h] BYREF
  int Data; // [rsp+E8h] [rbp+57h] BYREF

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v109);
  Data = 1;
  hKey[0] = 0;
  LastError = GetLastError();
  v13 = CurrentIP();
  v14 = ConstructPartialMsgW(0x4000000u, "Enabling GlobalLoggerSession");
  WdsSetupLogMessageW(
    v14,
    0,
    L"D",
    0,
    2024,
    L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
    L"SPEnableGlobalLoggerSession",
    v13,
    LastError,
    0,
    0);
  if ( a3 )
    dword_180887524 = 250;
  xmmword_18088AB48 = 0;
  xmmword_18088AB58 = 0;
  v15 = 0;
  v16 = a5;
  if ( (a7 & 1) != 0 )
  {
    v15 = 7;
    LODWORD(xmmword_18088AB48) = 7;
    if ( !a5 && !a4 )
    {
      v15 = 16777991;
      LODWORD(xmmword_18088AB48) = 16777991;
    }
  }
  v17 = v15 | 0x1000000;
  if ( (a7 & 2) != 0 )
    LODWORD(xmmword_18088AB48) = v15 | 0x1000000;
  else
    v17 = v15;
  v18 = v17 | 0x810;
  if ( (a7 & 4) != 0 )
    LODWORD(xmmword_18088AB48) = v17 | 0x810;
  else
    v18 = v17;
  if ( (a7 & 0x10) != 0 )
    LODWORD(xmmword_18088AB48) = v18 | 0x800000;
  v19 = (const BYTE *)&xmmword_18088AB48;
  if ( a6 )
    *((_DWORD *)&xmmword_18088AB48 + ((unsigned __int64)a6 >> 29)) |= a6 & 0x1FFFFFFF;
  CurrentControlSetKeyPath = pGetCurrentControlSetKeyPath(a1, L"\\Control\\WMI\\GlobalLogger");
  UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v110, CurrentControlSetKeyPath);
  UnBCL::SmartPtr<UnBCL::String>::operator=(v109, v110);
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v110);
  if ( (unsigned __int8)UnBCL::SmartPtr<UnBCL::String>::operator!(v109) )
  {
    v21 = GetLastError();
    v22 = v21 < 0;
    if ( v21 > 0 )
      v22 = 1;
    if ( v22 )
    {
      v23 = GetLastError();
      v24 = v23;
      if ( v23 > 0 )
        v24 = (unsigned __int16)v23 | 0x80070000;
    }
    else
    {
      v24 = -2147467259;
    }
    v25 = GetLastError();
    v26 = CurrentIP();
    v27 = ConstructPartialMsgW(0x2000000u, "Failed to get current control set value: 0x%x", v24);
    WdsSetupLogMessageW(
      v27,
      0,
      L"D",
      0,
      2046,
      L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
      L"SPEnableGlobalLoggerSession",
      v26,
      v25,
      0,
      0);
    goto LABEL_128;
  }
  v28 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v109);
  CString = UnBCL::String::get_CString(v28);
  Key = RegCreateKeyExW(a1, CString, 0, 0, 0, 0x2001Fu, 0, hKey, 0);
  v24 = Key;
  if ( Key )
  {
    if ( Key > 0 )
      v24 = (unsigned __int16)Key | 0x80070000;
    v31 = GetLastError();
    v32 = CurrentIP();
    v33 = ConstructPartialMsgW(0x2000000u, "Create reg key failed: 0x%x", v24);
    WdsSetupLogMessageW(
      v33,
      0,
      L"D",
      0,
      2067,
      L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
      L"SPEnableGlobalLoggerSession",
      v32,
      v31,
      0,
      0);
  }
  else
  {
    v34 = RegSetValueExW(hKey[0], L"Start", 0, 4u, (const BYTE *)&Data, 4u);
    v24 = v34;
    if ( v34 )
    {
      if ( v34 > 0 )
        v24 = (unsigned __int16)v34 | 0x80070000;
      v35 = GetLastError();
      v36 = CurrentIP();
      v37 = ConstructPartialMsgW(0x2000000u, "Set reg key value failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v37,
        0,
        L"D",
        0,
        2082,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v36,
        v35,
        0,
        0);
      goto LABEL_128;
    }
    v38 = -1;
    v39 = lpDataa;
    if ( !v16 )
    {
      if ( lpDataa )
      {
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)&lpDataa[2 * v40 + 60] );
        if ( v40 )
          lpData = lpDataa + 60;
      }
    }
    if ( lpData && *(_WORD *)lpData )
    {
      do
        ++v38;
      while ( *(_WORD *)&lpData[2 * v38] );
      v41 = RegSetValueExW(hKey[0], L"FileName", 0, 1u, lpData, 2 * v38 + 2);
      v24 = v41;
      if ( v41 )
      {
        if ( v41 > 0 )
          v24 = (unsigned __int16)v41 | 0x80070000;
        v42 = GetLastError();
        v43 = CurrentIP();
        v44 = ConstructPartialMsgW(0x2000000u, "Set reg key value failed: 0x%x", v24);
        WdsSetupLogMessageW(
          v44,
          0,
          L"D",
          0,
          2108,
          L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
          L"SPEnableGlobalLoggerSession",
          v43,
          v42,
          0,
          0);
        goto LABEL_128;
      }
    }
    if ( v39 && (v45 = *((_DWORD *)v39 + 10)) != 0 )
      v19 = (const BYTE *)*((_QWORD *)v39 + 4);
    else
      v45 = 32;
    v46 = RegSetValueExW(hKey[0], L"EnableKernelFlags", 0, 3u, v19, v45);
    v24 = v46;
    if ( v46 )
    {
      if ( v46 > 0 )
        v24 = (unsigned __int16)v46 | 0x80070000;
      v47 = GetLastError();
      v48 = CurrentIP();
      v49 = ConstructPartialMsgW(0x2000000u, "Set reg key value failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v49,
        0,
        L"D",
        0,
        2134,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v48,
        v47,
        0,
        0);
      goto LABEL_128;
    }
    if ( v39 && (v50 = *((_DWORD *)v39 + 14)) != 0 )
    {
      v51 = (const BYTE *)*((_QWORD *)v39 + 6);
    }
    else if ( v16 || a4 )
    {
      v51 = 0;
      v50 = 0;
    }
    else
    {
      v51 = &::Data;
      v50 = 4;
    }
    v52 = RegSetValueExW(hKey[0], L"StackWalkingFilter", 0, 3u, v51, v50);
    v24 = v52;
    if ( v52 )
    {
      if ( v52 > 0 )
        v24 = (unsigned __int16)v52 | 0x80070000;
      v53 = GetLastError();
      v54 = CurrentIP();
      v55 = ConstructPartialMsgW(0x2000000u, "Set reg key value StackWalkingFilter failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v55,
        0,
        L"D",
        0,
        2168,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v54,
        v53,
        0,
        0);
      goto LABEL_128;
    }
    if ( !v39 || (v56 = v39, !*(_DWORD *)v39) )
      v56 = (const BYTE *)&dword_18062A9EC;
    v57 = RegSetValueExW(hKey[0], L"BufferSize", 0, 4u, v56, 4u);
    v24 = v57;
    if ( v57 )
    {
      if ( v57 > 0 )
        v24 = (unsigned __int16)v57 | 0x80070000;
      v58 = GetLastError();
      v59 = CurrentIP();
      v60 = ConstructPartialMsgW(0x2000000u, "Set reg key value BufferSize failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v60,
        0,
        L"D",
        0,
        2192,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v59,
        v58,
        0,
        0);
      goto LABEL_128;
    }
    if ( !v39 || (v61 = v39 + 4, !*((_DWORD *)v39 + 1)) )
      v61 = (const BYTE *)byte_18062A9E8;
    v62 = RegSetValueExW(hKey[0], L"MinimumBuffers", 0, 4u, v61, 4u);
    v24 = v62;
    if ( v62 )
    {
      if ( v62 > 0 )
        v24 = (unsigned __int16)v62 | 0x80070000;
      v63 = GetLastError();
      v64 = CurrentIP();
      v65 = ConstructPartialMsgW(0x2000000u, "Set reg key value failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v65,
        0,
        L"D",
        0,
        2216,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v64,
        v63,
        0,
        0);
      goto LABEL_128;
    }
    if ( !v39 || (v66 = v39 + 8, !*((_DWORD *)v39 + 2)) )
      v66 = (const BYTE *)&dword_18062A9E4;
    v67 = RegSetValueExW(hKey[0], L"MaximumBuffers", 0, 4u, v66, 4u);
    v24 = v67;
    if ( v67 )
    {
      if ( v67 > 0 )
        v24 = (unsigned __int16)v67 | 0x80070000;
      v68 = GetLastError();
      v69 = CurrentIP();
      v70 = ConstructPartialMsgW(0x2000000u, "Set reg key value MaximumBuffers failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v70,
        0,
        L"D",
        0,
        2240,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v69,
        v68,
        0,
        0);
      goto LABEL_128;
    }
    if ( !v39 || (v71 = v39 + 12, !*((_DWORD *)v39 + 3)) )
      v71 = (const BYTE *)&dword_180887524;
    v72 = RegSetValueExW(hKey[0], L"MaxFileSize", 0, 4u, v71, 4u);
    v24 = v72;
    if ( v72 )
    {
      if ( v72 > 0 )
        v24 = (unsigned __int16)v72 | 0x80070000;
      v73 = GetLastError();
      v74 = CurrentIP();
      v75 = ConstructPartialMsgW(0x2000000u, "Set reg key value MaxFileSize failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v75,
        0,
        L"D",
        0,
        2264,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v74,
        v73,
        0,
        0);
      goto LABEL_128;
    }
    v76 = GetLastError();
    v77 = CurrentIP();
    v78 = ConstructPartialMsgW(0x4000000u, "MaxFileSize is set as %dMB", *(_DWORD *)v71);
    WdsSetupLogMessageW(
      v78,
      0,
      L"D",
      0,
      2267,
      L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
      L"SPEnableGlobalLoggerSession",
      v77,
      v76,
      0,
      0);
    if ( !v39 || (v79 = v39 + 16, !*((_DWORD *)v39 + 4)) )
      v79 = (const BYTE *)byte_18062A9E0;
    v80 = RegSetValueExW(hKey[0], L"LogFileMode", 0, 4u, v79, 4u);
    v24 = v80;
    if ( v80 )
    {
      if ( v80 > 0 )
        v24 = (unsigned __int16)v80 | 0x80070000;
      v81 = GetLastError();
      v82 = CurrentIP();
      v83 = ConstructPartialMsgW(0x2000000u, "Set reg key value LogFileMode failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v83,
        0,
        L"D",
        0,
        2289,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v82,
        v81,
        0,
        0);
      goto LABEL_128;
    }
    v84 = RegSetValueExW(hKey[0], L"FileMax", 0, 4u, &byte_18062A9DC, 4u);
    v24 = v84;
    if ( v84 )
    {
      if ( v84 > 0 )
        v24 = (unsigned __int16)v84 | 0x80070000;
      v85 = GetLastError();
      v86 = CurrentIP();
      v87 = ConstructPartialMsgW(0x2000000u, "Set reg key value FileMax failed: 0x%x", v24);
      WdsSetupLogMessageW(
        v87,
        0,
        L"D",
        0,
        2306,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v86,
        v85,
        0,
        0);
      goto LABEL_128;
    }
    v24 = 0;
    if ( v16 || a4 )
    {
LABEL_128:
      if ( hKey[0] )
        RegCloseKey(hKey[0]);
      goto LABEL_130;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v88 = pGetCurrentControlSetKeyPath(a1, L"\\Control\\WMI\\Trace");
    UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(v110, v88);
    UnBCL::SmartPtr<UnBCL::String>::operator=(v109, v110);
    UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v110);
    if ( (unsigned __int8)UnBCL::SmartPtr<UnBCL::String>::operator!(v109) )
    {
      v89 = GetLastError();
      v90 = v89 < 0;
      if ( v89 > 0 )
        v90 = 1;
      if ( v90 )
      {
        v91 = GetLastError();
        v24 = v91;
        if ( v91 > 0 )
          v24 = (unsigned __int16)v91 | 0x80070000;
      }
      else
      {
        v24 = -2147467259;
      }
      v92 = GetLastError();
      v93 = CurrentIP();
      v94 = ConstructPartialMsgW(0x2000000u, "Failed to get current control set value: 0x%x", v24);
      WdsSetupLogMessageW(
        v94,
        0,
        L"D",
        0,
        2323,
        L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
        L"SPEnableGlobalLoggerSession",
        v93,
        v92,
        0,
        0);
      goto LABEL_128;
    }
    v95 = (UnBCL::String *)UnBCL::SmartPtr<UnBCL::String>::operator->(v109);
    v96 = UnBCL::String::get_CString(v95);
    v97 = RegCreateKeyExW(a1, v96, 0, 0, 0, 0x2001Fu, 0, hKey, 0);
    v98 = v97;
    if ( !v97 )
    {
      if ( !v39 || (v102 = v39 + 580, !*(_DWORD *)v102) )
        v102 = (const BYTE *)&dword_18062A9F4;
      v103 = RegSetValueExW(hKey[0], L"ProfileInterval", 0, 4u, v102, 4u);
      if ( v103 )
      {
        if ( v103 > 0 )
          v24 = (unsigned __int16)v103 | 0x80070000;
        else
          v24 = v103;
        v104 = GetLastError();
        v105 = CurrentIP();
        v106 = ConstructPartialMsgW(0x2000000u, "Set reg key value ProfileInterval failed: 0x%x", v24);
        WdsSetupLogMessageW(
          v106,
          0,
          L"D",
          0,
          2365,
          L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
          L"SPEnableGlobalLoggerSession",
          v105,
          v104,
          0,
          0);
      }
      goto LABEL_128;
    }
    if ( v97 > 0 )
      v98 = (unsigned __int16)v97 | 0x80070000;
    v99 = GetLastError();
    v100 = CurrentIP();
    v101 = ConstructPartialMsgW(0x3000000u, "Create reg key failed: 0x%x", v98);
    WdsSetupLogMessageW(
      v101,
      0,
      L"D",
      0,
      2341,
      L"base\\ntsetup\\setupplatform\\lib\\tracing\\tracing.cpp",
      L"SPEnableGlobalLoggerSession",
      v100,
      v99,
      0,
      0);
    v24 = v98;
  }
LABEL_130:
  UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(v109);
  return v24;
}

```

## disassembly

```asm
0x180377bcc  mov     rax, rsp
0x180377bcf  mov     [rax+8], rcx
0x180377bd3  push    rbp
0x180377bd4  push    rsi
0x180377bd5  push    rdi
0x180377bd6  push    r12
0x180377bd8  push    r13
0x180377bda  push    r14
0x180377bdc  push    r15
0x180377bde  lea     rbp, [rax-3Fh]
0x180377be2  sub     rsp, 90h
0x180377be9  mov     [rbp+37h+var_58], 0FFFFFFFFFFFFFFFEh
0x180377bf1  mov     [rax+10h], rbx
0x180377bf5  mov     r13d, r9d
0x180377bf8  mov     esi, r8d
0x180377bfb  mov     r15, rdx
0x180377bfe  mov     r14, rcx
0x180377c01  lea     rcx, [rbp+37h+var_50]
0x180377c05  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(void)
0x180377c0b  nop
0x180377c0c  mov     [rbp+37h+Data], 1
0x180377c13  xor     r12d, r12d
0x180377c16  mov     [rbp+37h+hKey], r12
0x180377c1a  call    cs:__imp_GetLastError
0x180377c20  mov     edi, eax
0x180377c22  call    cs:__imp_CurrentIP
0x180377c28  mov     rbx, rax
0x180377c2b  lea     rdx, aEnablingGlobal; "Enabling GlobalLoggerSession"
0x180377c32  mov     ecx, 4000000h; unsigned int
0x180377c37  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180377c3c  mov     [rsp+50h], r12d
0x180377c41  mov     qword ptr [rsp+0C0h+var_78], r12
0x180377c46  mov     dword ptr [rsp+0C0h+lpdwDisposition], edi
0x180377c4a  mov     [rsp+0C0h+phkResult], rbx
0x180377c4f  lea     rcx, aSpenableglobal; "SPEnableGlobalLoggerSession"
0x180377c56  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x180377c5b  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x180377c62  mov     qword ptr [rsp+0C0h+samDesired], rcx
0x180377c67  mov     [rsp+0C0h+dwOptions], 7E8h
0x180377c6f  xor     r9d, r9d
0x180377c72  lea     r8, aD_0; "D"
0x180377c79  xor     edx, edx
0x180377c7b  mov     rcx, rax
0x180377c7e  call    cs:__imp_WdsSetupLogMessageW
0x180377c84  xor     edi, edi
0x180377c86  test    esi, esi
0x180377c88  jz      short loc_180377C94
0x180377c8a  mov     cs:dword_180887524, 0FAh
0x180377c94  xorps   xmm0, xmm0
0x180377c97  movups  cs:xmmword_18088AB48, xmm0
0x180377c9e  movups  cs:xmmword_18088AB58, xmm0
0x180377ca5  mov     eax, edi
0x180377ca7  mov     r8d, dword ptr [rbp+37h+arg_30]
0x180377cab  mov     r12d, [rbp+37h+arg_20]
0x180377caf  test    r8b, 1
0x180377cb3  jz      short loc_180377CD5
0x180377cb5  mov     eax, 7
0x180377cba  mov     dword ptr cs:xmmword_18088AB48, eax
0x180377cc0  test    r12d, r12d
0x180377cc3  jnz     short loc_180377CD5
0x180377cc5  test    r13d, r13d
0x180377cc8  jnz     short loc_180377CD5
0x180377cca  mov     eax, 1000307h
0x180377ccf  mov     dword ptr cs:xmmword_18088AB48, eax
0x180377cd5  mov     edx, r8d
0x180377cd8  mov     ecx, eax
0x180377cda  bts     ecx, 18h
0x180377cde  and     edx, 2
0x180377ce1  jz      short loc_180377CE9
0x180377ce3  mov     dword ptr cs:xmmword_18088AB48, ecx
0x180377ce9  test    edx, edx
0x180377ceb  cmovz   ecx, eax
0x180377cee  mov     edx, r8d
0x180377cf1  mov     eax, ecx
0x180377cf3  or      eax, 810h
0x180377cf8  and     edx, 4
0x180377cfb  jz      short loc_180377D03
0x180377cfd  mov     dword ptr cs:xmmword_18088AB48, eax
0x180377d03  test    edx, edx
0x180377d05  cmovz   eax, ecx
0x180377d08  test    r8b, 10h
0x180377d0c  jz      short loc_180377D18
0x180377d0e  bts     eax, 17h
0x180377d12  mov     dword ptr cs:xmmword_18088AB48, eax
0x180377d18  lea     rbx, xmmword_18088AB48
0x180377d1f  mov     ecx, [rbp+37h+arg_28]
0x180377d22  test    ecx, ecx
0x180377d24  jz      short loc_180377D35
0x180377d26  mov     eax, ecx
0x180377d28  shr     rax, 1Dh
0x180377d2c  and     ecx, 1FFFFFFFh
0x180377d32  or      [rbx+rax*4], ecx
0x180377d35  lea     rdx, aControlWmiGlob_0; "\\Control\\WMI\\GlobalLogger"
0x180377d3c  mov     rcx, r14; HKEY
0x180377d3f  call    ?pGetCurrentControlSetKeyPath@@YAPEAVString@UnBCL@@PEAUHKEY__@@PEBG@Z; pGetCurrentControlSetKeyPath(HKEY__ *,ushort const *)
0x180377d44  mov     rdx, rax
0x180377d47  lea     rcx, [rbp+37h+var_40]
0x180377d4b  call    cs:__imp_??0?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAA@PEAVString@1@@Z; UnBCL::SmartPtr<UnBCL::String>::SmartPtr<UnBCL::String>(UnBCL::String *)
0x180377d51  nop
0x180377d52  lea     rdx, [rbp+37h+var_40]
0x180377d56  lea     rcx, [rbp+37h+var_50]
0x180377d5a  call    cs:__imp_??4?$SmartPtr@VString@UnBCL@@@UnBCL@@QEAAAEAV01@AEBV01@@Z; UnBCL::SmartPtr<UnBCL::String>::operator=(UnBCL::SmartPtr<UnBCL::String> const &)
0x180377d60  nop
0x180377d61  lea     rcx, [rbp+37h+var_40]
0x180377d65  call    cs:__imp_??1?$SmartPtr@VString@UnBCL@@@UnBCL@@UEAA@XZ; UnBCL::SmartPtr<UnBCL::String>::~SmartPtr<UnBCL::String>(void)
0x180377d6b  lea     rcx, [rbp+37h+var_50]
0x180377d6f  call    cs:__imp_??7?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBA_NXZ; UnBCL::SmartPtr<UnBCL::String>::operator!(void)
0x180377d75  test    al, al
0x180377d77  jz      loc_180377E0F
0x180377d7d  call    cs:__imp_GetLastError
0x180377d83  xor     r15d, r15d
0x180377d86  test    eax, eax
0x180377d88  jle     short loc_180377D94
0x180377d8a  movzx   eax, ax
0x180377d8d  or      eax, 80070000h
0x180377d92  test    eax, eax
0x180377d94  jns     short loc_180377DAD
0x180377d96  call    cs:__imp_GetLastError
0x180377d9c  mov     esi, eax
0x180377d9e  test    eax, eax
0x180377da0  jle     short loc_180377DB2
0x180377da2  movzx   esi, ax
0x180377da5  or      esi, 80070000h
0x180377dab  jmp     short loc_180377DB2
0x180377dad  mov     esi, 80004005h
0x180377db2  call    cs:__imp_GetLastError
0x180377db8  mov     edi, eax
0x180377dba  call    cs:__imp_CurrentIP
0x180377dc0  mov     rbx, rax
0x180377dc3  mov     r8d, esi
0x180377dc6  lea     rdx, aFailedToGetCur; "Failed to get current control set value"...
0x180377dcd  mov     ecx, 2000000h; unsigned int
0x180377dd2  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180377dd7  mov     [rsp+50h], r15d
0x180377ddc  mov     qword ptr [rsp+0C0h+var_78], r15
0x180377de1  mov     dword ptr [rsp+0C0h+lpdwDisposition], edi
0x180377de5  mov     [rsp+0C0h+phkResult], rbx
0x180377dea  lea     rcx, aSpenableglobal; "SPEnableGlobalLoggerSession"
0x180377df1  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x180377df6  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x180377dfd  mov     qword ptr [rsp+0C0h+samDesired], rcx
0x180377e02  mov     [rsp+0C0h+dwOptions], 7FEh
0x180377e0a  jmp     loc_180378883
0x180377e0f  lea     rcx, [rbp+37h+var_50]
0x180377e13  call    cs:__imp_??C?$SmartPtr@VString@UnBCL@@@UnBCL@@QEBAPEAVString@1@XZ; UnBCL::SmartPtr<UnBCL::String>::operator->(void)
0x180377e19  mov     rcx, rax
0x180377e1c  call    cs:__imp_?get_CString@String@UnBCL@@QEBAPEBGXZ; UnBCL::String::get_CString(void)
0x180377e22  mov     rdx, rax; lpSubKey
0x180377e25  mov     [rsp+0C0h+lpdwDisposition], rdi; lpdwDisposition
0x180377e2a  lea     rax, [rbp+37h+hKey]
0x180377e2e  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180377e33  mov     [rsp+0C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180377e38  mov     [rsp+0C0h+samDesired], 2001Fh; samDesired
0x180377e40  mov     [rsp+0C0h+dwOptions], edi; dwOptions
0x180377e44  xor     r9d, r9d; lpClass
0x180377e47  xor     r8d, r8d; Reserved
0x180377e4a  mov     rcx, r14; hKey
0x180377e4d  call    cs:__imp_RegCreateKeyExW
0x180377e53  mov     esi, eax
0x180377e55  test    eax, eax
0x180377e57  jz      short loc_180377ED7
0x180377e59  jle     short loc_180377E64
0x180377e5b  movzx   esi, ax
0x180377e5e  or      esi, 80070000h
0x180377e64  call    cs:__imp_GetLastError
0x180377e6a  mov     edi, eax
0x180377e6c  call    cs:__imp_CurrentIP
0x180377e72  mov     rbx, rax
0x180377e75  mov     r8d, esi
0x180377e78  lea     rdx, aCreateRegKeyFa; "Create reg key failed: 0x%x"
0x180377e7f  mov     ecx, 2000000h; unsigned int
0x180377e84  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180377e89  xor     ecx, ecx
0x180377e8b  mov     [rsp+50h], ecx
0x180377e8f  mov     qword ptr [rsp+0C0h+var_78], rcx
0x180377e94  mov     dword ptr [rsp+0C0h+lpdwDisposition], edi
0x180377e98  mov     [rsp+0C0h+phkResult], rbx
0x180377e9d  lea     rcx, aSpenableglobal; "SPEnableGlobalLoggerSession"
0x180377ea4  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x180377ea9  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x180377eb0  mov     qword ptr [rsp+0C0h+samDesired], rcx
0x180377eb5  mov     [rsp+0C0h+dwOptions], 813h
0x180377ebd  xor     r9d, r9d
0x180377ec0  lea     r8, aD_0; "D"
0x180377ec7  xor     edx, edx
0x180377ec9  mov     rcx, rax
0x180377ecc  call    cs:__imp_WdsSetupLogMessageW
0x180377ed2  jmp     loc_1803788A8
0x180377ed7  mov     r9d, 4; dwType
0x180377edd  mov     [rsp+0C0h+samDesired], r9d; cbData
0x180377ee2  lea     rax, [rbp+37h+Data]
0x180377ee6  mov     qword ptr [rsp+0C0h+dwOptions], rax; lpData
0x180377eeb  xor     r8d, r8d; Reserved
0x180377eee  lea     rdx, aStart; "Start"
0x180377ef5  mov     rcx, [rbp+37h+hKey]; hKey
0x180377ef9  call    cs:__imp_RegSetValueExW
0x180377eff  mov     esi, eax
0x180377f01  test    eax, eax
0x180377f03  jz      short loc_180377F72
0x180377f05  xor     r15d, r15d
0x180377f08  test    eax, eax
0x180377f0a  jle     short loc_180377F15
0x180377f0c  movzx   esi, ax
0x180377f0f  or      esi, 80070000h
0x180377f15  call    cs:__imp_GetLastError
0x180377f1b  mov     edi, eax
0x180377f1d  call    cs:__imp_CurrentIP
0x180377f23  mov     rbx, rax
0x180377f26  mov     r8d, esi
0x180377f29  lea     rdx, aSetRegKeyValue_15; "Set reg key value failed: 0x%x"
0x180377f30  mov     ecx, 2000000h; unsigned int
0x180377f35  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180377f3a  mov     [rsp+50h], r15d
0x180377f3f  mov     qword ptr [rsp+0C0h+var_78], r15
0x180377f44  mov     dword ptr [rsp+0C0h+lpdwDisposition], edi
0x180377f48  mov     [rsp+0C0h+phkResult], rbx
0x180377f4d  lea     rcx, aSpenableglobal; "SPEnableGlobalLoggerSession"
0x180377f54  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x180377f59  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x180377f60  mov     qword ptr [rsp+0C0h+samDesired], rcx
0x180377f65  mov     [rsp+0C0h+dwOptions], 822h
0x180377f6d  jmp     loc_180378883
0x180377f72  or      rax, 0FFFFFFFFFFFFFFFFh
0x180377f76  mov     r14, [rbp+37h+lpData]
0x180377f7a  test    r12d, r12d
0x180377f7d  jnz     short loc_180377F9B
0x180377f7f  test    r14, r14
0x180377f82  jz      short loc_180377F9B
0x180377f84  lea     rdx, [r14+3Ch]
0x180377f88  mov     rcx, rax
0x180377f8b  inc     rcx
0x180377f8e  cmp     [rdx+rcx*2], di
0x180377f92  jnz     short loc_180377F8B
0x180377f94  test    rcx, rcx
0x180377f97  cmovnz  r15, rdx
0x180377f9b  test    r15, r15
0x180377f9e  jz      loc_180378053
0x180377fa4  cmp     [r15], di
0x180377fa8  jz      loc_180378053
0x180377fae  inc     rax
0x180377fb1  cmp     [r15+rax*2], di
0x180377fb6  jnz     short loc_180377FAE
0x180377fb8  lea     eax, ds:2[rax*2]
0x180377fbf  mov     [rsp+0C0h+samDesired], eax; cbData
0x180377fc3  mov     qword ptr [rsp+0C0h+dwOptions], r15; lpData
0x180377fc8  mov     r9d, 1; dwType
0x180377fce  xor     r8d, r8d; Reserved
0x180377fd1  lea     rdx, aFilename; "FileName"
0x180377fd8  mov     rcx, [rbp+37h+hKey]; hKey
0x180377fdc  call    cs:__imp_RegSetValueExW
0x180377fe2  mov     esi, eax
0x180377fe4  xor     r15d, r15d
0x180377fe7  test    eax, eax
0x180377fe9  jz      short loc_180378056
0x180377feb  jle     short loc_180377FF6
0x180377fed  movzx   esi, ax
0x180377ff0  or      esi, 80070000h
0x180377ff6  call    cs:__imp_GetLastError
0x180377ffc  mov     edi, eax
0x180377ffe  call    cs:__imp_CurrentIP
0x180378004  mov     rbx, rax
0x180378007  mov     r8d, esi
0x18037800a  lea     rdx, aSetRegKeyValue_15; "Set reg key value failed: 0x%x"
0x180378011  mov     ecx, 2000000h; unsigned int
0x180378016  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18037801b  mov     [rsp+50h], r15d
0x180378020  mov     qword ptr [rsp+0C0h+var_78], r15
0x180378025  mov     dword ptr [rsp+0C0h+lpdwDisposition], edi
0x180378029  mov     [rsp+0C0h+phkResult], rbx
0x18037802e  lea     rcx, aSpenableglobal; "SPEnableGlobalLoggerSession"
0x180378035  mov     [rsp+0C0h+lpSecurityAttributes], rcx
0x18037803a  lea     rcx, aBaseNtsetupSet_22; "base\\ntsetup\\setupplatform\\lib\\trac"...
0x180378041  mov     qword ptr [rsp+0C0h+samDesired], rcx
0x180378046  mov     [rsp+0C0h+dwOptions], 83Ch
0x18037804e  jmp     loc_180378883
0x180378053  xor     r15d, r15d
0x180378056  test    r14, r14
0x180378059  jz      short loc_180378069
0x18037805b  mov     eax, [r14+28h]
0x18037805f  test    eax, eax
0x180378061  jz      short loc_180378069
0x180378063  mov     rbx, [r14+20h]
0x180378067  jmp     short loc_18037806E
0x180378069  mov     eax, 20h ; ' '
0x18037806e  mov     [rsp+0C0h+samDesired], eax; cbData
0x180378072  mov     qword ptr [rsp+0C0h+dwOptions], rbx; lpData
0x180378077  mov     edi, 3
0x18037807c  mov     r9d, edi; dwType
0x18037807f  xor     r8d, r8d; Reserved
0x180378082  lea     rdx, aEnablekernelfl; "EnableKernelFlags"
0x180378089  mov     rcx, [rbp+37h+hKey]; hKey
0x18037808d  call    cs:__imp_RegSetValueExW
0x180378093  mov     esi, eax
0x180378095  test    eax, eax
0x180378097  jz      short loc_180378101
0x180378099  jle     short loc_1803780A4
0x18037809b  movzx   esi, ax
0x18037809e  or      esi, 80070000h
0x1803780a4  call    cs:__imp_GetLastError
0x1803780aa  mov     edi, eax
  ... truncated ...
```
