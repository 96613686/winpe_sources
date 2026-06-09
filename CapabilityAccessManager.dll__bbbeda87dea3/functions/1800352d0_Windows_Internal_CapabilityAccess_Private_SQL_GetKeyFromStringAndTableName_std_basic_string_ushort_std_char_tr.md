# Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)

- ea: `0x1800352d0`
- end: `0x1800355f5`
- name: `?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z`
- size: `805`
- prototype: ``
- caller_count: `11`
- callee_count: `19`
- tags: ``

## callers

- `0x18002fe74`
- `0x180031be0`
- `0x180031ef0`
- `0x180032d38`
- `0x180035bac`
- `0x18003684c`
- `0x180037690`
- `0x180039730`
- `0x18003a264`
- `0x18004bd1c`
- `0x18004c310`

## callees

- `0x1800094c0`
- `0x180020fcc`
- `0x18002392c`
- `0x1800293e8`
- `0x180029408`
- `0x180029450`
- `0x18002a32c`
- `0x180031698`
- `0x1800352d0`
- `0x1800a25e8`
- `0x1800a268c`
- `0x1800a2758`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a4280`
- `0x1800a4724`
- `0x1800a5520`

## string_xrefs

- `0x180035315`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035375`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800353b6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800353e4`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003541e`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035488`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800354ae`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x1800354f8`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180035529`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x18003554f`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
unsigned __int64 __fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        unsigned __int64 a2,
        unsigned __int64 a3,
        char a4)
{
  const char *v7; // rax
  int v8; // eax
  const wchar_t *v9; // rax
  int v10; // edx
  int v11; // eax
  int Row; // eax
  const char *v13; // rdx
  int ColumnUInt64; // eax
  std::_Ref_count_base *v15; // rcx
  int v17; // eax
  const char *v18; // rax
  int v19; // eax
  const wchar_t *v20; // rax
  int v21; // edx
  int v22; // eax
  int NoRow; // eax
  __int64 LastInsertRowID; // rdi
  std::_Ref_count_base *v25; // rcx
  std::_Ref_count_base *v26; // rcx
  int v27; // [rsp+20h] [rbp-49h] BYREF
  __int64 v28; // [rsp+28h] [rbp-41h] BYREF
  unsigned __int64 v29[4]; // [rsp+30h] [rbp-39h] BYREF
  char v30; // [rsp+50h] [rbp-19h]
  _BYTE v31[32]; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v32[32]; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v29[0] = a2;
  v29[1] = a3;
  if ( !Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24A,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v27);
  if ( *((_QWORD *)a1 + 2) )
  {
    v28 = 0;
    Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(
      v31,
      "SELECT ID FROM %s WHERE StringValue=?;",
      (const char *)v29);
    v7 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v31);
    v8 = StateRepository::Database::PrepareFromCache(
           *(StateRepository::Database **)a3,
           v7,
           (struct StateRepository::Statement *)&v28);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x256,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v8,
        v27);
    v29[2] = a3;
    v29[3] = (unsigned __int64)&v28;
    v30 = 1;
    v9 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
    v11 = StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v10, v9);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v11,
        v27);
    LOBYTE(v27) = 0;
    Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)&v28, (bool *)&v27);
    if ( Row < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x260,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)Row,
        v27);
    if ( (_BYTE)v27 )
    {
      v29[0] = 0;
      ColumnUInt64 = StateRepository::Statement::GetColumnUInt64((StateRepository::Statement *)&v28, 0, v29);
      if ( ColumnUInt64 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x266,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)ColumnUInt64,
          v27);
      StateRepository::Database::AddToCache(
        *(StateRepository::Database **)a3,
        (struct StateRepository::Statement *)&v28);
      std::string::_Tidy_deallocate(v31);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v28);
      v15 = *(std::_Ref_count_base **)(a3 + 8);
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
      return v29[0];
    }
    if ( (a4 & 1) != 0 )
    {
      if ( StateRepository::Database::IsReadOnly(*(StateRepository::Database **)a3, v13) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26B,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)0x80070005LL,
          v27);
      v17 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v28);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26F,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v17,
          v27);
      Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(
        v32,
        "INSERT INTO %s (StringValue) VALUES (?);",
        (const char *)v29);
      v18 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(v32);
      v19 = StateRepository::Database::PrepareFromCache(
              *(StateRepository::Database **)a3,
              v18,
              (struct StateRepository::Statement *)&v28);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x274,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v19,
          v27);
      v20 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
      v22 = StateRepository::Statement::Bind((StateRepository::Statement *)&v28, v21, v20);
      if ( v22 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x275,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)v22,
          v27);
      NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v28);
      if ( NoRow < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x278,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
          (const char *)(unsigned int)NoRow,
          v27);
      LastInsertRowID = StateRepository::Database::GetLastInsertRowID(*(StateRepository::Database **)a3);
      std::string::_Tidy_deallocate(v32);
      StateRepository::Database::AddToCache(
        *(StateRepository::Database **)a3,
        (struct StateRepository::Statement *)&v28);
      std::string::_Tidy_deallocate(v31);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v28);
      v25 = *(std::_Ref_count_base **)(a3 + 8);
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
      return LastInsertRowID;
    }
    StateRepository::Database::AddToCache(*(StateRepository::Database **)a3, (struct StateRepository::Statement *)&v28);
    std::string::_Tidy_deallocate(v31);
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v28);
  }
  v26 = *(std::_Ref_count_base **)(a3 + 8);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  return 0;
}

```

