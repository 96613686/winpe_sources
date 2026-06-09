# StateRepository::DatabaseCache::Add(StateRepository::Database &)

- ea: `0x180107ce8`
- end: `0x180108028`
- name: `?Add@DatabaseCache@StateRepository@@QEAAJAEAVDatabase@2@@Z`
- size: `832`
- prototype: `__int64 __fastcall(StateRepository::DatabaseCache *this, struct StateRepository::Database *)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800f70c4`

## callees

- `0x18000163c`
- `0x180003060`
- `0x1800038f0`
- `0x180016970`
- `0x1800e4c4c`
- `0x1800e4e0a`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f5fd0`
- `0x1800f7630`
- `0x1800f875c`
- `0x1800f89f4`
- `0x1800f9d28`
- `0x1800f9ee8`
- `0x1800fb768`
- `0x180107ce8`
- `0x180108668`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180107e9e`
- `ntdll!RtlAllocateHeap` at `0x180107e9e`
- `ntdll!RtlFreeHeap` at `0x180107ee2`
- `ntdll!RtlFreeHeap` at `0x180107ee2`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180107e1b`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180107e1b`

## string_xrefs

- `0x180107d5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180107f39`: `[DatabaseCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu`
- `0x180107d73`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180107da0`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180107fef`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180108010`: `onecore\base\appmodel\staterepository\dataaccesslayer\databasecache.cpp`
- `0x180107dfb`: `onecore\base\appmodel\StateRepository\DataAccessLayer\DatabaseCache.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::DatabaseCache::Add(
        StateRepository::DatabaseCache *this,
        struct StateRepository::Database *a2)
{
  StateRepository::DatabaseCache *v3; // rbx
  int v4; // eax
  unsigned int v5; // edi
  int v6; // eax
  __int64 v7; // r12
  StateRepository::Database *v8; // rax
  struct StateRepository::Database *v9; // rsi
  int v10; // eax
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rdi
  int v14; // edi
  unsigned __int64 v15; // rax
  PVOID Heap; // rax
  PVOID v17; // r15
  _DWORD *v18; // rcx
  int v20; // [rsp+20h] [rbp-49h]
  unsigned __int64 UnbiasedTime; // [rsp+40h] [rbp-29h] BYREF
  __int64 v22; // [rsp+48h] [rbp-21h] BYREF
  _BYTE v23[32]; // [rsp+50h] [rbp-19h] BYREF
  __int64 *v24; // [rsp+70h] [rbp+7h]
  __int64 v25; // [rsp+78h] [rbp+Fh]
  unsigned __int64 *p_UnbiasedTime; // [rsp+80h] [rbp+17h]
  __int64 v27; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !*(_QWORD *)a2 )
    return 0;
  v3 = StateRepository::DatabaseCacheSingleton::s_cache;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
      (const char *)0x80670014LL,
      v20);
  if ( (dword_18013F948 & 0x8000) != 0 )
  {
    v4 = StateRepository::Database::CheckBusyStatements(*(struct sqlite3 **)a2, 0, 0);
    v5 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA25,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v4,
        v20);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xD7,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)v5);
    }
  }
  if ( (dword_18013F948 & 8) != 0 )
  {
    v6 = StateRepository::Database::LogStatistics(a2);
    if ( v6 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1C,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
        (const char *)(unsigned int)v6);
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
        (int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\DatabaseCache.hpp",
        (const char *)(unsigned int)v10);
    UnbiasedTime = 0;
    QueryUnbiasedInterruptTime(&UnbiasedTime);
    *((_QWORD *)v9 + 16) = UnbiasedTime / 0x2710;
    v11 = *((_QWORD *)v3 + 2);
    v12 = *((_QWORD *)v3 + 1);
    v13 = v11 + 1;
    if ( v11 + 1 > v12 )
    {
      if ( v12 == 0x3FFFFFFF )
      {
        v14 = -2147483637;
LABEL_29:
        if ( (dword_18013F948 & 8) != 0 )
          sqlite3_log(
            (unsigned int)v14,
            "[DatabaseCache.Add] #%u Database %llu: StatementCache Size/Hits/Misses %u/%llu/%llu",
            _InterlockedIncrement(&dword_180140410),
            v7,
            *((_DWORD *)v3 + 4),
            *((_QWORD *)v3 + 4),
            *((_QWORD *)v3 + 5));
        if ( v14 < 0 )
        {
          StateRepository::Database::~Database(v9);
          operator delete(v9);
        }
        else
        {
          v18 = (_DWORD *)*((_QWORD *)v3 + 7);
          if ( *v18 > 5u )
          {
            UnbiasedTime = 0x1000000;
            p_UnbiasedTime = &UnbiasedTime;
            v22 = v7;
            v24 = &v22;
            v27 = 8;
            v25 = 8;
            tlgWriteTransfer_EventWriteTransfer(v18, &byte_18012AC17, 0, 0, 4, v23);
          }
          StateRepository::Database::Reset(a2);
        }
        return 0;
      }
      if ( v12 )
        v15 = ((3 * v12) >> 1) + 1;
      else
        v15 = 16;
      if ( v13 <= v15 )
        v13 = v15;
      if ( v13 > 0x3FFFFFFF )
        v13 = 0x3FFFFFFF;
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 8 * v13);
      v17 = Heap;
      if ( !Heap )
      {
        v14 = -2147024882;
        goto LABEL_29;
      }
      if ( *(_QWORD *)v3 )
      {
        memmove_0(Heap, *(const void **)v3, 8LL * *((_QWORD *)v3 + 2));
        if ( *(_QWORD *)v3 )
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *(PVOID *)v3);
      }
      v11 = *((_QWORD *)v3 + 2);
      *(_QWORD *)v3 = v17;
      *((_QWORD *)v3 + 1) = v13;
    }
    *(_QWORD *)(*(_QWORD *)v3 + 8 * v11) = v9;
    ++*((_QWORD *)v3 + 2);
    v14 = 0;
    goto LABEL_29;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\databasecache.cpp",
    (const char *)0x8007000ELL,
    v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180107ce8  mov     [rsp-8+arg_0], rbx
