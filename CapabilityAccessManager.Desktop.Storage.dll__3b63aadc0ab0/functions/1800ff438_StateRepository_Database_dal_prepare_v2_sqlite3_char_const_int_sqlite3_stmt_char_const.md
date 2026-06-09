# StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)

- ea: `0x1800ff438`
- end: `0x1800ffad6`
- name: `?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z`
- size: `1694`
- prototype: `__int64 __fastcall(struct sqlite3 *, char *, __int64, struct sqlite3_stmt **)`
- caller_count: `2`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1800f6a20`
- `0x1800fb06c`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180006a00`
- `0x180006f40`
- `0x180007280`
- `0x18000ecf0`
- `0x18000f220`
- `0x180016970`
- `0x1800f7630`
- `0x1800f85a8`
- `0x1800f89f4`
- `0x1800f9468`
- `0x1800ff438`
- `0x180102b2c`
- `0x180103cd8`
- `0x180106704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ff524`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800ff524`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ff87c`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x1800ff87c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff4ef`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff56a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff8fc`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ffa5f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff4ef`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff56a`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ff8fc`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800ffa5f`

## string_xrefs

- `0x1800ff48e`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800ff6f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::dal_prepare_v2(
        struct sqlite3 *a1,
        char *a2,
        __int64 a3,
        struct sqlite3_stmt **a4)
{
  int v4; // ebx
  int v7; // eax
  unsigned int v8; // r12d
  unsigned __int64 v9; // r14
  unsigned __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // ebx
  char v15; // r14
  unsigned int v16; // edi
  volatile signed __int64 *v17; // rax
  __int64 i; // rdx
  __int64 stmt; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rbx
  struct sqlite3_stmt *v25; // r9
  const char *v26; // rcx
  const char *v27; // rax
  int v28; // eax
  const char *v29; // rbx
  const char *v30; // rax
  unsigned __int64 v32; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int64 v34; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v35; // [rsp+68h] [rbp-98h]
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