## disassembly

```asm
0x1800352d0  push    rbp
0x1800352d2  push    rbx
0x1800352d3  push    rsi
0x1800352d4  push    rdi
0x1800352d5  push    r14
0x1800352d7  lea     rbp, [rsp-37h]
0x1800352dc  sub     rsp, 0A0h
0x1800352e3  mov     rax, cs:__security_cookie
0x1800352ea  xor     rax, rsp
0x1800352ed  mov     [rbp+57h+var_28], rax
0x1800352f1  mov     r14d, r9d
0x1800352f4  mov     rbx, r8
0x1800352f7  mov     rdi, rcx
0x1800352fa  mov     [rbp+57h+var_90], rdx
0x1800352fe  mov     [rbp+57h+var_88], rbx
0x180035302  mov     rsi, [rbp+5Fh]
0x180035306  call    ?DatabaseReady@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseReady(void)
0x18003530b  test    al, al
0x18003530d  jnz     short loc_18003532A
0x18003530f  mov     r9d, 80004001h; char *
0x180035315  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003531c  mov     edx, 24Ah; void *
0x180035321  mov     rcx, rsi; this
0x180035324  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003532a  cmp     qword ptr [rdi+10h], 0
0x18003532f  jz      loc_1800355CB
0x180035335  mov     [rbp+57h+var_98], 0
0x18003533d  lea     r8, [rbp+57h+var_90]
0x180035341  lea     rdx, aSelectIdFromSW; "SELECT ID FROM %s WHERE StringValue=?;"
0x180035348  lea     rcx, [rbp+57h+var_68]
0x18003534c  call    ??$FormatUTF8Statement@PEBD@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBD$$QEAPEBD@Z; Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(char const * const,char const * &&)
0x180035351  nop
0x180035352  lea     rcx, [rbp+57h+var_68]
0x180035356  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x18003535b  mov     rdx, rax; char *
0x18003535e  lea     r8, [rbp+57h+var_98]; struct StateRepository::Statement *
0x180035362  mov     rcx, [rbx]; this
0x180035365  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18003536a  mov     rcx, [rbp+5Fh]; this
0x18003536e  test    eax, eax
0x180035370  jns     short loc_180035387
0x180035372  mov     r9d, eax; char *
0x180035375  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003537c  mov     edx, 256h; void *
0x180035381  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035387  mov     [rbp+57h+var_80], rbx
0x18003538b  lea     rax, [rbp+57h+var_98]
0x18003538f  mov     [rbp+57h+var_78], rax
0x180035393  mov     [rbp+57h+var_70], 1
0x180035397  mov     rcx, rdi
0x18003539a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003539f  mov     r8, rax; wchar_t *
0x1800353a2  lea     rcx, [rbp+57h+var_98]; this
0x1800353a6  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x1800353ab  mov     rcx, [rbp+5Fh]; this
0x1800353af  test    eax, eax
0x1800353b1  jns     short loc_1800353C8
0x1800353b3  mov     r9d, eax; char *
0x1800353b6  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800353bd  mov     edx, 25Dh; void *
0x1800353c2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800353c8  mov     byte ptr [rbp+57h+var_A0], 0
0x1800353cc  lea     rdx, [rbp+57h+var_A0]; bool *
0x1800353d0  lea     rcx, [rbp+57h+var_98]; this
0x1800353d4  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x1800353d9  mov     rcx, [rbp+5Fh]; this
0x1800353dd  test    eax, eax
0x1800353df  jns     short loc_1800353F6
0x1800353e1  mov     r9d, eax; char *
0x1800353e4  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800353eb  mov     edx, 260h; void *
0x1800353f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800353f6  cmp     byte ptr [rbp+57h+var_A0], 0
0x1800353fa  jz      short loc_180035468
0x1800353fc  mov     [rbp+57h+var_90], 0
0x180035404  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x180035408  xor     edx, edx; int
0x18003540a  lea     rcx, [rbp+57h+var_98]; this
0x18003540e  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180035413  mov     rcx, [rbp+5Fh]; this
0x180035417  test    eax, eax
0x180035419  jns     short loc_180035430
0x18003541b  mov     r9d, eax; char *
0x18003541e  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180035425  mov     edx, 266h; void *
0x18003542a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035430  lea     rdx, [rbp+57h+var_98]; struct StateRepository::Statement *
0x180035434  mov     rcx, [rbx]; this
0x180035437  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18003543c  nop
0x18003543d  lea     rcx, [rbp+57h+var_68]
0x180035441  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035446  nop
0x180035447  lea     rcx, [rbp+57h+var_98]; this
0x18003544b  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180035450  nop
0x180035451  mov     rcx, [rbx+8]; this
0x180035455  test    rcx, rcx
0x180035458  jz      short loc_18003545F
0x18003545a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003545f  mov     rax, [rbp+57h+var_90]
0x180035463  jmp     loc_1800355DB
0x180035468  test    r14b, 1
0x18003546c  jz      loc_1800355AA
0x180035472  mov     rcx, [rbx]; this
0x180035475  call    ?IsReadOnly@Database@StateRepository@@QEAA_NPEBD@Z; StateRepository::Database::IsReadOnly(char const *)
0x18003547a  mov     rcx, [rbp+5Fh]; this
0x18003547e  test    al, al
0x180035480  jz      short loc_18003549A
0x180035482  mov     r9d, 80070005h; char *
0x180035488  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x18003548f  mov     edx, 26Bh; void *
0x180035494  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003549a  lea     rcx, [rbp+57h+var_98]; this
0x18003549e  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x1800354a3  mov     rcx, [rbp+5Fh]; this
0x1800354a7  test    eax, eax
0x1800354a9  jns     short loc_1800354C0
0x1800354ab  mov     r9d, eax; char *
0x1800354ae  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800354b5  mov     edx, 26Fh; void *
0x1800354ba  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800354c0  lea     r8, [rbp+57h+var_90]
0x1800354c4  lea     rdx, aInsertIntoSStr; "INSERT INTO %s (StringValue) VALUES (?)"...
0x1800354cb  lea     rcx, [rbp+57h+var_48]
0x1800354cf  call    ??$FormatUTF8Statement@PEBD@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBD$$QEAPEBD@Z; Windows::Internal::CapabilityAccess::Private::SQL::FormatUTF8Statement<char const *>(char const * const,char const * &&)
0x1800354d4  nop
0x1800354d5  lea     rcx, [rbp+57h+var_48]
0x1800354d9  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x1800354de  mov     rdx, rax; char *
0x1800354e1  lea     r8, [rbp+57h+var_98]; struct StateRepository::Statement *
0x1800354e5  mov     rcx, [rbx]; this
0x1800354e8  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x1800354ed  mov     rcx, [rbp+5Fh]; this
0x1800354f1  test    eax, eax
0x1800354f3  jns     short loc_18003550A
0x1800354f5  mov     r9d, eax; char *
0x1800354f8  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800354ff  mov     edx, 274h; void *
0x180035504  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003550a  mov     rcx, rdi
0x18003550d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180035512  mov     r8, rax; wchar_t *
0x180035515  lea     rcx, [rbp+57h+var_98]; this
0x180035519  call    ?Bind@Statement@StateRepository@@QEAAJHPEB_W@Z; StateRepository::Statement::Bind(int,wchar_t const *)
0x18003551e  mov     rcx, [rbp+5Fh]; this
0x180035522  test    eax, eax
0x180035524  jns     short loc_18003553B
0x180035526  mov     r9d, eax; char *
0x180035529  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180035530  mov     edx, 275h; void *
0x180035535  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003553b  lea     rcx, [rbp+57h+var_98]; this
0x18003553f  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x180035544  mov     rcx, [rbp+5Fh]; this
0x180035548  test    eax, eax
0x18003554a  jns     short loc_180035561
0x18003554c  mov     r9d, eax; char *
0x18003554f  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180035556  mov     edx, 278h; void *
0x18003555b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180035561  mov     rcx, [rbx]; this
0x180035564  call    ?GetLastInsertRowID@Database@StateRepository@@QEBA_JXZ; StateRepository::Database::GetLastInsertRowID(void)
0x180035569  mov     rdi, rax
0x18003556c  lea     rcx, [rbp+57h+var_48]
0x180035570  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035575  nop
0x180035576  lea     rdx, [rbp+57h+var_98]; struct StateRepository::Statement *
0x18003557a  mov     rcx, [rbx]; this
0x18003557d  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180035582  nop
0x180035583  lea     rcx, [rbp+57h+var_68]
0x180035587  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003558c  nop
0x18003558d  lea     rcx, [rbp+57h+var_98]; this
0x180035591  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180035596  nop
0x180035597  mov     rcx, [rbx+8]; this
0x18003559b  test    rcx, rcx
0x18003559e  jz      short loc_1800355A5
0x1800355a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800355a5  mov     rax, rdi
0x1800355a8  jmp     short loc_1800355DB
0x1800355aa  lea     rdx, [rbp+57h+var_98]; struct StateRepository::Statement *
0x1800355ae  mov     rcx, [rbx]; this
0x1800355b1  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x1800355b6  nop
0x1800355b7  lea     rcx, [rbp+57h+var_68]
0x1800355bb  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800355c0  nop
0x1800355c1  lea     rcx, [rbp+57h+var_98]; this
0x1800355c5  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800355ca  nop
0x1800355cb  mov     rcx, [rbx+8]; this
0x1800355cf  test    rcx, rcx
0x1800355d2  jz      short loc_1800355D9
0x1800355d4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800355d9  xor     eax, eax
0x1800355db  mov     rcx, [rbp+57h+var_28]
0x1800355df  xor     rcx, rsp; StackCookie
0x1800355e2  call    __security_check_cookie
0x1800355e7  add     rsp, 0A0h
0x1800355ee  pop     r14
0x1800355f0  pop     rdi
0x1800355f1  pop     rsi
0x1800355f2  pop     rbx
0x1800355f3  pop     rbp
0x1800355f4  retn
```
