# StateRepository::Database::dal_exec(sqlite3 *,char const *,int (*)(void *,int,char * *,char * *),void *,char * *,StateRepository::Partition,long (*)(void *),void *)

- ea: `0x18001a0e0`
- end: `0x18001abe6`
- name: `?dal_exec@Database@StateRepository@@SAJPEAUsqlite3@@PEBDP6AHPEAXHPEAPEAD3@Z23W4Partition@2@P6AJ2@Z2@Z`
- size: `2822`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `broker_com_uri`

## callers

- `0x180018c40`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x18000c3bc`
- `0x180015204`
- `0x180018224`
- `0x180018254`
- `0x180018694`
- `0x180018cb4`
- `0x180018f14`
- `0x180018f3c`
- `0x1800194f4`
- `0x180019550`
- `0x1800195ac`
- `0x180019b88`
- `0x18001a0e0`
- `0x18001b0c8`
- `0x1800264b0`
- `0x18002650c`
- `0x180027404`
- `0x180028200`
- `0x180029914`
- `0x18002a300`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a381`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001a381`
- `StateRepository.Core!sqlite3_log` at `0x18001a328`
- `StateRepository.Core!sqlite3_log` at `0x18001a6ef`
- `StateRepository.Core!sqlite3_log` at `0x18001a998`
- `StateRepository.Core!sqlite3_log` at `0x18001abab`
- `StateRepository.Core!sqlite3_log` at `0x18001a328`
- `StateRepository.Core!sqlite3_log` at `0x18001a6ef`
- `StateRepository.Core!sqlite3_log` at `0x18001a998`
- `StateRepository.Core!sqlite3_log` at `0x18001abab`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001a17e`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001a17e`
- `StateRepository.Core!sqlite3_exec` at `0x18001a3b9`
- `StateRepository.Core!sqlite3_exec` at `0x18001a3b9`

## string_xrefs

- `0x18001a160`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18001a472`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::dal_exec(
        struct sqlite3 *a1,
        struct sqlite3 *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        void (__fastcall *a7)(__int64),
        __int64 a8)
{
  struct sqlite3 *v8; // r14
  struct sqlite3 *v9; // rdi
  unsigned int v10; // r12d
  int v11; // eax
  __int64 clientdata; // rax
  unsigned __int64 *v13; // r9
  StateRepository::Time *v14; // rcx
  struct _SYSTEMTIME *v15; // rdx
  struct _SYSTEMTIME *v16; // rax
  int wMonth; // r10d
  int wDay; // r9d
  int wHour; // r8d
  int wMinute; // edx
  int wSecond; // ecx
  const char *v22; // rax
  unsigned __int64 v23; // r13
  unsigned int v24; // esi
  unsigned __int64 v25; // r15
  int v26; // eax
  int v27; // ebx
  StateRepository::Time *v28; // rcx
  unsigned __int64 v29; // rax
  int v30; // edx
  bool v31; // r13
  unsigned int v32; // eax
  int v33; // eax
  unsigned __int64 *v34; // r9
  struct _SYSTEMTIME *v35; // rax
  int v36; // edx
  const char *v37; // r13
  int v38; // r9d
  int v39; // r10d
  int v40; // r11d
  int v41; // ebx
  int v42; // edi
  int v43; // esi
  int v44; // ecx
  const char *v45; // rax
  int v46; // r14d
  const char *v47; // rcx
  unsigned __int64 *v48; // r9
  struct _SYSTEMTIME *v49; // rax
  int v50; // edx
  const char *v51; // r13
  int v52; // r9d
  int v53; // r10d
  int v54; // r11d
  int v55; // edi
  int v56; // esi
  int v57; // ecx
  const char *v58; // rax
  int v59; // r14d
  const char *v60; // rcx
  int v61; // ebx
  StateRepository::Logging *v62; // rcx
  unsigned __int64 *v63; // r9
  unsigned int v64; // edi
  struct sqlite3 *v65; // r13
  __int64 v66; // r12
  struct _SYSTEMTIME *v67; // rax
  WORD v68; // cx
  int v69; // r15d
  int v70; // r14d
  int v71; // esi
  int v72; // edi
  int v73; // ebx
  const char *v74; // rax
  int v75; // r13d
  unsigned __int64 v76; // rax
  int v78; // [rsp+20h] [rbp-150h]
  int v79; // [rsp+40h] [rbp-130h]
  int v80; // [rsp+50h] [rbp-120h]
  int v81; // [rsp+50h] [rbp-120h]
  int v82; // [rsp+B8h] [rbp-B8h]
  unsigned int busy; // [rsp+F0h] [rbp-80h]
  WORD wYear; // [rsp+F4h] [rbp-7Ch]
  int v85; // [rsp+F4h] [rbp-7Ch]
  int v86; // [rsp+F4h] [rbp-7Ch]
  WORD v87; // [rsp+F4h] [rbp-7Ch]
  int v88; // [rsp+F8h] [rbp-78h]
  int v89; // [rsp+F8h] [rbp-78h]
  int v90; // [rsp+F8h] [rbp-78h]
  int v91; // [rsp+FCh] [rbp-74h]
  int v92; // [rsp+FCh] [rbp-74h]
  int v93; // [rsp+FCh] [rbp-74h]
  int v94; // [rsp+100h] [rbp-70h]
  int v95; // [rsp+100h] [rbp-70h]
  int v96; // [rsp+100h] [rbp-70h]
  int v97; // [rsp+104h] [rbp-6Ch]
  int v98; // [rsp+104h] [rbp-6Ch]
  int v99; // [rsp+104h] [rbp-6Ch]
  int v100; // [rsp+108h] [rbp-68h]
  int v101; // [rsp+108h] [rbp-68h]
  int v102; // [rsp+108h] [rbp-68h]
  int v103; // [rsp+10Ch] [rbp-64h]
  int v104; // [rsp+10Ch] [rbp-64h]
  int v105; // [rsp+10Ch] [rbp-64h]
  int v106; // [rsp+110h] [rbp-60h]
  int v107; // [rsp+114h] [rbp-5Ch]
  unsigned int v108; // [rsp+114h] [rbp-5Ch]
  struct _GUID *v109; // [rsp+118h] [rbp-58h]
  struct _GUID *v110; // [rsp+118h] [rbp-58h]
  int v111; // [rsp+118h] [rbp-58h]
  unsigned __int64 v112; // [rsp+120h] [rbp-50h] BYREF
  unsigned __int64 v113; // [rsp+128h] [rbp-48h] BYREF
  struct sqlite3 *v114; // [rsp+130h] [rbp-40h]
  int v115[2]; // [rsp+138h] [rbp-38h]
  const char *v116; // [rsp+140h] [rbp-30h] BYREF
  __int64 v117; // [rsp+148h] [rbp-28h]
  const char *v118; // [rsp+150h] [rbp-20h]
  struct _SYSTEMTIME SystemTime; // [rsp+158h] [rbp-18h] BYREF
  char v120; // [rsp+168h] [rbp-8h]
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // [rsp+170h] [rbp+0h]
  void (__fastcall *v122)(__int64); // [rsp+178h] [rbp+8h]
  __int64 v123; // [rsp+180h] [rbp+10h]
  struct _SYSTEMTIME v124; // [rsp+188h] [rbp+18h] BYREF
  struct _SYSTEMTIME v125; // [rsp+198h] [rbp+28h] BYREF
  _BYTE v126[16]; // [rsp+1B0h] [rbp+40h] BYREF
  __int64 v127; // [rsp+1C0h] [rbp+50h]
  __int64 v128; // [rsp+1C8h] [rbp+58h]
  __int64 v129; // [rsp+1D0h] [rbp+60h]
  __int64 v130; // [rsp+1D8h] [rbp+68h]
  __int64 v131; // [rsp+1E0h] [rbp+70h]
  int v132; // [rsp+1E8h] [rbp+78h]
  __int64 v133; // [rsp+1ECh] [rbp+7Ch]
  int v134; // [rsp+1F4h] [rbp+84h]
  char v135[64]; // [rsp+200h] [rbp+90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+118h]

  v8 = a2;
  v9 = a1;
  v10 = a6;
  v122 = a7;
  v123 = a8;
  v114 = a2;
  *(_QWORD *)v115 = a1;
  if ( (dword_18004B904 & 0x4000) != 0 )
  {
    v11 = StateRepository::Database::CheckBusyStatements(a1, 1, 0);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x115C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v11,
        v78);
  }
  clientdata = sqlite3_get_clientdata(v9, "connection.id");
  v14 = (StateRepository::Time *)&_ImageBase;
  v117 = clientdata;
  if ( (dword_18004B904 & 0x40000) != 0 )
  {
    v15 = (struct _SYSTEMTIME *)qword_18004BE00[a6];
    v107 = dword_18004BE30[a6];
    v112 = 0;
    v16 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(
            &SystemTime,
            v15,
            (unsigned __int64)&v112,
            v13);
    wMonth = v16->wMonth;
    wDay = v16->wDay;
    wHour = v16->wHour;
    wMinute = v16->wMinute;
    wYear = v16->wYear;
    wSecond = v16->wSecond;
    v22 = "<null>";
    if ( v8 )
      v22 = (const char *)v8;
    v109 = (struct _GUID *)(16LL * (int)a6);
    sqlite3_log(
      0,
      "[pre-sqlite3_exec] #%u Database %llu {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} TID:%u @%04hu/%02hu/%02hu-"
      "%02hu:%02hu:%02hu.%06llu : SQL %s",
      _InterlockedIncrement(&dword_18004BFF0),
      v117,
      *(_DWORD *)((char *)xmmword_18004BE50 + (_QWORD)v109),
      *(unsigned __int16 *)((char *)xmmword_18004BE50 + (_QWORD)v109 + 4),
      *(unsigned __int16 *)((char *)xmmword_18004BE50 + (_QWORD)v109 + 6),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 8),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 9),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 10),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 11),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 12),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 13),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 14),
      *((unsigned __int8 *)xmmword_18004BE50 + (_QWORD)v109 + 15),
      v107,
      wYear,
      wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond,
      v112,
      v22);
    v9 = *(struct sqlite3 **)v115;
    v8 = v114;
    v10 = a6;
  }
  v23 = qword_18004B8F8;
  v24 = 0;
  v110 = (struct _GUID *)qword_18004B8F8;
  v116 = 0;
  v25 = 0;
  UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v14);
  v112 = 0;
  while ( 1 )
  {
    v108 = ++v24;
    if ( v24 > 1 )
    {
      if ( v122 )
        v122(v123);
      Sleep(dwMilliseconds);
    }
    wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&void sqlite3_free(void *)>>::reset(&v116);
    *(_QWORD *)&SystemTime.wHour = 0;
    *(_QWORD *)&SystemTime.wYear = &v116;
    v120 = 1;
    v26 = sqlite3_exec(v9, v8, 0, 0, &SystemTime.wHour);
    busy = v26;
    v27 = v26;
    if ( v26 > 0 )
    {
      v27 = (unsigned __int16)v26 | 0x87AF0000;
      busy = v27;
    }
    wil::details::out_param_t<wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&void sqlite3_free(void *)>>>::~out_param_t<wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&void sqlite3_free(void *)>>>(&SystemTime);
    if ( v27 >= 0 )
    {
      if ( v24 <= 1 )
        goto LABEL_49;
      memset_0(v135, 0, sizeof(v135));
      if ( IsHresultSqliteBusyOrLocked(v27) )
      {
        memset_0(v126, 0, 0x48u);
        v128 = 0;
        v130 = 0;
        v132 = 0;
        v133 = 0;
        v134 = 0;
        v127 = 0;
        v129 = 0;
        v131 = 0;
        StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
          (StateRepository::ResourcePriority::AutoPriority *)v126,
          (char (*)[64])v135);
        StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v126);
      }
      v113 = 0;
      v86 = dword_18004BE30[v10];
      v49 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(
              &v124,
              (struct _SYSTEMTIME *)qword_18004BE00[v10],
              (unsigned __int64)&v113,
              v48);
      v50 = BYTE13(xmmword_18004BE50[v10]);
      v51 = (const char *)&dword_180034EEC;
      v52 = BYTE12(xmmword_18004BE50[v10]);
      v53 = BYTE11(xmmword_18004BE50[v10]);
      v54 = BYTE10(xmmword_18004BE50[v10]);
      v55 = BYTE8(xmmword_18004BE50[v10]);
      v56 = WORD3(xmmword_18004BE50[v10]);
      v89 = v49->wYear;
      v92 = v49->wMonth;
      v95 = v49->wDay;
      v98 = v49->wHour;
      v57 = v49->wMinute;
      v104 = v49->wSecond;
      v58 = "<null>";
      if ( v8 )
        v58 = (const char *)v8;
      v101 = v57;
      v59 = WORD2(xmmword_18004BE50[v10]);
      v60 = "<no-error-message>";
      *(_QWORD *)&SystemTime.wYear = v58;
      if ( v116 )
        v60 = v116;
      v61 = BYTE9(xmmword_18004BE50[v10]);
      if ( v135[0] )
        v51 = " ";
      v118 = v60;
      v81 = v61;
      v27 = busy;
      v79 = v56;
      v24 = v108;
      v25 = v112;
      sqlite3_log(
        busy,
        "[sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}%s%s TID:%u "
        "@%04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu %s : SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        v117,
        v108,
        v112,
        LODWORD(xmmword_18004BE50[v10]),
        v59,
        v79,
        v55,
        v81,
        v54,
        v53,
        v52,
        v50,
        BYTE14(xmmword_18004BE50[v10]),
        HIBYTE(xmmword_18004BE50[v10]),
        v51,
        v135,
        v86,
        v89,
        v92,
        v95,
        v98,
        v101,
        v104,
        v113,
        v60,
        *(const char **)&SystemTime.wYear);
    }
    else
    {
      v29 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v28);
      v25 = v29 - UnbiasedInterruptTimeAsMSec;
      v112 = v29 - UnbiasedInterruptTimeAsMSec;
      busy = MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(v27, v9);
      v27 = busy;
      v31 = IsHresultSqliteBusyOrLocked(busy);
      if ( v31 )
      {
        v32 = v25 < (unsigned __int64)v110
            ? MapHresultSqliteBusyOrLockedToRetry(busy)
            : MapHresultSqliteBusyOrLockedToTimeoutExceeded(busy);
        v27 = v32;
        busy = v32;
      }
      else if ( (busy & 0xFFFF00FF) == 0x87AF000B )
      {
        StateRepository::ErrorTracking::details::TrackCorruptError((StateRepository::ErrorTracking::details *)busy, v30);
        v33 = StateRepository::Logging::ReportDatabaseCorruption(busy, "sqlite3_exec", v10, v9);
        if ( v33 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x118F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)(unsigned int)v33,
            (int)v8);
      }
      memset_0(v135, 0, sizeof(v135));
      if ( v31 )
      {
        memset_0(v126, 0, 0x48u);
        v128 = 0;
        v130 = 0;
        v132 = 0;
        v133 = 0;
        v134 = 0;
        v127 = 0;
        v129 = 0;
        v131 = 0;
        StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
          (StateRepository::ResourcePriority::AutoPriority *)v126,
          (char (*)[64])v135);
        StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v126);
      }
      if ( v24 == 1 )
      {
        v113 = 0;
        v85 = dword_18004BE30[v10];
        v35 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(
                &v125,
                (struct _SYSTEMTIME *)qword_18004BE00[v10],
                (unsigned __int64)&v113,
                v34);
        v36 = BYTE13(xmmword_18004BE50[v10]);
        v37 = (const char *)&dword_180034EEC;
        v38 = BYTE12(xmmword_18004BE50[v10]);
        v39 = BYTE11(xmmword_18004BE50[v10]);
        v40 = BYTE10(xmmword_18004BE50[v10]);
        v41 = BYTE9(xmmword_18004BE50[v10]);
        v42 = BYTE8(xmmword_18004BE50[v10]);
        v43 = WORD3(xmmword_18004BE50[v10]);
        v88 = v35->wYear;
        v91 = v35->wMonth;
        v94 = v35->wDay;
        v97 = v35->wHour;
        v44 = v35->wMinute;
        v103 = v35->wSecond;
        v45 = "<null>";
        if ( v8 )
          v45 = (const char *)v8;
        v100 = v44;
        v46 = WORD2(xmmword_18004BE50[v10]);
        v47 = "<no-error-message>";
        v118 = v45;
        if ( v116 )
          v47 = v116;
        *(_QWORD *)&SystemTime.wYear = v47;
        if ( v135[0] )
          v37 = " ";
        v80 = v41;
        v27 = busy;
        v25 = v112;
        sqlite3_log(
          busy,
          "[sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}%s%s TID:%"
          "u @%04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu %s : SQL %s",
          _InterlockedIncrement(&dword_18004BFF0),
          v117,
          1,
          v112,
          LODWORD(xmmword_18004BE50[v10]),
          v46,
          v43,
          v42,
          v80,
          v40,
          v39,
          v38,
          v36,
          BYTE14(xmmword_18004BE50[v10]),
          HIBYTE(xmmword_18004BE50[v10]),
          v37,
          v135,
          v85,
          v88,
          v91,
          v94,
          v97,
          v100,
          v103,
          v113,
          *(const char **)&SystemTime.wYear,
          v118);
        v9 = *(struct sqlite3 **)v115;
        v24 = v108;
        v8 = v114;
      }
      if ( v27 == -2018573819 )
      {
        StateRepository::Logging::FailFastBusySnapshot(v9, v8, 0, (struct sqlite3_stmt *)v34);
      }
      else if ( v27 == -2018574335 )
      {
        StateRepository::Database::FailFastIfNestingTransaction(v9);
      }
    }
    v23 = (unsigned __int64)v110;
