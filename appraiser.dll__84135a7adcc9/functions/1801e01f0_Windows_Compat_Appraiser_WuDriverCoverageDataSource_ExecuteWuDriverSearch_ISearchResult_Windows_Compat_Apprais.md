# Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch(ISearchResult * *,Windows::Compat::Appraiser::WuSessionInfo *,ushort const *)

- ea: `0x1801e01f0`
- end: `0x1801e0c6a`
- name: `?ExecuteWuDriverSearch@WuDriverCoverageDataSource@Appraiser@Compat@Windows@@AEAAJPEAPEAUISearchResult@@PEAUWuSessionInfo@234@PEBG@Z`
- size: `2682`
- prototype: `int(Windows::Compat::Appraiser::WuDriverCoverageDataSource *__hidden this, struct ISearchResult **, struct Windows::Compat::Appraiser::WuSessionInfo *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1801e3880`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x1800a5d88`
- `0x1801ab2f0`
- `0x1801e01f0`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1801e03fb`
- `KERNEL32!GetSystemTime` at `0x1801e0631`
- `KERNEL32!GetSystemTime` at `0x1801e0821`
- `KERNEL32!GetSystemTime` at `0x1801e09d3`
- `KERNEL32!GetSystemTime` at `0x1801e0b7c`
- `KERNEL32!GetSystemTime` at `0x1801e03fb`
- `KERNEL32!GetSystemTime` at `0x1801e0631`
- `KERNEL32!GetSystemTime` at `0x1801e0821`
- `KERNEL32!GetSystemTime` at `0x1801e09d3`
- `KERNEL32!GetSystemTime` at `0x1801e0b7c`
- `KERNEL32!CreateEventW` at `0x1801e0249`
- `KERNEL32!CreateEventW` at `0x1801e0249`
- `KERNEL32!CloseHandle` at `0x1801e0c3f`
- `KERNEL32!CloseHandle` at `0x1801e0c3f`
- `KERNEL32!GetLastError` at `0x1801e026c`
- `KERNEL32!GetLastError` at `0x1801e028b`
- `KERNEL32!GetLastError` at `0x1801e050b`
- `KERNEL32!GetLastError` at `0x1801e026c`
- `KERNEL32!GetLastError` at `0x1801e028b`
- `KERNEL32!GetLastError` at `0x1801e050b`
- `KERNEL32!WaitForSingleObject` at `0x1801e04fa`
- `KERNEL32!WaitForSingleObject` at `0x1801e04fa`
- `OLEAUT32!__imp_SysAllocString` at `0x1801e02c6`
- `OLEAUT32!__imp_SysAllocString` at `0x1801e02c6`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e0c32`
- `OLEAUT32!__imp_SysFreeString` at `0x1801e0c32`
- `OLEAUT32!__imp_VariantInit` at `0x1801e02e2`
- `OLEAUT32!__imp_VariantInit` at `0x1801e02e2`

## string_xrefs

- `0x1801e02a6`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e03ca`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e0480`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e04d6`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e0600`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e06b7`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e06ea`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e074b`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e07f3`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e08ae`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e08ba`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e0a9f`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e0c09`: `onecore\base\appcompat\appraiser\datasource\wudrivercoverage.cpp`
- `0x1801e025a`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e03d1`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0479`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e04c7`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e04e4`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0607`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e06b0`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e073d`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e08a2`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e08ea`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e09ac`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0a59`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0aa6`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0b59`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`
- `0x1801e0bfd`: `Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch(
        Windows::Compat::Appraiser::WuDriverCoverageDataSource *this,
        struct ISearchResult **a2,
        struct Windows::Compat::Appraiser::WuSessionInfo *a3,
        const unsigned __int16 *a4)
{
  char v8; // r14
  HANDLE EventW; // rax
  OLECHAR *v10; // r15
  signed int LastError; // eax
  signed int v12; // ebx
  char v13; // dl
  const char *v14; // rax
  __int64 *v15; // rcx
  __int64 v16; // rdx
  int v17; // esi
  volatile signed __int64 *v18; // rcx
  void **v19; // rdx
  int v20; // edi
  int v21; // r8d
  int v22; // r9d
  bool v23; // al
  char v24; // dl
  __int64 v25; // rcx
  DWORD v26; // eax
  int v27; // edi
  volatile signed __int64 *v28; // rcx
  void **v29; // rdx
  int v30; // esi
  int v31; // r8d
  int v32; // r9d
  bool v33; // al
  __int64 v34; // rcx
  int v35; // eax
  int v36; // esi
  volatile signed __int64 *v37; // rcx
  void **v38; // rdx
  int v39; // edi
  int v40; // r8d
  int v41; // r9d
  int v42; // eax
  int v43; // esi
  volatile signed __int64 *v44; // rcx
  void **v45; // rdx
  int v46; // edi
  int v47; // r8d
  int v48; // r9d
  int v49; // eax
  int v50; // esi
  volatile signed __int64 *v51; // rcx
  void **v52; // rdx
  int v53; // edi
  int v54; // r8d
  int v55; // r9d
  char *v57; // [rsp+20h] [rbp-E0h]
  const char *v58; // [rsp+28h] [rbp-D8h]
  char *v59; // [rsp+30h] [rbp-D0h]
  int v60; // [rsp+60h] [rbp-A0h] BYREF
  int v61; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v62; // [rsp+68h] [rbp-98h] BYREF
  char *v63; // [rsp+70h] [rbp-90h] BYREF
  const char *v64; // [rsp+78h] [rbp-88h] BYREF
  const char *v65; // [rsp+80h] [rbp-80h] BYREF
  const char *v66; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v67[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+A0h] [rbp-60h] BYREF
  HANDLE *v69; // [rsp+B0h] [rbp-50h]
  VARIANTARG pvarg; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG v71; // [rsp+D0h] [rbp-30h] BYREF
  char v72[144]; // [rsp+F0h] [rbp-10h] BYREF
  char v73[144]; // [rsp+180h] [rbp+80h] BYREF

  v62 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v8 = 0;
  EventW = CreateEventW(0, 1, 0, 0);
  v69 = (HANDLE *)((char *)this + 192);
  *((_QWORD *)this + 24) = EventW;
  if ( !EventW )
  {
    v10 = 0;
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    if ( v12 >= 0 )
      v12 = -2147467259;
    LODWORD(v59) = GetLastError();
    v13 = -67;
    v14 = "Error creating event: [%d].";
LABEL_7:
    LODWORD(v57) = v12;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v13,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
      v57,
      (int)v14,
      v59);
    goto LABEL_48;
  }
  v10 = SysAllocString(a4);
  if ( !v10 )
  {
    v12 = -2147024882;
    goto LABEL_48;
  }
  VariantInit(&pvarg);
  v15 = (__int64 *)*((_QWORD *)a3 + 2);
  v16 = *v15;
  v71 = pvarg;
  v17 = (*(__int64 (__fastcall **)(__int64 *, OLECHAR *, unsigned __int64, VARIANTARG *, __int64 *))(v16 + 120))(
          v15,
          v10,
          ((unsigned __int64)this + 16) & -(__int64)(this != 0),
          &v71,
          &v62);
  if ( v17 < 0 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v72);
    v18 = (volatile signed __int64 *)v72;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v18 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v18,
      _InterlockedExchangeAdd64(v18 + 17, 0),
      v73);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v19);
    v20 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v60 = v17;
      v63 = v73;
      v65 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v64 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch";
      v61 = 1225;
      v66 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v67[0] = &v71;
      *(struct _SYSTEMTIME *)&v71.vt = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v20,
        (unsigned int)&unk_1802A5769,
        v21,
        v22,
        (__int64)v67,
        (__int64)&v66,
        (__int64)&v61,
        (__int64)&v65,
        (__int64)&v64,
        (__int64)&v60,
        (__int64)&v63);
    }
    v23 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    LODWORD(v59) = v17;
    v58 = "Error beginning search: [0x%x].";
    v24 = -55;
    if ( v23 )
    {
      LODWORD(v57) = v17;
LABEL_21:
      v25 = 1;
LABEL_23:
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)v25,
        v24,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
        v57,
        (int)v58,
        v59);
      v12 = -2138537983;
      goto LABEL_48;
    }
    goto LABEL_22;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4C9u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
      "Error beginning search: [0x%x].",
      v17);
  v8 = 1;
  v26 = WaitForSingleObject(*v69, 0x493E0u);
  v12 = v26;
  if ( v26 )
  {
    if ( v26 == -1 )
      v12 = GetLastError();
    MicrosoftTelemetryAssertTriggeredNoArgs();
    if ( v12 > 0 )
      v12 = (unsigned __int16)v12 | 0x80070000;
    v13 = -43;
    if ( v12 >= 0 )
      v12 = -2147467259;
    v14 = "Error waiting on WU Scan: [0x%x].";
    LODWORD(v59) = v12;
    goto LABEL_7;
  }
  v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct ISearchResult **))(**((_QWORD **)a3 + 2) + 128LL))(
          *((_QWORD *)a3 + 2),
          v62,
          a2);
  if ( v27 < 0 )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v72);
    v28 = (volatile signed __int64 *)v72;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v28 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v28,
      _InterlockedExchangeAdd64(v28 + 17, 0),
      v73);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v29);
    v30 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v61 = v27;
      v67[0] = v73;
      v65 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v66 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch";
      v60 = 1241;
      v64 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v63 = (char *)&v71;
      *(struct _SYSTEMTIME *)&v71.vt = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v30,
        (unsigned int)&unk_1802A57CC,
        v31,
        v32,
        (__int64)&v63,
        (__int64)&v64,
        (__int64)&v60,
        (__int64)&v65,
        (__int64)&v66,
        (__int64)&v61,
        (__int64)v67);
    }
    v33 = Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors();
    LODWORD(v59) = v27;
    v58 = "Error ending search: [0x%x].";
    v24 = -39;
    if ( v33 )
    {
      LODWORD(v57) = v27;
      goto LABEL_21;
    }
