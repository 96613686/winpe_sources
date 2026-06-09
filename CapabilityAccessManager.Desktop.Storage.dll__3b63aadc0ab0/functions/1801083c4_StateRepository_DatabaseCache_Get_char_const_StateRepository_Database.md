# StateRepository::DatabaseCache::Get(char const *,StateRepository::Database &)

- ea: `0x1801083c4`
- end: `0x18010865f`
- name: `?Get@DatabaseCache@StateRepository@@QEAAPEAVDatabase@2@PEBDAEAV32@@Z`
- size: `667`
- prototype: `struct StateRepository::Database *__fastcall(StateRepository::DatabaseCache *__hidden this, const char *, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1801019b8`

## callees

- `0x18000163c`
- `0x180003060`
- `0x1800038f0`
- `0x180003a04`
- `0x18000ed50`
- `0x180016970`
- `0x1800e4e0a`
- `0x1800f7630`
- `0x1800f875c`
- `0x1801083c4`
- `0x180108668`

## string_xrefs

- `0x18010855d`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x18010853a`: `[DatabaseCache.Get(Hit)] #%u DatabaseCache Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x18010842a`: `[pre-DatabaseCache.Get] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`
- `0x18010861b`: `[DatabaseCache.Get(Miss)] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s`

## pseudocode

```c
struct StateRepository::Database *__fastcall StateRepository::DatabaseCache::Get(
        StateRepository::DatabaseCache *this,
        const char *a2,
        struct StateRepository::Database *a3)
{
  StateRepository::DatabaseCache *v4; // rbx
  _DWORD *v6; // r14
  unsigned __int64 i; // rdi
  __int64 v8; // rcx
  __int64 v9; // rax
  struct StateRepository::Database *v10; // rsi
  struct StateRepository::Database **v11; // rcx
  __int64 v12; // rdi
  const char *v13; // r9
  int v14; // eax
  _DWORD *v15; // rcx
  __int64 v17; // [rsp+40h] [rbp-88h] BYREF
  __int64 v18; // [rsp+48h] [rbp-80h] BYREF
  _BYTE v19[32]; // [rsp+50h] [rbp-78h] BYREF
  __int64 *v20; // [rsp+70h] [rbp-58h]
  __int64 v21; // [rsp+78h] [rbp-50h]
  __int64 *v22; // [rsp+80h] [rbp-48h]
  __int64 v23; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v4 = StateRepository::DatabaseCacheSingleton::s_cache;
  v6 = (_DWORD *)((char *)StateRepository::DatabaseCacheSingleton::s_cache + 16);
  if ( (dword_18013F948 & 8) != 0 )
    sqlite3_log(
      0,
      "[pre-DatabaseCache.Get] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s",
      _InterlockedIncrement(&dword_180140410),
      *v6,
      *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 4),
      *((_QWORD *)StateRepository::DatabaseCacheSingleton::s_cache + 5),
      a2);
  if ( !*(_QWORD *)v6 )
    goto LABEL_28;
  for ( i = *(_QWORD *)v6 - 1LL; ; --i )
  {
    v8 = **(_QWORD **)(*(_QWORD *)v4 + 8 * i);
    v9 = v8 ? sqlite3_db_filename(v8, 0) : 0LL;
    if ( !(unsigned int)o__stricmp_0(a2, v9) )
      break;
    if ( !i )
      goto LABEL_28;
  }
  if ( i == 0x40000000 )
  {
LABEL_28:
    ++*((_QWORD *)v4 + 5);
    if ( (dword_18013F948 & 8) != 0 )
      sqlite3_log(
        0,
        "[DatabaseCache.Get(Miss)] #%u DatabaseCache Size/Hits/Misses %u/%llu/%llu: Filename %s",
        _InterlockedIncrement(&dword_180140410),
        *v6,
        *((_QWORD *)v4 + 4),
        *((_QWORD *)v4 + 5),
        a2);
    return 0;
  }
  else
  {
    ++*((_QWORD *)v4 + 4);
    if ( i < *(_QWORD *)v6 )
    {
      _mm_lfence();
      v11 = (struct StateRepository::Database **)(*(_QWORD *)v4 + 8 * i);
      v10 = *v11;
      memmove_0(v11, v11 + 1, 8 * (*(_QWORD *)v6 - i) - 8);
      --*(_QWORD *)v6;
    }
    else
    {
      v10 = 0;
    }
    v12 = *((_QWORD *)v10 + 15);
    if ( (dword_18013F948 & 8) != 0 )
    {
      if ( *(_QWORD *)v10 && sqlite3_db_filename(*(_QWORD *)v10, 0) )
      {
        if ( *(_QWORD *)v10 )
          v13 = (const char *)sqlite3_db_filename(*(_QWORD *)v10, 0);
        else
          v13 = 0;
      }
      else
      {
        v13 = "<null>";
      }
      sqlite3_log(
        0,
        "[DatabaseCache.Get(Hit)] #%u DatabaseCache Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu: Filename %s",
        _InterlockedIncrement(&dword_180140410),
        v12,
        *v6,
        *((_QWORD *)v4 + 4),
        *((_QWORD *)v4 + 5),
        v13);
    }
    v14 = StateRepository::DatabaseCacheEntry::Move(v10, a3);
    if ( v14 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)(unsigned int)v14);
    v15 = (_DWORD *)*((_QWORD *)v4 + 7);
    if ( *v15 > 5u )
    {
      v17 = 0x1000000;
      v22 = &v17;
      v18 = v12;
      v20 = &v18;
      v23 = 8;
      v21 = 8;
      tlgWriteTransfer_EventWriteTransfer(v15, &unk_18012ABD8, 0, 0, 4, v19);
    }
    StateRepository::Database::~Database(v10);
    operator delete(v10);
    return a3;
  }
}

```

