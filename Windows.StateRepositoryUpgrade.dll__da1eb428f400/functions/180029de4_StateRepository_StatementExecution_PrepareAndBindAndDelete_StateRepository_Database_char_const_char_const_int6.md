# StateRepository::StatementExecution::PrepareAndBindAndDelete(StateRepository::Database &,char const *,char const *,__int64)

- ea: `0x180029de4`
- end: `0x180029ee5`
- name: `?PrepareAndBindAndDelete@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_J@Z`
- size: `257`
- prototype: `__int64 __fastcall(StateRepository::StatementExecution *__hidden this, struct StateRepository::Database *, const char *, const char *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x180025840`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b64c`
- `0x18001b810`
- `0x18001b8d4`
- `0x180029de4`

## string_xrefs

- `0x180029dfd`: `DELETE FROM PackageAppInstaller WHERE _PackageAppInstallerID=? AND _WorkId=0;`
- `0x180029e04`: `DELETE FROM PackageAppInstaller WHERE _PackageAppInstallerID=? AND (_WorkId=0 OR _WorkId=?);`
- `0x180029e55`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180029eb3`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::StatementExecution::PrepareAndBindAndDelete(
        StateRepository::StatementExecution *this,
        struct StateRepository::Database *a2,
        const char *a3,
        const char *a4)
{
  bool v4; // zf
  const char *v5; // rdx
  int NoRow; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v11; // eax
  int v13; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  const char *v15; // [rsp+40h] [rbp+18h] BYREF

  v15 = a3;
  v4 = *((_QWORD *)this + 1) == 0;
  v5 = "DELETE FROM PackageAppInstaller WHERE _PackageAppInstallerID=? AND (_WorkId=0 OR _WorkId=?);";
  v15 = 0;
  if ( v4 )
    v5 = "DELETE FROM PackageAppInstaller WHERE _PackageAppInstallerID=? AND _WorkId=0;";
  NoRow = StateRepository::Database::PrepareFromCache(this, v5, (struct StateRepository::Statement *)&v15);
  v9 = NoRow;
  if ( NoRow < 0 )
  {
    v10 = 115;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)NoRow,
      v13);
    goto LABEL_15;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 1, (__int64)a4);
  v9 = NoRow;
  if ( NoRow < 0 )
  {
    v10 = 116;
    goto LABEL_7;
  }
  NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)&v15, 2, *((_QWORD *)this + 1));
  v9 = NoRow;
  if ( NoRow < 0 )
  {
    v10 = 119;
    goto LABEL_7;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v15);
  v9 = NoRow;
  if ( NoRow < 0 )
  {
    v10 = 122;
    goto LABEL_7;
  }
  v11 = StateRepository::Database::AddToCache(this, (struct StateRepository::Statement *)&v15);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
      (const char *)(unsigned int)v11,
      v13);
  v9 = 0;
LABEL_15:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
  return v9;
}

```

## disassembly

```asm
0x180029de4  mov     r11, rsp
0x180029de7  mov     [r11+8], rbx
0x180029deb  mov     [r11+10h], rsi
0x180029def  mov     [r11+18h], r8
0x180029df3  push    rdi; int
0x180029df4  sub     rsp, 20h
0x180029df8  cmp     qword ptr [rcx+8], 0
0x180029dfd  lea     rax, aDeleteFromPack; "DELETE FROM PackageAppInstaller WHERE _"...
0x180029e04  lea     rdx, aDeleteFromPack_0; "DELETE FROM PackageAppInstaller WHERE _"...
0x180029e0b  mov     qword ptr [r11+18h], 0
0x180029e13  cmovz   rdx, rax; char *
0x180029e17  lea     r8, [r11+18h]; struct StateRepository::Statement *
0x180029e1b  mov     rsi, r9
0x180029e1e  mov     rdi, rcx
0x180029e21  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180029e26  mov     ebx, eax
0x180029e28  test    eax, eax
0x180029e2a  jns     short loc_180029E33
0x180029e2c  mov     edx, 73h ; 's'
0x180029e31  jmp     short loc_180029E50
0x180029e33  mov     r8, rsi; __int64
0x180029e36  lea     rcx, [rsp+28h+arg_10]; this
0x180029e3b  mov     edx, 1; int
0x180029e40  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180029e45  mov     ebx, eax
0x180029e47  test    eax, eax
0x180029e49  jns     short loc_180029E66
0x180029e4b  mov     edx, 74h ; 't'; void *
0x180029e50  mov     rcx, [rsp+28h]; this
0x180029e55  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\staterepositor"...
0x180029e5c  mov     r9d, eax; char *
0x180029e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029e64  jmp     short loc_180029EC9
0x180029e66  mov     r8, [rdi+8]; __int64
0x180029e6a  lea     rcx, [rsp+28h+arg_10]; this
0x180029e6f  mov     edx, 2; int
0x180029e74  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x180029e79  mov     ebx, eax
0x180029e7b  test    eax, eax
0x180029e7d  jns     short loc_180029E86
0x180029e7f  mov     edx, 77h ; 'w'
0x180029e84  jmp     short loc_180029E50
0x180029e86  lea     rcx, [rsp+28h+arg_10]; this
0x180029e8b  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180029e90  mov     ebx, eax
0x180029e92  test    eax, eax
0x180029e94  jns     short loc_180029E9D
0x180029e96  mov     edx, 7Ah ; 'z'
0x180029e9b  jmp     short loc_180029E50
0x180029e9d  lea     rdx, [rsp+28h+arg_10]; struct StateRepository::Statement *
0x180029ea2  mov     rcx, rdi; this
0x180029ea5  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180029eaa  test    eax, eax
0x180029eac  jns     short loc_180029EC7
0x180029eae  mov     rcx, [rsp+28h]; this
0x180029eb3  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\staterepositor"...
0x180029eba  mov     r9d, eax; char *
0x180029ebd  mov     edx, 7Ch ; '|'; void *
0x180029ec2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180029ec7  xor     ebx, ebx
0x180029ec9  lea     rcx, [rsp+28h+arg_10]; this
0x180029ece  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180029ed3  mov     rsi, [rsp+28h+arg_8]
0x180029ed8  mov     eax, ebx
0x180029eda  mov     rbx, [rsp+28h+arg_0]
0x180029edf  add     rsp, 20h
0x180029ee3  pop     rdi
0x180029ee4  retn
```
