# StateRepository::Statement::dal_step(sqlite3_stmt *)

- ea: `0x18001c314`
- end: `0x18001c8b9`
- name: `?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z`
- size: `1445`
- prototype: `__int64 __fastcall(struct sqlite3_stmt *)`
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x18001b8d4`
- `0x18001b920`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x18000c3bc`
- `0x180014ca0`
- `0x180015204`
- `0x180018254`
- `0x180018f14`
- `0x180018f3c`
- `0x1800194f4`
- `0x1800195ac`
- `0x18001c314`
- `0x1800264b0`
- `0x18002650c`
- `0x180028200`
- `0x180029914`
- `0x18002a300`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c3e3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001c3e3`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c359`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c443`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c46b`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c685`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c818`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c359`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c443`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c46b`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c685`
- `StateRepository.Core!sqlite3_db_handle` at `0x18001c818`
- `StateRepository.Core!sqlite3_log` at `0x18001c3ac`
- `StateRepository.Core!sqlite3_log` at `0x18001c665`
- `StateRepository.Core!sqlite3_log` at `0x18001c7d9`
- `StateRepository.Core!sqlite3_log` at `0x18001c879`
- `StateRepository.Core!sqlite3_log` at `0x18001c3ac`
- `StateRepository.Core!sqlite3_log` at `0x18001c665`
- `StateRepository.Core!sqlite3_log` at `0x18001c7d9`
- `StateRepository.Core!sqlite3_log` at `0x18001c879`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001c5d2`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001c746`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001c5d2`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001c746`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c36c`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c483`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c69d`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c82b`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c36c`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c483`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c69d`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001c82b`
- `StateRepository.Core!sqlite3_step` at `0x18001c3ec`
- `StateRepository.Core!sqlite3_step` at `0x18001c3ec`
- `StateRepository.Core!sqlite3_sql` at `0x18001c44f`
- `StateRepository.Core!sqlite3_sql` at `0x18001c494`
- `StateRepository.Core!sqlite3_sql` at `0x18001c752`
- `StateRepository.Core!sqlite3_sql` at `0x18001c44f`
- `StateRepository.Core!sqlite3_sql` at `0x18001c494`
- `StateRepository.Core!sqlite3_sql` at `0x18001c752`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c378`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c52e`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c6a9`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c837`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c378`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c52e`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c6a9`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001c837`

## string_xrefs

