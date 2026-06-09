# StateRepository::Entity::FileTypeAssociation::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)

- ea: `0x18001fafc`
- end: `0x18001fdb8`
- name: `?BindAndExecuteForAddOrUpdate@FileTypeAssociation@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z`
- size: `700`
- prototype: `int __high(struct StateRepository::Database *, const char *, bool, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update`

## callers

- `0x180020058`

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
- `0x18001fafc`
- `0x180029f90`

## string_xrefs

- `0x18001fb6a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x18001fcf4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x18001fd41`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::FileTypeAssociation::BindAndExecuteForAddOrUpdate(
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
    v8 = 1029;
LABEL_5:
    v9 = (unsigned int)NoRow;
    goto LABEL_6;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 1, *(_QWORD *)(a1 + 8) + 1LL);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1030;
    goto LABEL_5;
  }
  v11 = *((_QWORD *)a2 + 1);
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 2, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1032;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            3,
            *(const unsigned __int16 **)(a1 + 24));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1033;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            4,
            *(const unsigned __int16 **)(a1 + 40));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1034;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 5, *(_QWORD *)(a1 + 56));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1035;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 6, *(_DWORD *)(a1 + 64));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1036;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            7,
            *(const unsigned __int16 **)(a1 + 72));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1037;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)v18,
            8,
            (const struct StateRepository::Blob *)(a1 + 88));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1038;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 9, *(_QWORD *)a1);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1041;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 10, *(_QWORD *)(a1 + 8));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1042;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)v18, 11, v11);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1043;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 1046;
    goto LABEL_5;
  }
  v12 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)v18);
  if ( v12 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
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
          (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM FileTypeAssociation WHERE _FileTypeAssociation"
                                              "ID=? AND _WorkId=0 LIMIT 1);",
          "SELECT EXISTS(SELECT 1 FROM FileTypeAssociation WHERE _FileTypeAssociationID=? AND (_WorkId=0 OR _WorkId=?) LIMIT 1);",
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
      v8 = 1063;
      v9 = 2154233857LL;
    }
    else
    {
      v7 = -2147023728;
      v8 = 1064;
      v9 = 2147943568LL;
    }
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB2,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
    (const char *)(unsigned int)v14,
    v16);
  v9 = v7;
  v8 = 1062;
LABEL_6:
  v10 = retaddr;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    v10,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
    (const char *)v9,
    v16);
LABEL_39:
  StateRepository::Statement::~Statement((StateRepository::Statement *)v18);
  return v7;
}

