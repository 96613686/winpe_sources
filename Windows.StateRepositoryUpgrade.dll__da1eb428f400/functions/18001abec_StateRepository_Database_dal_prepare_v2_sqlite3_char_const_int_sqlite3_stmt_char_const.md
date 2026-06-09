# StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)

- ea: `0x18001abec`
- end: `0x18001b0bf`
- name: `?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z`
- size: `1235`
- prototype: `__int64 __fastcall(struct sqlite3 *, const char *, int, struct sqlite3_stmt **, const char **)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x180019614`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x18000c3bc`
- `0x180015204`
- `0x180018254`
- `0x180018694`
- `0x180018cb4`
- `0x180018f14`
- `0x180018f3c`
- `0x1800194f4`
- `0x1800195ac`
- `0x18001abec`
- `0x1800264b0`
- `0x18002650c`
- `0x180028200`
- `0x180029914`
- `0x18002a300`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001acd0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18001acd0`
- `StateRepository.Core!sqlite3_log` at `0x18001ac98`
- `StateRepository.Core!sqlite3_log` at `0x18001ae8d`
- `StateRepository.Core!sqlite3_log` at `0x18001af40`
- `StateRepository.Core!sqlite3_log` at `0x18001b051`
- `StateRepository.Core!sqlite3_log` at `0x18001b090`
- `StateRepository.Core!sqlite3_log` at `0x18001ac98`
- `StateRepository.Core!sqlite3_log` at `0x18001ae8d`
- `StateRepository.Core!sqlite3_log` at `0x18001af40`
- `StateRepository.Core!sqlite3_log` at `0x18001b051`
- `StateRepository.Core!sqlite3_log` at `0x18001b090`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001ad99`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001afe8`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001ad99`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001afe8`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001ac60`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x18001ac60`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001aeed`
- `StateRepository.Core!sqlite3_stmt_busy` at `0x18001aeed`
- `StateRepository.Core!sqlite3_prepare_v2` at `0x18001acec`
- `StateRepository.Core!sqlite3_prepare_v2` at `0x18001acec`

## string_xrefs

- `0x18001ac42`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18001ad82`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::dal_prepare_v2(
        struct sqlite3 *a1,
        char *a2,
        __int64 a3,
        struct sqlite3_stmt **a4)
{
  struct sqlite3_stmt **v4; // rdi
  int v7; // eax
  __int64 clientdata; // rax
  StateRepository::Time *v9; // rcx
  __int64 v10; // r12
  unsigned int v11; // esi
  unsigned __int64 UnbiasedInterruptTimeAsMSec; // r13
  unsigned __int64 v13; // r15
  int v14; // eax
  StateRepository::Time *v15; // rcx
  unsigned int busy; // edi
  int v17; // edx
  bool v18; // r13
  int v19; // eax
  struct sqlite3_stmt *v20; // r9
  const char *v21; // rcx
  const char *v22; // rax
  StateRepository::Logging *v23; // rcx
  const char *v24; // rbx
  unsigned __int64 v25; // rax
  const char *v26; // rax
  unsigned __int64 v27; // rax
  int v29; // [rsp+20h] [rbp-E0h]
  __int64 v30; // [rsp+28h] [rbp-D8h]
  unsigned __int64 v31; // [rsp+30h] [rbp-D0h]
  unsigned __int64 v32; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  _BYTE v36[16]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v37; // [rsp+80h] [rbp-80h]
  __int64 v38; // [rsp+88h] [rbp-78h]
  __int64 v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h]
  __int64 v41; // [rsp+A0h] [rbp-60h]
  int v42; // [rsp+A8h] [rbp-58h]
  __int64 v43; // [rsp+ACh] [rbp-54h]
  int v44; // [rsp+B4h] [rbp-4Ch]
  char v45[64]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v4 = a4;
  if ( (dword_18004B904 & 0x2000) != 0 )
  {
    v7 = StateRepository::Database::CheckBusyStatements(a1, 1, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10B4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v7,
        v29);
  }
  clientdata = sqlite3_get_clientdata(a1, "connection.id");
  v10 = clientdata;
  if ( (dword_18004B904 & 0x40000) != 0 )
    sqlite3_log(
      0,
      "[pre-sqlite3_prepare] #%u Database %llu : SQL %s",
      _InterlockedIncrement(&dword_18004BFF0),
      clientdata,
      a2);
  v11 = 0;
  v33 = qword_18004B8F8;
  UnbiasedInterruptTimeAsMSec = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v9);
  v32 = UnbiasedInterruptTimeAsMSec;
  v13 = 0;
  while ( 1 )
  {
    if ( ++v11 > 1 )
      Sleep(dwMilliseconds);
    v14 = sqlite3_prepare_v2(a1, a2, 0xFFFFFFFFLL, v4, 0, v30, v31);
    busy = v14;
    if ( v14 > 0 )
      busy = (unsigned __int16)v14 | 0x87AF0000;
    if ( (busy & 0x80000000) == 0 )
    {
      if ( v11 > 1 )
      {
        memset_0(v45, 0, sizeof(v45));
        if ( IsHresultSqliteBusyOrLocked(busy) )
        {
          memset_0(v36, 0, 0x48u);
          v38 = 0;
          v40 = 0;
          v42 = 0;
          v37 = 0;
          v39 = 0;
          v41 = 0;
          v43 = 0;
          v44 = 0;
          StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
            (StateRepository::ResourcePriority::AutoPriority *)v36,
            (char (*)[64])v45);
          StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v36);
        }
        sqlite3_errmsg(a1);
        v26 = (const char *)&dword_180034EEC;
        if ( v45[0] )
          v26 = " ";
        sqlite3_log(
          busy,
          "[sqlite3_prepare_final] #%u Database %llu: Try %u (%llums) %s : SQL %s",
          _InterlockedIncrement(&dword_18004BFF0),
          v10,
          v11,
          v13,
          v26,
          v45);
      }
    }
    else
    {
      v13 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v15) - UnbiasedInterruptTimeAsMSec;
      busy = MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(busy, a1);
      v18 = IsHresultSqliteBusyOrLocked(busy);
      if ( v18 && v13 < v33 )
      {
        busy = MapHresultSqliteBusyOrLockedToRetry(busy);
      }
      else if ( (busy & 0xFFFF00FF) == 0x87AF000B )
      {
        StateRepository::ErrorTracking::details::TrackCorruptError((StateRepository::ErrorTracking::details *)busy, v17);
        v31 = v13;
        v30 = v11;
        v19 = StateRepository::Logging::ReportDatabaseCorruption(busy, "sqlite3_prepare_v2", 0, a1);
        if ( v19 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x10DA,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)(unsigned int)v19,
            (int)a2);
      }
      v35 = sqlite3_errmsg(a1);
      memset_0(v45, 0, sizeof(v45));
      if ( v18 )
      {
        memset_0(v36, 0, 0x48u);
        v38 = 0;
        v40 = 0;
        v42 = 0;
        v43 = 0;
        v44 = 0;
        v37 = 0;
        v39 = 0;
        v41 = 0;
        StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
          (StateRepository::ResourcePriority::AutoPriority *)v36,
          (char (*)[64])v45);
        StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v36);
      }
      if ( v11 == 1 )
      {
        v21 = "<no-error-message>";
        if ( v35 )
          v21 = (const char *)v35;
        v22 = (const char *)&dword_180034EEC;
        if ( v45[0] )
          v22 = " ";
        sqlite3_log(
          busy,
          "[sqlite3_prepare] #%u Database %llu: Try %u (%llums)%s%s %s : SQL %s",
          _InterlockedIncrement(&dword_18004BFF0),
          v10,
          1,
          v13,
          v22,
          v45,
          v21,
          a2);
      }
      if ( busy == -2018573819 )
      {
        StateRepository::Logging::FailFastBusySnapshot(a1, (struct sqlite3 *)a2, 0, v20);
      }
      else if ( busy == -2018574335 )
      {
        StateRepository::Database::FailFastIfNestingTransaction(a1);
      }
      UnbiasedInterruptTimeAsMSec = v32;
    }
    if ( !IsHresultSqliteBusyOrLockedOrRetry(busy) )
      break;
    StateRepository::Logging::DebugBreak(v23);
    if ( v13 >= v33 )
      break;
    v4 = a4;
  }
  if ( (dword_18004B904 & 0x80000) != 0 )
  {
    if ( (busy & 0x80000000) != 0 )
    {
      v27 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v23);
      sqlite3_log(
        busy,
        "[post-sqlite3_prepare] #%u Database %llu: Statement -------- --: Try %u (%llums) : SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        v10,
        v11,
        v27 - UnbiasedInterruptTimeAsMSec,
        a2);
    }
    else
    {
      v24 = "BUSY";
      if ( !(unsigned int)sqlite3_stmt_busy(*a4) )
        v24 = "OK";
      v25 = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec((StateRepository::Time *)"OK");
      sqlite3_log(
        busy,
        "[post-sqlite3_prepare] #%u Database %llu: Statement %s: Try %u (%llums) : SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        v10,
        v24,
        v11,
        v25 - UnbiasedInterruptTimeAsMSec,
        a2);
    }
  }
  return busy;
}

