# StateRepository::Database::Close(void)

- ea: `0x180018804`
- end: `0x18001892e`
- name: `?Close@Database@StateRepository@@QEAAJXZ`
- size: `298`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000c1f4`
- `0x1800182b0`

## callees

- `0x18000a3c0`
- `0x18000b9f8`
- `0x18000c3bc`
- `0x180018694`
- `0x180018804`
- `0x180018fd0`
- `0x180019460`
- `0x1800196e4`

## import_xrefs

- `StateRepository.Core!sqlite3_log` at `0x1800188b7`
- `StateRepository.Core!sqlite3_log` at `0x1800188b7`
- `StateRepository.Core!sqlite3_close` at `0x180018871`
- `StateRepository.Core!sqlite3_close` at `0x180018871`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001888d`
- `StateRepository.Core!sqlite3_errmsg` at `0x18001888d`

## string_xrefs

- `0x180018829`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800188e4`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18001890d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Close(StateRepository::Database *this)
{
  int v2; // eax
  unsigned int v3; // edx
  unsigned __int64 i; // rdi
  StateRepository::StatementCacheEntry *v5; // rcx
  int v6; // eax
  unsigned int v7; // edi
  const char *v8; // rax
  unsigned int v9; // eax
  void *v10; // rdx
  unsigned int v11; // r8d
  int v13; // eax
  int v14; // [rsp+20h] [rbp-18h]
  int v15; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)this )
    return 0;
  v2 = StateRepository::Database::LogStatistics(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v2,
      v14);
  if ( *((_BYTE *)this + 64) )
  {
    for ( i = 0; i < *((_QWORD *)this + 7); ++i )
    {
      v5 = *(StateRepository::StatementCacheEntry **)(*((_QWORD *)this + 5) + 8 * i);
      if ( v5 )
        StateRepository::StatementCacheEntry::`scalar deleting destructor'(v5, v3);
    }
  }
  *((_QWORD *)this + 7) = 0;
  v6 = sqlite3_close(*(_QWORD *)this);
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x87AF0000;
  if ( (v7 & 0x80000000) == 0 )
  {
    v13 = StateRepository::Database::Reset(this);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v13,
        v14);
    return 0;
  }
  v8 = (const char *)sqlite3_errmsg(*(_QWORD *)this);
  sqlite3_log(
    v7,
    "[sqlite3_close] #%u Database %llu: %s",
    _InterlockedIncrement(&dword_18004BFF0),
    *((_QWORD *)this + 15),
    v8);
  if ( v7 == -2018574331 )
  {
    v9 = StateRepository::Database::CheckBusyStatements(*(struct sqlite3 **)this, 0, 0);
    wil::details::in1diag3::Log_Hr(retaddr, v10, v11, (const char *)v9, v15);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)v7,
    v15);
  return v7;
}

```

## disassembly

```asm
0x180018804  mov     [rsp+arg_0], rbx
0x180018809  push    rdi
0x18001880a  sub     rsp, 30h
0x18001880e  cmp     qword ptr [rcx], 0
0x180018812  mov     rbx, rcx
0x180018815  jz      loc_180018921
0x18001881b  call    ?LogStatistics@Database@StateRepository@@QEAAJXZ; StateRepository::Database::LogStatistics(void)
0x180018820  test    eax, eax
0x180018822  jns     short loc_18001883D
0x180018824  mov     rcx, [rsp+38h]; this
0x180018829  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018830  mov     r9d, eax; char *
0x180018833  mov     edx, 696h; void *
0x180018838  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001883d  cmp     byte ptr [rbx+40h], 0
0x180018841  jz      short loc_180018866
0x180018843  xor     edi, edi
0x180018845  cmp     [rbx+38h], rdi
0x180018849  jbe     short loc_180018866
0x18001884b  mov     rax, [rbx+28h]
0x18001884f  mov     rcx, [rax+rdi*8]; this
0x180018853  test    rcx, rcx
0x180018856  jz      short loc_18001885D
0x180018858  call    ??_GStatementCacheEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::StatementCacheEntry::`scalar deleting destructor'(uint)
0x18001885d  inc     rdi
0x180018860  cmp     rdi, [rbx+38h]
0x180018864  jb      short loc_18001884B
0x180018866  mov     qword ptr [rbx+38h], 0
0x18001886e  mov     rcx, [rbx]
0x180018871  call    cs:__imp_sqlite3_close
0x180018877  mov     edi, eax
0x180018879  test    eax, eax
0x18001887b  jle     short loc_180018886
0x18001887d  movzx   edi, ax
0x180018880  or      edi, 87AF0000h
0x180018886  test    edi, edi
0x180018888  jns     short loc_1800188FC
0x18001888a  mov     rcx, [rbx]
0x18001888d  call    cs:__imp_sqlite3_errmsg
0x180018893  mov     r9, [rbx+78h]
0x180018897  mov     r8d, 1
0x18001889d  lock xadd cs:dword_18004BFF0, r8d
0x1800188a6  inc     r8d
0x1800188a9  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800188ae  lea     rdx, aSqlite3CloseUD; "[sqlite3_close] #%u Database %llu: %s"
0x1800188b5  mov     ecx, edi
0x1800188b7  call    cs:__imp_sqlite3_log
0x1800188bd  cmp     edi, 87AF0005h
0x1800188c3  jnz     short loc_1800188DF
0x1800188c5  mov     rcx, [rbx]; struct sqlite3 *
0x1800188c8  xor     r8d, r8d; unsigned int *
0x1800188cb  xor     edx, edx; bool
0x1800188cd  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x1800188d2  mov     rcx, [rsp+38h]; this
0x1800188d7  mov     r9d, eax; char *
0x1800188da  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800188df  mov     rcx, [rsp+38h]; this
0x1800188e4  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x1800188eb  mov     r9d, edi; char *
0x1800188ee  mov     edx, 4Eh ; 'N'; void *
0x1800188f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188f8  mov     eax, edi
0x1800188fa  jmp     short loc_180018923
0x1800188fc  mov     rcx, rbx; this
0x1800188ff  call    ?Reset@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Reset(void)
0x180018904  test    eax, eax
0x180018906  jns     short loc_180018921
0x180018908  mov     rcx, [rsp+38h]; this
0x18001890d  lea     r8, aOnecoreBaseApp_45; "onecore\\base\\appmodel\\staterepositor"...
0x180018914  mov     r9d, eax; char *
0x180018917  mov     edx, 51h ; 'Q'; void *
0x18001891c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180018921  xor     eax, eax
0x180018923  mov     rbx, [rsp+38h+arg_0]
0x180018928  add     rsp, 30h
0x18001892c  pop     rdi
0x18001892d  retn
```
