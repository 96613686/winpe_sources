# OSIntegration::DEH::RuntimeExtensionHandler::FindAndAddRedirectionDll(__int64,ushort const *,ARI::DependencyMiniRepository::Writer &)

- ea: `0x180023d18`
- end: `0x1800242b2`
- name: `?FindAndAddRedirectionDll@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJ_JPEBGAEAVWriter@DependencyMiniRepository@ARI@@@Z`
- size: `1434`
- prototype: `__int64 __fastcall(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, __int64, const unsigned __int16 *, struct ARI::DependencyMiniRepository::Writer *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1801253fc`

## callees

- `0x18000b3bc`
- `0x180023d18`
- `0x180025910`
- `0x180026e08`
- `0x180027364`
- `0x1800274d0`
- `0x18002788c`
- `0x180029278`
- `0x18002af28`
- `0x18002afe8`
- `0x18003054c`
- `0x180077608`
- `0x18007b440`
- `0x18008c8c4`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0260`
- `0x18012504c`
- `0x180125d4c`
- `0x18017678c`
- `0x180179af0`
- `0x18017d1b0`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024062`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002409b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002411f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024036`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002409b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002411f`

## string_xrefs

- `0x1800241fd`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180024213`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180023e3a`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800241dd`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180024103`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x180024258`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x180023e11`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180024198`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x1800241b1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationproperty.cpp`
- `0x18002422e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationproperty.cpp`
- `0x180023e79`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::FindAndAddRedirectionDll(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        __int64 a2,
        const unsigned __int16 *a3,
        struct ARI::DependencyMiniRepository::Writer *a4)
{
  bool v6; // di
  __int64 v7; // rsi
  const char *v8; // r14
  int v9; // eax
  int v10; // r8d
  int v11; // ebx
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // r8
  __int64 v15; // rdx
  int Next; // eax
  const wchar_t *v17; // rdi
  __int64 (__fastcall *v18)(const wchar_t *, __int64, __int64 *); // rbx
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  const unsigned __int16 *StringRawBuffer; // rax
  unsigned int v22; // r9d
  __int64 v23; // rdx
  __int64 v25; // rdx
  const char **v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  int v29; // [rsp+20h] [rbp-E0h]
  bool v30; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  struct sqlite3_stmt *v32; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t *v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v35; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v37[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v38; // [rsp+80h] [rbp-80h]
  int v39; // [rsp+90h] [rbp-70h]
  __int64 v40; // [rsp+98h] [rbp-68h] BYREF
  void *v41[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v42[2]; // [rsp+B0h] [rbp-50h]
  _QWORD *v43; // [rsp+C0h] [rbp-40h]
  _QWORD v44[17]; // [rsp+C8h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+150h] [rbp+50h] BYREF
  __int64 v46; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]

  v32 = 0;
  v37[0] = 0;
  v37[1] = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  *(_OWORD *)v41 = 0;
  *(_OWORD *)v42 = 0;
  v6 = 0;
  v30 = 0;
  v33 = L"ImportRedirectionTable";
  v36[0] = a2;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  v44[0] = off_180212310;
  v44[1] = v36;
  v44[2] = &v33;
  v43 = v44;
  v8 = "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationProp"
       "erty WHERE Application=? AND Name=? AND _WorkId=0;";
  *(_DWORD *)&hstringHeader.Reserved.Reserved2[20] = 0;
  if ( *(_QWORD *)(v7 + 8)
    && "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationProp"
       "erty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);" )
  {
    v8 = "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationPr"
         "operty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);";
  }
  if ( !*(_QWORD *)v7 )
  {
    v11 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
      (const char *)0x8007139FLL,
      (int)v26);
LABEL_43:
    v12 = 21;
    goto LABEL_44;
  }
  if ( !StateRepository::StatementCache::Get(
          (StateRepository::StatementCache *)(v7 + 40),
          v8,
          (struct StateRepository::Statement *)&v32) )
  {
    v9 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v32);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x127,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
        (const char *)(unsigned int)v9,
        (int)v26);
    v11 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)v7, v8, v10, &v32, v26);
    if ( v11 < 0 )
      goto LABEL_43;
  }
  v11 = (*(__int64 (__fastcall **)(_QWORD *, struct sqlite3_stmt **))(*v43 + 8LL))(v43, &v32);
  if ( v11 >= 0 )
  {
    if ( "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationPr"
         "operty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);" )
    {
      v11 = StateRepository::Statement::BindIfWorkInProgress((StateRepository::Statement *)&v32, 3, *(_QWORD *)(v7 + 8));
      if ( v11 < 0 )
      {
        v12 = 27;
        goto LABEL_44;
      }
    }
    (*(void (__fastcall **)(_QWORD *, _QWORD))*v43)(v43, 0);
    if ( v32 )
    {
      v13 = StateRepository::Statement::dal_step(v32);
      v11 = v13;
      if ( v13 == -2018574236 )
      {
        v6 = 1;
LABEL_19:
        v30 = v6;
        if ( !v6 )
        {
LABEL_38:
          StateRepository::Blob::Reset((StateRepository::Blob *)&v41[1]);
          StateRepository::TextA::Reset((StateRepository::TextA *)&v40);
          StateRepository::Statement::~Statement((StateRepository::Statement *)&v32);
          return 0;
        }
        v11 = StateRepository::Entity::ApplicationProperty::RowToObject(
                (const struct StateRepository::Statement *)&v32,
                (struct StateRepository::Entity::ApplicationProperty *)v37,
                v14);
        if ( v11 >= 0 )
          goto LABEL_23;
        v15 = 474;
        goto LABEL_41;
      }
      if ( v13 == -2018574235 )
      {
        v6 = 0;
        goto LABEL_19;
      }
      if ( v13 >= 0 )
      {
        while ( 1 )
        {
LABEL_23:
          if ( !v6 )
            goto LABEL_38;
          v35 = 0;
          v33 = 0;
          v36[0] = 0;
          v34 = 0;
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          Next = StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(
                   (StateRepository::DictionarySerialization::WinRTReader *)v36,
                   v42[0],
                   v41[1],
                   &v35,
                   (struct IInspectable *)v26);
          v11 = Next;
          if ( Next < 0 )
          {
            v23 = 1617;
            goto LABEL_37;
          }
          Next = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                   &v35,
                   &v33);
          v11 = Next;
          if ( Next < 0 )
          {
            v23 = 1618;
            goto LABEL_37;
          }
          v17 = v33;
          v18 = *(__int64 (__fastcall **)(const wchar_t *, __int64, __int64 *))(*(_QWORD *)v33 + 48LL);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          v46 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"#text", 6u, 5u);
          Next = v18(v17, v46, &v34);
          v11 = Next;
          if ( Next < 0 )
          {
            v23 = 1619;
            goto LABEL_37;
          }
          v19 = v34;
          v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v34 + 152LL);
          WindowsDeleteString(string);
          string = 0;
          Next = v20(v19, &string);
          v11 = Next;
          if ( Next < 0 )
          {
            v23 = 1620;
            goto LABEL_37;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          Next = ARI::DependencyMiniRepository::Writer::AddSection_RedirectionDll(a4, a3, StringRawBuffer, v22);
          v11 = Next;
          if ( Next < 0 )
            break;
          Next = StateRepository::Entity::ApplicationProperty::FindNext(
                   (struct StateRepository::Statement *)&v32,
                   (struct StateRepository::Entity::ApplicationProperty *)v37,
                   &v30);
          v11 = Next;
          if ( Next < 0 )
          {
            v23 = 1624;
LABEL_37:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v23,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
              (const char *)(unsigned int)Next,
              (int)v26);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
            wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v36);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            StateRepository::Entity::PublisherCacheFolder::~PublisherCacheFolder((StateRepository::Entity::PublisherCacheFolder *)v37);
            goto LABEL_46;
          }
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(v36);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
          v6 = v30;
        }
        v23 = 1622;
        goto LABEL_37;
      }
    }
    else
    {
      v11 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        (int)v26);
    }
    v15 = 471;
