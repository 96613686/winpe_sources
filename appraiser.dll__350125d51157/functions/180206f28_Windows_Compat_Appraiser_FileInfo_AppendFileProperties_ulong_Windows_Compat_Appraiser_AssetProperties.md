# Windows::Compat::Appraiser::FileInfo::AppendFileProperties(ulong,Windows::Compat::Appraiser::AssetProperties *)

- ea: `0x180206f28`
- end: `0x180207723`
- name: `?AppendFileProperties@FileInfo@Appraiser@Compat@Windows@@CAJKPEAUAssetProperties@234@@Z`
- size: `2043`
- prototype: `__int64 __fastcall(unsigned int, struct Windows::Compat::Appraiser::AssetProperties *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180207810`

## callees

- `0x18000147c`
- `0x180008570`
- `0x1800085a0`
- `0x1800092dc`
- `0x18000a5dc`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180083390`
- `0x1800ad71c`
- `0x18011a9ac`
- `0x180206f28`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x180207481`
- `KERNEL32!GetSystemTime` at `0x180207481`
- `KERNEL32!CreateFileW` at `0x180207272`
- `KERNEL32!CreateFileW` at `0x180207272`
- `KERNEL32!CloseHandle` at `0x180207393`
- `KERNEL32!CloseHandle` at `0x180207393`
- `KERNEL32!GetLastError` at `0x180207285`
- `KERNEL32!GetLastError` at `0x1802072a4`
- `KERNEL32!GetLastError` at `0x180207325`
- `KERNEL32!GetLastError` at `0x180207344`
- `KERNEL32!GetLastError` at `0x180207285`
- `KERNEL32!GetLastError` at `0x1802072a4`
- `KERNEL32!GetLastError` at `0x180207325`
- `KERNEL32!GetLastError` at `0x180207344`
- `KERNEL32!GetFileInformationByHandle` at `0x180207315`
- `KERNEL32!GetFileInformationByHandle` at `0x180207315`

## string_xrefs

