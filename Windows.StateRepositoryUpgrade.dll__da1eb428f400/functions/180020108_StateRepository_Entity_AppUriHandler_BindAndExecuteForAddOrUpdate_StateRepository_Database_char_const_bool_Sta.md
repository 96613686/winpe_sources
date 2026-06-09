# StateRepository::Entity::AppUriHandler::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)

- ea: `0x180020108`
- end: `0x1800203c4`
- name: `?BindAndExecuteForAddOrUpdate@AppUriHandler@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z`
- size: `700`
- prototype: `int __high(struct StateRepository::Database *, const char *, bool, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020664`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b64c`
- `0x18001b6bc`
- `0x18001b750`
- `0x18001b810`
- `0x18001b8d4`
- `0x180020108`
- `0x180029f90`

## string_xrefs

- `0x180020176`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x180020300`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x18002034d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x180020334`: `SELECT EXISTS(SELECT 1 FROM AppUriHandler WHERE _AppUriHandlerID=? AND _WorkId=0 LIMIT 1);`
- `0x180020328`: `SELECT EXISTS(SELECT 1 FROM AppUriHandler WHERE _AppUriHandlerID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppUriHandler::BindAndExecuteForAddOrUpdate(
        __int64 a1,
        StateRepository::Database *a2,
        const char *a3,
        char a4)
{
  int NoRow; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // r14
  int v12; // eax
  const char *v13; // r9
  int v14; // eax
  int v16; // [rsp+20h] [rbp-20h]
  bool *v17; // [rsp+28h] [rbp-18h]
  _QWORD v18[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  __int64 v20; // [rsp+78h] [rbp+38h] BYREF

  LOBYTE(v20) = a4;
  v18[0] = 0;
  NoRow = StateRepository::Database::PrepareFromCache(a2, a3, (struct StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 820;
LABEL_5:
    v9 = (unsigned int)NoRow;
    goto LABEL_6;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 1, *(_QWORD *)(a1 + 8) + 1LL);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 821;
    goto LABEL_5;
  }
  v11 = *((_QWORD *)a2 + 1);
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 2, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 823;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            3,
            *(const unsigned __int16 **)(a1 + 24));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 824;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            4,
            *(const unsigned __int16 **)(a1 + 40));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 825;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 5, *(_QWORD *)(a1 + 56));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 826;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            6,
            *(const unsigned __int16 **)(a1 + 64));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 827;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 7, *(_QWORD *)(a1 + 80));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 828;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            8,
            (const struct StateRepository::Blob *)(a1 + 88));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 829;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 9, *(_QWORD *)a1);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 832;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 10, *(_QWORD *)(a1 + 8));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 833;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)v18, 11, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 834;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 837;
    goto LABEL_5;
  }
  v12 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)v18);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x347,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
      (const char *)(unsigned int)v12,
      v16);
  if ( (unsigned int)StateRepository::Database::GetChanges(a2) == 1 )
  {
    ++*(_QWORD *)(a1 + 8);
    v7 = 0;
    *(_QWORD *)(a1 + 16) = v11;
    goto LABEL_39;
  }
  v13 = *(const char **)a1;
  LOBYTE(v20) = 0;
  v14 = StateRepository::StatementExecution::PrepareAndBindAndExists(
          a2,
          (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM AppUriHandler WHERE _AppUriHandlerID=? AND _Wo"
                                              "rkId=0 LIMIT 1);",
          "SELECT EXISTS(SELECT 1 FROM AppUriHandler WHERE _AppUriHandlerID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);",
          v13,
          (__int64)&v20,
          v17);
  v10 = retaddr;
  v7 = v14;
  if ( v14 >= 0 )
  {
    if ( (_BYTE)v20 )
    {
      v7 = -2140733439;
      v8 = 854;
      v9 = 2154233857LL;
    }
    else
    {
      v7 = -2147023728;
      v8 = 855;
      v9 = 2147943568LL;
    }
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB2,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
    (const char *)(unsigned int)v14,
    v16);
  v9 = v7;
  v8 = 853;
LABEL_6:
  v10 = retaddr;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    v10,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
    (const char *)v9,
    v16);
LABEL_39:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v18);
  return v7;
}

