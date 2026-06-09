# Windows::Compat::Appraiser::DriverInventory::GetInventory(Windows::Compat::Appraiser::IAssetAppender *)

- ea: `0x1800c1390`
- end: `0x1800c1d95`
- name: `?GetInventory@DriverInventory@Appraiser@Compat@Windows@@UEAAJPEAVIAssetAppender@234@@Z`
- size: `2565`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::DriverInventory *__hidden this, struct Windows::Compat::Appraiser::IAssetAppender *)`
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000147c`
- `0x1800018a0`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008e3a0`
- `0x18008fadc`
- `0x1800c0fdc`
- `0x1800c1390`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800c149c`
- `KERNEL32!GetSystemTime` at `0x1800c19d2`
- `KERNEL32!GetSystemTime` at `0x1800c1b6d`
- `KERNEL32!GetSystemTime` at `0x1800c1ca3`
- `KERNEL32!GetSystemTime` at `0x1800c149c`
- `KERNEL32!GetSystemTime` at `0x1800c19d2`
- `KERNEL32!GetSystemTime` at `0x1800c1b6d`
- `KERNEL32!GetSystemTime` at `0x1800c1ca3`
- `KERNEL32!LoadLibraryW` at `0x1800c156c`
- `KERNEL32!LoadLibraryW` at `0x1800c156c`
- `KERNEL32!GetProcAddress` at `0x1800c162f`
- `KERNEL32!GetProcAddress` at `0x1800c1643`
- `KERNEL32!GetProcAddress` at `0x1800c1657`
- `KERNEL32!GetProcAddress` at `0x1800c166f`
- `KERNEL32!GetProcAddress` at `0x1800c1687`
- `KERNEL32!GetProcAddress` at `0x1800c169b`
- `KERNEL32!GetProcAddress` at `0x1800c162f`
- `KERNEL32!GetProcAddress` at `0x1800c1643`
- `KERNEL32!GetProcAddress` at `0x1800c1657`
- `KERNEL32!GetProcAddress` at `0x1800c166f`
- `KERNEL32!GetProcAddress` at `0x1800c1687`
- `KERNEL32!GetProcAddress` at `0x1800c169b`
- `KERNEL32!GetLastError` at `0x1800c15ae`
- `KERNEL32!GetLastError` at `0x1800c16d0`
- `KERNEL32!GetLastError` at `0x1800c1d60`
- `KERNEL32!GetLastError` at `0x1800c1d7a`
- `KERNEL32!GetLastError` at `0x1800c15ae`
- `KERNEL32!GetLastError` at `0x1800c16d0`
- `KERNEL32!GetLastError` at `0x1800c1d60`
- `KERNEL32!GetLastError` at `0x1800c1d7a`
- `SHLWAPI!PathFileExistsW` at `0x1800c1522`
- `SHLWAPI!PathFileExistsW` at `0x1800c1522`

## string_xrefs

