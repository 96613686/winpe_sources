# StateRepository::Database::dal_exec(sqlite3 *,char const *,int (*)(void *,int,char * *,char * *),void *,char * *,StateRepository::Partition,long (*)(void *),void *)

- ea: `0x1800fce08`
- end: `0x1800fdaf7`
- name: `?dal_exec@Database@StateRepository@@SAJPEAUsqlite3@@PEBDP6AHPEAXHPEAPEAD3@Z23W4Partition@2@P6AJ2@Z2@Z`
- size: `3311`
- prototype: `__int64 __fastcall(struct sqlite3 *, struct sqlite3 *, __int64, unsigned __int64 *, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x1800f9300`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180005980`
- `0x180007280`
- `0x18000ecf0`
- `0x18000f220`
- `0x180016970`
- `0x180022d00`
- `0x1800f7630`
- `0x1800f85a8`
- `0x1800f89f4`
- `0x1800f9468`
- `0x1800fc948`
- `0x1800fce08`
- `0x180102b2c`
- `0x180103210`
- `0x180103cd8`
- `0x180106704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800fd08e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800fd08e`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800fd63a`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800fd63a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd04c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd113`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd9c6`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd04c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd113`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800fd9c6`

## string_xrefs

- `0x1800fce71`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fd2a1`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::dal_exec(
        struct sqlite3 *a1,
        struct sqlite3 *a2,
        __int64 a3,
        unsigned __int64 *a4,
        __int64 a5,
        unsigned int a6)
{
  struct sqlite3 *v6; // r15
  StateRepository::Logging *v7; // r14
  int v8; // eax
  int v9; // eax
  struct _SYSTEMTIME *v10; // rdx
  __int64 v11; // r13
  struct _SYSTEMTIME *v12; // rax
  int v13; // edi
  int v14; // esi
  WORD wYear; // cx
  int wMonth; // r10d
  int wDay; // r9d
  int wHour; // r8d
  int wMinute; // edx
  int v20; // r14d
  int wSecond; // ecx
  const char *v22; // rax
  int v23; // r11d
  int v24; // r15d
  int v25; // r12d
  int v26; // r13d
  unsigned int v27; // r13d
  unsigned __int128 v28; // rax
  __int64 v29; // rdi
  const char *v30; // rcx
  int v31; // eax
  unsigned __int64 *v32; // r9
  signed int v33; // ebx
  __int64 v34; // rcx
  unsigned __int64 v35; // rsi
  char v36; // r12
  unsigned int v37; // edi
  volatile signed __int64 *v38; // rax
  __int64 j; // rdx
  __int64 stmt; // rax
  __int64 v41; // rdx
  __int64 v42; // r8
  __int64 v43; // rdi
  int v44; // eax
  __int64 v45; // r15
  struct _SYSTEMTIME *v46; // rdx
  struct _SYSTEMTIME *v47; // rax
  int v48; // edx
  const char *v49; // r13
  int v50; // r9d
  int v51; // r10d
  int v52; // r11d
  int v53; // edi
  int v54; // esi
  int v55; // r14d
  int v56; // ecx
  const char *v57; // rax
  const char *v58; // rcx
  int v59; // ebx
  unsigned int v60; // ebx
  __int64 v61; // rdi
  __int64 v62; // r12
  unsigned __int64 *v63; // r9
  struct _SYSTEMTIME *v64; // rdx
  struct _SYSTEMTIME *v65; // rax
  int v66; // r9d
  const char *v67; // r13
  int v68; // r10d
  const char *v69; // rsi
  int v70; // r11d
  int v71; // ebx
  int v72; // edi
  int v73; // r14d
  int v74; // r15d
  int v75; // ecx
  const char *v76; // rax
  int v77; // esi
  int v78; // ecx
  __int64 v79; // r13
  struct _SYSTEMTIME *v80; // rdx
  struct _SYSTEMTIME *v81; // rax
  int v82; // r12d
  int v83; // r15d
  int v84; // r14d
  int v85; // esi
  int v86; // edi
  int v87; // ebx
  const char *v88; // rax
  int v89; // eax
  int v90; // r13d
  const char *v91; // rcx
  struct _GUID *v93; // [rsp+20h] [rbp-150h]
  int v94; // [rsp+40h] [rbp-130h]
  int v95; // [rsp+48h] [rbp-128h]
  int v96; // [rsp+B0h] [rbp-C0h]
  WORD v97; // [rsp+F0h] [rbp-80h]
  unsigned int v98; // [rsp+F0h] [rbp-80h]
  unsigned __int64 UnbiasedTime; // [rsp+F8h] [rbp-78h] BYREF
  unsigned int v100; // [rsp+100h] [rbp-70h]
  unsigned int v101; // [rsp+104h] [rbp-6Ch]
  int v102; // [rsp+108h] [rbp-68h]
  int v103; // [rsp+10Ch] [rbp-64h]
  int v104; // [rsp+110h] [rbp-60h]
  int v105; // [rsp+114h] [rbp-5Ch]
  int v106; // [rsp+118h] [rbp-58h]
  signed __int32 v107; // [rsp+11Ch] [rbp-54h]
  unsigned int v108; // [rsp+120h] [rbp-50h]
  unsigned __int64 v109; // [rsp+128h] [rbp-48h] BYREF
  unsigned __int64 v110; // [rsp+130h] [rbp-40h] BYREF
  const char *v111; // [rsp+138h] [rbp-38h] BYREF
  StateRepository::Logging *v112; // [rsp+140h] [rbp-30h]
  struct sqlite3 *v113; // [rsp+148h] [rbp-28h]
  unsigned __int64 v114; // [rsp+150h] [rbp-20h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+158h] [rbp-18h] BYREF
  char v116; // [rsp+168h] [rbp-8h]
  __int64 i; // [rsp+170h] [rbp+0h]
  struct _SYSTEMTIME v118; // [rsp+178h] [rbp+8h] BYREF
  _BYTE v119[16]; // [rsp+190h] [rbp+20h] BYREF
  __int64 v120; // [rsp+1A0h] [rbp+30h]
  __int64 v121; // [rsp+1A8h] [rbp+38h]
  __int64 v122; // [rsp+1B0h] [rbp+40h]
  __int64 v123; // [rsp+1B8h] [rbp+48h]
  __int64 v124; // [rsp+1C0h] [rbp+50h]
  int v125; // [rsp+1C8h] [rbp+58h]
  __int64 v126; // [rsp+1CCh] [rbp+5Ch]
  int v127; // [rsp+1D4h] [rbp+64h]
  char v128[64]; // [rsp+1E0h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+F8h]

  v6 = a2;
  v7 = a1;
  v100 = a6;
  v113 = a2;
  v112 = a1;
  if ( (dword_18013F948 & 0x4000) != 0 )
  {
    v8 = StateRepository::Database::CheckBusyStatements(a1, 1, 0);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x115C,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v8);
  }
  if ( (dword_18013F948 & 0x40000) != 0 )
  {
    v9 = dword_180140320[a6];
    v10 = (struct _SYSTEMTIME *)qword_1801402F0[a6];
    v11 = (int)a6;
    UnbiasedTime = v11 * 16;
    v101 = v9;
    v110 = 0;
    v12 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(
            &SystemTime,
            v10,
            (unsigned __int64)&v110,
            a4);
    v13 = BYTE14(xmmword_180140340[v11]);
    v14 = BYTE13(xmmword_180140340[v11]);
    wYear = v12->wYear;
    wMonth = v12->wMonth;
    wDay = v12->wDay;
    wHour = v12->wHour;
    wMinute = v12->wMinute;
    v20 = BYTE12(xmmword_180140340[v11]);
    v108 = HIBYTE(xmmword_180140340[v11]);
    v97 = wYear;
    wSecond = v12->wSecond;
    v22 = "<null>";
    v23 = BYTE8(xmmword_180140340[v11]);
    if ( v6 )
      v22 = (const char *)v6;
    v24 = BYTE11(xmmword_180140340[v11]);
    v25 = BYTE10(xmmword_180140340[v11]);
    v26 = BYTE9(xmmword_180140340[v11]);
    v103 = *((unsigned __int8 *)xmmword_180140340 + UnbiasedTime + 8);
    v102 = v13;
    v104 = *(unsigned __int16 *)((char *)xmmword_180140340 + UnbiasedTime + 6);
    v105 = *(unsigned __int16 *)((char *)xmmword_180140340 + UnbiasedTime + 4);
    v106 = *(_DWORD *)((char *)xmmword_180140340 + UnbiasedTime);
    v107 = _InterlockedIncrement(&dword_180140410);
    sqlite3_log(
      0,
      "[pre-sqlite3_exec] #%u Database %llu {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} TID:%u @%04hu/%02hu/%02hu-"
      "%02hu:%02hu:%02hu.%06llu : SQL %s",
      v107,
      0,
      v106,
      v105,
      v104,
      v23,
      v26,
      v25,
      v24,
      v20,
      v14,
      v13,
      v108,
      v101,
      v97,
      wMonth,
      wDay,
      wHour,
      wMinute,
      wSecond,
      v110,
      v22);
    v7 = v112;
    v6 = v113;
  }
  v109 = qword_18013F940;
  v111 = 0;
  v27 = 0;
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v28 = UnbiasedTime * (unsigned __int128)0x346DC5D63886594BuLL;
  UnbiasedTime = 0;
  v29 = *((_QWORD *)&v28 + 1) >> 11;
  for ( i = *((_QWORD *)&v28 + 1) >> 11; ; v29 = i )
  {
    v108 = ++v27;
    if ( v27 > 1 )
      Sleep(dwMilliseconds);
    v30 = v111;
    v111 = 0;
    if ( v30 )
      sqlite3_free(v30);
    *(_QWORD *)&SystemTime.wHour = 0;
    *(_QWORD *)&SystemTime.wYear = &v111;
    v116 = 1;
    v31 = sqlite3_exec((_DWORD)v7, (_DWORD)v6, 0, 0, (__int64)&SystemTime.wHour);
    v101 = v31;
    v33 = v31;
    if ( v31 > 0 )
    {
      v33 = (unsigned __int16)v31 | 0x87AF0000;
      v101 = v33;
    }
    if ( v116 )
    {
      v34 = **(_QWORD **)&SystemTime.wYear;
      **(_QWORD **)&SystemTime.wYear = *(_QWORD *)&SystemTime.wHour;
      if ( v34 )
        sqlite3_free(v34);
    }
    if ( v33 >= 0 )
      break;
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    v35 = UnbiasedTime / 0x2710 - v29;
    UnbiasedTime = v35;
    if ( v33 == -2018573819 )
    {
      if ( (unsigned int)sqlite3_get_autocommit(v7) )
      {
        for ( j = 0; ; j = v43 )
        {
          stmt = sqlite3_next_stmt(v7, j);
          v43 = stmt;
          if ( !stmt )
            break;
          if ( (unsigned int)sqlite3_stmt_busy(stmt, v41, v42) )
            goto LABEL_23;
        }
        v33 = -2018574331;
LABEL_34:
        v36 = 1;
        if ( v35 < v109 )
        {
          switch ( v33 )
          {
            case -2018574331:
              v98 = -2140733433;
              break;
            case -2018574330:
              v98 = -2140733431;
              break;
            case -2018574075:
              v98 = -2140733432;
              break;
            case -2018574074:
              v98 = -2140733430;
              break;
            default:
LABEL_39:
              v98 = v33;
              break;
          }
        }
        else
        {
          switch ( v33 )
          {
            case -2018574331:
              v98 = -2140733428;
              break;
            case -2018574330:
              v98 = -2140733426;
              break;
            case -2018574075:
              v98 = -2140733427;
              break;
            case -2018574074:
              v98 = -2140733425;
              break;
            default:
              goto LABEL_39;
          }
        }
        v37 = v98;
        goto LABEL_61;
      }
      v33 = -2018573819;
    }
    else if ( v33 == -2018574331 || v33 == -2018574075 )
    {
      goto LABEL_34;
    }
LABEL_23:
    if ( (v33 & 0xFFFF00FF) == 0x87AF0006 )
      goto LABEL_34;
    v36 = 0;
    v98 = v33;
    v37 = v33;
    if ( (v33 & 0xFFFF00FF) == 0x87AF000B )
    {
      switch ( v33 )
      {
        case -2018574325:
          v38 = &qword_180140510;
          break;
        case -2018573557:
          v38 = &qword_180140518;
          break;
        case -2018573813:
          v38 = &qword_180140500;
          break;
        default:
          v38 = &qword_180140508;
          if ( v33 != -2018574069 )
            v38 = &qword_1801404F8;
          break;
      }
      _InterlockedIncrement64(v38);
      v93 = (struct _GUID *)v6;
      v44 = StateRepository::Logging::ReportDatabaseCorruption((unsigned int)v33, "sqlite3_exec", v100, v7);
      if ( v44 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x118F,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v44);
    }
LABEL_61:
    memset_0(v128, 0, sizeof(v128));
    if ( v36 )
    {
      memset_0(v119, 0, 0x48u);
      v121 = 0;
      v123 = 0;
      v125 = 0;
      v126 = 0;
      v127 = 0;
      v120 = 0;
      v122 = 0;
      v124 = 0;
      StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
        (StateRepository::ResourcePriority::AutoPriority *)v119,
        (char (*)[64])v128);
      StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v119);
    }
    if ( v27 == 1 )
    {
      v110 = 0;
      v45 = (int)v100;
      v46 = (struct _SYSTEMTIME *)qword_1801402F0[v100];
      v101 = dword_180140320[v100];
      v47 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(&v118, v46, (unsigned __int64)&v110, v32);
      v48 = BYTE13(xmmword_180140340[v45]);
      v49 = byte_180122168;
      v50 = BYTE12(xmmword_180140340[v45]);
      v51 = BYTE11(xmmword_180140340[v45]);
      v52 = BYTE10(xmmword_180140340[v45]);
      v53 = BYTE8(xmmword_180140340[v45]);
      v54 = WORD3(xmmword_180140340[v45]);
      v55 = WORD2(xmmword_180140340[v45]);
      v102 = v47->wYear;
      v103 = v47->wMonth;
      v104 = v47->wDay;
      v105 = v47->wHour;
      v56 = v47->wMinute;
      v107 = v47->wSecond;
      v57 = "<null>";
      v106 = v56;
      if ( v113 )
        v57 = (const char *)v113;
      v58 = "<no-error-message>";
      v114 = (unsigned __int64)v57;
      if ( v111 )
        v58 = v111;
      v59 = BYTE9(xmmword_180140340[v45]);
      if ( v128[0] )
        v49 = " ";
      *(_QWORD *)&SystemTime.wYear = v58;
      v95 = v53;
      v37 = v98;
      v94 = v54;
      v35 = UnbiasedTime;
      sqlite3_log(
        v98,
        "[sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}%s%s TID:%u "
        "@%04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu %s : SQL %s",
        _InterlockedIncrement(&dword_180140410),
        0,
        1,
        UnbiasedTime,
        LODWORD(xmmword_180140340[v45]),
        v55,
        v94,
        v95,
        v59,
        v52,
        v51,
        v50,
        v48,
        BYTE14(xmmword_180140340[v45]),
        HIBYTE(xmmword_180140340[v45]),
        v49,
        v128,
        v101,
        v102,
        v103,
        v104,
        v105,
        v106,
        v107,
        v110,
        v58,
        (const char *)v114);
      v7 = v112;
      v6 = v113;
      v27 = v108;
    }
    if ( v37 == -2018573819 )
    {
      StateRepository::Logging::FailFastBusySnapshot(v7, v6, 0, (struct sqlite3_stmt *)v32);
      goto LABEL_98;
    }
    if ( v37 == -2018574335 )
    {
      StateRepository::Database::FailFastIfNestingTransaction(v7);
      v98 = -2018574335;
    }
    else
    {
      v98 = v37;
      UnbiasedTime = v35;
      if ( v37 == -2018574330
        || v37 == -2018574074
        || v37 == -2140733433
        || v37 == -2140733432
        || v37 == -2140733431
        || v37 == -2140733430
        || v37 == -2140733428
        || v37 == -2140733427 )
      {
        goto LABEL_83;
      }
    }
    if ( v37 + 2140733426 > 1 )
      goto LABEL_98;
LABEL_83:
    if ( (dword_18013F948 & 0x1000) != 0 )
      DebugBreak();
    if ( v35 >= v109 )
    {
      v60 = v100;
      StateRepository::Logging::LogBusyOrLockedTimeoutExceeded(
        (StateRepository::Logging *)v37,
        (int)v7,
        v6,
        (const char *)&xmmword_180140340[v100],
        v93);
      goto LABEL_99;
    }
  }
  v98 = v33;
  v37 = v33;
  if ( v27 > 1 )
  {
    v61 = (int)v100;
    v62 = (int)v100;
    memset_0(v128, 0, sizeof(v128));
    if ( (v33 & 0xFFFF00FF) == 0x87AF0006 )
    {
      memset_0(v119, 0, 0x48u);
      v121 = 0;
      v123 = 0;
      v125 = 0;
      v126 = 0;
      v127 = 0;
      v120 = 0;
      v122 = 0;
      v124 = 0;
      StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
        (StateRepository::ResourcePriority::AutoPriority *)v119,
        (char (*)[64])v128);
      StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v119);
    }
    v109 = 0;
    v64 = (struct _SYSTEMTIME *)qword_1801402F0[v61];
    LODWORD(v112) = dword_180140320[v61];
    v65 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(&v118, v64, (unsigned __int64)&v109, v63);
    v66 = BYTE13(xmmword_180140340[v62]);
    v67 = "<null>";
    v68 = BYTE12(xmmword_180140340[v62]);
    v69 = "<no-error-message>";
    v70 = BYTE11(xmmword_180140340[v62]);
    v71 = BYTE10(xmmword_180140340[v62]);
    if ( v6 )
      v67 = (const char *)v6;
    v72 = BYTE9(xmmword_180140340[v62]);
    v73 = WORD3(xmmword_180140340[v62]);
    v74 = WORD2(xmmword_180140340[v62]);
    v102 = v65->wYear;
    v103 = v65->wMonth;
    v104 = v65->wDay;
    v105 = v65->wHour;
    v75 = v65->wMinute;
    v107 = v65->wSecond;
    v106 = v75;
    if ( v111 )
      v69 = v111;
    v76 = byte_180122168;
    *(_QWORD *)&SystemTime.wYear = v69;
    v77 = BYTE8(xmmword_180140340[v62]);
    if ( v128[0] )
      v76 = " ";
    v78 = BYTE14(xmmword_180140340[v62]);
    v114 = (unsigned __int64)v76;
    sqlite3_log(
      v101,
      "[sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}%s%s TID:%u @%"
      "04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu %s : SQL %s",
      _InterlockedIncrement(&dword_180140410),
      0,
      v108,
      UnbiasedTime,
      LODWORD(xmmword_180140340[v62]),
      v74,
      v73,
      v77,
      v72,
      v71,
      v70,
      v68,
      v66,
      v78,
      HIBYTE(xmmword_180140340[v62]),
      v76,
      v128,
      (_DWORD)v112,
      v102,
      v103,
      v104,
      v105,
      v106,
      v107,
      v109,
      *(const char **)&SystemTime.wYear,
      v67);
    v37 = v98;
  }
LABEL_98:
  v60 = v100;
LABEL_99:
  if ( (dword_18013F948 & 0x80000) != 0 )
  {
    v114 = 0;
    v79 = (int)v60;
    v80 = (struct _SYSTEMTIME *)qword_1801402F0[v60];
    LODWORD(v112) = dword_180140320[v60];
    v81 = StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(&v118, v80, (unsigned __int64)&v114, v32);
    v109 = 0;
    v82 = v81->wYear;
    v83 = v81->wMonth;
    v84 = v81->wDay;
    v85 = v81->wHour;
    v86 = v81->wMinute;
    v87 = v81->wSecond;
    v88 = "<null>";
    if ( v113 )
      v88 = (const char *)v113;
    *(_QWORD *)&SystemTime.wYear = v88;
    v107 = HIBYTE(xmmword_180140340[v79]);
    v106 = BYTE14(xmmword_180140340[v79]);
    v105 = BYTE13(xmmword_180140340[v79]);
    v104 = BYTE12(xmmword_180140340[v79]);
    v103 = BYTE11(xmmword_180140340[v79]);
    v102 = BYTE10(xmmword_180140340[v79]);
    v101 = BYTE9(xmmword_180140340[v79]);
    v100 = BYTE8(xmmword_180140340[v79]);
    LODWORD(v110) = WORD3(xmmword_180140340[v79]);
    v89 = WORD2(xmmword_180140340[v79]);
    v90 = xmmword_180140340[v79];
    LODWORD(v113) = v89;
    QueryUnbiasedInterruptTime(&v109);
    LODWORD(UnbiasedTime) = _InterlockedIncrement(&dword_180140410);
    v96 = v86;
    v37 = v98;
    sqlite3_log(
      v98,
      "[post-sqlite3_exec] #%u Database %llu: Try %u (%llums) {%08X-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X} TID:%u @"
      "%04hu/%02hu/%02hu-%02hu:%02hu:%02hu.%06llu : SQL %s",
      UnbiasedTime,
      0,
      v108,
      v109 / 0x2710 - i,
      v90,
      (_DWORD)v113,
      v110,
      v100,
      v101,
      v102,
      v103,
      v104,
      v105,
      v106,
      v107,
      (_DWORD)v112,
      v82,
      v83,
      v84,
      v85,
      v96,
      v87,
      v114,
      *(const char **)&SystemTime.wYear);
  }
  v91 = v111;
  v111 = 0;
  if ( v91 )
    sqlite3_free(v91);
  return v37;
}

```

