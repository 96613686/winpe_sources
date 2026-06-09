# Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys(ushort *,bool &,unsigned __int64,ushort *,bool &,unsigned __int64,ulong &,bool &,ulong &,bool &,ulong &,bool &,bool &)

- ea: `0x18008c378`
- end: `0x18008ccc5`
- name: `?GetWuConfigRegKeys@Utilities@Appraiser@Compat@Windows@@SAJPEAGAEA_N_K012AEAK131311@Z`
- size: `2381`
- prototype: `static int(unsigned __int16 *, bool *, unsigned __int64, unsigned __int16 *, bool *, unsigned __int64, unsigned int *, bool *, unsigned int *, bool *, unsigned int *, bool *, bool *)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180031920`
- `0x180053e24`
- `0x18008eb54`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180013c7c`
- `0x1800151f4`
- `0x180026fd0`
- `0x180029258`
- `0x1800301d0`
- `0x18008c378`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18008c5b4`
- `KERNEL32!GetSystemTime` at `0x18008c732`
- `KERNEL32!GetSystemTime` at `0x18008c92e`
- `KERNEL32!GetSystemTime` at `0x18008ca88`
- `KERNEL32!GetSystemTime` at `0x18008cc2d`
- `KERNEL32!GetSystemTime` at `0x18008c5b4`
- `KERNEL32!GetSystemTime` at `0x18008c732`
- `KERNEL32!GetSystemTime` at `0x18008c92e`
- `KERNEL32!GetSystemTime` at `0x18008ca88`
- `KERNEL32!GetSystemTime` at `0x18008cc2d`

## string_xrefs