```

## disassembly

```asm
0x18001abec  mov     [rsp-8+arg_10], rbx
0x18001abf1  push    rbp
0x18001abf2  push    rsi
0x18001abf3  push    rdi
0x18001abf4  push    r12
0x18001abf6  push    r13
0x18001abf8  push    r14
0x18001abfa  push    r15
0x18001abfc  lea     rbp, [rsp-10h]
0x18001ac01  sub     rsp, 110h
0x18001ac08  mov     rax, cs:__security_cookie
0x18001ac0f  xor     rax, rsp
0x18001ac12  mov     [rbp+40h+var_40], rax
0x18001ac16  test    cs:dword_18004B904, 2000h
0x18001ac20  mov     rdi, r9
0x18001ac23  mov     [rsp+140h+var_E0], r9
0x18001ac28  mov     r14, rdx
0x18001ac2b  mov     rbx, rcx
0x18001ac2e  jz      short loc_18001AC56
0x18001ac30  xor     r8d, r8d; unsigned int *
0x18001ac33  mov     dl, 1; bool
0x18001ac35  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x18001ac3a  test    eax, eax
0x18001ac3c  jns     short loc_18001AC56
0x18001ac3e  mov     rcx, [rbp+48h]; this
0x18001ac42  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001ac49  mov     r9d, eax; char *
0x18001ac4c  mov     edx, 10B4h; void *
0x18001ac51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ac56  lea     rdx, aConnectionId; "connection.id"
0x18001ac5d  mov     rcx, rbx
0x18001ac60  call    cs:__imp_sqlite3_get_clientdata
0x18001ac66  test    cs:dword_18004B904, 40000h
0x18001ac70  mov     r12, rax
0x18001ac73  jz      short loc_18001AC9E
0x18001ac75  mov     r8d, 1
0x18001ac7b  lock xadd cs:dword_18004BFF0, r8d
0x18001ac84  inc     r8d
0x18001ac87  mov     qword ptr [rsp+140h+var_120], r14
0x18001ac8c  mov     r9, rax
0x18001ac8f  lea     rdx, aPreSqlite3Prep; "[pre-sqlite3_prepare] #%u Database %llu"...
0x18001ac96  xor     ecx, ecx
0x18001ac98  call    cs:__imp_sqlite3_log
0x18001ac9e  mov     rax, cs:qword_18004B8F8
0x18001aca5  xor     esi, esi
0x18001aca7  mov     [rsp+140h+var_E8], rax
0x18001acac  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001acb1  mov     r13, rax
0x18001acb4  mov     [rsp+140h+var_F0], rax
0x18001acb9  xor     r15d, r15d
0x18001acbc  jmp     short loc_18001ACC3
0x18001acbe  mov     rdi, [rsp+140h+var_E0]
0x18001acc3  inc     esi
0x18001acc5  cmp     esi, 1
0x18001acc8  jbe     short loc_18001ACD6
0x18001acca  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x18001acd0  call    cs:__imp_Sleep
0x18001acd6  mov     r9, rdi
0x18001acd9  mov     qword ptr [rsp+140h+var_120], 0
0x18001ace2  or      r8d, 0FFFFFFFFh
0x18001ace6  mov     rdx, r14
0x18001ace9  mov     rcx, rbx
0x18001acec  call    cs:__imp_sqlite3_prepare_v2
0x18001acf2  mov     edi, eax
0x18001acf4  test    eax, eax
0x18001acf6  jle     short loc_18001AD01
0x18001acf8  movzx   edi, ax
0x18001acfb  or      edi, 87AF0000h
0x18001ad01  test    edi, edi
0x18001ad03  jns     loc_18001AF64
0x18001ad09  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001ad0e  mov     r15, rax
0x18001ad11  mov     rdx, rbx; struct sqlite3 *
0x18001ad14  mov     ecx, edi; int
0x18001ad16  sub     r15, r13
0x18001ad19  call    ?MapSqliteBusySnapshotToSqliteBusyIfRaceCondition@@YAJJPEAUsqlite3@@@Z; MapSqliteBusySnapshotToSqliteBusyIfRaceCondition(long,sqlite3 *)
0x18001ad1e  mov     ecx, eax; int
0x18001ad20  mov     edi, eax
0x18001ad22  call    ?IsHresultSqliteBusyOrLocked@@YA_NJ@Z; IsHresultSqliteBusyOrLocked(long)
0x18001ad27  mov     r13b, al
0x18001ad2a  test    al, al
0x18001ad2c  jz      short loc_18001AD40
0x18001ad2e  cmp     r15, [rsp+140h+var_E8]
0x18001ad33  jnb     short loc_18001AD40
0x18001ad35  mov     ecx, edi; int
0x18001ad37  call    ?MapHresultSqliteBusyOrLockedToRetry@@YAJJ@Z; MapHresultSqliteBusyOrLockedToRetry(long)
0x18001ad3c  mov     edi, eax
0x18001ad3e  jmp     short loc_18001AD96
0x18001ad40  mov     eax, edi
0x18001ad42  and     eax, 0FFFF00FFh
0x18001ad47  cmp     eax, 87AF000Bh
0x18001ad4c  jnz     short loc_18001AD96
0x18001ad4e  mov     ecx, edi; this
0x18001ad50  call    ?TrackCorruptError@details@ErrorTracking@StateRepository@@YAXJ@Z; StateRepository::ErrorTracking::details::TrackCorruptError(long)
0x18001ad55  mov     eax, esi
0x18001ad57  lea     rdx, aSqlite3Prepare; "sqlite3_prepare_v2"
0x18001ad5e  mov     [rsp+140h+var_110], r15
0x18001ad63  mov     r9, rbx
0x18001ad66  mov     [rsp+140h+var_118], rax
0x18001ad6b  xor     r8d, r8d
0x18001ad6e  mov     ecx, edi
0x18001ad70  mov     qword ptr [rsp+140h+var_120], r14; int
0x18001ad75  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x18001ad7a  test    eax, eax
0x18001ad7c  jns     short loc_18001AD96
0x18001ad7e  mov     rcx, [rbp+48h]; this
0x18001ad82  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x18001ad89  mov     r9d, eax; char *
0x18001ad8c  mov     edx, 10DAh; void *
0x18001ad91  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ad96  mov     rcx, rbx
0x18001ad99  call    cs:__imp_sqlite3_errmsg
0x18001ad9f  xor     edx, edx; Val
0x18001ada1  lea     rcx, [rbp+40h+var_80]; void *
0x18001ada5  mov     [rsp+140h+var_D8], rax
0x18001adaa  lea     r8d, [rdx+40h]; Size
0x18001adae  call    memset_0
0x18001adb3  test    r13b, r13b
0x18001adb6  jz      short loc_18001AE1C
0x18001adb8  xor     edx, edx; Val
0x18001adba  lea     rcx, [rsp+140h+var_D0]; void *
0x18001adbf  lea     r8d, [rdx+48h]; Size
0x18001adc3  call    memset_0
0x18001adc8  xor     r13d, r13d
0x18001adcb  lea     rdx, [rbp+40h+var_80]; char (*)[64]
0x18001adcf  xor     eax, eax
0x18001add1  mov     [rbp+40h+var_B8], r13
0x18001add5  mov     [rbp+40h+var_A8], r13
0x18001add9  lea     rcx, [rsp+140h+var_D0]; this
0x18001adde  mov     [rbp+40h+var_98], r13
0x18001ade2  mov     qword ptr [rbp+40h+var_90], r13
0x18001ade6  mov     byte ptr [rbp+40h+var_B8], r13b
0x18001adea  mov     dword ptr [rbp+40h+var_B8+4], eax
0x18001aded  mov     byte ptr [rbp+40h+var_A8], r13b
0x18001adf1  mov     dword ptr [rbp+40h+var_A8+4], eax
0x18001adf4  mov     byte ptr [rbp+40h+var_98], r13b
0x18001adf8  mov     [rbp+40h+var_98+4], rax
0x18001adfc  mov     [rbp+40h+var_90+4], eax
0x18001adff  mov     [rbp+40h+var_C0], r13
0x18001ae03  mov     [rbp+40h+var_B0], r13
0x18001ae07  mov     [rbp+40h+var_A0], r13
0x18001ae0b  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18001ae10  lea     rcx, [rsp+140h+var_D0]; this
0x18001ae15  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x18001ae1a  jmp     short loc_18001AE1F
0x18001ae1c  xor     r13d, r13d
0x18001ae1f  mov     edx, 1
0x18001ae24  cmp     esi, edx
0x18001ae26  jnz     short loc_18001AE93
0x18001ae28  mov     rax, [rsp+140h+var_D8]
0x18001ae2d  lea     r8, asc_18003D024; " "
0x18001ae34  test    rax, rax
0x18001ae37  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18001ae3e  cmovnz  rcx, rax
0x18001ae42  cmp     [rbp+40h+var_80], r13b
0x18001ae46  lea     rax, dword_180034EEC
0x18001ae4d  cmovnz  rax, r8
0x18001ae51  mov     r8d, edx
0x18001ae54  lock xadd cs:dword_18004BFF0, r8d
0x18001ae5d  mov     [rsp+140h+var_F8], r14
0x18001ae62  add     r8d, edx
0x18001ae65  mov     [rsp+140h+var_100], rcx
0x18001ae6a  mov     r9, r12
0x18001ae6d  lea     rcx, [rbp+40h+var_80]
0x18001ae71  mov     [rsp+140h+var_108], rcx
0x18001ae76  mov     ecx, edi
0x18001ae78  mov     [rsp+140h+var_110], rax
0x18001ae7d  mov     [rsp+140h+var_118], r15
0x18001ae82  mov     [rsp+140h+var_120], edx
0x18001ae86  lea     rdx, aSqlite3Prepare_1; "[sqlite3_prepare] #%u Database %llu: Tr"...
0x18001ae8d  call    cs:__imp_sqlite3_log
0x18001ae93  cmp     edi, 87AF0205h
0x18001ae99  jnz     loc_18001AF4B
0x18001ae9f  xor     r8d, r8d; char *
0x18001aea2  mov     rdx, r14; struct sqlite3 *
0x18001aea5  mov     rcx, rbx; this
0x18001aea8  call    ?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z; StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)
0x18001aead  mov     r13, [rsp+140h+var_F0]
0x18001aeb2  mov     ecx, edi; int
0x18001aeb4  call    ?IsHresultSqliteBusyOrLockedOrRetry@@YA_NJ@Z; IsHresultSqliteBusyOrLockedOrRetry(long)
0x18001aeb9  test    al, al
0x18001aebb  jz      short loc_18001AECD
0x18001aebd  call    ?DebugBreak@Logging@StateRepository@@YAXXZ; StateRepository::Logging::DebugBreak(void)
0x18001aec2  cmp     r15, [rsp+140h+var_E8]
0x18001aec7  jb      loc_18001ACBE
0x18001aecd  test    cs:dword_18004B904, 80000h
0x18001aed7  jz      loc_18001B096
0x18001aedd  test    edi, edi
0x18001aedf  js      loc_18001B05C
0x18001aee5  mov     rcx, [rsp+140h+var_E0]
0x18001aeea  mov     rcx, [rcx]
0x18001aeed  call    cs:__imp_sqlite3_stmt_busy
0x18001aef3  test    eax, eax
0x18001aef5  lea     rcx, aOk; "OK"
0x18001aefc  lea     rbx, aBusy; "BUSY"
0x18001af03  cmovz   rbx, rcx
0x18001af07  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001af0c  sub     rax, r13
0x18001af0f  mov     r8d, 1
0x18001af15  lock xadd cs:dword_18004BFF0, r8d
0x18001af1e  mov     [rsp+140h+var_108], r14
0x18001af23  lea     rdx, aPostSqlite3Pre; "[post-sqlite3_prepare] #%u Database %ll"...
0x18001af2a  mov     [rsp+140h+var_110], rax
0x18001af2f  inc     r8d
0x18001af32  mov     dword ptr [rsp+140h+var_118], esi
0x18001af36  mov     r9, r12
0x18001af39  mov     ecx, edi
0x18001af3b  mov     qword ptr [rsp+140h+var_120], rbx
0x18001af40  call    cs:__imp_sqlite3_log
0x18001af46  jmp     loc_18001B096
0x18001af4b  cmp     edi, 87AF0001h
0x18001af51  jnz     loc_18001AEAD
0x18001af57  mov     rcx, rbx; struct sqlite3 *
0x18001af5a  call    ?FailFastIfNestingTransaction@Database@StateRepository@@CAXPEAUsqlite3@@@Z; StateRepository::Database::FailFastIfNestingTransaction(sqlite3 *)
0x18001af5f  jmp     loc_18001AEAD
0x18001af64  cmp     esi, 1
0x18001af67  jbe     loc_18001AEB2
0x18001af6d  xor     edx, edx; Val
0x18001af6f  lea     rcx, [rbp+40h+var_80]; void *
0x18001af73  lea     r8d, [rdx+40h]; Size
0x18001af77  call    memset_0
0x18001af7c  mov     ecx, edi; int
0x18001af7e  call    ?IsHresultSqliteBusyOrLocked@@YA_NJ@Z; IsHresultSqliteBusyOrLocked(long)
0x18001af83  test    al, al
0x18001af85  jz      short loc_18001AFE5
0x18001af87  xor     edx, edx; Val
0x18001af89  lea     rcx, [rsp+140h+var_D0]; void *
0x18001af8e  lea     r8d, [rdx+48h]; Size
0x18001af92  call    memset_0
0x18001af97  xor     ecx, ecx
0x18001af99  lea     rdx, [rbp+40h+var_80]; char (*)[64]
0x18001af9d  xor     eax, eax
0x18001af9f  mov     [rbp+40h+var_B8], rcx
0x18001afa3  mov     [rbp+40h+var_A8], rcx
0x18001afa7  mov     [rbp+40h+var_98], rcx
0x18001afab  mov     qword ptr [rbp+40h+var_90], rcx
0x18001afaf  mov     byte ptr [rbp+40h+var_B8], cl
0x18001afb2  mov     byte ptr [rbp+40h+var_A8], cl
0x18001afb5  mov     byte ptr [rbp+40h+var_98], cl
0x18001afb8  mov     [rbp+40h+var_C0], rcx
0x18001afbc  mov     [rbp+40h+var_B0], rcx
0x18001afc0  mov     [rbp+40h+var_A0], rcx
0x18001afc4  lea     rcx, [rsp+140h+var_D0]; this
0x18001afc9  mov     dword ptr [rbp+40h+var_B8+4], eax
0x18001afcc  mov     dword ptr [rbp+40h+var_A8+4], eax
0x18001afcf  mov     [rbp+40h+var_98+4], rax
0x18001afd3  mov     [rbp+40h+var_90+4], eax
0x18001afd6  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18001afdb  lea     rcx, [rsp+140h+var_D0]; this
0x18001afe0  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x18001afe5  mov     rcx, rbx
0x18001afe8  call    cs:__imp_sqlite3_errmsg
0x18001afee  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18001aff5  mov     r8d, 1
0x18001affb  test    rax, rax
0x18001affe  lea     rdx, asc_18003D024; " "
0x18001b005  cmovnz  rcx, rax
0x18001b009  cmp     [rbp+40h+var_80], 0
0x18001b00d  lea     rax, dword_180034EEC
0x18001b014  cmovnz  rax, rdx
0x18001b018  lock xadd cs:dword_18004BFF0, r8d
0x18001b021  mov     [rsp+140h+var_F8], r14
0x18001b026  lea     rdx, aSqlite3Prepare_0; "[sqlite3_prepare_final] #%u Database %l"...
0x18001b02d  mov     [rsp+140h+var_100], rcx
0x18001b032  inc     r8d
0x18001b035  lea     rcx, [rbp+40h+var_80]
0x18001b039  mov     r9, r12
0x18001b03c  mov     [rsp+140h+var_108], rcx
0x18001b041  mov     ecx, edi
0x18001b043  mov     [rsp+140h+var_110], rax
0x18001b048  mov     [rsp+140h+var_118], r15
0x18001b04d  mov     [rsp+140h+var_120], esi
0x18001b051  call    cs:__imp_sqlite3_log
0x18001b057  jmp     loc_18001AEB2
0x18001b05c  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18001b061  sub     rax, r13
0x18001b064  mov     r8d, 1
0x18001b06a  lock xadd cs:dword_18004BFF0, r8d
0x18001b073  mov     [rsp+140h+var_110], r14
0x18001b078  lea     rdx, aPostSqlite3Pre_0; "[post-sqlite3_prepare] #%u Database %ll"...
0x18001b07f  mov     [rsp+140h+var_118], rax
0x18001b084  inc     r8d
0x18001b087  mov     r9, r12
0x18001b08a  mov     [rsp+140h+var_120], esi
0x18001b08e  mov     ecx, edi
0x18001b090  call    cs:__imp_sqlite3_log
0x18001b096  mov     eax, edi
0x18001b098  mov     rcx, [rbp+40h+var_40]
0x18001b09c  xor     rcx, rsp; StackCookie
0x18001b09f  call    __security_check_cookie
0x18001b0a4  mov     rbx, [rsp+140h+arg_10]
0x18001b0ac  add     rsp, 110h
0x18001b0b3  pop     r15
0x18001b0b5  pop     r14
0x18001b0b7  pop     r13
0x18001b0b9  pop     r12
0x18001b0bb  pop     rdi
0x18001b0bc  pop     rsi
0x18001b0bd  pop     rbp
0x18001b0be  retn
  ... truncated ...
```
