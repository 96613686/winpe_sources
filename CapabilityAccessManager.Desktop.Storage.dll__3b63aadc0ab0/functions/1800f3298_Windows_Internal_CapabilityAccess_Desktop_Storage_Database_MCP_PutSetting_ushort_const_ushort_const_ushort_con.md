# Windows::Internal::CapabilityAccess::Desktop::Storage::Database::MCP::PutSetting(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1800f3298`
- end: `0x1800f3520`
- name: `?PutSetting@MCP@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEBG0000_K@Z`
- size: `648`
- prototype: `void __fastcall(Windows::Internal::CapabilityAccess::Desktop::Storage::Database::MCP *__hidden this, char *, char *, char *, char *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800ee380`

## callees

- `0x1800edb4c`
- `0x1800f097c`
- `0x1800f3298`
- `0x1800f4518`
- `0x1800f6f6c`
- `0x1800f719c`
- `0x1800f73a4`
- `0x1800f73fc`
- `0x1800f75c0`
- `0x1800ffb60`
- `0x1800ffc0c`
- `0x1800ffc78`
- `0x180100908`

## string_xrefs

- `0x1800f33ba`: `INSERT INTO McpConsent(User, Client, Server, Resource, Operation, ExpiryTime, Value) VALUES(?,?,?,?,?,?,?)ON CONFLICT(User, Client, Server, Resource, Operation)DO UPDATE SET Value=Excluded.Value;`
- `0x1800f346f`: `userSidStringForeignKey{%llu}, clientForeignKey{%llu}, serverForeignKey{%llu}, resourceForeignKey{%llu}, operationForeignKey{%llu}, value{%llu}`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Database::MCP::PutSetting(
        const wchar_t *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        char *a5,
        const unsigned __int16 *a6)
{
  const wchar_t *v10; // rbx
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v11; // r9
  unsigned __int64 ForeignKeyForString; // r12
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v13; // r9
  unsigned __int64 v14; // r15
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v15; // r9
  unsigned __int64 v16; // r14
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v17; // r9
  unsigned __int64 v18; // rsi
  struct Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *v19; // r9
  const char *v20; // rdi
  const unsigned __int16 *v21; // rbx
  unsigned int NoRow; // eax
  unsigned __int64 v23; // rdx
  __int64 v24; // r8
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-B9h]
  struct _GUID v27; // [rsp+60h] [rbp-79h] BYREF
  unsigned __int16 v28[4]; // [rsp+70h] [rbp-69h] BYREF
  _QWORD v29[16]; // [rsp+A0h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]
  struct sqlite3_stmt *v31; // [rsp+130h] [rbp+57h] BYREF

  if ( !this )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47E,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v26);
  if ( !a2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x47F,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v26);
  v10 = (const wchar_t *)a5;
  if ( !a5 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x480,
      (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
      (const char *)0x80070057LL,
      v26);
  v31 = 0;
  v29[0] = &std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable';
  v29[1] = Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection;
  v29[7] = v29;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
    (__int64)v29,
    0);
  v27.Data1 = 1961282486;
  *(_DWORD *)&v27.Data2 = 1315610752;
  *(_DWORD *)v27.Data4 = -1340258423;
  *(_DWORD *)&v27.Data4[4] = -1838464981;
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
    &v27);
  ForeignKeyForString = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(
                          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Clients",
                          this,
                          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
                          v11);
  v14 = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(
          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Servers",
          a2,
          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
          v13);
  v16 = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(
          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Resources",
          a3,
          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
          v15);
  v18 = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(
          (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Operations",
          a4,
          (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
          v17);
  v20 = (const char *)Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(
                        (Windows::Internal::CapabilityAccess::Desktop::Storage::Database *)"Users",
                        v10,
                        (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
                        v19);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
    "INSERT INTO McpConsent(User, Client, Server, Resource, Operation, ExpiryTime, Value) VALUES(?,?,?,?,?,?,?)ON CONFLIC"
    "T(User, Client, Server, Resource, Operation)DO UPDATE SET Value=Excluded.Value;",
    (struct StateRepository::Statement *)&v31);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 1);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 2);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 3);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 4);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 5);
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 6);
  v21 = a6;
  StateRepository::Statement::Bind((StateRepository::Statement *)&v31, 7);
  NoRow = StateRepository::Statement::FetchNoRow(&v31);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0x4AC,
    (unsigned int)"onecore\\base\\devices\\cam\\desktop\\lib\\storage\\database.cpp",
    (const char *)NoRow,
    (int)"userSidStringForeignKey{%llu}, clientForeignKey{%llu}, serverForeignKey{%llu}, resourceForeignKey{%llu}, operat"
         "ionForeignKey{%llu}, value{%llu}",
    v20,
    ForeignKeyForString,
    v14,
    v16,
    v18,
    v21);
  if ( v31 )
    StateRepository::StatementCache::Add(
      (StateRepository::StatementCache *)(*(_QWORD *)v28 + 40LL),
      (struct StateRepository::Statement *)&v31);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(
    (Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28,
    v23,
    v24,
    v25);
  Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper((Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper *)v28);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v31);
}

