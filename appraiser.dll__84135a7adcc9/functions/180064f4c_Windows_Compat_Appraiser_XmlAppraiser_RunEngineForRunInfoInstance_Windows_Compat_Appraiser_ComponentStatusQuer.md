# Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance(Windows::Compat::Appraiser::ComponentStatusQuery *,unsigned __int64)

- ea: `0x180064f4c`
- end: `0x180066305`
- name: `?RunEngineForRunInfoInstance@XmlAppraiser@Appraiser@Compat@Windows@@AEAAJPEAVComponentStatusQuery@234@_K@Z`
- size: `5049`
- prototype: `__int64 __fastcall(Windows::Compat::Appraiser::XmlAppraiser *__hidden this, struct Windows::Compat::Appraiser::ComponentStatusQuery *, unsigned __int64)`
- caller_count: `1`
- callee_count: `30`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180064cd4`

## callees

- `0x18000147c`
- `0x180001990`
- `0x180008570`
- `0x1800092dc`
- `0x18000a5b8`
- `0x180011d94`
- `0x180013c7c`
- `0x1800151f4`
- `0x180029258`
- `0x18002a8b4`
- `0x18002b894`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180061e90`
- `0x180063c20`
- `0x180064f4c`
- `0x180066bec`
- `0x180081774`
- `0x180088980`
- `0x180088c0c`
- `0x1800a7ff0`
- `0x1800a8050`
- `0x1801b0af0`
- `0x1801b36a4`
- `0x1801fb6a4`
- `0x1801fb8d0`
- `0x1801fd54c`
- `0x1801fd7e0`
- `0x1802174cc`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetSystemTime` at `0x1800653f8`
- `KERNEL32!GetSystemTime` at `0x1800657b1`
- `KERNEL32!GetSystemTime` at `0x180065b15`
- `KERNEL32!GetSystemTime` at `0x180065d03`
- `KERNEL32!GetSystemTime` at `0x180065e8f`
- `KERNEL32!GetSystemTime` at `0x180066051`
- `KERNEL32!GetSystemTime` at `0x1800661d9`
- `KERNEL32!GetSystemTime` at `0x1800653f8`
- `KERNEL32!GetSystemTime` at `0x1800657b1`
- `KERNEL32!GetSystemTime` at `0x180065b15`
- `KERNEL32!GetSystemTime` at `0x180065d03`
- `KERNEL32!GetSystemTime` at `0x180065e8f`
- `KERNEL32!GetSystemTime` at `0x180066051`
- `KERNEL32!GetSystemTime` at `0x1800661d9`
- `KERNEL32!GetProcessHeap` at `0x180064fd0`
- `KERNEL32!GetProcessHeap` at `0x180064fd0`
- `KERNEL32!CloseHandle` at `0x1800662a2`
- `KERNEL32!CloseHandle` at `0x1800662a2`
- `KERNEL32!GetLastError` at `0x180065083`
- `KERNEL32!GetLastError` at `0x18006589e`
- `KERNEL32!GetLastError` at `0x180065083`
- `KERNEL32!GetLastError` at `0x18006589e`
- `KERNEL32!HeapFree` at `0x1800662b8`
- `KERNEL32!HeapFree` at `0x1800662b8`
- `SHLWAPI!PathFileExistsW` at `0x180065113`
- `SHLWAPI!PathFileExistsW` at `0x1800651e3`
- `SHLWAPI!PathFileExistsW` at `0x18006526e`
- `SHLWAPI!PathFileExistsW` at `0x180065113`
- `SHLWAPI!PathFileExistsW` at `0x1800651e3`
- `SHLWAPI!PathFileExistsW` at `0x18006526e`
- `acmigration!AcmEngineDelete` at `0x180065bb5`
- `acmigration!AcmEngineDelete` at `0x180065bb5`
- `acmigration!AcmEngineCreate` at `0x180065497`
- `acmigration!AcmEngineCreate` at `0x180065497`
- `ktmw32!CommitTransaction` at `0x180065894`
- `ktmw32!CommitTransaction` at `0x180065894`
- `ktmw32!CreateTransaction` at `0x180065073`
- `ktmw32!CreateTransaction` at `0x180065073`

## string_xrefs

- `0x180065512`: `Error listing non fatal components: [0x%x].`
- `0x180065536`: `Error listing non fatal components: [0x%x].`
- `0x1800650b0`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x180065100`: `onecore\base\appcompat\appraiser\heads\xml\xmlappraiser.cpp`
- `0x1800650a9`: `Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance`
- `0x1800650f9`: `Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance`
- `0x1800658bd`: `Error committing success transaction [0x%x].`
- `0x1800658f1`: `Failed to write XML for component status query: [0x%x].`
- `0x1800659d8`: `Failed to write XML for component status query: [0x%x].`
- `0x180065a01`: `Failed to write XML for component status query: [0x%x].`
- `0x18006565b`: `Error processing components: [0x%x].`
- `0x18006567f`: `Error processing components: [0x%x].`
- `0x180065da5`: `XmlAppraiser leaked one or more duplicate sdb handles [0x%x].`
- `0x180065f38`: `XmlAppraiser leaked one or more duplicate sdb handles [0x%x].`
- `0x180065f78`: `XmlAppraiser leaked one or more duplicate backup sdb handles [0x%x].`
- `0x1800660d1`: `XmlAppraiser leaked one or more duplicate backup sdb handles [0x%x].`
- `0x180065bd3`: `XmlAppraiser leaked one or more duplicate custom sdb handles [0x%x].`
- `0x180065d72`: `XmlAppraiser leaked one or more duplicate custom sdb handles [0x%x].`
- `0x180066100`: `XmlAppraiser leaked one or more duplicate restore sdb handles [0x%x].`
- `0x180066259`: `XmlAppraiser leaked one or more duplicate restore sdb handles [0x%x].`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance(
        Windows::Compat::Appraiser::XmlAppraiser *this,
        struct Windows::Compat::Appraiser::ComponentStatusQuery *a2,
        unsigned __int64 a3)
{
  __int64 *v5; // r14
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rcx
  __int64 v8; // r14
  __int64 v9; // rcx
  const wchar_t *v10; // rax
  unsigned __int8 v11; // r12
  signed int LastError; // eax
  signed int v13; // ebx
  const char *v14; // rax
  char v15; // dl
  const wchar_t *v16; // r15
  void *inited; // rcx
  const WCHAR *v18; // rcx
  void *v19; // rax
  const unsigned __int16 *v20; // rdx
  const WCHAR *v21; // rcx
  void *v22; // rax
  const unsigned __int16 *v23; // rdx
  int CustomSdbHandlesFromPath; // eax
  int v25; // ebx
  volatile signed __int64 *v26; // rcx
  void **v27; // rdx
  int v28; // r15d
  int v29; // r8d
  int v30; // r9d
  int v31; // eax
  struct RtlStringArray *v32; // rdx
  int v33; // eax
  void *v34; // rax
  unsigned __int16 **v35; // rax
  HANDLE v36; // r12
  int v37; // eax
  volatile signed __int64 *v38; // rcx
  void **v39; // rdx
  int v40; // ebx
  unsigned __int16 *v41; // rcx
  unsigned __int64 v42; // rdx
  int v43; // r8d
  int v44; // r9d
  signed int v45; // eax
  char *v46; // rdx
  int v47; // eax
  unsigned int v48; // ecx
  int v49; // eax
  int v50; // eax
  int v51; // eax
  int v52; // r15d
  volatile signed __int64 *v53; // rcx
  void **v54; // rdx
  int v55; // r14d
  int v56; // r8d
  int v57; // r9d
  unsigned __int64 v58; // r14
  unsigned __int64 v59; // rax
  _QWORD *v60; // rdx
  __int64 v61; // rax
  int v62; // eax
  int v63; // r12d
  volatile signed __int64 *v64; // rcx
  void **v65; // rdx
  int v66; // r15d
  int v67; // r8d
  int v68; // r9d
  int v69; // eax
  int v70; // r15d
  volatile signed __int64 *v71; // rcx
  void **v72; // rdx
  int v73; // r14d
  int v74; // r8d
  int v75; // r9d
  int v76; // eax
  int v77; // r15d
  volatile signed __int64 *v78; // rcx
  void **v79; // rdx
  int v80; // r14d
  int v81; // r8d
  int v82; // r9d
  int v83; // eax
  int v84; // r15d
  volatile signed __int64 *v85; // rcx
  void **v86; // rdx
  int v87; // r14d
  int v88; // r8d
  int v89; // r9d
  const char *IsolationFlags; // [rsp+28h] [rbp-E0h]
  const char *Timeout; // [rsp+30h] [rbp-D8h]
  const char *Description; // [rsp+38h] [rbp-D0h]
  const size_t *v94; // [rsp+78h] [rbp-90h] BYREF
  const unsigned __int16 *v95; // [rsp+80h] [rbp-88h] BYREF
  char *v96; // [rsp+88h] [rbp-80h] BYREF
  struct _SYSTEMTIME *v97; // [rsp+90h] [rbp-78h] BYREF
  const size_t *v98; // [rsp+98h] [rbp-70h] BYREF
  __int64 v99; // [rsp+A0h] [rbp-68h] BYREF
  _QWORD v100[2]; // [rsp+A8h] [rbp-60h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+B8h] [rbp-50h] BYREF
  _QWORD v102[2]; // [rsp+C8h] [rbp-40h] BYREF
  __int128 v103; // [rsp+D8h] [rbp-30h] BYREF
  void *v104[2]; // [rsp+E8h] [rbp-20h] BYREF
  void *v105; // [rsp+F8h] [rbp-10h] BYREF
  HANDLE hHeap[2]; // [rsp+100h] [rbp-8h] BYREF
  __int128 v107; // [rsp+110h] [rbp+8h]
  LPVOID lpMem[3]; // [rsp+120h] [rbp+18h]
  HANDLE TransactionHandle; // [rsp+138h] [rbp+30h]
  __int128 v110; // [rsp+148h] [rbp+40h] BYREF
  __int128 v111; // [rsp+158h] [rbp+50h]
  __int128 v112; // [rsp+168h] [rbp+60h]
  unsigned __int16 **v113[2]; // [rsp+178h] [rbp+70h] BYREF
  __int128 v114; // [rsp+188h] [rbp+80h]
  __int128 v115; // [rsp+198h] [rbp+90h]
  __int64 v116; // [rsp+1A8h] [rbp+A0h]
  _BYTE v117[56]; // [rsp+1B0h] [rbp+A8h] BYREF
  struct _SYSTEMTIME v118; // [rsp+1E8h] [rbp+E0h] BYREF
  struct _SYSTEMTIME v119; // [rsp+1F8h] [rbp+F0h] BYREF
  char v120[144]; // [rsp+208h] [rbp+100h] BYREF
  char v121[16]; // [rsp+298h] [rbp+190h] BYREF
  __int128 v122; // [rsp+2A8h] [rbp+1A0h]
  __int128 v123; // [rsp+2B8h] [rbp+1B0h]
  __int128 v124; // [rsp+2C8h] [rbp+1C0h]
  __int128 v125; // [rsp+2D8h] [rbp+1D0h]
  __int128 v126; // [rsp+2E8h] [rbp+1E0h]
  char v127[2]; // [rsp+328h] [rbp+220h] BYREF

  v116 = -2;
  v100[0] = a2;
  Windows::Compat::Appraiser::ComponentStatusQuery::ComponentStatusQuery((Windows::Compat::Appraiser::ComponentStatusQuery *)v117);
  memset_0(&v110, 0, 0x60u);
  v103 = 0;
  *(_OWORD *)v104 = 0;
  v105 = 0;
  hHeap[0] = GetProcessHeap();
  lpMem[0] = (LPVOID)16;
  v107 = 0u;
  lpMem[1] = 0;
  hHeap[1] = (HANDLE)8;
  v5 = 0;
  if ( a3 < *((_QWORD *)this + 2) )
  {
    *(_QWORD *)&SystemTime.wYear = 0;
    v6 = *((_QWORD *)this + 1) * a3;
    if ( !is_mul_ok(*((_QWORD *)this + 1), a3) || (v7 = *((_QWORD *)this + 5), v5 = (__int64 *)(v7 + v6), v7 + v6 < v7) )
      v5 = 0;
  }
  v8 = *v5;
  v9 = *((_QWORD *)this + 7);
  if ( !v9
    || (v10 = (const wchar_t *)(*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)v9 + 40LL))(
                                 v9,
                                 L"ExpressMode")) == 0
    || (v11 = 1, wcscmp_0(L"TRUE", v10)) )
  {
    v11 = 0;
  }
  TransactionHandle = CreateTransaction(0, 0, 0, 0, 0, 0, 0);
  if ( TransactionHandle == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v13 = LastError;
    if ( LastError > 0 )
      v13 = (unsigned __int16)LastError | 0x80070000;
    if ( v13 >= 0 )
      v13 = -2147467259;
    v14 = "Error creating success transaction [0x%x].";
    v15 = 72;
LABEL_15:
    LODWORD(Description) = v13;
LABEL_16:
    LODWORD(Timeout) = (_DWORD)v14;
LABEL_17:
    LODWORD(v94) = v13;
LABEL_18:
    LODWORD(IsolationFlags) = v13;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v15,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      IsolationFlags,
      (int)Timeout,
      Description);
    goto LABEL_115;
  }
  *((_QWORD *)&v103 + 1) = *(_QWORD *)(v8 + 216);
  v16 = *(const wchar_t **)(v8 + 8LL * v11 + 136);
  if ( v16 )
  {
    if ( !PathFileExistsW(*(LPCWSTR *)(v8 + 8LL * v11 + 136)) )
    {
      Description = (const char *)v16;
      v14 = "SDB file does not exist: %ls.";
      v13 = -2147024894;
      v15 = 91;
      goto LABEL_16;
    }
    g_ExpectedAlgorithm = 1;
    g_ExpandCallback = (__int64)Windows::Compat::Appraiser::SdbUtils::ZlibUnCompressBuffer;
    g_CompressCallback = 0;
    inited = (void *)SdbInitDatabase(3, v16);
    v104[0] = inited;
    if ( !inited )
    {
      v13 = -2138546174;
      Description = (const char *)v16;
      Timeout = "Error initializing SDB database: %ls.";
      v15 = 98;
      goto LABEL_17;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x462u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "Error initializing SDB database: %ls.",
        v16);
      inited = v104[0];
    }
    Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(inited, v16);
    v18 = *(const WCHAR **)(v8 + 152);
    if ( v18 && !v11 )
    {
      if ( PathFileExistsW(v18) )
      {
        v19 = (void *)SdbInitDatabase(3, *(_QWORD *)(v8 + 152));
        v104[1] = v19;
        v20 = *(const unsigned __int16 **)(v8 + 152);
        if ( v19 )
        {
          Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(v19, v20);
        }
        else
        {
          LODWORD(IsolationFlags) = -2138546174;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            113,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
            IsolationFlags,
            (int)"Error initializing Backup Sdb file: %ls",
            (const char *)v20);
        }
      }
      else
      {
        LODWORD(IsolationFlags) = -2147023728;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          123,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
          IsolationFlags,
          (int)"Backup Sdb file does not exist: %ls",
          *(const char **)(v8 + 152));
      }
    }
    v21 = *(const WCHAR **)(v8 + 160);
    if ( v21 )
    {
      if ( PathFileExistsW(v21) )
      {
        v22 = (void *)SdbInitDatabase(3, *(_QWORD *)(v8 + 160));
        v105 = v22;
        v23 = *(const unsigned __int16 **)(v8 + 160);
        if ( v22 )
        {
          Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(v22, v23);
        }
        else
        {
          LODWORD(IsolationFlags) = -2138546174;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            138,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
            IsolationFlags,
            (int)"Error initializing Restore Sdb file: %ls",
            (const char *)v23);
        }
      }
      else
      {
        LODWORD(IsolationFlags) = -2147023728;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          148,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
          IsolationFlags,
          (int)"Restore Sdb file does not exist: %ls",
          *(const char **)(v8 + 160));
      }
    }
    if ( *(_QWORD *)(v8 + 168) )
      CustomSdbHandlesFromPath = Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath(hHeap);
    else
      CustomSdbHandlesFromPath = Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandles(hHeap);
    v25 = CustomSdbHandlesFromPath;
    if ( CustomSdbHandlesFromPath >= 0 )
    {
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4A5u,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
          "Error getting custom SDB handles: [0x%x].",
          CustomSdbHandlesFromPath);
    }
    else
    {
      LODWORD(Description) = CustomSdbHandlesFromPath;
      LODWORD(IsolationFlags) = CustomSdbHandlesFromPath;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        165,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        IsolationFlags,
        (int)"Error getting custom SDB handles: [0x%x].",
        Description);
      TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
      v26 = (volatile signed __int64 *)v120;
      if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
        v26 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
      TraceLoggingCorrelationVector::ToStringImpl(
        (TraceLoggingCorrelationVector *)v26,
        _InterlockedExchangeAdd64(v26 + 17, 0),
        v121);
      if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
        UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v27);
      v28 = qword_1802C9628;
      if ( *(_DWORD *)qword_1802C9628 > 5u
        && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
        && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
      {
        v96 = v121;
        LODWORD(v94) = v25;
        v102[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
        v97 = (struct _SYSTEMTIME *)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
        LODWORD(v95) = 1189;
        v98 = &szValueBuf;
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        v118 = SystemTime;
        v99 = (__int64)&v118;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v28,
          (unsigned int)&unk_1802A12CE,
          v29,
          v30,
          (__int64)&v99,
          (__int64)&v98,
          (__int64)&v95,
          (__int64)&v97,
          (__int64)v102,
          (__int64)&v94,
          (__int64)&v96);
      }
    }
  }
  if ( *(_BYTE *)(v8 + 80) )
  {
    v31 = AcmEngineCreate((void **)&v103);
    v13 = v31;
    LODWORD(v94) = v31;
    if ( v31 < 0 )
    {
      LODWORD(Description) = v31;
      Timeout = "Error creating mig shim engine: [0x%x].";
      v15 = -81;
      goto LABEL_18;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4AFu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "Error creating mig shim engine: [0x%x].",
        v31);
  }
  if ( *((_QWORD *)&v103 + 1) )
  {
    v32 = *(struct RtlStringArray **)(*((_QWORD *)&v103 + 1) + 480LL);
    if ( v32 )
    {
      v33 = Windows::Compat::Appraiser::Utilities::ArrayToListAlloc((const unsigned __int16 ***)v113, v32);
      v13 = v33;
      LODWORD(v94) = v33;
      if ( v33 < 0 )
      {
        LODWORD(Description) = v33;
        Timeout = "Error listing non fatal components: [0x%x].";
        v15 = -69;
        goto LABEL_18;
      }
      if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
        Windows::Compat::Appraiser::WicaFactory::RunPrintf(
          0x4BBu,
          "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
          "Error listing non fatal components: [0x%x].",
          v33);
      DWORD2(v115) = *(_DWORD *)(*(_QWORD *)(*((_QWORD *)&v103 + 1) + 480LL) + 16LL);
    }
  }
  *(_QWORD *)&v110 = operator new[](0x80u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)&v110 + 1) = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&v111 = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)&v111 + 1) = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  *(_QWORD *)&v112 = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  v34 = operator new[](0x100u, (const struct std::nothrow_t *)&std::nothrow);
  *((_QWORD *)&v112 + 1) = v34;
  if ( !(_QWORD)v110 || !*((_QWORD *)&v110 + 1) || !(_QWORD)v111 || !*((_QWORD *)&v111 + 1) || !(_QWORD)v112 || !v34 )
  {
    v13 = -2147024882;
    LODWORD(v94) = -2147024882;
    goto LABEL_115;
  }
  *(_QWORD *)&v115 = 0;
  v114 = 0u;
  v35 = (unsigned __int16 **)v117;
  if ( v100[0] )
    v35 = (unsigned __int16 **)v100[0];
  v113[1] = v35;
  v36 = TransactionHandle;
  v37 = Windows::Compat::Appraiser::XmlAppraiser::InitializeComponentsIntoWicaRun(
          this,
          (struct Windows::Compat::Appraiser::WicaRun *)&v110,
          (struct Windows::Compat::Appraiser::RunInfoData *)v8,
          (struct Windows::Compat::Appraiser::RunInfoDataStruct *)&v103,
          TransactionHandle);
  v13 = v37;
  LODWORD(v94) = v37;
  if ( v37 < 0 )
  {
    LODWORD(Description) = v37;
    Timeout = "Error processing components: [0x%x].";
    v15 = -37;
    goto LABEL_18;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x4DBu,
      "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      "Error processing components: [0x%x].",
      v37);
  if ( *(_WORD *)(v8 + 352) )
  {
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
    v38 = (volatile signed __int64 *)v120;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v38 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v38,
      _InterlockedExchangeAdd64(v38 + 17, 0),
      v121);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v39);
    v40 = qword_1802C9560;
    if ( *(_DWORD *)qword_1802C9560 > 5u )
    {
      v41 = *(unsigned __int16 **)(qword_1802C9560 + 24);
      v42 = 0x800000000000LL;
      if ( (*(_QWORD *)(qword_1802C9560 + 16) & 0x800000000000LL) != 0
        && (unsigned __int16 *)((unsigned __int64)v41 & 0x800000000000LL) == v41 )
      {
        v100[0] = v121;
        v99 = 0x1000000;
        v98 = (const size_t *)(v8 + 416);
        v97 = (struct _SYSTEMTIME *)(v8 + 352);
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserProcessExe(v41, 0x800000000000uLL);
        v102[0] = &Windows::Compat::Appraiser::WicaFactory::AppraiserProcessExeBuffer;
        if ( !Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer )
          Windows::Compat::Appraiser::Utilities::GetAppraiserBranch(v41, v42);
        v96 = (char *)&Windows::Compat::Appraiser::WicaFactory::AppraiserBranchBuffer;
        v95 = Windows::Compat::Appraiser::WicaFactory::AppraiserVersion();
        v94 = &szValueBuf;
        v118 = 0;
        GetSystemTime(&v118);
        v119 = v118;
        *(_QWORD *)&SystemTime.wYear = &v119;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>,_tlgWrapSz<char>>(
          v40,
          (unsigned int)&unk_1802A117C,
          v43,
          v44,
          (__int64)&SystemTime,
          (__int64)&v94,
          (__int64)&v95,
          (__int64)&v96,
          (__int64)v102,
          (__int64)&v97,
          (__int64)&v98,
          (__int64)&v99,
          (__int64)v100);
      }
    }
  }
  *(_OWORD *)v121 = v110;
  v122 = v111;
  v123 = v112;
  v124 = *(_OWORD *)v113;
  v125 = v114;
  v126 = v115;
  v13 = Windows::Compat::Appraiser::WicaFactory::DoWicaRun(v121);
  LODWORD(v94) = v13;
  if ( v13 >= 0 && !CommitTransaction(v36) )
  {
    v45 = GetLastError();
    v13 = v45;
    if ( v45 > 0 )
      v13 = (unsigned __int16)v45 | 0x80070000;
    if ( v13 >= 0 )
      v13 = -2147467259;
    v14 = "Error committing success transaction [0x%x].";
    v15 = -18;
    goto LABEL_15;
  }
  v46 = *(char **)(v8 + 176);
  if ( v46 )
  {
    v47 = Windows::Compat::Appraiser::XmlAppraiser::WriteComponentStatusToXml(
            (struct Windows::Compat::Appraiser::ComponentStatusQuery *)v113[1],
            v46);
    v13 = v47;
    LODWORD(v94) = v47;
    if ( v47 < 0 )
    {
      LODWORD(Description) = v47;
      Timeout = "Failed to write XML for component status query: [0x%x].";
      v15 = -8;
      goto LABEL_18;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v48 = 1272;
LABEL_114:
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        v48,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "Failed to write XML for component status query: [0x%x].",
        v13);
    }
  }
  else if ( *(_QWORD *)(v8 + 184) && *(_QWORD *)(v8 + 192) && *(_QWORD *)(v8 + 200) )
  {
    HIDWORD(IsolationFlags) = HIDWORD(*(_QWORD *)(v8 + 192));
    v49 = StringCchPrintfW((unsigned __int16 *)v127, 0x104u, L"%ls\\%ls\\%ls");
    v13 = v49;
    LODWORD(v94) = v49;
    if ( v49 < 0 )
    {
      LODWORD(Description) = v49;
      Timeout = "Failed to print string: [0x%x].";
      v15 = 4;
      goto LABEL_18;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x504u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "Failed to print string: [0x%x].",
        v49);
    v50 = Windows::Compat::Appraiser::XmlAppraiser::WriteComponentStatusToXml(
            (struct Windows::Compat::Appraiser::ComponentStatusQuery *)v113[1],
            v127);
    v13 = v50;
    LODWORD(v94) = v50;
    if ( v50 < 0 )
    {
      LODWORD(Description) = v50;
      Timeout = "Failed to write XML for component status query: [0x%x].";
      v15 = 7;
      goto LABEL_18;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    {
      v48 = 1287;
      goto LABEL_114;
    }
  }
LABEL_115:
  v51 = Windows::Compat::Appraiser::XmlAppraiser::CleanupWicaRun((struct Windows::Compat::Appraiser::WicaRun *)&v110);
  v52 = v51;
  if ( v51 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x50Eu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "Error cleaning up: [0x%x].",
        v51);
  }
  else
  {
    LODWORD(Description) = v51;
    LODWORD(IsolationFlags) = v51;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      14,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      IsolationFlags,
      (int)"Error cleaning up: [0x%x].",
      Description);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
    v53 = (volatile signed __int64 *)v120;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v53 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v53,
      _InterlockedExchangeAdd64(v53 + 17, 0),
      v121);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v54);
    v55 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)&SystemTime.wYear = v121;
      LODWORD(v95) = v52;
      v100[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
      v99 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
      LODWORD(v96) = 1294;
      v98 = &szValueBuf;
      v118 = 0;
      GetSystemTime(&v118);
      v119 = v118;
      v97 = &v119;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v55,
        (unsigned int)&unk_1802A126B,
        v56,
        v57,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)&v96,
        (__int64)&v99,
        (__int64)v100,
        (__int64)&v95,
        (__int64)&SystemTime);
    }
  }
  if ( (_QWORD)v103 )
  {
    AcmEngineDelete((void *)v103);
    *(_QWORD *)&v103 = 0;
  }
  v58 = 0;
  v59 = v107;
  if ( (_QWORD)v107 )
  {
    do
    {
      v60 = 0;
      if ( v58 < v59 )
      {
        *(_QWORD *)&SystemTime.wYear = 0;
        v61 = (unsigned __int64)hHeap[1] * v58;
        if ( !is_mul_ok((unsigned __int64)hHeap[1], v58)
          || (v60 = (char *)lpMem[1] + v61, (char *)lpMem[1] + v61 < lpMem[1]) )
        {
          v60 = 0;
        }
      }
      *(_QWORD *)&SystemTime.wYear = *v60;
      v62 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase((void **)&SystemTime);
      v63 = v62;
      if ( v62 >= 0 )
      {
        if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
          Windows::Compat::Appraiser::WicaFactory::RunPrintf(
            0x51Au,
            "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
            "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
            "XmlAppraiser leaked one or more duplicate custom sdb handles [0x%x].",
            v62);
      }
      else
      {
        LODWORD(Description) = v62;
        LODWORD(IsolationFlags) = v62;
        Windows::Compat::Appraiser::WriteLog(
          (Windows::Compat::Appraiser *)1,
          26,
          (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
          "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
          IsolationFlags,
          (int)"XmlAppraiser leaked one or more duplicate custom sdb handles [0x%x].",
          Description);
        TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
        v64 = (volatile signed __int64 *)v120;
        if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
          v64 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
        TraceLoggingCorrelationVector::ToStringImpl(
          (TraceLoggingCorrelationVector *)v64,
          _InterlockedExchangeAdd64(v64 + 17, 0),
          v121);
        if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
          UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v65);
        v66 = qword_1802C9628;
        if ( *(_DWORD *)qword_1802C9628 > 5u
          && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
          && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
        {
          *(_QWORD *)&SystemTime.wYear = v121;
          LODWORD(v96) = v63;
          v100[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
          v99 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
          LODWORD(v95) = 1306;
          v98 = &szValueBuf;
          v118 = 0;
          GetSystemTime(&v118);
          v119 = v118;
          v97 = &v119;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v66,
            (unsigned int)&unk_1802A1208,
            v67,
            v68,
            (__int64)&v97,
            (__int64)&v98,
            (__int64)&v95,
            (__int64)&v99,
            (__int64)v100,
            (__int64)&v96,
            (__int64)&SystemTime);
        }
      }
      ++v58;
      v59 = v107;
    }
    while ( v58 < (unsigned __int64)v107 );
    v13 = (int)v94;
  }
  v69 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(v104);
  v70 = v69;
  if ( v69 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x51Eu,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "XmlAppraiser leaked one or more duplicate sdb handles [0x%x].",
        v69);
  }
  else
  {
    LODWORD(Description) = v69;
    LODWORD(IsolationFlags) = v69;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      30,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      IsolationFlags,
      (int)"XmlAppraiser leaked one or more duplicate sdb handles [0x%x].",
      Description);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
    v71 = (volatile signed __int64 *)v120;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v71 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v71,
      _InterlockedExchangeAdd64(v71 + 17, 0),
      v121);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v72);
    v73 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)&SystemTime.wYear = v121;
      LODWORD(v96) = v70;
      v100[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
      v99 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
      LODWORD(v95) = 1310;
      v98 = &szValueBuf;
      v118 = 0;
      GetSystemTime(&v118);
      v119 = v118;
      v97 = &v119;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v73,
        (unsigned int)&unk_1802A10B6,
        v74,
        v75,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)&v95,
        (__int64)&v99,
        (__int64)v100,
        (__int64)&v96,
        (__int64)&SystemTime);
    }
  }
  v76 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(&v104[1]);
  v77 = v76;
  if ( v76 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x521u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "XmlAppraiser leaked one or more duplicate backup sdb handles [0x%x].",
        v76);
  }
  else
  {
    LODWORD(Description) = v76;
    LODWORD(IsolationFlags) = v76;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      33,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      IsolationFlags,
      (int)"XmlAppraiser leaked one or more duplicate backup sdb handles [0x%x].",
      Description);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
    v78 = (volatile signed __int64 *)v120;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v78 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v78,
      _InterlockedExchangeAdd64(v78 + 17, 0),
      v121);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v79);
    v80 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)&SystemTime.wYear = v121;
      LODWORD(v96) = v77;
      v100[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
      v99 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
      LODWORD(v95) = 1313;
      v98 = &szValueBuf;
      v118 = 0;
      GetSystemTime(&v118);
      v119 = v118;
      v97 = &v119;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v80,
        (unsigned int)&unk_1802A1053,
        v81,
        v82,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)&v95,
        (__int64)&v99,
        (__int64)v100,
        (__int64)&v96,
        (__int64)&SystemTime);
    }
  }
  v83 = Windows::Compat::Appraiser::SdbUtils::SafeReleaseDatabase(&v105);
  v84 = v83;
  if ( v83 >= 0 )
  {
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x524u,
        "onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
        "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
        "XmlAppraiser leaked one or more duplicate restore sdb handles [0x%x].",
        v83);
    g_ExpectedAlgorithm = 1;
    g_ExpandCallback = 0;
    g_CompressCallback = 0;
    SdbOfflineRuntimePlatformDataFree();
  }
  else
  {
    LODWORD(Description) = v83;
    LODWORD(IsolationFlags) = v83;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      36,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp",
      "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance",
      IsolationFlags,
      (int)"XmlAppraiser leaked one or more duplicate restore sdb handles [0x%x].",
      Description);
    TraceLoggingCorrelationVector::TraceLoggingCorrelationVector((TraceLoggingCorrelationVector *)v120);
    v85 = (volatile signed __int64 *)v120;
    if ( Windows::Compat::Appraiser::WicaFactory::CorrelationVector )
      v85 = (volatile signed __int64 *)Windows::Compat::Appraiser::WicaFactory::CorrelationVector;
    TraceLoggingCorrelationVector::ToStringImpl(
      (TraceLoggingCorrelationVector *)v85,
      _InterlockedExchangeAdd64(v85 + 17, 0),
      v121);
    if ( Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive )
      UtcThrottle::Throttle((UtcThrottle *)&Windows::Compat::Appraiser::WicaFactory::UtcEventThrottler, v86);
    v87 = qword_1802C9628;
    if ( *(_DWORD *)qword_1802C9628 > 5u
      && (*(_QWORD *)(qword_1802C9628 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(qword_1802C9628 + 24) & 0x200000000000LL) == *(_QWORD *)(qword_1802C9628 + 24) )
    {
      *(_QWORD *)&SystemTime.wYear = v121;
      LODWORD(v96) = v84;
      v100[0] = "Windows::Compat::Appraiser::XmlAppraiser::RunEngineForRunInfoInstance";
      v99 = (__int64)"onecore\\base\\appcompat\\appraiser\\heads\\xml\\xmlappraiser.cpp";
      LODWORD(v95) = 1316;
      v98 = &szValueBuf;
      v118 = 0;
      GetSystemTime(&v118);
      v119 = v118;
      v97 = &v119;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v87,
        (unsigned int)&unk_1802A1119,
        v88,
        v89,
        (__int64)&v97,
        (__int64)&v98,
        (__int64)&v95,
        (__int64)&v99,
        (__int64)v100,
        (__int64)&v96,
        (__int64)&SystemTime);
    }
  }
  if ( TransactionHandle != (HANDLE)-1LL )
    CloseHandle(TransactionHandle);
  if ( lpMem[1] )
    HeapFree(hHeap[0], 0, lpMem[1]);
  *(_OWORD *)hHeap = 0;
  v107 = 0;
  *(_OWORD *)lpMem = 0;
  Windows::Compat::Appraiser::ComponentStatusQuery::~ComponentStatusQuery((Windows::Compat::Appraiser::ComponentStatusQuery *)v117);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180064f4c  mov     rax, rsp
