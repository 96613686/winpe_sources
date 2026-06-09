# Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag(ushort *,unsigned __int64,ushort *,unsigned __int64,ushort *,unsigned __int64,bool &,bool &,bool,void *,ulong,ushort const *)

- ea: `0x1801fa184`
- end: `0x1801fadc2`
- name: `?GetAppraiserDataTag@SdbUtils@Appraiser@Compat@Windows@@CAJPEAG_K0101AEA_N2_NPEAXKPEBG@Z`
- size: `3134`
- prototype: `__int64 __usercall@<rax>(unsigned __int16 *@<rcx>, unsigned __int64@<rdx>, unsigned __int16 *@<r8>, unsigned __int64@<r9>, unsigned __int16 *, unsigned __int64, bool *, bool *, bool, void *, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1801fadc8`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180011c5c`
- `0x180011d20`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1801baf00`
- `0x1801bbb00`
- `0x1801bbc0c`
- `0x1801bbd54`
- `0x1801fa184`
- `0x1801fc9d4`
- `0x1802174cc`
- `0x1802174d8`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1801fa322`
- `KERNEL32!GetSystemTime` at `0x1801fa70a`
- `KERNEL32!GetSystemTime` at `0x1801fa8f5`
- `KERNEL32!GetSystemTime` at `0x1801face1`
- `KERNEL32!GetSystemTime` at `0x1801fa322`
- `KERNEL32!GetSystemTime` at `0x1801fa70a`
- `KERNEL32!GetSystemTime` at `0x1801fa8f5`
- `KERNEL32!GetSystemTime` at `0x1801face1`
- `KERNEL32!GetProcessHeap` at `0x1801fad54`
- `KERNEL32!GetProcessHeap` at `0x1801fad54`
- `KERNEL32!HeapFree` at `0x1801fad62`
- `KERNEL32!HeapFree` at `0x1801fad62`

## string_xrefs

- `0x1801fa250`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fa3c5`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fa400`: `onecore\base\appcompat\appraiser\datasource\sdbutils.cpp`
- `0x1801fa407`: `Failed to copy string [0x%x].`
- `0x1801fa4f8`: `Failed to copy string [0x%x].`
- `0x1801fa526`: `Failed to copy string [0x%x].`
- `0x1801fa5bc`: `Failed to copy string [0x%x].`
- `0x1801fa5de`: `Failed to copy string [0x%x].`
- `0x1801fab5a`: `Failed to copy string [0x%x].`
- `0x1801fab77`: `Failed to copy string [0x%x].`
- `0x1801fa3a9`: `Failed to read name tag from sdb (parent TAGREF: 0x%X8).`
- `0x1801fa241`: `Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag`
- `0x1801fa3b9`: `Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag`
- `0x1801fa3f9`: `Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag`
- `0x1801fa9ea`: `Failed to read dword value tag from sdb.`
- `0x1801fadb1`: `Failed to read string value tag from sdb.`
- `0x1801fa777`: `Failed to read value type tag from sdb.`
- `0x1801faaf6`: `Failed to copy string value: [0x%x].`
- `0x1801fab10`: `Failed to copy string value: [0x%x].`
- `0x1801fa974`: `Failed to read qword value tag from sdb.`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag(
        unsigned __int16 *a1,
        __int64 a2,
        unsigned __int16 *a3,
        __int64 a4,
        unsigned __int16 *a5,
        unsigned __int64 a6,
        bool *a7,
        bool *a8,
        bool a9,
        void *a10,
        unsigned int a11,
        unsigned __int16 *a12)
{
  __int64 v12; // r13
  unsigned int FirstTagRef; // eax
  volatile signed __int64 *v15; // rcx
  void **v16; // rdx
  int v17; // ebx
  int v18; // r8d
  int v19; // r9d
  void *v20; // rdx
  unsigned __int16 **v21; // rax
  int v22; // ebx
  char v23; // dl
  int v24; // eax
  unsigned int v25; // ecx
  const unsigned __int16 *v26; // r8
  const char *v27; // r9
  int v28; // eax
  unsigned int v29; // eax
  volatile signed __int64 *v30; // rcx
  void **v31; // rdx
  int DWORDTagRef; // eax
  int v33; // ebx
  const char *v34; // rax
  char v35; // dl
  int v36; // eax
  int v37; // eax
  unsigned __int16 v38; // r8
  unsigned int v39; // eax
  volatile signed __int64 *v40; // rcx
  void **v41; // rdx
  int v42; // ebx
  int v43; // ebx
  __int64 QWORDTagRef; // rax
  const char *v45; // r9
  unsigned int v46; // ecx
  unsigned int v47; // eax
  unsigned __int16 *v48; // r9
  const char *v49; // r9
  char v50; // dl
  unsigned __int16 *v51; // r15
  int v52; // eax
  int v53; // eax
  volatile signed __int64 *v54; // rcx
  void **v55; // rdx
  int v56; // ebx
  int v57; // r8d
  int v58; // r9d
  void *v59; // rdi
  HANDLE ProcessHeap; // rax
  char *v62; // [rsp+20h] [rbp-E0h]
  void *v63; // [rsp+28h] [rbp-D8h]
  const char *v64; // [rsp+28h] [rbp-D8h]
  const char *v65; // [rsp+28h] [rbp-D8h]
  char *v66; // [rsp+30h] [rbp-D0h]
  char *v67; // [rsp+30h] [rbp-D0h]
  unsigned __int16 **v68; // [rsp+38h] [rbp-C8h]
  void *p_lpMem; // [rsp+40h] [rbp-C0h]
  unsigned __int16 **v70; // [rsp+48h] [rbp-B8h]
  unsigned __int16 **v71; // [rsp+50h] [rbp-B0h]
  bool v72; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v73; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int16 *v74; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v75; // [rsp+78h] [rbp-88h] BYREF
  char *v76; // [rsp+80h] [rbp-80h] BYREF
  LPVOID lpMem; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 *v78; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 *v79; // [rsp+98h] [rbp-68h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  struct _SYSTEMTIME v81; // [rsp+B0h] [rbp-50h] BYREF
  struct _SYSTEMTIME v82; // [rsp+C0h] [rbp-40h] BYREF
  char v83[144]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t String2[264]; // [rsp+160h] [rbp+60h] BYREF

  v12 = 0;
  v75 = a1;
  v78 = a12;
  v73 = a3;
  v79 = a5;
  v76 = (char *)a8;
  *a8 = 0;
  *a7 = 0;
  *a5 = 0;
  *a3 = 0;
  v72 = 0;
  *a1 = 0;
  lpMem = 0;
  FirstTagRef = SdbFindFirstTagRef(a10, a11, 0x6001u);
  if ( !FirstTagRef )
  {
    LODWORD(v66) = a11;
    LODWORD(v62) = -2138546173;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      222,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)"Encountered a missing name on data tag (TAGREF: 0x%X8).",
      v66);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
    v15 = (volatile signed __int64 *)String2;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v15 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v15,
      _InterlockedExchangeAdd64(v15 + 17, 0),
      v83);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v16);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 <= 5u
      || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
      || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
    {
      return 1;
    }
    LODWORD(v73) = 3038;
    v76 = v83;
    LODWORD(v74) = -2138546173;
    v78 = (unsigned __int16 *)&szValueBuf;
    lpMem = (LPVOID)"Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag";
    v75 = (unsigned __int16 *)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp";
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v79 = (unsigned __int16 *)&v81;
    v20 = &unk_1802A72BA;
    v71 = (unsigned __int16 **)&v76;
    v70 = &v74;
    p_lpMem = &lpMem;
    v68 = &v75;
    v67 = (char *)&v73;
    v63 = &v78;
    v21 = &v79;
    goto LABEL_10;
  }
  if ( !(unsigned int)SdbReadStringTagRef(a10, FirstTagRef, String2, 260) )
  {
    LODWORD(v66) = a11;
    v64 = "Failed to read name tag from sdb (parent TAGREF: 0x%X8).";
    v22 = -2138546173;
    v23 = -24;
LABEL_14:
    LODWORD(v62) = v22;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v23,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)v64,
      v66);
    return (unsigned int)v22;
  }
  v74 = 0;
  if ( !wcscmp_0(L"AppraiserData", String2) )
  {
    v24 = StringCchCopyW(a1, 0x104u, L"SdbAppraiserData");
    v22 = v24;
    if ( v24 < 0 )
    {
      LODWORD(v66) = v24;
      v64 = "Failed to copy string [0x%x].";
      v23 = -14;
      goto LABEL_14;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      goto LABEL_41;
    v25 = 3058;
    goto LABEL_40;
  }
  v12 = 21;
  if ( !wcsncmp_0(L"AppraiserResourceData", String2, 0x15u) )
    goto LABEL_23;
  v12 = 27;
  if ( !wcsncmp_0(L"AppraiserResourceBackupData", String2, 0x1Bu) )
  {
    *v76 = 1;
LABEL_23:
    *a7 = 1;
    v74 = L"SdbAppraiserResourceDataRedirectionInstruction";
    v26 = L"SdbAppraiserResourceData";
    goto LABEL_26;
  }
  v12 = 13;
  if ( wcsncmp_0(L"AppraiserData", String2, 0xDu) )
    goto LABEL_121;
  v26 = L"SdbAppraiserData";
LABEL_26:
  v22 = StringCchCopyW(a1, 0x104u, v26);
  if ( v22 < 0 )
  {
    v27 = "Failed to copy string [0x%x].";
    v23 = 20;
LABEL_28:
    LODWORD(v66) = v22;
    LODWORD(v64) = (_DWORD)v27;
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC14u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      "Failed to copy string [0x%x].",
      v22);
  v22 = StringCchCatW(v75, 0x104u, &String2[v12]);
  if ( v22 < 0 )
  {
    v27 = "Failed to extract property name [0x%x].";
    v23 = 23;
    goto LABEL_28;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC17u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      "Failed to extract property name [0x%x].",
      v22);
  if ( !*a7 )
    goto LABEL_41;
  v28 = StringCchCopyW(v79, 0x104u, v75);
  v22 = v28;
  if ( v28 < 0 )
  {
    LODWORD(v66) = v28;
    v23 = 28;
    v64 = "Failed to copy string [0x%x].";
    goto LABEL_14;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
    goto LABEL_41;
  v25 = 3100;
LABEL_40:
  Windows::Compat::Appraiser::WicaFactory::RunPrintf(
    v25,
    "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
    "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
    "Failed to copy string [0x%x].",
    v22);
LABEL_41:
  if ( !a9 && !*a7 )
    return 0;
  v29 = SdbFindFirstTagRef(a10, a11, 0x4018u);
  if ( !v29 )
  {
    LODWORD(v66) = a11;
    LODWORD(v62) = -2138546173;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      49,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)"Encountered a missing value type on data tag (TAGREF: 0x%X8).",
      v66);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
    v30 = (volatile signed __int64 *)String2;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v30 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v30,
      _InterlockedExchangeAdd64(v30 + 17, 0),
      v83);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v31);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 <= 5u
      || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
      || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
    {
      return 1;
    }
    LODWORD(v74) = 3121;
    v79 = (unsigned __int16 *)v83;
    LODWORD(v73) = -2138546173;
    lpMem = (LPVOID)&szValueBuf;
    v78 = (unsigned __int16 *)"Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag";
    v76 = "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp";
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v75 = (unsigned __int16 *)&v81;
    v20 = &unk_1802A715A;
    v71 = &v79;
    v70 = &v73;
    p_lpMem = &v78;
    v68 = (unsigned __int16 **)&v76;
    v67 = (char *)&v74;
    v63 = &lpMem;
    v21 = &v75;
    goto LABEL_10;
  }
  DWORDTagRef = SdbReadDWORDTagRef(a10, v29, 0xFFFFFFFFLL);
  v33 = DWORDTagRef;
  if ( DWORDTagRef == -1 )
  {
    v34 = "Failed to read value type tag from sdb.";
    v35 = 58;
LABEL_55:
    v22 = -2147024883;
    LODWORD(v62) = -2147024883;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v35,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)v34,
      v66);
    return (unsigned int)v22;
  }
  v36 = DWORDTagRef - 1;
  if ( v36 )
  {
    v37 = v36 - 3;
    if ( v37 )
    {
      if ( v37 != 7 )
      {
        LODWORD(v66) = v33;
        Windows::Compat::Appraiser::WriteLog(
          0,
          77,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
          0,
          (int)"Sdb had unsupported data tag value type of %d, skipping.",
          v66);
        return 1;
      }
      v38 = 20487;
    }
    else
    {
      v38 = 16409;
    }
  }
  else
  {
    v38 = 24606;
  }
  v39 = SdbFindFirstTagRef(a10, a11, v38);
  if ( !v39 )
  {
    LODWORD(v66) = a11;
    LODWORD(v62) = -2138546173;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      89,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)"Encountered a missing value on data tag (TAGREF: 0x%X8).",
      v66);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
    v40 = (volatile signed __int64 *)String2;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v40 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v40,
      _InterlockedExchangeAdd64(v40 + 17, 0),
      v83);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v41);
    v17 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 <= 5u
      || (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) == 0
      || (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) != *(_QWORD *)(qword_1802C9628 + 24) )
    {
      return 1;
    }
    LODWORD(v74) = 3161;
    v79 = (unsigned __int16 *)v83;
    LODWORD(v73) = -2138546173;
    lpMem = (LPVOID)&szValueBuf;
    v78 = (unsigned __int16 *)"Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag";
    v76 = "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp";
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v75 = (unsigned __int16 *)&v81;
    v20 = &unk_1802A71BD;
    v71 = &v79;
    v70 = &v73;
    p_lpMem = &v78;
    v68 = (unsigned __int16 **)&v76;
    v67 = (char *)&v74;
    v63 = &lpMem;
    v21 = &v75;
LABEL_10:
    v81 = SystemTime;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v17,
      (_DWORD)v20,
      v18,
      v19,
      (__int64)v21,
      (__int64)v63,
      (__int64)v67,
      (__int64)v68,
      (__int64)p_lpMem,
      (__int64)v70,
      (__int64)v71);
    return 1;
  }
  v42 = v33 - 1;
  if ( !v42 )
  {
    if ( !(unsigned int)SdbReadStringTagRef(a10, v39, v73, 260) )
    {
      v34 = "Failed to read string value tag from sdb.";
      v35 = 101;
      goto LABEL_55;
    }
    goto LABEL_111;
  }
  v43 = v42 - 3;
  if ( v43 )
  {
    if ( v43 != 7 )
      goto LABEL_111;
    QWORDTagRef = SdbReadQWORDTagRef(a10, v39);
    if ( QWORDTagRef == -1 )
    {
      v34 = "Failed to read qword value tag from sdb.";
      v35 = -93;
      goto LABEL_55;
    }
    v22 = StringCchPrintfW(v73, 0x104u, L"%llu", QWORDTagRef);
    if ( v22 < 0 )
    {
      v27 = "Failed to print qword value: [0x%x].";
      v23 = -89;
      goto LABEL_28;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      goto LABEL_111;
    v45 = "Failed to print qword value: [0x%x].";
    v46 = 3239;
    goto LABEL_110;
  }
  v47 = SdbReadDWORDTagRef(a10, v39, 0xFFFFFFFFLL);
  if ( v47 == -1 )
  {
    v34 = "Failed to read dword value tag from sdb.";
    v35 = 108;
    goto LABEL_55;
  }
  if ( !*a7 )
  {
    v22 = StringCchPrintfW(v73, 0x104u, L"%u", v47);
    if ( v22 < 0 )
    {
      v27 = "Failed to print dword value: [0x%x].";
      v23 = 114;
      goto LABEL_28;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
      goto LABEL_111;
    v45 = "Failed to print dword value: [0x%x].";
    v46 = 3186;
    goto LABEL_110;
  }
  v48 = (unsigned __int16 *)&szValueBuf;
  if ( v78 )
    v48 = v78;
  v22 = Windows::Compat::Appraiser::SdbUtils::InflateSdbResourceDataStringAlloc(
          (unsigned __int16 **)&lpMem,
          &v72,
          v47,
          v48);
  if ( v22 < 0 )
  {
    v49 = "Failed InflateSdbResourceDataStringAlloc: [0x%x]";
    v50 = 122;
    goto LABEL_92;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0xC7Au,
      "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      "Failed InflateSdbResourceDataStringAlloc: [0x%x]",
      v22);
  if ( v22 != 1 )
  {
    v22 = StringCchCopyW(v73, 0x104u, (const unsigned __int16 *)lpMem);
    if ( v22 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xC7Fu,
          "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
          "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
          "Failed to copy string value: [0x%x].",
          v22);
      if ( !v72 )
        goto LABEL_111;
      v51 = v75;
      v52 = StringCchCopyW(v75, 0x104u, v74);
      v22 = v52;
      if ( v52 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xC8Au,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
            "Failed to copy string [0x%x].",
            v52);
        v53 = StringCchCatW(v51, 0x104u, &String2[v12]);
        v22 = v53;
        if ( v53 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) == 0 )
          {
LABEL_111:
            v22 = 0;
            goto LABEL_122;
          }
          v45 = "Failed to extract property name [0x%x].";
          v46 = 3213;
LABEL_110:
          LODWORD(v62) = v22;
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            v46,
            "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
            "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
            v45,
            v62);
          goto LABEL_111;
        }
        LODWORD(v66) = v53;
        v50 = -115;
        v65 = "Failed to extract property name [0x%x].";
      }
      else
      {
        LODWORD(v66) = v52;
        v50 = -118;
        v65 = "Failed to copy string [0x%x].";
      }
LABEL_93:
      LODWORD(v62) = v22;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        v50,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
        "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
        v62,
        (int)v65,
        v66);
      goto LABEL_122;
    }
    v49 = "Failed to copy string value: [0x%x].";
    v50 = 127;
LABEL_92:
    LODWORD(v66) = v22;
    LODWORD(v65) = (_DWORD)v49;
    goto LABEL_93;
  }
  if ( *v76 )
  {
    LODWORD(v66) = a11;
    LODWORD(v62) = -2138546173;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      147,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp",
      "Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag",
      v62,
      (int)"Encountered a missing backup resource on data tag (TAGREF: 0x%X8).",
      v66);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)String2);
    v54 = (volatile signed __int64 *)String2;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v54 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v54,
      _InterlockedExchangeAdd64(v54 + 17, 0),
      v83);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v55);
    v56 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      LODWORD(v73) = -2138546173;
      v79 = (unsigned __int16 *)v83;
      v78 = (unsigned __int16 *)"Windows::Compat::Appraiser::SdbUtils::GetAppraiserDataTag";
      v81 = 0;
      v76 = "onecore\\base\\appcompat\\appraiser\\datasource\\sdbutils.cpp";
      LODWORD(v74) = 3219;
      v75 = (unsigned __int16 *)&szValueBuf;
      GetSystemTime(&v81);
      *(_QWORD *)&SystemTime.wYear = &v82;
      v82 = v81;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v56,
        (unsigned int)&unk_1802A70F7,
        v57,
        v58,
        (__int64)&SystemTime,
        (__int64)&v75,
        (__int64)&v74,
        (__int64)&v76,
        (__int64)&v78,
        (__int64)&v73,
        (__int64)&v79);
    }
  }
LABEL_121:
  v22 = 1;
LABEL_122:
  v59 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v59);
  }
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1801fa184  mov     [rsp-8+arg_8], rbx
0x1801fa189  push    rbp
0x1801fa18a  push    rsi
0x1801fa18b  push    rdi
0x1801fa18c  push    r12
0x1801fa18e  push    r13
0x1801fa190  push    r14
0x1801fa192  push    r15
0x1801fa194  lea     rbp, [rsp-280h]
0x1801fa19c  sub     rsp, 380h
0x1801fa1a3  mov     rax, cs:__security_cookie
0x1801fa1aa  xor     rax, rsp
0x1801fa1ad  mov     [rbp+2B0h+var_40], rax
0x1801fa1b4  mov     rax, [rbp+2B0h+arg_58]
0x1801fa1bb  xor     r13d, r13d
0x1801fa1be  mov     r12, [rbp+2B0h+arg_30]
0x1801fa1c5  mov     rbx, rcx
0x1801fa1c8  mov     r15, [rbp+2B0h+arg_48]
0x1801fa1cf  mov     edi, dword ptr [rbp+2B0h+arg_50]
0x1801fa1d5  mov     edx, edi; unsigned int
0x1801fa1d7  mov     [rsp+3B0h+var_338], rcx
0x1801fa1dc  mov     rcx, [rbp+2B0h+arg_20]
0x1801fa1e3  mov     [rbp+2B0h+var_320], rax
0x1801fa1e7  mov     rax, [rbp+2B0h+arg_38]
0x1801fa1ee  mov     [rsp+3B0h+var_348], r8
0x1801fa1f3  mov     [rbp+2B0h+var_318], rcx
0x1801fa1f7  mov     [rbp+2B0h+var_330], rax
0x1801fa1fb  mov     [rax], r13b
0x1801fa1fe  mov     [r12], r13b
0x1801fa202  mov     [rcx], r13w
0x1801fa206  mov     rcx, r15; void *
0x1801fa209  mov     [r8], r13w
0x1801fa20d  mov     r8d, 6001h; unsigned __int16
0x1801fa213  mov     [rsp+3B0h+var_350], r13b
0x1801fa218  mov     [rbx], r13w
0x1801fa21c  mov     [rbp+2B0h+lpMem], r13
0x1801fa220  call    SdbFindFirstTagRef
0x1801fa225  test    eax, eax
0x1801fa227  jnz     loc_1801FA391
0x1801fa22d  mov     dword ptr [rsp+3B0h+var_380], edi; char *
0x1801fa231  lea     rax, aEncounteredAMi_0; "Encountered a missing name on data tag "...
0x1801fa238  mov     qword ptr [rsp+3B0h+var_388], rax; int
0x1801fa23d  lea     edi, [r13+1]
0x1801fa241  lea     rsi, aWindowsCompatA_26; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fa248  mov     dword ptr [rsp+3B0h+var_390], 80886003h; char *
0x1801fa250  lea     r14, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fa257  mov     r15d, 0BDEh
0x1801fa25d  mov     ecx, edi; this
0x1801fa25f  mov     r9, rsi; char *
0x1801fa262  mov     r8, r14; unsigned int
0x1801fa265  mov     edx, r15d; bool
0x1801fa268  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fa26d  lea     rcx, [rbp+2B0h+String2]; this
0x1801fa271  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801fa276  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801fa27d  lea     rcx, [rbp+2B0h+String2]
0x1801fa281  test    rax, rax
0x1801fa284  mov     edx, r13d
0x1801fa287  cmovnz  rcx, rax; this
0x1801fa28b  lock xadd [rcx+88h], rdx; unsigned __int64
0x1801fa294  lea     r8, [rbp+2B0h+var_2E0]; char *
0x1801fa298  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801fa29d  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r13b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801fa2a4  jz      short loc_1801FA2B2
0x1801fa2a6  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801fa2ad  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801fa2b2  mov     rbx, cs:qword_1802C9628
0x1801fa2b9  mov     eax, [rbx]
0x1801fa2bb  cmp     eax, 5
0x1801fa2be  jbe     loc_1801FA38A
0x1801fa2c4  mov     rdx, [rbx+18h]
0x1801fa2c8  mov     rcx, 200000000000h
0x1801fa2d2  mov     rax, [rbx+10h]
0x1801fa2d6  test    rcx, rax
0x1801fa2d9  jz      loc_1801FA38A
0x1801fa2df  mov     rax, rdx
0x1801fa2e2  and     rax, rcx
0x1801fa2e5  cmp     rax, rdx
0x1801fa2e8  jnz     loc_1801FA38A
0x1801fa2ee  mov     dword ptr [rsp+3B0h+var_348], r15d
0x1801fa2f3  lea     rax, [rbp+2B0h+var_2E0]
0x1801fa2f7  xorps   xmm0, xmm0
0x1801fa2fa  mov     [rbp+2B0h+var_330], rax
0x1801fa2fe  lea     r15, szValueBuf
0x1801fa305  mov     dword ptr [rsp+3B0h+var_340], 80886003h
0x1801fa30d  lea     rcx, [rbp+2B0h+SystemTime]; lpSystemTime
0x1801fa311  mov     [rbp+2B0h+var_320], r15
0x1801fa315  mov     [rbp+2B0h+lpMem], rsi
0x1801fa319  mov     [rsp+3B0h+var_338], r14
0x1801fa31e  movups  xmmword ptr [rbp+2B0h+SystemTime.wYear], xmm0
0x1801fa322  call    cs:__imp_GetSystemTime
0x1801fa328  lea     rax, [rbp+2B0h+var_300]
0x1801fa32c  mov     [rbp+2B0h+var_318], rax
0x1801fa330  lea     rdx, unk_1802A72BA
0x1801fa337  lea     rax, [rbp+2B0h+var_330]
0x1801fa33b  mov     [rsp+3B0h+var_360], rax
0x1801fa340  lea     rax, [rsp+3B0h+var_340]
0x1801fa345  mov     [rsp+3B0h+var_368], rax
0x1801fa34a  lea     rax, [rbp+2B0h+lpMem]
0x1801fa34e  mov     [rsp+3B0h+var_370], rax
0x1801fa353  lea     rax, [rsp+3B0h+var_338]
0x1801fa358  mov     [rsp+3B0h+var_378], rax
0x1801fa35d  lea     rax, [rsp+3B0h+var_348]
0x1801fa362  mov     [rsp+3B0h+var_380], rax
0x1801fa367  lea     rax, [rbp+2B0h+var_320]
0x1801fa36b  mov     qword ptr [rsp+3B0h+var_388], rax
0x1801fa370  lea     rax, [rbp+2B0h+var_318]
0x1801fa374  movaps  xmm0, xmmword ptr [rbp+2B0h+SystemTime.wYear]
0x1801fa378  mov     rcx, rbx
0x1801fa37b  movdqa  xmmword ptr [rbp+2B0h+var_300.wYear], xmm0
0x1801fa380  mov     [rsp+3B0h+var_390], rax
0x1801fa385  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801fa38a  mov     ebx, edi
0x1801fa38c  jmp     loc_1801FAD68
0x1801fa391  mov     r9d, 104h
0x1801fa397  lea     r8, [rbp+2B0h+String2]
0x1801fa39b  mov     edx, eax
0x1801fa39d  mov     rcx, r15
0x1801fa3a0  call    SdbReadStringTagRef
0x1801fa3a5  test    eax, eax
0x1801fa3a7  jnz     short loc_1801FA3E4
0x1801fa3a9  lea     rax, aFailedToReadNa; "Failed to read name tag from sdb (paren"...
0x1801fa3b0  mov     dword ptr [rsp+3B0h+var_380], edi; char *
0x1801fa3b4  mov     qword ptr [rsp+3B0h+var_388], rax; int
0x1801fa3b9  lea     r9, aWindowsCompatA_26; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fa3c0  mov     ebx, 80886003h
0x1801fa3c5  lea     r8, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fa3cc  mov     edx, 0BE8h; bool
0x1801fa3d1  mov     ecx, 1; this
0x1801fa3d6  mov     dword ptr [rsp+3B0h+var_390], ebx; char *
0x1801fa3da  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fa3df  jmp     loc_1801FAD68
0x1801fa3e4  lea     rdx, [rbp+2B0h+String2]; String2
0x1801fa3e8  mov     [rsp+3B0h+var_340], r13
0x1801fa3ed  lea     rcx, aAppraiserdata; "AppraiserData"
0x1801fa3f4  call    wcscmp_0
0x1801fa3f9  lea     rsi, aWindowsCompatA_26; "Windows::Compat::Appraiser::SdbUtils::G"...
0x1801fa400  lea     r14, aOnecoreBaseApp_63; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801fa407  lea     rdi, aFailedToCopySt_1; "Failed to copy string [0x%x]."
0x1801fa40e  test    eax, eax
0x1801fa410  jnz     short loc_1801FA461
0x1801fa412  lea     r8, aSdbappraiserda; "SdbAppraiserData"
0x1801fa419  mov     edx, 104h; unsigned __int64
0x1801fa41e  mov     rcx, rbx; unsigned __int16 *
0x1801fa421  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801fa426  mov     ebx, eax
0x1801fa428  test    eax, eax
0x1801fa42a  jns     short loc_1801FA442
0x1801fa42c  mov     dword ptr [rsp+3B0h+var_380], eax
0x1801fa430  mov     r9, rsi
0x1801fa433  mov     qword ptr [rsp+3B0h+var_388], rdi
0x1801fa438  mov     r8, r14
0x1801fa43b  mov     edx, 0BF2h
0x1801fa440  jmp     short loc_1801FA3D1
0x1801fa442  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fa448  mov     edi, 1
0x1801fa44d  and     eax, edi
0x1801fa44f  test    al, al
0x1801fa451  jz      loc_1801FA5F4
0x1801fa457  mov     ecx, 0BF2h
0x1801fa45c  jmp     loc_1801FA5DE
0x1801fa461  mov     r13d, 15h
0x1801fa467  lea     rdx, [rbp+2B0h+String2]; String2
0x1801fa46b  mov     r8d, r13d; MaxCount
0x1801fa46e  lea     rcx, aAppraiserresou; "AppraiserResourceData"
0x1801fa475  call    wcsncmp_0
0x1801fa47a  lea     edi, [r13-14h]
0x1801fa47e  test    eax, eax
0x1801fa480  jz      short loc_1801FA4A4
0x1801fa482  lea     r13d, [rdi+1Ah]
0x1801fa486  mov     r8d, r13d; MaxCount
0x1801fa489  lea     rdx, [rbp+2B0h+String2]; String2
0x1801fa48d  lea     rcx, aAppraiserresou_0; "AppraiserResourceBackupData"
0x1801fa494  call    wcsncmp_0
0x1801fa499  test    eax, eax
0x1801fa49b  jnz     short loc_1801FA4BD
0x1801fa49d  mov     rax, [rbp+2B0h+var_330]
0x1801fa4a1  mov     [rax], dil
0x1801fa4a4  lea     rax, aSdbappraiserre_0; "SdbAppraiserResourceDataRedirectionInst"...
0x1801fa4ab  mov     [r12], dil
0x1801fa4af  mov     [rsp+3B0h+var_340], rax
0x1801fa4b4  lea     r8, aSdbappraiserre_3; "SdbAppraiserResourceData"
0x1801fa4bb  jmp     short loc_1801FA4E5
0x1801fa4bd  mov     r13d, 0Dh
0x1801fa4c3  lea     rdx, [rbp+2B0h+String2]; String2
0x1801fa4c7  mov     r8d, r13d; MaxCount
0x1801fa4ca  lea     rcx, aAppraiserdata; "AppraiserData"
0x1801fa4d1  call    wcsncmp_0
0x1801fa4d6  test    eax, eax
0x1801fa4d8  jnz     loc_1801FAD49
0x1801fa4de  lea     r8, aSdbappraiserda; "SdbAppraiserData"
0x1801fa4e5  mov     edx, 104h; unsigned __int64
0x1801fa4ea  mov     rcx, rbx; unsigned __int16 *
0x1801fa4ed  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801fa4f2  mov     ebx, eax
0x1801fa4f4  test    eax, eax
0x1801fa4f6  jns     short loc_1801FA51A
0x1801fa4f8  lea     r9, aFailedToCopySt_1; "Failed to copy string [0x%x]."
0x1801fa4ff  mov     edx, 0C14h
0x1801fa504  mov     dword ptr [rsp+3B0h+var_380], ebx
0x1801fa508  mov     qword ptr [rsp+3B0h+var_388], r9
0x1801fa50d  mov     r9, rsi
0x1801fa510  mov     r8, r14
0x1801fa513  mov     ecx, edi
0x1801fa515  jmp     loc_1801FA3D6
0x1801fa51a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fa520  and     eax, edi
0x1801fa522  test    al, al
0x1801fa524  jz      short loc_1801FA541
0x1801fa526  lea     r9, aFailedToCopySt_1; "Failed to copy string [0x%x]."
0x1801fa52d  mov     dword ptr [rsp+3B0h+var_390], ebx
0x1801fa531  mov     r8, rsi; char *
0x1801fa534  mov     rdx, r14; char *
0x1801fa537  mov     ecx, 0C14h; unsigned int
0x1801fa53c  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fa541  mov     rcx, [rsp+3B0h+var_338]; unsigned __int16 *
0x1801fa546  lea     r8, [rbp+2B0h+String2]
0x1801fa54a  lea     r8, [r8+r13*2]; unsigned __int16 *
0x1801fa54e  mov     edx, 104h; unsigned __int64
0x1801fa553  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801fa558  mov     ebx, eax
0x1801fa55a  test    eax, eax
0x1801fa55c  jns     short loc_1801FA56C
0x1801fa55e  lea     r9, aFailedToExtrac_3; "Failed to extract property name [0x%x]."
0x1801fa565  mov     edx, 0C17h
0x1801fa56a  jmp     short loc_1801FA504
0x1801fa56c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fa572  and     eax, edi
0x1801fa574  test    al, al
0x1801fa576  jz      short loc_1801FA593
0x1801fa578  lea     r9, aFailedToExtrac_3; "Failed to extract property name [0x%x]."
0x1801fa57f  mov     dword ptr [rsp+3B0h+var_390], ebx
0x1801fa583  mov     r8, rsi; char *
0x1801fa586  mov     rdx, r14; char *
0x1801fa589  mov     ecx, 0C17h; unsigned int
0x1801fa58e  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fa593  cmp     byte ptr [r12], 0
0x1801fa598  jz      short loc_1801FA5F4
0x1801fa59a  mov     r8, [rsp+3B0h+var_338]; unsigned __int16 *
0x1801fa59f  mov     edx, 104h; unsigned __int64
0x1801fa5a4  mov     rcx, [rbp+2B0h+var_318]; unsigned __int16 *
0x1801fa5a8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1801fa5ad  mov     ebx, eax
0x1801fa5af  test    eax, eax
0x1801fa5b1  jns     short loc_1801FA5CD
0x1801fa5b3  mov     dword ptr [rsp+3B0h+var_380], eax
0x1801fa5b7  mov     edx, 0C1Ch
0x1801fa5bc  lea     rax, aFailedToCopySt_1; "Failed to copy string [0x%x]."
0x1801fa5c3  mov     qword ptr [rsp+3B0h+var_388], rax
0x1801fa5c8  jmp     loc_1801FA50D
0x1801fa5cd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801fa5d3  and     eax, edi
0x1801fa5d5  test    al, al
0x1801fa5d7  jz      short loc_1801FA5F4
0x1801fa5d9  mov     ecx, 0C1Ch; unsigned int
0x1801fa5de  lea     r9, aFailedToCopySt_1; "Failed to copy string [0x%x]."
0x1801fa5e5  mov     dword ptr [rsp+3B0h+var_390], ebx
0x1801fa5e9  mov     r8, rsi; char *
0x1801fa5ec  mov     rdx, r14; char *
0x1801fa5ef  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801fa5f4  cmp     [rbp+2B0h+arg_40], 0
0x1801fa5fb  jnz     short loc_1801FA60B
0x1801fa5fd  cmp     byte ptr [r12], 0
0x1801fa602  jnz     short loc_1801FA60B
0x1801fa604  xor     ebx, ebx
0x1801fa606  jmp     loc_1801FAD68
0x1801fa60b  mov     ebx, dword ptr [rbp+2B0h+arg_50]
0x1801fa611  mov     r8d, 4018h; unsigned __int16
0x1801fa617  mov     edx, ebx; unsigned int
0x1801fa619  mov     rcx, r15; void *
0x1801fa61c  call    SdbFindFirstTagRef
0x1801fa621  test    eax, eax
0x1801fa623  jnz     loc_1801FA762
0x1801fa629  lea     rax, aEncounteredAMi_2; "Encountered a missing value type on dat"...
0x1801fa630  mov     dword ptr [rsp+3B0h+var_380], ebx; char *
0x1801fa634  mov     qword ptr [rsp+3B0h+var_388], rax; int
0x1801fa639  mov     r15d, 0C31h
0x1801fa63f  mov     edx, r15d; bool
0x1801fa642  mov     dword ptr [rsp+3B0h+var_390], 80886003h; char *
0x1801fa64a  mov     r9, rsi; char *
0x1801fa64d  mov     r8, r14; unsigned int
0x1801fa650  mov     ecx, edi; this
0x1801fa652  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801fa657  lea     rcx, [rbp+2B0h+String2]; this
0x1801fa65b  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801fa660  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801fa667  lea     rcx, [rbp+2B0h+String2]
0x1801fa66b  test    rax, rax
0x1801fa66e  cmovnz  rcx, rax; this
0x1801fa672  xor     edx, edx
0x1801fa674  lock xadd [rcx+88h], rdx; unsigned __int64
0x1801fa67d  lea     r8, [rbp+2B0h+var_2E0]; char *
0x1801fa681  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801fa686  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801fa68d  jz      short loc_1801FA69B
0x1801fa68f  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801fa696  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801fa69b  mov     rbx, cs:qword_1802C9628
0x1801fa6a2  mov     eax, [rbx]
0x1801fa6a4  cmp     eax, 5
  ... truncated ...
```