- `0x18008c4d9`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c586`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c654`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c717`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c7e0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c85b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008cc07`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x18008c411`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18008c486`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18008c802`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18008cb09`: `Software\Policies\Microsoft\Windows\WindowsUpdate`
- `0x18008c4c2`: `Error reading if WU status server is set, swallowing: [0x%x].`
- `0x18008c7b3`: `Software\Policies\Microsoft\Windows\WindowsUpdate\AU`
- `0x18008c844`: `Error reading if use WU server is set, swallowing: [0x%x].`
- `0x18008c456`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c4d2`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c57f`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c620`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c701`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c7e7`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c854`: `Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys`
- `0x18008c644`: `Error reading if WU server is set, swallowing: [0x%x].`
- `0x18008caf9`: `DisableWindowsUpdateAccess`
- `0x18008cb52`: `Error reading if disable WU access is set, swallowing: [0x%x].`
- `0x18008c7f2`: `DoNotConnectToWindowsUpdateInternetLocations`
- `0x18008c9ad`: `Error reading if don't connect to WU is set, swallowing: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys(
        unsigned __int16 *a1,
        bool *a2,
        __int64 a3,
        unsigned __int16 *a4,
        bool *a5,
        unsigned __int64 a6,
        unsigned int *pvData,
        bool *a8,
        unsigned int *a9,
        bool *a10,
        unsigned int *a11,
        bool *a12,
        bool *a13)
{
  int v13; // edi
  int v16; // eax
  HKEY v17; // r9
  int v18; // eax
  HKEY v19; // r9
  int v20; // ebx
  volatile signed __int64 *v21; // rcx
  void **v22; // rdx
  int v23; // ebx
  int v24; // r8d
  int v25; // r9d
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // edi
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  HKEY v32; // r9
  int v33; // edi
  _DWORD *v34; // rcx
  int Value; // eax
  HKEY v36; // r9
  int v37; // edi
  volatile signed __int64 *v38; // rcx
  void **v39; // rdx
  int v40; // ebx
  int v41; // r8d
  int v42; // r9d
  volatile signed __int64 *v43; // rcx
  void **v44; // rdx
  int v45; // ebx
  int v46; // r8d
  int v47; // r9d
  _DWORD *v48; // rcx
  int v49; // eax
  int v50; // edi
  volatile signed __int64 *v51; // rcx
  void **v52; // rdx
  int v53; // ebx
  int v54; // r8d
  int v55; // r9d
  char *v57; // [rsp+20h] [rbp-E0h]
  char *v58; // [rsp+20h] [rbp-E0h]
  char *v59; // [rsp+20h] [rbp-E0h]
  char *v60; // [rsp+20h] [rbp-E0h]
  char *v61; // [rsp+20h] [rbp-E0h]
  char *v62; // [rsp+30h] [rbp-D0h]
  int v63; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v64; // [rsp+68h] [rbp-98h] BYREF
  unsigned __int64 v65; // [rsp+70h] [rbp-90h] BYREF
  struct _SYSTEMTIME *v66; // [rsp+78h] [rbp-88h] BYREF
  const char *v67; // [rsp+80h] [rbp-80h] BYREF
  PVOID v68; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  char *v70; // [rsp+A0h] [rbp-60h] BYREF
  const char *v71; // [rsp+A8h] [rbp-58h] BYREF
  char *v72; // [rsp+B0h] [rbp-50h] BYREF
  PVOID v73; // [rsp+B8h] [rbp-48h] BYREF
  char *v74; // [rsp+C0h] [rbp-40h] BYREF
  struct _SYSTEMTIME v75; // [rsp+D0h] [rbp-30h] BYREF
  char v76[144]; // [rsp+E0h] [rbp-20h] BYREF
  char v77[144]; // [rsp+170h] [rbp+70h] BYREF

  v13 = 0;
  *a12 = 0;
  *a10 = 0;
  *a8 = 0;
  *a5 = 0;
  *a2 = 0;
  *a4 = 0;
  *a11 = 0;
  *a9 = 0;
  v72 = (char *)a10;
  *pvData = 0;
  v68 = a9;
  v73 = a11;
  *a13 = 1;
  *a1 = 0;
  v74 = (char *)a12;
  v65 = 520;
  v16 = Windows::Compat::Shared::Registry::ReadValue(
          a1,
          &v65,
          2u,
          (HKEY)a12,
          L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
          L"WUStatusServer");
  if ( v16 < 0 )
    v13 = v16;
  if ( v13 < 0 )
  {
    if ( (unsigned int)(v13 + 2147024894) > 1 )
    {
      LODWORD(v62) = v13;
      LODWORD(v57) = v13;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        166,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys",
        v57,
        (int)"Error reading if WU status server is set, swallowing: [0x%x].",
        v62);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v76);
      v21 = (volatile signed __int64 *)v76;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v21 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v21,
        _InterlockedExchangeAdd64(v21 + 17, 0),
        v77);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v22);
      v23 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v63 = v13;
        v70 = v77;
        v71 = "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys";
        v66 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        LODWORD(v65) = 7590;
        v67 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v64 = (unsigned __int64)&v75;
        v75 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v23,
          (unsigned int)&unk_1802A1BFD,
          v24,
          v25,
          (__int64)&v64,
          (__int64)&v67,
          (__int64)&v65,
          (__int64)&v66,
          (__int64)&v71,
          (__int64)&v63,
          (__int64)&v70);
      }
      *a13 = 0;
    }
  }
  else
  {
    *a2 = 1;
  }
  v64 = 520;
  *a4 = 0;
  v18 = Windows::Compat::Shared::Registry::ReadValue(
          a4,
          &v64,
          2u,
          v17,
          L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
          L"WUServer");
  v20 = 0;
  if ( v18 < 0 )
    v20 = v18;
  if ( v20 < 0 )
  {
    if ( (unsigned int)(v20 + 2147024894) > 1 )
    {
      LODWORD(v62) = v20;
      LODWORD(v58) = v20;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        180,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys",
        v58,
        (int)"Error reading if WU server is set, swallowing: [0x%x].",
        v62);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v76);
      v26 = (volatile signed __int64 *)v76;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v26,
        _InterlockedExchangeAdd64(v26 + 17, 0),
        v77);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
      v28 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v65) = v20;
        v64 = (unsigned __int64)v77;
        v63 = 7604;
        v67 = "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys";
        v66 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v71 = (const char *)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v70 = (char *)&v75;
        v75 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v28,
          (unsigned int)&unk_1802A1CC3,
          v29,
          v30,
          (__int64)&v70,
          (__int64)&v71,
          (__int64)&v63,
          (__int64)&v66,
          (__int64)&v67,
          (__int64)&v65,
          (__int64)&v64);
      }
      *a13 = 0;
    }
  }
  else
  {
    *a5 = 1;
  }
  *pvData = 0;
  v64 = 4;
  v31 = Windows::Compat::Shared::Registry::ReadValue(
          pvData,
          &v64,
          0x10u,
          v19,
          L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate\\AU",
          L"UseWUServer");
  v33 = v31;
  if ( v31 < 0 )
  {
    if ( (unsigned int)(v31 + 2147024894) > 1 )
    {
      LODWORD(v62) = v31;
      LODWORD(v59) = v31;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        193,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys",
        v59,
        (int)"Error reading if use WU server is set, swallowing: [0x%x].",
        v62);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v76);
      v38 = (volatile signed __int64 *)v76;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v38 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v38,
        _InterlockedExchangeAdd64(v38 + 17, 0),
        v77);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v39);
      v40 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v65) = v33;
        v64 = (unsigned __int64)v77;
        v67 = "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys";
        v71 = (const char *)&szValueBuf;
        v66 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v63 = 7617;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v70 = (char *)&v75;
        v75 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)&unk_1802A1C60,
          v41,
          v42,
          (__int64)&v70,
          (__int64)&v71,
          (__int64)&v63,
          (__int64)&v66,
          (__int64)&v67,
          (__int64)&v65,
          (__int64)&v64);
      }
      *a13 = 0;
    }
  }
  else
  {
    *a8 = 1;
  }
  v34 = v68;
  v68 = (PVOID)4;
  *v34 = 0;
  Value = Windows::Compat::Shared::Registry::ReadValue(
            v34,
            (unsigned __int64 *)&v68,
            0x10u,
            v32,
            L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
            L"DoNotConnectToWindowsUpdateInternetLocations");
  v37 = Value;
  if ( Value < 0 )
  {
    if ( (unsigned int)(Value + 2147024894) > 1 )
    {
      LODWORD(v62) = Value;
      LODWORD(v60) = Value;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        206,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys",
        v60,
        (int)"Error reading if don't connect to WU is set, swallowing: [0x%x].",
        v62);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v76);
      v43 = (volatile signed __int64 *)v76;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v43 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v43,
        _InterlockedExchangeAdd64(v43 + 17, 0),
        v77);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v44);
      v45 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v65) = v37;
        v72 = v77;
        v68 = (PVOID)"Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys";
        v67 = (const char *)&szValueBuf;
        v64 = (unsigned __int64)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v63 = 7630;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v66 = &v75;
        v75 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v45,
          (unsigned int)&unk_1802A1B9A,
          v46,
          v47,
          (__int64)&v66,
          (__int64)&v67,
          (__int64)&v63,
          (__int64)&v64,
          (__int64)&v68,
          (__int64)&v65,
          (__int64)&v72);
      }
      *a13 = 0;
    }
  }
  else
  {
    *v72 = 1;
  }
  v48 = v73;
  v73 = (PVOID)4;
  *v48 = 0;
  v49 = Windows::Compat::Shared::Registry::ReadValue(
          v48,
          (unsigned __int64 *)&v73,
          0x10u,
          v36,
          L"Software\\Policies\\Microsoft\\Windows\\WindowsUpdate",
          L"DisableWindowsUpdateAccess");
  v50 = v49;
  if ( v49 < 0 )
  {
    if ( (unsigned int)(v49 + 2147024894) > 1 )
    {
      LODWORD(v62) = v49;
      LODWORD(v61) = v49;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        219,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys",
        v61,
        (int)"Error reading if disable WU access is set, swallowing: [0x%x].",
        v62);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v76);
      v51 = (volatile signed __int64 *)v76;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v51 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v51,
        _InterlockedExchangeAdd64(v51 + 17, 0),
        v77);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v52);
      v53 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        LODWORD(v65) = v50;
        v74 = v77;
        v73 = (PVOID)"Windows::Compat::Appraiser::Utilities::GetWuConfigRegKeys";
        v72 = "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp";
        v63 = 7643;
        v68 = (PVOID)&szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v64 = (unsigned __int64)&v75;
        v75 = SystemTime;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v53,
          (unsigned int)&unk_1802A1B37,
          v54,
          v55,
          (__int64)&v64,
          (__int64)&v68,
          (__int64)&v63,
          (__int64)&v72,
          (__int64)&v73,
          (__int64)&v65,
          (__int64)&v74);
      }
      *a13 = 0;
    }
  }
  else
  {
    *v74 = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18008c378  mov     [rsp-8+arg_10], rbx
0x18008c37d  push    rbp
0x18008c37e  push    rsi
0x18008c37f  push    rdi
0x18008c380  push    r12
0x18008c382  push    r13
0x18008c384  push    r14
0x18008c386  push    r15
0x18008c388  lea     rbp, [rsp-110h]
0x18008c390  sub     rsp, 210h
0x18008c397  mov     rax, cs:__security_cookie
0x18008c39e  xor     rax, rsp
0x18008c3a1  mov     [rbp+140h+var_40], rax
0x18008c3a8  mov     r8, [rbp+140h+arg_50]
0x18008c3af  xor     edi, edi
0x18008c3b1  mov     rax, [rbp+140h+arg_48]
0x18008c3b8  mov     rbx, rdx
0x18008c3bb  mov     rdx, [rbp+140h+arg_40]
0x18008c3c2  mov     r14, r9
0x18008c3c5  mov     r9, [rbp+140h+arg_58]; HKEY
0x18008c3cc  mov     r13, [rbp+140h+arg_38]
0x18008c3d3  mov     r15, [rbp+140h+arg_20]
0x18008c3da  mov     r12, [rbp+140h+pvData]
0x18008c3e1  mov     rsi, [rbp+140h+arg_60]
0x18008c3e8  mov     [r9], dil
0x18008c3eb  mov     [rax], dil
0x18008c3ee  mov     [r13+0], dil
0x18008c3f2  mov     [r15], dil
0x18008c3f5  mov     [rbx], dil
0x18008c3f8  mov     [r14], di
0x18008c3fc  mov     [r8], edi
0x18008c3ff  mov     [rdx], edi
0x18008c401  mov     [rbp+140h+var_190], rax
0x18008c405  lea     rax, aWustatusserver_0; "WUStatusServer"
0x18008c40c  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18008c411  lea     rax, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18008c418  mov     [r12], edi
0x18008c41c  mov     [rbp+140h+var_1B8], rdx
0x18008c420  lea     rdx, [rsp+240h+var_1D0]; unsigned __int64 *
0x18008c425  mov     [rbp+140h+var_188], r8
0x18008c429  lea     r8d, [rdi+2]; unsigned int
0x18008c42d  mov     byte ptr [rsi], 1
0x18008c430  mov     [rcx], di
0x18008c433  mov     [rbp+140h+var_180], r9
0x18008c437  mov     [rsp+240h+var_1D0], 208h
0x18008c440  mov     [rsp+240h+var_220], rax; unsigned __int16 *
0x18008c445  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18008c44a  test    eax, eax
0x18008c44c  cmovs   edi, eax
0x18008c44f  test    edi, edi
0x18008c451  js      short loc_18008C4B7
0x18008c453  mov     byte ptr [rbx], 1
0x18008c456  lea     rdi, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c45d  xor     eax, eax
0x18008c45f  mov     [rsp+240h+var_1D8], 208h
0x18008c468  mov     [r14], ax
0x18008c46c  lea     rdx, [rsp+240h+var_1D8]; unsigned __int64 *
0x18008c471  lea     rax, aWuserver; "WUServer"
0x18008c478  mov     r8d, 2; unsigned int
0x18008c47e  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18008c483  mov     rcx, r14; pvData
0x18008c486  lea     rax, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18008c48d  mov     [rsp+240h+var_220], rax; unsigned __int16 *
0x18008c492  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18008c497  xor     r14d, r14d
0x18008c49a  test    eax, eax
0x18008c49c  mov     ebx, r14d
0x18008c49f  cmovs   ebx, eax
0x18008c4a2  test    ebx, ebx
0x18008c4a4  js      loc_18008C62F
0x18008c4aa  mov     byte ptr [r15], 1
0x18008c4ae  lea     r15d, [r14+1]
0x18008c4b2  jmp     loc_18008C79E
0x18008c4b7  lea     eax, [rdi+7FF8FFFEh]
0x18008c4bd  cmp     eax, 1
0x18008c4c0  jbe     short loc_18008C456
0x18008c4c2  lea     rax, aErrorReadingIf_0; "Error reading if WU status server is se"...
0x18008c4c9  mov     dword ptr [rsp+240h+var_210], edi; char *
0x18008c4cd  mov     [rsp+240h+var_218], rax; int
0x18008c4d2  lea     r9, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c4d9  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c4e0  mov     dword ptr [rsp+240h+var_220], edi; char *
0x18008c4e4  mov     edx, 1DA6h; bool
0x18008c4e9  mov     ecx, 1; this
0x18008c4ee  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008c4f3  lea     rcx, [rbp+140h+var_160]; this
0x18008c4f7  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18008c4fc  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18008c503  lea     rcx, [rbp+140h+var_160]
0x18008c507  test    rax, rax
0x18008c50a  cmovnz  rcx, rax; this
0x18008c50e  xor     edx, edx
0x18008c510  lock xadd [rcx+88h], rdx; unsigned __int64
0x18008c519  lea     r8, [rbp+140h+var_D0]; char *
0x18008c51d  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18008c522  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18008c529  jz      short loc_18008C537
0x18008c52b  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18008c532  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18008c537  mov     rbx, cs:qword_1802C9628
0x18008c53e  mov     eax, [rbx]
0x18008c540  cmp     eax, 5
0x18008c543  jbe     loc_18008C620
0x18008c549  mov     rcx, [rbx+18h]
0x18008c54d  mov     rdx, 200000000000h
0x18008c557  mov     rax, [rbx+10h]
0x18008c55b  test    rdx, rax
0x18008c55e  jz      loc_18008C620
0x18008c564  mov     rax, rcx
0x18008c567  and     rax, rdx
0x18008c56a  cmp     rax, rcx
0x18008c56d  jnz     loc_18008C620
0x18008c573  lea     rax, [rbp+140h+var_D0]
0x18008c577  mov     [rsp+240h+var_1E0], edi
0x18008c57b  mov     [rbp+140h+var_1A0], rax
0x18008c57f  lea     rdi, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c586  lea     rax, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c58d  mov     [rbp+140h+var_198], rdi
0x18008c591  mov     [rsp+240h+var_1C8], rax
0x18008c596  lea     rcx, [rbp+140h+SystemTime]; lpSystemTime
0x18008c59a  lea     rax, szValueBuf
0x18008c5a1  mov     dword ptr [rsp+240h+var_1D0], 1DA6h
0x18008c5a9  xorps   xmm0, xmm0
0x18008c5ac  mov     [rbp+140h+var_1C0], rax
0x18008c5b0  movups  xmmword ptr [rbp+140h+SystemTime.wYear], xmm0
0x18008c5b4  call    cs:__imp_GetSystemTime
0x18008c5ba  movaps  xmm0, xmmword ptr [rbp+140h+SystemTime.wYear]
0x18008c5be  lea     rax, [rbp+140h+var_170]
0x18008c5c2  mov     [rsp+240h+var_1D8], rax
0x18008c5c7  lea     rdx, unk_1802A1BFD
0x18008c5ce  lea     rax, [rbp+140h+var_1A0]
0x18008c5d2  movdqa  [rbp+140h+var_170], xmm0
0x18008c5d7  mov     [rsp+240h+var_1F0], rax
0x18008c5dc  mov     rcx, rbx
0x18008c5df  lea     rax, [rsp+240h+var_1E0]
0x18008c5e4  mov     [rsp+240h+var_1F8], rax
0x18008c5e9  lea     rax, [rbp+140h+var_198]
0x18008c5ed  mov     [rsp+240h+var_200], rax
0x18008c5f2  lea     rax, [rsp+240h+var_1C8]
0x18008c5f7  mov     [rsp+240h+var_208], rax
0x18008c5fc  lea     rax, [rsp+240h+var_1D0]
0x18008c601  mov     [rsp+240h+var_210], rax
0x18008c606  lea     rax, [rbp+140h+var_1C0]
0x18008c60a  mov     [rsp+240h+var_218], rax
0x18008c60f  lea     rax, [rsp+240h+var_1D8]
0x18008c614  mov     [rsp+240h+var_220], rax
0x18008c619  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008c61e  jmp     short loc_18008C627
0x18008c620  lea     rdi, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c627  mov     byte ptr [rsi], 0
0x18008c62a  jmp     loc_18008C45D
0x18008c62f  lea     eax, [rbx+7FF8FFFEh]
0x18008c635  mov     r15d, 1
0x18008c63b  cmp     eax, r15d
0x18008c63e  jbe     loc_18008C79E
0x18008c644  lea     rax, aErrorReadingIf_4; "Error reading if WU server is set, swal"...
0x18008c64b  mov     dword ptr [rsp+240h+var_210], ebx; char *
0x18008c64f  mov     [rsp+240h+var_218], rax; int
0x18008c654  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c65b  mov     r9, rdi; char *
0x18008c65e  mov     dword ptr [rsp+240h+var_220], ebx; char *
0x18008c662  mov     edx, 1DB4h; bool
0x18008c667  mov     ecx, r15d; this
0x18008c66a  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008c66f  lea     rcx, [rbp+140h+var_160]; this
0x18008c673  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18008c678  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18008c67f  lea     rcx, [rbp+140h+var_160]
0x18008c683  test    rax, rax
0x18008c686  mov     rdx, r14
0x18008c689  cmovnz  rcx, rax; this
0x18008c68d  lock xadd [rcx+88h], rdx; unsigned __int64
0x18008c696  lea     r8, [rbp+140h+var_D0]; char *
0x18008c69a  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18008c69f  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r14b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18008c6a6  jz      short loc_18008C6B4
0x18008c6a8  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18008c6af  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18008c6b4  mov     rdi, cs:qword_1802C9628
0x18008c6bb  mov     eax, [rdi]
0x18008c6bd  cmp     eax, 5
0x18008c6c0  jbe     loc_18008C79B
0x18008c6c6  mov     rcx, [rdi+18h]
0x18008c6ca  mov     rdx, 200000000000h
0x18008c6d4  mov     rax, [rdi+10h]
0x18008c6d8  test    rdx, rax
0x18008c6db  jz      loc_18008C79B
0x18008c6e1  mov     rax, rcx
0x18008c6e4  and     rax, rdx
0x18008c6e7  cmp     rax, rcx
0x18008c6ea  jnz     loc_18008C79B
0x18008c6f0  lea     rax, [rbp+140h+var_D0]
0x18008c6f4  mov     dword ptr [rsp+240h+var_1D0], ebx
0x18008c6f8  mov     [rsp+240h+var_1D8], rax
0x18008c6fd  lea     rcx, [rbp+140h+SystemTime]; lpSystemTime
0x18008c701  lea     rax, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c708  mov     [rsp+240h+var_1E0], 1DB4h
0x18008c710  mov     [rbp+140h+var_1C0], rax
0x18008c714  xorps   xmm0, xmm0
0x18008c717  lea     rax, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c71e  mov     [rsp+240h+var_1C8], rax
0x18008c723  lea     rax, szValueBuf
0x18008c72a  mov     [rbp+140h+var_198], rax
0x18008c72e  movups  xmmword ptr [rbp+140h+SystemTime.wYear], xmm0
0x18008c732  call    cs:__imp_GetSystemTime
0x18008c738  movaps  xmm0, xmmword ptr [rbp+140h+SystemTime.wYear]
0x18008c73c  lea     rax, [rbp+140h+var_170]
0x18008c740  mov     [rbp+140h+var_1A0], rax
0x18008c744  lea     rdx, unk_1802A1CC3
0x18008c74b  lea     rax, [rsp+240h+var_1D8]
0x18008c750  movdqa  [rbp+140h+var_170], xmm0
0x18008c755  mov     [rsp+240h+var_1F0], rax
0x18008c75a  mov     rcx, rdi
0x18008c75d  lea     rax, [rsp+240h+var_1D0]
0x18008c762  mov     [rsp+240h+var_1F8], rax
0x18008c767  lea     rax, [rbp+140h+var_1C0]
0x18008c76b  mov     [rsp+240h+var_200], rax
0x18008c770  lea     rax, [rsp+240h+var_1C8]
0x18008c775  mov     [rsp+240h+var_208], rax
0x18008c77a  lea     rax, [rsp+240h+var_1E0]
0x18008c77f  mov     [rsp+240h+var_210], rax
0x18008c784  lea     rax, [rbp+140h+var_198]
0x18008c788  mov     [rsp+240h+var_218], rax
0x18008c78d  lea     rax, [rbp+140h+var_1A0]
0x18008c791  mov     [rsp+240h+var_220], rax
0x18008c796  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18008c79b  mov     [rsi], r14b
0x18008c79e  lea     rax, aUsewuserver; "UseWUServer"
0x18008c7a5  mov     [r12], r14d
0x18008c7a9  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18008c7ae  lea     rdx, [rsp+240h+var_1D8]; unsigned __int64 *
0x18008c7b3  lea     rax, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\Windows"...
0x18008c7ba  mov     [rsp+240h+var_1D8], 4
0x18008c7c3  mov     r8d, 10h; unsigned int
0x18008c7c9  mov     [rsp+240h+var_220], rax; unsigned __int16 *
0x18008c7ce  mov     rcx, r12; pvData
0x18008c7d1  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18008c7d6  mov     edi, eax
0x18008c7d8  test    eax, eax
0x18008c7da  js      short loc_18008C83A
0x18008c7dc  mov     [r13+0], r15b
0x18008c7e0  lea     r12, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c7e7  lea     r13, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c7ee  mov     rcx, [rbp+140h+var_1B8]; pvData
0x18008c7f2  lea     rax, aDonotconnectto_0; "DoNotConnectToWindowsUpdateInternetLoca"...
0x18008c7f9  mov     [rsp+240h+var_218], rax; unsigned __int16 *
0x18008c7fe  lea     rdx, [rbp+140h+var_1B8]; unsigned __int64 *
0x18008c802  lea     rax, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\Windows"...
0x18008c809  mov     [rbp+140h+var_1B8], 4
0x18008c811  mov     r8d, 10h; unsigned int
0x18008c817  mov     [rsp+240h+var_220], rax; unsigned __int16 *
0x18008c81c  mov     [rcx], r14d
0x18008c81f  call    ?ReadValue@Registry@Shared@Compat@Windows@@SAJPEAEAEA_KKPEAUHKEY__@@PEBG3@Z; Windows::Compat::Shared::Registry::ReadValue(uchar *,unsigned __int64 &,ulong,HKEY__ *,ushort const *,ushort const *)
0x18008c824  mov     edi, eax
0x18008c826  test    eax, eax
0x18008c828  js      loc_18008C99F
0x18008c82e  mov     rax, [rbp+140h+var_190]
0x18008c832  mov     [rax], r15b
0x18008c835  jmp     loc_18008CAF5
0x18008c83a  add     eax, 7FF8FFFEh
0x18008c83f  cmp     eax, r15d
0x18008c842  jbe     short loc_18008C7E0
0x18008c844  lea     rax, aErrorReadingIf_2; "Error reading if use WU server is set, "...
0x18008c84b  mov     dword ptr [rsp+240h+var_210], edi; char *
0x18008c84f  mov     [rsp+240h+var_218], rax; int
0x18008c854  lea     r13, aWindowsCompatA_155; "Windows::Compat::Appraiser::Utilities::"...
0x18008c85b  lea     r12, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x18008c862  mov     dword ptr [rsp+240h+var_220], edi; char *
0x18008c866  mov     r9, r13; char *
0x18008c869  mov     r8, r12; unsigned int
0x18008c86c  mov     edx, 1DC1h; bool
0x18008c871  mov     ecx, r15d; this
0x18008c874  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18008c879  lea     rcx, [rbp+140h+var_160]; this
0x18008c87d  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18008c882  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18008c889  lea     rcx, [rbp+140h+var_160]
0x18008c88d  test    rax, rax
0x18008c890  mov     rdx, r14
0x18008c893  cmovnz  rcx, rax; this
0x18008c897  lock xadd [rcx+88h], rdx; unsigned __int64
0x18008c8a0  lea     r8, [rbp+140h+var_D0]; char *
0x18008c8a4  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18008c8a9  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r14b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x18008c8b0  jz      short loc_18008C8BE
0x18008c8b2  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x18008c8b9  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x18008c8be  mov     rbx, cs:qword_1802C9628
0x18008c8c5  mov     eax, [rbx]
0x18008c8c7  cmp     eax, 5
0x18008c8ca  jbe     loc_18008C997
0x18008c8d0  mov     rcx, [rbx+18h]
0x18008c8d4  mov     rdx, 200000000000h
0x18008c8de  mov     rax, [rbx+10h]
0x18008c8e2  test    rdx, rax
0x18008c8e5  jz      loc_18008C997
0x18008c8eb  mov     rax, rcx
0x18008c8ee  and     rax, rdx
0x18008c8f1  cmp     rax, rcx
0x18008c8f4  jnz     loc_18008C997
  ... truncated ...
```