- `0x18001c517`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18001c8a7`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Statement::dal_step(struct sqlite3_stmt *a1)
{
  const char *v1; // r13
  struct sqlite3 *v3; // rsi
  __int64 clientdata; // r15
  int v5; // eax
  const char *v6; // rcx
  unsigned int v7; // r12d
  unsigned __int64 v8; // rbx
  int v9; // eax
  unsigned int busy; // edi
  StateRepository::Time *v11; // rcx
  StateRepository::Logging *v12; // rbx
  struct sqlite3 *v13; // rax
  struct sqlite3_stmt *v14; // r9
  int v15; // edx
  bool v16; // r13
  int v17; // eax
  int v18; // eax
  const char *v19; // rcx
  __int64 v20; // rax
  const char *v21; // rdx
  const char *v22; // rcx
  const char *v23; // rax
  __int64 v24; // r13
  int v25; // eax
  const char *v26; // rcx
  __int64 v27; // rax
  const char *v28; // rdx
  const char *v29; // rcx
  const char *v30; // rax
  StateRepository::Logging *v31; // rcx
  bool v32; // zf
  const char *v33; // rax
  int v35; // [rsp+20h] [rbp-E0h]
  int v36[2]; // [rsp+60h] [rbp-A0h]
  const char *v37; // [rsp+68h] [rbp-98h]
  const char *v38; // [rsp+68h] [rbp-98h]
  unsigned __int64 v39; // [rsp+70h] [rbp-90h]
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // [rsp+78h] [rbp-88h]
  _BYTE v41[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v42; // [rsp+90h] [rbp-70h]
  __int64 v43; // [rsp+98h] [rbp-68h]
  __int64 v44; // [rsp+A0h] [rbp-60h]
  __int64 v45; // [rsp+A8h] [rbp-58h]
  __int64 v46; // [rsp+B0h] [rbp-50h]
  int v47; // [rsp+B8h] [rbp-48h]
  __int64 v48; // [rsp+BCh] [rbp-44h]
  int v49; // [rsp+C4h] [rbp-3Ch]
  char v50[64]; // [rsp+D0h] [rbp-30h] BYREF
  char v51[64]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v1 = 0;
  *(_QWORD *)v36 = 0;
  if ( (dword_18004B904 & 0x40000) != 0 )
  {
    v3 = (struct sqlite3 *)sqlite3_db_handle(a1);
    clientdata = sqlite3_get_clientdata(v3, "connection.id");
    v5 = sqlite3_stmt_busy(a1);
    v6 = "BUSY";
    if ( !v5 )
      v6 = "OK";
    sqlite3_log(
      0,
      "[pre-sqlite3_step] #%u Database %llu: Statement %s",
      _InterlockedIncrement(&dword_18004BFF0),
      clientdata,
      v6);
  }
  else
  {
    v3 = 0;
    clientdata = 0;
  }
  v7 = 0;
  v39 = qword_18004B8F8;
  UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(a1);
  v8 = 0;
  do
  {
    if ( ++v7 > 1 )
      Sleep(dwMilliseconds);
    v9 = sqlite3_step(a1);
    busy = v9;
    if ( v9 > 0 )
      busy = (unsigned __int16)v9 | 0x87AF0000;
    if ( busy == -2018574236 || busy == -2018574235 )
    {
      if ( v7 > 1 )
      {
        v24 = 0;
        if ( !v3 )
          v3 = (struct sqlite3 *)sqlite3_db_handle(a1);
        if ( !clientdata )
          clientdata = sqlite3_get_clientdata(v3, "connection.id");
        v25 = sqlite3_stmt_busy(a1);
        v26 = "BUSY";
        if ( !v25 )
          v26 = "OK";
        v38 = v26;
        memset_0(v51, 0, sizeof(v51));
        if ( IsHresultSqliteBusyOrLocked(busy) )
        {
          memset_0(v41, 0, 0x48u);
          v43 = 0;
          v45 = 0;
          v47 = 0;
          v48 = 0;
          v49 = 0;
          v42 = 0;
          v44 = 0;
          v46 = 0;
          StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
            (StateRepository::ResourcePriority::AutoPriority *)v41,
            (char (*)[64])v51);
          StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v41);
        }
        if ( v3 )
          v24 = sqlite3_errmsg(v3);
        v27 = sqlite3_sql(a1);
        *(_QWORD *)v36 = v27;
        v28 = "<null>";
        if ( v27 )
          v28 = (const char *)v27;
        v29 = "<no-error-message>";
        v30 = (const char *)&dword_180034EEC;
        if ( v24 )
          v29 = (const char *)v24;
        if ( v51[0] )
          v30 = " ";
        sqlite3_log(
          busy,
          "[sqlite3_step_final] #%u Database %llu: Statement %s: Try %u (%llums)%s%s %s : SQL %s",
          _InterlockedIncrement(&dword_18004BFF0),
          clientdata,
          v38,
          v7,
          v8,
          v30,
          v51,
          v29,
          v28);
        v1 = *(const char **)v36;
      }
    }
    else
    {
      if ( (busy & 0x80000000) == 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x41E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)0x8000FFFFLL,
          v35);
      busy = MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(busy, v3);
      if ( busy == -2018573819 )
      {
        v12 = (StateRepository::Logging *)sqlite3_db_handle(a1);
        v13 = (struct sqlite3 *)sqlite3_sql(a1);
        StateRepository::Logging::FailFastBusySnapshot(v12, v13, (const char *)a1, v14);
      }
      if ( !v3 )
        v3 = (struct sqlite3 *)sqlite3_db_handle(a1);
      if ( !clientdata )
        clientdata = sqlite3_get_clientdata(v3, "connection.id");
      if ( !v1 )
        *(_QWORD *)v36 = sqlite3_sql(a1);
      v8 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v11) - UnbiasedInterruptTimeAsMSec;
      v16 = IsHresultSqliteBusyOrLocked(busy);
      if ( v16 && v8 < v39 )
      {
        busy = MapHresultSqliteBusyOrLockedToRetry(busy);
      }
      else if ( (busy & 0xFFFF00FF) == 0x87AF000B )
      {
        StateRepository::ErrorTracking::details::TrackCorruptError((StateRepository::ErrorTracking::details *)busy, v15);
        v35 = v36[0];
        v17 = StateRepository::Logging::ReportDatabaseCorruption(busy, "sqlite3_step", 0, v3);
        if ( v17 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x43F,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v17,
            v36[0]);
      }
      v18 = sqlite3_stmt_busy(a1);
      v19 = "BUSY";
      if ( !v18 )
        v19 = "OK";
      v37 = v19;
      memset_0(v50, 0, sizeof(v50));
      if ( v16 )
      {
        memset_0(v41, 0, 0x48u);
        v43 = 0;
        v45 = 0;
        v47 = 0;
        v48 = 0;
        v49 = 0;
        v42 = 0;
        v44 = 0;
        v46 = 0;
        StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
          (StateRepository::ResourcePriority::AutoPriority *)v41,
          (char (*)[64])v50);
        StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v41);
      }
      if ( v3 )
        v20 = sqlite3_errmsg(v3);
      else
        v20 = 0;
      v1 = *(const char **)v36;
      if ( v7 == 1 )
      {
        v21 = "<null>";
        if ( *(_QWORD *)v36 )
          v21 = *(const char **)v36;
        v22 = "<no-error-message>";
        if ( v20 )
          v22 = (const char *)v20;
        v23 = (const char *)&dword_180034EEC;
        if ( v50[0] )
          v23 = " ";
        sqlite3_log(
          busy,
          "[sqlite3_step] #%u Database %llu: Statement %s: Try %u (%llums)%s%s %s : SQL %s",
          _InterlockedIncrement(&dword_18004BFF0),
          clientdata,
          v37,
          1,
          v8,
          v23,
          v50,
          v22,
          v21);
      }
    }
    if ( !IsHresultSqliteBusyOrLockedOrRetry(busy) )
      break;
    StateRepository::Logging::DebugBreak(v31);
  }
  while ( v8 < v39 );
  if ( (dword_18004B904 & 0x80000) != 0 )
  {
    if ( !clientdata )
    {
      if ( !v3 )
        v3 = (struct sqlite3 *)sqlite3_db_handle(a1);
      clientdata = sqlite3_get_clientdata(v3, "connection.id");
    }
    v32 = (unsigned int)sqlite3_stmt_busy(a1) == 0;
    v33 = "BUSY";
    if ( v32 )
      v33 = "OK";
    sqlite3_log(
      busy,
      "[post-sqlite3_step] #%u Database %llu: Statement %s: Tries %u",
      _InterlockedIncrement(&dword_18004BFF0),
      clientdata,
      v33,
      v7);
  }
  return busy;
}

```

