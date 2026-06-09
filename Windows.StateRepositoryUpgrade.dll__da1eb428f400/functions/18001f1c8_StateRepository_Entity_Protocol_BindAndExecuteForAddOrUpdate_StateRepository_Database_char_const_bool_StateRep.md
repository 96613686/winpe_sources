# StateRepository::Entity::Protocol::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)

- ea: `0x18001f1c8`
- end: `0x18001f484`
- name: `?BindAndExecuteForAddOrUpdate@Protocol@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z`
- size: `700`
- prototype: `int __high(struct StateRepository::Database *, const char *, bool, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f724`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b5dc`
- `0x18001b64c`
- `0x18001b6bc`
- `0x18001b750`
- `0x18001b810`
- `0x18001b8d4`
- `0x18001f1c8`
- `0x180029f90`

## string_xrefs

- `0x18001f236`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f3c0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f40d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f3f4`: `SELECT EXISTS(SELECT 1 FROM Protocol WHERE _ProtocolID=? AND _WorkId=0 LIMIT 1);`
- `0x18001f3e8`: `SELECT EXISTS(SELECT 1 FROM Protocol WHERE _ProtocolID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Protocol::BindAndExecuteForAddOrUpdate(
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
    v8 = 947;
LABEL_5:
    v9 = (unsigned int)NoRow;
    goto LABEL_6;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 1, *(_QWORD *)(a1 + 8) + 1LL);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 948;
    goto LABEL_5;
  }
  v11 = *((_QWORD *)a2 + 1);
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 2, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 950;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            3,
            *(const unsigned __int16 **)(a1 + 24));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 951;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 4, *(_DWORD *)(a1 + 40));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 952;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 5, *(_QWORD *)(a1 + 48));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 953;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 6, *(_DWORD *)(a1 + 56));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 954;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            7,
            *(const unsigned __int16 **)(a1 + 64));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 955;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            8,
            (const struct StateRepository::Blob *)(a1 + 80));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 956;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 9, *(_QWORD *)a1);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 959;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 10, *(_QWORD *)(a1 + 8));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 960;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)v18, 11, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 961;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 964;
    goto LABEL_5;
  }
  v12 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)v18);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x3C6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
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
          (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM Protocol WHERE _ProtocolID=? AND _WorkId=0 LIMIT 1);",
          "SELECT EXISTS(SELECT 1 FROM Protocol WHERE _ProtocolID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);",
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
      v8 = 981;
      v9 = 2154233857LL;
    }
    else
    {
      v7 = -2147023728;
      v8 = 982;
      v9 = 2147943568LL;
    }
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xA7,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
    (const char *)(unsigned int)v14,
    v16);
  v9 = v7;
  v8 = 980;
LABEL_6:
  v10 = retaddr;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    v10,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
    (const char *)v9,
    v16);
LABEL_39:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v18);
  return v7;
}

```

## disassembly