## disassembly

```asm
0x1800fce08  mov     [rsp-8+arg_10], rbx
0x1800fce0d  push    rbp
0x1800fce0e  push    rsi
0x1800fce0f  push    rdi
0x1800fce10  push    r12
0x1800fce12  push    r13
0x1800fce14  push    r14
0x1800fce16  push    r15
0x1800fce18  lea     rbp, [rsp-0C0h]
0x1800fce20  sub     rsp, 230h
0x1800fce27  mov     rax, cs:__security_cookie
0x1800fce2e  xor     rax, rsp
0x1800fce31  mov     [rbp+0F0h+var_40], rax
0x1800fce38  test    cs:dword_18013F948, 4000h
0x1800fce42  mov     r15, rdx
0x1800fce45  movsxd  rsi, [rbp+0F0h+arg_28]
0x1800fce4c  mov     r14, rcx
0x1800fce4f  mov     [rbp+0F0h+var_160], esi
0x1800fce52  mov     [rbp+0F0h+var_118], rdx
0x1800fce56  mov     [rbp+0F0h+var_120], rcx
0x1800fce5a  jz      short loc_1800FCE85
0x1800fce5c  xor     r8d, r8d; unsigned int *
0x1800fce5f  mov     dl, 1; bool
0x1800fce61  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x1800fce66  test    eax, eax
0x1800fce68  jns     short loc_1800FCE85
0x1800fce6a  mov     rcx, [rbp+0F8h]; this
0x1800fce71  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fce78  mov     r9d, eax; char *
0x1800fce7b  mov     edx, 115Ch; void *
0x1800fce80  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fce85  test    cs:dword_18013F948, 40000h
0x1800fce8f  lea     r12, xmmword_180140340
0x1800fce96  lea     rcx, cs:180000000h
0x1800fce9d  jz      loc_1800FD030
0x1800fcea3  mov     eax, rva dword_180140320[rcx+rsi*4]
0x1800fceaa  lea     r8, [rbp+0F0h+var_130]; unsigned __int64
0x1800fceae  mov     rdx, rva qword_1801402F0[rcx+rsi*8]; retstr
0x1800fceb6  mov     r13, rsi
0x1800fceb9  shl     r13, 4
0x1800fcebd  lea     rcx, [rbp+0F0h+SystemTime]; lpSystemTime
0x1800fcec1  mov     [rbp+0F0h+UnbiasedTime], r13
0x1800fcec5  mov     [rbp+0F0h+var_15C], eax
0x1800fcec8  mov     [rbp+0F0h+var_130], 0
0x1800fced0  call    ?ToSystemTimeAndMicroseconds@Temporal@DataType@StateRepository@@YA?AU_SYSTEMTIME@@_KAEA_K@Z; StateRepository::DataType::Temporal::ToSystemTimeAndMicroseconds(unsigned __int64,unsigned __int64 &)
0x1800fced5  movzx   ebx, byte ptr [r12+r13+0Fh]
0x1800fcedb  test    r15, r15
0x1800fcede  movzx   edi, byte ptr [r12+r13+0Eh]
0x1800fcee4  movzx   esi, byte ptr [r12+r13+0Dh]
0x1800fceea  movzx   ecx, word ptr [rax]
0x1800fceed  movzx   r10d, word ptr [rax+2]
0x1800fcef2  movzx   r9d, word ptr [rax+6]
0x1800fcef7  movzx   r8d, word ptr [rax+8]
0x1800fcefc  movzx   edx, word ptr [rax+0Ah]
0x1800fcf00  movzx   r14d, byte ptr [r12+r13+0Ch]
0x1800fcf06  mov     r11, [rbp+0F0h+UnbiasedTime]
0x1800fcf0a  mov     [rbp+0F0h+var_140], ebx
0x1800fcf0d  lea     rbx, xmmword_180140340
0x1800fcf14  mov     word ptr [rbp+0F0h+var_170], cx
0x1800fcf18  movzx   ecx, word ptr [rax+0Ch]
0x1800fcf1c  lea     rax, aNull_1; "<null>"
0x1800fcf23  movzx   r11d, byte ptr [r11+rbx+8]
0x1800fcf29  cmovnz  rax, r15
0x1800fcf2d  movzx   r15d, byte ptr [r12+r13+0Bh]
0x1800fcf33  movzx   r12d, byte ptr [r12+r13+0Ah]
0x1800fcf39  movzx   r13d, byte ptr [rbx+r13+9]
0x1800fcf3f  mov     rbx, [rbp+0F0h+UnbiasedTime]
0x1800fcf43  mov     [rbp+0F0h+var_154], r11d
0x1800fcf47  mov     [rbp+0F0h+var_158], edi
0x1800fcf4a  lea     rdi, xmmword_180140340
0x1800fcf51  movzx   r11d, word ptr [rbx+rdi+6]
0x1800fcf57  mov     [rbp+0F0h+var_150], r11d
0x1800fcf5b  movzx   r11d, word ptr [rbx+rdi+4]
0x1800fcf61  mov     [rbp+0F0h+var_14C], r11d
0x1800fcf65  mov     r11d, [rbx+rdi]
0x1800fcf69  mov     [rbp+0F0h+var_148], r11d
0x1800fcf6d  mov     r11d, 1
0x1800fcf73  lock xadd cs:dword_180140410, r11d
0x1800fcf7c  mov     ebx, [rbp+0F0h+var_140]
0x1800fcf7f  inc     r11d
0x1800fcf82  mov     edi, [rbp+0F0h+var_158]
0x1800fcf85  mov     [rsp+260h+var_1A8], rax
0x1800fcf8d  mov     rax, [rbp+0F0h+var_130]
0x1800fcf91  mov     [rsp+260h+var_1B0], rax
0x1800fcf99  mov     eax, [rbp+0F0h+var_15C]
0x1800fcf9c  mov     [rsp+260h+var_1B8], ecx
0x1800fcfa3  xor     ecx, ecx
0x1800fcfa5  mov     [rsp+260h+var_1C0], edx
0x1800fcfac  lea     rdx, aPreSqlite3Exec; "[pre-sqlite3_exec] #%u Database %llu {%"...
0x1800fcfb3  mov     [rsp+260h+var_1C8], r8d
0x1800fcfbb  mov     dword ptr [rsp+260h+var_1D0], r9d
0x1800fcfc3  xor     r9d, r9d
0x1800fcfc6  mov     dword ptr [rsp+260h+var_1D8], r10d
0x1800fcfce  mov     [rbp+0F0h+var_144], r11d
0x1800fcfd2  movzx   r11d, word ptr [rbp+0F0h+var_170]
0x1800fcfd7  mov     r8d, [rbp+0F0h+var_144]
0x1800fcfdb  mov     [rsp+260h+var_1E0], r11d
0x1800fcfe3  mov     [rsp+260h+var_1E8], eax
0x1800fcfe7  mov     eax, [rbp+0F0h+var_154]
0x1800fcfea  mov     [rsp+260h+var_1F0], ebx
0x1800fcfee  mov     [rsp+260h+var_1F8], edi
0x1800fcff2  mov     [rsp+260h+var_200], esi
0x1800fcff6  mov     [rsp+260h+var_208], r14d
0x1800fcffb  mov     [rsp+260h+var_210], r15d
0x1800fd000  mov     [rsp+260h+var_218], r12d
0x1800fd005  mov     [rsp+260h+var_220], r13d
0x1800fd00a  mov     [rsp+260h+var_228], eax
0x1800fd00e  mov     eax, [rbp+0F0h+var_150]
0x1800fd011  mov     dword ptr [rsp+260h+var_230], eax
0x1800fd015  mov     eax, [rbp+0F0h+var_14C]
0x1800fd018  mov     dword ptr [rsp+260h+var_238], eax
0x1800fd01c  mov     eax, [rbp+0F0h+var_148]
0x1800fd01f  mov     dword ptr [rsp+260h+var_240], eax
0x1800fd023  call    sqlite3_log
0x1800fd028  mov     r14, [rbp+0F0h+var_120]
0x1800fd02c  mov     r15, [rbp+0F0h+var_118]
0x1800fd030  mov     rax, cs:qword_18013F940
0x1800fd037  lea     rcx, [rbp+0F0h+UnbiasedTime]; UnbiasedTime
0x1800fd03b  xor     esi, esi
0x1800fd03d  mov     [rbp+0F0h+var_138], rax
0x1800fd041  mov     [rbp+0F0h+var_128], rsi
0x1800fd045  mov     r13d, esi
0x1800fd048  mov     [rbp+0F0h+UnbiasedTime], rsi
0x1800fd04c  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800fd052  mov     rax, 346DC5D63886594Bh
0x1800fd05c  mov     r12d, 87AF0205h
0x1800fd062  mul     [rbp+0F0h+UnbiasedTime]
0x1800fd066  mov     [rbp+0F0h+UnbiasedTime], rsi
0x1800fd06a  mov     rdi, rdx
0x1800fd06d  shr     rdi, 0Bh
0x1800fd071  mov     [rbp+0F0h+var_F0], rdi
0x1800fd075  jmp     short loc_1800FD07B
0x1800fd077  mov     rdi, [rbp+0F0h+var_F0]
0x1800fd07b  inc     r13d
0x1800fd07e  mov     [rbp+0F0h+var_140], r13d
0x1800fd082  cmp     r13d, 1
0x1800fd086  jbe     short loc_1800FD094
0x1800fd088  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x1800fd08e  call    cs:__imp_Sleep
0x1800fd094  mov     rcx, [rbp+0F0h+var_128]
0x1800fd098  mov     [rbp+0F0h+var_128], rsi
0x1800fd09c  test    rcx, rcx
0x1800fd09f  jz      short loc_1800FD0A6
0x1800fd0a1  call    sqlite3_free
0x1800fd0a6  lea     rax, [rbp+0F0h+var_128]
0x1800fd0aa  mov     qword ptr [rbp+0F0h+SystemTime.wHour], rsi
0x1800fd0ae  mov     qword ptr [rbp+0F0h+SystemTime.wYear], rax
0x1800fd0b2  xor     r9d, r9d
0x1800fd0b5  lea     rax, [rbp+0F0h+SystemTime.wHour]
0x1800fd0b9  mov     [rbp+0F0h+var_F8], 1
0x1800fd0bd  xor     r8d, r8d
0x1800fd0c0  mov     [rsp+260h+var_240], rax
0x1800fd0c5  mov     rdx, r15
0x1800fd0c8  mov     rcx, r14
0x1800fd0cb  call    sqlite3_exec
0x1800fd0d0  mov     [rbp+0F0h+var_15C], eax
0x1800fd0d3  mov     ebx, eax
0x1800fd0d5  test    eax, eax
0x1800fd0d7  jle     short loc_1800FD0E5
0x1800fd0d9  movzx   ebx, ax
0x1800fd0dc  or      ebx, 87AF0000h
0x1800fd0e2  mov     [rbp+0F0h+var_15C], ebx
0x1800fd0e5  cmp     [rbp+0F0h+var_F8], sil
0x1800fd0e9  jz      short loc_1800FD103
0x1800fd0eb  mov     rdx, qword ptr [rbp+0F0h+SystemTime.wYear]
0x1800fd0ef  mov     rax, qword ptr [rbp+0F0h+SystemTime.wHour]
0x1800fd0f3  mov     rcx, [rdx]
0x1800fd0f6  mov     [rdx], rax
0x1800fd0f9  test    rcx, rcx
0x1800fd0fc  jz      short loc_1800FD103
0x1800fd0fe  call    sqlite3_free
0x1800fd103  test    ebx, ebx
0x1800fd105  jns     loc_1800FD689
0x1800fd10b  lea     rcx, [rbp+0F0h+UnbiasedTime]; UnbiasedTime
0x1800fd10f  mov     [rbp+0F0h+UnbiasedTime], rsi
0x1800fd113  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800fd119  mov     rax, 346DC5D63886594Bh
0x1800fd123  mul     [rbp+0F0h+UnbiasedTime]
0x1800fd127  mov     rsi, rdx
0x1800fd12a  shr     rsi, 0Bh
0x1800fd12e  sub     rsi, rdi
0x1800fd131  mov     [rbp+0F0h+UnbiasedTime], rsi
0x1800fd135  cmp     ebx, r12d
0x1800fd138  jz      short loc_1800FD181
0x1800fd13a  cmp     ebx, 87AF0005h
0x1800fd140  jz      short loc_1800FD1BA
0x1800fd142  cmp     ebx, 87AF0105h
0x1800fd148  jz      short loc_1800FD1BA
0x1800fd14a  mov     eax, ebx
0x1800fd14c  and     eax, 0FFFF00FFh
0x1800fd151  cmp     eax, 87AF0006h
0x1800fd156  jz      short loc_1800FD1BA
0x1800fd158  xor     r12b, r12b
0x1800fd15b  mov     [rbp+0F0h+var_170], ebx
0x1800fd15e  mov     ecx, 87AF000Bh
0x1800fd163  mov     edi, ebx
0x1800fd165  cmp     eax, ecx
0x1800fd167  jnz     loc_1800FD33F
0x1800fd16d  cmp     ebx, ecx
0x1800fd16f  jnz     loc_1800FD22B
0x1800fd175  lea     rax, qword_180140510
0x1800fd17c  jmp     loc_1800FD265
0x1800fd181  mov     rcx, r14
0x1800fd184  call    sqlite3_get_autocommit
0x1800fd189  test    eax, eax
0x1800fd18b  jnz     short loc_1800FD192
0x1800fd18d  mov     ebx, r12d
0x1800fd190  jmp     short loc_1800FD14A
0x1800fd192  xor     edx, edx
0x1800fd194  jmp     short loc_1800FD1A5
0x1800fd196  mov     rcx, rdi
0x1800fd199  call    sqlite3_stmt_busy
0x1800fd19e  test    eax, eax
0x1800fd1a0  jnz     short loc_1800FD14A
0x1800fd1a2  mov     rdx, rdi
0x1800fd1a5  mov     rcx, r14
0x1800fd1a8  call    sqlite3_next_stmt
0x1800fd1ad  mov     rdi, rax
0x1800fd1b0  test    rax, rax
0x1800fd1b3  jnz     short loc_1800FD196
0x1800fd1b5  mov     ebx, 87AF0005h
0x1800fd1ba  mov     r12b, 1
0x1800fd1bd  cmp     rsi, [rbp+0F0h+var_138]
0x1800fd1c1  jb      loc_1800FD2DE
0x1800fd1c7  cmp     ebx, 87AF0005h
0x1800fd1cd  jz      loc_1800FD2D5
0x1800fd1d3  cmp     ebx, 87AF0006h
0x1800fd1d9  jz      loc_1800FD2C3
0x1800fd1df  cmp     ebx, 87AF0105h
0x1800fd1e5  jz      loc_1800FD2BA
0x1800fd1eb  cmp     ebx, 87AF0106h
0x1800fd1f1  jz      loc_1800FD2CC
0x1800fd1f7  cmp     ebx, 5
0x1800fd1fa  jz      loc_1800FD2D5
0x1800fd200  cmp     ebx, 6
0x1800fd203  jz      loc_1800FD2C3
0x1800fd209  cmp     ebx, 105h
0x1800fd20f  jz      loc_1800FD2BA
0x1800fd215  mov     eax, 8067000Fh
0x1800fd21a  cmp     ebx, 106h
0x1800fd220  cmovnz  eax, ebx
0x1800fd223  mov     [rbp+0F0h+var_170], eax
0x1800fd226  jmp     loc_1800FD33C
0x1800fd22b  cmp     ebx, 87AF030Bh
0x1800fd231  jnz     short loc_1800FD23C
0x1800fd233  lea     rax, qword_180140518
0x1800fd23a  jmp     short loc_1800FD265
0x1800fd23c  cmp     ebx, 87AF020Bh
0x1800fd242  jnz     short loc_1800FD24D
0x1800fd244  lea     rax, qword_180140500
0x1800fd24b  jmp     short loc_1800FD265
0x1800fd24d  cmp     ebx, 87AF010Bh
0x1800fd253  lea     rax, qword_180140508
0x1800fd25a  lea     rcx, qword_1801404F8
0x1800fd261  cmovnz  rax, rcx
0x1800fd265  lock inc qword ptr [rax]
0x1800fd269  mov     r8d, [rbp+0F0h+var_160]
0x1800fd26d  lea     rdx, aSqlite3Exec; "sqlite3_exec"
0x1800fd274  mov     eax, r13d
0x1800fd277  mov     r9, r14
0x1800fd27a  mov     [rsp+260h+var_230], rsi
0x1800fd27f  mov     ecx, ebx
0x1800fd281  mov     [rsp+260h+var_238], rax
0x1800fd286  mov     [rsp+260h+var_240], r15; int
0x1800fd28b  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x1800fd290  xor     ebx, ebx
0x1800fd292  test    eax, eax
0x1800fd294  jns     loc_1800FD341
0x1800fd29a  mov     rcx, [rbp+0F8h]; this
0x1800fd2a1  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fd2a8  mov     r9d, eax; char *
0x1800fd2ab  mov     edx, 118Fh; void *
0x1800fd2b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fd2b5  jmp     loc_1800FD341
0x1800fd2ba  mov     [rbp+0F0h+var_170], 8067000Dh
0x1800fd2c1  jmp     short loc_1800FD33C
0x1800fd2c3  mov     [rbp+0F0h+var_170], 8067000Eh
0x1800fd2ca  jmp     short loc_1800FD33C
0x1800fd2cc  mov     [rbp+0F0h+var_170], 8067000Fh
0x1800fd2d3  jmp     short loc_1800FD33C
0x1800fd2d5  mov     [rbp+0F0h+var_170], 8067000Ch
0x1800fd2dc  jmp     short loc_1800FD33C
0x1800fd2de  cmp     ebx, 87AF0005h
0x1800fd2e4  jz      short loc_1800FD335
0x1800fd2e6  cmp     ebx, 87AF0006h
0x1800fd2ec  jz      short loc_1800FD32C
0x1800fd2ee  cmp     ebx, 87AF0105h
0x1800fd2f4  jz      short loc_1800FD323
0x1800fd2f6  cmp     ebx, 87AF0106h
0x1800fd2fc  jz      short loc_1800FD31A
0x1800fd2fe  cmp     ebx, 5
0x1800fd301  jz      short loc_1800FD335
0x1800fd303  cmp     ebx, 6
0x1800fd306  jz      short loc_1800FD32C
0x1800fd308  cmp     ebx, 105h
0x1800fd30e  jz      short loc_1800FD323
0x1800fd310  mov     eax, 8067000Ah
0x1800fd315  jmp     loc_1800FD21A
0x1800fd31a  mov     [rbp+0F0h+var_170], 8067000Ah
0x1800fd321  jmp     short loc_1800FD33C
  ... truncated ...
```
