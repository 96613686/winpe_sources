# StateRepository::Database::GetPragma(char const *,int *)

- ea: `0x1800f9acc`
- end: `0x1800f9c28`
- name: `?GetPragma@Database@StateRepository@@QEAAJPEBDPEAH@Z`
- size: `348`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this, const char *, int *)`
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800f28f4`
- `0x1800f2a54`

## callees

- `0x180003060`
- `0x1800eabf4`
- `0x1800edb2c`
- `0x1800f7630`
- `0x1800f9acc`
- `0x1800fb06c`
- `0x1800fc60c`
- `0x1800ffb60`
- `0x1800ffcc4`
- `0x1800ffe44`
- `0x180100908`

## string_xrefs

- `0x1800f9afe`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9b98`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9bd1`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f9c13`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::GetPragma(StateRepository::Database *this, const char *a2, int *a3)
{
  unsigned int v5; // ebx
  int v7; // eax
  int Row; // eax
  __int64 v9; // rdx
  int v10; // edx
  int v11; // eax
  int v12; // [rsp+20h] [rbp-49h] BYREF
  struct sqlite3_stmt *v13; // [rsp+28h] [rbp-41h] BYREF
  char v14[112]; // [rsp+30h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( !*(_QWORD *)this )
  {
    v5 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      v12);
    return v5;
  }
  v7 = StringCchPrintfA(v14, 0x64u, "PRAGMA %s;", a2);
  if ( v7 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x5C9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v7,
      v12);
  v13 = 0;
  Row = StateRepository::Database::PrepareFromCache(this, v14, (struct StateRepository::Statement *)&v13);
  v5 = Row;
  if ( Row < 0 )
  {
    v9 = 1483;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)Row,
      v12);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v13);
    return v5;
  }
  Row = StateRepository::Statement::FetchRow(&v13, (bool *)&v12);
  v5 = Row;
  if ( Row < 0 )
  {
    v9 = 1486;
    goto LABEL_11;
  }
  Row = StateRepository::Statement::GetColumnInt32((StateRepository::Statement *)&v13, v10, a3);
  v5 = Row;
  if ( Row < 0 )
  {
    v9 = 1489;
    goto LABEL_11;
  }
  if ( v13 )
  {
    v11 = StateRepository::StatementCache::Add(
            (StateRepository::Database *)((char *)this + 40),
            (struct StateRepository::Statement *)&v13);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5D3,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v11);
  }
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v13);
  return 0;
}

```

## disassembly

```asm
0x1800f9acc  mov     [rsp-8+arg_18], rbx
0x1800f9ad1  push    rbp
0x1800f9ad2  push    rsi
0x1800f9ad3  push    rdi
0x1800f9ad4  lea     rbp, [rsp-47h]
0x1800f9ad9  sub     rsp, 0B0h
0x1800f9ae0  mov     rax, cs:__security_cookie
0x1800f9ae7  xor     rax, rsp
0x1800f9aea  mov     [rbp+57h+var_20], rax
0x1800f9aee  cmp     qword ptr [rcx], 0
0x1800f9af2  mov     rsi, r8
0x1800f9af5  mov     rdi, rcx
0x1800f9af8  jnz     short loc_1800F9B1E
0x1800f9afa  mov     rcx, [rbp+5Fh]; this
0x1800f9afe  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9b05  mov     ebx, 8007139Fh
0x1800f9b0a  mov     edx, 5C5h; void *
0x1800f9b0f  mov     r9d, ebx; char *
0x1800f9b12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9b17  mov     eax, ebx
0x1800f9b19  jmp     loc_1800F9BF0
0x1800f9b1e  mov     r9, rdx
0x1800f9b21  lea     r8, aPragmaS; "PRAGMA %s;"
0x1800f9b28  mov     edx, 64h ; 'd'; unsigned __int64
0x1800f9b2d  lea     rcx, [rbp+57h+var_90]; char *
0x1800f9b31  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800f9b36  test    eax, eax
0x1800f9b38  js      loc_1800F9C0F
0x1800f9b3e  lea     r8, [rbp+57h+var_98]; struct StateRepository::Statement *
0x1800f9b42  mov     [rbp+57h+var_98], 0
0x1800f9b4a  lea     rdx, [rbp+57h+var_90]; char *
0x1800f9b4e  mov     rcx, rdi; this
0x1800f9b51  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x1800f9b56  mov     ebx, eax
0x1800f9b58  test    eax, eax
0x1800f9b5a  jns     short loc_1800F9B63
0x1800f9b5c  mov     edx, 5CBh
0x1800f9b61  jmp     short loc_1800F9B94
0x1800f9b63  lea     rdx, [rbp+57h+var_A0]; bool *
0x1800f9b67  lea     rcx, [rbp+57h+var_98]; this
0x1800f9b6b  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800f9b70  mov     ebx, eax
0x1800f9b72  test    eax, eax
0x1800f9b74  jns     short loc_1800F9B7D
0x1800f9b76  mov     edx, 5CEh
0x1800f9b7b  jmp     short loc_1800F9B94
0x1800f9b7d  mov     r8, rsi; int *
0x1800f9b80  lea     rcx, [rbp+57h+var_98]; this
0x1800f9b84  call    ?GetColumnInt32@Statement@StateRepository@@QEBAJHPEAH@Z; StateRepository::Statement::GetColumnInt32(int,int *)
0x1800f9b89  mov     ebx, eax
0x1800f9b8b  test    eax, eax
0x1800f9b8d  jns     short loc_1800F9BB5
0x1800f9b8f  mov     edx, 5D1h; void *
0x1800f9b94  mov     rcx, [rbp+5Fh]; this
0x1800f9b98  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9b9f  mov     r9d, eax; char *
0x1800f9ba2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f9ba7  lea     rcx, [rbp+57h+var_98]; this
0x1800f9bab  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f9bb0  jmp     loc_1800F9B17
0x1800f9bb5  cmp     [rbp+57h+var_98], 0
0x1800f9bba  jz      short loc_1800F9BE5
0x1800f9bbc  lea     rcx, [rdi+28h]; this
0x1800f9bc0  lea     rdx, [rbp+57h+var_98]; struct StateRepository::Statement *
0x1800f9bc4  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800f9bc9  test    eax, eax
0x1800f9bcb  jns     short loc_1800F9BE5
0x1800f9bcd  mov     rcx, [rbp+5Fh]; this
0x1800f9bd1  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9bd8  mov     r9d, eax; char *
0x1800f9bdb  mov     edx, 5D3h; void *
0x1800f9be0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9be5  lea     rcx, [rbp+57h+var_98]; this
0x1800f9be9  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f9bee  xor     eax, eax
0x1800f9bf0  mov     rcx, [rbp+57h+var_20]
0x1800f9bf4  xor     rcx, rsp; StackCookie
0x1800f9bf7  call    __security_check_cookie
0x1800f9bfc  mov     rbx, [rsp+0C0h+arg_18]
0x1800f9c04  add     rsp, 0B0h
0x1800f9c0b  pop     rdi
0x1800f9c0c  pop     rsi
0x1800f9c0d  pop     rbp
0x1800f9c0e  retn
0x1800f9c0f  mov     rcx, [rbp+5Fh]; this
0x1800f9c13  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9c1a  mov     r9d, eax; char *
0x1800f9c1d  mov     edx, 5C9h; void *
0x1800f9c22  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
