# Windows::Internal::CapabilityAccess::Private::SQL::GetAccessGUIDByTypeAndRowID(Windows::Internal::CapabilityAccess::UsageHistory::AppType,unsigned __int64)

- ea: `0x1800318bc`
- end: `0x180031b27`
- name: `?GetAccessGUIDByTypeAndRowID@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4AppType@UsageHistory@345@_K@Z`
- size: `619`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x1800911c0`

## callees

- `0x180016490`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x1800318bc`
- `0x1800363b4`
- `0x180037460`
- `0x180039a1c`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x180031a6e`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031a83`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031a9b`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031ac1`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031ad6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031aeb`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031b00`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031b15`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180031975`: `SELECT AccessGUID From PackagedUsageHistory WHERE ID=?; `
- `0x180031950`: `SELECT AccessGUID FROM NonPackagedUsageHistory WHERE ID=?; `
- `0x180031a1a`: `AccessGUIDs`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Windows::Internal::CapabilityAccess::Private::SQL *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetAccessGUIDByTypeAndRowID(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        int a2,
        __int64 a3)
{
  _QWORD *v6; // rax
  int v7; // ebx
  StateRepository::Database *v8; // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int Row; // eax
  int ColumnUInt64; // eax
  int v14; // eax
  __int64 v15; // rax
  unsigned int v17; // eax
  int v18[4]; // [rsp+20h] [rbp-39h] BYREF
  struct _GUID v19; // [rsp+30h] [rbp-29h] BYREF
  StateRepository::Database *v20; // [rsp+40h] [rbp-19h] BYREF
  std::_Ref_count_base *v21; // [rsp+48h] [rbp-11h]
  _BYTE v22[16]; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v23[56]; // [rsp+68h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  unsigned __int64 v25; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE83,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v18[0]);
  std::make_shared<StateRepository::Database,>(&v20);
  *(_QWORD *)v18 = 0;
  v19.Data1 = 846342647;
  *(_DWORD *)&v19.Data2 = 1287176247;
  *(_DWORD *)v19.Data4 = 702582967;
  *(_DWORD *)&v19.Data4[4] = -981995655;
  v6 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                   v22,
                   &v20);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
    (Windows::Internal::CapabilityAccess::Private::SQL *)v23,
    v6,
    &v19,
    0);
  v7 = a2 - 1;
  if ( v7 )
  {
    if ( v7 != 1 )
    {
      v17 = wil::verify_hresult<long>(2147942487LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE94,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)v17,
        v18[0]);
    }
    v8 = v20;
    v9 = StateRepository::Database::PrepareFromCache(
           v20,
           "SELECT AccessGUID FROM NonPackagedUsageHistory WHERE ID=?; ",
           (struct StateRepository::Statement *)v18);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE8E,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v9,
        v18[0]);
  }
  else
  {
    v8 = v20;
    v10 = StateRepository::Database::PrepareFromCache(
            v20,
            "SELECT AccessGUID From PackagedUsageHistory WHERE ID=?; ",
            (struct StateRepository::Statement *)v18);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE91,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v10,
        v18[0]);
  }
  v11 = StateRepository::Statement::Bind((StateRepository::Statement *)v18, 1, a3);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE97,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v11,
      v18[0]);
  Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)v18, (bool *)&v25);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)Row,
      v18[0]);
  v25 = 0;
  ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)v18, 0, &v25);
  if ( ColumnUInt64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9D,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v18[0]);
  StateRepository::Database::AddToCache(v8, (struct StateRepository::Statement *)v18);
  v14 = StateRepository::Statement::Finalize((StateRepository::Statement *)v18);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xE9F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v14,
      v18[0]);
  v15 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          &v19,
          &v20);
  Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(a1, v25, "AccessGUIDs", v15);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v23);
  StateRepository::Statement::~Statement((StateRepository::Statement *)v18);
  if ( v21 )
    std::_Ref_count_base::_Decref(v21);
  return a1;
}

