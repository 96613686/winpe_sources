# StateRepository::StatementCache::Add(StateRepository::Statement &)

- ea: `0x180014cc0`
- end: `0x180014eae`
- name: `?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z`
- size: `494`
- prototype: `int(StateRepository::StatementCache *__hidden this, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800182f8`

## callees

- `0x180007f4c`
- `0x18000a3c0`
- `0x18000b9f8`
- `0x180014cc0`
- `0x180014f24`
- `0x1800151cc`
- `0x180015204`
- `0x18001b97c`
- `0x18001bfdc`
- `0x18001c150`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x180014df4`
- `StateRepository.Core!sqlite3_db_handle` at `0x180014df4`
- `StateRepository.Core!sqlite3_log` at `0x180014e69`
- `StateRepository.Core!sqlite3_log` at `0x180014e69`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180014e04`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x180014e04`
- `StateRepository.Core!sqlite3_clear_bindings` at `0x180014d3b`
- `StateRepository.Core!sqlite3_clear_bindings` at `0x180014d3b`

## string_xrefs

- `0x180014d65`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x180014e91`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x180014e5a`: `[StatementCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x180014d51`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`

## pseudocode

```c
int __fastcall StateRepository::StatementCache::Add(
        StateRepository::StatementCache *this,
        struct StateRepository::Statement *a2)
{
  __int64 v4; // rdi
  const char *Sql; // rbp
  int v6; // edi
  __int64 v7; // rdx
  StateRepository::Time **v9; // rax
  StateRepository::Statement *v10; // rdi
  StateRepository::Time *v11; // rcx
  unsigned int v12; // edx
  int v13; // esi
  __int64 v14; // rax
  __int64 clientdata; // rbp
  const char *v16; // rax
  StateRepository::StatementCacheEntry *v17; // rcx
  int v18; // [rsp+20h] [rbp-48h]
  int v19; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( !*(_QWORD *)a2 )
    return 0;
  v4 = 0;
  Sql = StateRepository::Statement::GetSql(a2);
  if ( *((_QWORD *)this + 2) )
  {
    while ( !(unsigned __int8)Common::ContainerOperations<char,StateRepository::StatementCacheEntry>::IsEqual(
                                Sql,
                                *(_QWORD *)(*(_QWORD *)this + 8 * v4)) )
    {
      if ( (unsigned __int64)++v4 >= *((_QWORD *)this + 2) )
        goto LABEL_5;
    }
    if ( v4 != 0x40000000 )
      return StateRepository::Statement::Finalize(a2);
  }
LABEL_5:
  v6 = StateRepository::Statement::dal_reset(*(struct sqlite3_stmt **)a2);
  if ( v6 < 0 )
  {
    v7 = 55;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)(unsigned int)v6,
      v18);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementcache.cpp",
      (const char *)(unsigned int)v6,
      v19);
    return v6;
  }
  if ( *(_QWORD *)a2 )
  {
    v6 = sqlite3_clear_bindings();
    if ( v6 < 0 )
    {
      v7 = 56;
      goto LABEL_12;
    }
  }
  v9 = (StateRepository::Time **)operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  v10 = (StateRepository::Statement *)v9;
  if ( v9 )
  {
    *v9 = 0;
    v9[1] = 0;
    v11 = *(StateRepository::Time **)a2;
    *(_QWORD *)a2 = 0;
    *v9 = v11;
    v9[1] = (StateRepository::Time *)StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v11);
    v13 = Common::Array<StateRepository::StatementCacheEntry,Common::ContainerOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>,char,Common::ContainerOperations<char,StateRepository::StatementCacheEntry>,Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>>::EnsureCapacity(
            this,
            *((_QWORD *)this + 2) + 1LL);
    if ( v13 >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)this + 8LL * (*((_QWORD *)this + 2))++) = v10;
      v13 = 0;
    }
    if ( (dword_18004B904 & 8) != 0 )
    {
      v14 = sqlite3_db_handle(*(_QWORD *)v10);
      clientdata = sqlite3_get_clientdata(v14, "connection.id");
      if ( StateRepository::Statement::GetSql(v10) )
        v16 = StateRepository::Statement::GetSql(v10);
      else
        v16 = "<null>";
      sqlite3_log(
        (unsigned int)v13,
        "[StatementCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        clientdata,
        *((_DWORD *)this + 4),
        *((_QWORD *)this + 4),
        *((_QWORD *)this + 5),
        v16);
    }
    v17 = 0;
    if ( v13 < 0 )
      v17 = v10;
    if ( v17 )
      StateRepository::StatementCacheEntry::`scalar deleting destructor'(v17, v12);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x20,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementcache.cpp",
    (const char *)0x8007000ELL,
    v18);
  return -2147024882;
}