- `0x180206fdc`: `COMPANY_NAME`
- `0x180207012`: `LINK_DATE`
- `0x18020706b`: `LowerCaseLongPath`
- `0x180207678`: `NtfsIdLow`
- `0x180207606`: `NtfsIdHigh`
- `0x180207086`: `Error getting file path: [0x%x].`
- `0x1802070db`: `Error getting file path: [0x%x].`
- `0x180207099`: `onecore\base\appcompat\appraiser\decisionaggregators\fileinfo.cpp`
- `0x1802070cc`: `onecore\base\appcompat\appraiser\decisionaggregators\fileinfo.cpp`
- `0x1802072b3`: `Failed to CreateFile on file %ls: [%d].`
- `0x1802072c3`: `Windows::Compat::Appraiser::FileInfo::GetNtfsFileId`
- `0x180207368`: `Windows::Compat::Appraiser::FileInfo::GetNtfsFileId`
- `0x180207092`: `Windows::Compat::Appraiser::FileInfo::AppendFileProperties`
- `0x1802070c5`: `Windows::Compat::Appraiser::FileInfo::AppendFileProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::FileInfo::AppendFileProperties(
        unsigned int a1,
        struct Windows::Compat::Appraiser::IPropertyAppender **a2)
{
  int RequiredSingleValue; // eax
  int appended; // ebx
  char v5; // dl
  __int64 v6; // r15
  unsigned __int64 i; // rbx
  int SpecifiedFileAttributes; // eax
  unsigned __int64 j; // r12
  const wchar_t *v10; // r13
  const unsigned __int16 *v11; // rdx
  const char *v12; // r15
  HANDLE FileW; // rax
  void *v14; // r13
  signed int LastError; // eax
  signed int v16; // ebx
  char v17; // dl
  DWORD nFileIndexHigh; // r15d
  DWORD nFileIndexLow; // r12d
  signed int v20; // eax
  volatile signed __int64 *v21; // rcx
  void **v22; // rdx
  __int64 v23; // r15
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // eax
  int v27; // eax
  struct Windows::Compat::Appraiser::IPropertyAppender **v28; // r15
  int v29; // eax
  int v30; // eax
  const char *dwCreationDisposition; // [rsp+28h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+30h] [rbp-D8h]
  const char *dwFlagsAndAttributesa; // [rsp+30h] [rbp-D8h]
  const char *hTemplateFile; // [rsp+38h] [rbp-D0h]
  unsigned __int16 *hTemplateFilea; // [rsp+38h] [rbp-D0h]
  __int64 v37; // [rsp+40h] [rbp-C8h]
  DWORD v38; // [rsp+40h] [rbp-C8h]
  DWORD v39; // [rsp+40h] [rbp-C8h]
  char v40; // [rsp+68h] [rbp-A0h]
  unsigned int v41[2]; // [rsp+70h] [rbp-98h] BYREF
  LPCWSTR lpFileName; // [rsp+78h] [rbp-90h] BYREF
  struct Windows::Compat::Appraiser::IPropertyAppender **v43; // [rsp+80h] [rbp-88h] BYREF
  const char *v44; // [rsp+88h] [rbp-80h] BYREF
  const char *v45; // [rsp+90h] [rbp-78h] BYREF
  const size_t *v46; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v47; // [rsp+A0h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-50h]
  _DWORD v50[2]; // [rsp+C8h] [rbp-40h] BYREF
  char *v51; // [rsp+D0h] [rbp-38h]
  int v52; // [rsp+D8h] [rbp-30h]
  const wchar_t *v53; // [rsp+E0h] [rbp-28h]
  int v54; // [rsp+E8h] [rbp-20h]
  const wchar_t *v55; // [rsp+F0h] [rbp-18h]
  int v56; // [rsp+F8h] [rbp-10h]
  const wchar_t *v57; // [rsp+100h] [rbp-8h]
  int v58; // [rsp+108h] [rbp+0h]
  const wchar_t *v59; // [rsp+110h] [rbp+8h]
  int v60; // [rsp+118h] [rbp+10h]
  const wchar_t *v61; // [rsp+120h] [rbp+18h]
  int v62; // [rsp+128h] [rbp+20h]
  const wchar_t *v63; // [rsp+130h] [rbp+28h]
  int v64; // [rsp+138h] [rbp+30h]
  const wchar_t *v65; // [rsp+140h] [rbp+38h]
  int v66; // [rsp+148h] [rbp+40h]
  const wchar_t *v67; // [rsp+150h] [rbp+48h]
  int v68; // [rsp+158h] [rbp+50h]
  const wchar_t *v69; // [rsp+160h] [rbp+58h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+168h] [rbp+60h] BYREF
  struct _SYSTEMTIME v71; // [rsp+1A8h] [rbp+A0h] BYREF
  _BYTE v72[1408]; // [rsp+1B8h] [rbp+B0h] BYREF
  unsigned __int16 v73[16]; // [rsp+738h] [rbp+630h] BYREF
  unsigned __int16 v74[16]; // [rsp+758h] [rbp+650h] BYREF
  char v75[144]; // [rsp+778h] [rbp+670h] BYREF

  v49 = -2;
  v43 = a2;
  v41[0] = a1;
  lpFileName = 0;
  `eh vector constructor iterator'(
    v72,
    0x20u,
    0x2Cu,
    (void (*)(void *))WString::WString,
    (void (*)(void *))WString::~WString);
  v50[0] = 17;
  v51 = (char *)L"FileId";
  v52 = 0;
  v53 = L"Name";
  v54 = 36;
  v55 = L"BOE_ProgramId";
  v56 = 23;
  v57 = L"COMPANY_NAME";
  v58 = 28;
  v59 = L"PRODUCT_NAME";
  v60 = 29;
  v61 = L"PRODUCT_VERSION";
  v62 = 8;
  v63 = L"LINK_DATE";
  v64 = 11;
  v65 = L"BIN_PRODUCT_VERSION";
  v66 = 10;
  v67 = L"BinFileVersion";
  v68 = 22;
  v69 = L"FILE_VERSION";
  memset_0(v72, 0, sizeof(v72));
  RequiredSingleValue = Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(
                          &lpFileName,
                          L"LowerCaseLongPath",
                          *a2);
  appended = RequiredSingleValue;
  if ( RequiredSingleValue >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xEAu,
        "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
        "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
        "Error getting file path: [0x%x].",
        RequiredSingleValue);
    v6 = 0;
    for ( i = 0; i < 0xA; ++i )
    {
      if ( !(*(__int64 (__fastcall **)(struct Windows::Compat::Appraiser::IPropertyAppender *, char *))(*(_QWORD *)*a2 + 40LL))(
              *a2,
              (&v51)[2 * i]) )
        _bittestandset64(&v6, (unsigned int)v50[4 * i]);
    }
    SpecifiedFileAttributes = Far::RetrieveSpecifiedFileAttributes(v72, lpFileName, v6);
    appended = SpecifiedFileAttributes;
    if ( SpecifiedFileAttributes < 0 )
    {
      LODWORD(hTemplateFile) = SpecifiedFileAttributes;
      dwFlagsAndAttributes = "Error calling FAR: [0x%x].";
      v5 = 4;
      goto LABEL_3;
    }
    v40 = 0;
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x104u,
        "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
        "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
        "Error calling FAR: [0x%x].",
        SpecifiedFileAttributes);
    for ( j = 0; j < 0xA; ++j )
    {
      if ( _bittest64(&v6, (unsigned int)v50[4 * j]) )
      {
        v10 = (const wchar_t *)(&v51)[2 * j];
        v11 = *(const unsigned __int16 **)&v72[32 * v50[4 * j] + 16];
        if ( !v11 || !*(_DWORD *)&v72[32 * v50[4 * j] + 8] )
          v11 = (const unsigned __int16 *)&v72[32 * v50[4 * j] + 24];
        appended = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(
                     (const unsigned __int16 *)(&v51)[2 * j],
                     v11,
                     v41,
                     v43[3]);
        if ( appended < 0 )
        {
          LODWORD(v37) = appended;
          hTemplateFilea = (unsigned __int16 *)v10;
          v17 = 26;
          goto LABEL_31;
        }
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x11Au,
            "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
            "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
            "Failed to append property %ls: [0x%x].",
            v10,
            appended);
        v40 = 1;
      }
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    v12 = (const char *)lpFileName;
    FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v14 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      v16 = LastError;
      if ( LastError > 0 )
        v16 = (unsigned __int16)LastError | 0x80070000;
      if ( v16 >= 0 )
        v16 = -2147467259;
      v38 = GetLastError();
      LODWORD(dwCreationDisposition) = v16;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        101,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
        "Windows::Compat::Appraiser::FileInfo::GetNtfsFileId",
        dwCreationDisposition,
        (int)"Failed to CreateFile on file %ls: [%d].",
        v12,
        v38);
    }
    else
    {
      if ( GetFileInformationByHandle(FileW, &FileInformation) )
      {
        nFileIndexHigh = FileInformation.nFileIndexHigh;
        nFileIndexLow = FileInformation.nFileIndexLow;
        v16 = 0;
      }
      else
      {
        nFileIndexHigh = 0;
        nFileIndexLow = 0;
        v20 = GetLastError();
        v16 = v20;
        if ( v20 > 0 )
          v16 = (unsigned __int16)v20 | 0x80070000;
        if ( v16 >= 0 )
          v16 = -2147467259;
        v39 = GetLastError();
        LODWORD(dwCreationDisposition) = v16;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          107,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
          "Windows::Compat::Appraiser::FileInfo::GetNtfsFileId",
          dwCreationDisposition,
          (int)"Failed to GetFileInformationByHandle on file %ls: [%d].",
          (const char *)lpFileName,
          v39);
      }
      CloseHandle(v14);
      if ( v16 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x125u,
            "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
            "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
            "Failed to get NTFS file id, swallowing error: [0x%x].",
            v16);
        v26 = StringCchPrintfW(v73, 0x10u, L"%d", nFileIndexHigh);
        appended = v26;
        if ( v26 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x12Au,
              "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
              "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
              "Failed to call StringCchPrintfW on %d: [0x%x].",
              nFileIndexHigh,
              v26);
          v27 = StringCchPrintfW(v74, 0x10u, L"%d", nFileIndexLow);
          appended = v27;
          if ( v27 >= 0 )
          {
            if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
              Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                0x12Du,
                "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
                "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
                "Failed to call StringCchPrintfW on %d: [0x%x].",
                nFileIndexLow,
                v27);
            v28 = v43;
            v29 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"NtfsIdHigh", v73, v41, v43[3]);
            appended = v29;
            if ( v29 >= 0 )
            {
              if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                  0x13Cu,
                  "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
                  "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
                  "Failed to append property %ls: [0x%x].",
                  v73,
                  v29);
              v30 = Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(L"NtfsIdLow", v74, v41, v28[3]);
              appended = v30;
              if ( v30 >= 0 )
              {
                if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
                  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
                    0x142u,
                    "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
                    "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
                    "Failed to append property %ls: [0x%x].",
                    v74,
                    v30);
                goto LABEL_69;
              }
              LODWORD(v37) = v30;
              hTemplateFilea = v74;
              dwFlagsAndAttributesa = "Failed to append property %ls: [0x%x].";
              v17 = 66;
            }
            else
            {
              LODWORD(v37) = v29;
              hTemplateFilea = v73;
              v17 = 60;
LABEL_31:
              dwFlagsAndAttributesa = "Failed to append property %ls: [0x%x].";
            }
          }
          else
          {
            LODWORD(v37) = v27;
            LODWORD(hTemplateFilea) = nFileIndexLow;
            dwFlagsAndAttributesa = "Failed to call StringCchPrintfW on %d: [0x%x].";
            v17 = 45;
          }
        }
        else
        {
          LODWORD(v37) = v26;
          LODWORD(hTemplateFilea) = nFileIndexHigh;
          dwFlagsAndAttributesa = "Failed to call StringCchPrintfW on %d: [0x%x].";
          v17 = 42;
        }
        LODWORD(dwCreationDisposition) = appended;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          v17,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
          "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
          dwCreationDisposition,
          (int)dwFlagsAndAttributesa,
          (const char *)hTemplateFilea,
          v37);
        goto LABEL_70;
      }
    }
    LODWORD(hTemplateFilea) = v16;
    LODWORD(dwCreationDisposition) = v16;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      37,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
      "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
      dwCreationDisposition,
      (int)"Failed to get NTFS file id, swallowing error: [0x%x].",
      (const char *)hTemplateFilea);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v50);
    v21 = (volatile signed __int64 *)v50;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v21 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v21,
      _InterlockedExchangeAdd64(v21 + 17, 0),
      v75);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v22);
    v23 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v43 = (struct Windows::Compat::Appraiser::IPropertyAppender **)v75;
      v41[0] = v16;
      v44 = "Windows::Compat::Appraiser::FileInfo::AppendFileProperties";
      v45 = "onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp";
      LODWORD(lpFileName) = 293;
      v46 = &szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v71 = SystemTime;
      v47 = &v71;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v23,
        (__int64)byte_1802A7C55,
        v24,
        v25,
        (__int64 *)&v47,
        &v46,
        (__int64)&lpFileName,
        &v45,
        &v44,
        (__int64)v41,
        (const char **)&v43);
    }
    if ( !v40 )
    {
      appended = 1;
      goto LABEL_70;
    }