## disassembly

```asm
0x1801083c4  mov     [rsp+arg_0], rbx
0x1801083c9  push    rbp
0x1801083ca  push    rsi
0x1801083cb  push    rdi
0x1801083cc  push    r14
0x1801083ce  push    r15
0x1801083d0  sub     rsp, 0A0h
0x1801083d7  mov     rax, cs:__security_cookie
0x1801083de  xor     rax, rsp
0x1801083e1  mov     [rsp+0C8h+var_38], rax
0x1801083e9  test    byte ptr cs:dword_18013F948, 8
0x1801083f0  mov     r15, r8
0x1801083f3  mov     rbx, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x1801083fa  mov     rbp, rdx
0x1801083fd  lea     r14, [rbx+10h]
0x180108401  jz      short loc_18010843D
0x180108403  mov     rax, [rbx+28h]
0x180108407  mov     r8d, 1
0x18010840d  mov     rcx, [rbx+20h]
0x180108411  mov     r9d, [r14]
0x180108414  lock xadd cs:dword_180140410, r8d
0x18010841d  mov     [rsp+0C8h+var_98], rdx
0x180108422  inc     r8d
0x180108425  mov     [rsp+0C8h+var_A0], rax
0x18010842a  lea     rdx, aPreDatabasecac; "[pre-DatabaseCache.Get] #%u DatabaseCac"...
0x180108431  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x180108436  xor     ecx, ecx
0x180108438  call    sqlite3_log
0x18010843d  mov     rdi, [r14]
0x180108440  test    rdi, rdi
0x180108443  jz      loc_1801085EF
0x180108449  dec     rdi
0x18010844c  mov     rax, [rbx]
0x18010844f  mov     rcx, [rax+rdi*8]
0x180108453  mov     rcx, [rcx]
0x180108456  test    rcx, rcx
0x180108459  jz      short loc_180108464
0x18010845b  xor     edx, edx
0x18010845d  call    sqlite3_db_filename
0x180108462  jmp     short loc_180108466
0x180108464  xor     eax, eax
0x180108466  mov     rdx, rax
0x180108469  mov     rcx, rbp
0x18010846c  call    _o__stricmp_0
0x180108471  test    eax, eax
0x180108473  jz      short loc_180108483
0x180108475  test    rdi, rdi
0x180108478  jz      loc_1801085EF
0x18010847e  dec     rdi
0x180108481  jmp     short loc_18010844C
0x180108483  cmp     rdi, 40000000h
0x18010848a  jz      loc_1801085EF
0x180108490  inc     qword ptr [rbx+20h]
0x180108494  mov     r8, [r14]
0x180108497  cmp     rdi, r8
0x18010849a  jb      short loc_1801084A0
0x18010849c  xor     esi, esi
0x18010849e  jmp     short loc_1801084C4
0x1801084a0  lfence
0x1801084a3  mov     rax, [rbx]
0x1801084a6  sub     r8, rdi
0x1801084a9  lea     rcx, [rax+rdi*8]; void *
0x1801084ad  mov     rsi, [rcx]
0x1801084b0  lea     rdx, [rcx+8]; Src
0x1801084b4  lea     r8, ds:0FFFFFFFFFFFFFFF8h[r8*8]; Size
0x1801084bc  call    memmove_0
0x1801084c1  dec     qword ptr [r14]
0x1801084c4  test    byte ptr cs:dword_18013F948, 8
0x1801084cb  mov     rdi, [rsi+78h]
0x1801084cf  jz      short loc_180108546
0x1801084d1  mov     rcx, [rsi]
0x1801084d4  test    rcx, rcx
0x1801084d7  jz      short loc_1801084FE
0x1801084d9  xor     edx, edx
0x1801084db  call    sqlite3_db_filename
0x1801084e0  test    rax, rax
0x1801084e3  jz      short loc_1801084FE
0x1801084e5  mov     rcx, [rsi]
0x1801084e8  test    rcx, rcx
0x1801084eb  jz      short loc_1801084F9
0x1801084ed  xor     edx, edx
0x1801084ef  call    sqlite3_db_filename
0x1801084f4  mov     r9, rax
0x1801084f7  jmp     short loc_180108505
0x1801084f9  xor     r9d, r9d
0x1801084fc  jmp     short loc_180108505
0x1801084fe  lea     r9, aNull_1; "<null>"
0x180108505  mov     rax, [rbx+28h]
0x180108509  mov     r8d, 1
0x18010850f  mov     rcx, [rbx+20h]
0x180108513  mov     edx, [r14]
0x180108516  lock xadd cs:dword_180140410, r8d
0x18010851f  mov     [rsp+0C8h+var_90], r9
0x180108524  inc     r8d
0x180108527  mov     [rsp+0C8h+var_98], rax
0x18010852c  mov     r9, rdi
0x18010852f  mov     [rsp+0C8h+var_A0], rcx
0x180108534  xor     ecx, ecx
0x180108536  mov     [rsp+0C8h+var_A8], edx; int
0x18010853a  lea     rdx, aDatabasecacheG; "[DatabaseCache.Get(Hit)] #%u DatabaseCa"...
0x180108541  call    sqlite3_log
0x180108546  mov     rdx, r15; struct StateRepository::Database *
0x180108549  mov     rcx, rsi; struct StateRepository::Database *
0x18010854c  call    ?Move@DatabaseCacheEntry@StateRepository@@CAJAEAVDatabase@2@0@Z; StateRepository::DatabaseCacheEntry::Move(StateRepository::Database &,StateRepository::Database &)
0x180108551  test    eax, eax
0x180108553  jns     short loc_180108571
0x180108555  mov     rcx, [rsp+0C8h]; this
0x18010855d  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180108564  mov     r9d, eax; char *
0x180108567  mov     edx, 51h ; 'Q'; void *
0x18010856c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180108571  mov     rcx, [rbx+38h]
0x180108575  mov     eax, [rcx]
0x180108577  cmp     eax, 5
0x18010857a  jbe     short loc_1801085DA
0x18010857c  lea     rax, [rsp+0C8h+var_88]
0x180108581  mov     [rsp+0C8h+var_88], 1000000h
0x18010858a  mov     [rsp+0C8h+var_48], rax
0x180108592  lea     rdx, unk_18012ABD8
0x180108599  lea     rax, [rsp+0C8h+var_80]
0x18010859e  mov     [rsp+0C8h+var_80], rdi
0x1801085a3  mov     [rsp+0C8h+var_58], rax
0x1801085a8  xor     r9d, r9d
0x1801085ab  lea     rax, [rsp+0C8h+var_78]
0x1801085b0  mov     [rsp+0C8h+var_40], 8
0x1801085bc  mov     [rsp+0C8h+var_A0], rax
0x1801085c1  xor     r8d, r8d
0x1801085c4  mov     [rsp+0C8h+var_A8], 4
0x1801085cc  mov     [rsp+0C8h+var_50], 8
0x1801085d5  call    _tlgWriteTransfer_EventWriteTransfer
0x1801085da  mov     rcx, rsi; this
0x1801085dd  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x1801085e2  mov     rcx, rsi; Block
0x1801085e5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1801085ea  mov     rax, r15
0x1801085ed  jmp     short loc_180108638
0x1801085ef  inc     qword ptr [rbx+28h]
0x1801085f3  test    byte ptr cs:dword_18013F948, 8
0x1801085fa  mov     rcx, [rbx+28h]
0x1801085fe  jz      short loc_180108636
0x180108600  mov     rax, [rbx+20h]
0x180108604  mov     r8d, 1
0x18010860a  mov     r9d, [r14]
0x18010860d  lock xadd cs:dword_180140410, r8d
0x180108616  mov     [rsp+0C8h+var_98], rbp
0x18010861b  lea     rdx, aDatabasecacheG_0; "[DatabaseCache.Get(Miss)] #%u DatabaseC"...
0x180108622  mov     [rsp+0C8h+var_A0], rcx
0x180108627  inc     r8d
0x18010862a  xor     ecx, ecx
0x18010862c  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180108631  call    sqlite3_log
0x180108636  xor     eax, eax
0x180108638  mov     rcx, [rsp+0C8h+var_38]
0x180108640  xor     rcx, rsp; StackCookie
0x180108643  call    __security_check_cookie
0x180108648  mov     rbx, [rsp+0C8h+arg_0]
0x180108650  add     rsp, 0A0h
0x180108657  pop     r15
0x180108659  pop     r14
0x18010865b  pop     rdi
0x18010865c  pop     rsi
0x18010865d  pop     rbp
0x18010865e  retn
```
