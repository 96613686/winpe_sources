# StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdAndUserSidFromUser(Windows::Internal::StateRepository::IUser *,StateRepository::Database &,__int64 *,void * *,bool *)

- ea: `0x18000e144`
- end: `0x18000e68e`
- name: `?TryGet_UserIdAndUserSidFromUser@User@DataAccessLayer@WinRT@StateRepository@@SAJPEAUIUser@4Internal@Windows@@AEAVDatabase@4@PEA_JPEAPEAXPEA_N@Z`
- size: `1354`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IUser *, struct StateRepository::Database *, __int64 *, void **, bool *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180116340`

## callees

- `0x180007a40`
- `0x18000a100`
- `0x18000e144`
- `0x18000e694`
- `0x180010d28`
- `0x1800131f8`
- `0x180017a58`
- `0x180018bbc`
- `0x180019794`
- `0x18001a548`
- `0x18001a9e0`
- `0x18018fb50`
- `0x18019914d`
- `0x18020b074`
- `0x18027e010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e556`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e556`
- `StateRepository.Core!sqlite3_db_handle` at `0x18000e52b`
- `StateRepository.Core!sqlite3_db_handle` at `0x18000e52b`
- `StateRepository.Core!sqlite3_column_int64` at `0x18000e4a6`
- `StateRepository.Core!sqlite3_column_int64` at `0x18000e4a6`
- `StateRepository.Core!sqlite3_errcode` at `0x18000e4fb`
- `StateRepository.Core!sqlite3_errcode` at `0x18000e4fb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e658`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18000e658`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e662`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e662`

## string_xrefs

- `0x18000e2d9`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18000e2f3`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000e3f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000e406`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000e453`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18000e5c1`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x18000e1f9`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000e3e0`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000e5f7`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18000e2bd`: `SELECT _UserID FROM User WHERE UserSid=?;`
- `0x18000e1bc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x18000e327`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`
- `0x18000e583`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user-custom.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::WinRT::DataAccessLayer::User::TryGet_UserIdAndUserSidFromUser(
        struct Windows::Internal::StateRepository::IUser *a1,
        struct sqlite3 **a2,
        __int64 *a3,
        void **a4,
        bool *a5)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  int v12; // eax
  int v13; // ebx
  int v14; // eax
  HLOCAL v15; // r12
  bool *v16; // r13
  void *v17; // rsi
  wil::details::in1diag3 *v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  unsigned int v21; // r15d
  __int64 v22; // rdx
  void *v23; // rcx
  int v24; // eax
  unsigned int v25; // edi
  int v26; // eax
  char v27; // cl
  int v28; // eax
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rax
  int v32; // eax
  unsigned __int64 v33; // r9
  __int64 v34; // rdx
  int token_information; // eax
  int v36; // eax
  int v37; // r8d
  SIZE_T LengthSid; // rbx
  void *v39; // rax
  const char **v40; // [rsp+28h] [rbp-C1h]
  void *Block; // [rsp+38h] [rbp-B1h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-A9h] BYREF
  HLOCAL v43; // [rsp+48h] [rbp-A1h] BYREF
  _QWORD *v44; // [rsp+58h] [rbp-91h]
  _QWORD v45[27]; // [rsp+60h] [rbp-89h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+140h] [rbp+57h]
  struct sqlite3_stmt *v47; // [rsp+150h] [rbp+67h] BYREF
  __int64 *v48; // [rsp+158h] [rbp+6Fh]
  void **v49; // [rsp+160h] [rbp+77h]

  v49 = a4;
  v48 = a3;
  if ( !*a2 )
  {
    v9 = -2147019873;
    v10 = 31;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\dal-user.cpp",
      (const char *)v9,
      (int)v40);
    return v9;
  }
  if ( a4 )
    *a4 = 0;
  if ( !a1 )
  {
    hMem = 0;
    v14 = StateRepository::AutoCoSid::FromCaller(&hMem);
    v9 = v14;
    v15 = hMem;
    if ( v14 < 0 )
    {
      v33 = (unsigned int)v14;
      v34 = 52;
LABEL_68:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\dal-user.cpp",
        (const char *)v33,
        (int)v40);
      LocalFree(v15);
      return v9;
    }
    v43 = hMem;
    *a3 = 0;
    v16 = a5;
    *a5 = 0;
    v17 = 0;
    Block = 0;
    if ( !v15 )
    {
      token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, -6);
      v9 = token_information;
      if ( token_information < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-user-custom.cpp",
          (const char *)(unsigned int)token_information,
          (int)v40);
        v23 = Block;
        if ( Block )
          goto LABEL_71;
        goto LABEL_72;
      }
      v17 = Block;
      v43 = *(HLOCAL *)Block;
    }
    v47 = 0;
    v45[0] = off_180282620;
    v45[1] = &v43;
    v44 = v45;
    if ( !*a2 )
    {
      v9 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
        (const char *)0x8007139FLL,
        (int)v40);
