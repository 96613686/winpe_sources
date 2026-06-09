# Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun(Windows::Compat::Appraiser::WicaRun *)

- ea: `0x180061e90`
- end: `0x1800629ae`
- name: `?CleanupWicaRun@XmlAppraiser@Appraiser@Compat@Windows@@CAJPEAUWicaRun@234@@Z`
- size: `2846`
- prototype: `__int64 __fastcall(struct Windows::Compat::Appraiser::WicaRun *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180064f4c`

## callees

- `0x18000147c`
- `0x180008570`
- `0x180008a1c`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180061e90`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x18006203b`
- `KERNEL32!GetSystemTime` at `0x18006223e`
- `KERNEL32!GetSystemTime` at `0x180062436`
- `KERNEL32!GetSystemTime` at `0x180062632`
- `KERNEL32!GetSystemTime` at `0x18006282e`
- `KERNEL32!GetSystemTime` at `0x18006203b`
- `KERNEL32!GetSystemTime` at `0x18006223e`
- `KERNEL32!GetSystemTime` at `0x180062436`
- `KERNEL32!GetSystemTime` at `0x180062632`
- `KERNEL32!GetSystemTime` at `0x18006282e`
- `KERNEL32!GetProcessHeap` at `0x18006296e`
- `KERNEL32!GetProcessHeap` at `0x18006296e`
- `KERNEL32!HeapFree` at `0x18006297c`
- `KERNEL32!HeapFree` at `0x18006297c`

## string_xrefs

