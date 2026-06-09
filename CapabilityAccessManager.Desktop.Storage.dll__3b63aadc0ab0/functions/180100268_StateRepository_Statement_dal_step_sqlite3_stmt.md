# StateRepository::Statement::dal_step(sqlite3_stmt *)

- ea: `0x180100268`
- end: `0x180100902`
- name: `?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z`
- size: `1690`
- prototype: `__int64 __fastcall(struct sqlite3_stmt *)`
- caller_count: `2`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800ffc78`
- `0x1800ffcc4`

## callees

- `0x180003060`
- `0x180003a40`
- `0x180006a00`
- `0x180007040`
- `0x180007280`
- `0x180008870`
- `0x18000ecf0`
- `0x18000ed00`
- `0x18000f220`
- `0x180016970`
- `0x1800edb2c`
- `0x1800f7630`
- `0x1800f85a8`
- `0x180100268`
- `0x180102b2c`
- `0x180103cd8`
- `0x180106704`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180100342`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180100342`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180100856`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x180100856`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18010030d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180100425`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18010030d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180100425`

## string_xrefs

- `0x180100573`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1801008f0`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Statement::dal_step(struct sqlite3_stmt *a1)
{
  const char *v1; // rbx
  __int64 v2; // rsi
  const char *v3; // r15
  __int64 v5; // rdx
  __int64 v6; // r8
  int v7; // eax
  const char *v8; // rcx
  unsigned int v9; // r12d
  unsigned __int64 v10; // r13
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // r8
  unsigned int v14; // edi
  StateRepository::Logging *v15; // rbx
  struct sqlite3 *v16; // rax
  struct sqlite3_stmt *v17; // r9
  __int64 i; // rdx
  __int64 stmt; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rbx
  __int64 v23; // r8
  __int64 v24; // rdx
  unsigned int v25; // eax
  char v26; // r15
  unsigned int v27; // ebx
  volatile signed __int64 *v28; // rax
  int v29; // eax
  const char *v30; // rdi
  __int64 v31; // rax
  const char *v32; // rdx
  const char *v33; // rcx
  const char *v34; // rax
  const char *v35; // r12
  __int64 v36; // r15
  __int64 v37; // rax
  const char *v38; // rdx
  const char *v39; // rcx
  const char *v40; // rax
  int v41; // ecx
  int v43; // [rsp+20h] [rbp-E0h]
  unsigned __int64 UnbiasedTime; // [rsp+60h] [rbp-A0h] BYREF
  int v45[2]; // [rsp+68h] [rbp-98h]
  unsigned __int64 v46; // [rsp+70h] [rbp-90h]
  unsigned __int64 v47; // [rsp+78h] [rbp-88h]
  _BYTE v48[16]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v49; // [rsp+90h] [rbp-70h]
  __int64 v50; // [rsp+98h] [rbp-68h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  __int64 v53; // [rsp+B0h] [rbp-50h]
  int v54; // [rsp+B8h] [rbp-48h]
  __int64 v55; // [rsp+BCh] [rbp-44h]
  int v56; // [rsp+C4h] [rbp-3Ch]
  char v57[64]; // [rsp+D0h] [rbp-30h] BYREF
  char v58[64]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v1 = 0;
  v2 = 0;
  *(_QWORD *)v45 = 0;
  v3 = "BUSY";
  if ( (dword_18013F948 & 0x40000) != 0 )
  {
    v2 = sqlite3_db_handle(a1);
    v7 = sqlite3_stmt_busy(a1, v5, v6);
    v8 = "BUSY";
    if ( !v7 )
      v8 = "OK";
    sqlite3_log(0, "[pre-sqlite3_step] #%u Database %llu: Statement %s", _InterlockedIncrement(&dword_180140410), 0, v8);
  }
  v46 = qword_18013F940;
  v9 = 0;
  UnbiasedTime = 0;
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  v47 = UnbiasedTime / 0x2710;
  v10 = 0;
  while ( 1 )
  {
    LODWORD(UnbiasedTime) = ++v9;
    if ( v9 > 1 )
      Sleep(dwMilliseconds);
    v11 = sqlite3_step(a1);
    v14 = v11;
    if ( v11 > 0 )
      v14 = (unsigned __int16)v11 | 0x87AF0000;
    if ( v14 != -2018574236 && v14 != -2018574235 )
    {
      if ( (v14 & 0x80000000) == 0 )
        wil::details::in1diag3::_FailFast_Hr(
          retaddr,
          (void *)0x41E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)0x8000FFFFLL,
          v43);
      if ( v14 == -2018573819 )
      {
        if ( (unsigned int)sqlite3_get_autocommit(v2) )
        {
          for ( i = 0; ; i = v22 )
          {
            stmt = sqlite3_next_stmt(v2, i);
            v22 = stmt;
            if ( !stmt )
              break;
            if ( (unsigned int)sqlite3_stmt_busy(stmt, v20, v21) )
              goto LABEL_16;
          }
          v14 = -2018574331;
        }
        else
        {
          v14 = -2018573819;
LABEL_16:
          v15 = (StateRepository::Logging *)sqlite3_db_handle(a1);
          v16 = (struct sqlite3 *)sqlite3_sql(a1);
          StateRepository::Logging::FailFastBusySnapshot(v15, v16, (const char *)a1, v17);
        }
        v1 = *(const char **)v45;
      }
      if ( !v2 )
        v2 = sqlite3_db_handle(a1);
      if ( !v1 )
        *(_QWORD *)v45 = sqlite3_sql(a1);
      UnbiasedTime = 0;
      QueryUnbiasedInterruptTime(&UnbiasedTime);
      v24 = (UnbiasedTime * (unsigned __int128)0x346DC5D63886594BuLL) >> 64;
      v25 = v14 & 0xFFFF00FF;
      v10 = UnbiasedTime / 0x2710 - v47;
      if ( ((v14 + 2018574331) & 0xFFFFFEFF) == 0 || v25 == -2018574330 )
      {
        v26 = 1;
        if ( v10 < v46 )
        {
          switch ( v14 )
          {
            case 0x87AF0005:
              v27 = -2140733433;
              break;
            case 0x87AF0006:
              v27 = -2140733431;
              break;
            case 0x87AF0105:
              v27 = -2140733432;
              break;
            case 0x87AF0106:
              v27 = -2140733430;
              break;
            default:
              v27 = v14;
              break;
          }
LABEL_51:
          v30 = "BUSY";
          if ( !(unsigned int)sqlite3_stmt_busy(a1, v24, v23) )
            v30 = "OK";
          memset_0(v57, 0, sizeof(v57));
          if ( v26 )
          {
            memset_0(v48, 0, 0x48u);
            v50 = 0;
            v52 = 0;
            v54 = 0;
            v55 = 0;
            v56 = 0;
            v49 = 0;
            v51 = 0;
            v53 = 0;
            StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
              (StateRepository::ResourcePriority::AutoPriority *)v48,
              (char (*)[64])v57);
            StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v48);
          }
          if ( v2 )
            v31 = sqlite3_errmsg(v2);
          else
            v31 = 0;
          if ( v9 == 1 )
          {
            v32 = "<null>";
            if ( *(_QWORD *)v45 )
              v32 = *(const char **)v45;
            v33 = "<no-error-message>";
            if ( v31 )
              v33 = (const char *)v31;
            v34 = byte_180122168;
            if ( v57[0] )
              v34 = " ";
            sqlite3_log(
              v27,
              "[sqlite3_step] #%u Database %llu: Statement %s: Try %u (%llums)%s%s %s : SQL %s",
              _InterlockedIncrement(&dword_180140410),
              0,
              v30,
              1,
              v10,
              v34,
              v57,
              v33,
              v32);
          }
          goto LABEL_83;
        }
      }
      else
      {
        v26 = 0;
      }
      v27 = v14;
      if ( v25 == -2018574325 )
      {
        switch ( v14 )
        {
          case 0x87AF000B:
            v28 = &qword_180140510;
            break;
          case 0x87AF030B:
            v28 = &qword_180140518;
            break;
          case 0x87AF020B:
            v28 = &qword_180140500;
            break;
          default:
            v28 = &qword_180140508;
            if ( v14 != -2018574069 )
              v28 = &qword_1801404F8;
            break;
        }
        _InterlockedIncrement64(v28);
        v43 = v45[0];
        v29 = StateRepository::Logging::ReportDatabaseCorruption(v14, "sqlite3_step", 0, v2);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x43F,
            (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v29);
      }
      goto LABEL_51;
    }
    v27 = v14;
    if ( v9 <= 1 )
      goto LABEL_84;
    if ( !v2 )
      v2 = sqlite3_db_handle(a1);
    v35 = "BUSY";
    v36 = 0;
    if ( !(unsigned int)sqlite3_stmt_busy(a1, v12, v13) )
      v35 = "OK";
    memset_0(v58, 0, sizeof(v58));
    if ( ((v14 + 2018574331) & 0xFFFFFEFF) == 0 || (v14 & 0xFFFF00FF) == 0x87AF0006 )
    {
      memset_0(v48, 0, 0x48u);
      v50 = 0;
      v52 = 0;
      v54 = 0;
      v55 = 0;
      v56 = 0;
      v49 = 0;
      v51 = 0;
      v53 = 0;
      StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(
        (StateRepository::ResourcePriority::AutoPriority *)v48,
        (char (*)[64])v58);
      StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)v48);
    }
    if ( v2 )
      v36 = sqlite3_errmsg(v2);
    v37 = sqlite3_sql(a1);
    *(_QWORD *)v45 = v37;
    v38 = "<null>";
    if ( v37 )
      v38 = (const char *)v37;
    v39 = "<no-error-message>";
    v40 = byte_180122168;
    if ( v36 )
      v39 = (const char *)v36;
    if ( v58[0] )
      v40 = " ";
    sqlite3_log(
      v14,
      "[sqlite3_step_final] #%u Database %llu: Statement %s: Try %u (%llums)%s%s %s : SQL %s",
      _InterlockedIncrement(&dword_180140410),
      0,
      v35,
      UnbiasedTime,
      v10,
      v40,
      v58,
      v39,
      v38);
    v9 = UnbiasedTime;