- `0x1800c14f9`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c16fd`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c173c`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c1780`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c17bc`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c17ef`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c18fb`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c19a5`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c1a53`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c1a6c`: `Windows::Compat::Appraiser::DriverInventory::GetInventory`
- `0x1800c1503`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1545`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c15de`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1613`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1707`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1743`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c178a`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c17c3`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1811`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c1846`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c186a`: `onecore\base\appcompat\appraiser\inventory\driverinventory.cpp`
- `0x1800c15cb`: `LoadLibrary(dismapi) failed: [0x%x].`
- `0x1800c1609`: `LoadLibrary(dismapi) failed: [0x%x].`
- `0x1800c1565`: `dismapi.dll`
- `0x1800c167c`: `DismOpenSession`
- `0x1800c164c`: `DismDelete`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::DriverInventory::GetInventory(
        Windows::Compat::Appraiser::DriverInventory *this,
        struct Windows::Compat::Appraiser::IAssetAppender *a2)
{
  volatile signed __int64 *v3; // rcx
  void **v4; // rdx
  int v5; // ebx
  int v6; // r8d
  int v7; // r9d
  signed int v8; // ebx
  HMODULE LibraryW; // rbx
  HMODULE v10; // rcx
  signed int LastError; // eax
  FARPROC ProcAddress; // r12
  FARPROC v13; // rsi
  FARPROC v14; // r14
  FARPROC v15; // rax
  __int64 (*v16)(void); // r13
  signed int v17; // eax
  int v18; // eax
  int v19; // eax
  int appended; // eax
  int v21; // eax
  int v22; // r14d
  volatile signed __int64 *v23; // rcx
  void **v24; // rdx
  int v25; // esi
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  int v29; // esi
  volatile signed __int64 *v30; // rcx
  void **v31; // rdx
  int v32; // edi
  int v33; // r8d
  int v34; // r9d
  volatile signed __int64 *v35; // rcx
  void **v36; // rdx
  int v37; // edi
  int v38; // r8d
  int v39; // r9d
  signed int v41; // eax
  int v42; // edx
  unsigned int v43; // r8d
  signed int v44; // eax
  int v45; // edx
  unsigned int v46; // r8d
  char *v47; // [rsp+28h] [rbp-E0h]
  char *v48; // [rsp+38h] [rbp-D0h]
  char *v49; // [rsp+38h] [rbp-D0h]
  unsigned int v50[2]; // [rsp+68h] [rbp-A0h] BYREF
  struct _SYSTEMTIME *v51; // [rsp+70h] [rbp-98h] BYREF
  struct Windows::Compat::Appraiser::IAssetAppender *v52; // [rsp+78h] [rbp-90h] BYREF
  void **v53; // [rsp+80h] [rbp-88h] BYREF
  HMODULE hModule; // [rsp+88h] [rbp-80h]
  char v55[8]; // [rsp+90h] [rbp-78h] BYREF
  char *v56; // [rsp+98h] [rbp-70h] BYREF
  struct _SYSTEMTIME *v57; // [rsp+A0h] [rbp-68h] BYREF
  char v58[8]; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v60; // [rsp+C8h] [rbp-40h]
  struct _SYSTEMTIME v61; // [rsp+D8h] [rbp-30h] BYREF
  struct _SYSTEMTIME v62; // [rsp+E8h] [rbp-20h] BYREF
  char v63[144]; // [rsp+F8h] [rbp-10h] BYREF
  char v64[144]; // [rsp+188h] [rbp+80h] BYREF

  v60 = -2;
  v52 = a2;
  v50[0] = 0;
  v53 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  hModule = 0;
  Windows::Compat::Appraiser::DismDelete = 0;
  Windows::Compat::Appraiser::DismGetDriverInfo = 0;
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v63);
  v3 = (volatile signed __int64 *)v63;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v3 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v3,
    _InterlockedExchangeAdd64(v3 + 17, 0),
    v64);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v4);
  v5 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000004LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000004LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    v56 = v64;
    *(_QWORD *)v55 = 0x1000000;
    v57 = (struct _SYSTEMTIME *)&szValueBuf;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    v61 = SystemTime;
    v51 = &v61;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v5,
      (unsigned int)byte_1802A319B,
      v6,
      v7,
      (__int64)&v51,
      (__int64)&v57,
      (__int64)v55,
      (__int64)&v56);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    147,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
    "Windows::Compat::Appraiser::DriverInventory::GetInventory",
    0,
    (int)"Starting Driver Inventory.",
    v48);
  v50[0] = 0;
  if ( !PathFileExistsW((LPCWSTR)this + 8) )
  {
    Windows::Compat::Appraiser::WriteLog(
      0,
      155,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
      "Windows::Compat::Appraiser::DriverInventory::GetInventory",
      0,
      (int)"Driver folder %ls not present.",
      (const char *)this + 16);
    v8 = 1;
    goto LABEL_72;
  }
  LibraryW = LoadLibraryW(L"dismapi.dll");
  v10 = hModule;
  if ( LibraryW != hModule )
  {
    if ( hModule && !((unsigned __int8 (__fastcall *)(void ***))*v53)(&v53) )
      goto LABEL_86;
    v10 = LibraryW;
    hModule = LibraryW;
  }
  if ( !v10 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 < 0 )
    {
      LODWORD(v49) = v8;
      LODWORD(v47) = v8;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        164,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        v47,
        (int)"LoadLibrary(dismapi) failed: [0x%x].",
        v49);
      goto LABEL_72;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xA4u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        "LoadLibrary(dismapi) failed: [0x%x].",
        v8);
    v10 = hModule;
  }
  ProcAddress = GetProcAddress(v10, "DismInitialize");
  v13 = GetProcAddress(hModule, "DismCloseSession");
  Windows::Compat::Appraiser::DismDelete = (int (*)(void *))GetProcAddress(hModule, "DismDelete");
  Windows::Compat::Appraiser::DismGetDriverInfo = (int (*)(unsigned int, const unsigned __int16 *, struct _DismDriver **, unsigned int *, struct _DismDriverPackage **))GetProcAddress(hModule, "DismGetDriverInfo");
  v14 = GetProcAddress(hModule, "DismOpenSession");
  v15 = GetProcAddress(hModule, "DismShutdown");
  v16 = v15;
  if ( !ProcAddress
    || !v13
    || !Windows::Compat::Appraiser::DismDelete
    || !Windows::Compat::Appraiser::DismGetDriverInfo
    || !v14
    || !v15 )
  {
    v17 = GetLastError();
    v8 = v17;
    if ( v17 > 0 )
      v8 = (unsigned __int16)v17 | 0x80070000;
    if ( v8 < 0 )
    {
      LODWORD(v49) = v8;
      LODWORD(v47) = v8;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        181,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        v47,
        (int)"GetProcAddress(some Dism function) failed: [0x%x].",
        v49);
      goto LABEL_72;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB5u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        "GetProcAddress(some Dism function) failed: [0x%x].",
        v8);
  }
  v18 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))ProcAddress)(0, 0, 0);
  v8 = v18;
  if ( v18 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0xB9u,
        "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        "Error initializing DISM: [0x%x].",
        v18);
    v19 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD, _QWORD, unsigned int *))v14)(
            L"DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF845}",
            0,
            0,
            v50);
    v8 = v19;
    if ( v19 >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0xBDu,
          "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
          "Windows::Compat::Appraiser::DriverInventory::GetInventory",
          "Error initializing DISM Session: [0x%x].",
          v19);
      appended = Windows::Compat::Appraiser::DriverInventory::FindAndAppendDriversFromFolder(
                   (const unsigned __int16 *)this + 8,
                   v50[0],
                   v52);
      v8 = appended;
      if ( appended >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xC1u,
            "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
            "Windows::Compat::Appraiser::DriverInventory::GetInventory",
            "Error finding and appending drivers: [0x%x].",
            appended);
        v8 = 0;
      }
      else
      {
        LODWORD(v49) = appended;
        LODWORD(v47) = appended;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          193,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
          "Windows::Compat::Appraiser::DriverInventory::GetInventory",
          v47,
          (int)"Error finding and appending drivers: [0x%x].",
          v49);
      }
      if ( v13 )
      {
        v21 = ((__int64 (__fastcall *)(_QWORD))v13)(v50[0]);
        v22 = v21;
        if ( v21 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0xCAu,
              "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
              "Windows::Compat::Appraiser::DriverInventory::GetInventory",
              "Error closing DISM Session: [0x%x].",
              v21);
        }
        else
        {
          LODWORD(v49) = v21;
          LODWORD(v47) = v21;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            202,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
            "Windows::Compat::Appraiser::DriverInventory::GetInventory",
            v47,
            (int)"Error closing DISM Session: [0x%x].",
            v49);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v63);
          v23 = (volatile signed __int64 *)v63;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v23 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v23,
            _InterlockedExchangeAdd64(v23 + 17, 0),
            v64);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v24);
          v25 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v52 = (struct Windows::Compat::Appraiser::IAssetAppender *)v64;
            *(_DWORD *)v55 = v22;
            v51 = (struct _SYSTEMTIME *)"Windows::Compat::Appraiser::DriverInventory::GetInventory";
            v57 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp";
            LODWORD(v56) = 202;
            *(_QWORD *)v58 = &szValueBuf;
            v61 = 0;
            GetSystemTime(&v61);
            v62 = v61;
            *(_QWORD *)&SystemTime.wYear = &v62;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v25,
              (unsigned int)byte_1802A31E9,
              v26,
              v27,
              (__int64)&SystemTime,
              (__int64)v58,
              (__int64)&v56,
              (__int64)&v57,
              (__int64)&v51,
              (__int64)v55,
              (__int64)&v52);
          }
        }
      }
    }
    else
    {
      LODWORD(v49) = v19;
      LODWORD(v47) = v19;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        189,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
        "Windows::Compat::Appraiser::DriverInventory::GetInventory",
        v47,
        (int)"Error initializing DISM Session: [0x%x].",
        v49);
    }
    if ( v16 )
    {
      v28 = v16();
      v29 = v28;
      if ( v28 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0xD0u,
            "onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
            "Windows::Compat::Appraiser::DriverInventory::GetInventory",
            "Error shutting down DISM: [0x%x].",
            v28);
      }
      else
      {
        LODWORD(v49) = v28;
        LODWORD(v47) = v28;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          208,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
          "Windows::Compat::Appraiser::DriverInventory::GetInventory",
          v47,
          (int)"Error shutting down DISM: [0x%x].",
          v49);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v63);
        v30 = (volatile signed __int64 *)v63;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v30 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v30,
          _InterlockedExchangeAdd64(v30 + 17, 0),
          v64);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v31);
        v32 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          *(_QWORD *)&SystemTime.wYear = v64;
          LODWORD(v56) = v29;
          *(_QWORD *)v58 = "Windows::Compat::Appraiser::DriverInventory::GetInventory";
          v52 = (struct Windows::Compat::Appraiser::IAssetAppender *)"onecore\\base\\appcompat\\appraiser\\inventory\\dri"
                                                                     "verinventory.cpp";
          *(_DWORD *)v55 = 208;
          v51 = (struct _SYSTEMTIME *)&szValueBuf;
          v61 = 0;
          GetSystemTime(&v61);
          v62 = v61;
          v57 = &v62;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v32,
            (unsigned int)&dword_1802A324C,
            v33,
            v34,
            (__int64)&v57,
            (__int64)&v51,
            (__int64)v55,
            (__int64)&v52,
            (__int64)v58,
            (__int64)&v56,
            (__int64)&SystemTime);
        }
      }
    }
  }
  else
  {
    LODWORD(v49) = v18;
    LODWORD(v47) = v18;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      185,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
      "Windows::Compat::Appraiser::DriverInventory::GetInventory",
      v47,
      (int)"Error initializing DISM: [0x%x].",
      v49);
  }
LABEL_72:
  TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v63);
  v35 = (volatile signed __int64 *)v63;
  if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
    v35 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
  TraceLoggingCorrelationVector::ToStringImpl(
    (TraceLoggingCorrelationVector *)v35,
    _InterlockedExchangeAdd64(v35 + 17, 0),
    v64);
  if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
    UtcThrottle::Throttle((UtcThrottle *)Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v36);
  v37 = qword_1802C9628;
  if ( *(_DWORD *)qword_1802C9628 > 5u
    && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000004LL) != 0
    && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000004LL) == *(_QWORD *)(qword_1802C9628 + 24) )
  {
    *(_QWORD *)&SystemTime.wYear = v64;
    *(_QWORD *)v58 = 0x1000000;
    v52 = (struct Windows::Compat::Appraiser::IAssetAppender *)&szValueBuf;
    v61 = 0;
    GetSystemTime(&v61);
    v62 = v61;
    v51 = &v62;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
      v37,
      (unsigned int)byte_1802A3089,
      v38,
      v39,
      (__int64)&v51,
      (__int64)&v52,
      (__int64)v58,
      (__int64)&SystemTime);
  }
  Windows::Compat::Appraiser::WriteLog(
    0,
    211,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\inventory\\driverinventory.cpp",
    "Windows::Compat::Appraiser::DriverInventory::GetInventory",
    0,
    (int)"Finished Driver Inventory.",
    v49);
  v53 = &Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable';
  if ( hModule && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::InternalClose(&v53) )
  {
    v41 = GetLastError();
    if ( v41 > 0 )
      v41 = (unsigned __int16)v41 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v41, v42, v43);
LABEL_86:
    v44 = GetLastError();
    if ( v44 > 0 )
      v44 = (unsigned __int16)v44 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v44, v45, v46);
    JUMPOUT(0x1800C1D94LL);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800c1390  mov     rax, rsp
0x1800c1393  push    rbp
0x1800c1394  push    rsi
0x1800c1395  push    rdi
0x1800c1396  push    r12
0x1800c1398  push    r13
0x1800c139a  push    r14
0x1800c139c  push    r15
0x1800c139e  lea     rbp, [rax-158h]
0x1800c13a5  sub     rsp, 220h
0x1800c13ac  mov     [rbp+150h+var_190], 0FFFFFFFFFFFFFFFEh
0x1800c13b4  mov     [rax+18h], rbx
0x1800c13b8  mov     rax, cs:__security_cookie
0x1800c13bf  xor     rax, rsp
0x1800c13c2  mov     [rbp+150h+var_40], rax
0x1800c13c9  mov     [rsp+250h+var_1E0], rdx
0x1800c13ce  mov     rdi, rcx
0x1800c13d1  xor     r12d, r12d
0x1800c13d4  mov     [rsp+250h+var_1F0], r12d
0x1800c13d9  lea     rax, ??_7?$HandleT@UModuleHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<ModuleHandleTraits>::`vftable'
0x1800c13e0  mov     [rsp+250h+var_1D8], rax
0x1800c13e5  mov     [rbp+150h+hModule], r12
0x1800c13e9  mov     cs:?DismDelete@Appraiser@Compat@Windows@@3P6AJPEAX@ZEA, r12; long (*Windows::Compat::Appraiser::DismDelete)(void *)
0x1800c13f0  mov     cs:?DismGetDriverInfo@Appraiser@Compat@Windows@@3P6AJIPEBGPEAPEAU_DismDriver@@PEAIPEAPEAU_DismDriverPackage@@@ZEA, r12; long (*Windows::Compat::Appraiser::DismGetDriverInfo)(uint,ushort const *,_DismDriver * *,uint *,_DismDriverPackage * *)
0x1800c13f7  lea     rcx, [rbp+150h+var_160]; this
0x1800c13fb  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x1800c1400  lea     rcx, [rbp+150h+var_160]
0x1800c1404  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x1800c140b  test    rax, rax
0x1800c140e  cmovnz  rcx, rax; this
0x1800c1412  mov     edx, r12d
0x1800c1415  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800c141e  lea     r8, [rbp+150h+var_D0]; char *
0x1800c1425  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800c142a  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800c1431  jz      short loc_1800C143F
0x1800c1433  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800c143a  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800c143f  mov     rbx, cs:qword_1802C9628
0x1800c1446  mov     eax, [rbx]
0x1800c1448  mov     rsi, 200000000004h
0x1800c1452  lea     r13, szValueBuf
0x1800c1459  cmp     eax, 5
0x1800c145c  jbe     loc_1800C14E8
0x1800c1462  mov     rcx, [rbx+18h]
0x1800c1466  mov     rax, [rbx+10h]
0x1800c146a  test    rsi, rax
0x1800c146d  jz      short loc_1800C14E8
0x1800c146f  mov     rax, rcx
0x1800c1472  and     rax, rsi
0x1800c1475  cmp     rax, rcx
0x1800c1478  jnz     short loc_1800C14E8
0x1800c147a  lea     rax, [rbp+150h+var_D0]
0x1800c1481  mov     [rbp+150h+var_1C0], rax
0x1800c1485  mov     qword ptr [rbp+150h+var_1C8], 1000000h
0x1800c148d  mov     [rbp+150h+var_1B8], r13
0x1800c1491  xorps   xmm0, xmm0
0x1800c1494  movups  xmmword ptr [rbp+150h+SystemTime.wYear], xmm0
0x1800c1498  lea     rcx, [rbp+150h+SystemTime]; lpSystemTime
0x1800c149c  call    cs:__imp_GetSystemTime
0x1800c14a2  movaps  xmm0, xmmword ptr [rbp+150h+SystemTime.wYear]
0x1800c14a6  movdqa  xmmword ptr [rbp+150h+var_180.wYear], xmm0
0x1800c14ab  lea     rax, [rbp+150h+var_180]
0x1800c14af  mov     [rsp+250h+var_1E8], rax
0x1800c14b4  lea     rax, [rbp+150h+var_1C0]
0x1800c14b8  mov     [rsp+250h+var_218], rax
0x1800c14bd  lea     rax, [rbp+150h+var_1C8]
0x1800c14c1  mov     [rsp+250h+var_220], rax; char *
0x1800c14c6  lea     rax, [rbp+150h+var_1B8]
0x1800c14ca  mov     qword ptr [rsp+250h+var_228], rax
0x1800c14cf  lea     rax, [rsp+250h+var_1E8]
0x1800c14d4  mov     [rsp+250h+var_230], rax
0x1800c14d9  lea     rdx, byte_1802A319B
0x1800c14e0  mov     rcx, rbx
0x1800c14e3  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &)
0x1800c14e8  lea     rax, aStartingDriver; "Starting Driver Inventory."
0x1800c14ef  mov     qword ptr [rsp+250h+var_228], rax; int
0x1800c14f4  mov     [rsp+250h+var_230], r12; char *
0x1800c14f9  lea     r14, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c1500  mov     r9, r14; char *
0x1800c1503  lea     r8, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c150a  mov     edx, 93h; bool
0x1800c150f  xor     ecx, ecx; this
0x1800c1511  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c1516  mov     [rsp+250h+var_1F0], r12d
0x1800c151b  lea     r15, [rdi+10h]
0x1800c151f  mov     rcx, r15; pszPath
0x1800c1522  call    cs:__imp_PathFileExistsW
0x1800c1528  test    eax, eax
0x1800c152a  jnz     short loc_1800C1565
0x1800c152c  mov     [rsp+250h+var_220], r15; char *
0x1800c1531  lea     rax, aDriverFolderLs; "Driver folder %ls not present."
0x1800c1538  mov     qword ptr [rsp+250h+var_228], rax; int
0x1800c153d  mov     [rsp+250h+var_230], r12; char *
0x1800c1542  mov     r9, r14; char *
0x1800c1545  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c154c  mov     r8, r15; unsigned int
0x1800c154f  mov     edx, 9Bh; bool
0x1800c1554  xor     ecx, ecx; this
0x1800c1556  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c155b  mov     ebx, 1
0x1800c1560  jmp     loc_1800C1C0E
0x1800c1565  lea     rcx, aDismapiDll; "dismapi.dll"
0x1800c156c  call    cs:__imp_LoadLibraryW
0x1800c1572  mov     rbx, rax
0x1800c1575  mov     rcx, [rbp+150h+hModule]
0x1800c1579  cmp     rax, rcx
0x1800c157c  jz      short loc_1800C15A4
0x1800c157e  test    rcx, rcx
0x1800c1581  jz      short loc_1800C159D
0x1800c1583  mov     rcx, [rsp+250h+var_1D8]
0x1800c1588  mov     rax, [rcx]
0x1800c158b  lea     rcx, [rsp+250h+var_1D8]
0x1800c1590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1595  test    al, al
0x1800c1597  jz      loc_1800C1D7A
0x1800c159d  mov     rcx, rbx
0x1800c15a0  mov     [rbp+150h+hModule], rbx
0x1800c15a4  mov     edi, 1
0x1800c15a9  test    rcx, rcx
0x1800c15ac  jnz     short loc_1800C1628
0x1800c15ae  call    cs:__imp_GetLastError
0x1800c15b4  mov     ebx, eax
0x1800c15b6  test    eax, eax
0x1800c15b8  jle     short loc_1800C15C3
0x1800c15ba  movzx   ebx, ax
0x1800c15bd  or      ebx, 80070000h
0x1800c15c3  test    ebx, ebx
0x1800c15c5  jns     short loc_1800C15F9
0x1800c15c7  mov     dword ptr [rsp+250h+var_220], ebx; char *
0x1800c15cb  lea     r9, aLoadlibraryDis; "LoadLibrary(dismapi) failed: [0x%x]."
0x1800c15d2  mov     qword ptr [rsp+250h+var_228], r9; int
0x1800c15d7  mov     dword ptr [rsp+250h+var_230], ebx; char *
0x1800c15db  mov     r9, r14; char *
0x1800c15de  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c15e5  mov     r8, r15; unsigned int
0x1800c15e8  mov     edx, 0A4h; bool
0x1800c15ed  mov     ecx, edi; this
0x1800c15ef  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c15f4  jmp     loc_1800C1C0E
0x1800c15f9  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c15ff  and     eax, edi
0x1800c1601  test    al, al
0x1800c1603  jz      short loc_1800C1624
0x1800c1605  mov     dword ptr [rsp+250h+var_230], ebx
0x1800c1609  lea     r9, aLoadlibraryDis; "LoadLibrary(dismapi) failed: [0x%x]."
0x1800c1610  mov     r8, r14; char *
0x1800c1613  lea     rdx, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c161a  mov     ecx, 0A4h; unsigned int
0x1800c161f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c1624  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c1628  lea     rdx, aDisminitialize; "DismInitialize"
0x1800c162f  call    cs:__imp_GetProcAddress
0x1800c1635  mov     r12, rax
0x1800c1638  lea     rdx, aDismclosesessi; "DismCloseSession"
0x1800c163f  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c1643  call    cs:__imp_GetProcAddress
0x1800c1649  mov     rsi, rax
0x1800c164c  lea     rdx, aDismdelete; "DismDelete"
0x1800c1653  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c1657  call    cs:__imp_GetProcAddress
0x1800c165d  mov     cs:?DismDelete@Appraiser@Compat@Windows@@3P6AJPEAX@ZEA, rax; long (*Windows::Compat::Appraiser::DismDelete)(void *)
0x1800c1664  lea     rdx, aDismgetdriveri; "DismGetDriverInfo"
0x1800c166b  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c166f  call    cs:__imp_GetProcAddress
0x1800c1675  mov     cs:?DismGetDriverInfo@Appraiser@Compat@Windows@@3P6AJIPEBGPEAPEAU_DismDriver@@PEAIPEAPEAU_DismDriverPackage@@@ZEA, rax; long (*Windows::Compat::Appraiser::DismGetDriverInfo)(uint,ushort const *,_DismDriver * *,uint *,_DismDriverPackage * *)
0x1800c167c  lea     rdx, aDismopensessio; "DismOpenSession"
0x1800c1683  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c1687  call    cs:__imp_GetProcAddress
0x1800c168d  mov     r14, rax
0x1800c1690  lea     rdx, aDismshutdown; "DismShutdown"
0x1800c1697  mov     rcx, [rbp+150h+hModule]; hModule
0x1800c169b  call    cs:__imp_GetProcAddress
0x1800c16a1  mov     r13, rax
0x1800c16a4  test    r12, r12
0x1800c16a7  jz      short loc_1800C16D0
0x1800c16a9  test    rsi, rsi
0x1800c16ac  jz      short loc_1800C16D0
0x1800c16ae  cmp     cs:?DismDelete@Appraiser@Compat@Windows@@3P6AJPEAX@ZEA, 0; long (*Windows::Compat::Appraiser::DismDelete)(void *)
0x1800c16b6  jz      short loc_1800C16D0
0x1800c16b8  cmp     cs:?DismGetDriverInfo@Appraiser@Compat@Windows@@3P6AJIPEBGPEAPEAU_DismDriver@@PEAIPEAPEAU_DismDriverPackage@@@ZEA, 0; long (*Windows::Compat::Appraiser::DismGetDriverInfo)(uint,ushort const *,_DismDriver * *,uint *,_DismDriverPackage * *)
0x1800c16c0  jz      short loc_1800C16D0
0x1800c16c2  test    r14, r14
0x1800c16c5  jz      short loc_1800C16D0
0x1800c16c7  test    rax, rax
0x1800c16ca  jnz     loc_1800C1754
0x1800c16d0  call    cs:__imp_GetLastError
0x1800c16d6  mov     ebx, eax
0x1800c16d8  test    eax, eax
0x1800c16da  jle     short loc_1800C16E5
0x1800c16dc  movzx   ebx, ax
0x1800c16df  or      ebx, 80070000h
0x1800c16e5  test    ebx, ebx
0x1800c16e7  jns     short loc_1800C1725
0x1800c16e9  mov     dword ptr [rsp+250h+var_220], ebx; char *
0x1800c16ed  lea     r9, aGetprocaddress_0; "GetProcAddress(some Dism function) fail"...
0x1800c16f4  mov     qword ptr [rsp+250h+var_228], r9; int
0x1800c16f9  mov     dword ptr [rsp+250h+var_230], ebx; char *
0x1800c16fd  lea     r14, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c1704  mov     r9, r14; char *
0x1800c1707  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c170e  mov     r8, r15; unsigned int
0x1800c1711  mov     edx, 0B5h; bool
0x1800c1716  mov     ecx, edi; this
0x1800c1718  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c171d  xor     r12d, r12d
0x1800c1720  jmp     loc_1800C1BFD
0x1800c1725  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c172b  and     eax, edi
0x1800c172d  test    al, al
0x1800c172f  jz      short loc_1800C1754
0x1800c1731  mov     dword ptr [rsp+250h+var_230], ebx
0x1800c1735  lea     r9, aGetprocaddress_0; "GetProcAddress(some Dism function) fail"...
0x1800c173c  lea     r8, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c1743  lea     rdx, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c174a  mov     ecx, 0B5h; unsigned int
0x1800c174f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c1754  xor     r8d, r8d
0x1800c1757  xor     edx, edx
0x1800c1759  xor     ecx, ecx
0x1800c175b  mov     rax, r12
0x1800c175e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1763  mov     ebx, eax
0x1800c1765  xor     r12d, r12d
0x1800c1768  test    eax, eax
0x1800c176a  jns     short loc_1800C17A5
0x1800c176c  mov     dword ptr [rsp+250h+var_220], eax; char *
0x1800c1770  lea     r9, aErrorInitializ_2; "Error initializing DISM: [0x%x]."
0x1800c1777  mov     qword ptr [rsp+250h+var_228], r9; int
0x1800c177c  mov     dword ptr [rsp+250h+var_230], eax; char *
0x1800c1780  lea     r14, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c1787  mov     r9, r14; char *
0x1800c178a  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c1791  mov     r8, r15; unsigned int
0x1800c1794  mov     edx, 0B9h; bool
0x1800c1799  mov     ecx, edi; this
0x1800c179b  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c17a0  jmp     loc_1800C1BFD
0x1800c17a5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c17ab  and     eax, edi
0x1800c17ad  test    al, al
0x1800c17af  jz      short loc_1800C17D4
0x1800c17b1  mov     dword ptr [rsp+250h+var_230], ebx
0x1800c17b5  lea     r9, aErrorInitializ_2; "Error initializing DISM: [0x%x]."
0x1800c17bc  lea     r8, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c17c3  lea     rdx, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c17ca  mov     ecx, 0B9h; unsigned int
0x1800c17cf  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c17d4  lea     r9, [rsp+250h+var_1F0]
0x1800c17d9  xor     r8d, r8d
0x1800c17dc  xor     edx, edx
0x1800c17de  lea     rcx, aDism53bfae52B1; "DISM_{53BFAE52-B167-4E2F-A258-0A37B57FF"...
0x1800c17e5  mov     rax, r14
0x1800c17e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c17ed  mov     ebx, eax
0x1800c17ef  lea     r14, aWindowsCompatA_650; "Windows::Compat::Appraiser::DriverInven"...
0x1800c17f6  test    eax, eax
0x1800c17f8  jns     short loc_1800C182C
0x1800c17fa  mov     dword ptr [rsp+250h+var_220], eax; char *
0x1800c17fe  lea     r9, aErrorInitializ_8; "Error initializing DISM Session: [0x%x]"...
0x1800c1805  mov     qword ptr [rsp+250h+var_228], r9; int
0x1800c180a  mov     dword ptr [rsp+250h+var_230], eax; char *
0x1800c180e  mov     r9, r14; char *
0x1800c1811  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c1818  mov     r8, r15; unsigned int
0x1800c181b  mov     edx, 0BDh; bool
0x1800c1820  mov     ecx, edi; this
0x1800c1822  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c1827  jmp     loc_1800C1A73
0x1800c182c  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c1832  and     eax, edi
0x1800c1834  test    al, al
0x1800c1836  jz      short loc_1800C1857
0x1800c1838  mov     dword ptr [rsp+250h+var_230], ebx
0x1800c183c  lea     r9, aErrorInitializ_8; "Error initializing DISM Session: [0x%x]"...
0x1800c1843  mov     r8, r14; char *
0x1800c1846  lea     rdx, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c184d  mov     ecx, 0BDh; unsigned int
0x1800c1852  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800c1857  mov     r8, [rsp+250h+var_1E0]; struct Windows::Compat::Appraiser::IAssetAppender *
0x1800c185c  mov     edx, [rsp+250h+var_1F0]; unsigned int
0x1800c1860  mov     rcx, r15; unsigned __int16 *
0x1800c1863  call    ?FindAndAppendDriversFromFolder@DriverInventory@Appraiser@Compat@Windows@@CAJPEBGIPEAVIAssetAppender@234@@Z; Windows::Compat::Appraiser::DriverInventory::FindAndAppendDriversFromFolder(ushort const *,uint,Windows::Compat::Appraiser::IAssetAppender *)
0x1800c1868  mov     ebx, eax
0x1800c186a  lea     r15, aOnecoreBaseApp_108; "onecore\\base\\appcompat\\appraiser\\in"...
0x1800c1871  test    eax, eax
0x1800c1873  jns     short loc_1800C189D
0x1800c1875  mov     dword ptr [rsp+250h+var_220], eax; char *
0x1800c1879  lea     r9, aErrorFindingAn_0; "Error finding and appending drivers: [0"...
0x1800c1880  mov     qword ptr [rsp+250h+var_228], r9; int
0x1800c1885  mov     dword ptr [rsp+250h+var_230], eax; char *
0x1800c1889  mov     r9, r14; char *
0x1800c188c  mov     r8, r15; unsigned int
0x1800c188f  mov     edx, 0C1h; bool
0x1800c1894  mov     ecx, edi; this
0x1800c1896  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800c189b  jmp     short loc_1800C18C7
0x1800c189d  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800c18a3  and     eax, edi
0x1800c18a5  test    al, al
  ... truncated ...
```