```

## disassembly

```asm
0x180014cc0  push    rbx
0x180014cc2  push    rbp
0x180014cc3  push    rsi
0x180014cc4  push    rdi
0x180014cc5  sub     rsp, 48h
0x180014cc9  cmp     qword ptr [rdx], 0
0x180014ccd  mov     rsi, rdx
0x180014cd0  mov     rbx, rcx
0x180014cd3  jz      loc_180014E81
0x180014cd9  mov     rcx, rdx; this
0x180014cdc  call    ?GetSql@Statement@StateRepository@@QEBAPEBDXZ; StateRepository::Statement::GetSql(void)
0x180014ce1  xor     edi, edi
0x180014ce3  mov     rbp, rax
0x180014ce6  cmp     [rbx+10h], rdi
0x180014cea  jbe     short loc_180014D08
0x180014cec  mov     rdx, [rbx]
0x180014cef  mov     rcx, rbp
0x180014cf2  mov     rdx, [rdx+rdi*8]
0x180014cf6  call    ?IsEqual@?$ContainerOperations@DVStatementCacheEntry@StateRepository@@@Common@@SA_NPEBDPEBVStatementCacheEntry@StateRepository@@@Z; Common::ContainerOperations<char,StateRepository::StatementCacheEntry>::IsEqual(char const *,StateRepository::StatementCacheEntry const *)
0x180014cfb  test    al, al
0x180014cfd  jnz     short loc_180014D1D
0x180014cff  inc     rdi
0x180014d02  cmp     rdi, [rbx+10h]
0x180014d06  jb      short loc_180014CEC
0x180014d08  mov     rcx, [rsi]; struct sqlite3_stmt *
0x180014d0b  call    ?dal_reset@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_reset(sqlite3_stmt *)
0x180014d10  mov     edi, eax
0x180014d12  test    eax, eax
0x180014d14  jns     short loc_180014D33
0x180014d16  mov     edx, 37h ; '7'
0x180014d1b  jmp     short loc_180014D4C
0x180014d1d  cmp     rdi, 40000000h
0x180014d24  jz      short loc_180014D08
0x180014d26  mov     rcx, rsi; this
0x180014d29  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180014d2e  jmp     loc_180014E83
0x180014d33  mov     rcx, [rsi]
0x180014d36  test    rcx, rcx
0x180014d39  jz      short loc_180014D80
0x180014d3b  call    cs:__imp_sqlite3_clear_bindings
0x180014d41  mov     edi, eax
0x180014d43  test    eax, eax
0x180014d45  jns     short loc_180014D80
0x180014d47  mov     edx, 38h ; '8'; void *
0x180014d4c  mov     rcx, [rsp+68h]; this
0x180014d51  lea     r8, aOnecoreBaseApp_61; "onecore\\base\\appmodel\\staterepositor"...
0x180014d58  mov     r9d, edi; char *
0x180014d5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d60  mov     rcx, [rsp+68h]; this
0x180014d65  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\staterepositor"...
0x180014d6c  mov     r9d, edi; char *
0x180014d6f  mov     edx, 1Dh; void *
0x180014d74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d79  mov     eax, edi
0x180014d7b  jmp     loc_180014E83
0x180014d80  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180014d87  mov     ecx, 10h; unsigned __int64
0x180014d8c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180014d91  mov     rdi, rax
0x180014d94  test    rax, rax
0x180014d97  jz      loc_180014E8C
0x180014d9d  mov     qword ptr [rax], 0
0x180014da4  mov     qword ptr [rax+8], 0
0x180014dac  mov     rcx, [rsi]; this
0x180014daf  mov     qword ptr [rsi], 0
0x180014db6  mov     [rax], rcx
0x180014db9  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x180014dbe  mov     [rdi+8], rax
0x180014dc2  mov     rcx, rbx
0x180014dc5  mov     rdx, [rbx+10h]
0x180014dc9  inc     rdx
0x180014dcc  call    ?EnsureCapacity@?$Array@VStatementCacheEntry@StateRepository@@V?$ContainerOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@DV?$ContainerOperations@DVStatementCacheEntry@StateRepository@@@4@V?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@4@@Common@@QEAAJ_K@Z; Common::Array<StateRepository::StatementCacheEntry,Common::ContainerOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>,char,Common::ContainerOperations<char,StateRepository::StatementCacheEntry>,Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>>::EnsureCapacity(unsigned __int64)
0x180014dd1  mov     esi, eax
0x180014dd3  test    eax, eax
0x180014dd5  js      short loc_180014DE8
0x180014dd7  mov     rcx, [rbx+10h]
0x180014ddb  mov     rax, [rbx]
0x180014dde  mov     [rax+rcx*8], rdi
0x180014de2  inc     qword ptr [rbx+10h]
0x180014de6  xor     esi, esi
0x180014de8  test    byte ptr cs:dword_18004B904, 8
0x180014def  jz      short loc_180014E6F
0x180014df1  mov     rcx, [rdi]
0x180014df4  call    cs:__imp_sqlite3_db_handle
0x180014dfa  mov     rcx, rax
0x180014dfd  lea     rdx, aConnectionId; "connection.id"
0x180014e04  call    cs:__imp_sqlite3_get_clientdata
0x180014e0a  mov     rcx, rdi; this
0x180014e0d  mov     rbp, rax
0x180014e10  call    ?GetSql@Statement@StateRepository@@QEBAPEBDXZ; StateRepository::Statement::GetSql(void)
0x180014e15  test    rax, rax
0x180014e18  jnz     short loc_180014E23
0x180014e1a  lea     rax, aNull; "<null>"
0x180014e21  jmp     short loc_180014E2B
0x180014e23  mov     rcx, rdi; this
0x180014e26  call    ?GetSql@Statement@StateRepository@@QEBAPEBDXZ; StateRepository::Statement::GetSql(void)
0x180014e2b  mov     rcx, [rbx+28h]
0x180014e2f  mov     r8d, 1
0x180014e35  mov     rdx, [rbx+20h]
0x180014e39  mov     r9d, [rbx+10h]
0x180014e3d  lock xadd cs:dword_18004BFF0, r8d
0x180014e46  mov     [rsp+68h+var_30], rax
0x180014e4b  inc     r8d
0x180014e4e  mov     [rsp+68h+var_38], rcx
0x180014e53  mov     ecx, esi
0x180014e55  mov     [rsp+68h+var_40], rdx
0x180014e5a  lea     rdx, aStatementcache; "[StatementCache.Add] #%u Database %llu:"...
0x180014e61  mov     [rsp+68h+var_48], r9d
0x180014e66  mov     r9, rbp
0x180014e69  call    cs:__imp_sqlite3_log
0x180014e6f  xor     ecx, ecx
0x180014e71  test    esi, esi
0x180014e73  cmovs   rcx, rdi; this
0x180014e77  test    rcx, rcx
0x180014e7a  jz      short loc_180014E81
0x180014e7c  call    ??_GStatementCacheEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::StatementCacheEntry::`scalar deleting destructor'(uint)
0x180014e81  xor     eax, eax
0x180014e83  add     rsp, 48h
0x180014e87  pop     rdi
0x180014e88  pop     rsi
0x180014e89  pop     rbp
0x180014e8a  pop     rbx
0x180014e8b  retn
0x180014e8c  mov     rcx, [rsp+68h]; this
0x180014e91  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\staterepositor"...
0x180014e98  mov     ebx, 8007000Eh
0x180014e9d  mov     edx, 20h ; ' '; void *
0x180014ea2  mov     r9d, ebx; char *
0x180014ea5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014eaa  mov     eax, ebx
0x180014eac  jmp     short loc_180014E83
```