## disassembly

```asm
0x18001c314  push    rbp
0x18001c316  push    rbx
0x18001c317  push    rsi
0x18001c318  push    rdi
0x18001c319  push    r12
0x18001c31b  push    r13
0x18001c31d  push    r14
0x18001c31f  push    r15
0x18001c321  lea     rbp, [rsp-68h]
0x18001c326  sub     rsp, 168h
0x18001c32d  mov     rax, cs:__security_cookie
0x18001c334  xor     rax, rsp
0x18001c337  mov     [rbp+0A0h+var_50], rax
0x18001c33b  xor     r13d, r13d
0x18001c33e  lea     rbx, aOk; "OK"
0x18001c345  test    cs:dword_18004B904, 40000h
0x18001c34f  mov     r14, rcx
0x18001c352  mov     qword ptr [rsp+1A0h+var_140], r13
0x18001c357  jz      short loc_18001C3B4
0x18001c359  call    cs:__imp_sqlite3_db_handle
0x18001c35f  mov     rcx, rax
0x18001c362  lea     rdx, aConnectionId; "connection.id"
0x18001c369  mov     rsi, rax
0x18001c36c  call    cs:__imp_sqlite3_get_clientdata
0x18001c372  mov     rcx, r14
0x18001c375  mov     r15, rax
0x18001c378  call    cs:__imp_sqlite3_stmt_busy
0x18001c37e  test    eax, eax
0x18001c380  lea     rcx, aBusy; "BUSY"
0x18001c387  lea     r8d, [r13+1]
0x18001c38b  cmovz   rcx, rbx
0x18001c38f  lock xadd cs:dword_18004BFF0, r8d
0x18001c398  mov     qword ptr [rsp+1A0h+var_180], rcx
0x18001c39d  lea     rdx, aPreSqlite3Step; "[pre-sqlite3_step] #%u Database %llu: S"...
0x18001c3a4  xor     ecx, ecx
0x18001c3a6  inc     r8d
0x18001c3a9  mov     r9, r15
0x18001c3ac  call    cs:__imp_sqlite3_log
0x18001c3b2  jmp     short loc_18001C3B9
0x18001c3b4  xor     esi, esi
0x18001c3b6  xor     r15d, r15d
0x18001c3b9  mov     rax, cs:qword_18004B8F8
0x18001c3c0  xor     r12d, r12d
0x18001c3c3  mov     [rsp+1A0h+var_130], rax
0x18001c3c8  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001c3cd  mov     [rsp+1A0h+var_128], rax
0x18001c3d2  xor     ebx, ebx
0x18001c3d4  inc     r12d
0x18001c3d7  cmp     r12d, 1
0x18001c3db  jbe     short loc_18001C3E9
0x18001c3dd  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x18001c3e3  call    cs:__imp_Sleep
0x18001c3e9  mov     rcx, r14
0x18001c3ec  call    cs:__imp_sqlite3_step
0x18001c3f2  mov     edi, eax
0x18001c3f4  test    eax, eax
0x18001c3f6  jle     short loc_18001C401
0x18001c3f8  movzx   edi, ax
0x18001c3fb  or      edi, 87AF0000h
0x18001c401  cmp     edi, 87AF0064h
0x18001c407  jz      loc_18001C670
0x18001c40d  cmp     edi, 87AF0065h
0x18001c413  jz      loc_18001C670
0x18001c419  mov     rcx, [rbp+0A8h]; this
0x18001c420  mov     eax, edi
0x18001c422  shr     eax, 1Fh
0x18001c425  xor     al, 1
0x18001c427  jnz     loc_18001C8A1
0x18001c42d  mov     rdx, rsi; struct sqlite3 *
0x18001c430  mov     ecx, edi; int
0x18001c432  call    ?MapSqliteBusySnapshotToSqliteBusyIfRaceCondition@@YAJJPEAUsqlite3@@@Z; MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(long,sqlite3 *)
0x18001c437  mov     edi, eax
0x18001c439  cmp     eax, 87AF0205h
0x18001c43e  jnz     short loc_18001C463
0x18001c440  mov     rcx, r14
0x18001c443  call    cs:__imp_sqlite3_db_handle
0x18001c449  mov     rcx, r14
0x18001c44c  mov     rbx, rax
0x18001c44f  call    cs:__imp_sqlite3_sql
0x18001c455  mov     r8, r14; char *
0x18001c458  mov     rcx, rbx; this
0x18001c45b  mov     rdx, rax; struct sqlite3 *
0x18001c45e  call    ?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z; StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)
0x18001c463  test    rsi, rsi
0x18001c466  jnz     short loc_18001C474
0x18001c468  mov     rcx, r14
0x18001c46b  call    cs:__imp_sqlite3_db_handle
0x18001c471  mov     rsi, rax
0x18001c474  test    r15, r15
0x18001c477  jnz     short loc_18001C48C
0x18001c479  lea     rdx, aConnectionId; "connection.id"
0x18001c480  mov     rcx, rsi
0x18001c483  call    cs:__imp_sqlite3_get_clientdata
0x18001c489  mov     r15, rax
0x18001c48c  test    r13, r13
0x18001c48f  jnz     short loc_18001C49F
0x18001c491  mov     rcx, r14
0x18001c494  call    cs:__imp_sqlite3_sql
0x18001c49a  mov     qword ptr [rsp+1A0h+var_140], rax
0x18001c49f  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001c4a4  mov     rbx, rax
0x18001c4a7  mov     ecx, edi; int
0x18001c4a9  sub     rbx, [rsp+1A0h+var_128]
0x18001c4ae  call    ?IsHresultSqliteBusyOrLocked@@YA_NJ@Z; IsHresultSqliteBusyOrLocked(long)
0x18001c4b3  mov     r13b, al
0x18001c4b6  test    al, al
0x18001c4b8  jz      short loc_18001C4CC
0x18001c4ba  cmp     rbx, [rsp+1A0h+var_130]
0x18001c4bf  jnb     short loc_18001C4CC
0x18001c4c1  mov     ecx, edi; int
0x18001c4c3  call    ?MapHresultSqliteBusyOrLockedToRetry@@YAJJ@Z; MapHresultSqliteBusyOrLockedToRetry(long)
0x18001c4c8  mov     edi, eax
0x18001c4ca  jmp     short loc_18001C52B
0x18001c4cc  mov     eax, edi
0x18001c4ce  and     eax, 0FFFF00FFh
0x18001c4d3  cmp     eax, 87AF000Bh
0x18001c4d8  jnz     short loc_18001C52B
0x18001c4da  mov     ecx, edi; this
0x18001c4dc  call    ?TrackCorruptError@details@ErrorTracking@StateRepository@@YAXJ@Z; StateRepository::ErrorTracking::details::TrackCorruptError(long)
0x18001c4e1  mov     eax, r12d
0x18001c4e4  lea     rdx, aSqlite3Step; "sqlite3_step"
0x18001c4eb  mov     [rsp+1A0h+var_170], rbx
0x18001c4f0  mov     r9, rsi
0x18001c4f3  mov     [rsp+1A0h+var_178], rax
0x18001c4f8  xor     r8d, r8d
0x18001c4fb  mov     rax, qword ptr [rsp+1A0h+var_140]
0x18001c500  mov     ecx, edi
0x18001c502  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x18001c507  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x18001c50c  test    eax, eax
0x18001c50e  jns     short loc_18001C52B
0x18001c510  mov     rcx, [rbp+0A8h]; this
0x18001c517  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x18001c51e  mov     r9d, eax; char *
0x18001c521  mov     edx, 43Fh; void *
0x18001c526  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c52b  mov     rcx, r14
0x18001c52e  call    cs:__imp_sqlite3_stmt_busy
0x18001c534  test    eax, eax
0x18001c536  lea     rcx, aBusy; "BUSY"
0x18001c53d  lea     rax, aOk; "OK"
0x18001c544  cmovz   rcx, rax
0x18001c548  xor     edx, edx; Val
0x18001c54a  mov     [rsp+1A0h+var_138], rcx
0x18001c54f  lea     rcx, [rbp+0A0h+var_D0]; void *
0x18001c553  lea     r8d, [rdx+40h]; Size
0x18001c557  call    memset_0
0x18001c55c  test    r13b, r13b
0x18001c55f  jz      short loc_18001C5C2
0x18001c561  xor     edx, edx; Val
0x18001c563  lea     rcx, [rbp+0A0h+var_120]; void *
0x18001c567  lea     r8d, [rdx+48h]; Size
0x18001c56b  call    memset_0
0x18001c570  xor     r13d, r13d
0x18001c573  lea     rdx, [rbp+0A0h+var_D0]; char (*)[64]
0x18001c577  xor     eax, eax
0x18001c579  mov     [rbp+0A0h+var_108], r13
0x18001c57d  mov     [rbp+0A0h+var_F8], r13
0x18001c581  lea     rcx, [rbp+0A0h+var_120]; this
0x18001c585  mov     [rbp+0A0h+var_E8], r13
0x18001c589  mov     qword ptr [rbp+0A0h+var_E0], r13
0x18001c58d  mov     byte ptr [rbp+0A0h+var_108], r13b
0x18001c591  mov     dword ptr [rbp+0A0h+var_108+4], eax
0x18001c594  mov     byte ptr [rbp+0A0h+var_F8], r13b
0x18001c598  mov     dword ptr [rbp+0A0h+var_F8+4], eax
0x18001c59b  mov     byte ptr [rbp+0A0h+var_E8], r13b
0x18001c59f  mov     [rbp+0A0h+var_E8+4], rax
0x18001c5a3  mov     [rbp+0A0h+var_E0+4], eax
0x18001c5a6  mov     [rbp+0A0h+var_110], r13
0x18001c5aa  mov     [rbp+0A0h+var_100], r13
0x18001c5ae  mov     [rbp+0A0h+var_F0], r13
0x18001c5b2  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18001c5b7  lea     rcx, [rbp+0A0h+var_120]; this
0x18001c5bb  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x18001c5c0  jmp     short loc_18001C5C5
0x18001c5c2  xor     r13d, r13d
0x18001c5c5  test    rsi, rsi
0x18001c5c8  jnz     short loc_18001C5CF
0x18001c5ca  mov     rax, r13
0x18001c5cd  jmp     short loc_18001C5D8
0x18001c5cf  mov     rcx, rsi
0x18001c5d2  call    cs:__imp_sqlite3_errmsg
0x18001c5d8  mov     r13, qword ptr [rsp+1A0h+var_140]
0x18001c5dd  mov     r9d, 1
0x18001c5e3  cmp     r12d, r9d
0x18001c5e6  jnz     loc_18001C7E4
0x18001c5ec  test    r13, r13
0x18001c5ef  lea     r8, asc_18003D024; " "
0x18001c5f6  lea     rdx, aNull; "<null>"
0x18001c5fd  cmovnz  rdx, r13
0x18001c601  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18001c608  test    rax, rax
0x18001c60b  cmovnz  rcx, rax
0x18001c60f  cmp     [rbp+0A0h+var_D0], 0
0x18001c613  lea     rax, dword_180034EEC
0x18001c61a  cmovnz  rax, r8
0x18001c61e  mov     r8d, r9d
0x18001c621  lock xadd cs:dword_18004BFF0, r8d
0x18001c62a  mov     [rsp+1A0h+var_150], rdx
0x18001c62f  add     r8d, r9d
0x18001c632  mov     [rsp+1A0h+var_158], rcx
0x18001c637  lea     rdx, aSqlite3StepUDa; "[sqlite3_step] #%u Database %llu: State"...
0x18001c63e  lea     rcx, [rbp+0A0h+var_D0]
0x18001c642  mov     [rsp+1A0h+var_160], rcx
0x18001c647  mov     ecx, edi
0x18001c649  mov     [rsp+1A0h+var_168], rax
0x18001c64e  mov     rax, [rsp+1A0h+var_138]
0x18001c653  mov     [rsp+1A0h+var_170], rbx
0x18001c658  mov     dword ptr [rsp+1A0h+var_178], r9d
0x18001c65d  mov     r9, r15
0x18001c660  mov     qword ptr [rsp+1A0h+var_180], rax
0x18001c665  call    cs:__imp_sqlite3_log
0x18001c66b  jmp     loc_18001C7E4
0x18001c670  cmp     r12d, 1
0x18001c674  jbe     loc_18001C7E4
0x18001c67a  xor     r13d, r13d
0x18001c67d  test    rsi, rsi
0x18001c680  jnz     short loc_18001C68E
0x18001c682  mov     rcx, r14
0x18001c685  call    cs:__imp_sqlite3_db_handle
0x18001c68b  mov     rsi, rax
0x18001c68e  test    r15, r15
0x18001c691  jnz     short loc_18001C6A6
0x18001c693  lea     rdx, aConnectionId; "connection.id"
0x18001c69a  mov     rcx, rsi
0x18001c69d  call    cs:__imp_sqlite3_get_clientdata
0x18001c6a3  mov     r15, rax
0x18001c6a6  mov     rcx, r14
0x18001c6a9  call    cs:__imp_sqlite3_stmt_busy
0x18001c6af  test    eax, eax
0x18001c6b1  lea     rcx, aBusy; "BUSY"
0x18001c6b8  lea     rax, aOk; "OK"
0x18001c6bf  cmovz   rcx, rax
0x18001c6c3  xor     edx, edx; Val
0x18001c6c5  mov     [rsp+1A0h+var_138], rcx
0x18001c6ca  lea     rcx, [rbp+0A0h+var_90]; void *
0x18001c6ce  lea     r8d, [rdx+40h]; Size
0x18001c6d2  call    memset_0
0x18001c6d7  mov     ecx, edi; int
0x18001c6d9  call    ?IsHresultSqliteBusyOrLocked@@YA_NJ@Z; IsHresultSqliteBusyOrLocked(long)
0x18001c6de  test    al, al
0x18001c6e0  jz      short loc_18001C73E
0x18001c6e2  xor     edx, edx; Val
0x18001c6e4  lea     rcx, [rbp+0A0h+var_120]; void *
0x18001c6e8  lea     r8d, [rdx+48h]; Size
0x18001c6ec  call    memset_0
0x18001c6f1  xor     eax, eax
0x18001c6f3  mov     [rbp+0A0h+var_108], r13
0x18001c6f7  mov     [rbp+0A0h+var_F8], r13
0x18001c6fb  lea     rdx, [rbp+0A0h+var_90]; char (*)[64]
0x18001c6ff  mov     [rbp+0A0h+var_E8], r13
0x18001c703  lea     rcx, [rbp+0A0h+var_120]; this
0x18001c707  mov     qword ptr [rbp+0A0h+var_E0], r13
0x18001c70b  mov     dword ptr [rbp+0A0h+var_108+4], eax
0x18001c70e  mov     dword ptr [rbp+0A0h+var_F8+4], eax
0x18001c711  mov     [rbp+0A0h+var_E8+4], rax
0x18001c715  mov     [rbp+0A0h+var_E0+4], eax
0x18001c718  mov     [rbp+0A0h+var_110], r13
0x18001c71c  mov     byte ptr [rbp+0A0h+var_108], r13b
0x18001c720  mov     [rbp+0A0h+var_100], r13
0x18001c724  mov     byte ptr [rbp+0A0h+var_F8], r13b
0x18001c728  mov     [rbp+0A0h+var_F0], r13
0x18001c72c  mov     byte ptr [rbp+0A0h+var_E8], r13b
0x18001c730  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18001c735  lea     rcx, [rbp+0A0h+var_120]; this
0x18001c739  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x18001c73e  test    rsi, rsi
0x18001c741  jz      short loc_18001C74F
0x18001c743  mov     rcx, rsi
0x18001c746  call    cs:__imp_sqlite3_errmsg
0x18001c74c  mov     r13, rax
0x18001c74f  mov     rcx, r14
0x18001c752  call    cs:__imp_sqlite3_sql
0x18001c758  test    rax, rax
0x18001c75b  mov     qword ptr [rsp+1A0h+var_140], rax
0x18001c760  lea     r8, asc_18003D024; " "
0x18001c767  lea     rdx, aNull; "<null>"
0x18001c76e  cmovnz  rdx, rax
0x18001c772  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18001c779  test    r13, r13
0x18001c77c  lea     rax, dword_180034EEC
0x18001c783  cmovnz  rcx, r13
0x18001c787  cmp     [rbp+0A0h+var_90], 0
0x18001c78b  cmovnz  rax, r8
0x18001c78f  mov     r8d, 1
0x18001c795  lock xadd cs:dword_18004BFF0, r8d
0x18001c79e  mov     [rsp+1A0h+var_150], rdx
0x18001c7a3  inc     r8d
0x18001c7a6  mov     [rsp+1A0h+var_158], rcx
0x18001c7ab  lea     rdx, aSqlite3StepFin; "[sqlite3_step_final] #%u Database %llu:"...
0x18001c7b2  lea     rcx, [rbp+0A0h+var_90]
0x18001c7b6  mov     r9, r15
0x18001c7b9  mov     [rsp+1A0h+var_160], rcx
0x18001c7be  mov     ecx, edi
0x18001c7c0  mov     [rsp+1A0h+var_168], rax
0x18001c7c5  mov     rax, [rsp+1A0h+var_138]
0x18001c7ca  mov     [rsp+1A0h+var_170], rbx
0x18001c7cf  mov     dword ptr [rsp+1A0h+var_178], r12d
0x18001c7d4  mov     qword ptr [rsp+1A0h+var_180], rax
0x18001c7d9  call    cs:__imp_sqlite3_log
  ... truncated ...
```