LABEL_24:
      v18 = retaddr;
      v19 = 21;
      v20 = v9;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        v18,
        (void *)v19,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)(unsigned int)v20,
        (int)v40);
      v21 = 199;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
        (const char *)v9,
        (int)v40);
      v22 = 152;
      goto LABEL_27;
    }
    if ( !StateRepository::StatementCache::Get(
            (StateRepository::StatementCache *)(a2 + 5),
            "SELECT _UserID FROM User WHERE UserSid=?;",
            (struct StateRepository::Statement *)&v47) )
    {
      v36 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v47);
      if ( v36 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
          (const char *)(unsigned int)v36,
          (int)v40);
      v9 = StateRepository::Database::dal_prepare_v2(*a2, "SELECT _UserID FROM User WHERE UserSid=?;", v37, &v47, v40);
      if ( (v9 & 0x80000000) != 0 )
        goto LABEL_24;
    }
    v20 = (*(__int64 (__fastcall **)(_QWORD *, struct sqlite3_stmt **))(*v44 + 8LL))(v44, &v47);
    v9 = v20;
    if ( v20 < 0 )
    {
      v18 = retaddr;
      v19 = 23;
      goto LABEL_25;
    }
    v9 = -2147019873;
    v21 = 201;
    if ( !v47 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        (int)v40);
      goto LABEL_26;
    }
    v26 = StateRepository::Statement::dal_step(v47);
    v9 = v26;
    if ( v26 == -2018574236 )
    {
      v27 = 1;
    }
    else
    {
      if ( v26 != -2018574235 )
      {
        if ( v26 < 0 )
          goto LABEL_26;
LABEL_40:
        if ( *v16 )
          goto LABEL_50;
        if ( v47 )
          v28 = StateRepository::StatementCache::Add(
                  (StateRepository::StatementCache *)(a2 + 5),
                  (struct StateRepository::Statement *)&v47);
        else
          v28 = 0;
        if ( v28 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
            (const char *)(unsigned int)v28,
            (int)v40);
        if ( *v16 )
        {
LABEL_50:
          v29 = sqlite3_column_int64(v47, 0);
          if ( v29
            || (v47 ? (v31 = sqlite3_db_handle()) : (v31 = 0),
                (v32 = sqlite3_errcode(v31), (v9 = v32) == 0) || v32 == 100) )
          {
            *v48 = v29;
          }
          else
          {
            if ( v32 > 0 )
              v9 = (unsigned __int16)v32 | 0x87AF0000;
            if ( (v9 & 0x80000000) != 0 )
            {
              v22 = 155;
LABEL_27:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v22,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-user-custom.cpp",
                (const char *)v9,
                (int)v40);
              (*(void (__fastcall **)(_QWORD *, _QWORD))*v44)(v44, 0);
              StateRepository::Statement::~Statement((StateRepository::Statement *)&v47);
              if ( v17 )
              {
                v23 = v17;
LABEL_71:
                operator delete(v23);
              }
LABEL_72:
              v34 = 56;
LABEL_73:
              v33 = v9;
              goto LABEL_68;
            }
          }
        }
        if ( v47 )
          v12 = StateRepository::StatementCache::Add(
                  (StateRepository::StatementCache *)(a2 + 5),
                  (struct StateRepository::Statement *)&v47);
        else
          v12 = 0;
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x9E,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-user-custom.cpp",
            (const char *)(unsigned int)v12,
            (int)v40);
        (*(void (__fastcall **)(_QWORD *, _QWORD))*v44)(v44, 0);
        if ( v47 )
        {
          v30 = StateRepository::Statement::dal_finalize(v47);
          v13 = v30;
          if ( v30 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x7B,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
              (const char *)(unsigned int)v30,
              (int)v40);
            goto LABEL_10;
          }
          v47 = 0;
        }
        v13 = 0;
