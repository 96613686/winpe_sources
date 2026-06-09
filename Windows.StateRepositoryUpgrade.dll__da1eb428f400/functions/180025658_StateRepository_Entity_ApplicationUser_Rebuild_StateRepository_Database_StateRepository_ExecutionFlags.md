# StateRepository::Entity::ApplicationUser::Rebuild(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x180025658`
- end: `0x1800257dc`
- name: `?Rebuild@ApplicationUser@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013980`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018f78`
- `0x180019614`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001b5a8`
- `0x18001b8d4`
- `0x180025658`

## string_xrefs

- `0x18002567b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationuser-custom.cpp`
- `0x1800256f6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationuser-custom.cpp`
- `0x18002571f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationuser-custom.cpp`
- `0x180025766`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationuser-custom.cpp`
- `0x1800257aa`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationuser-custom.cpp`
- `0x1800256c2`: `DELETE FROM ApplicationUser;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationUser::Rebuild(StateRepository::Database *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  int NoRow; // eax
  __int64 v5; // rdx
  StateRepository::Statement *v6; // rcx
  int v7; // eax
  int v8; // eax
  __int64 v9; // rdx
  int v10; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v14; // [rsp+40h] [rbp+20h] BYREF
  __int64 v15; // [rsp+50h] [rbp+30h] BYREF
  char v16; // [rsp+58h] [rbp+38h] BYREF

  if ( !*((_QWORD *)a1 + 1) )
  {
    if ( StateRepository::Database::IsInAutoCommitMode(a1) )
    {
      v2 = -2140733429;
      v3 = 115;
      goto LABEL_3;
    }
    StateRepository::DatabaseTriggers::Disable(&v16, a1, 16);
    v15 = 0;
    NoRow = StateRepository::Database::PrepareFromCache(
              a1,
              "DELETE FROM ApplicationUser;",
              (struct StateRepository::Statement *)&v15);
    v2 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v15);
      v2 = NoRow;
      if ( NoRow >= 0 )
      {
        v7 = StateRepository::Database::AddToCache(a1, (struct StateRepository::Statement *)&v15);
        if ( v7 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x80,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationuser-custom.cpp",
            (const char *)(unsigned int)v7,
            savedregs);
        StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
        v14 = 0;
        v8 = StateRepository::Database::PrepareFromCache(
               a1,
               "INSERT INTO ApplicationUser (_Revision, _WorkId, User, ApplicationIdentity, Application, Package, Package"
               "User)SELECT 1, 0, pu.User, ai._ApplicationIdentityID, a._ApplicationID, pu.Package, pu._PackageUserID FRO"
               "M PackageUser AS pu INNER JOIN Application AS a ON a.Package=pu.Package INNER JOIN ApplicationIdentity AS"
               " ai ON ai.ApplicationUserModelId=a.ApplicationUserModelId WHERE pu._WorkId=0;",
               (struct StateRepository::Statement *)&v14);
        v2 = v8;
        if ( v8 >= 0 )
        {
          v8 = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v14);
          v2 = v8;
          if ( v8 >= 0 )
          {
            v10 = StateRepository::Database::AddToCache(a1, (struct StateRepository::Statement *)&v14);
            if ( v10 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x90,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationuser-custom.cpp",
                (const char *)(unsigned int)v10,
                savedregs);
            StateRepository::Statement::~Statement((StateRepository::Statement *)&v14);
            v2 = 0;
            goto LABEL_22;
          }
          v9 = 142;
        }
        else
        {
          v9 = 140;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationuser-custom.cpp",
          (const char *)(unsigned int)v8,
          savedregs);
        v6 = (StateRepository::Statement *)&v14;
LABEL_16:
        StateRepository::Statement::~Statement(v6);
LABEL_22:
        StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v16);
        return v2;
      }
      v5 = 126;
    }
    else
    {
      v5 = 124;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationuser-custom.cpp",
      (const char *)(unsigned int)NoRow,
      savedregs);
    v6 = (StateRepository::Statement *)&v15;
    goto LABEL_16;
  }
  v2 = -2147019873;
  v3 = 114;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v3,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationuser-custom.cpp",
    (const char *)v2,
    savedregs);
  return v2;
}

```

## disassembly

