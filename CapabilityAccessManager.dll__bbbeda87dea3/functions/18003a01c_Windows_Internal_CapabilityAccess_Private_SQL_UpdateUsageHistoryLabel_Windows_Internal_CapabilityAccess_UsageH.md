# Windows::Internal::CapabilityAccess::Private::SQL::UpdateUsageHistoryLabel(Windows::Internal::CapabilityAccess::UsageHistory::AppType,unsigned __int64,Windows::Internal::CapabilityAccess::UsageHistory::UsageHistoryLabel)

- ea: `0x18003a01c`
- end: `0x18003a25e`
- name: `?UpdateUsageHistoryLabel@SQL@Private@CapabilityAccess@Internal@Windows@@YAXW4AppType@UsageHistory@345@_KW4UsageHistoryLabel@7345@@Z`
- size: `578`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180091620`

## callees

- `0x180016490`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x1800311c4`
- `0x180037460`
- `0x180039a1c`
- `0x18003a01c`
- `0x1800a25e8`
- `0x1800a261c`
- `0x1800a26e8`
- `0x1800a2758`
- `0x1800a2800`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x18003a1a5`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a1ba`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a1d2`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a1f8`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a20d`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a222`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a237`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a24c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003a0d6`: `UPDATE PackagedUsageHistory SET Label=? WHERE ID=?; `
- `0x18003a0b1`: `UPDATE NonPackagedUsageHistory SET Label=? WHERE ID=?; `

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Windows::Internal::CapabilityAccess::Private::SQL::UpdateUsageHistoryLabel(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        __int64 a2,
        int a3)
{
  int v5; // ebx
  _QWORD *v6; // rax
  int v7; // ebx
  StateRepository::Database *v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int NoRow; // eax
  int v14; // eax
  unsigned int v15; // eax
  struct _GUID v16; // [rsp+20h] [rbp-60h] BYREF
  StateRepository::Database *v17; // [rsp+30h] [rbp-50h] BYREF
  std::_Ref_count_base *v18; // [rsp+38h] [rbp-48h]
  _BYTE v19[16]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE v20[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+18h]
  __int64 v22; // [rsp+B8h] [rbp+38h] BYREF

  v5 = (int)a1;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97E,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v16.Data1);
  std::make_shared<StateRepository::Database,>(&v17);
  v16.Data1 = -1332578128;
  *(_DWORD *)&v16.Data2 = 1116522614;
  *(_DWORD *)v16.Data4 = -21903990;
  *(_DWORD *)&v16.Data4[4] = -418904402;
  v6 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                   v19,
                   &v17);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
    (Windows::Internal::CapabilityAccess::Private::SQL *)v20,
    v6,
    &v16,
    1);
  v22 = 0;
  v7 = v5 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      v15 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x991,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)v15,
        v16.Data1);
    }
    v8 = v17;
    v9 = StateRepository::Database::PrepareFromCache(
           v17,
           "UPDATE NonPackagedUsageHistory SET Label=? WHERE ID=?; ",
           (struct StateRepository::Statement *)&v22);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x989,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v9,
        v16.Data1);
  }
  else
  {
    v8 = v17;
    v10 = StateRepository::Database::PrepareFromCache(
            v17,
            "UPDATE PackagedUsageHistory SET Label=? WHERE ID=?; ",
            (struct StateRepository::Statement *)&v22);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x98D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v10,
        v16.Data1);
  }
  v11 = StateRepository::Statement::Bind((StateRepository::Statement *)&v22, 1, a3);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x994,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v11,
      v16.Data1);
  v12 = StateRepository::Statement::Bind((StateRepository::Statement *)&v22, 2, a2);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x995,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v12,
      v16.Data1);
  NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v22);
  if ( NoRow < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x996,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)NoRow,
      v16.Data1);
  StateRepository::Database::AddToCache(v8, (struct StateRepository::Statement *)&v22);
  v14 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v22);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x998,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v14,
      v16.Data1);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v20);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v22);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v20);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
}