LABEL_10:
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v13,
            (int)v40);
        if ( v17 )
          operator delete(v17);
        if ( v49 )
        {
          LengthSid = GetLengthSid(v15);
          v39 = CoTaskMemAlloc(LengthSid);
          if ( !v39 )
          {
            v9 = -2147024882;
            v34 = 61;
            goto LABEL_73;
          }
          memcpy_0(v39, v15, LengthSid);
        }
        LocalFree(v15);
        return 0;
      }
      v27 = 0;
    }
    *v16 = v27;
    goto LABEL_40;
  }
  v24 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IUser *, __int64 *))(*(_QWORD *)a1 + 48LL))(
          a1,
          a3);
  v25 = v24;
  if ( v24 >= 0 )
  {
    if ( a4 )
    {
      LODWORD(v47) = 0;
      v9 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IUser *, struct sqlite3_stmt **, void **))(*(_QWORD *)a1 + 88LL))(
             a1,
             &v47,
             a4);
      if ( (v9 & 0x80000000) != 0 )
      {
        v10 = 44;
        goto LABEL_3;
      }
    }
    *a5 = 1;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\client\\lib\\dal-user.cpp",
    (const char *)(unsigned int)v24,
    (int)v40);
  return v25;
}

```

## disassembly

```asm
0x18000e144  mov     rax, rsp
0x18000e147  mov     [rax+8], rbx
0x18000e14b  mov     [rax+20h], r9
0x18000e14f  mov     [rax+18h], r8
0x18000e153  push    rbp
0x18000e154  push    rsi
0x18000e155  push    rdi
0x18000e156  push    r12
0x18000e158  push    r13
0x18000e15a  push    r14
0x18000e15c  push    r15
0x18000e15e  lea     rbp, [rax-57h]
0x18000e162  sub     rsp, 100h
0x18000e169  mov     rsi, r9
0x18000e16c  mov     rdi, r8
0x18000e16f  mov     r14, rdx
0x18000e172  mov     rbx, rcx
0x18000e175  xor     r15d, r15d
0x18000e178  cmp     [rdx], r15
0x18000e17b  jnz     loc_18000E248
0x18000e181  mov     ebx, 8007139Fh
0x18000e186  lea     edx, [r15+1Fh]; void *
0x18000e18a  lea     r8, aOnecoreBaseApp_114; "onecore\\base\\appmodel\\staterepositor"...
0x18000e191  mov     r9d, ebx; char *
0x18000e194  mov     rcx, [rbp+57h]; this
0x18000e198  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e19d  mov     eax, ebx
0x18000e19f  jmp     loc_18000E22D
0x18000e1a4  lea     rcx, [r14+28h]; this
0x18000e1a8  lea     rdx, [rbp+4Fh+arg_8]; struct StateRepository::Statement *
0x18000e1ac  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x18000e1b1  mov     rcx, [rbp+57h]; this
0x18000e1b5  test    eax, eax
0x18000e1b7  jns     short loc_18000E1CD
0x18000e1b9  mov     r9d, eax; char *
0x18000e1bc  lea     r8, aOnecoreBaseApp_498; "onecore\\base\\appmodel\\staterepositor"...
0x18000e1c3  mov     edx, 9Eh; void *
0x18000e1c8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e1cd  mov     rcx, [rsp+130h+var_E0]
0x18000e1d2  mov     rax, [rcx]
0x18000e1d5  xor     edx, edx
0x18000e1d7  mov     rax, [rax]
0x18000e1da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1df  mov     rcx, [rbp+4Fh+arg_8]; struct sqlite3_stmt *
0x18000e1e3  test    rcx, rcx
0x18000e1e6  jnz     loc_18000E4D1
0x18000e1ec  xor     ebx, ebx
0x18000e1ee  mov     rcx, [rbp+57h]; this
0x18000e1f2  test    ebx, ebx
0x18000e1f4  jns     short loc_18000E20A
0x18000e1f6  mov     r9d, ebx; char *
0x18000e1f9  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18000e200  mov     edx, 16h; void *
0x18000e205  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e20a  test    rsi, rsi
0x18000e20d  jz      short loc_18000E217
0x18000e20f  mov     rcx, rsi; Block
0x18000e212  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e217  cmp     [rbp+4Fh+arg_18], 0
0x18000e21c  jnz     loc_18000E655
0x18000e222  mov     rcx, r12; hMem
0x18000e225  call    cs:__imp_LocalFree
0x18000e22b  xor     eax, eax
0x18000e22d  mov     rbx, [rsp+130h+arg_0]
0x18000e235  add     rsp, 100h
0x18000e23c  pop     r15
0x18000e23e  pop     r14
0x18000e240  pop     r13
0x18000e242  pop     r12
0x18000e244  pop     rdi
0x18000e245  pop     rsi
0x18000e246  pop     rbp
0x18000e247  retn
0x18000e248  test    rsi, rsi
0x18000e24b  jnz     loc_18000E63B
0x18000e251  test    rbx, rbx
0x18000e254  jnz     loc_18000E363
0x18000e25a  mov     [rsp+130h+hMem], r15
0x18000e25f  lea     rcx, [rsp+130h+hMem]; this
0x18000e264  call    ?FromCaller@AutoCoSid@StateRepository@@QEAAJXZ; StateRepository::AutoCoSid::FromCaller(void)
0x18000e269  mov     ebx, eax
0x18000e26b  mov     r12, [rsp+130h+hMem]
0x18000e270  test    eax, eax
0x18000e272  js      loc_18000E53A
0x18000e278  mov     [rsp+130h+var_F0], r12
0x18000e27d  mov     [rdi], r15
0x18000e280  mov     r13, [rbp+4Fh+arg_20]
0x18000e284  mov     [r13+0], r15b
0x18000e288  mov     rsi, r15
0x18000e28b  mov     [rsp+130h+Block], r15
0x18000e290  test    r12, r12
0x18000e293  jz      loc_18000E561
0x18000e299  mov     [rbp+4Fh+arg_8], r15
0x18000e29d  lea     rax, off_180282620
0x18000e2a4  mov     [rsp+130h+var_D8], rax
0x18000e2a9  lea     rax, [rsp+130h+var_F0]
0x18000e2ae  mov     [rsp+130h+var_D8+8], rax
0x18000e2b3  lea     rax, [rsp+130h+var_D8]
0x18000e2b8  mov     [rsp+130h+var_E0], rax
0x18000e2bd  lea     rbx, aSelectUseridFr; "SELECT _UserID FROM User WHERE UserSid="...
0x18000e2c4  cmp     [r14], r15
0x18000e2c7  jnz     loc_18000E391
0x18000e2cd  mov     rcx, [rbp+57h]; this
0x18000e2d1  mov     ebx, 8007139Fh
0x18000e2d6  mov     r9d, ebx; char *
0x18000e2d9  lea     r8, aOnecoreBaseApp_370; "onecore\\base\\appmodel\\staterepositor"...
0x18000e2e0  mov     edx, 66Eh; void *
0x18000e2e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2ea  mov     rcx, [rbp+57h]; this
0x18000e2ee  mov     edx, 15h; void *
0x18000e2f3  lea     rdi, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000e2fa  mov     r8, rdi; unsigned int
0x18000e2fd  mov     eax, ebx
0x18000e2ff  mov     r9d, eax; char *
0x18000e302  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e307  mov     r15d, 0C7h
0x18000e30d  mov     r9d, ebx; char *
0x18000e310  mov     rcx, [rbp+57h]; this
0x18000e314  mov     r8, rdi; unsigned int
0x18000e317  mov     edx, r15d; void *
0x18000e31a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e31f  mov     edx, 98h; void *
0x18000e324  mov     r9d, ebx; char *
0x18000e327  lea     r8, aOnecoreBaseApp_498; "onecore\\base\\appmodel\\staterepositor"...
0x18000e32e  mov     rcx, [rbp+57h]; this
0x18000e332  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e337  mov     rcx, [rsp+130h+var_E0]
0x18000e33c  mov     rax, [rcx]
0x18000e33f  xor     edx, edx
0x18000e341  mov     rax, [rax]
0x18000e344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e349  lea     rcx, [rbp+4Fh+arg_8]; this
0x18000e34d  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18000e352  test    rsi, rsi
0x18000e355  jz      loc_18000E5A3
0x18000e35b  mov     rcx, rsi
0x18000e35e  jmp     loc_18000E59E
0x18000e363  mov     rax, [rcx]
0x18000e366  mov     rdx, rdi
0x18000e369  mov     rax, [rax+30h]
0x18000e36d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e372  mov     edi, eax
0x18000e374  test    eax, eax
0x18000e376  js      loc_18000E47D
0x18000e37c  test    rsi, rsi
0x18000e37f  jnz     loc_18000E60D
0x18000e385  mov     rax, [rbp+4Fh+arg_20]
0x18000e389  mov     byte ptr [rax], 1
0x18000e38c  jmp     loc_18000E22B
0x18000e391  lea     rcx, [r14+28h]; this
0x18000e395  lea     r8, [rbp+4Fh+arg_8]; struct StateRepository::Statement *
0x18000e399  mov     rdx, rbx; char *
0x18000e39c  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x18000e3a1  test    rax, rax
0x18000e3a4  jz      loc_18000E5AD
0x18000e3aa  mov     rcx, [rsp+130h+var_E0]
0x18000e3af  mov     rax, [rcx]
0x18000e3b2  lea     rdx, [rbp+4Fh+arg_8]
0x18000e3b6  mov     rax, [rax+8]
0x18000e3ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3bf  mov     ebx, eax
0x18000e3c1  test    eax, eax
0x18000e3c3  js      short loc_18000E3FD
0x18000e3c5  mov     ebx, 8007139Fh
0x18000e3ca  mov     r15d, 0C9h
0x18000e3d0  mov     rcx, [rbp+4Fh+arg_8]; struct sqlite3_stmt *
0x18000e3d4  test    rcx, rcx
0x18000e3d7  jnz     short loc_18000E415
0x18000e3d9  mov     rcx, [rbp+57h]; this
0x18000e3dd  mov     r9d, ebx; char *
0x18000e3e0  lea     r8, aOnecoreBaseApp_463; "onecore\\base\\appmodel\\staterepositor"...
0x18000e3e7  mov     edx, 3Fh ; '?'; void *
0x18000e3ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e3f1  lea     rdi, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000e3f8  jmp     loc_18000E30D
0x18000e3fd  mov     rcx, [rbp+57h]
0x18000e401  mov     edx, 17h
0x18000e406  lea     rdi, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000e40d  mov     r8, rdi
0x18000e410  jmp     loc_18000E2FF
0x18000e415  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x18000e41a  mov     ebx, eax
0x18000e41c  cmp     eax, 87AF0064h
0x18000e421  jnz     loc_18000E4BD
0x18000e427  mov     cl, 1
0x18000e429  mov     [r13+0], cl
0x18000e42d  cmp     byte ptr [r13+0], 0
0x18000e432  jnz     short loc_18000E4A0
0x18000e434  cmp     [rbp+4Fh+arg_8], 0
0x18000e439  jz      short loc_18000E49C
0x18000e43b  lea     rcx, [r14+28h]; this
0x18000e43f  lea     rdx, [rbp+4Fh+arg_8]; struct StateRepository::Statement *
0x18000e443  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x18000e448  mov     rcx, [rbp+57h]; this
0x18000e44c  test    eax, eax
0x18000e44e  jns     short loc_18000E464
0x18000e450  mov     r9d, eax; char *
0x18000e453  lea     r8, aOnecoreBaseApp_248; "onecore\\base\\appmodel\\staterepositor"...
0x18000e45a  mov     edx, 0CDh; void *
0x18000e45f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e464  cmp     byte ptr [r13+0], 0
0x18000e469  jnz     short loc_18000E4A0
0x18000e46b  cmp     [rbp+4Fh+arg_8], 0
0x18000e470  jnz     loc_18000E1A4
0x18000e476  xor     eax, eax
0x18000e478  jmp     loc_18000E1B1
0x18000e47d  mov     rcx, [rbp+57h]; this
0x18000e481  mov     r9d, edi; char *
0x18000e484  lea     r8, aOnecoreBaseApp_114; "onecore\\base\\appmodel\\staterepositor"...
0x18000e48b  mov     edx, 28h ; '('; void *
0x18000e490  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e495  mov     eax, edi
0x18000e497  jmp     loc_18000E22D
0x18000e49c  xor     eax, eax
0x18000e49e  jmp     short loc_18000E448
0x18000e4a0  xor     edx, edx
0x18000e4a2  mov     rcx, [rbp+4Fh+arg_8]
0x18000e4a6  call    cs:__imp_sqlite3_column_int64
0x18000e4ac  mov     rdi, rax
0x18000e4af  test    rax, rax
0x18000e4b2  jz      short loc_18000E4ED
0x18000e4b4  mov     rax, [rbp+4Fh+arg_10]
0x18000e4b8  mov     [rax], rdi
0x18000e4bb  jmp     short loc_18000E46B
0x18000e4bd  cmp     eax, 87AF0065h
0x18000e4c2  jz      short loc_18000E533
0x18000e4c4  test    eax, eax
0x18000e4c6  jns     loc_18000E42D
0x18000e4cc  jmp     loc_18000E3F1
0x18000e4d1  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x18000e4d6  mov     ebx, eax
0x18000e4d8  test    eax, eax
0x18000e4da  js      loc_18000E5F0
0x18000e4e0  mov     [rbp+4Fh+arg_8], 0
0x18000e4e8  jmp     loc_18000E1EC
0x18000e4ed  mov     rcx, [rbp+4Fh+arg_8]
0x18000e4f1  test    rcx, rcx
0x18000e4f4  jnz     short loc_18000E52B
0x18000e4f6  xor     eax, eax
0x18000e4f8  mov     rcx, rax
0x18000e4fb  call    cs:__imp_sqlite3_errcode
0x18000e501  mov     ebx, eax
0x18000e503  test    eax, eax
0x18000e505  jz      short loc_18000E4B4
0x18000e507  cmp     eax, 64h ; 'd'
0x18000e50a  jz      short loc_18000E4B4
0x18000e50c  test    eax, eax
0x18000e50e  jle     short loc_18000E519
0x18000e510  movzx   ebx, ax
0x18000e513  or      ebx, 87AF0000h
0x18000e519  test    ebx, ebx
0x18000e51b  jns     loc_18000E46B
0x18000e521  mov     edx, 9Bh
0x18000e526  jmp     loc_18000E324
0x18000e52b  call    cs:__imp_sqlite3_db_handle
0x18000e531  jmp     short loc_18000E4F8
0x18000e533  xor     cl, cl
0x18000e535  jmp     loc_18000E429
0x18000e53a  mov     r9d, eax; char *
0x18000e53d  mov     edx, 34h ; '4'; void *
0x18000e542  lea     r8, aOnecoreBaseApp_114; "onecore\\base\\appmodel\\staterepositor"...
0x18000e549  mov     rcx, [rbp+57h]; this
0x18000e54d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e552  nop
0x18000e553  mov     rcx, r12; hMem
0x18000e556  call    cs:__imp_LocalFree
0x18000e55c  jmp     loc_18000E19D
0x18000e561  mov     rdx, 0FFFFFFFFFFFFFFFAh
0x18000e568  lea     rcx, [rsp+130h+Block]
0x18000e56d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18000e572  mov     ebx, eax
0x18000e574  test    eax, eax
0x18000e576  jns     loc_18000E643
0x18000e57c  mov     rcx, [rbp+57h]; this
0x18000e580  mov     r9d, eax; char *
0x18000e583  lea     r8, aOnecoreBaseApp_498; "onecore\\base\\appmodel\\staterepositor"...
0x18000e58a  mov     edx, 86h; void *
0x18000e58f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e594  mov     rcx, [rsp+130h+Block]; Block
0x18000e599  test    rcx, rcx
0x18000e59c  jz      short loc_18000E5A3
0x18000e59e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000e5a3  mov     edx, 38h ; '8'
0x18000e5a8  mov     r9d, ebx
0x18000e5ab  jmp     short loc_18000E542
0x18000e5ad  lea     rcx, [rbp+4Fh+arg_8]; this
0x18000e5b1  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18000e5b6  mov     rcx, [rbp+57h]; this
0x18000e5ba  test    eax, eax
0x18000e5bc  jns     short loc_18000E5D2
0x18000e5be  mov     r9d, eax; char *
0x18000e5c1  lea     r8, aOnecoreBaseApp_149; "onecore\\base\\appmodel\\StateRepositor"...
0x18000e5c8  mov     edx, 127h; void *
0x18000e5cd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e5d2  lea     r9, [rbp+4Fh+arg_8]; struct sqlite3_stmt **
0x18000e5d6  mov     rdx, rbx; char *
0x18000e5d9  mov     rcx, [r14]; struct sqlite3 *
0x18000e5dc  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x18000e5e1  mov     ebx, eax
0x18000e5e3  test    eax, eax
  ... truncated ...
```