```

## disassembly

```asm
0x18001fafc  mov     [rsp-18h+arg_0], rbx
0x18001fb01  mov     [rsp-18h+arg_8], rsi
0x18001fb06  mov     byte ptr [rsp-18h+arg_18], r9b
0x18001fb0b  push    rbp
0x18001fb0c  push    rdi
0x18001fb0d  push    r14
0x18001fb0f  mov     rbp, rsp
0x18001fb12  sub     rsp, 40h
0x18001fb16  mov     rax, r8
0x18001fb19  mov     [rbp+var_10], 0
0x18001fb21  mov     rsi, rdx
0x18001fb24  lea     r8, [rbp+var_10]; struct StateRepository::Statement *
0x18001fb28  mov     rdi, rcx
0x18001fb2b  mov     rdx, rax; char *
0x18001fb2e  mov     rcx, rsi; this
0x18001fb31  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001fb36  mov     ebx, eax
0x18001fb38  test    eax, eax
0x18001fb3a  jns     short loc_18001FB43
0x18001fb3c  mov     edx, 405h
0x18001fb41  jmp     short loc_18001FB63
0x18001fb43  mov     r8, [rdi+8]
0x18001fb47  lea     rcx, [rbp+var_10]; this
0x18001fb4b  inc     r8; __int64
0x18001fb4e  mov     edx, 1; int
0x18001fb53  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001fb58  mov     ebx, eax
0x18001fb5a  test    eax, eax
0x18001fb5c  jns     short loc_18001FB7B
0x18001fb5e  mov     edx, 406h; void *
0x18001fb63  mov     r9d, eax; char *
0x18001fb66  mov     rcx, [rbp+18h]; this
0x18001fb6a  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fb71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb76  jmp     loc_18001FD9A
0x18001fb7b  mov     r14, [rsi+8]
0x18001fb7f  lea     rcx, [rbp+var_10]; this
0x18001fb83  mov     r8, r14; __int64
0x18001fb86  mov     edx, 2; int
0x18001fb8b  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001fb90  mov     ebx, eax
0x18001fb92  test    eax, eax
0x18001fb94  jns     short loc_18001FB9D
0x18001fb96  mov     edx, 408h
0x18001fb9b  jmp     short loc_18001FB63
0x18001fb9d  mov     r8, [rdi+18h]; unsigned __int16 *
0x18001fba1  lea     rcx, [rbp+var_10]; this
0x18001fba5  mov     edx, 3; int
0x18001fbaa  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001fbaf  mov     ebx, eax
0x18001fbb1  test    eax, eax
0x18001fbb3  jns     short loc_18001FBBC
0x18001fbb5  mov     edx, 409h
0x18001fbba  jmp     short loc_18001FB63
0x18001fbbc  mov     r8, [rdi+28h]; unsigned __int16 *
0x18001fbc0  lea     rcx, [rbp+var_10]; this
0x18001fbc4  mov     edx, 4; int
0x18001fbc9  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001fbce  mov     ebx, eax
0x18001fbd0  test    eax, eax
0x18001fbd2  jns     short loc_18001FBDB
0x18001fbd4  mov     edx, 40Ah
0x18001fbd9  jmp     short loc_18001FB63
0x18001fbdb  mov     r8, [rdi+38h]; __int64
0x18001fbdf  lea     rcx, [rbp+var_10]; this
0x18001fbe3  mov     edx, 5; int
0x18001fbe8  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001fbed  mov     ebx, eax
0x18001fbef  test    eax, eax
0x18001fbf1  jns     short loc_18001FBFD
0x18001fbf3  mov     edx, 40Bh
0x18001fbf8  jmp     loc_18001FB63
0x18001fbfd  mov     r8d, [rdi+40h]; int
0x18001fc01  lea     rcx, [rbp+var_10]; this
0x18001fc05  mov     edx, 6; int
0x18001fc0a  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18001fc0f  mov     ebx, eax
0x18001fc11  test    eax, eax
0x18001fc13  jns     short loc_18001FC1F
0x18001fc15  mov     edx, 40Ch
0x18001fc1a  jmp     loc_18001FB63
0x18001fc1f  mov     r8, [rdi+48h]; unsigned __int16 *
0x18001fc23  lea     rcx, [rbp+var_10]; this
0x18001fc27  mov     edx, 7; int
0x18001fc2c  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x18001fc31  mov     ebx, eax
0x18001fc33  test    eax, eax
0x18001fc35  jns     short loc_18001FC41
0x18001fc37  mov     edx, 40Dh
0x18001fc3c  jmp     loc_18001FB63
0x18001fc41  lea     r8, [rdi+58h]; struct StateRepository::Blob *
0x18001fc45  mov     edx, 8; int
0x18001fc4a  lea     rcx, [rbp+var_10]; this
0x18001fc4e  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x18001fc53  mov     ebx, eax
0x18001fc55  test    eax, eax
0x18001fc57  jns     short loc_18001FC63
0x18001fc59  mov     edx, 40Eh
0x18001fc5e  jmp     loc_18001FB63
0x18001fc63  mov     r8, [rdi]; __int64
0x18001fc66  lea     rcx, [rbp+var_10]; this
0x18001fc6a  mov     edx, 9; int
0x18001fc6f  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001fc74  mov     ebx, eax
0x18001fc76  test    eax, eax
0x18001fc78  jns     short loc_18001FC84
0x18001fc7a  mov     edx, 411h
0x18001fc7f  jmp     loc_18001FB63
0x18001fc84  mov     r8, [rdi+8]; __int64
0x18001fc88  lea     rcx, [rbp+var_10]; this
0x18001fc8c  mov     edx, 0Ah; int
0x18001fc91  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001fc96  mov     ebx, eax
0x18001fc98  test    eax, eax
0x18001fc9a  jns     short loc_18001FCA6
0x18001fc9c  mov     edx, 412h
0x18001fca1  jmp     loc_18001FB63
0x18001fca6  mov     r8, r14; __int64
0x18001fca9  lea     rcx, [rbp+var_10]; this
0x18001fcad  mov     edx, 0Bh; int
0x18001fcb2  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x18001fcb7  mov     ebx, eax
0x18001fcb9  test    eax, eax
0x18001fcbb  jns     short loc_18001FCC7
0x18001fcbd  mov     edx, 413h
0x18001fcc2  jmp     loc_18001FB63
0x18001fcc7  lea     rcx, [rbp+var_10]; this
0x18001fccb  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001fcd0  mov     ebx, eax
0x18001fcd2  test    eax, eax
0x18001fcd4  jns     short loc_18001FCE0
0x18001fcd6  mov     edx, 416h
0x18001fcdb  jmp     loc_18001FB63
0x18001fce0  lea     rdx, [rbp+var_10]; struct StateRepository::Statement *
0x18001fce4  mov     rcx, rsi; this
0x18001fce7  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001fcec  test    eax, eax
0x18001fcee  jns     short loc_18001FD08
0x18001fcf0  mov     rcx, [rbp+18h]; this
0x18001fcf4  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fcfb  mov     r9d, eax; char *
0x18001fcfe  mov     edx, 418h; void *
0x18001fd03  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001fd08  mov     rcx, rsi; this
0x18001fd0b  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001fd10  cmp     eax, 1
0x18001fd13  jz      short loc_18001FD90
0x18001fd15  mov     r9, [rdi]; char *
0x18001fd18  lea     rax, [rbp+arg_18]
0x18001fd1c  lea     r8, aSelectExistsSe_4; "SELECT EXISTS(SELECT 1 FROM FileTypeAss"...
0x18001fd23  mov     [rsp+40h+var_20], rax; int
0x18001fd28  lea     rdx, aSelectExistsSe_0; "SELECT EXISTS(SELECT 1 FROM FileTypeAss"...
0x18001fd2f  mov     byte ptr [rbp+arg_18], 0
0x18001fd33  mov     rcx, rsi; this
0x18001fd36  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18001fd3b  mov     rcx, [rbp+18h]; this
0x18001fd3f  mov     ebx, eax
0x18001fd41  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x18001fd48  test    eax, eax
0x18001fd4a  jns     short loc_18001FD66
0x18001fd4c  mov     r9d, eax; char *
0x18001fd4f  mov     edx, 0B2h; void *
0x18001fd54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fd59  mov     r9d, ebx
0x18001fd5c  mov     edx, 426h
0x18001fd61  jmp     loc_18001FB66
0x18001fd66  cmp     byte ptr [rbp+arg_18], 0
0x18001fd6a  jz      short loc_18001FD7E
0x18001fd6c  mov     ebx, 80670001h
0x18001fd71  mov     edx, 427h
0x18001fd76  mov     r9d, ebx
0x18001fd79  jmp     loc_18001FB71
0x18001fd7e  mov     ebx, 80070490h
0x18001fd83  mov     edx, 428h
0x18001fd88  mov     r9d, ebx
0x18001fd8b  jmp     loc_18001FB71
0x18001fd90  inc     qword ptr [rdi+8]
0x18001fd94  xor     ebx, ebx
0x18001fd96  mov     [rdi+10h], r14
0x18001fd9a  lea     rcx, [rbp+var_10]; this
0x18001fd9e  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001fda3  mov     rsi, [rsp+40h+arg_8]
0x18001fda8  mov     eax, ebx
0x18001fdaa  mov     rbx, [rsp+40h+arg_0]
0x18001fdaf  add     rsp, 40h
0x18001fdb3  pop     r14
0x18001fdb5  pop     rdi
0x18001fdb6  pop     rbp
0x18001fdb7  retn
```