LABEL_22:
    v57 = 0;
    v25 = 0;
    goto LABEL_23;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4D9u,
      "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
      "Error ending search: [0x%x].",
      v27);
  v8 = 0;
  v12 = 0;
LABEL_48:
  v34 = v62;
  if ( !v62 )
    goto LABEL_85;
  if ( v8 )
  {
    v35 = (*(__int64 (**)(void))(*(_QWORD *)v62 + 80LL))();
    v36 = v35;
    if ( v35 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4E5u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
          "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
          "Error aborting WU search job, swallowing: [0x%x].",
          v35);
    }
    else
    {
      LODWORD(v59) = v35;
      LODWORD(v57) = v35;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        229,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
        v57,
        (int)"Error aborting WU search job, swallowing: [0x%x].",
        v59);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v72);
      v37 = (volatile signed __int64 *)v72;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v37 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v37,
        _InterlockedExchangeAdd64(v37 + 17, 0),
        v73);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v38);
      v39 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v66 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch";
        v67[0] = v73;
        v61 = v36;
        v64 = (const char *)&szValueBuf;
        v65 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
        v60 = 1253;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v63 = (char *)&v71;
        *(struct _SYSTEMTIME *)&v71.vt = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v39,
          (unsigned int)&unk_1802A58F5,
          v40,
          v41,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v60,
          (__int64)&v65,
          (__int64)&v66,
          (__int64)&v61,
          (__int64)v67);
      }
    }
    v42 = (*(__int64 (__fastcall **)(_QWORD, __int64, struct ISearchResult **))(**((_QWORD **)a3 + 2) + 128LL))(
            *((_QWORD *)a3 + 2),
            v62,
            a2);
    v43 = v42;
    if ( v42 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4E8u,
          "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
          "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
          "Error ending search: [0x%x].",
          v42);
    }
    else
    {
      LODWORD(v59) = v42;
      LODWORD(v57) = v42;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        232,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
        v57,
        (int)"Error ending search: [0x%x].",
        v59);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v72);
      v44 = (volatile signed __int64 *)v72;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v44 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v44,
        _InterlockedExchangeAdd64(v44 + 17, 0),
        v73);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v45);
      v46 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v61 = v43;
        v67[0] = v73;
        v65 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
        v66 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch";
        v60 = 1256;
        v64 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v63 = (char *)&v71;
        *(struct _SYSTEMTIME *)&v71.vt = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v46,
          (unsigned int)&unk_1802A582F,
          v47,
          v48,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v60,
          (__int64)&v65,
          (__int64)&v66,
          (__int64)&v61,
          (__int64)v67);
        v34 = v62;
        goto LABEL_73;
      }
    }
    v34 = v62;
  }
