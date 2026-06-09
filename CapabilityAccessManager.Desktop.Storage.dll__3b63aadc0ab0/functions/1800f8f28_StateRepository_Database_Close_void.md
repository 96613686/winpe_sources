# StateRepository::Database::Close(void)

- ea: `0x1800f8f28`
- end: `0x1800f901e`
- name: `?Close@Database@StateRepository@@QEAAJXZ`
- size: `246`
- prototype: `__int64 __fastcall(StateRepository::Database *__hidden this)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800f875c`
- `0x1800fa944`
- `0x1801019b8`

## callees

- `0x180006a00`
- `0x180016970`
- `0x180022a30`
- `0x1800eabf4`
- `0x1800f7630`
- `0x1800f89f4`
- `0x1800f8e98`
- `0x1800f8f28`
- `0x1800fa4f4`
- `0x1800fb768`

## string_xrefs

- `0x1800f8f4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f8fd4`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800f8ffd`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Database::Close(StateRepository::Database *this)
{
  int v2; // eax
  int v3; // eax
  unsigned int v4; // ebx
  const char *v5; // rax
  unsigned int v6; // eax
  void *v7; // rdx
  unsigned int v8; // r8d
  int v10; // eax
  int v11; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)this )
    return 0;
  v2 = StateRepository::Database::ClearCache(this);
  if ( v2 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x40,
      (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)(unsigned int)v2);
  v3 = sqlite3_close(*(_QWORD *)this);
  v4 = v3;
  if ( v3 > 0 )
    v4 = (unsigned __int16)v3 | 0x87AF0000;
  if ( (v4 & 0x80000000) == 0 )
  {
    v10 = StateRepository::Database::Reset(this);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x51,
        (int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)(unsigned int)v10);
    return 0;
  }
  v5 = (const char *)sqlite3_errmsg(*(_QWORD *)this);
  sqlite3_log(
    v4,
    "[sqlite3_close] #%u Database %llu: %s",
    _InterlockedIncrement(&dword_180140410),
    *((_QWORD *)this + 15),
    v5);
  if ( v4 == -2018574331 )
  {
    v6 = StateRepository::Database::CheckBusyStatements(*(struct sqlite3 **)this, 0, 0);
    wil::details::in1diag3::Log_Hr(retaddr, v7, v8, (const char *)v6, v11);
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)v4,
    v11);
  return v4;
}

```

## disassembly

```asm
0x1800f8f28  mov     [rsp+arg_0], rbx
0x1800f8f2d  push    rdi
0x1800f8f2e  sub     rsp, 30h
0x1800f8f32  cmp     qword ptr [rcx], 0
0x1800f8f36  mov     rdi, rcx
0x1800f8f39  jz      loc_1800F9011
0x1800f8f3f  call    ?ClearCache@Database@StateRepository@@QEAAJXZ; StateRepository::Database::ClearCache(void)
0x1800f8f44  test    eax, eax
0x1800f8f46  jns     short loc_1800F8F61
0x1800f8f48  mov     rcx, [rsp+38h]; this
0x1800f8f4d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8f54  mov     r9d, eax; char *
0x1800f8f57  mov     edx, 40h ; '@'; void *
0x1800f8f5c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f8f61  mov     rcx, [rdi]
0x1800f8f64  call    sqlite3_close
0x1800f8f69  mov     ebx, eax
0x1800f8f6b  test    eax, eax
0x1800f8f6d  jle     short loc_1800F8F78
0x1800f8f6f  movzx   ebx, ax
0x1800f8f72  or      ebx, 87AF0000h
0x1800f8f78  test    ebx, ebx
0x1800f8f7a  jns     short loc_1800F8FEC
0x1800f8f7c  mov     rcx, [rdi]
0x1800f8f7f  call    sqlite3_errmsg
0x1800f8f84  mov     r9, [rdi+78h]
0x1800f8f88  mov     r8d, 1
0x1800f8f8e  lock xadd cs:dword_180140410, r8d
0x1800f8f97  inc     r8d
0x1800f8f9a  mov     qword ptr [rsp+38h+var_18], rax; int
0x1800f8f9f  lea     rdx, aSqlite3CloseUD; "[sqlite3_close] #%u Database %llu: %s"
0x1800f8fa6  mov     ecx, ebx
0x1800f8fa8  call    sqlite3_log
0x1800f8fad  cmp     ebx, 87AF0005h
0x1800f8fb3  jnz     short loc_1800F8FCF
0x1800f8fb5  mov     rcx, [rdi]; struct sqlite3 *
0x1800f8fb8  xor     r8d, r8d; unsigned int *
0x1800f8fbb  xor     edx, edx; bool
0x1800f8fbd  call    ?CheckBusyStatements@Database@StateRepository@@CAJPEAUsqlite3@@_NPEAI@Z; StateRepository::Database::CheckBusyStatements(sqlite3 *,bool,uint *)
0x1800f8fc2  mov     rcx, [rsp+38h]; this
0x1800f8fc7  mov     r9d, eax; char *
0x1800f8fca  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800f8fcf  mov     rcx, [rsp+38h]; this
0x1800f8fd4  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f8fdb  mov     r9d, ebx; char *
0x1800f8fde  mov     edx, 4Eh ; 'N'; void *
0x1800f8fe3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f8fe8  mov     eax, ebx
0x1800f8fea  jmp     short loc_1800F9013
0x1800f8fec  mov     rcx, rdi; this
0x1800f8fef  call    ?Reset@Database@StateRepository@@QEAAJXZ; StateRepository::Database::Reset(void)
0x1800f8ff4  test    eax, eax
0x1800f8ff6  jns     short loc_1800F9011
0x1800f8ff8  mov     rcx, [rsp+38h]; this
0x1800f8ffd  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\staterepositor"...
0x1800f9004  mov     r9d, eax; char *
0x1800f9007  mov     edx, 51h ; 'Q'; void *
0x1800f900c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800f9011  xor     eax, eax
0x1800f9013  mov     rbx, [rsp+38h+arg_0]
0x1800f9018  add     rsp, 30h
0x1800f901c  pop     rdi
0x1800f901d  retn
```