```

## disassembly

```asm
0x18003a01c  mov     [rsp-18h+arg_0], rbx
0x18003a021  mov     [rsp-18h+arg_8], rsi
0x18003a026  push    rbp
0x18003a027  push    rdi
0x18003a028  push    r14
0x18003a02a  mov     rbp, rsp
0x18003a02d  sub     rsp, 80h
0x18003a034  mov     r14d, r8d
0x18003a037  mov     rsi, rdx
0x18003a03a  mov     ebx, ecx
0x18003a03c  mov     rdi, [rbp+18h]
0x18003a040  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x18003a045  test    al, al
0x18003a047  jz      loc_18003A1CC
0x18003a04d  lea     rcx, [rbp+var_50]
0x18003a051  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x18003a056  nop
0x18003a057  mov     [rbp+var_60], 0B09278B0h
0x18003a05e  mov     [rbp+var_5C], 428CC876h
0x18003a065  mov     [rbp+var_58], 0FEB1C58Ah
0x18003a06c  mov     [rbp+var_54], 0E70806AEh
0x18003a073  lea     rdx, [rbp+var_50]
0x18003a077  lea     rcx, [rbp+var_40]
0x18003a07b  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003a080  mov     edi, 1
0x18003a085  mov     r9d, edi
0x18003a088  lea     r8, [rbp+var_60]
0x18003a08c  mov     rdx, rax
0x18003a08f  lea     rcx, [rbp+var_30]
0x18003a093  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x18003a098  nop
0x18003a099  mov     [rbp+arg_18], 0
0x18003a0a1  sub     ebx, edi
0x18003a0a3  jz      short loc_18003A0D2
0x18003a0a5  cmp     ebx, edi
0x18003a0a7  jnz     loc_18003A1E7
0x18003a0ad  lea     r8, [rbp+arg_18]; struct StateRepository::Statement *
0x18003a0b1  lea     rdx, aUpdateNonpacka_0; "UPDATE NonPackagedUsageHistory SET Labe"...
0x18003a0b8  mov     rbx, [rbp+var_50]
0x18003a0bc  mov     rcx, rbx; this
0x18003a0bf  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003a0c4  mov     rcx, [rbp+18h]; this
0x18003a0c8  test    eax, eax
0x18003a0ca  js      loc_18003A1B7
0x18003a0d0  jmp     short loc_18003A0F5
0x18003a0d2  lea     r8, [rbp+arg_18]; struct StateRepository::Statement *
0x18003a0d6  lea     rdx, aUpdatePackaged_0; "UPDATE PackagedUsageHistory SET Label=?"...
0x18003a0dd  mov     rbx, [rbp+var_50]
0x18003a0e1  mov     rcx, rbx; this
0x18003a0e4  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003a0e9  mov     rcx, [rbp+18h]; this
0x18003a0ed  test    eax, eax
0x18003a0ef  js      loc_18003A20A
0x18003a0f5  mov     r8d, r14d; int
0x18003a0f8  mov     edx, edi; int
0x18003a0fa  lea     rcx, [rbp+arg_18]; this
0x18003a0fe  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x18003a103  mov     rcx, [rbp+18h]; this
0x18003a107  test    eax, eax
0x18003a109  js      loc_18003A21F
0x18003a10f  mov     r8, rsi; __int64
0x18003a112  mov     edx, 2; int
0x18003a117  lea     rcx, [rbp+arg_18]; this
0x18003a11b  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18003a120  mov     rcx, [rbp+18h]; this
0x18003a124  test    eax, eax
0x18003a126  js      loc_18003A234
0x18003a12c  lea     rcx, [rbp+arg_18]; this
0x18003a130  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18003a135  mov     rcx, [rbp+18h]; this
0x18003a139  test    eax, eax
0x18003a13b  js      loc_18003A249
0x18003a141  lea     rdx, [rbp+arg_18]; struct StateRepository::Statement *
0x18003a145  mov     rcx, rbx; this
0x18003a148  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18003a14d  lea     rcx, [rbp+arg_18]; this
0x18003a151  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18003a156  mov     rcx, [rbp+18h]; this
0x18003a15a  test    eax, eax
0x18003a15c  js      short loc_18003A1A2
0x18003a15e  lea     rcx, [rbp+var_30]; this
0x18003a162  call    ?CommitTransaction@DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAAXXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::CommitTransaction(void)
0x18003a167  nop
0x18003a168  lea     rcx, [rbp+arg_18]; this
0x18003a16c  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18003a171  nop
0x18003a172  lea     rcx, [rbp+var_30]; this
0x18003a176  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x18003a17b  nop
0x18003a17c  mov     rcx, [rbp+var_48]; this
0x18003a180  test    rcx, rcx
0x18003a183  jz      short loc_18003A18A
0x18003a185  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003a18a  lea     r11, [rsp+80h+var_s0]
0x18003a192  mov     rbx, [r11+20h]
0x18003a196  mov     rsi, [r11+28h]
0x18003a19a  mov     rsp, r11
0x18003a19d  pop     r14
0x18003a19f  pop     rdi
0x18003a1a0  pop     rbp
0x18003a1a1  retn
0x18003a1a2  mov     r9d, eax; char *
0x18003a1a5  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a1ac  mov     edx, 998h; void *
0x18003a1b1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a1b7  mov     r9d, eax; char *
0x18003a1ba  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a1c1  mov     edx, 989h; void *
0x18003a1c6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a1cc  mov     r9d, 80004001h; char *
0x18003a1d2  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a1d9  mov     edx, 97Eh; void *
0x18003a1de  mov     rcx, rdi; this
0x18003a1e1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a1e7  mov     ecx, 8000FFFFh
0x18003a1ec  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18003a1f1  mov     r9d, eax; char *
0x18003a1f4  mov     rcx, [rbp+18h]; this
0x18003a1f8  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a1ff  mov     edx, 991h; void *
0x18003a204  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a20a  mov     r9d, eax; char *
0x18003a20d  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a214  mov     edx, 98Dh; void *
0x18003a219  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a21f  mov     r9d, eax; char *
0x18003a222  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a229  mov     edx, 994h; void *
0x18003a22e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a234  mov     r9d, eax; char *
0x18003a237  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a23e  mov     edx, 995h; void *
0x18003a243  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003a249  mov     r9d, eax; char *
0x18003a24c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003a253  mov     edx, 996h; void *
0x18003a258  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
