# Windows::Internal::CapabilityAccess::Private::SQL::GetAppDataForFileID(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::shared_ptr<StateRepository::Database>)

- ea: `0x180032d38`
- end: `0x180033022`
- name: `?GetAppDataForFileID@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AUInternalApp@12345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@VDatabase@StateRepository@@@8@@Z`
- size: `746`
- prototype: `__int64 __fastcall(Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *this)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x18004bd1c`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x180020fcc`
- `0x18002392c`
- `0x18002e704`
- `0x18002e9dc`
- `0x18002f93c`
- `0x18002f978`
- `0x180031698`
- `0x180032d38`
- `0x1800352d0`
- `0x1800363b4`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## string_xrefs

- `0x180032f5c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032f74`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032f8c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032fa4`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032fb9`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032fce`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032fe6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032ffb`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180033010`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180032ea8`: `BinaryFullPaths`
- `0x180032d9e`: `SELECT MAX(LastObservedTime), ProgramID, BinaryFullPath FROM NonPackagedIdentityRelationship  WHERE FileID=?;`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *__fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetAppDataForFileID(
        Windows::Internal::CapabilityAccess::Private::SQL::InternalApp *this,
        __int64 a2,
        unsigned __int64 a3)
{
  int v6; // eax
  __int64 v7; // rax
  __int64 KeyFromStringAndTableName; // rax
  int v9; // eax
  int Row; // eax
  int ColumnUInt64; // eax
  int v12; // eax
  int v13; // eax
  __int64 v14; // rax
  __int64 StringFromKeyAndTableName; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  std::_Ref_count_base *v18; // rcx
  int v20; // [rsp+20h] [rbp-49h] BYREF
  __int64 v21; // [rsp+28h] [rbp-41h] BYREF
  _BYTE v22[16]; // [rsp+30h] [rbp-39h] BYREF
  int v23; // [rsp+40h] [rbp-29h]
  unsigned __int64 v24; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v25[5]; // [rsp+50h] [rbp-19h] BYREF
  _BYTE v26[32]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v25[2] = (unsigned __int64)this;
  v25[4] = a3;
  v23 = 0;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(this) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x685,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v20);
  v21 = 0;
  v25[0] = 0;
  v24 = 0;
  v6 = StateRepository::Database::PrepareFromCache(
         *(StateRepository::Database **)a3,
         "SELECT MAX(LastObservedTime), ProgramID, BinaryFullPath FROM NonPackagedIdentityRelationship  WHERE FileID=?;",
         (struct StateRepository::Statement *)&v21);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x68B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v6,
      v20);
  v7 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
         v22,
         a3);
  KeyFromStringAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
                                a2,
                                "FileIDs",
                                v7,
                                0);
  if ( !KeyFromStringAndTableName )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x68F,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80070002LL,
      v20);
  LOBYTE(v20) = 0;
  v9 = StateRepository::Statement::Bind((StateRepository::Statement *)&v21, 1, KeyFromStringAndTableName);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x692,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v9,
      v20);
  Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v21, (bool *)&v20);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x693,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)Row,
      v20);
  if ( !(_BYTE)v20 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x694,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x8000FFFFLL,
      v20);
  ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v21, 1, v25);
  if ( ColumnUInt64 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x696,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)ColumnUInt64,
      v20);
  v12 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v21, 2, &v24);
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x697,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v12,
      v20);
  StateRepository::Database::AddToCache(*(StateRepository::Database **)a3, (struct StateRepository::Statement *)&v21);
  v13 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v21);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x69C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v13,
      v20);
  Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp(this);
  v23 = 1;
  v14 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          v22,
          a3);
  StringFromKeyAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(
                                v26,
                                v24,
                                "BinaryFullPaths",
                                v14);
  std::wstring::operator=(this, StringFromKeyAndTableName);
  std::wstring::_Tidy_deallocate(v26);
  std::wstring::operator=((char *)this + 160, a2);
  v16 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          v22,
          a3);
  v17 = Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(v26, v25[0], "ProgramIDs", v16);
  std::wstring::operator=((char *)this + 192, v17);
  std::wstring::_Tidy_deallocate(v26);
  *((_DWORD *)this + 64) = 2;
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v21);
  v18 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  return this;
}

```

