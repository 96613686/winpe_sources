# Windows::Internal::CapabilityAccess::Private::SQL::GetUsageFrequency(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::AppIdType,uint)

- ea: `0x18003684c`
- end: `0x180036be2`
- name: `?GetUsageFrequency@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@I@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation`

## callers

- `0x180048784`

## callees

- `0x180016490`
- `0x180020fcc`
- `0x18002392c`
- `0x18002d638`
- `0x18002e704`
- `0x18002f560`
- `0x1800352d0`
- `0x18003684c`
- `0x180037460`
- `0x180039a1c`
- `0x1800a25e8`
- `0x1800a26e8`
- `0x1800a27a4`
- `0x1800a2800`
- `0x1800a2b30`
- `0x1800a3804`
- `0x1800a5520`

## import_xrefs

- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180036a1d`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180036a1d`

## string_xrefs

- `0x180036aea`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036aff`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b17`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b3d`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b52`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b67`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b7c`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036b91`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036ba6`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036bbb`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036bd0`: `onecore\base\devices\cam\core\capabilityaccessmanagersql.cpp`
- `0x180036951`: `SELECT COUNT(*) FROM NonPackagedUsageHistory WHERE UserSid=? AND Capability=? AND BinaryFullPath=? AND LastUsedTimeStart>?; `
- `0x18003699b`: `SELECT COUNT(*) FROM PackagedUsageHistory WHERE UserSid=? AND Capability=? AND PackageFamilyName=? AND LastUsedTimeStart>?; `
- `0x18003693b`: `BinaryFullPaths`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::SQL::GetUsageFrequency(
        Windows::Internal::CapabilityAccess::Private::SQL *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        bool a5)
{
  _QWORD *v9; // rax
  __int64 v10; // rax
  __int64 KeyFromStringAndTableName; // r15
  __int64 v12; // rax
  __int64 v13; // r14
  int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rbx
  StateRepository::Database *v17; // rdi
  int v18; // eax
  __int64 v19; // rax
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rbx
  int Row; // eax
  int ColumnUInt64; // eax
  int v28; // eax
  unsigned int v30; // eax
  int v31[4]; // [rsp+20h] [rbp-51h] BYREF
  struct _GUID UnbiasedTime; // [rsp+30h] [rbp-41h] BYREF
  StateRepository::Database *v33; // [rsp+40h] [rbp-31h] BYREF
  std::_Ref_count_base *v34; // [rsp+48h] [rbp-29h]
  _BYTE v35[16]; // [rsp+50h] [rbp-21h] BYREF
  _BYTE v36[96]; // [rsp+60h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+57h]

  if ( !Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(a1) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9AA,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)0x80004001LL,
      v31[0]);
  std::make_shared<StateRepository::Database,>(&v33);
  *(_QWORD *)&UnbiasedTime.Data1 = 0x41C0CC94A511E616LL;
  *(_DWORD *)UnbiasedTime.Data4 = -686863721;
  *(_DWORD *)&UnbiasedTime.Data4[4] = -1172498986;
  v9 = (_QWORD *)std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
                   v35,
                   &v33);
  Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(
    (Windows::Internal::CapabilityAccess::Private::SQL *)v36,
    v9,
    &UnbiasedTime,
    1);
  *(_QWORD *)v31 = 0;
  v10 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          v35,
          &v33);
  KeyFromStringAndTableName = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
                                a1,
                                "Users",
                                v10,
                                0);
  v12 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
          v35,
          &v33);
  v13 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(a2, "Capabilities", v12, 0);
  v14 = a4 - 1;
  if ( v14 )
  {
    if ( v14 != 1 )
    {
      v30 = wil::verify_hresult<long>(2147549183LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9C3,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)v30,
        v31[0]);
    }
    v15 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
            v35,
            &v33);
    v16 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(a3, "BinaryFullPaths", v15, 0);
    v17 = v33;
    v18 = StateRepository::Database::PrepareFromCache(
            v33,
            "SELECT COUNT(*) FROM NonPackagedUsageHistory WHERE UserSid=? AND Capability=? AND BinaryFullPath=? AND LastU"
            "sedTimeStart>?; ",
            (struct StateRepository::Statement *)v31);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9BF,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v18,
        v31[0]);
  }
  else
  {
    v19 = std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(
            v35,
            &v33);
    v16 = Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(
            a3,
            "PackageFamilyNames",
            v19,
            0);
    v17 = v33;
    v20 = StateRepository::Database::PrepareFromCache(
            v33,
            "SELECT COUNT(*) FROM PackagedUsageHistory WHERE UserSid=? AND Capability=? AND PackageFamilyName=? AND LastU"
            "sedTimeStart>?; ",
            (struct StateRepository::Statement *)v31);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9BA,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)v20,
        v31[0]);
  }
  v21 = StateRepository::Statement::Bind((StateRepository::Statement *)v31, 1, KeyFromStringAndTableName);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C6,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v21,
      v31[0]);
  v22 = StateRepository::Statement::Bind((StateRepository::Statement *)v31, 2, v13);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C7,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v22,
      v31[0]);
  v23 = StateRepository::Statement::Bind((StateRepository::Statement *)v31, 3, v16);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v23,
      v31[0]);
  *(_QWORD *)&UnbiasedTime.Data1 = 0;
  QueryUnbiasedInterruptTime((PULONGLONG)&UnbiasedTime.Data1);
  v24 = StateRepository::Statement::Bind(
          (StateRepository::Statement *)v31,
          4,
          *(_QWORD *)&UnbiasedTime.Data1 - 24192000000000LL);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C9,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v24,
      v31[0]);
  a5 = 0;
  v25 = 0;
  *(_QWORD *)&UnbiasedTime.Data1 = 0;
  Row = StateRepository::Statement::FetchRow((StateRepository::Statement *)v31, &a5);
  if ( Row < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9CE,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)Row,
      v31[0]);
  if ( a5 )
  {
    ColumnUInt64 = StateRepository::Statement::GetColumnUInt64(
                     (StateRepository::Statement *)v31,
                     0,
                     (unsigned __int64 *)&UnbiasedTime.Data1);
    if ( ColumnUInt64 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9D2,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
        (const char *)(unsigned int)ColumnUInt64,
        v31[0]);
    v25 = *(_QWORD *)&UnbiasedTime.Data1;
  }
  StateRepository::Database::AddToCache(v17, (struct StateRepository::Statement *)v31);
  v28 = StateRepository::Statement::Finalize((StateRepository::Statement *)v31);
  if ( v28 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9D6,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanagersql.cpp",
      (const char *)(unsigned int)v28,
      v31[0]);
  StateRepository::Statement::~Statement((StateRepository::Statement *)v31);
  Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper((Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper *)v36);
  if ( v34 )
    std::_Ref_count_base::_Decref(v34);
  return v25;
}

