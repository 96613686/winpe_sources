# StateRepository::Entity::AppInstaller::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)

- ea: `0x180025b24`
- end: `0x180025dd0`
- name: `?BindAndExecuteForAddOrUpdate@AppInstaller@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z`
- size: `684`
- prototype: `int __high(struct StateRepository::Database *, const char *, bool, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180026080`

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
- `0x18001b8d4`
- `0x180025b24`
- `0x180029f90`

## string_xrefs

- `0x180025b92`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025d1a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025d63`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appinstaller.cpp`
- `0x180025d4a`: `SELECT EXISTS(SELECT 1 FROM AppInstaller WHERE _AppInstallerID=? LIMIT 1);`
- `0x180025b52`: `UPDATE AppInstaller SET _Revision=?, PackageFamily=?, Uri=?, Version=?, LastChecked=?, CheckUpdateInterval=?, Flags=?, PauseUntil=?, _Dictionary=? WHERE _AppInstallerID=? AND _Revision=?;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppInstaller::BindAndExecuteForAddOrUpdate(
        __int64 a1,
        StateRepository::Database *a2,
        __int64 a3,
        char a4)
{
  int NoRow; // eax
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r9
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-10h]
  bool *v16; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v18; // [rsp+60h] [rbp+30h] BYREF
  __int64 v19; // [rsp+68h] [rbp+38h] BYREF

  LOBYTE(v19) = a4;
  v18 = 0;
  NoRow = StateRepository::Database::PrepareFromCache(
            a2,
            "UPDATE AppInstaller SET _Revision=?, PackageFamily=?, Uri=?, Version=?, LastChecked=?, CheckUpdateInterval=?"
            ", Flags=?, PauseUntil=?, _Dictionary=? WHERE _AppInstallerID=? AND _Revision=?;",
            (struct StateRepository::Statement *)&v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 675;
LABEL_5:
    v9 = (unsigned int)NoRow;
    goto LABEL_6;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 1, *(_QWORD *)(a1 + 8) + 1LL);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 676;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 2, *(_QWORD *)(a1 + 16));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 677;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)&v18,
            3,
            *(const unsigned __int16 **)(a1 + 24));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 678;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 4, *(_QWORD *)(a1 + 40));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 679;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 5, *(_QWORD *)(a1 + 48));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 680;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 6, *(_DWORD *)(a1 + 56));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 681;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 7, *(_DWORD *)(a1 + 60));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 682;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 8, *(_QWORD *)(a1 + 64));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 683;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::BindAddress(
            (StateRepository::Statement *)&v18,
            9,
            (const struct StateRepository::Blob *)(a1 + 72));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 684;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 10, *(_QWORD *)a1);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 687;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v18, 11, *(_QWORD *)(a1 + 8));
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 688;
    goto LABEL_5;
  }
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v18);
  v7 = NoRow;
  if ( NoRow < 0 )
  {
    v8 = 691;
    goto LABEL_5;
  }
  v11 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)&v18);
  if ( v11 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
      (const char *)(unsigned int)v11,
      v15);
  if ( (unsigned int)StateRepository::Database::GetChanges(a2) == 1 )
  {
    ++*(_QWORD *)(a1 + 8);
    v7 = 0;
    goto LABEL_39;
  }
  v12 = *(const char **)a1;
  LOBYTE(v19) = 0;
  v13 = StateRepository::StatementExecution::PrepareAndBindAndExists(
          a2,
          (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM AppInstaller WHERE _AppInstallerID=? LIMIT 1);",
          0,
          v12,
          (__int64)&v19,
          v16);
  v10 = retaddr;
  v7 = v13;
  if ( v13 >= 0 )
  {
    if ( (_BYTE)v19 )
    {
      v7 = -2140733439;
      v8 = 707;
      v9 = 2154233857LL;
    }
    else
    {
      v7 = -2147023728;
      v8 = 708;
      v9 = 2147943568LL;
    }
    goto LABEL_7;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x141,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
    (const char *)(unsigned int)v13,
    v15);
  v9 = v7;
  v8 = 706;
LABEL_6:
  v10 = retaddr;
LABEL_7:
  wil::details::in1diag3::Return_Hr(
    v10,
    (void *)v8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appinstaller.cpp",
    (const char *)v9,
    v15);
LABEL_39:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v18);
  return v7;
}

```

## disassembly