- `0x180061f53`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062020`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062118`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062157`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062222`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800622c6`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062361`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006241a`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800624c5`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x18006255d`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062616`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800626c1`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062759`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180062812`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800628bd`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180061f08`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x18006200c`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x1800620a5`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x180062129`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x18006220f`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x18006234b`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x180062407`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x1800624bb`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x180062547`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x180062603`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x1800626b7`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x180062743`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x1800627ff`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`
- `0x1800628b3`: `Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun(
        struct Windows::Compat::Appraiser::WicaRun *a1)
{
  unsigned int v2; // edi
  unsigned __int64 i; // rsi
  void (__fastcall ***v4)(_QWORD); // rcx
  unsigned __int64 j; // rsi
  __int64 v6; // rcx
  int v7; // eax
  int v8; // r15d
  volatile signed __int64 *v9; // rcx
  void **v10; // rdx
  int v11; // r14d
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rcx
  unsigned __int64 k; // rsi
  __int64 v16; // rcx
  int v17; // eax
  int v18; // r15d
  volatile signed __int64 *v19; // rcx
  void **v20; // rdx
  int v21; // r14d
  int v22; // r8d
  int v23; // r9d
  __int64 v24; // rcx
  unsigned __int64 m; // rsi
  __int64 v26; // rcx
  int v27; // eax
  int v28; // r15d
  volatile signed __int64 *v29; // rcx
  void **v30; // rdx
  int v31; // r14d
  int v32; // r8d
  int v33; // r9d
  __int64 v34; // rcx
  unsigned __int64 n; // rsi
  __int64 v36; // rcx
  int v37; // eax
  int v38; // r15d
  volatile signed __int64 *v39; // rcx
  void **v40; // rdx
  int v41; // r14d
  int v42; // r8d
  int v43; // r9d
  __int64 v44; // rcx
  unsigned __int64 ii; // rsi
  __int64 v46; // rcx
  int v47; // eax
  int v48; // r15d
  volatile signed __int64 *v49; // rcx
  void **v50; // rdx
  int v51; // r14d
  int v52; // r8d
  int v53; // r9d
  __int64 v54; // rcx
  void *v55; // rcx
  void *v56; // rcx
  void *v57; // rcx
  void *v58; // rcx
  void *v59; // rcx
  void *v60; // rdi
  HANDLE ProcessHeap; // rax
  char *v63; // [rsp+20h] [rbp-E0h]
  char *v64; // [rsp+30h] [rbp-D0h]
  int v65; // [rsp+60h] [rbp-A0h] BYREF
  int v66; // [rsp+64h] [rbp-9Ch] BYREF
  char *v67; // [rsp+68h] [rbp-98h] BYREF
  const char *v68; // [rsp+70h] [rbp-90h] BYREF
  const char *v69; // [rsp+78h] [rbp-88h] BYREF
  const char *v70; // [rsp+80h] [rbp-80h] BYREF
  char *v71; // [rsp+88h] [rbp-78h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  struct _SYSTEMTIME v73; // [rsp+A0h] [rbp-60h] BYREF
  char v74[144]; // [rsp+B0h] [rbp-50h] BYREF
  char v75[144]; // [rsp+140h] [rbp+40h] BYREF

  v2 = 1;
  if ( a1 )
  {
    if ( *(_QWORD *)a1 )
    {
      for ( i = 0; i < *((unsigned int *)a1 + 16); ++i )
      {
        v4 = *(void (__fastcall ****)(_QWORD))(*(_QWORD *)a1 + 8 * i);
        if ( v4 )
        {
          (**v4)(v4);
          *(_QWORD *)(*(_QWORD *)a1 + 8 * i) = 0;
        }
      }
    }
    if ( *((_QWORD *)a1 + 1) )
    {
      for ( j = 0; j < *((unsigned int *)a1 + 17); ++j )
      {
        v6 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * j) + 8LL;
        v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
        v8 = v7;
        if ( v7 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x18Fu,
              "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
              "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
              "Error Uninitializing: [0x%x].",
              v7);
        }
        else
        {
          LODWORD(v64) = v7;
          LODWORD(v63) = v7;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            143,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
            v63,
            (int)"Error Uninitializing: [0x%x].",
            v64);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
          v9 = (volatile signed __int64 *)v74;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v9 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v9,
            _InterlockedExchangeAdd64(v9 + 17, 0),
            v75);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v10);
          v11 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v65 = v8;
            v67 = v75;
            v66 = 399;
            v68 = "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun";
            v69 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
            v70 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v71 = (char *)&v73;
            v73 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v11,
              (unsigned int)&unk_1802A16F6,
              v12,
              v13,
              (__int64)&v71,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v69,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v67);
          }
        }
        v14 = *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * j);
        if ( v14 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 8LL))(v14, 1);
          *(_QWORD *)(*((_QWORD *)a1 + 1) + 8 * j) = 0;
        }
      }
    }
    if ( *((_QWORD *)a1 + 2) )
    {
      for ( k = 0; k < *((unsigned int *)a1 + 18); ++k )
      {
        v16 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 8 * k) + 8LL;
        v17 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        v18 = v17;
        if ( v17 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x19Eu,
              "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
              "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
              "Error Uninitializing: [0x%x].",
              v17);
        }
        else
        {
          LODWORD(v64) = v17;
          LODWORD(v63) = v17;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            158,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
            v63,
            (int)"Error Uninitializing: [0x%x].",
            v64);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
          v19 = (volatile signed __int64 *)v74;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v19 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v19,
            _InterlockedExchangeAdd64(v19 + 17, 0),
            v75);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v20);
          v21 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v66 = v18;
            v71 = v75;
            v65 = 414;
            v70 = "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun";
            v69 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
            v68 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v67 = (char *)&v73;
            v73 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v21,
              (unsigned int)&unk_1802A1693,
              v22,
              v23,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v69,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v71);
          }
        }
        v24 = *(_QWORD *)(*((_QWORD *)a1 + 2) + 8 * k);
        if ( v24 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v24 + 8LL))(v24, 1);
          *(_QWORD *)(*((_QWORD *)a1 + 2) + 8 * k) = 0;
        }
      }
    }
    if ( *((_QWORD *)a1 + 3) )
    {
      for ( m = 0; m < *((unsigned int *)a1 + 19); ++m )
      {
        v26 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 8 * m) + 8LL;
        v27 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v26 + 8LL))(v26);
        v28 = v27;
        if ( v27 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1ADu,
              "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
              "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
              "Error Uninitializing: [0x%x].",
              v27);
        }
        else
        {
          LODWORD(v64) = v27;
          LODWORD(v63) = v27;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            173,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
            v63,
            (int)"Error Uninitializing: [0x%x].",
            v64);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
          v29 = (volatile signed __int64 *)v74;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v29 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v29,
            _InterlockedExchangeAdd64(v29 + 17, 0),
            v75);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v30);
          v31 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v66 = v28;
            v71 = v75;
            v65 = 429;
            v70 = "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun";
            v69 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
            v68 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v67 = (char *)&v73;
            v73 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v31,
              (unsigned int)&unk_1802A1630,
              v32,
              v33,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v69,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v71);
          }
        }
        v34 = *(_QWORD *)(*((_QWORD *)a1 + 3) + 8 * m);
        if ( v34 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v34 + 8LL))(v34, 1);
          *(_QWORD *)(*((_QWORD *)a1 + 3) + 8 * m) = 0;
        }
      }
    }
    if ( *((_QWORD *)a1 + 4) )
    {
      for ( n = 0; n < *((unsigned int *)a1 + 20); ++n )
      {
        v36 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * n) + 8LL;
        v37 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
        v38 = v37;
        if ( v37 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1BCu,
              "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
              "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
              "Error Uninitializing: [0x%x].",
              v37);
        }
        else
        {
          LODWORD(v64) = v37;
          LODWORD(v63) = v37;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            188,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
            v63,
            (int)"Error Uninitializing: [0x%x].",
            v64);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
          v39 = (volatile signed __int64 *)v74;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v39 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v39,
            _InterlockedExchangeAdd64(v39 + 17, 0),
            v75);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v40);
          v41 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v66 = v38;
            v71 = v75;
            v65 = 444;
            v70 = "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun";
            v69 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
            v68 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v67 = (char *)&v73;
            v73 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v41,
              (unsigned int)&unk_1802A15CD,
              v42,
              v43,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v69,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v71);
          }
        }
        v44 = *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * n);
        if ( v44 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v44 + 8LL))(v44, 1);
          *(_QWORD *)(*((_QWORD *)a1 + 4) + 8 * n) = 0;
        }
      }
    }
    if ( *((_QWORD *)a1 + 5) )
    {
      for ( ii = 0; ii < *((unsigned int *)a1 + 21); ++ii )
      {
        v46 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 8 * ii) + 8LL;
        v47 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v46 + 8LL))(v46);
        v48 = v47;
        if ( v47 >= 0 )
        {
          if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
            Windows::Compat::Appraiser::WicaFactory::RunPrintf(
              0x1CBu,
              "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
              "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
              "Error Uninitializing: [0x%x].",
              v47);
        }
        else
        {
          LODWORD(v64) = v47;
          LODWORD(v63) = v47;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            203,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun",
            v63,
            (int)"Error Uninitializing: [0x%x].",
            v64);
          TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v74);
          v49 = (volatile signed __int64 *)v74;
          if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
            v49 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
          TraceLoggingCorrelationVector::ToStringImpl(
            (TraceLoggingCorrelationVector *)v49,
            _InterlockedExchangeAdd64(v49 + 17, 0),
            v75);
          if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
            UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v50);
          v51 = qword_1802C9628;
          if ( *(_DWORD *)qword_1802C9628 > 5u
            && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
            && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
          {
            v66 = v48;
            v71 = v75;
            v65 = 459;
            v70 = "Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun";
            v69 = "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
            v68 = (const char *)&szValueBuf;
            SystemTime = 0;
            GetSystemTime(&SystemTime);
            v67 = (char *)&v73;
            v73 = SystemTime;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v51,
              (unsigned int)&unk_1802A156A,
              v52,
              v53,
              (__int64)&v67,
              (__int64)&v68,
              (__int64)&v65,
              (__int64)&v69,
              (__int64)&v70,
              (__int64)&v66,
              (__int64)&v71);
          }
        }
        v54 = *(_QWORD *)(*((_QWORD *)a1 + 5) + 8 * ii);
        if ( v54 )
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 8LL))(v54, 1);
          *(_QWORD *)(*((_QWORD *)a1 + 5) + 8 * ii) = 0;
        }
      }
    }
    if ( *(_QWORD *)a1 )
    {
      operator delete(*(void **)a1);
      *(_QWORD *)a1 = 0;
    }
    v55 = (void *)*((_QWORD *)a1 + 1);
    if ( v55 )
    {
      operator delete(v55);
      *((_QWORD *)a1 + 1) = 0;
    }
    v56 = (void *)*((_QWORD *)a1 + 2);
    if ( v56 )
    {
      operator delete(v56);
      *((_QWORD *)a1 + 2) = 0;
    }
    v57 = (void *)*((_QWORD *)a1 + 3);
    if ( v57 )
    {
      operator delete(v57);
      *((_QWORD *)a1 + 3) = 0;
    }
    v58 = (void *)*((_QWORD *)a1 + 4);
    if ( v58 )
    {
      operator delete(v58);
      *((_QWORD *)a1 + 4) = 0;
    }
    v59 = (void *)*((_QWORD *)a1 + 5);
    if ( v59 )
    {
      operator delete(v59);
      *((_QWORD *)a1 + 5) = 0;
    }
    v60 = (void *)*((_QWORD *)a1 + 6);
    if ( v60 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v60);
      *((_QWORD *)a1 + 6) = 0;
    }
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180061e90  push    rbp
0x180061e92  push    rbx
0x180061e93  push    rsi
0x180061e94  push    rdi
0x180061e95  push    r12
0x180061e97  push    r13
0x180061e99  push    r14
0x180061e9b  push    r15
0x180061e9d  lea     rbp, [rsp-0E8h]
0x180061ea5  sub     rsp, 1E8h
0x180061eac  mov     rax, cs:__security_cookie
0x180061eb3  xor     rax, rsp
0x180061eb6  mov     [rbp+120h+var_50], rax
0x180061ebd  xor     r12d, r12d
0x180061ec0  mov     rbx, rcx
0x180061ec3  mov     edi, 1
0x180061ec8  test    rcx, rcx
0x180061ecb  jz      loc_180062989
0x180061ed1  cmp     [rcx], r12
0x180061ed4  jz      short loc_180061F08
0x180061ed6  mov     esi, r12d
0x180061ed9  cmp     [rcx+40h], r12d
0x180061edd  jbe     short loc_180061F08
0x180061edf  mov     rax, [rbx]
0x180061ee2  mov     rcx, [rax+rsi*8]
0x180061ee6  test    rcx, rcx
0x180061ee9  jz      short loc_180061EFD
0x180061eeb  mov     rax, [rcx]
0x180061eee  mov     rax, [rax]
0x180061ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061ef6  mov     rax, [rbx]
0x180061ef9  mov     [rax+rsi*8], r12
0x180061efd  mov     eax, [rbx+40h]
0x180061f00  add     rsi, rdi
0x180061f03  cmp     rsi, rax
0x180061f06  jb      short loc_180061EDF
0x180061f08  lea     r14, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x180061f0f  cmp     [rbx+8], r12
0x180061f13  jz      loc_1800620DE
0x180061f19  mov     rsi, r12
0x180061f1c  cmp     [rbx+44h], r12d
0x180061f20  jbe     loc_1800620DE
0x180061f26  mov     r13d, 18Fh
0x180061f2c  mov     rax, [rbx+8]
0x180061f30  mov     rcx, [rax+rsi*8]
0x180061f34  add     rcx, 8
0x180061f38  mov     rax, [rcx]
0x180061f3b  mov     rax, [rax+8]
0x180061f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061f44  mov     r15d, eax
0x180061f47  test    eax, eax
0x180061f49  jns     loc_1800620FD
0x180061f4f  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x180061f53  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180061f5a  lea     rax, aErrorUninitial_4; "Error Uninitializing: [0x%x]."
0x180061f61  mov     r9, r14; char *
0x180061f64  mov     qword ptr [rsp+220h+var_1F8], rax; int
0x180061f69  mov     edx, r13d; bool
0x180061f6c  mov     ecx, edi; this
0x180061f6e  mov     dword ptr [rsp+220h+var_200], r15d; char *
0x180061f73  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180061f78  lea     rcx, [rbp+120h+var_170]; this
0x180061f7c  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180061f81  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180061f88  lea     rcx, [rbp+120h+var_170]
0x180061f8c  test    rax, rax
0x180061f8f  mov     rdx, r12
0x180061f92  cmovnz  rcx, rax; this
0x180061f96  lock xadd [rcx+88h], rdx; unsigned __int64
0x180061f9f  lea     r8, [rbp+120h+var_E0]; char *
0x180061fa3  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180061fa8  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180061faf  jz      short loc_180061FBD
0x180061fb1  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180061fb8  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180061fbd  mov     r14, cs:qword_1802C9628
0x180061fc4  mov     eax, [r14]
0x180061fc7  cmp     eax, 5
0x180061fca  jbe     loc_1800620A5
0x180061fd0  mov     rcx, [r14+18h]
0x180061fd4  mov     rdx, 200000000000h
0x180061fde  mov     rax, [r14+10h]
0x180061fe2  test    rdx, rax
0x180061fe5  jz      loc_1800620A5
0x180061feb  mov     rax, rcx
0x180061fee  and     rax, rdx
0x180061ff1  cmp     rax, rcx
0x180061ff4  jnz     loc_1800620A5
0x180061ffa  lea     rax, [rbp+120h+var_E0]
0x180061ffe  mov     [rsp+220h+var_1C0], r15d
0x180062003  mov     [rsp+220h+var_1B8], rax
0x180062008  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x18006200c  lea     rax, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x180062013  mov     [rsp+220h+var_1BC], r13d
0x180062018  mov     [rsp+220h+var_1B0], rax
0x18006201d  xorps   xmm0, xmm0
0x180062020  lea     rax, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180062027  mov     [rsp+220h+var_1A8], rax
0x18006202c  lea     rax, szValueBuf
0x180062033  mov     [rbp+120h+var_1A0], rax
0x180062037  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x18006203b  call    cs:__imp_GetSystemTime
0x180062041  movaps  xmm0, xmmword ptr [rbp+120h+SystemTime.wYear]
0x180062045  lea     rax, [rbp+120h+var_180]
0x180062049  mov     [rbp+120h+var_198], rax
0x18006204d  lea     rdx, unk_1802A16F6
0x180062054  lea     rax, [rsp+220h+var_1B8]
0x180062059  movdqa  [rbp+120h+var_180], xmm0
0x18006205e  mov     [rsp+220h+var_1D0], rax
0x180062063  mov     rcx, r14
0x180062066  lea     rax, [rsp+220h+var_1C0]
0x18006206b  mov     [rsp+220h+var_1D8], rax
0x180062070  lea     rax, [rsp+220h+var_1B0]
0x180062075  mov     [rsp+220h+var_1E0], rax
0x18006207a  lea     rax, [rsp+220h+var_1A8]
0x18006207f  mov     [rsp+220h+var_1E8], rax
0x180062084  lea     rax, [rsp+220h+var_1BC]
0x180062089  mov     [rsp+220h+var_1F0], rax
0x18006208e  lea     rax, [rbp+120h+var_1A0]
0x180062092  mov     qword ptr [rsp+220h+var_1F8], rax
0x180062097  lea     rax, [rbp+120h+var_198]
0x18006209b  mov     [rsp+220h+var_200], rax
0x1800620a0  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800620a5  lea     r14, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800620ac  mov     rax, [rbx+8]
0x1800620b0  mov     rcx, [rax+rsi*8]
0x1800620b4  test    rcx, rcx
0x1800620b7  jz      short loc_1800620CF
0x1800620b9  mov     rax, [rcx]
0x1800620bc  mov     edx, edi
0x1800620be  mov     rax, [rax+8]
0x1800620c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800620c7  mov     rax, [rbx+8]
0x1800620cb  mov     [rax+rsi*8], r12
0x1800620cf  mov     eax, [rbx+44h]
0x1800620d2  add     rsi, rdi
0x1800620d5  cmp     rsi, rax
0x1800620d8  jb      loc_180061F2C
0x1800620de  cmp     [rbx+10h], r12
0x1800620e2  jz      loc_180062307
0x1800620e8  mov     rsi, r12
0x1800620eb  cmp     [rbx+48h], r12d
0x1800620ef  jbe     loc_180062307
0x1800620f5  mov     r13d, 19Eh
0x1800620fb  jmp     short loc_180062130
0x1800620fd  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180062103  and     eax, edi
0x180062105  test    al, al
0x180062107  jz      short loc_1800620AC
0x180062109  lea     r9, aErrorUninitial_4; "Error Uninitializing: [0x%x]."
0x180062110  mov     dword ptr [rsp+220h+var_200], r15d
0x180062115  mov     r8, r14; char *
0x180062118  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006211f  mov     ecx, r13d; unsigned int
0x180062122  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180062127  jmp     short loc_1800620AC
0x180062129  lea     r14, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x180062130  mov     rax, [rbx+10h]
0x180062134  mov     rcx, [rax+rsi*8]
0x180062138  add     rcx, 8
0x18006213c  mov     rax, [rcx]
0x18006213f  mov     rax, [rax+8]
0x180062143  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062148  mov     r15d, eax
0x18006214b  test    eax, eax
0x18006214d  jns     loc_1800622AB
0x180062153  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x180062157  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x18006215e  lea     rax, aErrorUninitial_4; "Error Uninitializing: [0x%x]."
0x180062165  mov     r9, r14; char *
0x180062168  mov     qword ptr [rsp+220h+var_1F8], rax; int
0x18006216d  mov     edx, r13d; bool
0x180062170  mov     ecx, edi; this
0x180062172  mov     dword ptr [rsp+220h+var_200], r15d; char *
0x180062177  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x18006217c  lea     rcx, [rbp+120h+var_170]; this
0x180062180  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180062185  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x18006218c  lea     rcx, [rbp+120h+var_170]
0x180062190  test    rax, rax
0x180062193  mov     rdx, r12
0x180062196  cmovnz  rcx, rax; this
0x18006219a  lock xadd [rcx+88h], rdx; unsigned __int64
0x1800621a3  lea     r8, [rbp+120h+var_E0]; char *
0x1800621a7  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800621ac  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800621b3  jz      short loc_1800621C1
0x1800621b5  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800621bc  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x1800621c1  mov     r14, cs:qword_1802C9628
0x1800621c8  mov     eax, [r14]
0x1800621cb  cmp     eax, 5
0x1800621ce  jbe     loc_1800622D5
0x1800621d4  mov     rcx, [r14+18h]
0x1800621d8  mov     rdx, 200000000000h
0x1800621e2  mov     rax, [r14+10h]
0x1800621e6  test    rdx, rax
0x1800621e9  jz      loc_1800622D5
0x1800621ef  mov     rax, rcx
0x1800621f2  and     rax, rdx
0x1800621f5  cmp     rax, rcx
0x1800621f8  jnz     loc_1800622D5
0x1800621fe  lea     rax, [rbp+120h+var_E0]
0x180062202  mov     [rsp+220h+var_1BC], r15d
0x180062207  mov     [rbp+120h+var_198], rax
0x18006220b  lea     rcx, [rbp+120h+SystemTime]; lpSystemTime
0x18006220f  lea     rax, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x180062216  mov     [rsp+220h+var_1C0], r13d
0x18006221b  mov     [rbp+120h+var_1A0], rax
0x18006221f  xorps   xmm0, xmm0
0x180062222  lea     rax, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180062229  mov     [rsp+220h+var_1A8], rax
0x18006222e  lea     rax, szValueBuf
0x180062235  mov     [rsp+220h+var_1B0], rax
0x18006223a  movups  xmmword ptr [rbp+120h+SystemTime.wYear], xmm0
0x18006223e  call    cs:__imp_GetSystemTime
0x180062244  movaps  xmm0, xmmword ptr [rbp+120h+SystemTime.wYear]
0x180062248  lea     rax, [rbp+120h+var_180]
0x18006224c  mov     [rsp+220h+var_1B8], rax
0x180062251  lea     rdx, unk_1802A1693
0x180062258  lea     rax, [rbp+120h+var_198]
0x18006225c  movdqa  [rbp+120h+var_180], xmm0
0x180062261  mov     [rsp+220h+var_1D0], rax
0x180062266  mov     rcx, r14
0x180062269  lea     rax, [rsp+220h+var_1BC]
0x18006226e  mov     [rsp+220h+var_1D8], rax
0x180062273  lea     rax, [rbp+120h+var_1A0]
0x180062277  mov     [rsp+220h+var_1E0], rax
0x18006227c  lea     rax, [rsp+220h+var_1A8]
0x180062281  mov     [rsp+220h+var_1E8], rax
0x180062286  lea     rax, [rsp+220h+var_1C0]
0x18006228b  mov     [rsp+220h+var_1F0], rax
0x180062290  lea     rax, [rsp+220h+var_1B0]
0x180062295  mov     qword ptr [rsp+220h+var_1F8], rax
0x18006229a  lea     rax, [rsp+220h+var_1B8]
0x18006229f  mov     [rsp+220h+var_200], rax
0x1800622a4  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800622a9  jmp     short loc_1800622D5
0x1800622ab  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800622b1  and     eax, edi
0x1800622b3  test    al, al
0x1800622b5  jz      short loc_1800622D5
0x1800622b7  lea     r9, aErrorUninitial_4; "Error Uninitializing: [0x%x]."
0x1800622be  mov     dword ptr [rsp+220h+var_200], r15d
0x1800622c3  mov     r8, r14; char *
0x1800622c6  lea     rdx, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800622cd  mov     ecx, r13d; unsigned int
0x1800622d0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800622d5  mov     rax, [rbx+10h]
0x1800622d9  mov     rcx, [rax+rsi*8]
0x1800622dd  test    rcx, rcx
0x1800622e0  jz      short loc_1800622F8
0x1800622e2  mov     rax, [rcx]
0x1800622e5  mov     edx, edi
0x1800622e7  mov     rax, [rax+8]
0x1800622eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800622f0  mov     rax, [rbx+10h]
0x1800622f4  mov     [rax+rsi*8], r12
0x1800622f8  mov     eax, [rbx+48h]
0x1800622fb  add     rsi, rdi
0x1800622fe  cmp     rsi, rax
0x180062301  jb      loc_180062129
0x180062307  cmp     [rbx+18h], r12
0x18006230b  jz      loc_180062503
0x180062311  mov     rsi, r12
0x180062314  cmp     [rbx+4Ch], r12d
0x180062318  jbe     loc_180062503
0x18006231e  mov     r13d, 1ADh
0x180062324  mov     rax, [rbx+18h]
0x180062328  mov     rcx, [rax+rsi*8]
0x18006232c  add     rcx, 8
0x180062330  mov     rax, [rcx]
0x180062333  mov     rax, [rax+8]
0x180062337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006233c  mov     r15d, eax
0x18006233f  test    eax, eax
0x180062341  jns     loc_1800624A3
0x180062347  mov     dword ptr [rsp+220h+var_1F0], eax; char *
0x18006234b  lea     r9, aWindowsCompatA_69; "Windows::Compat::Appraiser::XmlAppraise"...
0x180062352  lea     rax, aErrorUninitial_4; "Error Uninitializing: [0x%x]."
0x180062359  mov     edx, r13d; bool
0x18006235c  mov     qword ptr [rsp+220h+var_1F8], rax; int
0x180062361  lea     r8, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180062368  mov     ecx, edi; this
0x18006236a  mov     dword ptr [rsp+220h+var_200], r15d; char *
0x18006236f  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180062374  lea     rcx, [rbp+120h+var_170]; this
0x180062378  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x18006237d  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180062384  lea     rcx, [rbp+120h+var_170]
0x180062388  test    rax, rax
0x18006238b  mov     rdx, r12
0x18006238e  cmovnz  rcx, rax; this
0x180062392  lock xadd [rcx+88h], rdx; unsigned __int64
0x18006239b  lea     r8, [rbp+120h+var_E0]; char *
0x18006239f  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x1800623a4  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, r12b; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x1800623ab  jz      short loc_1800623B9
0x1800623ad  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x1800623b4  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
  ... truncated ...
```
