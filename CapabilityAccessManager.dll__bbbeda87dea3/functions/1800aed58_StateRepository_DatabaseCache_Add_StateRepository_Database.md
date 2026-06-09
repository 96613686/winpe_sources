# StateRepository::DatabaseCache::Add(StateRepository::Database &)

- ea: `0x1800aed58`
- end: `0x1800aef69`
- name: `?Add@DatabaseCache@StateRepository@@QEAAJAEAVDatabase@2@@Z`
- size: `529`
- prototype: `int(StateRepository::DatabaseCache *__hidden this, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800a0bb8`

## callees

- `0x180006854`
- `0x180009528`
- `0x18001ab9c`
- `0x180021074`
- `0x1800210d4`
- `0x18002e79c`
- `0x1800a2d60`
- `0x1800a46cc`
- `0x1800a48d0`
- `0x1800a5b7c`
- `0x1800a9844`
- `0x1800ad850`
- `0x1800aed58`
- `0x1800af52c`
- `0x1800af620`

## import_xrefs

- `winsqlite3!sqlite3_log` at `0x1800aeec0`
- `winsqlite3!sqlite3_log` at `0x1800aeec0`

## string_xrefs

- `0x1800aeeb9`: `[DatabaseCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu`
- `0x1800aedb0`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800aedde`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800aef2f`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800aef51`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x1800aee3a`: `onecore\base\appmodel\StateRepository\DataAccessLayer\DatabaseCache.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DatabaseCache::Add(
        StateRepository::DatabaseCache *this,
        struct StateRepository::Database *a2)
{
  StateRepository::DatabaseCache *v3; // rdi
  StateRepository::DatabaseCache *v4; // rcx
  int IsBusy; // eax
  int v6; // eax
  __int64 v7; // r14
  StateRepository::Database *v8; // rax
  struct StateRepository::Database *v9; // rsi
  int v10; // eax
  StateRepository::Time *v11; // rcx
  unsigned int v12; // edx
  int v13; // ebp
  int v14; // r8d
  int v15; // r9d
  _DWORD *v16; // rcx
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 v20; // [rsp+60h] [rbp+8h] BYREF
  __int64 v21; // [rsp+68h] [rbp+10h] BYREF

  v20 = (__int64)this;
  if ( !*(_QWORD *)a2 )
    return 0;
  v3 = StateRepository::DatabaseCacheSingleton::s_cache;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
      (const char *)0x80670014LL,
      v18);
  if ( (dword_180166488 & 0x8000) != 0 )
  {
    IsBusy = StateRepository::DatabaseCache::IsBusy(v4, a2);
    if ( IsBusy < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x15,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)(unsigned int)IsBusy,
        v18);
  }
  if ( (dword_180166488 & 8) != 0 )
  {
    v6 = StateRepository::Database::LogStatistics(a2);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)(unsigned int)v6,
        v18);
  }
  v7 = *((_QWORD *)a2 + 15);
  v8 = (StateRepository::Database *)operator new(0x88u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    StateRepository::Database::Database(v8);
    *((_QWORD *)v9 + 16) = 0;
    v10 = StateRepository::DatabaseCacheEntry::Move(a2, v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\DatabaseCache.hpp",
        (const char *)(unsigned int)v10,
        v18);
    *((_QWORD *)v9 + 16) = StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v11);
    v13 = Common::Array<StateRepository::StatementCacheEntry,Common::ContainerOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>,char,Common::ContainerOperations<char,StateRepository::StatementCacheEntry>,Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>>::EnsureCapacity(
            v3,
            *((_QWORD *)v3 + 2) + 1LL);
    if ( v13 >= 0 )
    {
      *(_QWORD *)(*(_QWORD *)v3 + 8LL * (*((_QWORD *)v3 + 2))++) = v9;
      v13 = 0;
    }
    if ( (dword_180166488 & 8) != 0 )
      sqlite3_log(
        (unsigned int)v13,
        "[DatabaseCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu",
        _InterlockedIncrement(&dword_180169080),
        v7,
        *((_DWORD *)v3 + 4),
        *((_QWORD *)v3 + 4),
        *((_QWORD *)v3 + 5));
    if ( v13 < 0 )
    {
      StateRepository::DatabaseCacheEntry::`scalar deleting destructor'(v9, v12);
    }
    else
    {
      v16 = (_DWORD *)*((_QWORD *)v3 + 7);
      if ( *v16 > 5u )
      {
        v20 = 0x1000000;
        v21 = v7;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
          (_DWORD)v16,
          (unsigned int)&byte_18014C997,
          v14,
          v15,
          (__int64)&v21,
          (__int64)&v20);
      }
      StateRepository::Database::Reset(a2);
    }
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
    (const char *)0x8007000ELL,
    v18);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800aed58  mov     [rsp+arg_10], rbx