## disassembly

```asm
0x180032d38  push    rbp
0x180032d3a  push    rbx
0x180032d3b  push    rsi
0x180032d3c  push    rdi
0x180032d3d  push    r14
0x180032d3f  lea     rbp, [rsp-37h]
0x180032d44  sub     rsp, 0A0h
0x180032d4b  mov     rax, cs:__security_cookie
0x180032d52  xor     rax, rsp
0x180032d55  mov     [rbp+57h+var_28], rax
0x180032d59  mov     rbx, r8
0x180032d5c  mov     r14, rdx
0x180032d5f  mov     rdi, rcx
0x180032d62  mov     [rbp+57h+var_60], rcx
0x180032d66  mov     [rbp+57h+var_50], rbx
0x180032d6a  mov     [rbp+57h+var_80], 0
0x180032d71  mov     rsi, [rbp+5Fh]
0x180032d75  call    ?DatabaseReady@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(void)
0x180032d7a  test    al, al
0x180032d7c  jz      loc_180032F6E
0x180032d82  mov     [rbp+57h+var_98], 0
0x180032d8a  mov     [rbp+57h+var_70], 0
0x180032d92  mov     [rbp+57h+var_78], 0
0x180032d9a  lea     r8, [rbp+57h+var_98]; struct StateRepository::Statement *
0x180032d9e  lea     rdx, aSelectMaxLasto; "SELECT MAX(LastObservedTime), ProgramID"...
0x180032da5  mov     rcx, [rbx]; this
0x180032da8  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180032dad  mov     rcx, [rbp+5Fh]; this
0x180032db1  test    eax, eax
0x180032db3  js      loc_180032F89
0x180032db9  mov     rdx, rbx
0x180032dbc  lea     rcx, [rbp+57h+var_90]
0x180032dc0  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180032dc5  xor     r9d, r9d
0x180032dc8  mov     r8, rax
0x180032dcb  lea     rdx, aFileids; "FileIDs"
0x180032dd2  mov     rcx, r14
0x180032dd5  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180032dda  mov     rcx, [rbp+5Fh]; this
0x180032dde  test    rax, rax
0x180032de1  jz      loc_180032F9E
0x180032de7  mov     byte ptr [rbp+57h+var_A0], 0
0x180032deb  mov     r8, rax; __int64
0x180032dee  mov     esi, 1
0x180032df3  mov     edx, esi; int
0x180032df5  lea     rcx, [rbp+57h+var_98]; this
0x180032df9  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180032dfe  mov     rcx, [rbp+5Fh]; this
0x180032e02  test    eax, eax
0x180032e04  js      loc_180032FB6
0x180032e0a  lea     rdx, [rbp+57h+var_A0]; bool *
0x180032e0e  lea     rcx, [rbp+57h+var_98]; this
0x180032e12  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180032e17  mov     rcx, [rbp+5Fh]; this
0x180032e1b  test    eax, eax
0x180032e1d  js      loc_180032FCB
0x180032e23  cmp     byte ptr [rbp+57h+var_A0], 0
0x180032e27  setz    al
0x180032e2a  mov     rcx, [rbp+5Fh]; this
0x180032e2e  test    al, al
0x180032e30  jnz     loc_180032FE0
0x180032e36  lea     r8, [rbp+57h+var_70]; unsigned __int64 *
0x180032e3a  mov     edx, esi; int
0x180032e3c  lea     rcx, [rbp+57h+var_98]; this
0x180032e40  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180032e45  mov     rcx, [rbp+5Fh]; this
0x180032e49  test    eax, eax
0x180032e4b  js      loc_180032FF8
0x180032e51  lea     r8, [rbp+57h+var_78]; unsigned __int64 *
0x180032e55  lea     edx, [rsi+1]; int
0x180032e58  lea     rcx, [rbp+57h+var_98]; this
0x180032e5c  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180032e61  mov     rcx, [rbp+5Fh]; this
0x180032e65  test    eax, eax
0x180032e67  js      loc_18003300D
0x180032e6d  lea     rdx, [rbp+57h+var_98]; struct StateRepository::Statement *
0x180032e71  mov     rcx, [rbx]; this
0x180032e74  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180032e79  lea     rcx, [rbp+57h+var_98]; this
0x180032e7d  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180032e82  mov     rcx, [rbp+5Fh]; this
0x180032e86  test    eax, eax
0x180032e88  js      loc_180032F59
0x180032e8e  mov     rcx, rdi; this
0x180032e91  call    ??0InternalApp@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::InternalApp::InternalApp(void)
0x180032e96  mov     [rbp+57h+var_80], esi
0x180032e99  mov     rdx, rbx
0x180032e9c  lea     rcx, [rbp+57h+var_90]
0x180032ea0  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180032ea5  mov     r9, rax
0x180032ea8  lea     r8, aBinaryfullpath; "BinaryFullPaths"
0x180032eaf  mov     rdx, [rbp+57h+var_78]
0x180032eb3  lea     rcx, [rbp+57h+var_48]
0x180032eb7  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180032ebc  mov     rdx, rax
0x180032ebf  mov     rcx, rdi
0x180032ec2  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032ec7  lea     rcx, [rbp+57h+var_48]
0x180032ecb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032ed0  lea     rcx, [rdi+0A0h]
0x180032ed7  mov     rdx, r14
0x180032eda  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180032edf  mov     rdx, rbx
0x180032ee2  lea     rcx, [rbp+57h+var_90]
0x180032ee6  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180032eeb  mov     r9, rax
0x180032eee  lea     r8, aProgramids; "ProgramIDs"
0x180032ef5  mov     rdx, [rbp+57h+var_70]
0x180032ef9  lea     rcx, [rbp+57h+var_48]
0x180032efd  call    ?GetStringFromKeyAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KQEBDV?$shared_ptr@VDatabase@StateRepository@@@7@@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetStringFromKeyAndTableName(unsigned __int64,char const * const,std::shared_ptr<StateRepository::Database>)
0x180032f02  lea     rcx, [rdi+0C0h]
0x180032f09  mov     rdx, rax
0x180032f0c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180032f11  lea     rcx, [rbp+57h+var_48]
0x180032f15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180032f1a  mov     dword ptr [rdi+100h], 2
0x180032f24  lea     rcx, [rbp+57h+var_98]; this
0x180032f28  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180032f2d  nop
0x180032f2e  mov     rcx, [rbx+8]; this
0x180032f32  test    rcx, rcx
0x180032f35  jz      short loc_180032F3C
0x180032f37  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032f3c  mov     rax, rdi
0x180032f3f  mov     rcx, [rbp+57h+var_28]
0x180032f43  xor     rcx, rsp; StackCookie
0x180032f46  call    __security_check_cookie
0x180032f4b  add     rsp, 0A0h
0x180032f52  pop     r14
0x180032f54  pop     rdi
0x180032f55  pop     rsi
0x180032f56  pop     rbx
0x180032f57  pop     rbp
0x180032f58  retn
0x180032f59  mov     r9d, eax; char *
0x180032f5c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032f63  mov     edx, 69Ch; void *
0x180032f68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032f6e  mov     r9d, 80004001h; char *
0x180032f74  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032f7b  mov     edx, 685h; void *
0x180032f80  mov     rcx, rsi; this
0x180032f83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032f89  mov     r9d, eax; char *
0x180032f8c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032f93  mov     edx, 68Bh; void *
0x180032f98  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032f9e  mov     r9d, 80070002h; char *
0x180032fa4  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032fab  mov     edx, 68Fh; void *
0x180032fb0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032fb6  mov     r9d, eax; char *
0x180032fb9  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032fc0  mov     edx, 692h; void *
0x180032fc5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032fcb  mov     r9d, eax; char *
0x180032fce  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032fd5  mov     edx, 693h; void *
0x180032fda  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032fe0  mov     r9d, 8000FFFFh; char *
0x180032fe6  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180032fed  mov     edx, 694h; void *
0x180032ff2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180032ff8  mov     r9d, eax; char *
0x180032ffb  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180033002  mov     edx, 696h; void *
0x180033007  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003300d  mov     r9d, eax; char *
0x180033010  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180033017  mov     edx, 697h; void *
0x18003301c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