```

## disassembly

```asm
0x1800318bc  mov     [rsp-8+arg_0], rbx
0x1800318c1  mov     [rsp-8+arg_8], rsi
0x1800318c6  push    rbp
0x1800318c7  push    rdi
0x1800318c8  push    r14
0x1800318ca  lea     rbp, [rsp-47h]
0x1800318cf  sub     rsp, 0A0h
0x1800318d6  mov     r14, r8
0x1800318d9  mov     ebx, edx
0x1800318db  mov     rdi, rcx
0x1800318de  mov     rsi, [rbp+5Fh]
0x1800318e2  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x1800318e7  test    al, al
0x1800318e9  jz      loc_180031A95
0x1800318ef  lea     rcx, [rbp+57h+var_70]
0x1800318f3  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x1800318f8  nop
0x1800318f9  mov     qword ptr [rbp+57h+var_90], 0
0x180031901  mov     [rbp+57h+var_80], 327229F7h
0x180031908  mov     [rbp+57h+var_7C], 4CB8C037h
0x18003190f  mov     [rbp+57h+var_78], 29E090B7h
0x180031916  mov     [rbp+57h+var_74], 0C577EF79h
0x18003191d  lea     rdx, [rbp+57h+var_70]
0x180031921  lea     rcx, [rbp+57h+var_58]
0x180031925  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003192a  xor     r9d, r9d
0x18003192d  lea     r8, [rbp+57h+var_80]
0x180031931  mov     rdx, rax
0x180031934  lea     rcx, [rbp+57h+var_48]
0x180031938  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x18003193d  nop
0x18003193e  sub     ebx, 1
0x180031941  jz      short loc_180031971
0x180031943  cmp     ebx, 1
0x180031946  jnz     loc_180031AB0
0x18003194c  lea     r8, [rbp+57h+var_90]; struct StateRepository::Statement *
0x180031950  lea     rdx, aSelectAccessgu; "SELECT AccessGUID FROM NonPackagedUsage"...
0x180031957  mov     rbx, [rbp+57h+var_70]
0x18003195b  mov     rcx, rbx; this
0x18003195e  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180031963  mov     rcx, [rbp+5Fh]; this
0x180031967  test    eax, eax
0x180031969  js      loc_180031A80
0x18003196f  jmp     short loc_180031994
0x180031971  lea     r8, [rbp+57h+var_90]; struct StateRepository::Statement *
0x180031975  lea     rdx, aSelectAccessgu_0; "SELECT AccessGUID From PackagedUsageHis"...
0x18003197c  mov     rbx, [rbp+57h+var_70]
0x180031980  mov     rcx, rbx; this
0x180031983  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180031988  mov     rcx, [rbp+5Fh]; this
0x18003198c  test    eax, eax
0x18003198e  js      loc_180031AD3
0x180031994  mov     r8, r14; __int64
0x180031997  mov     edx, 1; int
0x18003199c  lea     rcx, [rbp+57h+var_90]; this
0x1800319a0  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800319a5  mov     rcx, [rbp+5Fh]; this
0x1800319a9  test    eax, eax
0x1800319ab  js      loc_180031AE8
0x1800319b1  lea     rdx, [rbp+57h+arg_18]; bool *
0x1800319b5  lea     rcx, [rbp+57h+var_90]; this
0x1800319b9  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800319be  mov     rcx, [rbp+5Fh]; this
0x1800319c2  test    eax, eax
0x1800319c4  js      loc_180031AFD
0x1800319ca  mov     [rbp+57h+arg_18], 0
0x1800319d2  lea     r8, [rbp+57h+arg_18]; unsigned __int64 *
0x1800319d6  xor     edx, edx; int
0x1800319d8  lea     rcx, [rbp+57h+var_90]; this
0x1800319dc  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x1800319e1  mov     rcx, [rbp+5Fh]; this
0x1800319e5  test    eax, eax
0x1800319e7  js      loc_180031B12
0x1800319ed  lea     rdx, [rbp+57h+var_90]; struct StateRepository::Statement *
0x1800319f1  mov     rcx, rbx; this
0x1800319f4  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800319f9  lea     rcx, [rbp+57h+var_90]; this
0x1800319fd  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180031a02  mov     rcx, [rbp+5Fh]; this
0x180031a06  test    eax, eax
0x180031a08  js      short loc_180031A6B
0x180031a0a  lea     rdx, [rbp+57h+var_70]
0x180031a0e  lea     rcx, [rbp+57h+var_80]
0x180031a12  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180031a17  mov     r9, rax
0x180031a1a  lea     r8, aAccessguids; "AccessGUIDs"
0x180031a21  mov     rdx, [rbp+57h+arg_18]
0x180031a25  mov     rcx, rdi
0x180031a28  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180031a2d  nop
0x180031a2e  lea     rcx, [rbp+57h+var_48]; this
0x180031a32  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x180031a37  nop
0x180031a38  lea     rcx, [rbp+57h+var_90]; this
0x180031a3c  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180031a41  nop
0x180031a42  mov     rcx, [rbp+57h+var_68]; this
0x180031a46  test    rcx, rcx
0x180031a49  jz      short loc_180031A50
0x180031a4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180031a50  mov     rax, rdi
0x180031a53  lea     r11, [rsp+0B0h+var_10]
0x180031a5b  mov     rbx, [r11+20h]
0x180031a5f  mov     rsi, [r11+28h]
0x180031a63  mov     rsp, r11
0x180031a66  pop     r14
0x180031a68  pop     rdi
0x180031a69  pop     rbp
0x180031a6a  retn
0x180031a6b  mov     r9d, eax; char *
0x180031a6e  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031a75  mov     edx, 0E9Fh; void *
0x180031a7a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031a80  mov     r9d, eax; char *
0x180031a83  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031a8a  mov     edx, 0E8Eh; void *
0x180031a8f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031a95  mov     r9d, 80004001h; char *
0x180031a9b  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031aa2  mov     edx, 0E83h; void *
0x180031aa7  mov     rcx, rsi; this
0x180031aaa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031ab0  mov     ecx, 80070057h
0x180031ab5  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180031aba  mov     r9d, eax; char *
0x180031abd  mov     rcx, [rbp+5Fh]; this
0x180031ac1  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031ac8  mov     edx, 0E94h; void *
0x180031acd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031ad3  mov     r9d, eax; char *
0x180031ad6  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031add  mov     edx, 0E91h; void *
0x180031ae2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031ae8  mov     r9d, eax; char *
0x180031aeb  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031af2  mov     edx, 0E97h; void *
0x180031af7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031afd  mov     r9d, eax; char *
0x180031b00  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031b07  mov     edx, 0E9Ah; void *
0x180031b0c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180031b12  mov     r9d, eax; char *
0x180031b15  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180031b1c  mov     edx, 0E9Dh; void *
0x180031b21  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