0x1800aed5d  mov     [rsp+arg_18], rbp
0x1800aed62  mov     [rsp+arg_0], rcx
0x1800aed67  push    rsi
0x1800aed68  push    rdi
0x1800aed69  push    r14
0x1800aed6b  sub     rsp, 40h
0x1800aed6f  cmp     qword ptr [rdx], 0
0x1800aed73  mov     rbx, rdx
0x1800aed76  jz      loc_1800AEF0B
0x1800aed7c  mov     rdi, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x1800aed83  mov     rcx, rdx; this
0x1800aed86  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800aed8b  test    al, al
0x1800aed8d  jz      loc_1800AEF4C
0x1800aed93  test    cs:dword_180166488, 8000h
0x1800aed9d  jz      short loc_1800AEDC4
0x1800aed9f  mov     rdx, rbx; struct StateRepository::Database *
0x1800aeda2  call    ?IsBusy@DatabaseCache@StateRepository@@AEAAJAEAVDatabase@2@@Z; StateRepository::DatabaseCache::IsBusy(StateRepository::Database &)
0x1800aeda7  test    eax, eax
0x1800aeda9  jns     short loc_1800AEDC4
0x1800aedab  mov     rcx, [rsp+58h]; this
0x1800aedb0  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1800aedb7  mov     r9d, eax; char *
0x1800aedba  mov     edx, 15h; void *
0x1800aedbf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aedc4  test    byte ptr cs:dword_180166488, 8
0x1800aedcb  jz      short loc_1800AEDF2
0x1800aedcd  mov     rcx, rbx; this
0x1800aedd0  call    ?LogStatistics@Database@StateRepository@@QEAAJXZ; StateRepository::Database::LogStatistics(void)
0x1800aedd5  test    eax, eax
0x1800aedd7  jns     short loc_1800AEDF2
0x1800aedd9  mov     rcx, [rsp+58h]; this
0x1800aedde  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1800aede5  mov     r9d, eax; char *
0x1800aede8  mov     edx, 1Ch; void *
0x1800aeded  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aedf2  mov     r14, [rbx+78h]
0x1800aedf6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800aedfd  mov     ecx, 88h; unsigned __int64
0x1800aee02  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800aee07  mov     rsi, rax
0x1800aee0a  test    rax, rax
0x1800aee0d  jz      loc_1800AEF2A
0x1800aee13  mov     rcx, rax; this
0x1800aee16  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x1800aee1b  mov     rdx, rsi; struct StateRepository::Database *
0x1800aee1e  mov     qword ptr [rsi+80h], 0
0x1800aee29  mov     rcx, rbx; struct StateRepository::Database *
0x1800aee2c  call    ?Move@DatabaseCacheEntry@StateRepository@@CAJAEAVDatabase@2@0@Z; StateRepository::DatabaseCacheEntry::Move(StateRepository::Database &,StateRepository::Database &)
0x1800aee31  test    eax, eax
0x1800aee33  jns     short loc_1800AEE4E
0x1800aee35  mov     rcx, [rsp+58h]; this
0x1800aee3a  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x1800aee41  mov     r9d, eax; char *
0x1800aee44  mov     edx, 22h ; '"'; void *
0x1800aee49  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800aee4e  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x1800aee53  mov     [rsi+80h], rax
0x1800aee5a  mov     rcx, rdi
0x1800aee5d  mov     rdx, [rdi+10h]
0x1800aee61  inc     rdx
0x1800aee64  call    ?EnsureCapacity@?$Array@VStatementCacheEntry@StateRepository@@V?$ContainerOperations@VStatementCacheEntry@StateRepository@@V12@@Common@@DV?$ContainerOperations@DVStatementCacheEntry@StateRepository@@@4@V?$ArrayOperations@VStatementCacheEntry@StateRepository@@V12@@4@@Common@@QEAAJ_K@Z; Common::Array<StateRepository::StatementCacheEntry,Common::ContainerOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>,char,Common::ContainerOperations<char,StateRepository::StatementCacheEntry>,Common::ArrayOperations<StateRepository::StatementCacheEntry,StateRepository::StatementCacheEntry>>::EnsureCapacity(unsigned __int64)
0x1800aee69  mov     ebp, eax
0x1800aee6b  test    eax, eax
0x1800aee6d  js      short loc_1800AEE80
0x1800aee6f  mov     rcx, [rdi+10h]
0x1800aee73  mov     rax, [rdi]
0x1800aee76  mov     [rax+rcx*8], rsi
0x1800aee7a  inc     qword ptr [rdi+10h]
0x1800aee7e  xor     ebp, ebp
0x1800aee80  test    byte ptr cs:dword_180166488, 8
0x1800aee87  jz      short loc_1800AEEC6
0x1800aee89  mov     rax, [rdi+28h]
0x1800aee8d  mov     r8d, 1
0x1800aee93  mov     rcx, [rdi+20h]
0x1800aee97  mov     edx, [rdi+10h]
0x1800aee9a  lock xadd cs:dword_180169080, r8d
0x1800aeea3  mov     [rsp+58h+var_28], rax
0x1800aeea8  inc     r8d
0x1800aeeab  mov     [rsp+58h+var_30], rcx
0x1800aeeb0  mov     r9, r14
0x1800aeeb3  mov     dword ptr [rsp+58h+var_38], edx
0x1800aeeb7  mov     ecx, ebp
0x1800aeeb9  lea     rdx, aDatabasecacheA; "[DatabaseCache.Add] #%u Database %llu: "...
0x1800aeec0  call    cs:__imp_sqlite3_log
0x1800aeec6  test    ebp, ebp
0x1800aeec8  js      short loc_1800AEF20
0x1800aeeca  mov     rcx, [rdi+38h]
0x1800aeece  mov     eax, [rcx]
0x1800aeed0  cmp     eax, 5
0x1800aeed3  jbe     short loc_1800AEF03
0x1800aeed5  lea     rax, [rsp+58h+arg_0]
0x1800aeeda  mov     [rsp+58h+arg_0], 1000000h
0x1800aeee3  mov     [rsp+58h+var_30], rax
0x1800aeee8  lea     rdx, byte_18014C997
0x1800aeeef  lea     rax, [rsp+58h+arg_8]
0x1800aeef4  mov     [rsp+58h+arg_8], r14
0x1800aeef9  mov     [rsp+58h+var_38], rax
0x1800aeefe  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800aef03  mov     rcx, rbx; this
0x1800aef06  call    ?Reset@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Reset(void)
0x1800aef0b  xor     eax, eax
0x1800aef0d  mov     rbx, [rsp+58h+arg_10]
0x1800aef12  mov     rbp, [rsp+58h+arg_18]
0x1800aef17  add     rsp, 40h
0x1800aef1b  pop     r14
0x1800aef1d  pop     rdi
0x1800aef1e  pop     rsi
0x1800aef1f  retn
0x1800aef20  mov     rcx, rsi; this
0x1800aef23  call    ??_GDatabaseCacheEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::DatabaseCacheEntry::`scalar deleting destructor'(uint)
0x1800aef28  jmp     short loc_1800AEF0B
0x1800aef2a  mov     rcx, [rsp+58h]; this
0x1800aef2f  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1800aef36  mov     ebx, 8007000Eh
0x1800aef3b  mov     edx, 22h ; '"'; void *
0x1800aef40  mov     r9d, ebx; char *
0x1800aef43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aef48  mov     eax, ebx
0x1800aef4a  jmp     short loc_1800AEF0D
0x1800aef4c  mov     rcx, [rsp+58h]; this
0x1800aef51  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x1800aef58  mov     r9d, 80670014h; char *
0x1800aef5e  mov     edx, 11h; void *
0x1800aef63  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