LABEL_83:
    v3 = "BUSY";
LABEL_84:
    if ( v27 + 2018574331 > 1 && v27 + 2018574075 > 1 )
    {
      if ( v27 + 2140733433 > 8 )
        break;
      v41 = 495;
      if ( !_bittest(&v41, v27 + 2140733433) )
        break;
    }
    if ( (dword_18013F948 & 0x1000) != 0 )
      DebugBreak();
    if ( v10 >= v46 )
      break;
    v1 = *(const char **)v45;
  }
  if ( (dword_18013F948 & 0x80000) != 0 )
  {
    if ( !v2 )
      sqlite3_db_handle(a1);
    if ( !(unsigned int)sqlite3_stmt_busy(a1, v12, v13) )
      v3 = "OK";
    sqlite3_log(
      v27,
      "[post-sqlite3_step] #%u Database %llu: Statement %s: Tries %u",
      _InterlockedIncrement(&dword_180140410),
      0,
      v3,
      v9);
  }
  return v27;
}

```

## disassembly

```asm
0x180100268  push    rbp
0x18010026a  push    rbx
0x18010026b  push    rsi
0x18010026c  push    rdi
0x18010026d  push    r12
0x18010026f  push    r13
0x180100271  push    r14
0x180100273  push    r15
0x180100275  lea     rbp, [rsp-68h]
0x18010027a  sub     rsp, 168h
0x180100281  mov     rax, cs:__security_cookie
0x180100288  xor     rax, rsp
0x18010028b  mov     [rbp+0A0h+var_50], rax
0x18010028f  xor     ebx, ebx
0x180100291  lea     rdi, aOk; "OK"
0x180100298  xor     esi, esi
0x18010029a  mov     qword ptr [rsp+1A0h+var_138], rbx
0x18010029f  test    cs:dword_18013F948, 40000h
0x1801002a9  lea     r15, aBusy; "BUSY"
0x1801002b0  mov     r14, rcx
0x1801002b3  jz      short loc_1801002F4
0x1801002b5  call    sqlite3_db_handle
0x1801002ba  mov     rcx, r14
0x1801002bd  mov     rsi, rax
0x1801002c0  call    sqlite3_stmt_busy
0x1801002c5  test    eax, eax
0x1801002c7  lea     r8d, [rbx+1]
0x1801002cb  mov     rcx, r15
0x1801002ce  cmovz   rcx, rdi
0x1801002d2  lock xadd cs:dword_180140410, r8d
0x1801002db  mov     qword ptr [rsp+1A0h+var_180], rcx; int
0x1801002e0  lea     rdx, aPreSqlite3Step; "[pre-sqlite3_step] #%u Database %llu: S"...
0x1801002e7  xor     ecx, ecx
0x1801002e9  inc     r8d
0x1801002ec  xor     r9d, r9d
0x1801002ef  call    sqlite3_log
0x1801002f4  mov     rax, cs:qword_18013F940
0x1801002fb  lea     rcx, [rsp+1A0h+UnbiasedTime]; UnbiasedTime
0x180100300  mov     [rsp+1A0h+var_130], rax
0x180100305  xor     r12d, r12d
0x180100308  mov     [rsp+1A0h+UnbiasedTime], rbx
0x18010030d  call    cs:__imp_QueryUnbiasedInterruptTime
0x180100313  mov     rax, 346DC5D63886594Bh
0x18010031d  mul     [rsp+1A0h+UnbiasedTime]
0x180100322  shr     rdx, 0Bh
0x180100326  mov     [rsp+1A0h+var_128], rdx
0x18010032b  xor     r13d, r13d
0x18010032e  inc     r12d
0x180100331  mov     dword ptr [rsp+1A0h+UnbiasedTime], r12d
0x180100336  cmp     r12d, 1
0x18010033a  jbe     short loc_180100348
0x18010033c  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x180100342  call    cs:__imp_Sleep
0x180100348  mov     rcx, r14
0x18010034b  call    sqlite3_step
0x180100350  mov     edi, eax
0x180100352  test    eax, eax
0x180100354  jle     short loc_18010035F
0x180100356  movzx   edi, ax
0x180100359  or      edi, 87AF0000h
0x18010035f  cmp     edi, 87AF0064h
0x180100365  jz      loc_1801006BA
0x18010036b  cmp     edi, 87AF0065h
0x180100371  jz      loc_1801006BA
0x180100377  mov     rcx, [rbp+0A8h]; this
0x18010037e  mov     eax, edi
0x180100380  shr     eax, 1Fh
0x180100383  xor     al, 1
0x180100385  jnz     loc_1801008EA
0x18010038b  mov     r15d, 87AF0205h
0x180100391  cmp     edi, r15d
0x180100394  jnz     short loc_1801003F5
0x180100396  mov     rcx, rsi
0x180100399  call    sqlite3_get_autocommit
0x18010039e  test    eax, eax
0x1801003a0  jnz     short loc_1801003C8
0x1801003a2  mov     edi, r15d
0x1801003a5  mov     rcx, r14
0x1801003a8  call    sqlite3_db_handle
0x1801003ad  mov     rcx, r14
0x1801003b0  mov     rbx, rax
0x1801003b3  call    sqlite3_sql
0x1801003b8  mov     r8, r14; char *
0x1801003bb  mov     rdx, rax; struct sqlite3 *
0x1801003be  mov     rcx, rbx; this
0x1801003c1  call    ?FailFastBusySnapshot@Logging@StateRepository@@YAXPEAUsqlite3@@PEBDPEAUsqlite3_stmt@@@Z; StateRepository::Logging::FailFastBusySnapshot(sqlite3 *,char const *,sqlite3_stmt *)
0x1801003c6  jmp     short loc_1801003F0
0x1801003c8  xor     edx, edx
0x1801003ca  jmp     short loc_1801003DB
0x1801003cc  mov     rcx, rbx
0x1801003cf  call    sqlite3_stmt_busy
0x1801003d4  test    eax, eax
0x1801003d6  jnz     short loc_1801003A5
0x1801003d8  mov     rdx, rbx
0x1801003db  mov     rcx, rsi
0x1801003de  call    sqlite3_next_stmt
0x1801003e3  mov     rbx, rax
0x1801003e6  test    rax, rax
0x1801003e9  jnz     short loc_1801003CC
0x1801003eb  mov     edi, 87AF0005h
0x1801003f0  mov     rbx, qword ptr [rsp+1A0h+var_138]
0x1801003f5  test    rsi, rsi
0x1801003f8  jnz     short loc_180100405
0x1801003fa  mov     rcx, r14
0x1801003fd  call    sqlite3_db_handle
0x180100402  mov     rsi, rax
0x180100405  test    rbx, rbx
0x180100408  jnz     short loc_180100417
0x18010040a  mov     rcx, r14
0x18010040d  call    sqlite3_sql
0x180100412  mov     qword ptr [rsp+1A0h+var_138], rax
0x180100417  lea     rcx, [rsp+1A0h+UnbiasedTime]; UnbiasedTime
0x18010041c  mov     [rsp+1A0h+UnbiasedTime], 0
0x180100425  call    cs:__imp_QueryUnbiasedInterruptTime
0x18010042b  mov     rax, 346DC5D63886594Bh
0x180100435  lea     ecx, [rdi+7850FFFBh]
0x18010043b  mul     [rsp+1A0h+UnbiasedTime]
0x180100440  mov     eax, edi
0x180100442  mov     r13, rdx
0x180100445  and     eax, 0FFFF00FFh
0x18010044a  shr     r13, 0Bh
0x18010044e  sub     r13, [rsp+1A0h+var_128]
0x180100453  test    ecx, 0FFFFFEFFh
0x180100459  jz      short loc_180100488
0x18010045b  cmp     eax, 87AF0006h
0x180100460  jz      short loc_180100488
0x180100462  xor     r15b, r15b
0x180100465  mov     ecx, 87AF000Bh
0x18010046a  mov     ebx, edi
0x18010046c  cmp     eax, ecx
0x18010046e  jnz     loc_180100587
0x180100474  cmp     edi, ecx
0x180100476  jnz     loc_1801004FF
0x18010047c  lea     rax, qword_180140510
0x180100483  jmp     loc_180100539
0x180100488  mov     r15b, 1
0x18010048b  cmp     r13, [rsp+1A0h+var_130]
0x180100490  jnb     short loc_180100465
0x180100492  cmp     edi, 87AF0005h
0x180100498  jz      short loc_1801004F5
0x18010049a  cmp     edi, 87AF0006h
0x1801004a0  jz      short loc_1801004E1
0x1801004a2  cmp     edi, 87AF0105h
0x1801004a8  jz      short loc_1801004D7
0x1801004aa  cmp     edi, 87AF0106h
0x1801004b0  jz      short loc_1801004EB
0x1801004b2  cmp     edi, 5
0x1801004b5  jz      short loc_1801004F5
0x1801004b7  cmp     edi, 6
0x1801004ba  jz      short loc_1801004E1
0x1801004bc  cmp     edi, 105h
0x1801004c2  jz      short loc_1801004D7
0x1801004c4  cmp     edi, 106h
0x1801004ca  mov     ebx, 8067000Ah
0x1801004cf  cmovnz  ebx, edi
0x1801004d2  jmp     loc_180100587
0x1801004d7  mov     ebx, 80670008h
0x1801004dc  jmp     loc_180100587
0x1801004e1  mov     ebx, 80670009h
0x1801004e6  jmp     loc_180100587
0x1801004eb  mov     ebx, 8067000Ah
0x1801004f0  jmp     loc_180100587
0x1801004f5  mov     ebx, 80670007h
0x1801004fa  jmp     loc_180100587
0x1801004ff  cmp     edi, 87AF030Bh
0x180100505  jnz     short loc_180100510
0x180100507  lea     rax, qword_180140518
0x18010050e  jmp     short loc_180100539
0x180100510  cmp     edi, 87AF020Bh
0x180100516  jnz     short loc_180100521
0x180100518  lea     rax, qword_180140500
0x18010051f  jmp     short loc_180100539
0x180100521  cmp     edi, 87AF010Bh
0x180100527  lea     rax, qword_180140508
0x18010052e  lea     rcx, qword_1801404F8
0x180100535  cmovnz  rax, rcx
0x180100539  lock inc qword ptr [rax]
0x18010053d  mov     eax, r12d
0x180100540  lea     rdx, aSqlite3Step; "sqlite3_step"
0x180100547  mov     [rsp+1A0h+var_170], r13
0x18010054c  mov     r9, rsi
0x18010054f  mov     [rsp+1A0h+var_178], rax
0x180100554  xor     r8d, r8d
0x180100557  mov     rax, qword ptr [rsp+1A0h+var_138]
0x18010055c  mov     ecx, edi
0x18010055e  mov     qword ptr [rsp+1A0h+var_180], rax; int
0x180100563  call    ?ReportDatabaseCorruption@Logging@StateRepository@@YAJJPEBDW4Partition@2@PEAUsqlite3@@0_K3@Z; StateRepository::Logging::ReportDatabaseCorruption(long,char const *,StateRepository::Partition,sqlite3 *,char const *,unsigned __int64,unsigned __int64)
0x180100568  test    eax, eax
0x18010056a  jns     short loc_180100587
0x18010056c  mov     rcx, [rbp+0A8h]; this
0x180100573  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\staterepositor"...
0x18010057a  mov     r9d, eax; char *
0x18010057d  mov     edx, 43Fh; void *
0x180100582  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180100587  mov     rcx, r14
0x18010058a  call    sqlite3_stmt_busy
0x18010058f  test    eax, eax
0x180100591  lea     rdi, aBusy; "BUSY"
0x180100598  lea     rax, aOk; "OK"
0x18010059f  cmovz   rdi, rax
0x1801005a3  lea     rcx, [rbp+0A0h+var_D0]; void *
0x1801005a7  xor     edx, edx; Val
0x1801005a9  lea     r8d, [rdx+40h]; Size
0x1801005ad  call    memset_0
0x1801005b2  test    r15b, r15b
0x1801005b5  jz      short loc_180100618
0x1801005b7  xor     edx, edx; Val
0x1801005b9  lea     rcx, [rbp+0A0h+var_120]; void *
0x1801005bd  lea     r8d, [rdx+48h]; Size
0x1801005c1  call    memset_0
0x1801005c6  xor     r15d, r15d
0x1801005c9  lea     rdx, [rbp+0A0h+var_D0]; char (*)[64]
0x1801005cd  xor     eax, eax
0x1801005cf  mov     [rbp+0A0h+var_108], r15
0x1801005d3  mov     [rbp+0A0h+var_F8], r15
0x1801005d7  lea     rcx, [rbp+0A0h+var_120]; this
0x1801005db  mov     [rbp+0A0h+var_E8], r15
0x1801005df  mov     qword ptr [rbp+0A0h+var_E0], r15
0x1801005e3  mov     byte ptr [rbp+0A0h+var_108], r15b
0x1801005e7  mov     dword ptr [rbp+0A0h+var_108+4], eax
0x1801005ea  mov     byte ptr [rbp+0A0h+var_F8], r15b
0x1801005ee  mov     dword ptr [rbp+0A0h+var_F8+4], eax
0x1801005f1  mov     byte ptr [rbp+0A0h+var_E8], r15b
0x1801005f5  mov     [rbp+0A0h+var_E8+4], rax
0x1801005f9  mov     [rbp+0A0h+var_E0+4], eax
0x1801005fc  mov     [rbp+0A0h+var_110], r15
0x180100600  mov     [rbp+0A0h+var_100], r15
0x180100604  mov     [rbp+0A0h+var_F0], r15
0x180100608  call    ?GetCurrentFormattedForLogging@AutoPriority@ResourcePriority@StateRepository@@QEAAXAEAY0EA@D@Z; StateRepository::ResourcePriority::AutoPriority::GetCurrentFormattedForLogging(char (&)[64])
0x18010060d  lea     rcx, [rbp+0A0h+var_120]; this
0x180100611  call    ??1AutoPriority@ResourcePriority@StateRepository@@QEAA@XZ; StateRepository::ResourcePriority::AutoPriority::~AutoPriority(void)
0x180100616  jmp     short loc_18010061B
0x180100618  xor     r15d, r15d
0x18010061b  test    rsi, rsi
0x18010061e  jnz     short loc_180100625
0x180100620  mov     rax, r15
0x180100623  jmp     short loc_18010062D
0x180100625  mov     rcx, rsi
0x180100628  call    sqlite3_errmsg
0x18010062d  cmp     r12d, 1
0x180100631  jnz     loc_180100818
0x180100637  mov     rcx, qword ptr [rsp+1A0h+var_138]
0x18010063c  lea     r8, asc_180125C6C; " "
0x180100643  test    rcx, rcx
0x180100646  lea     rdx, aNull_1; "<null>"
0x18010064d  cmovnz  rdx, rcx
0x180100651  test    rax, rax
0x180100654  lea     rcx, aNoErrorMessage; "<no-error-message>"
0x18010065b  cmovnz  rcx, rax
0x18010065f  cmp     [rbp+0A0h+var_D0], r15b
0x180100663  lea     rax, byte_180122168
0x18010066a  cmovnz  rax, r8
0x18010066e  mov     r8d, r12d
0x180100671  lock xadd cs:dword_180140410, r8d
0x18010067a  mov     [rsp+1A0h+var_150], rdx
0x18010067f  inc     r8d
0x180100682  mov     [rsp+1A0h+var_158], rcx
0x180100687  lea     rdx, aSqlite3StepUDa; "[sqlite3_step] #%u Database %llu: State"...
0x18010068e  lea     rcx, [rbp+0A0h+var_D0]
0x180100692  xor     r9d, r9d
0x180100695  mov     [rsp+1A0h+var_160], rcx
0x18010069a  mov     ecx, ebx
0x18010069c  mov     [rsp+1A0h+var_168], rax
0x1801006a1  mov     [rsp+1A0h+var_170], r13
0x1801006a6  mov     dword ptr [rsp+1A0h+var_178], r12d
0x1801006ab  mov     qword ptr [rsp+1A0h+var_180], rdi
0x1801006b0  call    sqlite3_log
0x1801006b5  jmp     loc_180100818
0x1801006ba  mov     ebx, edi
0x1801006bc  cmp     r12d, 1
0x1801006c0  jbe     loc_18010081F
0x1801006c6  test    rsi, rsi
0x1801006c9  jnz     short loc_1801006D6
0x1801006cb  mov     rcx, r14
0x1801006ce  call    sqlite3_db_handle
0x1801006d3  mov     rsi, rax
0x1801006d6  mov     rcx, r14
0x1801006d9  call    sqlite3_stmt_busy
0x1801006de  mov     r12, r15
0x1801006e1  lea     rcx, [rbp+0A0h+var_90]; void *
0x1801006e5  xor     r15d, r15d
0x1801006e8  test    eax, eax
0x1801006ea  lea     rax, aOk; "OK"
0x1801006f1  cmovz   r12, rax
0x1801006f5  xor     edx, edx; Val
0x1801006f7  lea     r8d, [r15+40h]; Size
0x1801006fb  call    memset_0
0x180100700  lea     eax, [rdi+7850FFFBh]
0x180100706  test    eax, 0FFFFFEFFh
0x18010070b  jz      short loc_18010071B
0x18010070d  mov     eax, edi
0x18010070f  and     eax, 0FFFF00FFh
0x180100714  cmp     eax, 87AF0006h
0x180100719  jnz     short loc_180100777
0x18010071b  xor     edx, edx; Val
0x18010071d  lea     rcx, [rbp+0A0h+var_120]; void *
0x180100721  lea     r8d, [rdx+48h]; Size
0x180100725  call    memset_0
0x18010072a  xor     eax, eax
0x18010072c  mov     [rbp+0A0h+var_108], r15
  ... truncated ...
```