LABEL_69:
    appended = 0;
    goto LABEL_70;
  }
  LODWORD(hTemplateFile) = RequiredSingleValue;
  dwFlagsAndAttributes = "Error getting file path: [0x%x].";
  v5 = -22;
LABEL_3:
  LODWORD(dwCreationDisposition) = appended;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v5,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\decisionaggregators\\fileinfo.cpp",
    "Windows::Compat::Appraiser::FileInfo::AppendFileProperties",
    dwCreationDisposition,
    (int)dwFlagsAndAttributes,
    hTemplateFile);
LABEL_70:
  `eh vector destructor iterator'(v72, 0x20u, 0x2Cu, (void (*)(void *))WString::~WString);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x180206f28  mov     rax, rsp
0x180206f2b  push    rbp
0x180206f2c  push    rsi
0x180206f2d  push    rdi
0x180206f2e  push    r12
0x180206f30  push    r13
0x180206f32  push    r14
0x180206f34  push    r15
0x180206f36  lea     rbp, [rax-748h]
0x180206f3d  sub     rsp, 810h
0x180206f44  mov     [rbp+740h+var_790], 0FFFFFFFFFFFFFFFEh
0x180206f4c  mov     [rax+18h], rbx
0x180206f50  mov     rax, cs:__security_cookie
0x180206f57  xor     rax, rsp
0x180206f5a  mov     [rbp+740h+var_40], rax
0x180206f61  mov     r13, rdx
0x180206f64  mov     [rsp+840h+var_7C8], rdx
0x180206f69  mov     [rsp+840h+var_7D8], ecx
0x180206f6d  mov     [rsp+840h+lpFileName], 0
0x180206f76  lea     rax, ??1WString@@UEAA@XZ; WString::~WString(void)
0x180206f7d  mov     qword ptr [rsp+840h+dwCreationDisposition], rax; void (*)(void *)
0x180206f82  lea     r9, ??0WString@@QEAA@XZ; void (*)(void *)
0x180206f89  mov     edx, 20h ; ' '; unsigned __int64
0x180206f8e  lea     r8d, [rdx+0Ch]; unsigned __int64
0x180206f92  lea     rcx, [rbp+740h+var_690]; void *
0x180206f99  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x180206f9e  nop
0x180206f9f  mov     [rbp+740h+var_780], 11h
0x180206fa6  lea     rax, aFileid; "FileId"
0x180206fad  mov     [rbp+740h+var_778], rax
0x180206fb1  mov     [rbp+740h+var_770], 0
0x180206fb8  lea     rax, aName_0; "Name"
0x180206fbf  mov     [rbp+740h+var_768], rax
0x180206fc3  mov     [rbp+740h+var_760], 24h ; '$'
0x180206fca  lea     rax, aBoeProgramid; "BOE_ProgramId"
0x180206fd1  mov     [rbp+740h+var_758], rax
0x180206fd5  mov     [rbp+740h+var_750], 17h
0x180206fdc  lea     rax, aCompanyName; "COMPANY_NAME"
0x180206fe3  mov     [rbp+740h+var_748], rax
0x180206fe7  mov     [rbp+740h+var_740], 1Ch
0x180206fee  lea     rax, aProductName; "PRODUCT_NAME"
0x180206ff5  mov     [rbp+740h+var_738], rax
0x180206ff9  mov     [rbp+740h+var_730], 1Dh
0x180207000  lea     rax, aProductVersion; "PRODUCT_VERSION"
0x180207007  mov     [rbp+740h+var_728], rax
0x18020700b  mov     [rbp+740h+var_720], 8
0x180207012  lea     rax, aLinkDate; "LINK_DATE"
0x180207019  mov     [rbp+740h+var_718], rax
0x18020701d  mov     [rbp+740h+var_710], 0Bh
0x180207024  lea     rax, aBinProductVers; "BIN_PRODUCT_VERSION"
0x18020702b  mov     [rbp+740h+var_708], rax
0x18020702f  mov     [rbp+740h+var_700], 0Ah
0x180207036  lea     rax, aBinfileversion_0; "BinFileVersion"
0x18020703d  mov     [rbp+740h+var_6F8], rax
0x180207041  mov     [rbp+740h+var_6F0], 16h
0x180207048  lea     rax, aFileVersion; "FILE_VERSION"
0x18020704f  mov     [rbp+740h+var_6E8], rax
0x180207053  xor     edx, edx; Val
0x180207055  mov     r8d, 580h; Size
0x18020705b  lea     rcx, [rbp+740h+var_690]; void *
0x180207062  call    memset_0
0x180207067  mov     r8, [r13+0]; struct Windows::Compat::Appraiser::IPropertyListEnumerator *
0x18020706b  lea     rdx, aLowercaselongp_0; "LowerCaseLongPath"
0x180207072  lea     rcx, [rsp+840h+lpFileName]; unsigned __int16 **
0x180207077  call    ?GetRequiredSingleValue@AssetUtils@Appraiser@Compat@Windows@@SAJPEAPEBGPEBGPEAVIPropertyListEnumerator@234@@Z; Windows::Compat::Appraiser::AssetUtils::GetRequiredSingleValue(ushort const * *,ushort const *,Windows::Compat::Appraiser::IPropertyListEnumerator *)
0x18020707c  mov     ebx, eax
0x18020707e  test    eax, eax
0x180207080  jns     short loc_1802070B8
0x180207082  mov     dword ptr [rsp+840h+hTemplateFile], eax; char *
0x180207086  lea     r9, aErrorGettingFi_0; "Error getting file path: [0x%x]."
0x18020708d  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], r9; int
0x180207092  lea     r9, aWindowsCompatA_328; "Windows::Compat::Appraiser::FileInfo::A"...
0x180207099  lea     r8, aOnecoreBaseApp_57; "onecore\\base\\appcompat\\appraiser\\de"...
0x1802070a0  mov     edx, 0EAh; bool
0x1802070a5  mov     ecx, 1; this
0x1802070aa  mov     [rsp+840h+dwCreationDisposition], ebx; char *
0x1802070ae  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1802070b3  jmp     loc_1802076DA
0x1802070b8  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802070be  mov     edi, 1
0x1802070c3  and     eax, edi
0x1802070c5  lea     r14, aWindowsCompatA_328; "Windows::Compat::Appraiser::FileInfo::A"...
0x1802070cc  lea     rsi, aOnecoreBaseApp_57; "onecore\\base\\appcompat\\appraiser\\de"...
0x1802070d3  test    al, al
0x1802070d5  jz      short loc_1802070F2
0x1802070d7  mov     [rsp+840h+dwCreationDisposition], ebx
0x1802070db  lea     r9, aErrorGettingFi_0; "Error getting file path: [0x%x]."
0x1802070e2  mov     r8, r14; char *
0x1802070e5  mov     rdx, rsi; char *
0x1802070e8  mov     ecx, 0EAh; unsigned int
0x1802070ed  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1802070f2  xor     r15d, r15d
0x1802070f5  xor     ebx, ebx
0x1802070f7  mov     r12, rbx
0x1802070fa  add     r12, r12
0x1802070fd  mov     rcx, [r13+0]
0x180207101  mov     rax, [rcx]
0x180207104  mov     rdx, [rbp+r12*8+740h+var_778]
0x180207109  mov     rax, [rax+28h]
0x18020710d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180207112  test    rax, rax
0x180207115  jnz     short loc_180207120
0x180207117  mov     eax, [rbp+r12*8+740h+var_780]
0x18020711c  bts     r15, rax
0x180207120  add     rbx, rdi
0x180207123  cmp     rbx, 0Ah
0x180207127  jb      short loc_1802070F7
0x180207129  mov     r8, r15
0x18020712c  mov     rdx, [rsp+840h+lpFileName]
0x180207131  lea     rcx, [rbp+740h+var_690]
0x180207138  call    ?RetrieveSpecifiedFileAttributes@Far@@SAJAEAUtagFILE_ATTRIBUTE@@PEBG_KW4FAR_MODE_FLAGS@@@Z; Far::RetrieveSpecifiedFileAttributes(tagFILE_ATTRIBUTE &,ushort const *,unsigned __int64,FAR_MODE_FLAGS)
0x18020713d  mov     ebx, eax
0x18020713f  test    eax, eax
0x180207141  jns     short loc_180207165
0x180207143  mov     dword ptr [rsp+840h+hTemplateFile], eax
0x180207147  lea     r9, aErrorCallingFa; "Error calling FAR: [0x%x]."
0x18020714e  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], r9
0x180207153  mov     r9, r14
0x180207156  mov     r8, rsi
0x180207159  mov     edx, 104h
0x18020715e  mov     ecx, edi
0x180207160  jmp     loc_1802070AA
0x180207165  mov     [rsp+840h+var_7E0], 0
0x18020716a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180207170  and     eax, edi
0x180207172  test    al, al
0x180207174  jz      short loc_180207191
0x180207176  mov     [rsp+840h+dwCreationDisposition], ebx
0x18020717a  lea     r9, aErrorCallingFa; "Error calling FAR: [0x%x]."
0x180207181  mov     r8, r14; char *
0x180207184  mov     rdx, rsi; char *
0x180207187  mov     ecx, 104h; unsigned int
0x18020718c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180207191  xor     r12d, r12d
0x180207194  mov     rcx, r12
0x180207197  add     rcx, rcx
0x18020719a  mov     eax, [rbp+rcx*8+740h+var_780]
0x18020719e  bt      r15, rax
0x1802071a2  jnb     short loc_180207223
0x1802071a4  mov     r13, [rbp+rcx*8+740h+var_778]
0x1802071a9  mov     eax, [rbp+rcx*8+740h+var_780]
0x1802071ad  shl     rax, 5
0x1802071b1  mov     rdx, [rbp+rax+740h+var_680]
0x1802071b9  test    rdx, rdx
0x1802071bc  jz      short loc_1802071C8
0x1802071be  cmp     [rbp+rax+740h+var_688], 0
0x1802071c6  jnz     short loc_1802071D2
0x1802071c8  lea     rdx, [rbp+740h+var_678]
0x1802071cf  add     rdx, rax; unsigned __int16 *
0x1802071d2  mov     rax, [rsp+840h+var_7C8]
0x1802071d7  mov     r9, [rax+18h]; struct Windows::Compat::Appraiser::IPropertyAppender *
0x1802071db  lea     r8, [rsp+840h+var_7D8]; unsigned int *
0x1802071e0  mov     rcx, r13; unsigned __int16 *
0x1802071e3  call    ?CreateAndAppendProperty@Utilities@Appraiser@Compat@Windows@@SAJPEBG0PEAKPEAVIPropertyAppender@234@@Z; Windows::Compat::Appraiser::Utilities::CreateAndAppendProperty(ushort const *,ushort const *,ulong *,Windows::Compat::Appraiser::IPropertyAppender *)
0x1802071e8  mov     ebx, eax
0x1802071ea  test    eax, eax
0x1802071ec  js      loc_1802072DE
0x1802071f2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1802071f8  and     eax, edi
0x1802071fa  test    al, al
0x1802071fc  jz      short loc_18020721E
0x1802071fe  mov     [rsp+840h+dwFlagsAndAttributes], ebx
0x180207202  mov     qword ptr [rsp+840h+dwCreationDisposition], r13
0x180207207  lea     r9, aFailedToAppend_109; "Failed to append property %ls: [0x%x]."
0x18020720e  mov     r8, r14; char *
0x180207211  mov     rdx, rsi; char *
0x180207214  mov     ecx, 11Ah; unsigned int
0x180207219  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x18020721e  mov     [rsp+840h+var_7E0], dil
0x180207223  add     r12, rdi
0x180207226  cmp     r12, 0Ah
0x18020722a  jb      loc_180207194
0x180207230  xorps   xmm0, xmm0
0x180207233  xor     eax, eax
0x180207235  movups  xmmword ptr [rbp+740h+FileInformation.dwFileAttributes], xmm0
0x180207239  movups  xmmword ptr [rbp+740h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18020723d  movups  xmmword ptr [rbp+740h+FileInformation.nFileSizeHigh], xmm0
0x180207244  mov     [rbp+740h+FileInformation.nFileIndexLow], eax
0x18020724a  mov     [rsp+840h+hTemplateFile], rax; hTemplateFile
0x18020724f  mov     [rsp+840h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180207257  mov     [rsp+840h+dwCreationDisposition], 3; dwCreationDisposition
0x18020725f  xor     r9d, r9d; lpSecurityAttributes
0x180207262  mov     r8d, edi; dwShareMode
0x180207265  mov     edx, 80000000h; dwDesiredAccess
0x18020726a  mov     r15, [rsp+840h+lpFileName]
0x18020726f  mov     rcx, r15; lpFileName
0x180207272  call    cs:__imp_CreateFileW
0x180207278  mov     r13, rax
0x18020727b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18020727f  jnz     loc_18020730E
0x180207285  call    cs:__imp_GetLastError
0x18020728b  mov     ebx, eax
0x18020728d  test    eax, eax
0x18020728f  jle     short loc_18020729A
0x180207291  movzx   ebx, ax
0x180207294  or      ebx, 80070000h
0x18020729a  mov     eax, 80004005h
0x18020729f  test    ebx, ebx
0x1802072a1  cmovns  ebx, eax
0x1802072a4  call    cs:__imp_GetLastError
0x1802072aa  mov     dword ptr [rsp+840h+var_808], eax
0x1802072ae  mov     [rsp+840h+hTemplateFile], r15; char *
0x1802072b3  lea     rax, aFailedToCreate_53; "Failed to CreateFile on file %ls: [%d]."
0x1802072ba  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], rax; int
0x1802072bf  mov     [rsp+840h+dwCreationDisposition], ebx; char *
0x1802072c3  lea     r9, aWindowsCompatA_81; "Windows::Compat::Appraiser::FileInfo::G"...
0x1802072ca  mov     r8, rsi; unsigned int
0x1802072cd  mov     edx, 165h; bool
0x1802072d2  mov     ecx, edi; this
0x1802072d4  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1802072d9  jmp     loc_1802073A1
0x1802072de  mov     dword ptr [rsp+840h+var_808], ebx
0x1802072e2  mov     [rsp+840h+hTemplateFile], r13; char *
0x1802072e7  mov     edx, 11Ah; bool
0x1802072ec  lea     rax, aFailedToAppend_109; "Failed to append property %ls: [0x%x]."
0x1802072f3  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], rax; int
0x1802072f8  mov     [rsp+840h+dwCreationDisposition], ebx; char *
0x1802072fc  mov     r9, r14; char *
0x1802072ff  mov     r8, rsi; unsigned int
0x180207302  mov     ecx, edi; this
0x180207304  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180207309  jmp     loc_1802076DA
0x18020730e  lea     rdx, [rbp+740h+FileInformation]; lpFileInformation
0x180207312  mov     rcx, r13; hFile
0x180207315  call    cs:__imp_GetFileInformationByHandle
0x18020731b  test    eax, eax
0x18020731d  jnz     short loc_180207380
0x18020731f  xor     r15d, r15d
0x180207322  xor     r12d, r12d
0x180207325  call    cs:__imp_GetLastError
0x18020732b  mov     ebx, eax
0x18020732d  test    eax, eax
0x18020732f  jle     short loc_18020733A
0x180207331  movzx   ebx, ax
0x180207334  or      ebx, 80070000h
0x18020733a  mov     eax, 80004005h
0x18020733f  test    ebx, ebx
0x180207341  cmovns  ebx, eax
0x180207344  call    cs:__imp_GetLastError
0x18020734a  mov     dword ptr [rsp+840h+var_808], eax
0x18020734e  mov     rax, [rsp+840h+lpFileName]
0x180207353  mov     [rsp+840h+hTemplateFile], rax; char *
0x180207358  lea     rax, aFailedToGetfil; "Failed to GetFileInformationByHandle on"...
0x18020735f  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], rax; int
0x180207364  mov     [rsp+840h+dwCreationDisposition], ebx; char *
0x180207368  lea     r9, aWindowsCompatA_81; "Windows::Compat::Appraiser::FileInfo::G"...
0x18020736f  mov     r8, rsi; unsigned int
0x180207372  mov     edx, 16Bh; bool
0x180207377  mov     ecx, edi; this
0x180207379  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18020737e  jmp     short loc_180207390
0x180207380  mov     r15d, [rbp+740h+FileInformation.nFileIndexHigh]
0x180207387  mov     r12d, [rbp+740h+FileInformation.nFileIndexLow]
0x18020738e  xor     ebx, ebx
0x180207390  mov     rcx, r13; hObject
0x180207393  call    cs:__imp_CloseHandle
0x180207399  test    ebx, ebx
0x18020739b  jns     loc_180207501
0x1802073a1  mov     dword ptr [rsp+840h+hTemplateFile], ebx; char *
0x1802073a5  lea     r9, aFailedToGetNtf_0; "Failed to get NTFS file id, swallowing "...
0x1802073ac  mov     qword ptr [rsp+840h+dwFlagsAndAttributes], r9; int
0x1802073b1  mov     [rsp+840h+dwCreationDisposition], ebx; char *
0x1802073b5  mov     r9, r14; char *
0x1802073b8  mov     r8, rsi; unsigned int
0x1802073bb  mov     edx, 125h; bool
0x1802073c0  mov     ecx, edi; this
0x1802073c2  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1802073c7  lea     rcx, [rbp+740h+var_780]; this
0x1802073cb  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1802073d0  lea     rcx, [rbp+740h+var_780]
0x1802073d4  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1802073db  test    rax, rax
0x1802073de  cmovnz  rcx, rax; this
0x1802073e2  xor     edx, edx
0x1802073e4  lock xadd [rcx+88h], rdx; unsigned __int64
0x1802073ed  lea     r8, [rbp+740h+var_D0]; char *
0x1802073f4  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1802073f9  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180207400  jz      short loc_18020740E
0x180207402  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180207409  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18020740e  mov     r15, cs:qword_1802C9628
0x180207415  mov     eax, [r15]
0x180207418  cmp     eax, 5
0x18020741b  jbe     loc_1802074EF
0x180207421  mov     rcx, [r15+18h]
0x180207425  mov     rax, [r15+10h]
0x180207429  mov     rdx, 200000000000h
0x180207433  test    rdx, rax
0x180207436  jz      loc_1802074EF
0x18020743c  mov     rax, rcx
0x18020743f  and     rax, rdx
0x180207442  cmp     rax, rcx
0x180207445  jnz     loc_1802074EF
0x18020744b  lea     rax, [rbp+740h+var_D0]
0x180207452  mov     [rsp+840h+var_7C8], rax
0x180207457  mov     [rsp+840h+var_7D8], ebx
0x18020745b  mov     [rbp+740h+var_7C0], r14
0x18020745f  mov     [rbp+740h+var_7B8], rsi
0x180207463  mov     dword ptr [rsp+840h+lpFileName], 125h
  ... truncated ...
```