```

## disassembly

```asm
0x18003684c  push    rbp
0x18003684e  push    rbx
0x18003684f  push    rsi
0x180036850  push    rdi
0x180036851  push    r14
0x180036853  push    r15
0x180036855  lea     rbp, [rsp-27h]
0x18003685a  sub     rsp, 98h
0x180036861  mov     ebx, r9d
0x180036864  mov     rsi, r8
0x180036867  mov     r14, rdx
0x18003686a  mov     r15, rcx
0x18003686d  mov     rdi, [rbp+57h]
0x180036871  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180036876  test    al, al
0x180036878  jz      loc_180036B11
0x18003687e  lea     rcx, [rbp+4Fh+var_80]
0x180036882  call    ??$make_shared@VDatabase@StateRepository@@$$V@std@@YA?AV?$shared_ptr@VDatabase@StateRepository@@@0@XZ; std::make_shared<StateRepository::Database,>(void)
0x180036887  nop
0x180036888  mov     dword ptr [rbp+4Fh+UnbiasedTime], 0A511E616h
0x18003688f  mov     dword ptr [rbp+4Fh+UnbiasedTime+4], 41C0CC94h
0x180036896  mov     [rbp+4Fh+var_88], 0D70F4A97h
0x18003689d  mov     [rbp+4Fh+var_84], 0BA1D15D6h
0x1800368a4  lea     rdx, [rbp+4Fh+var_80]
0x1800368a8  lea     rcx, [rbp+4Fh+var_70]
0x1800368ac  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800368b1  mov     r9d, 1
0x1800368b7  lea     r8, [rbp+4Fh+UnbiasedTime]
0x1800368bb  mov     rdx, rax
0x1800368be  lea     rcx, [rbp+4Fh+var_60]
0x1800368c2  call    ?OpenCAMDatabase@SQL@Private@CapabilityAccess@Internal@Windows@@YA?AVDatabaseScopeHelper@12345@V?$shared_ptr@VDatabase@StateRepository@@@std@@U_GUID@@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::OpenCAMDatabase(std::shared_ptr<StateRepository::Database>,_GUID,uint)
0x1800368c7  nop
0x1800368c8  mov     qword ptr [rbp+4Fh+var_A0], 0
0x1800368d0  lea     rdx, [rbp+4Fh+var_80]
0x1800368d4  lea     rcx, [rbp+4Fh+var_70]
0x1800368d8  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x1800368dd  xor     r9d, r9d
0x1800368e0  mov     r8, rax
0x1800368e3  lea     rdx, aUsers; "Users"
0x1800368ea  mov     rcx, r15
0x1800368ed  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x1800368f2  mov     r15, rax
0x1800368f5  lea     rdx, [rbp+4Fh+var_80]
0x1800368f9  lea     rcx, [rbp+4Fh+var_70]
0x1800368fd  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180036902  xor     r9d, r9d
0x180036905  mov     r8, rax
0x180036908  lea     rdx, aCapabilities_0; "Capabilities"
0x18003690f  mov     rcx, r14
0x180036912  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180036917  mov     r14, rax
0x18003691a  sub     ebx, 1
0x18003691d  jz      short loc_180036972
0x18003691f  cmp     ebx, 1
0x180036922  jnz     loc_180036B2C
0x180036928  lea     rdx, [rbp+4Fh+var_80]
0x18003692c  lea     rcx, [rbp+4Fh+var_70]
0x180036930  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x180036935  xor     r9d, r9d
0x180036938  mov     r8, rax
0x18003693b  lea     rdx, aBinaryfullpath; "BinaryFullPaths"
0x180036942  mov     rcx, rsi
0x180036945  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x18003694a  mov     rbx, rax
0x18003694d  lea     r8, [rbp+4Fh+var_A0]; struct StateRepository::Statement *
0x180036951  lea     rdx, aSelectCountFro_3; "SELECT COUNT(*) FROM NonPackagedUsageHi"...
0x180036958  mov     rdi, [rbp+4Fh+var_80]
0x18003695c  mov     rcx, rdi; this
0x18003695f  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x180036964  mov     rcx, [rbp+57h]; this
0x180036968  test    eax, eax
0x18003696a  js      loc_180036AFC
0x180036970  jmp     short loc_1800369BA
0x180036972  lea     rdx, [rbp+4Fh+var_80]
0x180036976  lea     rcx, [rbp+4Fh+var_70]
0x18003697a  call    ??0?$shared_ptr@VCapabilityUsageSession@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession>(std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityUsageSession> const &)
0x18003697f  xor     r9d, r9d
0x180036982  mov     r8, rax
0x180036985  lea     rdx, aPackagefamilyn_0; "PackageFamilyNames"
0x18003698c  mov     rcx, rsi
0x18003698f  call    ?GetKeyFromStringAndTableName@SQL@Private@CapabilityAccess@Internal@Windows@@YA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBDV?$shared_ptr@VDatabase@StateRepository@@@7@I@Z; Windows::Internal::CapabilityAccess::Private::SQL::GetKeyFromStringAndTableName(std::wstring const &,char const * const,std::shared_ptr<StateRepository::Database>,uint)
0x180036994  mov     rbx, rax
0x180036997  lea     r8, [rbp+4Fh+var_A0]; struct StateRepository::Statement *
0x18003699b  lea     rdx, aSelectCountFro_4; "SELECT COUNT(*) FROM PackagedUsageHisto"...
0x1800369a2  mov     rdi, [rbp+4Fh+var_80]
0x1800369a6  mov     rcx, rdi; this
0x1800369a9  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x1800369ae  mov     rcx, [rbp+57h]; this
0x1800369b2  test    eax, eax
0x1800369b4  js      loc_180036B4F
0x1800369ba  mov     r8, r15; __int64
0x1800369bd  mov     edx, 1; int
0x1800369c2  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800369c6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800369cb  mov     rcx, [rbp+57h]; this
0x1800369cf  test    eax, eax
0x1800369d1  js      loc_180036B64
0x1800369d7  mov     r8, r14; __int64
0x1800369da  mov     edx, 2; int
0x1800369df  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800369e3  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x1800369e8  mov     rcx, [rbp+57h]; this
0x1800369ec  test    eax, eax
0x1800369ee  js      loc_180036B79
0x1800369f4  mov     r8, rbx; __int64
0x1800369f7  mov     edx, 3; int
0x1800369fc  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036a00  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180036a05  mov     rcx, [rbp+57h]; this
0x180036a09  test    eax, eax
0x180036a0b  js      loc_180036B8E
0x180036a11  mov     [rbp+4Fh+UnbiasedTime], 0
0x180036a19  lea     rcx, [rbp+4Fh+UnbiasedTime]; UnbiasedTime
0x180036a1d  call    cs:__imp_QueryUnbiasedInterruptTime
0x180036a23  mov     rcx, 0FFFFE9FF5C6F0000h
0x180036a2d  mov     r8, [rbp+4Fh+UnbiasedTime]
0x180036a31  add     r8, rcx; __int64
0x180036a34  mov     edx, 4; int
0x180036a39  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036a3d  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x180036a42  mov     rcx, [rbp+57h]; this
0x180036a46  test    eax, eax
0x180036a48  js      loc_180036BA3
0x180036a4e  mov     [rbp+4Fh+arg_20], 0
0x180036a52  xor     ebx, ebx
0x180036a54  mov     [rbp+4Fh+UnbiasedTime], rbx
0x180036a58  lea     rdx, [rbp+4Fh+arg_20]; bool *
0x180036a5c  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036a60  call    ?FetchRow@Statement@StateRepository@@QEAAJPEA_N@Z; StateRepository::Statement::FetchRow(bool *)
0x180036a65  mov     rcx, [rbp+57h]; this
0x180036a69  test    eax, eax
0x180036a6b  js      loc_180036BB8
0x180036a71  cmp     [rbp+4Fh+arg_20], bl
0x180036a74  jz      short loc_180036A95
0x180036a76  lea     r8, [rbp+4Fh+UnbiasedTime]; unsigned __int64 *
0x180036a7a  xor     edx, edx; int
0x180036a7c  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036a80  call    ?GetColumnUInt64@Statement@StateRepository@@QEBAJHPEA_K@Z; StateRepository::Statement::GetColumnUInt64(int,unsigned __int64 *)
0x180036a85  mov     rcx, [rbp+57h]; this
0x180036a89  test    eax, eax
0x180036a8b  js      loc_180036BCD
0x180036a91  mov     rbx, [rbp+4Fh+UnbiasedTime]
0x180036a95  lea     rdx, [rbp+4Fh+var_A0]; struct StateRepository::Statement *
0x180036a99  mov     rcx, rdi; this
0x180036a9c  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180036aa1  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036aa5  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180036aaa  mov     rcx, [rbp+57h]; this
0x180036aae  test    eax, eax
0x180036ab0  js      short loc_180036AE7
0x180036ab2  lea     rcx, [rbp+4Fh+var_A0]; this
0x180036ab6  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180036abb  nop
0x180036abc  lea     rcx, [rbp+4Fh+var_60]; this
0x180036ac0  call    ??1DatabaseScopeHelper@SQL@Private@CapabilityAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::CapabilityAccess::Private::SQL::DatabaseScopeHelper::~DatabaseScopeHelper(void)
0x180036ac5  nop
0x180036ac6  mov     rcx, [rbp+4Fh+var_78]; this
0x180036aca  test    rcx, rcx
0x180036acd  jz      short loc_180036AD4
0x180036acf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036ad4  mov     rax, rbx
0x180036ad7  add     rsp, 98h
0x180036ade  pop     r15
0x180036ae0  pop     r14
0x180036ae2  pop     rdi
0x180036ae3  pop     rsi
0x180036ae4  pop     rbx
0x180036ae5  pop     rbp
0x180036ae6  retn
0x180036ae7  mov     r9d, eax; char *
0x180036aea  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036af1  mov     edx, 9D6h; void *
0x180036af6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036afc  mov     r9d, eax; char *
0x180036aff  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b06  mov     edx, 9BFh; void *
0x180036b0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b11  mov     r9d, 80004001h; char *
0x180036b17  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b1e  mov     edx, 9AAh; void *
0x180036b23  mov     rcx, rdi; this
0x180036b26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b2c  mov     ecx, 8000FFFFh
0x180036b31  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180036b36  mov     r9d, eax; char *
0x180036b39  mov     rcx, [rbp+57h]; this
0x180036b3d  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b44  mov     edx, 9C3h; void *
0x180036b49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b4f  mov     r9d, eax; char *
0x180036b52  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b59  mov     edx, 9BAh; void *
0x180036b5e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b64  mov     r9d, eax; char *
0x180036b67  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b6e  mov     edx, 9C6h; void *
0x180036b73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b79  mov     r9d, eax; char *
0x180036b7c  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b83  mov     edx, 9C7h; void *
0x180036b88  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036b8e  mov     r9d, eax; char *
0x180036b91  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036b98  mov     edx, 9C8h; void *
0x180036b9d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036ba3  mov     r9d, eax; char *
0x180036ba6  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036bad  mov     edx, 9C9h; void *
0x180036bb2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036bb8  mov     r9d, eax; char *
0x180036bbb  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036bc2  mov     edx, 9CEh; void *
0x180036bc7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180036bcd  mov     r9d, eax; char *
0x180036bd0  lea     r8, aOnecoreBaseDev_56; "onecore\\base\\devices\\cam\\core\\capa"...
0x180036bd7  mov     edx, 9D2h; void *
0x180036bdc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