```asm
0x180025658  push    rbp
0x18002565a  push    rbx
0x18002565b  push    rdi; int
0x18002565c  mov     rbp, rsp
0x18002565f  sub     rsp, 20h
0x180025663  cmp     qword ptr [rcx+8], 0
0x180025668  mov     rdi, rcx
0x18002566b  jz      short loc_18002568F
0x18002566d  mov     ebx, 8007139Fh
0x180025672  mov     edx, 72h ; 'r'; void *
0x180025677  mov     rcx, [rbp+18h]; this
0x18002567b  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180025682  mov     r9d, ebx; char *
0x180025685  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002568a  jmp     loc_1800257D2
0x18002568f  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180025694  test    al, al
0x180025696  jz      short loc_1800256A4
0x180025698  mov     ebx, 8067000Bh
0x18002569d  mov     edx, 73h ; 's'
0x1800256a2  jmp     short loc_180025677
0x1800256a4  mov     r8d, 10h
0x1800256aa  lea     rcx, [rbp+arg_18]
0x1800256ae  mov     rdx, rdi
0x1800256b1  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x1800256b6  lea     r8, [rbp+arg_10]; struct StateRepository::Statement *
0x1800256ba  mov     [rbp+arg_10], 0
0x1800256c2  lea     rdx, aDeleteFromAppl; "DELETE FROM ApplicationUser;"
0x1800256c9  mov     rcx, rdi; this
0x1800256cc  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x1800256d1  mov     ebx, eax
0x1800256d3  test    eax, eax
0x1800256d5  jns     short loc_1800256DE
0x1800256d7  mov     edx, 7Ch ; '|'
0x1800256dc  jmp     short loc_1800256F2
0x1800256de  lea     rcx, [rbp+arg_10]; this
0x1800256e2  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x1800256e7  mov     ebx, eax
0x1800256e9  test    eax, eax
0x1800256eb  jns     short loc_18002570B
0x1800256ed  mov     edx, 7Eh ; '~'; void *
0x1800256f2  mov     rcx, [rbp+18h]; this
0x1800256f6  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x1800256fd  mov     r9d, eax; char *
0x180025700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025705  lea     rcx, [rbp+arg_10]
0x180025709  jmp     short loc_180025779
0x18002570b  lea     rdx, [rbp+arg_10]; struct StateRepository::Statement *
0x18002570f  mov     rcx, rdi; this
0x180025712  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180025717  test    eax, eax
0x180025719  jns     short loc_180025733
0x18002571b  mov     rcx, [rbp+18h]; this
0x18002571f  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x180025726  mov     r9d, eax; char *
0x180025729  mov     edx, 80h; void *
0x18002572e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025733  lea     rcx, [rbp+arg_10]; this
0x180025737  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18002573c  lea     r8, [rbp+arg_0]; struct StateRepository::Statement *
0x180025740  mov     [rbp+arg_0], 0
0x180025748  lea     rdx, aInsertIntoAppl; "INSERT INTO ApplicationUser (_Revision,"...
0x18002574f  mov     rcx, rdi; this
0x180025752  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180025757  mov     ebx, eax
0x180025759  test    eax, eax
0x18002575b  jns     short loc_180025780
0x18002575d  mov     edx, 8Ch; void *
0x180025762  mov     rcx, [rbp+18h]; this
0x180025766  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x18002576d  mov     r9d, eax; char *
0x180025770  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025775  lea     rcx, [rbp+arg_0]; this
0x180025779  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18002577e  jmp     short loc_1800257C9
0x180025780  lea     rcx, [rbp+arg_0]; this
0x180025784  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180025789  mov     ebx, eax
0x18002578b  test    eax, eax
0x18002578d  jns     short loc_180025796
0x18002578f  mov     edx, 8Eh
0x180025794  jmp     short loc_180025762
0x180025796  lea     rdx, [rbp+arg_0]; struct StateRepository::Statement *
0x18002579a  mov     rcx, rdi; this
0x18002579d  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800257a2  test    eax, eax
0x1800257a4  jns     short loc_1800257BE
0x1800257a6  mov     rcx, [rbp+18h]; this
0x1800257aa  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\staterepositor"...
0x1800257b1  mov     r9d, eax; char *
0x1800257b4  mov     edx, 90h; void *
0x1800257b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800257be  lea     rcx, [rbp+arg_0]; this
0x1800257c2  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800257c7  xor     ebx, ebx
0x1800257c9  lea     rcx, [rbp+arg_18]; this
0x1800257cd  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800257d2  mov     eax, ebx
0x1800257d4  add     rsp, 20h
0x1800257d8  pop     rdi
0x1800257d9  pop     rbx
0x1800257da  pop     rbp
0x1800257db  retn
```
