# Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded(bool &,ushort const *,ushort const *,ushort const *,ushort const *,bool *)

- ea: `0x1800858c8`
- end: `0x180086ebf`
- name: `?EnsureAlternateCabUpToDateAndExtractIfNeeded@Utilities@Appraiser@Compat@Windows@@SAJAEA_NPEBG111PEA_N@Z`
- size: `5623`
- prototype: `__int64 __fastcall(bool *, const unsigned __int16 *, wchar_t *, const unsigned __int16 *, unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18004ba00`
- `0x18005bc4c`

## callees

- `0x18000147c`
- `0x1800018a0`
- `0x180001f18`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x18001a2f4`
- `0x180026fd0`
- `0x18002750c`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008513c`
- `0x1800858c8`
- `0x180086ec8`
- `0x180087108`
- `0x18008b308`
- `0x18008b878`
- `0x18008bfbc`
- `0x180093cfc`
- `0x180096f80`
- `0x1801afbd0`
- `0x1802174cc`

## import_xrefs

- `KERNEL32!InitOnceExecuteOnce` at `0x180085a44`
- `KERNEL32!InitOnceExecuteOnce` at `0x180085dfd`
- `KERNEL32!InitOnceExecuteOnce` at `0x18008659b`
- `KERNEL32!InitOnceExecuteOnce` at `0x18008675a`
- `KERNEL32!InitOnceExecuteOnce` at `0x180085a44`
- `KERNEL32!InitOnceExecuteOnce` at `0x180085dfd`
- `KERNEL32!InitOnceExecuteOnce` at `0x18008659b`
- `KERNEL32!InitOnceExecuteOnce` at `0x18008675a`
- `KERNEL32!MoveFileExW` at `0x1800861a7`
- `KERNEL32!MoveFileExW` at `0x1800861a7`
- `KERNEL32!DeleteFileW` at `0x180086b4e`
- `KERNEL32!DeleteFileW` at `0x180086b4e`
- `KERNEL32!GetSystemTime` at `0x180085d0b`
- `KERNEL32!GetSystemTime` at `0x180085f24`
- `KERNEL32!GetSystemTime` at `0x1800860e8`
- `KERNEL32!GetSystemTime` at `0x1800864e3`
- `KERNEL32!GetSystemTime` at `0x1800866ae`
- `KERNEL32!GetSystemTime` at `0x180086811`
- `KERNEL32!GetSystemTime` at `0x18008697f`
- `KERNEL32!GetSystemTime` at `0x180086ab6`
- `KERNEL32!GetSystemTime` at `0x180086c00`
- `KERNEL32!GetSystemTime` at `0x180085d0b`
- `KERNEL32!GetSystemTime` at `0x180085f24`
- `KERNEL32!GetSystemTime` at `0x1800860e8`
- `KERNEL32!GetSystemTime` at `0x1800864e3`
- `KERNEL32!GetSystemTime` at `0x1800866ae`
- `KERNEL32!GetSystemTime` at `0x180086811`
- `KERNEL32!GetSystemTime` at `0x18008697f`
- `KERNEL32!GetSystemTime` at `0x180086ab6`
- `KERNEL32!GetSystemTime` at `0x180086c00`
- `KERNEL32!GetLastError` at `0x1800861b1`
- `KERNEL32!GetLastError` at `0x1800861d3`
- `KERNEL32!GetLastError` at `0x1800861f2`
- `KERNEL32!GetLastError` at `0x1800861b1`
- `KERNEL32!GetLastError` at `0x1800861d3`
- `KERNEL32!GetLastError` at `0x1800861f2`

## string_xrefs