0x180064f4f  push    rbp
0x180064f50  push    rsi
0x180064f51  push    rdi
0x180064f52  push    r12
0x180064f54  push    r13
0x180064f56  push    r14
0x180064f58  push    r15
0x180064f5a  lea     rbp, [rax-478h]
0x180064f61  sub     rsp, 540h
0x180064f68  mov     [rbp+470h+var_3D0], 0FFFFFFFFFFFFFFFEh
0x180064f73  mov     [rax+20h], rbx
0x180064f77  mov     rax, cs:__security_cookie
0x180064f7e  xor     rax, rsp
0x180064f81  mov     [rbp+470h+var_40], rax
0x180064f88  mov     rbx, r8
0x180064f8b  mov     [rbp+470h+var_4D0], rdx
0x180064f8f  mov     r13, rcx
0x180064f92  lea     rcx, [rbp+470h+var_3C8]; this
0x180064f99  call    ??0ComponentStatusQuery@Appraiser@Compat@Windows@@QEAA@XZ; Windows::Compat::Appraiser::ComponentStatusQuery::ComponentStatusQuery(void)
0x180064f9e  nop
0x180064f9f  xor     edx, edx; Val
0x180064fa1  lea     r8d, [rdx+60h]; Size
0x180064fa5  lea     rcx, [rbp+470h+var_430]; void *
0x180064fa9  call    memset_0
0x180064fae  xorps   xmm0, xmm0
0x180064fb1  movdqa  [rbp+470h+var_4A0], xmm0
0x180064fb6  xorps   xmm1, xmm1
0x180064fb9  movdqa  xmmword ptr [rbp+470h+var_490], xmm1
0x180064fbe  xor     edi, edi
0x180064fc0  mov     [rbp+470h+var_480], rdi
0x180064fc4  movups  xmmword ptr [rbp+470h+hHeap], xmm0
0x180064fc8  movups  [rbp+470h+var_468], xmm0
0x180064fcc  movups  xmmword ptr [rbp+470h+lpMem], xmm0
0x180064fd0  call    cs:__imp_GetProcessHeap
0x180064fd6  mov     [rbp+470h+hHeap], rax
0x180064fda  mov     [rbp+470h+lpMem], 10h
0x180064fe2  mov     qword ptr [rbp+470h+var_468], rdi
0x180064fe6  mov     qword ptr [rbp+470h+var_468+8], rdi
0x180064fea  mov     [rbp+470h+lpMem+8], rdi
0x180064fee  mov     [rbp+470h+hHeap+8], 8
0x180064ff6  mov     r14d, edi
0x180064ff9  cmp     rbx, [r13+10h]
0x180064ffd  jnb     short loc_18006501F
0x180064fff  mov     qword ptr [rbp+470h+SystemTime.wYear], rdi
0x180065003  mov     rax, rbx
0x180065006  mul     qword ptr [r13+8]
0x18006500a  test    rdx, rdx
0x18006500d  jnz     short loc_18006501C
0x18006500f  mov     rcx, [r13+28h]
0x180065013  lea     r14, [rcx+rax]
0x180065017  cmp     r14, rcx
0x18006501a  jnb     short loc_18006501F
0x18006501c  mov     r14, rdi
0x18006501f  mov     r14, [r14]
0x180065022  mov     rcx, [r13+38h]
0x180065026  test    rcx, rcx
0x180065029  jz      short loc_180065059
0x18006502b  mov     rax, [rcx]
0x18006502e  lea     rdx, aExpressmode; "ExpressMode"
0x180065035  mov     rax, [rax+28h]
0x180065039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006503e  test    rax, rax
0x180065041  jz      short loc_180065059
0x180065043  mov     rdx, rax; String2
0x180065046  lea     rcx, aTrue_2; "TRUE"
0x18006504d  call    wcscmp_0
0x180065052  test    eax, eax
0x180065054  mov     r12b, 1
0x180065057  jz      short loc_18006505C
0x180065059  mov     r12b, dil
0x18006505c  mov     [rsp+570h+Description], rdi; Description
0x180065061  mov     [rsp+570h+Timeout], edi; Timeout
0x180065065  mov     [rsp+570h+IsolationFlags], edi; IsolationFlags
0x180065069  xor     r9d, r9d; IsolationLevel
0x18006506c  xor     r8d, r8d; CreateOptions
0x18006506f  xor     edx, edx; UOW
0x180065071  xor     ecx, ecx; lpTransactionAttributes
0x180065073  call    cs:__imp_CreateTransaction
0x180065079  mov     [rbp+470h+TransactionHandle], rax
0x18006507d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065081  jnz     short loc_1800650E2
0x180065083  call    cs:__imp_GetLastError
0x180065089  mov     ebx, eax
0x18006508b  test    eax, eax
0x18006508d  jle     short loc_180065098
0x18006508f  movzx   ebx, ax
0x180065092  or      ebx, 80070000h
0x180065098  mov     eax, 80004005h
0x18006509d  test    ebx, ebx
0x18006509f  cmovns  ebx, eax
0x1800650a2  lea     rax, aErrorCreatingS; "Error creating success transaction [0x%"...
0x1800650a9  lea     rdi, aWindowsCompatA_456; "Windows::Compat::Appraiser::XmlAppraise"...
0x1800650b0  lea     rsi, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800650b7  mov     edx, 448h; bool
0x1800650bc  mov     dword ptr [rsp+570h+Description], ebx; char *
0x1800650c0  mov     qword ptr [rsp+570h+Timeout], rax; int
0x1800650c5  mov     dword ptr [rsp+570h+var_500], ebx
0x1800650c9  mov     r8, rsi; unsigned int
0x1800650cc  mov     r9, rdi; char *
0x1800650cf  mov     [rsp+570h+IsolationFlags], ebx; char *
0x1800650d3  mov     ecx, 1; this
0x1800650d8  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800650dd  jmp     loc_180065A13
0x1800650e2  mov     rax, [r14+0D8h]
0x1800650e9  mov     qword ptr [rbp+470h+var_4A0+8], rax
0x1800650ed  movzx   eax, r12b
0x1800650f1  mov     r15, [r14+rax*8+88h]
0x1800650f9  lea     rdi, aWindowsCompatA_456; "Windows::Compat::Appraiser::XmlAppraise"...
0x180065100  lea     rsi, aOnecoreBaseApp_56; "onecore\\base\\appcompat\\appraiser\\he"...
0x180065107  test    r15, r15
0x18006510a  jz      loc_18006548C
0x180065110  mov     rcx, r15; pszPath
0x180065113  call    cs:__imp_PathFileExistsW
0x180065119  test    eax, eax
0x18006511b  jnz     short loc_180065135
0x18006511d  mov     [rsp+570h+Description], r15
0x180065122  lea     rax, aSdbFileDoesNot; "SDB file does not exist: %ls."
0x180065129  mov     ebx, 80070002h
0x18006512e  mov     edx, 45Bh
0x180065133  jmp     short loc_1800650C0
0x180065135  mov     cs:g_ExpectedAlgorithm, 1
0x18006513f  lea     rax, ?ZlibUnCompressBuffer@SdbUtils@Appraiser@Compat@Windows@@SAHPEAEPEAKQEAEK@Z; Windows::Compat::Appraiser::SdbUtils::ZlibUnCompressBuffer(uchar *,ulong *,uchar * const,ulong)
0x180065146  mov     cs:g_ExpandCallback, rax
0x18006514d  mov     cs:g_CompressCallback, 0
0x180065158  mov     rdx, r15
0x18006515b  mov     ecx, 3
0x180065160  call    SdbInitDatabase
0x180065165  mov     rcx, rax
0x180065168  mov     [rbp+470h+var_490], rax
0x18006516c  test    rax, rax
0x18006516f  jnz     short loc_180065191
0x180065171  mov     ebx, 80886002h
0x180065176  mov     [rsp+570h+Description], r15
0x18006517b  lea     r9, aErrorInitializ_5; "Error initializing SDB database: %ls."
0x180065182  mov     qword ptr [rsp+570h+Timeout], r9
0x180065187  mov     edx, 462h
0x18006518c  jmp     loc_1800650C5
0x180065191  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180065197  test    al, 1
0x180065199  jz      short loc_1800651BB
0x18006519b  mov     qword ptr [rsp+570h+IsolationFlags], r15
0x1800651a0  lea     r9, aErrorInitializ_5; "Error initializing SDB database: %ls."
0x1800651a7  mov     r8, rdi; char *
0x1800651aa  mov     rdx, rsi; char *
0x1800651ad  mov     ecx, 462h; unsigned int
0x1800651b2  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800651b7  mov     rcx, [rbp+470h+var_490]; void *
0x1800651bb  mov     rdx, r15; unsigned __int16 *
0x1800651be  call    ?SendSdbInfoTelemetry@SdbUtils@Appraiser@Compat@Windows@@SAXPEAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(void *,ushort const *)
0x1800651c3  mov     rcx, [r14+98h]; pszPath
0x1800651ca  mov     ebx, 80886002h
0x1800651cf  mov     r15d, 80070490h
0x1800651d5  test    rcx, rcx
0x1800651d8  jz      loc_180065262
0x1800651de  test    r12b, r12b
0x1800651e1  jnz     short loc_180065262
0x1800651e3  call    cs:__imp_PathFileExistsW
0x1800651e9  mov     rcx, [r14+98h]
0x1800651f0  test    eax, eax
0x1800651f2  jz      short loc_180065237
0x1800651f4  mov     rdx, rcx
0x1800651f7  mov     ecx, 3
0x1800651fc  call    SdbInitDatabase
0x180065201  mov     [rbp+470h+var_490+8], rax
0x180065205  mov     rdx, [r14+98h]; unsigned __int16 *
0x18006520c  test    rax, rax
0x18006520f  jnz     short loc_18006522D
0x180065211  mov     [rsp+570h+Description], rdx
0x180065216  lea     rax, aErrorInitializ_1; "Error initializing Backup Sdb file: %ls"
0x18006521d  mov     qword ptr [rsp+570h+Timeout], rax
0x180065222  mov     [rsp+570h+IsolationFlags], ebx
0x180065226  mov     edx, 471h
0x18006522b  jmp     short loc_180065252
0x18006522d  mov     rcx, rax; void *
0x180065230  call    ?SendSdbInfoTelemetry@SdbUtils@Appraiser@Compat@Windows@@SAXPEAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(void *,ushort const *)
0x180065235  jmp     short loc_180065262
0x180065237  mov     [rsp+570h+Description], rcx; char *
0x18006523c  lea     rax, aBackupSdbFileD; "Backup Sdb file does not exist: %ls"
0x180065243  mov     qword ptr [rsp+570h+Timeout], rax; int
0x180065248  mov     [rsp+570h+IsolationFlags], r15d; char *
0x18006524d  mov     edx, 47Bh; bool
0x180065252  mov     r9, rdi; char *
0x180065255  mov     r8, rsi; unsigned int
0x180065258  mov     ecx, 1; this
0x18006525d  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180065262  mov     rcx, [r14+0A0h]; pszPath
0x180065269  test    rcx, rcx
0x18006526c  jz      short loc_1800652EA
0x18006526e  call    cs:__imp_PathFileExistsW
0x180065274  mov     rdx, [r14+0A0h]
0x18006527b  test    eax, eax
0x18006527d  jz      short loc_1800652BF
0x18006527f  mov     ecx, 3
0x180065284  call    SdbInitDatabase
0x180065289  mov     [rbp+470h+var_480], rax
0x18006528d  mov     rdx, [r14+0A0h]; unsigned __int16 *
0x180065294  test    rax, rax
0x180065297  jnz     short loc_1800652B5
0x180065299  mov     [rsp+570h+Description], rdx
0x18006529e  lea     rax, aErrorInitializ_25; "Error initializing Restore Sdb file: %l"...
0x1800652a5  mov     qword ptr [rsp+570h+Timeout], rax
0x1800652aa  mov     [rsp+570h+IsolationFlags], ebx
0x1800652ae  mov     edx, 48Ah
0x1800652b3  jmp     short loc_1800652DA
0x1800652b5  mov     rcx, rax; void *
0x1800652b8  call    ?SendSdbInfoTelemetry@SdbUtils@Appraiser@Compat@Windows@@SAXPEAXPEBG@Z; Windows::Compat::Appraiser::SdbUtils::SendSdbInfoTelemetry(void *,ushort const *)
0x1800652bd  jmp     short loc_1800652EA
0x1800652bf  mov     [rsp+570h+Description], rdx; char *
0x1800652c4  lea     rax, aRestoreSdbFile; "Restore Sdb file does not exist: %ls"
0x1800652cb  mov     qword ptr [rsp+570h+Timeout], rax; int
0x1800652d0  mov     [rsp+570h+IsolationFlags], r15d; char *
0x1800652d5  mov     edx, 494h; bool
0x1800652da  mov     r9, rdi; char *
0x1800652dd  mov     r8, rsi; unsigned int
0x1800652e0  mov     ecx, 1; this
0x1800652e5  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800652ea  mov     rdx, [r14+0A8h]
0x1800652f1  lea     rcx, [rbp+470h+hHeap]
0x1800652f5  test    rdx, rdx
0x1800652f8  jz      short loc_180065301
0x1800652fa  call    ?GetCustomSdbHandlesFromPath@SdbUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEAX@@PEBG@Z; Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandlesFromPath(RtlArray<void *> &,ushort const *)
0x1800652ff  jmp     short loc_180065306
0x180065301  call    ?GetCustomSdbHandles@SdbUtils@Appraiser@Compat@Windows@@SAJAEAV?$RtlArray@PEAX@@@Z; Windows::Compat::Appraiser::SdbUtils::GetCustomSdbHandles(RtlArray<void *> &)
0x180065306  mov     ebx, eax
0x180065308  test    eax, eax
0x18006530a  jns     loc_180065467
0x180065310  mov     dword ptr [rsp+570h+Description], eax; char *
0x180065314  lea     r9, aErrorGettingCu_2; "Error getting custom SDB handles: [0x%x"...
0x18006531b  mov     qword ptr [rsp+570h+Timeout], r9; int
0x180065320  mov     [rsp+570h+IsolationFlags], eax; char *
0x180065324  mov     r9, rdi; char *
0x180065327  mov     r8, rsi; unsigned int
0x18006532a  mov     edx, 4A5h; bool
0x18006532f  mov     ecx, 1; this
0x180065334  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180065339  lea     rcx, [rbp+470h+var_370]; this
0x180065340  call    ??0TraceLoggingCorrelationVector@@QEAA@XZ; TraceLoggingCorrelationVector::TraceLoggingCorrelationVector(void)
0x180065345  lea     rcx, [rbp+470h+var_370]
0x18006534c  mov     rax, cs:?CorrelationVector@WicaFactory@Appraiser@Compat@Windows@@2PEAVTraceLoggingCorrelationVector@@EA; TraceLoggingCorrelationVector * Windows::Compat::Appraiser::WicaFactory::CorrelationVector
0x180065353  test    rax, rax
0x180065356  cmovnz  rcx, rax; this
0x18006535a  xor     edx, edx
0x18006535c  lock xadd [rcx+88h], rdx; unsigned __int64
0x180065365  lea     r8, [rbp+470h+var_2E0]; char *
0x18006536c  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x180065371  cmp     cs:?UtcEventThrottlerActive@WicaFactory@Appraiser@Compat@Windows@@2_NA, 0; bool Windows::Compat::Appraiser::WicaFactory::UtcEventThrottlerActive
0x180065378  jz      short loc_180065386
0x18006537a  lea     rcx, ?UtcEventThrottler@WicaFactory@Appraiser@Compat@Windows@@2VUtcThrottle@@A; this
0x180065381  call    ?Throttle@UtcThrottle@@QEAA_NPEAPEAX@Z; UtcThrottle::Throttle(void * *)
0x180065386  mov     r15, cs:qword_1802C9628
0x18006538d  mov     eax, [r15]
0x180065390  cmp     eax, 5
0x180065393  jbe     loc_18006548C
0x180065399  mov     rcx, [r15+18h]
0x18006539d  mov     rax, [r15+10h]
0x1800653a1  mov     rdx, 200000000000h
0x1800653ab  test    rdx, rax
0x1800653ae  jz      loc_18006548C
0x1800653b4  mov     rax, rcx
0x1800653b7  and     rax, rdx
0x1800653ba  cmp     rax, rcx
0x1800653bd  jnz     loc_18006548C
0x1800653c3  lea     rax, [rbp+470h+var_2E0]
0x1800653ca  mov     [rbp+470h+var_4F0], rax
0x1800653ce  mov     dword ptr [rsp+570h+var_500], ebx
0x1800653d2  mov     [rbp+470h+var_4B0], rdi
0x1800653d6  mov     [rbp+470h+var_4E8], rsi
0x1800653da  mov     dword ptr [rsp+570h+var_4F8], 4A5h
0x1800653e2  lea     rax, szValueBuf
0x1800653e9  mov     [rbp+470h+var_4E0], rax
0x1800653ed  xorps   xmm0, xmm0
0x1800653f0  movups  xmmword ptr [rbp+470h+SystemTime.wYear], xmm0
0x1800653f4  lea     rcx, [rbp+470h+SystemTime]; lpSystemTime
0x1800653f8  call    cs:__imp_GetSystemTime
0x1800653fe  movaps  xmm0, xmmword ptr [rbp+470h+SystemTime.wYear]
0x180065402  movdqa  xmmword ptr [rbp+470h+var_390.wYear], xmm0
0x18006540a  lea     rax, [rbp+470h+var_390]
0x180065411  mov     [rbp+470h+var_4D8], rax
0x180065415  lea     rax, [rbp+470h+var_4F0]
0x180065419  mov     [rsp+570h+var_520], rax
0x18006541e  lea     rax, [rsp+570h+var_500]
0x180065423  mov     [rsp+570h+var_528], rax
0x180065428  lea     rax, [rbp+470h+var_4B0]
0x18006542c  mov     [rsp+570h+var_530], rax
0x180065431  lea     rax, [rbp+470h+var_4E8]
0x180065435  mov     [rsp+570h+var_538], rax
0x18006543a  lea     rax, [rsp+570h+var_4F8]
0x18006543f  mov     [rsp+570h+Description], rax
0x180065444  lea     rax, [rbp+470h+var_4E0]
0x180065448  mov     qword ptr [rsp+570h+Timeout], rax
0x18006544d  lea     rax, [rbp+470h+var_4D8]
0x180065451  mov     qword ptr [rsp+570h+IsolationFlags], rax
0x180065456  lea     rdx, unk_1802A12CE
0x18006545d  mov     rcx, r15
0x180065460  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U4@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@656@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180065465  jmp     short loc_18006548C
0x180065467  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x18006546d  test    al, 1
0x18006546f  jz      short loc_18006548C
  ... truncated ...
```