LABEL_49:
    if ( !IsHresultSqliteBusyOrLockedOrRetry(v27) )
      break;
    StateRepository::Logging::DebugBreak(v62);
    v9 = *(struct sqlite3 **)v115;
    v8 = v114;
    v10 = a6;
    if ( v25 >= v23 )
    {
      v64 = a6;
      v65 = v114;
      StateRepository::Logging::LogBusyOrLockedTimeoutExceeded(
        (StateRepository::Logging *)(unsigned int)v27,
        *(__int64 *)v115,
        v114,
        (const char *)&xmmword_18004BE50[a6]);
      goto LABEL_53;
    }
  }
  v65 = v114;
  v64 = a6;
LABEL_53:
  if ( (dword_18004B904 & 0x80000) != 0 )
  {
    v113 = 0;
    v66 = (int)v64;
    v105 = dword_18004BE30[v64];
    v67 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(
            &v124,
            (struct _SYSTEMTIME *)qword_18004BE00[v64],
            (unsigned __int64)&v113,
            v63);
    v68 = v67->wYear;
    v69 = v67->wMonth;
    v70 = v67->wDay;
    v71 = v67->wHour;
    v72 = v67->wMinute;
    v73 = v67->wSecond;
    v74 = "<null>";
    if ( v65 )
      v74 = (const char *)v65;
    v87 = v68;
    *(_QWORD *)&SystemTime.wYear = v74;
    v75 = HIBYTE(xmmword_18004BE50[v66]);
    v102 = BYTE14(xmmword_18004BE50[v66]);
    v99 = BYTE13(xmmword_18004BE50[v66]);
    v96 = BYTE12(xmmword_18004BE50[v66]);
    v93 = BYTE11(xmmword_18004BE50[v66]);
    v90 = BYTE10(xmmword_18004BE50[v66]);
    v106 = BYTE9(xmmword_18004BE50[v66]);
    LODWORD(v112) = BYTE8(xmmword_18004BE50[v66]);
    v115[0] = WORD3(xmmword_18004BE50[v66]);
    LODWORD(v114) = WORD2(xmmword_18004BE50[v66]);
    v111 = xmmword_18004BE50[v66];
    v76 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec((StateRepository::Time *)xmmword_18004BE50);
    v82 = v73;
    v27 = busy;
    sqlite3_log(
      busy,
      "[post-sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} TID:%u @"
      "%04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu : SQL %s",
      _InterlockedIncrement(&dword_18004BFF0),
      v117,
      v108,
      v76 - UnbiasedInterruptTimeAsMSec,
      v111,
      (_DWORD)v114,
      v115[0],
      v112,
      v106,
      v90,
      v93,
      v96,
      v99,
      v102,
      v75,
      v105,
      v87,
      v69,
      v70,
      v71,
      v72,
      v82,
      v113,
      *(const char **)&SystemTime.wYear);
  }
  wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&void sqlite3_free(void *)>>::reset(&v116);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x18001a0e0  mov     [rsp-8+arg_10], rbx