0x180107ced  mov     [rsp-8+arg_10], rsi
0x180107cf2  push    rbp
0x180107cf3  push    rdi
0x180107cf4  push    r12
0x180107cf6  push    r14
0x180107cf8  push    r15
0x180107cfa  lea     rbp, [rsp-37h]
0x180107cff  sub     rsp, 0A0h
0x180107d06  mov     rax, cs:__security_cookie
0x180107d0d  xor     rax, rsp
0x180107d10  mov     [rbp+57h+var_30], rax
0x180107d14  cmp     qword ptr [rdx], 0
0x180107d18  mov     r14, rdx
0x180107d1b  jz      loc_180107FAF
0x180107d21  mov     rbx, cs:?s_cache@DatabaseCacheSingleton@StateRepository@@0PEAVDatabaseCache@2@EA; StateRepository::DatabaseCache * StateRepository::DatabaseCacheSingleton::s_cache
0x180107d28  mov     rcx, rdx; this
0x180107d2b  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180107d30  test    al, al
0x180107d32  jz      loc_18010800C
0x180107d38  test    cs:dword_18013F948, 8000h
0x180107d42  jz      short loc_180107D87
0x180107d44  mov     rcx, [r14]; struct sqlite3 *
0x180107d47  xor     r8d, r8d; unsigned int *
0x180107d4a  xor     edx, edx; bool
0x180107d4c  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x180107d51  mov     edi, eax
0x180107d53  test    eax, eax
0x180107d55  jns     short loc_180107D87
0x180107d57  mov     rcx, [rbp+5Fh]; this
0x180107d5b  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x180107d62  mov     r9d, eax; char *
0x180107d65  mov     edx, 0A25h; void *
0x180107d6a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180107d6f  mov     rcx, [rbp+5Fh]; this
0x180107d73  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180107d7a  mov     r9d, edi; char *
0x180107d7d  mov     edx, 0D7h; void *
0x180107d82  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107d87  test    byte ptr cs:dword_18013F948, 8
0x180107d8e  jz      short loc_180107DB4
0x180107d90  mov     rcx, r14; this
0x180107d93  call    ?LogStatistics@Database@StateRepository@@QEAAJXZ; StateRepository::Database::LogStatistics(void)
0x180107d98  test    eax, eax
0x180107d9a  jns     short loc_180107DB4
0x180107d9c  mov     rcx, [rbp+5Fh]; this
0x180107da0  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180107da7  mov     r9d, eax; char *
0x180107daa  mov     edx, 1Ch; void *
0x180107daf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107db4  mov     r12, [r14+78h]
0x180107db8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180107dbf  mov     ecx, 88h; unsigned __int64
0x180107dc4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180107dc9  mov     rsi, rax
0x180107dcc  test    rax, rax
0x180107dcf  jz      loc_180107FEB
0x180107dd5  mov     rcx, rax; this
0x180107dd8  call    ??0Database@StateRepository@@QEAA@XZ; StateRepository::Database::Database(void)
0x180107ddd  mov     rdx, rsi; struct StateRepository::Database *
0x180107de0  mov     qword ptr [rsi+80h], 0
0x180107deb  mov     rcx, r14; struct StateRepository::Database *
0x180107dee  call    ?Move@DatabaseCacheEntry@StateRepository@@CAJAEAVDatabase@2@0@Z; StateRepository::DatabaseCacheEntry::Move(StateRepository::Database &,StateRepository::Database &)
0x180107df3  test    eax, eax
0x180107df5  jns     short loc_180107E0F
0x180107df7  mov     rcx, [rbp+5Fh]; this
0x180107dfb  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x180107e02  mov     r9d, eax; char *
0x180107e05  mov     edx, 22h ; '"'; void *
0x180107e0a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180107e0f  lea     rcx, [rbp+57h+UnbiasedTime]; UnbiasedTime
0x180107e13  mov     [rbp+57h+UnbiasedTime], 0
0x180107e1b  call    cs:__imp_QueryUnbiasedInterruptTime
0x180107e21  mov     rax, 346DC5D63886594Bh
0x180107e2b  mul     [rbp+57h+UnbiasedTime]
0x180107e2f  shr     rdx, 0Bh
0x180107e33  mov     [rsi+80h], rdx
0x180107e3a  mov     rcx, [rbx+10h]
0x180107e3e  mov     rax, [rbx+8]
0x180107e42  lea     rdi, [rcx+1]
0x180107e46  cmp     rdi, rax
0x180107e49  jbe     loc_180107EF3
0x180107e4f  mov     ecx, 3FFFFFFFh
0x180107e54  cmp     rax, rcx
0x180107e57  jnz     short loc_180107E63
0x180107e59  mov     edi, 8000000Bh
0x180107e5e  jmp     loc_180107F00
0x180107e63  test    rax, rax
0x180107e66  jnz     short loc_180107E6F
0x180107e68  mov     eax, 10h
0x180107e6d  jmp     short loc_180107E79
0x180107e6f  lea     rax, [rax+rax*2]
0x180107e73  shr     rax, 1
0x180107e76  inc     rax
0x180107e79  cmp     rdi, rax
0x180107e7c  cmovbe  rdi, rax
0x180107e80  cmp     rdi, rcx
0x180107e83  cmova   rdi, rcx
0x180107e87  mov     rcx, gs:60h
0x180107e90  xor     edx, edx; Flags
0x180107e92  mov     rcx, [rcx+30h]; HeapHandle
0x180107e96  lea     r8, ds:0[rdi*8]; Size
0x180107e9e  call    cs:__imp_RtlAllocateHeap
0x180107ea4  mov     r15, rax
0x180107ea7  test    rax, rax
0x180107eaa  jnz     short loc_180107EB3
0x180107eac  mov     edi, 8007000Eh
0x180107eb1  jmp     short loc_180107F00
0x180107eb3  mov     rdx, [rbx]; Src
0x180107eb6  test    rdx, rdx
0x180107eb9  jz      short loc_180107EE8
0x180107ebb  mov     r8, [rbx+10h]
0x180107ebf  mov     rcx, r15; void *
0x180107ec2  shl     r8, 3; Size
0x180107ec6  call    memmove_0
0x180107ecb  mov     r8, [rbx]; P
0x180107ece  test    r8, r8
0x180107ed1  jz      short loc_180107EE8
0x180107ed3  mov     rcx, gs:60h
0x180107edc  xor     edx, edx; Flags
0x180107ede  mov     rcx, [rcx+30h]; HeapHandle
0x180107ee2  call    cs:__imp_RtlFreeHeap
0x180107ee8  mov     rcx, [rbx+10h]
0x180107eec  mov     [rbx], r15
0x180107eef  mov     [rbx+8], rdi
0x180107ef3  mov     rax, [rbx]
0x180107ef6  mov     [rax+rcx*8], rsi
0x180107efa  inc     qword ptr [rbx+10h]
0x180107efe  xor     edi, edi
0x180107f00  test    byte ptr cs:dword_18013F948, 8
0x180107f07  jz      short loc_180107F45
0x180107f09  mov     rax, [rbx+28h]
0x180107f0d  mov     r8d, 1
0x180107f13  mov     rcx, [rbx+20h]
0x180107f17  mov     edx, [rbx+10h]
0x180107f1a  lock xadd cs:dword_180140410, r8d
0x180107f23  mov     [rsp+0C0h+var_90], rax
0x180107f28  inc     r8d
0x180107f2b  mov     [rsp+0C0h+var_98], rcx
0x180107f30  mov     r9, r12
0x180107f33  mov     [rsp+0C0h+var_A0], edx
0x180107f37  mov     ecx, edi
0x180107f39  lea     rdx, aDatabasecacheA; "[DatabaseCache.Add] #%u Database %llu: "...
0x180107f40  call    sqlite3_log
0x180107f45  test    edi, edi
0x180107f47  js      loc_180107FD9
0x180107f4d  mov     rcx, [rbx+38h]
0x180107f51  mov     eax, [rcx]
0x180107f53  cmp     eax, 5
0x180107f56  jbe     short loc_180107FA7
0x180107f58  lea     rax, [rbp+57h+UnbiasedTime]
0x180107f5c  mov     [rbp+57h+UnbiasedTime], 1000000h
0x180107f64  mov     [rbp+57h+var_40], rax
0x180107f68  lea     rdx, byte_18012AC17
0x180107f6f  lea     rax, [rbp+57h+var_78]
0x180107f73  mov     [rbp+57h+var_78], r12
0x180107f77  mov     [rbp+57h+var_50], rax
0x180107f7b  xor     r9d, r9d
0x180107f7e  lea     rax, [rbp+57h+var_70]
0x180107f82  mov     [rbp+57h+var_38], 8
0x180107f8a  mov     [rsp+0C0h+var_98], rax
0x180107f8f  xor     r8d, r8d
0x180107f92  mov     [rsp+0C0h+var_A0], 4
0x180107f9a  mov     [rbp+57h+var_48], 8
0x180107fa2  call    _tlgWriteTransfer_EventWriteTransfer
0x180107fa7  mov     rcx, r14; this
0x180107faa  call    ?Reset@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Reset(void)
0x180107faf  xor     eax, eax
0x180107fb1  mov     rcx, [rbp+57h+var_30]
0x180107fb5  xor     rcx, rsp; StackCookie
0x180107fb8  call    __security_check_cookie
0x180107fbd  lea     r11, [rsp+0C0h+var_20]
0x180107fc5  mov     rbx, [r11+30h]
0x180107fc9  mov     rsi, [r11+40h]
0x180107fcd  mov     rsp, r11
0x180107fd0  pop     r15
0x180107fd2  pop     r14
0x180107fd4  pop     r12
0x180107fd6  pop     rdi
0x180107fd7  pop     rbp
0x180107fd8  retn
0x180107fd9  mov     rcx, rsi; this
0x180107fdc  call    ??1Database@StateRepository@@QEAA@XZ; StateRepository::Database::~Database(void)
0x180107fe1  mov     rcx, rsi; Block
0x180107fe4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180107fe9  jmp     short loc_180107FAF
0x180107feb  mov     rcx, [rbp+5Fh]; this
0x180107fef  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180107ff6  mov     edi, 8007000Eh
0x180107ffb  mov     edx, 22h ; '"'; void *
0x180108000  mov     r9d, edi; char *
0x180108003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180108008  mov     eax, edi
0x18010800a  jmp     short loc_180107FB1
0x18010800c  mov     rcx, [rbp+5Fh]; this
0x180108010  lea     r8, aOnecoreBaseApp_13; "onecore\\base\\appmodel\\staterepositor"...
0x180108017  mov     r9d, 80670014h; char *
0x18010801d  mov     edx, 11h; void *
0x180108022  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