LABEL_41:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationproperty.cpp",
      (const char *)(unsigned int)v11,
      (int)v26);
    v25 = 1607;
    goto LABEL_45;
  }
  v12 = 23;
LABEL_44:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)(unsigned int)v11,
    (int)v26);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)(unsigned int)v11,
    v28);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B7,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationproperty.cpp",
    (const char *)(unsigned int)v11,
    v29);
  (*(void (__fastcall **)(_QWORD *, _QWORD))*v43)(v43, 0);
  v25 = 1605;
LABEL_45:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v25,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
    (const char *)(unsigned int)v11,
    v27);
  StateRepository::Blob::Reset((StateRepository::Blob *)&v41[1]);
  StateRepository::TextA::Reset((StateRepository::TextA *)&v40);
LABEL_46:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180023d18  mov     [rsp-8+arg_8], rbx
0x180023d1d  push    rbp
0x180023d1e  push    rsi
0x180023d1f  push    rdi
0x180023d20  push    r12
0x180023d22  push    r13
0x180023d24  push    r14
0x180023d26  push    r15
0x180023d28  lea     rbp, [rsp-80h]
0x180023d2d  sub     rsp, 180h
0x180023d34  mov     rax, cs:__security_cookie
0x180023d3b  xor     rax, rsp
0x180023d3e  mov     [rbp+0B0h+var_40], rax
0x180023d42  mov     r12, r9
0x180023d45  mov     r15, r8
0x180023d48  xor     r13d, r13d
0x180023d4b  mov     [rsp+1B0h+var_170], r13
0x180023d50  mov     [rsp+1B0h+var_140], r13
0x180023d55  mov     [rsp+1B0h+var_138], r13
0x180023d5a  xorps   xmm0, xmm0
0x180023d5d  movdqa  [rbp+0B0h+var_130], xmm0
0x180023d62  mov     [rbp+0B0h+var_120], r13d
0x180023d66  mov     [rbp+0B0h+var_118], r13
0x180023d6a  movdqa  xmmword ptr [rbp+0B0h+var_110], xmm0
0x180023d6f  xorps   xmm1, xmm1
0x180023d72  movdqa  xmmword ptr [rbp+0B0h+var_100], xmm1
0x180023d77  mov     dil, r13b
0x180023d7a  mov     [rsp+1B0h+var_180], r13b
0x180023d7f  lea     rax, aImportredirect; "ImportRedirectionTable"
0x180023d86  mov     [rsp+1B0h+var_168], rax
0x180023d8b  mov     [rsp+1B0h+var_150], rdx
0x180023d90  mov     rcx, [rcx+18h]
0x180023d94  mov     rax, [rcx]
0x180023d97  mov     rax, [rax+8]
0x180023d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023da0  mov     rsi, rax
0x180023da3  lea     rax, off_180212310
0x180023daa  mov     [rbp+0B0h+var_E8], rax
0x180023dae  lea     rax, [rsp+1B0h+var_150]
0x180023db3  mov     [rbp+0B0h+var_E0], rax
0x180023db7  lea     rax, [rsp+1B0h+var_168]
0x180023dbc  mov     [rbp+0B0h+var_D8], rax
0x180023dc0  lea     rax, [rbp+0B0h+var_E8]
0x180023dc4  mov     [rbp+0B0h+var_F0], rax
0x180023dc8  lea     r14, aSelectApplicat_0; "SELECT _ApplicationPropertyID, _Revisio"...
0x180023dcf  lea     rcx, aSelectApplicat; "SELECT _ApplicationPropertyID, _Revisio"...
0x180023dd6  xor     eax, eax
0x180023dd8  mov     dword ptr [rbp+0B0h+hstringHeader.Reserved+14h], eax
0x180023ddb  cmp     [rsi+8], r13
0x180023ddf  jz      short loc_180023DE9
0x180023de1  test    rcx, rcx
0x180023de4  jz      short loc_180023DE9
0x180023de6  mov     r14, rcx
0x180023de9  cmp     [rsi], r13
0x180023dec  jz      loc_1800241CE
0x180023df2  mov     rcx, [rsp+1B0h+var_170]; struct sqlite3_stmt *
0x180023df7  test    rcx, rcx
0x180023dfa  jz      short loc_180023E29
0x180023dfc  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x180023e01  mov     ebx, eax
0x180023e03  test    eax, eax
0x180023e05  jns     short loc_180023E24
0x180023e07  mov     rcx, [rbp+0B8h]; this
0x180023e0e  mov     r9d, eax; char *
0x180023e11  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\staterepositor"...
0x180023e18  mov     edx, 7Bh ; '{'; void *
0x180023e1d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023e22  jmp     short loc_180023E2C
0x180023e24  mov     [rsp+1B0h+var_170], r13
0x180023e29  mov     ebx, r13d
0x180023e2c  mov     rcx, [rbp+0B8h]; this
0x180023e33  test    ebx, ebx
0x180023e35  jns     short loc_180023E4B
0x180023e37  mov     r9d, ebx; char *
0x180023e3a  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x180023e41  mov     edx, 679h; void *
0x180023e46  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023e4b  lea     rcx, [rsi+28h]; this
0x180023e4f  lea     r8, [rsp+1B0h+var_170]; struct StateRepository::Statement *
0x180023e54  mov     rdx, r14; char *
0x180023e57  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x180023e5c  test    rax, rax
0x180023e5f  jnz     short loc_180023EA4
0x180023e61  lea     rcx, [rsp+1B0h+var_170]; this
0x180023e66  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180023e6b  mov     rcx, [rbp+0B8h]; this
0x180023e72  test    eax, eax
0x180023e74  jns     short loc_180023E8A
0x180023e76  mov     r9d, eax; char *
0x180023e79  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\StateRepositor"...
0x180023e80  mov     edx, 127h; void *
0x180023e85  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180023e8a  lea     r9, [rsp+1B0h+var_170]; struct sqlite3_stmt **
0x180023e8f  mov     rdx, r14; char *
0x180023e92  mov     rcx, [rsi]; struct sqlite3 *
0x180023e95  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180023e9a  mov     ebx, eax
0x180023e9c  test    eax, eax
0x180023e9e  js      loc_1800241EE
0x180023ea4  mov     rcx, [rbp+0B0h+var_F0]
0x180023ea8  mov     rax, [rcx]
0x180023eab  lea     rdx, [rsp+1B0h+var_170]
0x180023eb0  mov     rax, [rax+8]
0x180023eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023eb9  mov     ebx, eax
0x180023ebb  test    eax, eax
0x180023ebd  jns     short loc_180023EC9
0x180023ebf  mov     edx, 17h
0x180023ec4  jmp     loc_1800241F3
0x180023ec9  lea     rax, aSelectApplicat; "SELECT _ApplicationPropertyID, _Revisio"...
0x180023ed0  test    rax, rax
0x180023ed3  jz      short loc_180023EF8
0x180023ed5  mov     r8, [rsi+8]; __int64
0x180023ed9  mov     edx, 3; int
0x180023ede  lea     rcx, [rsp+1B0h+var_170]; this
0x180023ee3  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x180023ee8  mov     ebx, eax
0x180023eea  test    eax, eax
0x180023eec  jns     short loc_180023EF8
0x180023eee  mov     edx, 1Bh
0x180023ef3  jmp     loc_1800241F3
0x180023ef8  mov     rcx, [rbp+0B0h+var_F0]
0x180023efc  mov     rax, [rcx]
0x180023eff  xor     edx, edx
0x180023f01  mov     rax, [rax]
0x180023f04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023f09  mov     rcx, [rsp+1B0h+var_170]; struct sqlite3_stmt *
0x180023f0e  test    rcx, rcx
0x180023f11  jz      loc_180024189
0x180023f17  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x180023f1c  mov     ebx, eax
0x180023f1e  cmp     eax, 87AF0064h
0x180023f23  jnz     short loc_180023F2A
0x180023f25  mov     dil, 1
0x180023f28  jmp     short loc_180023F34
0x180023f2a  cmp     eax, 87AF0065h
0x180023f2f  jnz     short loc_180023F61
0x180023f31  mov     dil, r13b
0x180023f34  mov     [rsp+1B0h+var_180], dil
0x180023f39  test    dil, dil
0x180023f3c  jz      loc_180024165
0x180023f42  lea     rdx, [rsp+1B0h+var_140]; struct StateRepository::Entity::ApplicationProperty *
0x180023f47  lea     rcx, [rsp+1B0h+var_170]; this
0x180023f4c  call    ?RowToObject@ApplicationProperty@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::ApplicationProperty::RowToObject(StateRepository::Statement const &,StateRepository::Entity::ApplicationProperty &,__int64)
0x180023f51  mov     ebx, eax
0x180023f53  test    eax, eax
0x180023f55  jns     short loc_180023F69
0x180023f57  mov     edx, 1DAh
0x180023f5c  jmp     loc_1800241AE
0x180023f61  test    eax, eax
0x180023f63  js      loc_1800241A9
0x180023f69  test    dil, dil
0x180023f6c  jz      loc_180024165
0x180023f72  mov     [rsp+1B0h+var_158], r13
0x180023f77  mov     [rsp+1B0h+var_168], r13
0x180023f7c  mov     [rsp+1B0h+var_150], r13
0x180023f81  mov     [rsp+1B0h+var_160], r13
0x180023f86  mov     [rsp+1B0h+string], r13
0x180023f8b  lea     rcx, [rsp+1B0h+var_158]
0x180023f90  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023f95  lea     r9, [rsp+1B0h+var_158]; struct Windows::Foundation::Collections::IPropertySet **
0x180023f9a  mov     r8, [rbp+0B0h+var_110+8]; void *
0x180023f9e  mov     rdx, [rbp+0B0h+var_100]; unsigned __int64
0x180023fa2  lea     rcx, [rsp+1B0h+var_150]; this
0x180023fa7  call    ?DeserializeAsPropertySet@WinRTReader@DictionarySerialization@StateRepository@@QEAAJ_KPEBXPEAPEAUIPropertySet@Collections@Foundation@Windows@@PEA_K@Z; StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(unsigned __int64,void const *,Windows::Foundation::Collections::IPropertySet * *,unsigned __int64 *)
0x180023fac  mov     ebx, eax
0x180023fae  test    eax, eax
0x180023fb0  js      loc_1800240FE
0x180023fb6  lea     rdx, [rsp+1B0h+var_168]
0x180023fbb  lea     rcx, [rsp+1B0h+var_158]
0x180023fc0  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180023fc5  mov     ebx, eax
0x180023fc7  test    eax, eax
0x180023fc9  js      loc_1800240F7
0x180023fcf  mov     rdi, [rsp+1B0h+var_168]
0x180023fd4  mov     rax, [rdi]
0x180023fd7  mov     rbx, [rax+30h]
0x180023fdb  lea     rcx, [rsp+1B0h+var_160]
0x180023fe0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180023fe5  mov     [rbp+0B0h+var_48], r13
0x180023fe9  mov     r9d, 5; unsigned int
0x180023fef  lea     r8d, [r9+1]; unsigned int
0x180023ff3  lea     rdx, aText_0; "#text"
0x180023ffa  lea     rcx, [rbp+0B0h+hstringHeader]; hstringHeader
0x180023ffe  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024003  nop
0x180024004  lea     r8, [rsp+1B0h+var_160]
0x180024009  mov     rdx, [rbp+0B0h+var_48]
0x18002400d  mov     rcx, rdi
0x180024010  mov     rax, rbx
0x180024013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024018  mov     ebx, eax
0x18002401a  test    eax, eax
0x18002401c  js      loc_1800240F0
0x180024022  mov     rdi, [rsp+1B0h+var_160]
0x180024027  mov     rax, [rdi]
0x18002402a  mov     rbx, [rax+98h]
0x180024031  mov     rcx, [rsp+1B0h+string]; string
0x180024036  call    cs:__imp_WindowsDeleteString
0x18002403c  mov     [rsp+1B0h+string], r13
0x180024041  lea     rdx, [rsp+1B0h+string]
0x180024046  mov     rcx, rdi
0x180024049  mov     rax, rbx
0x18002404c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024051  mov     ebx, eax
0x180024053  test    eax, eax
0x180024055  js      loc_1800240E9
0x18002405b  xor     edx, edx; length
0x18002405d  mov     rcx, [rsp+1B0h+string]; string
0x180024062  call    cs:__imp_WindowsGetStringRawBuffer
0x180024068  mov     r8, rax; unsigned __int16 *
0x18002406b  mov     rdx, r15; unsigned __int16 *
0x18002406e  mov     rcx, r12; this
0x180024071  call    ?AddSection_RedirectionDll@Writer@DependencyMiniRepository@ARI@@QEAAJPEBG0I@Z; ARI::DependencyMiniRepository::Writer::AddSection_RedirectionDll(ushort const *,ushort const *,uint)
0x180024076  mov     ebx, eax
0x180024078  test    eax, eax
0x18002407a  js      short loc_1800240E2
0x18002407c  lea     r8, [rsp+1B0h+var_180]; bool *
0x180024081  lea     rdx, [rsp+1B0h+var_140]; struct StateRepository::Entity::ApplicationProperty *
0x180024086  lea     rcx, [rsp+1B0h+var_170]; struct StateRepository::Statement *
0x18002408b  call    ?FindNext@ApplicationProperty@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::ApplicationProperty::FindNext(StateRepository::Statement &,StateRepository::Entity::ApplicationProperty &,bool &)
0x180024090  mov     ebx, eax
0x180024092  test    eax, eax
0x180024094  js      short loc_1800240DB
0x180024096  mov     rcx, [rsp+1B0h+string]; string
0x18002409b  call    cs:__imp_WindowsDeleteString
0x1800240a1  mov     [rsp+1B0h+string], r13
0x1800240a6  lea     rcx, [rsp+1B0h+var_160]
0x1800240ab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800240b0  nop
0x1800240b1  lea     rcx, [rsp+1B0h+var_150]
0x1800240b6  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x1800240bb  nop
0x1800240bc  lea     rcx, [rsp+1B0h+var_168]
0x1800240c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800240c6  nop
0x1800240c7  lea     rcx, [rsp+1B0h+var_158]
0x1800240cc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800240d1  mov     dil, [rsp+1B0h+var_180]
0x1800240d6  jmp     loc_180023F69
0x1800240db  mov     edx, 658h
0x1800240e0  jmp     short loc_180024103
0x1800240e2  mov     edx, 656h
0x1800240e7  jmp     short loc_180024103
0x1800240e9  mov     edx, 654h
0x1800240ee  jmp     short loc_180024103
0x1800240f0  mov     edx, 653h
0x1800240f5  jmp     short loc_180024103
0x1800240f7  mov     edx, 652h
0x1800240fc  jmp     short loc_180024103
0x1800240fe  mov     edx, 651h; void *
0x180024103  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002410a  mov     r9d, eax; char *
0x18002410d  mov     rcx, [rbp+0B8h]; this
0x180024114  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024119  nop
0x18002411a  mov     rcx, [rsp+1B0h+string]; string
0x18002411f  call    cs:__imp_WindowsDeleteString
0x180024125  mov     [rsp+1B0h+string], r13
0x18002412a  lea     rcx, [rsp+1B0h+var_160]
0x18002412f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024134  nop
0x180024135  lea     rcx, [rsp+1B0h+var_150]
0x18002413a  call    ??1?$com_ptr_t@U?$IMap@U_GUID@@PEAVComClassRegistrationCombinedProperties@Internal@DEH@OSIntegration@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(void)
0x18002413f  nop
0x180024140  lea     rcx, [rsp+1B0h+var_168]
0x180024145  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18002414a  nop
0x18002414b  lea     rcx, [rsp+1B0h+var_158]
0x180024150  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024155  nop
0x180024156  lea     rcx, [rsp+1B0h+var_140]; this
0x18002415b  call    ??1PublisherCacheFolder@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PublisherCacheFolder::~PublisherCacheFolder(void)
0x180024160  jmp     loc_18002427F
0x180024165  lea     rcx, [rbp+0B0h+var_110+8]; this
0x180024169  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x18002416e  lea     rcx, [rbp+0B0h+var_118]; this
0x180024172  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180024177  nop
0x180024178  lea     rcx, [rsp+1B0h+var_170]; this
0x18002417d  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180024182  xor     eax, eax
0x180024184  jmp     loc_18002428B
0x180024189  mov     rcx, [rbp+0B8h]; this
0x180024190  mov     ebx, 8007139Fh
0x180024195  mov     r9d, ebx; char *
0x180024198  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\staterepositor"...
0x18002419f  mov     edx, 3Fh ; '?'; void *
0x1800241a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800241a9  mov     edx, 1D7h; void *
0x1800241ae  mov     r9d, ebx; char *
0x1800241b1  lea     r8, aOnecoreBaseApp_91; "onecore\\base\\appmodel\\staterepositor"...
0x1800241b8  mov     rcx, [rbp+0B8h]; this
0x1800241bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800241c4  mov     edx, 647h
0x1800241c9  jmp     loc_180024255
0x1800241ce  mov     rcx, [rbp+0B8h]; this
0x1800241d5  mov     ebx, 8007139Fh
0x1800241da  mov     r9d, ebx; char *
0x1800241dd  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
  ... truncated ...
```
