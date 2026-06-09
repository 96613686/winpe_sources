# StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)

- ea: `0x180014fe4`
- end: `0x1800151c3`
- name: `?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z`
- size: `479`
- prototype: `struct StateRepository::Statement *(StateRepository::StatementCache *__hidden this, const char *, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180019614`

## callees

- `0x18000b9f8`
- `0x18000c3bc`
- `0x180014eb4`
- `0x180014fe4`
- `0x1800151cc`
- `0x18001bfdc`
- `0x18002dc7c`

## import_xrefs

- `StateRepository.Core!sqlite3_db_handle` at `0x1800150b8`
- `StateRepository.Core!sqlite3_db_handle` at `0x1800150b8`
- `StateRepository.Core!sqlite3_log` at `0x180015037`
- `StateRepository.Core!sqlite3_log` at `0x18001512c`
- `StateRepository.Core!sqlite3_log` at `0x1800151ae`
- `StateRepository.Core!sqlite3_log` at `0x180015037`
- `StateRepository.Core!sqlite3_log` at `0x18001512c`
- `StateRepository.Core!sqlite3_log` at `0x1800151ae`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800150c8`
- `StateRepository.Core!sqlite3_get_clientdata` at `0x1800150c8`

## string_xrefs

- `0x180015146`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementcache.cpp`
- `0x180015026`: `[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu`
- `0x18001511d`: `[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`
- `0x180015198`: `[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s`

## pseudocode

```c
struct StateRepository::Statement *__fastcall StateRepository::StatementCache::Get(
        StateRepository::StatementCache *this,
        const char *a2,
        struct StateRepository::Statement *a3)
{
  _DWORD *v3; // r14
  unsigned __int64 i; // rdi
  unsigned __int64 v8; // r8
  StateRepository::StatementCacheEntry *v9; // rsi
  StateRepository::StatementCacheEntry **v10; // rcx
  __int64 v11; // rax
  __int64 clientdata; // rdi
  const char *Sql; // rax
  int v14; // eax
  unsigned int v15; // edx
  int v17; // [rsp+20h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v3 = (_DWORD *)((char *)this + 16);
  if ( (dword_18004B904 & 8) != 0 )
    sqlite3_log(
      0,
      "[pre-StatementCache.Get] #%u StatementCache Size/Hits/Misses %u/%llu/%llu",
      _InterlockedIncrement(&dword_18004BFF0),
      *v3,
      *((_QWORD *)this + 4),
      *((_QWORD *)this + 5));
  if ( !*(_QWORD *)v3 )
    goto LABEL_22;
  for ( i = *(_QWORD *)v3 - 1LL;
        !(unsigned __int8)Common::ContainerOperations<char,StateRepository::StatementCacheEntry>::IsEqual(
                            a2,
                            *(_QWORD *)(*(_QWORD *)this + 8 * i));
        --i )
  {
    if ( !i )
      goto LABEL_22;
  }
  if ( i == 0x40000000 )
  {
LABEL_22:
    ++*((_QWORD *)this + 5);
    if ( (dword_18004B904 & 8) != 0 )
      sqlite3_log(
        0,
        "[StatementCache.Get(Miss)] #%u StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        *v3,
        *((_QWORD *)this + 4),
        *((_QWORD *)this + 5),
        a2);
    return 0;
  }
  else
  {
    ++*((_QWORD *)this + 4);
    v8 = *((_QWORD *)this + 2);
    if ( i < v8 )
    {
      v10 = (StateRepository::StatementCacheEntry **)(*(_QWORD *)this + 8 * i);
      v9 = *v10;
      memmove_0(v10, v10 + 1, 8 * (v8 - i) - 8);
      --*(_QWORD *)v3;
    }
    else
    {
      v9 = 0;
    }
    if ( (dword_18004B904 & 8) != 0 )
    {
      v11 = sqlite3_db_handle(*(_QWORD *)a3);
      clientdata = sqlite3_get_clientdata(v11, "connection.id");
      if ( StateRepository::Statement::GetSql(a3) )
        Sql = StateRepository::Statement::GetSql(a3);
      else
        Sql = "<null>";
      sqlite3_log(
        0,
        "[StatementCache.Get(Hit)] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: SQL %s",
        _InterlockedIncrement(&dword_18004BFF0),
        clientdata,
        *v3,
        *((_QWORD *)this + 4),
        *((_QWORD *)this + 5),
        Sql);
    }
    v14 = StateRepository::StatementCacheEntry::Detach(v9, a3);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x70,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementcache.cpp",
        (const char *)(unsigned int)v14,
        v17);
    if ( v9 )
      StateRepository::StatementCacheEntry::`scalar deleting destructor'(v9, v15);
    return a3;
  }
}