- `0x1800865d3`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x180086723`: `Error getting WIP configuration, swallowing: [0x%x].`
- `0x180086889`: `https://go.microsoft.com/fwlink/?linkid=2112329`
- `0x180085978`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180085999`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180085946`: `Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded`
- `0x180085953`: `Error expanding temporary cab file path: [0x%x].`
- `0x1800859ab`: `Error expanding temporary cab file path: [0x%x].`
- `0x18008622b`: `%ls - Moving cab file from temp path to final path done.`
- `0x18008624f`: `Temp path %ls.`
- `0x180086266`: `Final path %ls.`
- `0x180086cd4`: `Error ensuring ADL cab extract path exists: [0x%x].`
- `0x180086cf0`: `Error ensuring cab extract path exists: [0x%x].`
- `0x180086d0a`: `Error ensuring cab extract path exists: [0x%x].`
- `0x1800863a0`: `Error expanding ADL cab extract path: [0x%x].`
- `0x1800863bc`: `Error expanding cab extract path: [0x%x].`
- `0x180086ca7`: `Error expanding cab extract path: [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded(
        bool *a1,
        const unsigned __int16 *a2,
        wchar_t *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        bool *a6)
{
  int v7; // eax
  signed int v8; // ebx
  char v9; // dl
  char v10; // si
  int InboxDataFileVersion; // eax
  HKEY v12; // r9
  int v13; // eax
  unsigned int v14; // r15d
  unsigned __int64 v15; // rdx
  unsigned int v16; // ecx
  int v17; // r15d
  char v18; // al
  char v19; // r13
  int v20; // eax
  volatile signed __int64 *v21; // rcx
  void **v22; // rdx
  int v23; // r8d
  int v24; // r9d
  int v25; // eax
  int v26; // ebx
  volatile signed __int64 *v27; // rcx
  void **v28; // rdx
  int v29; // ebx
  int v30; // r15d
  int v31; // r8d
  int v32; // r9d
  unsigned int v33; // edx
  int v34; // eax
  int v35; // ebx
  volatile signed __int64 *v36; // rcx
  void **v37; // rdx
  int v38; // r15d
  int v39; // r8d
  int v40; // r9d
  const wchar_t *v41; // rbx
  unsigned __int64 v42; // rdx
  DWORD LastError; // eax
  signed int v44; // eax
  HKEY v45; // r9
  unsigned __int64 v46; // rdx
  const char *v47; // r9
  int v48; // eax
  int Random; // eax
  unsigned __int64 v50; // r9
  int v51; // r13d
  volatile signed __int64 *v52; // rcx
  void **v53; // rdx
  int v54; // ebx
  int v55; // r8d
  int v56; // r9d
  int WipConfigSettings; // eax
  int v58; // r13d
  volatile signed __int64 *v59; // rcx
  void **v60; // rdx
  int v61; // ebx
  int v62; // r8d
  int v63; // r9d
  volatile signed __int64 *v64; // rcx
  void **v65; // rdx
  int v66; // ebx
  int v67; // r8d
  int v68; // r9d
  int v69; // eax
  int v70; // r13d
  volatile signed __int64 *v71; // rcx
  void **v72; // rdx
  int v73; // ebx
  int v74; // r8d
  int v75; // r9d
  __int16 *v76; // rdx
  int v77; // eax
  int v78; // r13d
  volatile signed __int64 *v79; // rcx
  void **v80; // rdx
  volatile signed __int64 *v81; // rcx
  void **v82; // rdx
  int v83; // ebx
  int v84; // r8d
  int v85; // r9d
  int v86; // eax
  void (*v87)(const unsigned __int16 *, void *); // r8
  void *v88; // r9
  int Cabinet; // eax
  unsigned __int64 v90; // rdx
  int v91; // r15d
  int v92; // r15d
  const char *v93; // rbx
  char v94; // dl
  const char *lpSubKey; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeya; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeye; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeyf; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKeyb; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeyg; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpSubKeyc; // [rsp+20h] [rbp-E0h]
  const char *lpSubKeyd; // [rsp+20h] [rbp-E0h]
  const char *v104; // [rsp+28h] [rbp-D8h]
  char *v105; // [rsp+30h] [rbp-D0h]
  char *v106; // [rsp+30h] [rbp-D0h]
  char *v107; // [rsp+30h] [rbp-D0h]
  bool v108; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v109; // [rsp+64h] [rbp-9Ch] BYREF
  bool v110; // [rsp+68h] [rbp-98h] BYREF
  _DWORD Data[3]; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int pvData; // [rsp+78h] [rbp-88h] BYREF
  struct _SYSTEMTIME *v113; // [rsp+80h] [rbp-80h] BYREF
  const char *v114; // [rsp+88h] [rbp-78h] BYREF
  char v115[8]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v116; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v117[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v119; // [rsp+C0h] [rbp-40h] BYREF
  unsigned int v120; // [rsp+C4h] [rbp-3Ch] BYREF
  struct _SYSTEMTIME *v121; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t *String1; // [rsp+D0h] [rbp-30h]
  LPCWSTR lpNewFileName; // [rsp+D8h] [rbp-28h]
  char *v124; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 *v125; // [rsp+E8h] [rbp-18h]
  bool *v126; // [rsp+F0h] [rbp-10h]
  struct _SYSTEMTIME v127; // [rsp+100h] [rbp+0h] BYREF
  char v128[144]; // [rsp+110h] [rbp+10h] BYREF
  char v129[144]; // [rsp+1A0h] [rbp+A0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v131[264]; // [rsp+440h] [rbp+340h] BYREF
  WCHAR Dst[264]; // [rsp+650h] [rbp+550h] BYREF
  unsigned __int16 v133[264]; // [rsp+860h] [rbp+760h] BYREF

  v125 = a5;
  String1 = a3;
  lpNewFileName = a2;
  v126 = a1;
  v117[0] = a6;
  v119 = 0;
  pvData = 0;
  v120 = 0;
  v110 = 0;
  if ( a6 )
    *a6 = 0;
  v7 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(ExistingFileName, (unsigned int)a2, a4);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v10 = 1;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xFFBu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        "Error expanding temporary cab file path: [0x%x].",
        v7);
    InboxDataFileVersion = Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion(&v119);
    v8 = InboxDataFileVersion;
    if ( InboxDataFileVersion < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        4098,
        "Error getting inbox data file version: [0x%x].",
        InboxDataFileVersion);
      LODWORD(v105) = v8;
      v9 = 3;
      v104 = "Error getting inbox data file version: [0x%x].";
      goto LABEL_167;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1003u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        "Error getting inbox data file version: [0x%x].",
        InboxDataFileVersion);
    InitOnceExecuteOnce(
      &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
      Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
      0,
      0);
    v109 = Windows::Compat::Appraiser::AppraiserSettings::SettingAlternateDataVersion;
    pvData = 0;
    *(_QWORD *)&Data[1] = 4;
    v13 = Windows::Compat::Shared::Registry::ReadValue(
            &pvData,
            (unsigned __int64 *)&Data[1],
            0x10u,
            v12,
            Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
            a3);
    v8 = v13;
    if ( v13 == -2147024894 )
    {
      pvData = 0;
      v8 = 0;
    }
    else if ( v13 < 0 )
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        4112,
        "Error checking alternate data file's version: [0x%x].",
        v13);
      LODWORD(v105) = v8;
      v9 = 17;
      v104 = "Error checking alternate data file's version: [0x%x].";
      goto LABEL_167;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x1011u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        "Error checking alternate data file's version: [0x%x].",
        v8);
    v14 = v119;
    AslLogCallPrintf(
      3,
      "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
      4122,
      "Online alternate data version is %d, local alternate data version is %d, inbox data version is %d.",
      v109,
      pvData,
      v119);
    LODWORD(v106) = v109;
    Windows::Compat::Appraiser::WriteLog(
      0,
      30,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
      0,
      (int)"Online alternate data version is %d, local alternate data version is %d, inbox data version is %d.",
      v106,
      pvData,
      v14);
    v16 = pvData;
    if ( v109 <= pvData || v109 <= v14 )
    {
      v17 = v14 < pvData ? 2 : 4;
    }
    else
    {
      Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v131, v15);
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        4131,
        "%ls - ADL online version is newer than local ADL version and inbox data file version.",
        v131);
      v16 = pvData;
      v17 = 1;
    }
    v108 = 1;
    v18 = 4;
    if ( v16 )
      v18 = 6;
    v19 = v18 | (v109 != 0);
    if ( (v19 & 2) != 0 )
    {
      v20 = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, lpNewFileName);
      Data[0] = v20;
      if ( v20 >= 0 )
      {
        v108 = 1;
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          goto LABEL_41;
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x103Cu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          "Failed to verify local cab signature, swallowing: [0x%x].",
          v20);
        goto LABEL_40;
      }
      AslLogCallPrintf(
        3,
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        4155,
        "Failed to verify local ADL cab signature, swallowing: [0x%x].",
        v20);
      LODWORD(v105) = Data[0];
      LODWORD(lpSubKeye) = Data[0];
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        60,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        lpSubKeye,
        (int)"Failed to verify local cab signature, swallowing: [0x%x].",
        v105);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
      v21 = (volatile signed __int64 *)v128;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v21 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v21,
        _InterlockedExchangeAdd64(v21 + 17, 0),
        v129);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v22);
      *(_QWORD *)v115 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v121 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
        v124 = v129;
        v113 = (struct _SYSTEMTIME *)&szValueBuf;
        v116 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        Data[1] = 4156;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v114 = (const char *)&v127;
        v127 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          *(_DWORD *)v115,
          (unsigned int)byte_1802A2071,
          v23,
          v24,
          (__int64)&v114,
          (__int64)&v113,
          (__int64)&Data[1],
          (__int64)&v116,
          (__int64)&v121,
          (__int64)Data,
          (__int64)&v124);
      }
      v19 &= ~2u;
      v108 = 1;
      if ( v17 == 2 )
      {
        if ( (v19 & 1) != 0 && v109 > v119 )
        {
          v17 = 1;
          v108 = 0;
          goto LABEL_41;
        }
        v17 = 4;
LABEL_40:
        v108 = 1;
      }
    }
LABEL_41:
    if ( (v19 & 1) != 0 && v17 == 1 )
    {
      InitOnceExecuteOnce(
        &Windows::Compat::Appraiser::AppraiserSettings::InitOnce,
        Windows::Compat::Appraiser::AppraiserSettings::InitOnceCallback,
        0,
        0);
      v25 = Windows::Compat::Appraiser::Utilities::DownloadCabFile(
              &Windows::Compat::Appraiser::AppraiserSettings::SettingAlternateDataLink,
              ExistingFileName);
      Data[0] = v25;
      v26 = v25;
      if ( v25 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x1068u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            "Error downloading new cab file, swallowing: [0x%x].",
            v25);
        v34 = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, ExistingFileName);
        v35 = v34;
        if ( v34 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1072u,
              "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
              "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
              "Failed to verify cab signature, swallowing: [0x%x].",
              v34);
          v41 = lpNewFileName;
          if ( !MoveFileExW(ExistingFileName, lpNewFileName, 1u) )
          {
            LastError = GetLastError();
            AslLogCallPrintf(
              3,
              "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
              4226,
              "Error saving downloaded ADL cab file: [%d].",
              LastError);
            v44 = GetLastError();
            v8 = v44;
            if ( v44 > 0 )
              v8 = (unsigned __int16)v44 | 0x80070000;
            if ( v8 >= 0 )
              v8 = -2147467259;
            LODWORD(v105) = GetLastError();
            v9 = -125;
            v104 = "Error saving downloaded cab file: [%d].";
            goto LABEL_167;
          }
          Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v131, v42);
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4231,
            "%ls - Moving cab file from temp path to final path done.",
            v131);
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4232,
            "Temp path %ls.",
            ExistingFileName);
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4233,
            "Final path %ls.",
            v41);
          Data[1] = v109;
          v8 = Windows::Compat::Shared::Registry::WriteValue(
                 (BYTE *)&Data[1],
                 4u,
                 4u,
                 v45,
                 Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser,
                 String1);
          if ( v8 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x1093u,
                "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
                "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
                "Error saving alternate data file's version: [0x%x].",
                v8);
          }
          else if ( wcscmp_0(String1, L"AlternateDownloadRestoreVersion") )
          {
            AslLogCallPrintf(
              3,
              "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
              4242,
              "Error saving ADL/alternate data file's version: [0x%x].",
              v8);
            v47 = "Error saving alternate data file's version: [0x%x].";
            v9 = -109;
LABEL_166:
            LODWORD(v105) = v8;
            LODWORD(v104) = (_DWORD)v47;
            goto LABEL_167;
          }
          if ( v117[0] )
            *(_BYTE *)v117[0] = v108;
          Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v131, v46);
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4257,
            "%ls - Finished downloading ADL version %d.",
            v131,
            v109);
          goto LABEL_85;
        }
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          4209,
          "Failed to verify online ADL cab signature, swallowing: [0x%x].",
          v34);
        LODWORD(v105) = v35;
        LODWORD(lpSubKeyg) = v35;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          114,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          lpSubKeyg,
          (int)"Failed to verify cab signature, swallowing: [0x%x].",
          v105);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
        v36 = (volatile signed __int64 *)v128;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v36 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v36,
          _InterlockedExchangeAdd64(v36 + 17, 0),
          v129);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v37);
        v38 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          Data[1] = v35;
          *(_QWORD *)v115 = v129;
          v114 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
          v116 = (struct _SYSTEMTIME *)&szValueBuf;
          v113 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          v109 = 4210;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v121 = &v127;
          v127 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v38,
            (unsigned int)byte_1802A1EE5,
            v39,
            v40,
            (__int64)&v121,
            (__int64)&v116,
            (__int64)&v109,
            (__int64)&v113,
            (__int64)&v114,
            (__int64)&Data[1],
            (__int64)v115);
        }
        LODWORD(lpSubKeyc) = v35;
        AslLogCallPrintf(
          1,
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          4213,
          "Appraiser ADL Pipeline - Error verifying alternate data files: [ApprADL:0x%x]",
          lpSubKeyc);
      }
      else
      {
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          4199,
          "Error downloading new ADL cab file, swallowing: [0x%x]",
          v25);
        LODWORD(v105) = v26;
        LODWORD(lpSubKeyf) = v26;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          104,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          lpSubKeyf,
          (int)"Error downloading new cab file, swallowing: [0x%x].",
          v105);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
        v27 = (volatile signed __int64 *)v128;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v27 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v27,
          _InterlockedExchangeAdd64(v27 + 17, 0),
          v129);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v28);
        v29 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          v30 = Data[0];
          *(_QWORD *)v115 = v129;
          Data[1] = Data[0];
          v116 = (struct _SYSTEMTIME *)&szValueBuf;
          v114 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
          v113 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
          v109 = 4200;
          SystemTime = 0;
          GetSystemTime(&SystemTime);
          v121 = &v127;
          v127 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v29,
            (unsigned int)qword_1802A1F48,
            v31,
            v32,
            (__int64)&v121,
            (__int64)&v116,
            (__int64)&v109,
            (__int64)&v113,
            (__int64)&v114,
            (__int64)&Data[1],
            (__int64)v115);
        }
        else
        {
          v30 = Data[0];
        }
        LODWORD(lpSubKeyb) = v30;
        AslLogCallPrintf(
          1,
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          4203,
          "Appraiser ADL Pipeline - Error downloading alternate data files: [ApprADL:0x%x]",
          lpSubKeyb);
      }
      if ( (v19 & 2) != 0 && pvData > v119 )
      {
        v17 = 2;
LABEL_85:
        v48 = Windows::Compat::Appraiser::Utilities::ExpandDirectory(Dst, v33, v125);
        v8 = v48;
        if ( v48 < 0 )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4341,
            "Error expanding ADL cab extract path: [0x%x].",
            v48);
          v47 = "Error expanding cab extract path: [0x%x].";
          v9 = -10;
          goto LABEL_166;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x10F6u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            "Error expanding cab extract path: [0x%x].",
            v48);
        v86 = Windows::Compat::Appraiser::Utilities::EnsureDirectoryExists(Dst);
        v8 = v86;
        if ( v86 < 0 )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4345,
            "Error ensuring ADL cab extract path exists: [0x%x].",
            v86);
          v47 = "Error ensuring cab extract path exists: [0x%x].";
          v9 = -6;
          goto LABEL_166;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x10FAu,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            "Error ensuring cab extract path exists: [0x%x].",
            v86);
        Cabinet = DiagExtractCabinet(lpNewFileName, Dst, v87, v88);
        v8 = Cabinet;
        if ( Cabinet < 0 )
        {
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4349,
            "Failed to extract ADL cab file: [0x%x].",
            Cabinet);
          v47 = "Failed to extract cab file: [0x%x].";
          v9 = -2;
          goto LABEL_166;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x10FEu,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            "Failed to extract cab file: [0x%x].",
            Cabinet);
        Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(v131, v90);
        AslLogCallPrintf(
          3,
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          4353,
          "%ls - Cab file extraction to %ls done.",
          v131,
          Dst);
LABEL_171:
        *v126 = v10;
        v91 = v17 - 1;
        if ( v91 )
        {
          v92 = v91 - 1;
          if ( v92 )
          {
            if ( v92 != 2 )
              return 0;
            v93 = "Using inbox data file.";
            AslLogCallPrintf(
              3,
              "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
              4373,
              "Using inbox data file.");
            v94 = 22;
          }
          else
          {
            v93 = "Using local alternate data file.";
            AslLogCallPrintf(
              3,
              "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
              4369,
              "Using local alternate data file.");
            v94 = 18;
          }
        }
        else
        {
          v93 = "Using online alternate data file.";
          AslLogCallPrintf(
            3,
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            4365,
            "Using online alternate data file.");
          v94 = 14;
        }
        Windows::Compat::Appraiser::WriteLog(
          0,
          v94,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          0,
          (int)v93,
          v105);
        return 0;
      }
      v17 = 4;
LABEL_157:
      v10 = 0;
      goto LABEL_171;
    }
    if ( !wcscmp_0(String1, L"AlternateDownloadRestoreVersion") )
    {
LABEL_156:
      if ( (unsigned int)(v17 - 1) <= 1 )
        goto LABEL_85;
      goto LABEL_157;
    }
    Random = Windows::Compat::Appraiser::Utilities::GetRandom(&v120);
    v51 = Random;
    if ( Random >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x10C7u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          "Error generating random number, swallowing: [0x%x].",
          Random);
      if ( v120 == 100 * (v120 / 0x64) )
        goto LABEL_102;
    }
    else
    {
      LODWORD(v105) = Random;
      LODWORD(lpSubKeya) = Random;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        199,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        lpSubKeya,
        (int)"Error generating random number, swallowing: [0x%x].",
        v105);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
      v52 = (volatile signed __int64 *)v128;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v52 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v52,
        _InterlockedExchangeAdd64(v52 + 17, 0),
        v129);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v53);
      v54 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        Data[1] = v51;
        v117[0] = v129;
        *(_QWORD *)v115 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
        v113 = (struct _SYSTEMTIME *)&szValueBuf;
        v114 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v109 = 4295;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v116 = &v127;
        v127 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v54,
          (unsigned int)&word_1802A200E,
          v55,
          v56,
          (__int64)&v116,
          (__int64)&v113,
          (__int64)&v109,
          (__int64)&v114,
          (__int64)v115,
          (__int64)&Data[1],
          (__int64)v117);
      }
    }
    InitOnceExecuteOnce(
      &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
      Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
      0,
      0);
    if ( !Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceAdlDownloadTest )
      goto LABEL_156;
LABEL_102:
    WipConfigSettings = Windows::Compat::Appraiser::Utilities::GetWipConfigSettings(&v110, &v108, v133, v50);
    v58 = WipConfigSettings;
    if ( WipConfigSettings >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x10CCu,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          "Error getting WIP configuration, swallowing: [0x%x].",
          WipConfigSettings);
      if ( v110 )
        goto LABEL_115;
    }
    else
    {
      LODWORD(v105) = WipConfigSettings;
      LODWORD(lpSubKeya) = WipConfigSettings;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        204,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        lpSubKeya,
        (int)"Error getting WIP configuration, swallowing: [0x%x].",
        v105);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
      v59 = (volatile signed __int64 *)v128;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v59 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v59,
        _InterlockedExchangeAdd64(v59 + 17, 0),
        v129);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v60);
      v61 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        Data[1] = v58;
        v117[0] = v129;
        *(_QWORD *)v115 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
        v113 = (struct _SYSTEMTIME *)&szValueBuf;
        v114 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v109 = 4300;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v116 = &v127;
        v127 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v61,
          (unsigned int)byte_1802A1FAB,
          v62,
          v63,
          (__int64)&v116,
          (__int64)&v113,
          (__int64)&v109,
          (__int64)&v114,
          (__int64)v115,
          (__int64)&Data[1],
          (__int64)v117);
      }
    }
    InitOnceExecuteOnce(
      &Windows::Compat::Appraiser::AppraiserTestHooks::InitOnce,
      Windows::Compat::Appraiser::AppraiserTestHooks::InitOnceCallback,
      0,
      0);
    if ( !Windows::Compat::Appraiser::AppraiserTestHooks::TestHookForceAdlDownloadTest )
      goto LABEL_156;
LABEL_115:
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
    v64 = (volatile signed __int64 *)v128;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v64 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v64,
      _InterlockedExchangeAdd64(v64 + 17, 0),
      v129);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v65);
    v66 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)v115 = 0x1000000;
      v117[0] = v129;
      v114 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v113 = &v127;
      v127 = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
        v66,
        (unsigned int)&dword_1802A1DEC,
        v67,
        v68,
        (__int64)&v113,
        (__int64)&v114,
        (__int64)v115,
        (__int64)v117);
    }
    Windows::Compat::Appraiser::WriteLog(
      0,
      209,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
      0,
      (int)"Performing ADL test download.",
      v105);
    v69 = Windows::Compat::Appraiser::Utilities::DownloadCabFile(
            L"https://go.microsoft.com/fwlink/?linkid=2112329",
            ExistingFileName);
    v70 = v69;
    if ( v69 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x10D4u,
          "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          "Error downloading default cab file, swallowing: [0x%x].",
          v69);
      v77 = Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(0, 0, ExistingFileName);
      v78 = v77;
      if ( v77 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x10D9u,
            "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
            "Failed to verify default cab signature, swallowing: [0x%x].",
            v77);
        DeleteFileW(ExistingFileName);
        goto LABEL_147;
      }
      LODWORD(v107) = v77;
      LODWORD(lpSubKeyd) = v77;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        217,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        lpSubKeyd,
        (int)"Failed to verify default cab signature, swallowing: [0x%x].",
        v107);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
      v79 = (volatile signed __int64 *)v128;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v79 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v79,
        _InterlockedExchangeAdd64(v79 + 17, 0),
        v129);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v80);
      v73 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 <= 5u
        || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
        || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
      {
LABEL_147:
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
        v81 = (volatile signed __int64 *)v128;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v81 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v81,
          _InterlockedExchangeAdd64(v81 + 17, 0),
          v129);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v82);
        v83 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          *(_QWORD *)v115 = 0x1000000;
          v117[0] = v129;
          Data[1] = 1;
          SystemTime = 0;
          v114 = (const char *)&szValueBuf;
          GetSystemTime(&SystemTime);
          v113 = &v127;
          v127 = SystemTime;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
            v83,
            (unsigned int)byte_1802A1E31,
            v84,
            v85,
            (__int64)&v113,
            (__int64)&v114,
            (__int64)&Data[1],
            (__int64)v115,
            (__int64)v117);
        }
        Windows::Compat::Appraiser::WriteLog(
          0,
          227,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
          "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
          0,
          (int)"ADL test download %hs.",
          "Succeeded");
        goto LABEL_156;
      }
      Data[1] = v78;
      v117[0] = v129;
      *(_QWORD *)v115 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
      v113 = (struct _SYSTEMTIME *)&szValueBuf;
      v114 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      v109 = 4313;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v76 = word_1802A1E82;
    }
    else
    {
      LODWORD(v107) = v69;
      LODWORD(lpSubKeyd) = v69;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        212,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
        lpSubKeyd,
        (int)"Error downloading default cab file, swallowing: [0x%x].",
        v107);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v128);
      v71 = (volatile signed __int64 *)v128;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v71 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v71,
        _InterlockedExchangeAdd64(v71 + 17, 0),
        v129);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v72);
      v73 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 <= 5u
        || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
        || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
      {
        goto LABEL_147;
      }
      Data[1] = v70;
      v117[0] = v129;
      *(_QWORD *)v115 = "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded";
      v113 = (struct _SYSTEMTIME *)&szValueBuf;
      v114 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
      v109 = 4308;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v76 = (__int16 *)byte_1802A1D89;
    }
    v116 = &v127;
    v127 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v73,
      (_DWORD)v76,
      v74,
      v75,
      (__int64)&v116,
      (__int64)&v113,
      (__int64)&v109,
      (__int64)&v114,
      (__int64)v115,
      (__int64)&Data[1],
      (__int64)v117);
    goto LABEL_147;
  }
  AslLogCallPrintf(
    3,
    "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
    4090,
    "Error expanding temporary cab file path: [0x%x].",
    v7);
  LODWORD(v105) = v8;
  v104 = "Error expanding temporary cab file path: [0x%x].";
  v9 = -5;
LABEL_167:
  LODWORD(lpSubKey) = v8;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v9,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
    lpSubKey,
    (int)v104,
    v105);
  AslLogCallPrintf(
    1,
    "Windows::Compat::Appraiser::Utilities::EnsureAlternateCabUpToDateAndExtractIfNeeded",
    4385,
    "Appraiser ADL Pipeline - Error getting alternate data files: [ApprADL:0x%x]",
    v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800858c8  push    rbp
0x1800858ca  push    rbx
0x1800858cb  push    rsi
0x1800858cc  push    rdi
0x1800858cd  push    r12
0x1800858cf  push    r13
0x1800858d1  push    r14
0x1800858d3  push    r15
0x1800858d5  lea     rbp, [rsp-988h]
0x1800858dd  sub     rsp, 0A88h
0x1800858e4  mov     rax, cs:__security_cookie
0x1800858eb  xor     rax, rsp
0x1800858ee  mov     [rbp+9C0h+var_50], rax
0x1800858f5  mov     rax, [rbp+9C0h+arg_20]
0x1800858fc  xor     r13d, r13d
0x1800858ff  mov     [rbp+9C0h+var_9D8], rax
0x180085903  mov     r12, r8
0x180085906  mov     rax, [rbp+9C0h+arg_28]
0x18008590d  mov     [rbp+9C0h+String1], r8
0x180085911  mov     [rbp+9C0h+lpNewFileName], rdx
0x180085915  mov     [rbp+9C0h+var_9D0], rcx
0x180085919  mov     [rbp+9C0h+var_A20], rax
0x18008591d  mov     [rbp+9C0h+var_A00], r13d
0x180085921  mov     [rsp+0AC0h+pvData], r13d
0x180085926  mov     [rbp+9C0h+var_9FC], r13d
0x18008592a  mov     byte ptr [rsp+0AC0h+var_A5C+4], r13b
0x18008592f  test    rax, rax
0x180085932  jz      short loc_180085937
0x180085934  mov     [rax], r13b
0x180085937  mov     r8, r9; unsigned __int16 *
0x18008593a  lea     rcx, [rbp+9C0h+ExistingFileName]; lpDst
0x180085941  call    ?ExpandDirectory@Utilities@Appraiser@Compat@Windows@@SAJPEAGKPEBG@Z; Windows::Compat::Appraiser::Utilities::ExpandDirectory(ushort *,ulong,ushort const *)
0x180085946  lea     rdi, aWindowsCompatA_410; "Windows::Compat::Appraiser::Utilities::"...
0x18008594d  mov     ebx, eax
0x18008594f  test    eax, eax
0x180085951  jns     short loc_180085993
0x180085953  lea     r15, aErrorExpanding_7; "Error expanding temporary cab file path"...
0x18008595a  mov     dword ptr [rsp+0AC0h+lpSubKey], eax
0x18008595e  mov     r9, r15
0x180085961  mov     r8d, 0FFAh
0x180085967  mov     rdx, rdi
0x18008596a  mov     ecx, 3
0x18008596f  call    AslLogCallPrintf
0x180085974  mov     dword ptr [rsp+0AC0h+var_A90], ebx
0x180085978  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008597f  mov     [rsp+0AC0h+var_A98], r15
0x180085984  mov     edx, 0FFBh
0x180085989  mov     esi, 1
0x18008598e  jmp     loc_180086D6F
0x180085993  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180085999  lea     r14, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800859a0  mov     esi, 1
0x1800859a5  and     eax, esi
0x1800859a7  test    al, al
0x1800859a9  jz      short loc_1800859C6
0x1800859ab  lea     r9, aErrorExpanding_7; "Error expanding temporary cab file path"...
0x1800859b2  mov     dword ptr [rsp+0AC0h+lpSubKey], ebx
0x1800859b6  mov     r8, rdi; char *
0x1800859b9  mov     rdx, r14; char *
0x1800859bc  mov     ecx, 0FFBh; unsigned int
0x1800859c1  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800859c6  lea     rcx, [rbp+9C0h+var_A00]; unsigned int *
0x1800859ca  call    ?GetInboxDataFileVersion@DataFile@Appraiser@Compat@Windows@@SAJAEAK@Z; Windows::Compat::Appraiser::DataFile::GetInboxDataFileVersion(ulong &)
0x1800859cf  mov     ebx, eax
0x1800859d1  test    eax, eax
0x1800859d3  jns     short loc_180085A09
0x1800859d5  lea     r15, aErrorGettingIn_0; "Error getting inbox data file version: "...
0x1800859dc  mov     dword ptr [rsp+0AC0h+lpSubKey], eax
0x1800859e0  mov     r9, r15
0x1800859e3  mov     r8d, 1002h
0x1800859e9  mov     rdx, rdi
0x1800859ec  mov     ecx, 3
0x1800859f1  call    AslLogCallPrintf
0x1800859f6  mov     dword ptr [rsp+0AC0h+var_A90], ebx
0x1800859fa  mov     edx, 1003h
0x1800859ff  mov     [rsp+0AC0h+var_A98], r15
0x180085a04  jmp     loc_180086D6C
0x180085a09  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180085a0f  and     eax, esi
0x180085a11  test    al, al
0x180085a13  jz      short loc_180085A30
0x180085a15  lea     r9, aErrorGettingIn_0; "Error getting inbox data file version: "...
0x180085a1c  mov     dword ptr [rsp+0AC0h+lpSubKey], ebx
0x180085a20  mov     r8, rdi; char *
0x180085a23  mov     rdx, r14; char *
0x180085a26  mov     ecx, 1003h; unsigned int
0x180085a2b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180085a30  xor     r9d, r9d; Context
0x180085a33  lea     rdx, ?InitOnceCallback@AppraiserSettings@Appraiser@Compat@Windows@@CAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x180085a3a  xor     r8d, r8d; Parameter
0x180085a3d  lea     rcx, ?InitOnce@AppraiserSettings@Appraiser@Compat@Windows@@0T_RTL_RUN_ONCE@@A; InitOnce
0x180085a44  call    cs:__imp_InitOnceExecuteOnce
0x180085a4a  mov     eax, cs:?SettingAlternateDataVersion@AppraiserSettings@Appraiser@Compat@Windows@@0KA; ulong Windows::Compat::Appraiser::AppraiserSettings::SettingAlternateDataVersion
0x180085a50  lea     rdx, [rsp+0AC0h+Data+4]; unsigned __int64 *
0x180085a55  mov     dword ptr [rsp+0AC0h+var_A5C], eax
0x180085a59  lea     rcx, [rsp+0AC0h+pvData]; pvData
0x180085a5e  mov     rax, cs:?RegistryPathAppraiser@WicaFactory@Appraiser@Compat@Windows@@2PEAGEA; ushort * Windows::Compat::Appraiser::WicaFactory::RegistryPathAppraiser
0x180085a65  mov     r8d, 10h; unsigned int
0x180085a6b  mov     [rsp+0AC0h+var_A98], r12; unsigned __int16 *
0x180085a70  mov     [rsp+0AC0h+lpSubKey], rax; unsigned __int16 *
0x180085a75  mov     [rsp+0AC0h+pvData], r13d
0x180085a7a  mov     qword ptr [rsp+0AC0h+Data+4], 4
0x180085a83  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x180085a88  mov     ebx, eax
0x180085a8a  cmp     eax, 80070002h
0x180085a8f  jnz     loc_180085B75
0x180085a95  mov     [rsp+0AC0h+pvData], r13d
0x180085a9a  mov     ebx, r13d
0x180085a9d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180085aa3  and     eax, esi
0x180085aa5  test    al, al
0x180085aa7  jz      short loc_180085AC4
0x180085aa9  lea     r9, aErrorCheckingA; "Error checking alternate data file's ve"...
0x180085ab0  mov     dword ptr [rsp+0AC0h+lpSubKey], ebx
0x180085ab4  mov     r8, rdi; char *
0x180085ab7  mov     rdx, r14; char *
0x180085aba  mov     ecx, 1011h; unsigned int
0x180085abf  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180085ac4  mov     eax, [rsp+0AC0h+pvData]
0x180085ac8  lea     r13, aOnlineAlternat; "Online alternate data version is %d, lo"...
0x180085acf  mov     r15d, [rbp+9C0h+var_A00]
0x180085ad3  mov     r12d, 3
0x180085ad9  mov     ebx, dword ptr [rsp+0AC0h+var_A5C]
0x180085add  mov     r9, r13
0x180085ae0  mov     dword ptr [rsp+0AC0h+var_A90], r15d
0x180085ae5  mov     ecx, r12d
0x180085ae8  mov     dword ptr [rsp+0AC0h+var_A98], eax
0x180085aec  mov     r8d, 101Ah
0x180085af2  mov     rdx, rdi
0x180085af5  mov     dword ptr [rsp+0AC0h+lpSubKey], ebx
0x180085af9  call    AslLogCallPrintf
0x180085afe  mov     eax, [rsp+0AC0h+pvData]
0x180085b02  mov     r9, rdi; char *
0x180085b05  mov     dword ptr [rsp+0AC0h+var_A80], r15d
0x180085b0a  mov     r8, r14; unsigned int
0x180085b0d  mov     dword ptr [rsp+0AC0h+var_A88], eax
0x180085b11  mov     edx, 101Eh; bool
0x180085b16  mov     dword ptr [rsp+0AC0h+var_A90], ebx; char *
0x180085b1a  xor     ecx, ecx; this
0x180085b1c  mov     [rsp+0AC0h+var_A98], r13; int
0x180085b21  mov     [rsp+0AC0h+lpSubKey], 0; char *
0x180085b2a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180085b2f  mov     ecx, [rsp+0AC0h+pvData]
0x180085b33  cmp     ebx, ecx
0x180085b35  jbe     short loc_180085BB1
0x180085b37  cmp     ebx, r15d
0x180085b3a  jbe     short loc_180085BB1
0x180085b3c  lea     rcx, [rbp+9C0h+var_680]; unsigned __int16 *
0x180085b43  call    ?GetSystemTimeIso8601@Utilities@Appraiser@Compat@Windows@@SAXPEAG_K@Z; Windows::Compat::Appraiser::Utilities::GetSystemTimeIso8601(ushort *,unsigned __int64)
0x180085b48  lea     rax, [rbp+9C0h+var_680]
0x180085b4f  mov     r8d, 1023h
0x180085b55  lea     r9, aLsAdlOnlineVer; "%ls - ADL online version is newer than "...
0x180085b5c  mov     [rsp+0AC0h+lpSubKey], rax
0x180085b61  mov     rdx, rdi
0x180085b64  mov     ecx, r12d
0x180085b67  call    AslLogCallPrintf
0x180085b6c  mov     ecx, [rsp+0AC0h+pvData]
0x180085b70  mov     r15d, esi
0x180085b73  jmp     short loc_180085BBF
0x180085b75  test    ebx, ebx
0x180085b77  jns     loc_180085A9D
0x180085b7d  lea     r15, aErrorCheckingA; "Error checking alternate data file's ve"...
0x180085b84  mov     dword ptr [rsp+0AC0h+lpSubKey], ebx
0x180085b88  mov     r9, r15
0x180085b8b  mov     r8d, 1010h
0x180085b91  mov     rdx, rdi
0x180085b94  mov     ecx, 3
0x180085b99  call    AslLogCallPrintf
0x180085b9e  mov     dword ptr [rsp+0AC0h+var_A90], ebx
0x180085ba2  mov     edx, 1011h
0x180085ba7  mov     [rsp+0AC0h+var_A98], r15
0x180085bac  jmp     loc_180086D6C
0x180085bb1  cmp     r15d, ecx
0x180085bb4  sbb     r15d, r15d
0x180085bb7  and     r15d, 0FFFFFFFEh
0x180085bbb  add     r15d, 4
0x180085bbf  test    ecx, ecx
0x180085bc1  mov     [rsp+0AC0h+var_A60], sil
0x180085bc6  mov     eax, 4
0x180085bcb  lea     edx, [rax+2]
0x180085bce  cmovnz  eax, edx
0x180085bd1  xor     r13d, r13d
0x180085bd4  test    ebx, ebx
0x180085bd6  setnz   r13b
0x180085bda  or      r13d, eax
0x180085bdd  test    r13b, 2
0x180085be1  jz      loc_180085DD3
0x180085be7  mov     r8, [rbp+9C0h+lpNewFileName]; unsigned __int16 *
0x180085beb  xor     r9d, r9d; bool
0x180085bee  xor     edx, edx; unsigned int *
0x180085bf0  xor     ecx, ecx; int *
0x180085bf2  call    ?VerifySignatureRecursive@Utilities@Appraiser@Compat@Windows@@SAJPEAJPEAKPEBG_N@Z; Windows::Compat::Appraiser::Utilities::VerifySignatureRecursive(long *,ulong *,ushort const *,bool)
0x180085bf7  mov     dword ptr [rsp+0AC0h+Data], eax
0x180085bfb  mov     ecx, eax
0x180085bfd  test    eax, eax
0x180085bff  jns     loc_180085DA2
0x180085c05  lea     r9, aFailedToVerify_3; "Failed to verify local ADL cab signatur"...
0x180085c0c  mov     dword ptr [rsp+0AC0h+lpSubKey], eax
0x180085c10  mov     r8d, 103Bh
0x180085c16  mov     rdx, rdi
0x180085c19  mov     ecx, r12d
0x180085c1c  call    AslLogCallPrintf
0x180085c21  mov     eax, dword ptr [rsp+0AC0h+Data]
0x180085c25  lea     r9, aFailedToVerify; "Failed to verify local cab signature, s"...
0x180085c2c  mov     dword ptr [rsp+0AC0h+var_A90], eax; char *
0x180085c30  mov     r8, r14; unsigned int
0x180085c33  mov     [rsp+0AC0h+var_A98], r9; int
0x180085c38  mov     edx, 103Ch; bool
0x180085c3d  mov     r9, rdi; char *
0x180085c40  mov     dword ptr [rsp+0AC0h+lpSubKey], eax; char *
0x180085c44  mov     ecx, esi; this
0x180085c46  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180085c4b  lea     rcx, [rbp+9C0h+var_9B0]; this
0x180085c4f  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180085c54  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180085c5b  lea     rcx, [rbp+9C0h+var_9B0]
0x180085c5f  test    rax, rax
0x180085c62  cmovnz  rcx, rax; this
0x180085c66  xor     edx, edx
0x180085c68  lock xadd [rcx+88h], rdx; unsigned __int64
0x180085c71  lea     r8, [rbp+9C0h+var_920]; char *
0x180085c78  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180085c7d  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180085c84  jz      short loc_180085C92
0x180085c86  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180085c8d  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180085c92  mov     rcx, cs:qword_1802C9628
0x180085c99  mov     qword ptr [rbp+9C0h+var_A30], rcx
0x180085c9d  mov     eax, [rcx]
0x180085c9f  cmp     eax, 5
0x180085ca2  jbe     loc_180085D73
0x180085ca8  mov     rdx, [rcx+18h]
0x180085cac  mov     rax, [rcx+10h]
0x180085cb0  mov     rcx, 200000000000h
0x180085cba  test    rcx, rax
0x180085cbd  jz      loc_180085D73
0x180085cc3  mov     rax, rdx
0x180085cc6  and     rax, rcx
0x180085cc9  cmp     rax, rdx
0x180085ccc  jnz     loc_180085D73
0x180085cd2  lea     rax, [rbp+9C0h+var_920]
0x180085cd9  mov     [rbp+9C0h+var_9F8], rdi
0x180085cdd  mov     [rbp+9C0h+var_9E0], rax
0x180085ce1  lea     rcx, [rbp+9C0h+SystemTime]; lpSystemTime
0x180085ce5  mov     eax, dword ptr [rsp+0AC0h+Data]
0x180085ce9  xorps   xmm0, xmm0
0x180085cec  mov     dword ptr [rsp+0AC0h+Data], eax
0x180085cf0  lea     rax, szValueBuf
0x180085cf7  mov     [rbp+9C0h+var_A40], rax
0x180085cfb  mov     [rbp+9C0h+var_A28], r14
0x180085cff  mov     dword ptr [rsp+0AC0h+Data+4], 103Ch
0x180085d07  movups  xmmword ptr [rbp+9C0h+SystemTime.wYear], xmm0
0x180085d0b  call    cs:__imp_GetSystemTime
0x180085d11  movaps  xmm0, xmmword ptr [rbp+9C0h+SystemTime.wYear]
0x180085d15  lea     rax, [rbp+9C0h+var_9C0]
0x180085d19  mov     rcx, qword ptr [rbp+9C0h+var_A30]
0x180085d1d  lea     rdx, byte_1802A2071
0x180085d24  mov     [rbp+9C0h+var_A38], rax
0x180085d28  lea     rax, [rbp+9C0h+var_9E0]
0x180085d2c  mov     [rsp+0AC0h+var_A70], rax
0x180085d31  lea     rax, [rsp+0AC0h+Data]
0x180085d36  mov     [rsp+0AC0h+var_A78], rax
0x180085d3b  lea     rax, [rbp+9C0h+var_9F8]
0x180085d3f  mov     [rsp+0AC0h+var_A80], rax
0x180085d44  lea     rax, [rbp+9C0h+var_A28]
0x180085d48  mov     [rsp+0AC0h+var_A88], rax
0x180085d4d  lea     rax, [rsp+0AC0h+Data+4]
0x180085d52  mov     [rsp+0AC0h+var_A90], rax
0x180085d57  lea     rax, [rbp+9C0h+var_A40]
0x180085d5b  mov     [rsp+0AC0h+var_A98], rax
0x180085d60  lea     rax, [rbp+9C0h+var_A38]
0x180085d64  mov     [rsp+0AC0h+lpSubKey], rax
0x180085d69  movdqa  [rbp+9C0h+var_9C0], xmm0
0x180085d6e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180085d73  and     r13d, 0FFFFFFFDh
0x180085d77  mov     [rsp+0AC0h+var_A60], sil
0x180085d7c  cmp     r15d, 2
0x180085d80  jnz     short loc_180085DD3
0x180085d82  mov     eax, r13d
0x180085d85  and     eax, esi
0x180085d87  test    al, al
0x180085d89  jz      short loc_180085D9A
0x180085d8b  cmp     ebx, [rbp+9C0h+var_A00]
0x180085d8e  jbe     short loc_180085D9A
0x180085d90  mov     r15d, esi
0x180085d93  mov     [rsp+0AC0h+var_A60], 0
0x180085d98  jmp     short loc_180085DD3
0x180085d9a  mov     r15d, 4
0x180085da0  jmp     short loc_180085DCE
0x180085da2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180085da8  and     eax, esi
0x180085daa  mov     [rsp+0AC0h+var_A60], sil
0x180085daf  test    al, al
0x180085db1  jz      short loc_180085DD3
0x180085db3  mov     dword ptr [rsp+0AC0h+lpSubKey], ecx
0x180085db7  lea     r9, aFailedToVerify; "Failed to verify local cab signature, s"...
0x180085dbe  mov     ecx, 103Ch; unsigned int
0x180085dc3  mov     r8, rdi; char *
0x180085dc6  mov     rdx, r14; char *
0x180085dc9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
  ... truncated ...
```