```asm
0x180025b24  mov     [rsp-18h+arg_0], rbx
0x180025b29  mov     byte ptr [rsp-18h+arg_18], r9b
0x180025b2e  mov     [rsp-18h+arg_10], r8
0x180025b33  push    rbp
0x180025b34  push    rsi
0x180025b35  push    rdi
0x180025b36  mov     rbp, rsp
0x180025b39  sub     rsp, 30h
0x180025b3d  mov     rsi, rdx
0x180025b40  mov     [rbp+arg_10], 0
0x180025b48  mov     rdi, rcx
0x180025b4b  lea     r8, [rbp+arg_10]; struct StateRepository::Statement *
0x180025b4f  mov     rcx, rsi; this
0x180025b52  lea     rdx, aUpdateAppinsta; "UPDATE AppInstaller SET _Revision=?, Pa"...
0x180025b59  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180025b5e  mov     ebx, eax
0x180025b60  test    eax, eax
0x180025b62  jns     short loc_180025B6B
0x180025b64  mov     edx, 2A3h
0x180025b69  jmp     short loc_180025B8B
0x180025b6b  mov     r8, [rdi+8]
0x180025b6f  lea     rcx, [rbp+arg_10]; this
0x180025b73  inc     r8; __int64
0x180025b76  mov     edx, 1; int
0x180025b7b  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025b80  mov     ebx, eax
0x180025b82  test    eax, eax
0x180025b84  jns     short loc_180025BA3
0x180025b86  mov     edx, 2A4h; void *
0x180025b8b  mov     r9d, eax; char *
0x180025b8e  mov     rcx, [rbp+18h]; this
0x180025b92  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025b99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025b9e  jmp     loc_180025DB8
0x180025ba3  mov     r8, [rdi+10h]; __int64
0x180025ba7  lea     rcx, [rbp+arg_10]; this
0x180025bab  mov     edx, 2; int
0x180025bb0  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025bb5  mov     ebx, eax
0x180025bb7  test    eax, eax
0x180025bb9  jns     short loc_180025BC2
0x180025bbb  mov     edx, 2A5h
0x180025bc0  jmp     short loc_180025B8B
0x180025bc2  mov     r8, [rdi+18h]; unsigned __int16 *
0x180025bc6  lea     rcx, [rbp+arg_10]; this
0x180025bca  mov     edx, 3; int
0x180025bcf  call    ?BindAddress@Statement@StateRepository@@QEAAJHPEBG@Z; StateRepository::Statement::BindAddress(int,ushort const *)
0x180025bd4  mov     ebx, eax
0x180025bd6  test    eax, eax
0x180025bd8  jns     short loc_180025BE1
0x180025bda  mov     edx, 2A6h
0x180025bdf  jmp     short loc_180025B8B
0x180025be1  mov     r8, [rdi+28h]; __int64
0x180025be5  lea     rcx, [rbp+arg_10]; this
0x180025be9  mov     edx, 4; int
0x180025bee  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025bf3  mov     ebx, eax
0x180025bf5  test    eax, eax
0x180025bf7  jns     short loc_180025C00
0x180025bf9  mov     edx, 2A7h
0x180025bfe  jmp     short loc_180025B8B
0x180025c00  mov     r8, [rdi+30h]; __int64
0x180025c04  lea     rcx, [rbp+arg_10]; this
0x180025c08  mov     edx, 5; int
0x180025c0d  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025c12  mov     ebx, eax
0x180025c14  test    eax, eax
0x180025c16  jns     short loc_180025C22
0x180025c18  mov     edx, 2A8h
0x180025c1d  jmp     loc_180025B8B
0x180025c22  mov     r8d, [rdi+38h]; int
0x180025c26  lea     rcx, [rbp+arg_10]; this
0x180025c2a  mov     edx, 6; int
0x180025c2f  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180025c34  mov     ebx, eax
0x180025c36  test    eax, eax
0x180025c38  jns     short loc_180025C44
0x180025c3a  mov     edx, 2A9h
0x180025c3f  jmp     loc_180025B8B
0x180025c44  mov     r8d, [rdi+3Ch]; int
0x180025c48  lea     rcx, [rbp+arg_10]; this
0x180025c4c  mov     edx, 7; int
0x180025c51  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180025c56  mov     ebx, eax
0x180025c58  test    eax, eax
0x180025c5a  jns     short loc_180025C66
0x180025c5c  mov     edx, 2AAh
0x180025c61  jmp     loc_180025B8B
0x180025c66  mov     r8, [rdi+40h]; __int64
0x180025c6a  lea     rcx, [rbp+arg_10]; this
0x180025c6e  mov     edx, 8; int
0x180025c73  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025c78  mov     ebx, eax
0x180025c7a  test    eax, eax
0x180025c7c  jns     short loc_180025C88
0x180025c7e  mov     edx, 2ABh
0x180025c83  jmp     loc_180025B8B
0x180025c88  lea     r8, [rdi+48h]; struct StateRepository::Blob *
0x180025c8c  mov     edx, 9; int
0x180025c91  lea     rcx, [rbp+arg_10]; this
0x180025c95  call    ?BindAddress@Statement@StateRepository@@QEAAJHAEBVBlob@2@@Z; StateRepository::Statement::BindAddress(int,StateRepository::Blob const &)
0x180025c9a  mov     ebx, eax
0x180025c9c  test    eax, eax
0x180025c9e  jns     short loc_180025CAA
0x180025ca0  mov     edx, 2ACh
0x180025ca5  jmp     loc_180025B8B
0x180025caa  mov     r8, [rdi]; __int64
0x180025cad  lea     rcx, [rbp+arg_10]; this
0x180025cb1  mov     edx, 0Ah; int
0x180025cb6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025cbb  mov     ebx, eax
0x180025cbd  test    eax, eax
0x180025cbf  jns     short loc_180025CCB
0x180025cc1  mov     edx, 2AFh
0x180025cc6  jmp     loc_180025B8B
0x180025ccb  mov     r8, [rdi+8]; __int64
0x180025ccf  lea     rcx, [rbp+arg_10]; this
0x180025cd3  mov     edx, 0Bh; int
0x180025cd8  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180025cdd  mov     ebx, eax
0x180025cdf  test    eax, eax
0x180025ce1  jns     short loc_180025CED
0x180025ce3  mov     edx, 2B0h
0x180025ce8  jmp     loc_180025B8B
0x180025ced  lea     rcx, [rbp+arg_10]; this
0x180025cf1  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180025cf6  mov     ebx, eax
0x180025cf8  test    eax, eax
0x180025cfa  jns     short loc_180025D06
0x180025cfc  mov     edx, 2B3h
0x180025d01  jmp     loc_180025B8B
0x180025d06  lea     rdx, [rbp+arg_10]; struct StateRepository::Statement *
0x180025d0a  mov     rcx, rsi; this
0x180025d0d  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180025d12  test    eax, eax
0x180025d14  jns     short loc_180025D2E
0x180025d16  mov     rcx, [rbp+18h]; this
0x180025d1a  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025d21  mov     r9d, eax; char *
0x180025d24  mov     edx, 2B5h; void *
0x180025d29  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180025d2e  mov     rcx, rsi; this
0x180025d31  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x180025d36  cmp     eax, 1
0x180025d39  jz      short loc_180025DB2
0x180025d3b  mov     r9, [rdi]; char *
0x180025d3e  lea     rax, [rbp+arg_18]
0x180025d42  xor     r8d, r8d; char *
0x180025d45  mov     [rsp+30h+var_10], rax; int
0x180025d4a  lea     rdx, aSelectExistsSe_6; "SELECT EXISTS(SELECT 1 FROM AppInstalle"...
0x180025d51  mov     byte ptr [rbp+arg_18], 0
0x180025d55  mov     rcx, rsi; this
0x180025d58  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180025d5d  mov     rcx, [rbp+18h]; this
0x180025d61  mov     ebx, eax
0x180025d63  lea     r8, aOnecoreBaseApp_49; "onecore\\base\\appmodel\\staterepositor"...
0x180025d6a  test    eax, eax
0x180025d6c  jns     short loc_180025D88
0x180025d6e  mov     r9d, eax; char *
0x180025d71  mov     edx, 141h; void *
0x180025d76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025d7b  mov     r9d, ebx
0x180025d7e  mov     edx, 2C2h
0x180025d83  jmp     loc_180025B8E
0x180025d88  cmp     byte ptr [rbp+arg_18], 0
0x180025d8c  jz      short loc_180025DA0
0x180025d8e  mov     ebx, 80670001h
0x180025d93  mov     edx, 2C3h
0x180025d98  mov     r9d, ebx
0x180025d9b  jmp     loc_180025B99
0x180025da0  mov     ebx, 80070490h
0x180025da5  mov     edx, 2C4h
0x180025daa  mov     r9d, ebx
0x180025dad  jmp     loc_180025B99
0x180025db2  inc     qword ptr [rdi+8]
0x180025db6  xor     ebx, ebx
0x180025db8  lea     rcx, [rbp+arg_10]; this
0x180025dbc  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180025dc1  mov     eax, ebx
0x180025dc3  mov     rbx, [rsp+30h+arg_0]
0x180025dc8  add     rsp, 30h
0x180025dcc  pop     rdi
0x180025dcd  pop     rsi
0x180025dce  pop     rbp
0x180025dcf  retn
```