  v4 = (int)a4;
  v32 = (unsigned __int64)a4;
  if ( (dword_18013F948 & 0x2000) != 0 )
  {
    v7 = StateRepository::Database::CheckBusyStatements(a1, 1, 0);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x10B4,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v7);
  }
  if ( (dword_18013F948 & 0x40000) != 0 )
    sqlite3_log(0, "[pre-sqlite3_prepare] #%u Database %llu : SQL %s", _InterlockedIncrement(&dword_180140410), 0, a2);
  v8 = 0;
  v35 = qword_18013F940;
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v9 = UnbiasedTime / 0x2710;
  UnbiasedTime /= 0x2710u;
  v10 = 0;
  while ( 1 )
  {
    if ( ++v8 > 1 )
      Sleep(dwMilliseconds);
    v11 = sqlite3_prepare_v2((_DWORD)a1, (_DWORD)a2, -1, v4, 0);
    v14 = v11;
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x87AF0000;
    if ( (v14 & 0x80000000) == 0 )
      break;
    v34 = 0;
    QueryUnbiasedInterruptTime(&v34);
    v10 = v34 / 0x2710 - v9;
    if ( v14 == -2018573819 )
    {
      if ( (unsigned int)sqlite3_get_autocommit(a1) )
      {
        for ( i = 0; ; i = v22 )
        {
          stmt = sqlite3_next_stmt(a1, i);
          v22 = stmt;
          if ( !stmt )
            break;
          if ( (unsigned int)sqlite3_stmt_busy(stmt, v20, v21) )
            goto LABEL_15;
        }
        v14 = -2018574331;
        goto LABEL_27;
      }
      v14 = -2018573819;
    }
    else if ( v14 == -2018574331 || v14 == -2018574075 )
    {
      goto LABEL_27;
    }
LABEL_15:
    if ( (v14 & 0xFFFF00FF) != 0x87AF0006 )
    {
      v15 = 0;
      goto LABEL_17;
    }
LABEL_27:
    v15 = 1;
    if ( v10 < v35 )
    {
      switch ( v14 )
      {
        case 0x87AF0005:
          v16 = -2140733433;
          break;
        case 0x87AF0006:
          v16 = -2140733431;
          break;
        case 0x87AF0105:
          v16 = -2140733432;
          break;
        case 0x87AF0106:
          v16 = -2140733430;
          break;
        default:
          v16 = v14;
          break;
      }
      goto LABEL_45;
    }
LABEL_17:
    v16 = v14;
    if ( (v14 & 0xFFFF00FF) == 0x87AF000B )
    {
      switch ( v14 )
      {
        case 0x87AF000B:
          v17 = &qword_180140510;
          break;
        case 0x87AF030B:
          v17 = &qword_180140518;
          break;
        case 0x87AF020B:
          v17 = &qword_180140500;
          break;
        default:
          v17 = &qword_180140508;
          if ( v14 != -2018574069 )
            v17 = &qword_1801404F8;
          break;
      }
      _InterlockedIncrement64(v17);
      v23 = StateRepository::Logging::ReportDatabaseCorruption(v14, "sqlite3_prepare_v2", 0, a1);
      if ( v23 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x10DA,
          (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)(unsigned int)v23);
    }
LABEL_45:
    v24 = sqlite3_errmsg(a1);
    memset_0(v45, 0, sizeof(v45));
    if ( v15 )
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
    if ( v8 == 1 )
    {
      v26 = "<no-error-message>";
      v27 = byte_180122168;
      if ( v24 )
        v26 = (const char *)v24;
      if ( v45[0] )
        v27 = " ";
      sqlite3_log(
        v16,
        "[sqlite3_prepare] #%u Database %llu: Try %u (%llums)%s%s %s : SQL %s",
        _InterlockedIncrement(&dword_180140410),
        0,
        1,
        v10,
        v27,
        v45,
        v26,
        a2);
    }
    switch ( v16 )
    {
      case 0x87AF0205:
        StateRepository::Logging::FailFastBusySnapshot(a1, (struct sqlite3 *)a2, 0, v25);
LABEL_72:
        v9 = UnbiasedTime;
        goto LABEL_73;
      case 0x87AF0001:
        StateRepository::Database::FailFastIfNestingTransaction(a1);
        break;
      case 0x87AF0005:
      case 0x87AF0105:
      case 0x87AF0006:
      case 0x87AF0106:
      case 0x80670007:
      case 0x80670008:
      case 0x80670009:
      case 0x8067000A:
      case 0x8067000C:
      case 0x8067000D:
        goto LABEL_67;
    }
    if ( v16 + 2140733426 > 1 )
      goto LABEL_72;
LABEL_67:
    if ( (dword_18013F948 & 0x1000) != 0 )
      DebugBreak();
    v9 = UnbiasedTime;
    if ( v10 >= v35 )
      goto LABEL_73;
    v4 = v32;
  }
  v16 = v14;
  if ( v8 > 1 )
  {
    memset_0(v45, 0, sizeof(v45));
    if ( (v14 & 0xFFFF00FF) == 0x87AF0006 )
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
    v30 = byte_180122168;
    if ( v45[0] )
      v30 = " ";
    sqlite3_log(
      v14,
      "[sqlite3_prepare_final] #%u Database %llu: Try %u (%llums) %s : SQL %s",
      _InterlockedIncrement(&dword_180140410),
      0,
      v8,
      v10,
      v30,
      v45);
  }