LABEL_73:
  v49 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v34 + 72LL))(v34);
  v50 = v49;
  if ( v49 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4ECu,
        "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
        "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
        "Error cleaning up WU search job, swallowing: [0x%x].",
        v49);
  }
  else
  {
    LODWORD(v59) = v49;
    LODWORD(v57) = v49;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      236,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp",
      "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch",
      v57,
      (int)"Error cleaning up WU search job, swallowing: [0x%x].",
      v59);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v72);
    v51 = (volatile signed __int64 *)v72;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v51 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v51,
      _InterlockedExchangeAdd64(v51 + 17, 0),
      v73);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v52);
    v53 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      v61 = v50;
      v67[0] = v73;
      v65 = "onecore\\base\\appcompat\\appraiser\\datasource\\wudrivercoverage.cpp";
      v66 = "Windows::Compat::Appraiser::WuDriverCoverageDataSource::ExecuteWuDriverSearch";
      v60 = 1260;
      v64 = (const char *)&szValueBuf;
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      v63 = (char *)&v71;
      *(struct _SYSTEMTIME *)&v71.vt = SystemTime;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v53,
        (unsigned int)&unk_1802A5892,
        v54,
        v55,
        (__int64)&v63,
        (__int64)&v64,
        (__int64)&v60,
        (__int64)&v65,
        (__int64)&v66,
        (__int64)&v61,
        (__int64)v67);
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v62 + 16LL))(v62);
  v62 = 0;