0x18001a0e5  push    rbp
0x18001a0e6  push    rsi
0x18001a0e7  push    rdi
0x18001a0e8  push    r12
0x18001a0ea  push    r13
0x18001a0ec  push    r14
0x18001a0ee  push    r15
0x18001a0f0  lea     rbp, [rsp-0E0h]
0x18001a0f8  sub     rsp, 250h
0x18001a0ff  mov     rax, cs:__security_cookie
0x18001a106  xor     rax, rsp
0x18001a109  mov     [rbp+110h+var_40], rax
0x18001a110  test    cs:dword_18004B904, 4000h
0x18001a11a  mov     r14, rdx
0x18001a11d  mov     rax, [rbp+110h+arg_30]
0x18001a124  mov     rdi, rcx
0x18001a127  movsxd  r12, [rbp+110h+arg_28]
0x18001a12e  mov     [rbp+110h+var_108], rax
0x18001a132  mov     rax, [rbp+110h+arg_38]
0x18001a139  mov     [rbp+110h+var_100], rax
0x18001a13d  mov     [rbp+110h+var_150], rdx
0x18001a141  mov     qword ptr [rbp+110h+var_148], rcx
0x18001a145  mov     [rbp+110h+var_170], r12d
0x18001a149  jz      short loc_18001A174
0x18001a14b  xor     r8d, r8d; unsigned int *
0x18001a14e  mov     dl, 1; bool
0x18001a150  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x18001a155  test    eax, eax
0x18001a157  jns     short loc_18001A174
0x18001a159  mov     rcx, [rbp+118h]; this
0x18001a160  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001a167  mov     r9d, eax; char *
0x18001a16a  mov     edx, 115Ch; void *
0x18001a16f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a174  lea     rdx, aConnectionId; "connection.id"
0x18001a17b  mov     rcx, rdi
0x18001a17e  call    cs:__imp_sqlite3_get_clientdata
0x18001a184  test    cs:dword_18004B904, 40000h
0x18001a18e  lea     rcx, __ImageBase
0x18001a195  mov     [rbp+110h+var_138], rax
0x18001a199  jz      loc_18001A33A
0x18001a19f  mov     eax, rva dword_18004BE30[rcx+r12*4]
0x18001a1a7  lea     r8, [rbp+110h+var_160]; unsigned __int64
0x18001a1ab  mov     rdx, rva qword_18004BE00[rcx+r12*8]; retstr
0x18001a1b3  mov     r13, r12
0x18001a1b6  shl     r13, 4
0x18001a1ba  lea     rcx, [rbp+110h+SystemTime]; lpSystemTime
0x18001a1be  mov     [rbp+110h+var_16C+4], r13
0x18001a1c2  mov     dword ptr [rbp+110h+var_16C], eax
0x18001a1c5  mov     [rbp+110h+var_160], 0
0x18001a1cd  call    ?ToSystemTimeAndMicroseconds@Temporal@DataType@StateRepository@@YA?AU_SYSTEMTIME@@_KAEA_K@Z; StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(unsigned __int64,unsigned __int64 &)
0x18001a1d2  lea     r11, xmmword_18004BE50
0x18001a1d9  test    r14, r14
0x18001a1dc  movzx   ebx, byte ptr [r11+r13+0Fh]
0x18001a1e2  movzx   edi, byte ptr [r11+r13+0Eh]
0x18001a1e8  movzx   esi, byte ptr [r11+r13+0Dh]
0x18001a1ee  movzx   r15d, byte ptr [r11+r13+0Bh]
0x18001a1f4  movzx   r12d, byte ptr [r11+r13+0Ah]
0x18001a1fa  movzx   ecx, word ptr [rax]
0x18001a1fd  movzx   r10d, word ptr [rax+2]
0x18001a202  movzx   r9d, word ptr [rax+6]
0x18001a207  movzx   r8d, word ptr [rax+8]
0x18001a20c  movzx   edx, word ptr [rax+0Ah]
0x18001a210  mov     [rbp+110h+var_190], ebx
0x18001a213  lea     rbx, xmmword_18004BE50
0x18001a21a  mov     word ptr [rbp+110h+var_18C], cx
0x18001a21e  movzx   ecx, word ptr [rax+0Ch]
0x18001a222  lea     rax, aNull; "<null>"
0x18001a229  cmovnz  rax, r14
0x18001a22d  mov     [rbp+110h+var_188], edi
0x18001a230  movzx   r14d, byte ptr [r11+r13+0Ch]
0x18001a236  lea     rdi, xmmword_18004BE50
0x18001a23d  movzx   r13d, byte ptr [r11+r13+9]
0x18001a243  mov     r11, [rbp+110h+var_16C+4]
0x18001a247  movzx   r11d, byte ptr [r11+rbx+8]
0x18001a24d  mov     rbx, [rbp+110h+var_16C+4]
0x18001a251  mov     [rbp+110h+var_184], r11d
0x18001a255  movzx   r11d, word ptr [rbx+rdi+6]
0x18001a25b  mov     [rbp+110h+var_180], r11d
0x18001a25f  movzx   r11d, word ptr [rbx+rdi+4]
0x18001a265  mov     [rbp+110h+var_17C], r11d
0x18001a269  mov     r11d, [rbx+rdi]
0x18001a26d  mov     [rbp+110h+var_178], r11d
0x18001a271  mov     r11d, 1
0x18001a277  lock xadd cs:dword_18004BFF0, r11d
0x18001a280  mov     ebx, [rbp+110h+var_190]
0x18001a283  inc     r11d
0x18001a286  mov     edi, [rbp+110h+var_188]
0x18001a289  mov     [rsp+280h+var_1C8], rax
0x18001a291  mov     rax, [rbp+110h+var_160]
0x18001a295  mov     [rsp+280h+var_1D0], rax
0x18001a29d  mov     eax, dword ptr [rbp+110h+var_16C]
0x18001a2a0  mov     [rsp+280h+var_1D8], ecx
0x18001a2a7  xor     ecx, ecx
0x18001a2a9  mov     [rsp+280h+var_1E0], edx
0x18001a2b0  lea     rdx, aPreSqlite3Exec; "[pre-sqlite3_exec] #%u Database %llu {%"...
0x18001a2b7  mov     [rsp+280h+var_1E8], r8d
0x18001a2bf  mov     dword ptr [rsp+280h+var_1F0], r9d
0x18001a2c7  mov     r9, [rbp+110h+var_138]
0x18001a2cb  mov     dword ptr [rsp+280h+var_1F8], r10d
0x18001a2d3  mov     [rbp+110h+var_174], r11d
0x18001a2d7  movzx   r11d, word ptr [rbp+110h+var_18C]
0x18001a2dc  mov     r8d, [rbp+110h+var_174]
0x18001a2e0  mov     [rsp+280h+var_200], r11d
0x18001a2e8  mov     [rsp+280h+var_208], eax
0x18001a2ec  mov     eax, [rbp+110h+var_184]
0x18001a2ef  mov     [rsp+280h+var_210], ebx
0x18001a2f3  mov     [rsp+280h+var_218], edi
0x18001a2f7  mov     [rsp+280h+var_220], esi
0x18001a2fb  mov     [rsp+280h+var_228], r14d
0x18001a300  mov     [rsp+280h+var_230], r15d
0x18001a305  mov     [rsp+280h+var_238], r12d
0x18001a30a  mov     [rsp+280h+var_240], r13d
0x18001a30f  mov     [rsp+280h+var_248], eax
0x18001a313  mov     eax, [rbp+110h+var_180]
0x18001a316  mov     dword ptr [rsp+280h+var_250], eax
0x18001a31a  mov     eax, [rbp+110h+var_17C]
0x18001a31d  mov     dword ptr [rsp+280h+var_258], eax
0x18001a321  mov     eax, [rbp+110h+var_178]
0x18001a324  mov     dword ptr [rsp+280h+var_260], eax
0x18001a328  call    cs:__imp_sqlite3_log
0x18001a32e  mov     rdi, qword ptr [rbp+110h+var_148]
0x18001a332  mov     r14, [rbp+110h+var_150]
0x18001a336  mov     r12d, [rbp+110h+var_170]
0x18001a33a  mov     r13, cs:qword_18004B8F8
0x18001a341  xor     esi, esi
0x18001a343  mov     [rbp+110h+var_16C+4], r13
0x18001a347  mov     [rbp+110h+var_140], 0
0x18001a34f  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001a354  xor     r15d, r15d
0x18001a357  mov     [rbp+110h+var_110], rax
0x18001a35b  mov     [rbp+110h+var_160], r15
0x18001a35f  inc     esi
0x18001a361  mov     dword ptr [rbp+110h+var_16C], esi
0x18001a364  cmp     esi, 1
0x18001a367  jbe     short loc_18001A387
0x18001a369  mov     rax, [rbp+110h+var_108]
0x18001a36d  test    rax, rax
0x18001a370  jz      short loc_18001A37B
0x18001a372  mov     rcx, [rbp+110h+var_100]
0x18001a376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a37b  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x18001a381  call    cs:__imp_Sleep
0x18001a387  lea     rcx, [rbp+110h+var_140]
0x18001a38b  call    ?reset@?$unique_ptr@$$BY0A@DU?$function_deleter@P6AXPEAX@Z$1?sqlite3_free@@YAX0@Z@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&sqlite3_free(void *)>>::reset(std::nullptr_t)
0x18001a390  lea     rax, [rbp+110h+var_140]
0x18001a394  mov     qword ptr [rbp+110h+SystemTime.wHour], 0
0x18001a39c  mov     qword ptr [rbp+110h+SystemTime.wYear], rax
0x18001a3a0  xor     r9d, r9d
0x18001a3a3  lea     rax, [rbp+110h+SystemTime.wHour]
0x18001a3a7  mov     [rbp+110h+var_118], 1
0x18001a3ab  xor     r8d, r8d
0x18001a3ae  mov     [rsp+280h+var_260], rax
0x18001a3b3  mov     rdx, r14
0x18001a3b6  mov     rcx, rdi
0x18001a3b9  call    cs:__imp_sqlite3_exec
0x18001a3bf  mov     [rbp+110h+var_190], eax
0x18001a3c2  mov     ebx, eax
0x18001a3c4  test    eax, eax
0x18001a3c6  jle     short loc_18001A3D4
0x18001a3c8  movzx   ebx, ax
0x18001a3cb  or      ebx, 87AF0000h
0x18001a3d1  mov     [rbp+110h+var_190], ebx
0x18001a3d4  lea     rcx, [rbp+110h+SystemTime]
0x18001a3d8  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@DU?$function_deleter@P6AXPEAX@Z$1?sqlite3_free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&sqlite3_free(void *)>>>::~out_param_t<wistd::unique_ptr<char [0],wil::function_deleter<void (*)(void *),&sqlite3_free(void *)>>>(void)
0x18001a3dd  test    ebx, ebx
0x18001a3df  jns     loc_18001A734
0x18001a3e5  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001a3ea  mov     r15, rax
0x18001a3ed  mov     rdx, rdi; struct sqlite3 *
0x18001a3f0  sub     r15, [rbp+110h+var_110]
0x18001a3f4  mov     ecx, ebx; int
0x18001a3f6  mov     [rbp+110h+var_160], r15
0x18001a3fa  call    ?MapSqliteBusySnapshotToSqliteBusyIfRaceCondition@@YAJJPEAUsqlite3@@@Z; MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(long,sqlite3 *)
0x18001a3ff  mov     ecx, eax; int
0x18001a401  mov     [rbp+110h+var_190], eax
0x18001a404  mov     ebx, eax
0x18001a406  call    ?IsHresultSqliteBusyOrLocked@@YA_NJ@Z; IsHresultSqliteBusyOrLocked(long)
0x18001a40b  mov     r13b, al
0x18001a40e  test    al, al
0x18001a410  jz      short loc_18001A42D
0x18001a412  mov     ecx, ebx; int
0x18001a414  cmp     r15, [rbp+110h+var_16C+4]
0x18001a418  jb      short loc_18001A421
0x18001a41a  call    ?MapHresultSqliteBusyOrLockedToTimeoutExceeded@@YAJJ@Z; MapHresultSqliteBusyOrLockedToTimeoutExceeded(long)
0x18001a41f  jmp     short loc_18001A426
0x18001a421  call    ?MapHresultSqliteBusyOrLockedToRetry@@YAJJ@Z; MapHresultSqliteBusyOrLockedToRetry(long)
0x18001a426  mov     ebx, eax
0x18001a428  mov     [rbp+110h+var_190], eax
0x18001a42b  jmp     short loc_18001A486
0x18001a42d  mov     eax, ebx
0x18001a42f  and     eax, 0FFFF00FFh
0x18001a434  cmp     eax, 87AF000Bh
0x18001a439  jnz     short loc_18001A486
0x18001a43b  mov     ecx, ebx; this
0x18001a43d  call    ?TrackCorruptError@details@ErrorTracking@StateRepository@@YAXJ@Z; StateRepository::ErrorTracking::details::TrackCorruptError(long)
0x18001a442  mov     eax, esi
0x18001a444  lea     rdx, aSqlite3Exec; "sqlite3_exec"
0x18001a44b  mov     [rsp+280h+var_250], r15
0x18001a450  mov     r9, rdi
0x18001a453  mov     [rsp+280h+var_258], rax
0x18001a458  mov     r8d, r12d
0x18001a45b  mov     ecx, ebx
0x18001a45d  mov     [rsp+280h+var_260], r14; int
0x18001a462  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x18001a467  test    eax, eax
0x18001a469  jns     short loc_18001A486
0x18001a46b  mov     rcx, [rbp+118h]; this
0x18001a472  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001a479  mov     r9d, eax; char *
0x18001a47c  mov     edx, 118Fh; void *
0x18001a481  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001a486  xor     edx, edx; Val
0x18001a488  lea     rcx, [rbp+110h+var_80]; void *
0x18001a48f  lea     r8d, [rdx+40h]; Size
0x18001a493  call    memset_0
0x18001a498  test    r13b, r13b
0x18001a49b  jz      short loc_18001A507
0x18001a49d  xor     edx, edx; Val
0x18001a49f  lea     rcx, [rbp+110h+var_D0]; void *
0x18001a4a3  lea     r8d, [rdx+48h]; Size
0x18001a4a7  call    memset_0
0x18001a4ac  xor     r13d, r13d
0x18001a4af  lea     rdx, [rbp+110h+var_80]; char (*)[64]
0x18001a4b6  xor     eax, eax
0x18001a4b8  mov     [rbp+110h+var_B8], r13
0x18001a4bc  mov     [rbp+110h+var_A8], r13
0x18001a4c0  lea     rcx, [rbp+110h+var_D0]; this
0x18001a4c4  mov     [rbp+110h+var_98], r13
0x18001a4c8  mov     qword ptr [rbp+110h+var_90], r13
0x18001a4cf  mov     byte ptr [rbp+110h+var_B8], r13b
0x18001a4d3  mov     dword ptr [rbp+110h+var_B8+4], eax
0x18001a4d6  mov     byte ptr [rbp+110h+var_A8], r13b
0x18001a4da  mov     dword ptr [rbp+110h+var_A8+4], eax
0x18001a4dd  mov     byte ptr [rbp+110h+var_98], r13b
0x18001a4e1  mov     [rbp+110h+var_98+4], rax
0x18001a4e5  mov     [rbp+110h+var_90+4], eax
0x18001a4eb  mov     [rbp+110h+var_C0], r13
0x18001a4ef  mov     [rbp+110h+var_B0], r13
0x18001a4f3  mov     [rbp+110h+var_A0], r13
0x18001a4f7  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18001a4fc  lea     rcx, [rbp+110h+var_D0]; this
0x18001a500  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x18001a505  jmp     short loc_18001A50A
0x18001a507  xor     r13d, r13d
0x18001a50a  cmp     esi, 1
0x18001a50d  jnz     loc_18001A700
0x18001a513  movsxd  rdx, r12d
0x18001a516  lea     rcx, __ImageBase
0x18001a51d  mov     r15, rdx
0x18001a520  mov     [rbp+110h+var_158], r13
0x18001a524  lea     r8, [rbp+110h+var_158]; unsigned __int64
0x18001a528  add     r15, r15
0x18001a52b  mov     eax, rva dword_18004BE30[rcx+rdx*4]
0x18001a532  mov     rdx, rva qword_18004BE00[rcx+rdx*8]; retstr
0x18001a53a  lea     rcx, [rbp+110h+var_E8]; lpSystemTime
0x18001a53e  mov     [rbp+110h+var_18C], eax
0x18001a541  call    ?ToSystemTimeAndMicroseconds@Temporal@DataType@StateRepository@@YA?AU_SYSTEMTIME@@_KAEA_K@Z; StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(unsigned __int64,unsigned __int64 &)
0x18001a546  lea     r8, xmmword_18004BE50
0x18001a54d  test    r14, r14
0x18001a550  movzx   edx, byte ptr [r8+r15*8+0Dh]
0x18001a556  lea     r13, dword_180034EEC
0x18001a55d  movzx   r9d, byte ptr [r8+r15*8+0Ch]
0x18001a563  mov     r12d, 1
0x18001a569  movzx   ecx, word ptr [rax]
0x18001a56c  movzx   r10d, byte ptr [r8+r15*8+0Bh]
0x18001a572  movzx   r11d, byte ptr [r8+r15*8+0Ah]
0x18001a578  movzx   ebx, byte ptr [r8+r15*8+9]
0x18001a57e  movzx   edi, byte ptr [r8+r15*8+8]
0x18001a584  movzx   esi, word ptr [r8+r15*8+6]
0x18001a58a  mov     [rbp+110h+var_188], ecx
0x18001a58d  movzx   ecx, word ptr [rax+2]
0x18001a591  mov     [rbp+110h+var_184], ecx
0x18001a594  movzx   ecx, word ptr [rax+6]
0x18001a598  mov     [rbp+110h+var_180], ecx
0x18001a59b  movzx   ecx, word ptr [rax+8]
0x18001a59f  mov     [rbp+110h+var_17C], ecx
0x18001a5a2  movzx   ecx, word ptr [rax+0Ah]
0x18001a5a6  movzx   eax, word ptr [rax+0Ch]
0x18001a5aa  mov     [rbp+110h+var_174], eax
0x18001a5ad  lea     rax, aNull; "<null>"
0x18001a5b4  cmovnz  rax, r14
0x18001a5b8  mov     [rbp+110h+var_178], ecx
0x18001a5bb  movzx   r14d, word ptr [r8+r15*8+4]
0x18001a5c1  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18001a5c8  mov     [rbp+110h+var_130], rax
0x18001a5cc  mov     rax, [rbp+110h+var_140]
0x18001a5d0  test    rax, rax
0x18001a5d3  cmovnz  rcx, rax
0x18001a5d7  cmp     [rbp+110h+var_80], 0
0x18001a5de  lea     rax, asc_18003D024; " "
0x18001a5e5  mov     qword ptr [rbp+110h+SystemTime.wYear], rcx
0x18001a5e9  movzx   ecx, byte ptr [r8+r15*8+0Eh]
0x18001a5ef  cmovnz  r13, rax
0x18001a5f3  movzx   eax, byte ptr [r8+r15*8+0Fh]
0x18001a5f9  mov     r15d, [r8+r15*8]
0x18001a5fd  lock xadd cs:dword_18004BFF0, r12d
0x18001a606  mov     r8, [rbp+110h+var_130]
0x18001a60a  mov     [rsp+280h+var_1A0], r8
  ... truncated ...
```