LABEL_73:
  if ( (dword_18013F948 & 0x80000) != 0 )
  {
    if ( (v16 & 0x80000000) != 0 )
    {
      v32 = 0;
      QueryUnbiasedInterruptTime(&v32);
      sqlite3_log(
        v16,
        "[post-sqlite3_prepare] #%u Database %llu: Statement -------- --: Try %u (%llums) : SQL %s",
        _InterlockedIncrement(&dword_180140410),
        0,
        v8,
        v32 / 0x2710 - v9,
        a2);
    }
    else
    {
      v28 = sqlite3_stmt_busy(*(_QWORD *)v32, v12, v13);
      v32 = 0;
      v29 = "BUSY";
      if ( !v28 )
        v29 = "OK";
      QueryUnbiasedInterruptTime(&v32);
      sqlite3_log(
        v16,
        "[post-sqlite3_prepare] #%u Database %llu: Statement %s: Try %u (%llums) : SQL %s",
        _InterlockedIncrement(&dword_180140410),
        0,
        v29,
        v8,
        v32 / 0x2710 - v9,
        a2);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800ff438  mov     [rsp-8+arg_10], rbx
0x1800ff43d  push    rbp
0x1800ff43e  push    rsi
0x1800ff43f  push    rdi
0x1800ff440  push    r12
0x1800ff442  push    r13
0x1800ff444  push    r14
0x1800ff446  push    r15
0x1800ff448  lea     rbp, [rsp-10h]
0x1800ff44d  sub     rsp, 110h
0x1800ff454  mov     rax, cs:__security_cookie
0x1800ff45b  xor     rax, rsp
0x1800ff45e  mov     [rbp+40h+var_40], rax
0x1800ff462  test    cs:dword_18013F948, 2000h
0x1800ff46c  mov     rbx, r9
0x1800ff46f  mov     [rsp+140h+var_F0], rbx
0x1800ff474  mov     r13, rdx
0x1800ff477  mov     r15, rcx
0x1800ff47a  jz      short loc_1800FF4A2
0x1800ff47c  xor     r8d, r8d; unsigned int *
0x1800ff47f  mov     dl, 1; bool
0x1800ff481  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x1800ff486  test    eax, eax
0x1800ff488  jns     short loc_1800FF4A2
0x1800ff48a  mov     rcx, [rbp+48h]; this
0x1800ff48e  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800ff495  mov     r9d, eax; char *
0x1800ff498  mov     edx, 10B4h; void *
0x1800ff49d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff4a2  test    cs:dword_18013F948, 40000h
0x1800ff4ac  jz      short loc_1800FF4D6
0x1800ff4ae  mov     r8d, 1
0x1800ff4b4  lock xadd cs:dword_180140410, r8d
0x1800ff4bd  inc     r8d
0x1800ff4c0  mov     qword ptr [rsp+140h+var_120], r13
0x1800ff4c5  xor     r9d, r9d
0x1800ff4c8  lea     rdx, aPreSqlite3Prep; "[pre-sqlite3_prepare] #%u Database %llu"...
0x1800ff4cf  xor     ecx, ecx
0x1800ff4d1  call    sqlite3_log
0x1800ff4d6  mov     rax, cs:qword_18013F940
0x1800ff4dd  lea     rcx, [rsp+140h+UnbiasedTime]; UnbiasedTime
0x1800ff4e2  xor     r12d, r12d
0x1800ff4e5  mov     [rsp+140h+var_D8], rax
0x1800ff4ea  mov     [rsp+140h+UnbiasedTime], r12
0x1800ff4ef  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800ff4f5  mov     rdi, 346DC5D63886594Bh
0x1800ff4ff  mov     rax, rdi
0x1800ff502  mul     [rsp+140h+UnbiasedTime]
0x1800ff507  mov     r14, rdx
0x1800ff50a  shr     r14, 0Bh
0x1800ff50e  mov     [rsp+140h+UnbiasedTime], r14
0x1800ff513  xor     esi, esi
0x1800ff515  inc     r12d
0x1800ff518  cmp     r12d, 1
0x1800ff51c  jbe     short loc_1800FF52A
0x1800ff51e  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x1800ff524  call    cs:__imp_Sleep
0x1800ff52a  mov     r9, rbx
0x1800ff52d  mov     qword ptr [rsp+140h+var_120], 0
0x1800ff536  or      r8d, 0FFFFFFFFh
0x1800ff53a  mov     rdx, r13
0x1800ff53d  mov     rcx, r15
0x1800ff540  call    sqlite3_prepare_v2
0x1800ff545  mov     ebx, eax
0x1800ff547  test    eax, eax
0x1800ff549  jle     short loc_1800FF554
0x1800ff54b  movzx   ebx, ax
0x1800ff54e  or      ebx, 87AF0000h
0x1800ff554  test    ebx, ebx
0x1800ff556  jns     loc_1800FF954
0x1800ff55c  lea     rcx, [rsp+140h+var_E0]; UnbiasedTime
0x1800ff561  mov     [rsp+140h+var_E0], 0
0x1800ff56a  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800ff570  mov     rax, rdi
0x1800ff573  mov     edi, 87AF0205h
0x1800ff578  mul     [rsp+140h+var_E0]
0x1800ff57d  mov     rsi, rdx
0x1800ff580  shr     rsi, 0Bh
0x1800ff584  sub     rsi, r14
0x1800ff587  cmp     ebx, edi
0x1800ff589  jz      short loc_1800FF5D6
0x1800ff58b  cmp     ebx, 87AF0005h
0x1800ff591  jz      short loc_1800FF60E
0x1800ff593  cmp     ebx, 87AF0105h
0x1800ff599  jz      short loc_1800FF60E
0x1800ff59b  mov     eax, ebx
0x1800ff59d  and     eax, 0FFFF00FFh
0x1800ff5a2  cmp     eax, 87AF0006h
0x1800ff5a7  jz      short loc_1800FF60E
0x1800ff5a9  xor     r14b, r14b
0x1800ff5ac  mov     eax, ebx
0x1800ff5ae  mov     ecx, 87AF000Bh
0x1800ff5b3  and     eax, 0FFFF00FFh
0x1800ff5b8  mov     edi, ebx
0x1800ff5ba  cmp     eax, ecx
0x1800ff5bc  jnz     loc_1800FF705
0x1800ff5c2  cmp     ebx, ecx
0x1800ff5c4  jnz     loc_1800FF685
0x1800ff5ca  lea     rax, qword_180140510
0x1800ff5d1  jmp     loc_1800FF6BF
0x1800ff5d6  mov     rcx, r15
0x1800ff5d9  call    sqlite3_get_autocommit
0x1800ff5de  test    eax, eax
0x1800ff5e0  jnz     short loc_1800FF5E6
0x1800ff5e2  mov     ebx, edi
0x1800ff5e4  jmp     short loc_1800FF59B
0x1800ff5e6  xor     edx, edx
0x1800ff5e8  jmp     short loc_1800FF5F9
0x1800ff5ea  mov     rcx, rdi
0x1800ff5ed  call    sqlite3_stmt_busy
0x1800ff5f2  test    eax, eax
0x1800ff5f4  jnz     short loc_1800FF59B
0x1800ff5f6  mov     rdx, rdi
0x1800ff5f9  mov     rcx, r15
0x1800ff5fc  call    sqlite3_next_stmt
0x1800ff601  mov     rdi, rax
0x1800ff604  test    rax, rax
0x1800ff607  jnz     short loc_1800FF5EA
0x1800ff609  mov     ebx, 87AF0005h
0x1800ff60e  mov     r14b, 1
0x1800ff611  cmp     rsi, [rsp+140h+var_D8]
0x1800ff616  jnb     short loc_1800FF5AC
0x1800ff618  cmp     ebx, 87AF0005h
0x1800ff61e  jz      short loc_1800FF67B
0x1800ff620  cmp     ebx, 87AF0006h
0x1800ff626  jz      short loc_1800FF667
0x1800ff628  cmp     ebx, 87AF0105h
0x1800ff62e  jz      short loc_1800FF65D
0x1800ff630  cmp     ebx, 87AF0106h
0x1800ff636  jz      short loc_1800FF671
0x1800ff638  cmp     ebx, 5
0x1800ff63b  jz      short loc_1800FF67B
0x1800ff63d  cmp     ebx, 6
0x1800ff640  jz      short loc_1800FF667
0x1800ff642  cmp     ebx, 105h
0x1800ff648  jz      short loc_1800FF65D
0x1800ff64a  cmp     ebx, 106h
0x1800ff650  mov     edi, 8067000Ah
0x1800ff655  cmovnz  edi, ebx
0x1800ff658  jmp     loc_1800FF705
0x1800ff65d  mov     edi, 80670008h
0x1800ff662  jmp     loc_1800FF705
0x1800ff667  mov     edi, 80670009h
0x1800ff66c  jmp     loc_1800FF705
0x1800ff671  mov     edi, 8067000Ah
0x1800ff676  jmp     loc_1800FF705
0x1800ff67b  mov     edi, 80670007h
0x1800ff680  jmp     loc_1800FF705
0x1800ff685  cmp     ebx, 87AF030Bh
0x1800ff68b  jnz     short loc_1800FF696
0x1800ff68d  lea     rax, qword_180140518
0x1800ff694  jmp     short loc_1800FF6BF
0x1800ff696  cmp     ebx, 87AF020Bh
0x1800ff69c  jnz     short loc_1800FF6A7
0x1800ff69e  lea     rax, qword_180140500
0x1800ff6a5  jmp     short loc_1800FF6BF
0x1800ff6a7  cmp     ebx, 87AF010Bh
0x1800ff6ad  lea     rax, qword_180140508
0x1800ff6b4  lea     rcx, qword_1801404F8
0x1800ff6bb  cmovnz  rax, rcx
0x1800ff6bf  lock inc qword ptr [rax]
0x1800ff6c3  mov     eax, r12d
0x1800ff6c6  lea     rdx, aSqlite3Prepare; "sqlite3_prepare_v2"
0x1800ff6cd  mov     [rsp+140h+var_110], rsi
0x1800ff6d2  mov     r9, r15
0x1800ff6d5  mov     [rsp+140h+var_118], rax
0x1800ff6da  xor     r8d, r8d
0x1800ff6dd  mov     ecx, ebx
0x1800ff6df  mov     qword ptr [rsp+140h+var_120], r13; int
0x1800ff6e4  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x1800ff6e9  test    eax, eax
0x1800ff6eb  jns     short loc_1800FF705
0x1800ff6ed  mov     rcx, [rbp+48h]; this
0x1800ff6f1  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800ff6f8  mov     r9d, eax; char *
0x1800ff6fb  mov     edx, 10DAh; void *
0x1800ff700  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800ff705  mov     rcx, r15
0x1800ff708  call    sqlite3_errmsg
0x1800ff70d  xor     edx, edx; Val
0x1800ff70f  lea     rcx, [rbp+40h+var_80]; void *
0x1800ff713  mov     rbx, rax
0x1800ff716  lea     r8d, [rdx+40h]; Size
0x1800ff71a  call    memset_0
0x1800ff71f  test    r14b, r14b
0x1800ff722  jz      short loc_1800FF788
0x1800ff724  xor     edx, edx; Val
0x1800ff726  lea     rcx, [rsp+140h+var_D0]; void *
0x1800ff72b  lea     r8d, [rdx+48h]; Size
0x1800ff72f  call    memset_0
0x1800ff734  xor     r14d, r14d
0x1800ff737  lea     rdx, [rbp+40h+var_80]; char (*)[64]
0x1800ff73b  xor     eax, eax
0x1800ff73d  mov     [rbp+40h+var_B8], r14
0x1800ff741  mov     [rbp+40h+var_A8], r14
0x1800ff745  lea     rcx, [rsp+140h+var_D0]; this
0x1800ff74a  mov     [rbp+40h+var_98], r14
0x1800ff74e  mov     qword ptr [rbp+40h+var_90], r14
0x1800ff752  mov     byte ptr [rbp+40h+var_B8], r14b
0x1800ff756  mov     dword ptr [rbp+40h+var_B8+4], eax
0x1800ff759  mov     byte ptr [rbp+40h+var_A8], r14b
0x1800ff75d  mov     dword ptr [rbp+40h+var_A8+4], eax
0x1800ff760  mov     byte ptr [rbp+40h+var_98], r14b
0x1800ff764  mov     [rbp+40h+var_98+4], rax
0x1800ff768  mov     [rbp+40h+var_90+4], eax
0x1800ff76b  mov     [rbp+40h+var_C0], r14
0x1800ff76f  mov     [rbp+40h+var_B0], r14
0x1800ff773  mov     [rbp+40h+var_A0], r14
0x1800ff777  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x1800ff77c  lea     rcx, [rsp+140h+var_D0]; this
0x1800ff781  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x1800ff786  jmp     short loc_1800FF78B
0x1800ff788  xor     r14d, r14d
0x1800ff78b  cmp     r12d, 1
0x1800ff78f  jnz     short loc_1800FF7F7
0x1800ff791  test    rbx, rbx
0x1800ff794  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x1800ff79b  lea     rax, byte_180122168
0x1800ff7a2  mov     r8d, r12d
0x1800ff7a5  cmovnz  rcx, rbx
0x1800ff7a9  lea     rdx, asc_180125C6C; " "
0x1800ff7b0  cmp     [rbp+40h+var_80], r14b
0x1800ff7b4  cmovnz  rax, rdx
0x1800ff7b8  lock xadd cs:dword_180140410, r8d
0x1800ff7c1  mov     [rsp+140h+var_F8], r13
0x1800ff7c6  lea     rdx, aSqlite3Prepare_1; "[sqlite3_prepare] #%u Database %llu: Tr"...
0x1800ff7cd  mov     [rsp+140h+var_100], rcx
0x1800ff7d2  inc     r8d
0x1800ff7d5  lea     rcx, [rbp+40h+var_80]
0x1800ff7d9  xor     r9d, r9d
0x1800ff7dc  mov     [rsp+140h+var_108], rcx
0x1800ff7e1  mov     ecx, edi
0x1800ff7e3  mov     [rsp+140h+var_110], rax
0x1800ff7e8  mov     [rsp+140h+var_118], rsi
0x1800ff7ed  mov     [rsp+140h+var_120], r12d
0x1800ff7f2  call    sqlite3_log
0x1800ff7f7  cmp     edi, 87AF0205h
0x1800ff7fd  jz      loc_1800FF8A2
0x1800ff803  cmp     edi, 87AF0001h
0x1800ff809  jnz     short loc_1800FF815
0x1800ff80b  mov     rcx, r15; struct sqlite3 *
0x1800ff80e  call    ?FailFastIfNestingTransaction@Database@StateRepository@@CAXPEAUsqlite3@@@Z; StateRepository::Database::FailFastIfNestingTransaction(sqlite3 *)
0x1800ff813  jmp     short loc_1800FF865
0x1800ff815  cmp     edi, 87AF0005h
0x1800ff81b  jz      short loc_1800FF870
0x1800ff81d  cmp     edi, 87AF0105h
0x1800ff823  jz      short loc_1800FF870
0x1800ff825  cmp     edi, 87AF0006h
0x1800ff82b  jz      short loc_1800FF870
0x1800ff82d  cmp     edi, 87AF0106h
0x1800ff833  jz      short loc_1800FF870
0x1800ff835  cmp     edi, 80670007h
0x1800ff83b  jz      short loc_1800FF870
0x1800ff83d  cmp     edi, 80670008h
0x1800ff843  jz      short loc_1800FF870
0x1800ff845  cmp     edi, 80670009h
0x1800ff84b  jz      short loc_1800FF870
0x1800ff84d  cmp     edi, 8067000Ah
0x1800ff853  jz      short loc_1800FF870
0x1800ff855  cmp     edi, 8067000Ch
0x1800ff85b  jz      short loc_1800FF870
0x1800ff85d  cmp     edi, 8067000Dh
0x1800ff863  jz      short loc_1800FF870
0x1800ff865  lea     eax, [rdi+7F98FFF2h]
0x1800ff86b  cmp     eax, 1
0x1800ff86e  ja      short loc_1800FF8B0
0x1800ff870  test    cs:dword_18013F948, 1000h
0x1800ff87a  jz      short loc_1800FF882
0x1800ff87c  call    cs:__imp_DebugBreak
0x1800ff882  mov     r14, [rsp+140h+UnbiasedTime]
0x1800ff887  cmp     rsi, [rsp+140h+var_D8]
0x1800ff88c  jnb     short loc_1800FF8B5
0x1800ff88e  mov     rbx, [rsp+140h+var_F0]
0x1800ff893  mov     rdi, 346DC5D63886594Bh
0x1800ff89d  jmp     loc_1800FF515
0x1800ff8a2  xor     r8d, r8d; char *
0x1800ff8a5  mov     rdx, r13; struct sqlite3 *
0x1800ff8a8  mov     rcx, r15; this
0x1800ff8ab  call    ?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z; StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)
0x1800ff8b0  mov     r14, [rsp+140h+UnbiasedTime]
0x1800ff8b5  test    cs:dword_18013F948, 80000h
0x1800ff8bf  jz      loc_1800FFAAD
0x1800ff8c5  test    edi, edi
0x1800ff8c7  js      loc_1800FFA51
0x1800ff8cd  mov     rcx, [rsp+140h+var_F0]
0x1800ff8d2  mov     rcx, [rcx]
0x1800ff8d5  call    sqlite3_stmt_busy
0x1800ff8da  test    eax, eax
0x1800ff8dc  mov     [rsp+140h+var_F0], 0
0x1800ff8e5  lea     rcx, aOk; "OK"
0x1800ff8ec  lea     rbx, aBusy; "BUSY"
0x1800ff8f3  cmovz   rbx, rcx
0x1800ff8f7  lea     rcx, [rsp+140h+var_F0]; UnbiasedTime
0x1800ff8fc  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800ff902  mov     r8d, 1
0x1800ff908  lock xadd cs:dword_180140410, r8d
0x1800ff911  mov     [rsp+140h+var_108], r13
0x1800ff916  mov     rax, 346DC5D63886594Bh
0x1800ff920  mul     [rsp+140h+var_F0]
0x1800ff925  inc     r8d
  ... truncated ...
```