LABEL_85:
  SysFreeString(v10);
  CloseHandle(*v69);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1801e01f0  push    rbp
0x1801e01f2  push    rbx
0x1801e01f3  push    rsi
0x1801e01f4  push    rdi
0x1801e01f5  push    r12
0x1801e01f7  push    r13
0x1801e01f9  push    r14
0x1801e01fb  push    r15
0x1801e01fd  lea     rbp, [rsp-128h]
0x1801e0205  sub     rsp, 228h
0x1801e020c  mov     rax, cs:__security_cookie
0x1801e0213  xor     rax, rsp
0x1801e0216  mov     [rbp+160h+var_50], rax
0x1801e021d  xor     eax, eax
0x1801e021f  mov     rbx, r9
0x1801e0222  mov     r13, r8
0x1801e0225  mov     qword ptr [rbp+160h+pvarg+10h], rax
0x1801e0229  mov     r12, rdx
0x1801e022c  mov     [rsp+260h+var_1F8], rax
0x1801e0231  mov     rdi, rcx
0x1801e0234  xorps   xmm0, xmm0
0x1801e0237  lea     edx, [rax+1]; bManualReset
0x1801e023a  xor     r9d, r9d; lpName
0x1801e023d  xor     r8d, r8d; bInitialState
0x1801e0240  xor     ecx, ecx; lpEventAttributes
0x1801e0242  movups  xmmword ptr [rbp+160h+pvarg], xmm0
0x1801e0246  xor     r14b, r14b
0x1801e0249  call    cs:__imp_CreateEventW
0x1801e024f  lea     rcx, [rdi+0C0h]
0x1801e0256  mov     [rbp+160h+var_1B0], rcx
0x1801e025a  lea     rsi, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e0261  mov     [rcx], rax
0x1801e0264  test    rax, rax
0x1801e0267  jnz     short loc_1801E02C3
0x1801e0269  xor     r15d, r15d
0x1801e026c  call    cs:__imp_GetLastError
0x1801e0272  mov     ebx, eax
0x1801e0274  test    eax, eax
0x1801e0276  jle     short loc_1801E0281
0x1801e0278  movzx   ebx, ax
0x1801e027b  or      ebx, 80070000h
0x1801e0281  test    ebx, ebx
0x1801e0283  mov     eax, 80004005h
0x1801e0288  cmovns  ebx, eax
0x1801e028b  call    cs:__imp_GetLastError
0x1801e0291  mov     dword ptr [rsp+260h+var_230], eax; char *
0x1801e0295  mov     edx, 4BDh; bool
0x1801e029a  lea     rax, aErrorCreatingE_1; "Error creating event: [%d]."
0x1801e02a1  mov     qword ptr [rsp+260h+var_238], rax; int
0x1801e02a6  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e02ad  mov     r9, rsi; char *
0x1801e02b0  mov     dword ptr [rsp+260h+var_240], ebx; char *
0x1801e02b4  mov     ecx, 1; this
0x1801e02b9  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e02be  jmp     loc_1801E0700
0x1801e02c3  mov     rcx, rbx; psz
0x1801e02c6  call    cs:__imp_SysAllocString
0x1801e02cc  mov     r15, rax
0x1801e02cf  test    rax, rax
0x1801e02d2  jnz     short loc_1801E02DE
0x1801e02d4  mov     ebx, 8007000Eh
0x1801e02d9  jmp     loc_1801E0700
0x1801e02de  lea     rcx, [rbp+160h+pvarg]; pvarg
0x1801e02e2  call    cs:__imp_VariantInit
0x1801e02e8  mov     rcx, [r13+10h]
0x1801e02ec  lea     rax, [rdi+10h]
0x1801e02f0  movups  xmm0, xmmword ptr [rbp+160h+pvarg]
0x1801e02f4  lea     r9, [rbp+160h+var_190]
0x1801e02f8  neg     rdi
0x1801e02fb  movsd   xmm1, qword ptr [rbp+160h+pvarg+10h]
0x1801e0300  mov     rdx, [rcx]
0x1801e0303  sbb     r8, r8
0x1801e0306  and     r8, rax
0x1801e0309  movaps  [rbp+160h+var_190], xmm0
0x1801e030d  movsd   [rbp+160h+var_180], xmm1
0x1801e0312  mov     rax, [rdx+78h]
0x1801e0316  lea     rdx, [rsp+260h+var_1F8]
0x1801e031b  mov     [rsp+260h+var_240], rdx
0x1801e0320  mov     rdx, r15
0x1801e0323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e0328  mov     esi, eax
0x1801e032a  test    eax, eax
0x1801e032c  jns     loc_1801E04B2
0x1801e0332  lea     rcx, [rbp+160h+var_170]; this
0x1801e0336  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e033b  mov     rdx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e0342  lea     rcx, [rbp+160h+var_170]
0x1801e0346  test    rdx, rdx
0x1801e0349  cmovnz  rcx, rdx; this
0x1801e034d  xor     edx, edx
0x1801e034f  lock xadd [rcx+88h], rdx; unsigned __int64
0x1801e0358  lea     r8, [rbp+160h+var_E0]; char *
0x1801e035f  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e0364  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r14b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e036b  jz      short loc_1801E0379
0x1801e036d  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e0374  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e0379  mov     rdi, cs:qword_1802C9628
0x1801e0380  mov     ebx, 4C9h
0x1801e0385  mov     eax, [rdi]
0x1801e0387  cmp     eax, 5
0x1801e038a  jbe     loc_1801E0464
0x1801e0390  mov     rcx, [rdi+18h]
0x1801e0394  mov     rdx, 200000000000h
0x1801e039e  mov     rax, [rdi+10h]
0x1801e03a2  test    rdx, rax
0x1801e03a5  jz      loc_1801E0464
0x1801e03ab  mov     rax, rcx
0x1801e03ae  and     rax, rdx
0x1801e03b1  cmp     rax, rcx
0x1801e03b4  jnz     loc_1801E0464
0x1801e03ba  lea     rax, [rbp+160h+var_E0]
0x1801e03c1  mov     [rsp+260h+var_200], esi
0x1801e03c5  mov     [rsp+260h+var_1F0], rax
0x1801e03ca  lea     rdx, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e03d1  lea     rax, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e03d8  mov     [rbp+160h+var_1E0], rdx
0x1801e03dc  mov     [rsp+260h+var_1E8], rax
0x1801e03e1  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x1801e03e5  lea     rax, szValueBuf
0x1801e03ec  mov     [rsp+260h+var_1FC], ebx
0x1801e03f0  xorps   xmm0, xmm0
0x1801e03f3  mov     [rbp+160h+var_1D8], rax
0x1801e03f7  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x1801e03fb  call    cs:__imp_GetSystemTime
0x1801e0401  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x1801e0405  lea     rax, [rbp+160h+var_190]
0x1801e0409  mov     [rbp+160h+var_1D0], rax
0x1801e040d  lea     rdx, unk_1802A5769
0x1801e0414  lea     rax, [rsp+260h+var_1F0]
0x1801e0419  movdqa  [rbp+160h+var_190], xmm0
0x1801e041e  mov     [rsp+260h+var_210], rax
0x1801e0423  mov     rcx, rdi
0x1801e0426  lea     rax, [rsp+260h+var_200]
0x1801e042b  mov     [rsp+260h+var_218], rax
0x1801e0430  lea     rax, [rsp+260h+var_1E8]
0x1801e0435  mov     [rsp+260h+var_220], rax
0x1801e043a  lea     rax, [rbp+160h+var_1E0]
0x1801e043e  mov     [rsp+260h+var_228], rax
0x1801e0443  lea     rax, [rsp+260h+var_1FC]
0x1801e0448  mov     [rsp+260h+var_230], rax
0x1801e044d  lea     rax, [rbp+160h+var_1D8]
0x1801e0451  mov     qword ptr [rsp+260h+var_238], rax
0x1801e0456  lea     rax, [rbp+160h+var_1D0]
0x1801e045a  mov     [rsp+260h+var_240], rax
0x1801e045f  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e0464  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e0469  mov     dword ptr [rsp+260h+var_230], esi; char *
0x1801e046d  lea     r9, aErrorBeginning; "Error beginning search: [0x%x]."
0x1801e0474  mov     qword ptr [rsp+260h+var_238], r9; int
0x1801e0479  lea     r9, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e0480  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e0487  mov     edx, ebx; bool
0x1801e0489  test    al, al
0x1801e048b  jz      short loc_1801E0498
0x1801e048d  mov     dword ptr [rsp+260h+var_240], esi
0x1801e0491  mov     ecx, 1
0x1801e0496  jmp     short loc_1801E04A3
0x1801e0498  mov     [rsp+260h+var_240], 0; char *
0x1801e04a1  xor     ecx, ecx; this
0x1801e04a3  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1801e04a8  mov     ebx, 80888001h
0x1801e04ad  jmp     loc_1801E0700
0x1801e04b2  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e04b8  test    al, 1
0x1801e04ba  jz      short loc_1801E04E4
0x1801e04bc  mov     dword ptr [rsp+260h+var_240], esi
0x1801e04c0  lea     r9, aErrorBeginning; "Error beginning search: [0x%x]."
0x1801e04c7  lea     rsi, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e04ce  mov     ecx, 4C9h; unsigned int
0x1801e04d3  mov     r8, rsi; char *
0x1801e04d6  lea     rdx, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e04dd  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e04e2  jmp     short loc_1801E04EB
0x1801e04e4  lea     rsi, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e04eb  mov     rcx, [rbp+160h+var_1B0]
0x1801e04ef  mov     edx, 493E0h; dwMilliseconds
0x1801e04f4  mov     r14b, 1
0x1801e04f7  mov     rcx, [rcx]; hHandle
0x1801e04fa  call    cs:__imp_WaitForSingleObject
0x1801e0500  mov     ebx, eax
0x1801e0502  test    eax, eax
0x1801e0504  jz      short loc_1801E0544
0x1801e0506  cmp     eax, 0FFFFFFFFh
0x1801e0509  jnz     short loc_1801E0513
0x1801e050b  call    cs:__imp_GetLastError
0x1801e0511  mov     ebx, eax
0x1801e0513  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1801e0518  test    ebx, ebx
0x1801e051a  jle     short loc_1801E0525
0x1801e051c  movzx   ebx, bx
0x1801e051f  or      ebx, 80070000h
0x1801e0525  mov     eax, 80004005h
0x1801e052a  test    ebx, ebx
0x1801e052c  mov     edx, 4D5h
0x1801e0531  cmovns  ebx, eax
0x1801e0534  lea     rax, aErrorWaitingOn; "Error waiting on WU Scan: [0x%x]."
0x1801e053b  mov     dword ptr [rsp+260h+var_230], ebx
0x1801e053f  jmp     loc_1801E02A1
0x1801e0544  mov     rcx, [r13+10h]
0x1801e0548  mov     r8, r12
0x1801e054b  mov     rdx, [rsp+260h+var_1F8]
0x1801e0550  mov     rax, [rcx]
0x1801e0553  mov     rax, [rax+80h]
0x1801e055a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801e055f  mov     edi, eax
0x1801e0561  test    eax, eax
0x1801e0563  jns     loc_1801E06D1
0x1801e0569  lea     rcx, [rbp+160h+var_170]; this
0x1801e056d  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1801e0572  mov     rdx, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1801e0579  lea     rcx, [rbp+160h+var_170]
0x1801e057d  test    rdx, rdx
0x1801e0580  cmovnz  rcx, rdx; this
0x1801e0584  xor     edx, edx
0x1801e0586  lock xadd [rcx+88h], rdx; unsigned __int64
0x1801e058f  lea     r8, [rbp+160h+var_E0]; char *
0x1801e0596  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1801e059b  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1801e05a2  jz      short loc_1801E05B0
0x1801e05a4  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1801e05ab  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1801e05b0  mov     rsi, cs:qword_1802C9628
0x1801e05b7  mov     ebx, 4D9h
0x1801e05bc  mov     eax, [rsi]
0x1801e05be  cmp     eax, 5
0x1801e05c1  jbe     loc_1801E069B
0x1801e05c7  mov     rcx, [rsi+18h]
0x1801e05cb  mov     rdx, 200000000000h
0x1801e05d5  mov     rax, [rsi+10h]
0x1801e05d9  test    rdx, rax
0x1801e05dc  jz      loc_1801E069B
0x1801e05e2  mov     rax, rcx
0x1801e05e5  and     rax, rdx
0x1801e05e8  cmp     rax, rcx
0x1801e05eb  jnz     loc_1801E069B
0x1801e05f1  lea     rax, [rbp+160h+var_E0]
0x1801e05f8  mov     [rsp+260h+var_1FC], edi
0x1801e05fc  mov     [rbp+160h+var_1D0], rax
0x1801e0600  lea     rdx, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e0607  lea     rax, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e060e  mov     [rbp+160h+var_1E0], rdx
0x1801e0612  mov     [rbp+160h+var_1D8], rax
0x1801e0616  lea     rcx, [rbp+160h+SystemTime]; lpSystemTime
0x1801e061a  lea     rax, szValueBuf
0x1801e0621  mov     [rsp+260h+var_200], ebx
0x1801e0625  xorps   xmm0, xmm0
0x1801e0628  mov     [rsp+260h+var_1E8], rax
0x1801e062d  movups  xmmword ptr [rbp+160h+SystemTime.wYear], xmm0
0x1801e0631  call    cs:__imp_GetSystemTime
0x1801e0637  movaps  xmm0, xmmword ptr [rbp+160h+SystemTime.wYear]
0x1801e063b  lea     rax, [rbp+160h+var_190]
0x1801e063f  mov     [rsp+260h+var_1F0], rax
0x1801e0644  lea     rdx, unk_1802A57CC
0x1801e064b  lea     rax, [rbp+160h+var_1D0]
0x1801e064f  movdqa  [rbp+160h+var_190], xmm0
0x1801e0654  mov     [rsp+260h+var_210], rax
0x1801e0659  mov     rcx, rsi
0x1801e065c  lea     rax, [rsp+260h+var_1FC]
0x1801e0661  mov     [rsp+260h+var_218], rax
0x1801e0666  lea     rax, [rbp+160h+var_1D8]
0x1801e066a  mov     [rsp+260h+var_220], rax
0x1801e066f  lea     rax, [rbp+160h+var_1E0]
0x1801e0673  mov     [rsp+260h+var_228], rax
0x1801e0678  lea     rax, [rsp+260h+var_200]
0x1801e067d  mov     [rsp+260h+var_230], rax
0x1801e0682  lea     rax, [rsp+260h+var_1E8]
0x1801e0687  mov     qword ptr [rsp+260h+var_238], rax
0x1801e068c  lea     rax, [rsp+260h+var_1F0]
0x1801e0691  mov     [rsp+260h+var_240], rax
0x1801e0696  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1801e069b  call    ?TreatWarningsAsErrors@AppraiserTestHooks@Appraiser@Compat@Windows@@SA_NXZ; Windows::Compat::Appraiser::AppraiserTestHooks::TreatWarningsAsErrors(void)
0x1801e06a0  mov     dword ptr [rsp+260h+var_230], edi
0x1801e06a4  lea     r9, aErrorEndingSea; "Error ending search: [0x%x]."
0x1801e06ab  mov     qword ptr [rsp+260h+var_238], r9
0x1801e06b0  lea     r9, aWindowsCompatA_297; "Windows::Compat::Appraiser::WuDriverCov"...
0x1801e06b7  lea     r8, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e06be  mov     edx, ebx
0x1801e06c0  test    al, al
0x1801e06c2  jz      loc_1801E0498
0x1801e06c8  mov     dword ptr [rsp+260h+var_240], edi
0x1801e06cc  jmp     loc_1801E0491
0x1801e06d1  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1801e06d7  test    r14b, al
0x1801e06da  jz      short loc_1801E06FB
0x1801e06dc  lea     r9, aErrorEndingSea; "Error ending search: [0x%x]."
0x1801e06e3  mov     dword ptr [rsp+260h+var_240], edi
0x1801e06e7  mov     r8, rsi; char *
0x1801e06ea  lea     rdx, aOnecoreBaseApp_99; "onecore\\base\\appcompat\\appraiser\\da"...
0x1801e06f1  mov     ecx, 4D9h; unsigned int
0x1801e06f6  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1801e06fb  xor     r14b, r14b
0x1801e06fe  xor     ebx, ebx
0x1801e0700  mov     rcx, [rsp+260h+var_1F8]
0x1801e0705  test    rcx, rcx
0x1801e0708  jz      loc_1801E0C2F
0x1801e070e  test    r14b, r14b
0x1801e0711  jz      loc_1801E0A72
0x1801e0717  mov     rax, [rcx]
0x1801e071a  mov     rax, [rax+50h]
  ... truncated ...
```