```

## disassembly

```asm
0x180014fe4  push    rbx
0x180014fe6  push    rbp
0x180014fe7  push    rsi
0x180014fe8  push    rdi
0x180014fe9  push    r14
0x180014feb  push    r15
0x180014fed  sub     rsp, 48h
0x180014ff1  test    byte ptr cs:dword_18004B904, 8
0x180014ff8  lea     r14, [rcx+10h]
0x180014ffc  mov     r15, r8
0x180014fff  mov     rbp, rdx
0x180015002  mov     rbx, rcx
0x180015005  jz      short loc_18001503D
0x180015007  mov     rax, [rcx+28h]
0x18001500b  mov     r8d, 1
0x180015011  mov     r10, [rcx+20h]
0x180015015  mov     r9d, [r14]
0x180015018  lock xadd cs:dword_18004BFF0, r8d
0x180015021  mov     [rsp+78h+var_50], rax
0x180015026  lea     rdx, aPreStatementca; "[pre-StatementCache.Get] #%u StatementC"...
0x18001502d  inc     r8d
0x180015030  mov     qword ptr [rsp+78h+var_58], r10
0x180015035  xor     ecx, ecx
0x180015037  call    cs:__imp_sqlite3_log
0x18001503d  mov     rdi, [r14]
0x180015040  test    rdi, rdi
0x180015043  jz      loc_18001516C
0x180015049  dec     rdi
0x18001504c  jmp     short loc_18001505A
0x18001504e  test    rdi, rdi
0x180015051  jz      loc_18001516C
0x180015057  dec     rdi
0x18001505a  mov     rdx, [rbx]
0x18001505d  mov     rcx, rbp
0x180015060  mov     rdx, [rdx+rdi*8]
0x180015064  call    ?IsEqual@?$ContainerOperations@DVStatementCacheEntry@StateRepository@@@Common@@SA_NPEBDPEBVStatementCacheEntry@StateRepository@@@Z; Common::ContainerOperations<char,StateRepository::StatementCacheEntry>::IsEqual(char const *,StateRepository::StatementCacheEntry const *)
0x180015069  test    al, al
0x18001506b  jz      short loc_18001504E
0x18001506d  cmp     rdi, 40000000h
0x180015074  jz      loc_18001516C
0x18001507a  inc     qword ptr [rbx+20h]
0x18001507e  mov     r8, [rbx+10h]
0x180015082  cmp     rdi, r8
0x180015085  jb      short loc_18001508B
0x180015087  xor     esi, esi
0x180015089  jmp     short loc_1800150AC
0x18001508b  mov     rax, [rbx]
0x18001508e  sub     r8, rdi
0x180015091  lea     rcx, [rax+rdi*8]; void *
0x180015095  mov     rsi, [rcx]
0x180015098  lea     rdx, [rcx+8]; Src
0x18001509c  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x1800150a4  call    memmove_0
0x1800150a9  dec     qword ptr [r14]
0x1800150ac  test    byte ptr cs:dword_18004B904, 8
0x1800150b3  jz      short loc_180015132
0x1800150b5  mov     rcx, [r15]
0x1800150b8  call    cs:__imp_sqlite3_db_handle
0x1800150be  mov     rcx, rax
0x1800150c1  lea     rdx, aConnectionId; "connection.id"
0x1800150c8  call    cs:__imp_sqlite3_get_clientdata
0x1800150ce  mov     rcx, r15; this
0x1800150d1  mov     rdi, rax
0x1800150d4  call    ?GetSql@Statement@StateRepository@@QEBAPEBDXZ; StateRepository::Statement::GetSql(void)
0x1800150d9  test    rax, rax
0x1800150dc  jnz     short loc_1800150E7
0x1800150de  lea     rax, aNull; "<null>"
0x1800150e5  jmp     short loc_1800150EF
0x1800150e7  mov     rcx, r15; this
0x1800150ea  call    ?GetSql@Statement@StateRepository@@QEBAPEBDXZ; StateRepository::Statement::GetSql(void)
0x1800150ef  mov     rcx, [rbx+28h]
0x1800150f3  mov     r8d, 1
0x1800150f9  mov     rdx, [rbx+20h]
0x1800150fd  mov     r9d, [r14]
0x180015100  lock xadd cs:dword_18004BFF0, r8d
0x180015109  mov     [rsp+78h+var_40], rax
0x18001510e  inc     r8d
0x180015111  mov     [rsp+78h+var_48], rcx
0x180015116  xor     ecx, ecx
0x180015118  mov     [rsp+78h+var_50], rdx
0x18001511d  lea     rdx, aStatementcache_1; "[StatementCache.Get(Hit)] #%u Database "...
0x180015124  mov     [rsp+78h+var_58], r9d; int
0x180015129  mov     r9, rdi
0x18001512c  call    cs:__imp_sqlite3_log
0x180015132  mov     rdx, r15; struct StateRepository::Statement *
0x180015135  mov     rcx, rsi; this
0x180015138  call    ?Detach@StatementCacheEntry@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCacheEntry::Detach(StateRepository::Statement &)
0x18001513d  test    eax, eax
0x18001513f  jns     short loc_18001515A
0x180015141  mov     rcx, [rsp+78h]; this
0x180015146  lea     r8, aOnecoreBaseApp_52; "onecore\\base\\appmodel\\staterepositor"...
0x18001514d  mov     r9d, eax; char *
0x180015150  mov     edx, 70h ; 'p'; void *
0x180015155  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001515a  test    rsi, rsi
0x18001515d  jz      short loc_180015167
0x18001515f  mov     rcx, rsi; this
0x180015162  call    ??_GStatementCacheEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::StatementCacheEntry::`scalar deleting destructor'(uint)
0x180015167  mov     rax, r15
0x18001516a  jmp     short loc_1800151B6
0x18001516c  inc     qword ptr [rbx+28h]
0x180015170  test    byte ptr cs:dword_18004B904, 8
0x180015177  mov     rcx, [rbx+28h]
0x18001517b  jz      short loc_1800151B4
0x18001517d  mov     rax, [rbx+20h]
0x180015181  mov     r8d, 1
0x180015187  mov     r9d, [r14]
0x18001518a  lock xadd cs:dword_18004BFF0, r8d
0x180015193  mov     [rsp+78h+var_48], rbp
0x180015198  lea     rdx, aStatementcache_0; "[StatementCache.Get(Miss)] #%u Statemen"...
0x18001519f  mov     [rsp+78h+var_50], rcx
0x1800151a4  inc     r8d
0x1800151a7  xor     ecx, ecx
0x1800151a9  mov     qword ptr [rsp+78h+var_58], rax
0x1800151ae  call    cs:__imp_sqlite3_log
0x1800151b4  xor     eax, eax
0x1800151b6  add     rsp, 48h
0x1800151ba  pop     r15
0x1800151bc  pop     r14
0x1800151be  pop     rdi
0x1800151bf  pop     rsi
0x1800151c0  pop     rbp
0x1800151c1  pop     rbx
0x1800151c2  retn
```