```

## disassembly

```asm
0x1800f3298  push    rbp
0x1800f329a  push    rbx
0x1800f329b  push    rsi
0x1800f329c  push    rdi
0x1800f329d  push    r12
0x1800f329f  push    r13
0x1800f32a1  push    r14
0x1800f32a3  push    r15
0x1800f32a5  lea     rbp, [rsp-0Fh]
0x1800f32aa  sub     rsp, 0E8h
0x1800f32b1  mov     r13, r9
0x1800f32b4  mov     r14, r8
0x1800f32b7  mov     rdi, rdx
0x1800f32ba  mov     rsi, rcx
0x1800f32bd  mov     rcx, [rbp+4Fh]; this
0x1800f32c1  test    rsi, rsi
0x1800f32c4  jz      loc_1800F34F0
0x1800f32ca  mov     rcx, [rbp+4Fh]; this
0x1800f32ce  test    rdx, rdx
0x1800f32d1  jz      loc_1800F3508
0x1800f32d7  mov     rcx, [rbp+4Fh]; this
0x1800f32db  mov     rbx, [rbp+47h+arg_20]
0x1800f32df  test    rbx, rbx
0x1800f32e2  jz      loc_1800F34D8
0x1800f32e8  mov     [rbp+47h+arg_0], 0
0x1800f32f0  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZV12@$$V@std@@6B@; const std::_Func_impl_no_alloc<std::shared_ptr<StateRepository::Database> (*)(void),std::shared_ptr<StateRepository::Database>,>::`vftable'
0x1800f32f7  mov     [rbp+47h+var_80], rax
0x1800f32fb  lea     rax, ?GetDatabaseConnection@StorageDatabaseManager@Globals@Storage@Desktop@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ; Windows::Internal::CapabilityAccess::Desktop::Storage::Globals::StorageDatabaseManager::GetDatabaseConnection(void)
0x1800f3302  mov     [rbp+47h+var_78], rax
0x1800f3306  lea     rax, [rbp+47h+var_80]
0x1800f330a  mov     [rbp+47h+var_48], rax
0x1800f330e  xor     r8d, r8d
0x1800f3311  lea     rdx, [rbp+47h+var_80]
0x1800f3315  lea     rcx, [rbp+47h+var_B0]; this
0x1800f3319  call    ??0DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@V?$function@$$A6A?AV?$shared_ptr@VDatabase@StateRepository@@@std@@XZ@std@@I@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::DatabaseWrapper(std::function<std::shared_ptr<StateRepository::Database> (void)>,uint)
0x1800f331e  nop
0x1800f331f  mov     [rbp+47h+var_C0.Data1], 74E6CBB6h
0x1800f3326  mov     dword ptr [rbp+47h+var_C0.Data2], 4E6AA080h
0x1800f332d  mov     dword ptr [rbp+47h+var_C0.Data4], 0B01D4789h
0x1800f3334  mov     dword ptr [rbp+47h+var_C0.Data4+4], 926B402Bh
0x1800f333b  lea     rdx, [rbp+47h+var_C0]; struct _GUID
0x1800f333f  lea     rcx, [rbp+47h+var_B0]; this
0x1800f3343  call    ?BeginExclusiveTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXU_GUID@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::BeginExclusiveTransaction(_GUID)
0x1800f3348  lea     r8, [rbp+47h+var_B0]; unsigned __int16 *
0x1800f334c  mov     rdx, rsi; char *
0x1800f334f  lea     rcx, aClients; "Clients"
0x1800f3356  call    ?GetForeignKeyForString@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_KPEBDPEBGAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(char const *,ushort const *,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f335b  mov     r12, rax
0x1800f335e  lea     r8, [rbp+47h+var_B0]; unsigned __int16 *
0x1800f3362  mov     rdx, rdi; char *
0x1800f3365  lea     rcx, aServers; "Servers"
0x1800f336c  call    ?GetForeignKeyForString@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_KPEBDPEBGAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(char const *,ushort const *,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f3371  mov     r15, rax
0x1800f3374  lea     r8, [rbp+47h+var_B0]; unsigned __int16 *
0x1800f3378  mov     rdx, r14; char *
0x1800f337b  lea     rcx, aResources; "Resources"
0x1800f3382  call    ?GetForeignKeyForString@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_KPEBDPEBGAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(char const *,ushort const *,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f3387  mov     r14, rax
0x1800f338a  lea     r8, [rbp+47h+var_B0]; unsigned __int16 *
0x1800f338e  mov     rdx, r13; char *
0x1800f3391  lea     rcx, aOperations; "Operations"
0x1800f3398  call    ?GetForeignKeyForString@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_KPEBDPEBGAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(char const *,ushort const *,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f339d  mov     rsi, rax
0x1800f33a0  lea     r8, [rbp+47h+var_B0]; unsigned __int16 *
0x1800f33a4  mov     rdx, rbx; char *
0x1800f33a7  lea     rcx, aUsers; "Users"
0x1800f33ae  call    ?GetForeignKeyForString@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_KPEBDPEBGAEAVDatabaseWrapper@Shared@3456@@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::GetForeignKeyForString(char const *,ushort const *,Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper &)
0x1800f33b3  mov     rdi, rax
0x1800f33b6  lea     r8, [rbp+47h+arg_0]; struct StateRepository::Statement *
0x1800f33ba  lea     rdx, aInsertIntoMcpc; "INSERT INTO McpConsent(User, Client, Se"...
0x1800f33c1  lea     rcx, [rbp+47h+var_B0]; this
0x1800f33c5  call    ?PrepareFromCache@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXQEBDAEAVStatement@StateRepository@@@Z; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::PrepareFromCache(char const * const,StateRepository::Statement &)
0x1800f33ca  mov     r8, rdi; __int64
0x1800f33cd  mov     edx, 1; int
0x1800f33d2  lea     rcx, [rbp+47h+arg_0]; this
0x1800f33d6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f33db  mov     r8, r12; __int64
0x1800f33de  mov     edx, 2; int
0x1800f33e3  lea     rcx, [rbp+47h+arg_0]; this
0x1800f33e7  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f33ec  mov     r8, r15; __int64
0x1800f33ef  mov     edx, 3; int
0x1800f33f4  lea     rcx, [rbp+47h+arg_0]; this
0x1800f33f8  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f33fd  mov     r8, r14; __int64
0x1800f3400  mov     edx, 4; int
0x1800f3405  lea     rcx, [rbp+47h+arg_0]; this
0x1800f3409  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f340e  mov     r8, rsi; __int64
0x1800f3411  mov     edx, 5; int
0x1800f3416  lea     rcx, [rbp+47h+arg_0]; this
0x1800f341a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f341f  xor     r8d, r8d; __int64
0x1800f3422  lea     edx, [r8+6]; int
0x1800f3426  lea     rcx, [rbp+47h+arg_0]; this
0x1800f342a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f342f  mov     rbx, [rbp+47h+arg_28]
0x1800f3433  mov     r8, rbx; __int64
0x1800f3436  mov     edx, 7; int
0x1800f343b  lea     rcx, [rbp+47h+arg_0]; this
0x1800f343f  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800f3444  lea     rcx, [rbp+47h+arg_0]; this
0x1800f3448  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x1800f344d  mov     rcx, [rbp+4Fh]; this
0x1800f3451  mov     [rsp+120h+var_D0], rbx
0x1800f3456  mov     [rsp+120h+var_D8], rsi
0x1800f345b  mov     [rsp+120h+var_E0], r14
0x1800f3460  mov     [rsp+120h+var_E8], r15
0x1800f3465  mov     [rsp+120h+var_F0], r12
0x1800f346a  mov     [rsp+120h+var_F8], rdi; char *
0x1800f346f  lea     rdx, aUsersidstringf; "userSidStringForeignKey{%llu}, clientFo"...
0x1800f3476  mov     qword ptr [rsp+120h+var_100], rdx; int
0x1800f347b  mov     r9d, eax; char *
0x1800f347e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3485  mov     edx, 4ACh; void *
0x1800f348a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800f348f  cmp     [rbp+47h+arg_0], 0
0x1800f3494  jz      short loc_1800F34A7
0x1800f3496  mov     rcx, qword ptr [rbp+47h+var_B0]
0x1800f349a  add     rcx, 28h ; '('; this
0x1800f349e  lea     rdx, [rbp+47h+arg_0]; struct StateRepository::Statement *
0x1800f34a2  call    ?Add@StatementCache@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::StatementCache::Add(StateRepository::Statement &)
0x1800f34a7  lea     rcx, [rbp+47h+var_B0]; this
0x1800f34ab  call    ?CommitTransaction@DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::CommitTransaction(void)
0x1800f34b0  nop
0x1800f34b1  lea     rcx, [rbp+47h+var_B0]; this
0x1800f34b5  call    ??1DatabaseWrapper@Shared@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Desktop::Shared::DatabaseWrapper::~DatabaseWrapper(void)
0x1800f34ba  nop
0x1800f34bb  lea     rcx, [rbp+47h+arg_0]; this
0x1800f34bf  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800f34c4  add     rsp, 0E8h
0x1800f34cb  pop     r15
0x1800f34cd  pop     r14
0x1800f34cf  pop     r13
0x1800f34d1  pop     r12
0x1800f34d3  pop     rdi
0x1800f34d4  pop     rsi
0x1800f34d5  pop     rbx
0x1800f34d6  pop     rbp
0x1800f34d7  retn
0x1800f34d8  mov     r9d, 80070057h; char *
0x1800f34de  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f34e5  mov     edx, 480h; void *
0x1800f34ea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f34f0  mov     r9d, 80070057h; char *
0x1800f34f6  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f34fd  mov     edx, 47Eh; void *
0x1800f3502  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f3508  mov     r9d, 80070057h; char *
0x1800f350e  lea     r8, aOnecoreBaseDev_2; "onecore\\base\\devices\\cam\\desktop\\l"...
0x1800f3515  mov     edx, 47Fh; void *
0x1800f351a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