```asm
0x18001f1c8  mov     [rsp-18h+arg_0], rbx
0x18001f1cd  mov     [rsp-18h+arg_8], rsi
0x18001f1d2  mov     byte ptr [rsp-18h+arg_18], r9b
0x18001f1d7  push    rbp
0x18001f1d8  push    rdi
0x18001f1d9  push    r14
0x18001f1db  mov     rbp, rsp
0x18001f1de  sub     rsp, 40h
0x18001f1e2  mov     rax, r8
0x18001f1e5  mov     [rbp+var_10], 0
0x18001f1ed  mov     rsi, rdx
0x18001f1f0  lea     r8, [rbp+var_10]; struct StateRepository::Statement *
0x18001f1f4  mov     rdi, rcx
0x18001f1f7  mov     rdx, rax; char *
0x18001f1fa  mov     rcx, rsi; this
0x18001f1fd  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001f202  mov     ebx, eax
0x18001f204  test    eax, eax
0x18001f206  jns     short loc_18001F20F
0x18001f208  mov     edx, 3B3h
0x18001f20d  jmp     short loc_18001F22F
0x18001f20f  mov     r8, [rdi+8]
0x18001f213  lea     rcx, [rbp+var_10]; this
0x18001f217  inc     r8; __int64
0x18001f21a  mov     edx, 1; int
0x18001f21f  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001f224  mov     ebx, eax
0x18001f226  test    eax, eax
0x18001f228  jns     short loc_18001F247
0x18001f22a  mov     edx, 3B4h; void *
0x18001f22f  mov     r9d, eax; char *
0x18001f232  mov     rcx, [rbp+18h]; this
0x18001f236  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f23d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f242  jmp     loc_18001F466
0x18001f247  mov     r14, [rsi+8]
0x18001f24b  lea     rcx, [rbp+var_10]; this
0x18001f24f  mov     r8, r14; __int64
0x18001f252  mov     edx, 2; int
0x18001f257  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001f25c  mov     ebx, eax
0x18001f25e  test    eax, eax
0x18001f260  jns     short loc_18001F269
0x18001f262  mov     edx, 3B6h
0x18001f267  jmp     short loc_18001F22F
0x18001f269  mov     r8, [rdi+18h]; unsigned __int16 *
0x18001f26d  lea     rcx, [rbp+var_10]; this
0x18001f271  mov     edx, 3; int
0x18001f276  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001f27b  mov     ebx, eax
0x18001f27d  test    eax, eax
0x18001f27f  jns     short loc_18001F288
0x18001f281  mov     edx, 3B7h
0x18001f286  jmp     short loc_18001F22F
0x18001f288  mov     r8d, [rdi+28h]; int
0x18001f28c  lea     rcx, [rbp+var_10]; this
0x18001f290  mov     edx, 4; int
0x18001f295  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001f29a  mov     ebx, eax
0x18001f29c  test    eax, eax
0x18001f29e  jns     short loc_18001F2A7
0x18001f2a0  mov     edx, 3B8h
0x18001f2a5  jmp     short loc_18001F22F
0x18001f2a7  mov     r8, [rdi+30h]; __int64
0x18001f2ab  lea     rcx, [rbp+var_10]; this
0x18001f2af  mov     edx, 5; int
0x18001f2b4  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001f2b9  mov     ebx, eax
0x18001f2bb  test    eax, eax
0x18001f2bd  jns     short loc_18001F2C9
0x18001f2bf  mov     edx, 3B9h
0x18001f2c4  jmp     loc_18001F22F
0x18001f2c9  mov     r8d, [rdi+38h]; int
0x18001f2cd  lea     rcx, [rbp+var_10]; this
0x18001f2d1  mov     edx, 6; int
0x18001f2d6  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001f2db  mov     ebx, eax
0x18001f2dd  test    eax, eax
0x18001f2df  jns     short loc_18001F2EB
0x18001f2e1  mov     edx, 3BAh
0x18001f2e6  jmp     loc_18001F22F
0x18001f2eb  mov     r8, [rdi+40h]; unsigned __int16 *
0x18001f2ef  lea     rcx, [rbp+var_10]; this
0x18001f2f3  mov     edx, 7; int
0x18001f2f8  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001f2fd  mov     ebx, eax
0x18001f2ff  test    eax, eax
0x18001f301  jns     short loc_18001F30D
0x18001f303  mov     edx, 3BBh
0x18001f308  jmp     loc_18001F22F
0x18001f30d  lea     r8, [rdi+50h]; struct StateRepository::Blob *
0x18001f311  mov     edx, 8; int
0x18001f316  lea     rcx, [rbp+var_10]; this
0x18001f31a  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x18001f31f  mov     ebx, eax
0x18001f321  test    eax, eax
0x18001f323  jns     short loc_18001F32F
0x18001f325  mov     edx, 3BCh
0x18001f32a  jmp     loc_18001F22F
0x18001f32f  mov     r8, [rdi]; __int64
0x18001f332  lea     rcx, [rbp+var_10]; this
0x18001f336  mov     edx, 9; int
0x18001f33b  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001f340  mov     ebx, eax
0x18001f342  test    eax, eax
0x18001f344  jns     short loc_18001F350
0x18001f346  mov     edx, 3BFh
0x18001f34b  jmp     loc_18001F22F
0x18001f350  mov     r8, [rdi+8]; __int64
0x18001f354  lea     rcx, [rbp+var_10]; this
0x18001f358  mov     edx, 0Ah; int
0x18001f35d  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001f362  mov     ebx, eax
0x18001f364  test    eax, eax
0x18001f366  jns     short loc_18001F372
0x18001f368  mov     edx, 3C0h
0x18001f36d  jmp     loc_18001F22F
0x18001f372  mov     r8, r14; __int64
0x18001f375  lea     rcx, [rbp+var_10]; this
0x18001f379  mov     edx, 0Bh; int
0x18001f37e  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x18001f383  mov     ebx, eax
0x18001f385  test    eax, eax
0x18001f387  jns     short loc_18001F393
0x18001f389  mov     edx, 3C1h
0x18001f38e  jmp     loc_18001F22F
0x18001f393  lea     rcx, [rbp+var_10]; this
0x18001f397  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001f39c  mov     ebx, eax
0x18001f39e  test    eax, eax
0x18001f3a0  jns     short loc_18001F3AC
0x18001f3a2  mov     edx, 3C4h
0x18001f3a7  jmp     loc_18001F22F
0x18001f3ac  lea     rdx, [rbp+var_10]; struct StateRepository::Statement *
0x18001f3b0  mov     rcx, rsi; this
0x18001f3b3  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001f3b8  test    eax, eax
0x18001f3ba  jns     short loc_18001F3D4
0x18001f3bc  mov     rcx, [rbp+18h]; this
0x18001f3c0  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f3c7  mov     r9d, eax; char *
0x18001f3ca  mov     edx, 3C6h; void *
0x18001f3cf  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001f3d4  mov     rcx, rsi; this
0x18001f3d7  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001f3dc  cmp     eax, 1
0x18001f3df  jz      short loc_18001F45C
0x18001f3e1  mov     r9, [rdi]; char *
0x18001f3e4  lea     rax, [rbp+arg_18]
0x18001f3e8  lea     r8, aSelectExistsSe_3; "SELECT EXISTS(SELECT 1 FROM Protocol WH"...
0x18001f3ef  mov     [rsp+40h+var_20], rax; int
0x18001f3f4  lea     rdx, aSelectExistsSe_7; "SELECT EXISTS(SELECT 1 FROM Protocol WH"...
0x18001f3fb  mov     byte ptr [rbp+arg_18], 0
0x18001f3ff  mov     rcx, rsi; this
0x18001f402  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18001f407  mov     rcx, [rbp+18h]; this
0x18001f40b  mov     ebx, eax
0x18001f40d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f414  test    eax, eax
0x18001f416  jns     short loc_18001F432
0x18001f418  mov     r9d, eax; char *
0x18001f41b  mov     edx, 0A7h; void *
0x18001f420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f425  mov     r9d, ebx
0x18001f428  mov     edx, 3D4h
0x18001f42d  jmp     loc_18001F232
0x18001f432  cmp     byte ptr [rbp+arg_18], 0
0x18001f436  jz      short loc_18001F44A
0x18001f438  mov     ebx, 80670001h
0x18001f43d  mov     edx, 3D5h
0x18001f442  mov     r9d, ebx
0x18001f445  jmp     loc_18001F23D
0x18001f44a  mov     ebx, 80070490h
0x18001f44f  mov     edx, 3D6h
0x18001f454  mov     r9d, ebx
0x18001f457  jmp     loc_18001F23D
0x18001f45c  inc     qword ptr [rdi+8]
0x18001f460  xor     ebx, ebx
0x18001f462  mov     [rdi+10h], r14
0x18001f466  lea     rcx, [rbp+var_10]; this
0x18001f46a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001f46f  mov     rsi, [rsp+40h+arg_8]
0x18001f474  mov     eax, ebx
0x18001f476  mov     rbx, [rsp+40h+arg_0]
0x18001f47b  add     rsp, 40h
0x18001f47f  pop     r14
0x18001f481  pop     rdi
0x18001f482  pop     rbp
0x18001f483  retn
```