```

## disassembly

```asm
0x180020108  mov     [rsp-18h+arg_0], rbx
0x18002010d  mov     [rsp-18h+arg_8], rsi
0x180020112  mov     byte ptr [rsp-18h+arg_18], r9b
0x180020117  push    rbp
0x180020118  push    rdi
0x180020119  push    r14
0x18002011b  mov     rbp, rsp
0x18002011e  sub     rsp, 40h
0x180020122  mov     rax, r8
0x180020125  mov     [rbp+var_10], 0
0x18002012d  mov     rsi, rdx
0x180020130  lea     r8, [rbp+var_10]; struct StateRepository::Statement *
0x180020134  mov     rdi, rcx
0x180020137  mov     rdx, rax; char *
0x18002013a  mov     rcx, rsi; this
0x18002013d  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180020142  mov     ebx, eax
0x180020144  test    eax, eax
0x180020146  jns     short loc_18002014F
0x180020148  mov     edx, 334h
0x18002014d  jmp     short loc_18002016F
0x18002014f  mov     r8, [rdi+8]
0x180020153  lea     rcx, [rbp+var_10]; this
0x180020157  inc     r8; __int64
0x18002015a  mov     edx, 1; int
0x18002015f  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180020164  mov     ebx, eax
0x180020166  test    eax, eax
0x180020168  jns     short loc_180020187
0x18002016a  mov     edx, 335h; void *
0x18002016f  mov     r9d, eax; char *
0x180020172  mov     rcx, [rbp+18h]; this
0x180020176  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x18002017d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020182  jmp     loc_1800203A6
0x180020187  mov     r14, [rsi+8]
0x18002018b  lea     rcx, [rbp+var_10]; this
0x18002018f  mov     r8, r14; __int64
0x180020192  mov     edx, 2; int
0x180020197  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18002019c  mov     ebx, eax
0x18002019e  test    eax, eax
0x1800201a0  jns     short loc_1800201A9
0x1800201a2  mov     edx, 337h
0x1800201a7  jmp     short loc_18002016F
0x1800201a9  mov     r8, [rdi+18h]; unsigned __int16 *
0x1800201ad  lea     rcx, [rbp+var_10]; this
0x1800201b1  mov     edx, 3; int
0x1800201b6  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x1800201bb  mov     ebx, eax
0x1800201bd  test    eax, eax
0x1800201bf  jns     short loc_1800201C8
0x1800201c1  mov     edx, 338h
0x1800201c6  jmp     short loc_18002016F
0x1800201c8  mov     r8, [rdi+28h]; unsigned __int16 *
0x1800201cc  lea     rcx, [rbp+var_10]; this
0x1800201d0  mov     edx, 4; int
0x1800201d5  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x1800201da  mov     ebx, eax
0x1800201dc  test    eax, eax
0x1800201de  jns     short loc_1800201E7
0x1800201e0  mov     edx, 339h
0x1800201e5  jmp     short loc_18002016F
0x1800201e7  mov     r8, [rdi+38h]; __int64
0x1800201eb  lea     rcx, [rbp+var_10]; this
0x1800201ef  mov     edx, 5; int
0x1800201f4  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800201f9  mov     ebx, eax
0x1800201fb  test    eax, eax
0x1800201fd  jns     short loc_180020209
0x1800201ff  mov     edx, 33Ah
0x180020204  jmp     loc_18002016F
0x180020209  mov     r8, [rdi+40h]; unsigned __int16 *
0x18002020d  lea     rcx, [rbp+var_10]; this
0x180020211  mov     edx, 6; int
0x180020216  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18002021b  mov     ebx, eax
0x18002021d  test    eax, eax
0x18002021f  jns     short loc_18002022B
0x180020221  mov     edx, 33Bh
0x180020226  jmp     loc_18002016F
0x18002022b  mov     r8, [rdi+50h]; __int64
0x18002022f  lea     rcx, [rbp+var_10]; this
0x180020233  mov     edx, 7; int
0x180020238  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18002023d  mov     ebx, eax
0x18002023f  test    eax, eax
0x180020241  jns     short loc_18002024D
0x180020243  mov     edx, 33Ch
0x180020248  jmp     loc_18002016F
0x18002024d  lea     r8, [rdi+58h]; struct StateRepository::Blob *
0x180020251  mov     edx, 8; int
0x180020256  lea     rcx, [rbp+var_10]; this
0x18002025a  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x18002025f  mov     ebx, eax
0x180020261  test    eax, eax
0x180020263  jns     short loc_18002026F
0x180020265  mov     edx, 33Dh
0x18002026a  jmp     loc_18002016F
0x18002026f  mov     r8, [rdi]; __int64
0x180020272  lea     rcx, [rbp+var_10]; this
0x180020276  mov     edx, 9; int
0x18002027b  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180020280  mov     ebx, eax
0x180020282  test    eax, eax
0x180020284  jns     short loc_180020290
0x180020286  mov     edx, 340h
0x18002028b  jmp     loc_18002016F
0x180020290  mov     r8, [rdi+8]; __int64
0x180020294  lea     rcx, [rbp+var_10]; this
0x180020298  mov     edx, 0Ah; int
0x18002029d  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800202a2  mov     ebx, eax
0x1800202a4  test    eax, eax
0x1800202a6  jns     short loc_1800202B2
0x1800202a8  mov     edx, 341h
0x1800202ad  jmp     loc_18002016F
0x1800202b2  mov     r8, r14; __int64
0x1800202b5  lea     rcx, [rbp+var_10]; this
0x1800202b9  mov     edx, 0Bh; int
0x1800202be  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x1800202c3  mov     ebx, eax
0x1800202c5  test    eax, eax
0x1800202c7  jns     short loc_1800202D3
0x1800202c9  mov     edx, 342h
0x1800202ce  jmp     loc_18002016F
0x1800202d3  lea     rcx, [rbp+var_10]; this
0x1800202d7  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x1800202dc  mov     ebx, eax
0x1800202de  test    eax, eax
0x1800202e0  jns     short loc_1800202EC
0x1800202e2  mov     edx, 345h
0x1800202e7  jmp     loc_18002016F
0x1800202ec  lea     rdx, [rbp+var_10]; struct StateRepository::Statement *
0x1800202f0  mov     rcx, rsi; this
0x1800202f3  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800202f8  test    eax, eax
0x1800202fa  jns     short loc_180020314
0x1800202fc  mov     rcx, [rbp+18h]; this
0x180020300  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x180020307  mov     r9d, eax; char *
0x18002030a  mov     edx, 347h; void *
0x18002030f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020314  mov     rcx, rsi; this
0x180020317  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18002031c  cmp     eax, 1
0x18002031f  jz      short loc_18002039C
0x180020321  mov     r9, [rdi]; char *
0x180020324  lea     rax, [rbp+arg_18]
0x180020328  lea     r8, aSelectExistsSe_5; "SELECT EXISTS(SELECT 1 FROM AppUriHandl"...
0x18002032f  mov     [rsp+40h+var_20], rax; int
0x180020334  lea     rdx, aSelectExistsSe; "SELECT EXISTS(SELECT 1 FROM AppUriHandl"...
0x18002033b  mov     byte ptr [rbp+arg_18], 0
0x18002033f  mov     rcx, rsi; this
0x180020342  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180020347  mov     rcx, [rbp+18h]; this
0x18002034b  mov     ebx, eax
0x18002034d  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x180020354  test    eax, eax
0x180020356  jns     short loc_180020372
0x180020358  mov     r9d, eax; char *
0x18002035b  mov     edx, 0B2h; void *
0x180020360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020365  mov     r9d, ebx
0x180020368  mov     edx, 355h
0x18002036d  jmp     loc_180020172
0x180020372  cmp     byte ptr [rbp+arg_18], 0
0x180020376  jz      short loc_18002038A
0x180020378  mov     ebx, 80670001h
0x18002037d  mov     edx, 356h
0x180020382  mov     r9d, ebx
0x180020385  jmp     loc_18002017D
0x18002038a  mov     ebx, 80070490h
0x18002038f  mov     edx, 357h
0x180020394  mov     r9d, ebx
0x180020397  jmp     loc_18002017D
0x18002039c  inc     qword ptr [rdi+8]
0x1800203a0  xor     ebx, ebx
0x1800203a2  mov     [rdi+10h], r14
0x1800203a6  lea     rcx, [rbp+var_10]; this
0x1800203aa  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800203af  mov     rsi, [rsp+40h+arg_8]
0x1800203b4  mov     eax, ebx
0x1800203b6  mov     rbx, [rsp+40h+arg_0]
0x1800203bb  add     rsp, 40h
0x1800203bf  pop     r14
0x1800203c1  pop     rdi
0x1800203c2  pop     rbp
0x1800203c3  retn
```
