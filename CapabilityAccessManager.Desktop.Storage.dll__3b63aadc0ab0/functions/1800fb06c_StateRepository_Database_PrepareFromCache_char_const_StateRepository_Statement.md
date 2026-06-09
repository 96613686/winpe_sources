# StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)

- ea: `0x1800fb06c`
- end: `0x1800fb12c`
- name: `?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z`
- size: `192`
- prototype: `__int64 __fastcall(struct sqlite3 **this, char *, struct StateRepository::Statement *)`
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x1800f75c0`
- `0x1800f937c`
- `0x1800f9acc`

## callees

- `0x1800eabf4`
- `0x1800f7630`
- `0x1800fb06c`
- `0x1800ff438`
- `0x1800ffd20`
- `0x180100d34`

## string_xrefs

- `0x1800fb08f`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fb0bd`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800fb0fa`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::PrepareFromCache(
        struct sqlite3 **this,
        char *a2,
        struct StateRepository::Statement *a3)
{
  int v7; // eax
  int v8; // eax
  __int64 v9; // r8
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( *this )
  {
    v7 = StateRepository::Statement::Finalize(a3);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x679,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v7);
    if ( StateRepository::StatementCache::Get((StateRepository::StatementCache *)(this + 5), a2, a3) )
    {
      return 0;
    }
    else
    {
      v8 = StateRepository::Statement::Finalize(a3);
      if ( v8 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x127,
          (int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
          (const char *)(unsigned int)v8);
      return StateRepository::Database::dal_prepare_v2(*this, a2, v9, (struct sqlite3_stmt **)a3);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v10);
    return 2147947423LL;
  }
}

```

## disassembly

```asm
0x1800fb06c  mov     [rsp+arg_0], rbx
0x1800fb071  mov     [rsp+arg_8], rsi
0x1800fb076  push    rdi
0x1800fb077  sub     rsp, 30h
0x1800fb07b  cmp     qword ptr [rcx], 0
0x1800fb07f  mov     rbx, r8
0x1800fb082  mov     rsi, rdx
0x1800fb085  mov     rdi, rcx
0x1800fb088  jnz     short loc_1800FB0AC
0x1800fb08a  mov     rcx, [rsp+38h]; this
0x1800fb08f  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fb096  mov     ebx, 8007139Fh
0x1800fb09b  mov     edx, 66Eh; void *
0x1800fb0a0  mov     r9d, ebx; char *
0x1800fb0a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fb0a8  mov     eax, ebx
0x1800fb0aa  jmp     short loc_1800FB11C
0x1800fb0ac  mov     rcx, rbx; this
0x1800fb0af  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800fb0b4  test    eax, eax
0x1800fb0b6  jns     short loc_1800FB0D1
0x1800fb0b8  mov     rcx, [rsp+38h]; this
0x1800fb0bd  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800fb0c4  mov     r9d, eax; char *
0x1800fb0c7  mov     edx, 679h; void *
0x1800fb0cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fb0d1  lea     rcx, [rdi+28h]; this
0x1800fb0d5  mov     r8, rbx; struct StateRepository::Statement *
0x1800fb0d8  mov     rdx, rsi; char *
0x1800fb0db  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x1800fb0e0  test    rax, rax
0x1800fb0e3  jz      short loc_1800FB0E9
0x1800fb0e5  xor     eax, eax
0x1800fb0e7  jmp     short loc_1800FB11C
0x1800fb0e9  mov     rcx, rbx; this
0x1800fb0ec  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800fb0f1  test    eax, eax
0x1800fb0f3  jns     short loc_1800FB10E
0x1800fb0f5  mov     rcx, [rsp+38h]; this
0x1800fb0fa  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\StateRepositor"...
0x1800fb101  mov     r9d, eax; char *
0x1800fb104  mov     edx, 127h; void *
0x1800fb109  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800fb10e  mov     rcx, [rdi]; struct sqlite3 *
0x1800fb111  mov     r9, rbx; struct sqlite3_stmt **
0x1800fb114  mov     rdx, rsi; char *
0x1800fb117  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x1800fb11c  mov     rbx, [rsp+38h+arg_0]
0x1800fb121  mov     rsi, [rsp+38h+arg_8]
0x1800fb126  add     rsp, 30h
0x1800fb12a  pop     rdi
0x1800fb12b  retn
```
