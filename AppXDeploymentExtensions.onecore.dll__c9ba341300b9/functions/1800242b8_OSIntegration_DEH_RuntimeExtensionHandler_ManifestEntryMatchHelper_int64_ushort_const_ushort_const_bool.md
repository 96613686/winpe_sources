# OSIntegration::DEH::RuntimeExtensionHandler::ManifestEntryMatchHelper(__int64,ushort const *,ushort const *,bool *)

- ea: `0x1800242b8`
- end: `0x180024805`
- name: `?ManifestEntryMatchHelper@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJ_JPEBG1PEA_N@Z`
- size: `1357`
- prototype: `int(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, __int64, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180023688`

## callees

- `0x18000b3bc`
- `0x1800242b8`
- `0x180025910`
- `0x180026e08`
- `0x180027364`
- `0x1800274d0`
- `0x18002788c`
- `0x180029278`
- `0x18002af28`
- `0x18002afe8`
- `0x18003054c`
- `0x18007b440`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800f0260`
- `0x18012504c`
- `0x18017678c`
- `0x180179af0`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800247c0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800247c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800247a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800247a6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002477a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800247d4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800246b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002477a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800247d4`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x1800245e6`
- `ext-ms-onecore-appmodel-staterepository-internal-l1-1-3!SRDictionaryToPropertySet` at `0x1800245e6`

## string_xrefs

- `0x180024412`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180024428`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180024392`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x180024554`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18002446a`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002469a`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002461f`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002465f`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180024443`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationproperty.cpp`
- `0x180024638`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationproperty.cpp`
- `0x18002456d`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::ManifestEntryMatchHelper(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        __int64 a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        bool *a5)
{
  __int64 v6; // rdi
  const char *v7; // rsi
  int v8; // ebx
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // rdx
  int v13; // eax
  int v14; // eax
  int v15; // r8d
  int v16; // eax
  __int64 v17; // r8
  char v18; // di
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // rdi
  __int64 (__fastcall *v23)(__int64, __int64, _QWORD *); // rbx
  __int64 v24; // rdi
  __int64 (__fastcall *v25)(__int64, HSTRING *); // rbx
  const WCHAR *StringRawBuffer; // rax
  const char **bIgnoreCase; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCaseb; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasec; // [rsp+20h] [rbp-E0h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  struct sqlite3_stmt *v32; // [rsp+38h] [rbp-C8h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64); // [rsp+40h] [rbp-C0h] BYREF
  __int64 v34; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v35[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v37; // [rsp+70h] [rbp-90h]
  int v38; // [rsp+80h] [rbp-80h]
  __int64 v39; // [rsp+88h] [rbp-78h] BYREF
  __int128 v40; // [rsp+90h] [rbp-70h] BYREF
  __int128 v41; // [rsp+A0h] [rbp-60h]
  _QWORD *v42; // [rsp+B0h] [rbp-50h]
  _QWORD v43[17]; // [rsp+B8h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+140h] [rbp+40h] BYREF
  __int64 v45; // [rsp+158h] [rbp+58h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v32 = 0;
  v36[0] = 0;
  v36[1] = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  *a5 = 0;
  v33 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))a3;
  v34 = a2;
  v6 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  v43[0] = off_180212310;
  v43[1] = &v34;
  v43[2] = &v33;
  v42 = v43;
  v7 = "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationProp"
       "erty WHERE Application=? AND Name=? AND _WorkId=0;";
  *(_DWORD *)&hstringHeader.Reserved.Reserved2[20] = 0;
  if ( *(_QWORD *)(v6 + 8)
    && "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationProp"
       "erty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);" )
  {
    v7 = "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM ApplicationPr"
         "operty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);";
  }
  if ( *(_QWORD *)v6 )
  {
    if ( v32 )
    {
      v13 = StateRepository::Statement::dal_finalize(v32);
      v10 = v13;
      if ( v13 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x7B,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)(unsigned int)v13,
          (int)bIgnoreCase);
LABEL_7:
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x679,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
            (const char *)(unsigned int)v10,
            (int)bIgnoreCase);
        if ( !StateRepository::StatementCache::Get(
                (StateRepository::StatementCache *)(v6 + 40),
                v7,
                (struct StateRepository::Statement *)&v32) )
        {
          v14 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v32);
          if ( v14 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x127,
              (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
              (const char *)(unsigned int)v14,
              (int)bIgnoreCase);
          v8 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)v6, v7, v15, &v32, bIgnoreCase);
          if ( v8 < 0 )
            goto LABEL_4;
        }
        v8 = (*(__int64 (__fastcall **)(_QWORD *, struct sqlite3_stmt **))(*v42 + 8LL))(v42, &v32);
        if ( v8 < 0 )
        {
          v9 = 23;
          goto LABEL_12;
        }
        if ( "SELECT _ApplicationPropertyID, _Revision, _WorkId, Application, \"Index\", Name, _Dictionary FROM Applicati"
             "onProperty WHERE Application=? AND Name=? AND (_WorkId=0 OR _WorkId=?);" )
        {
          v8 = StateRepository::Statement::BindIfWorkInProgress(
                 (StateRepository::Statement *)&v32,
                 3,
                 *(_QWORD *)(v6 + 8));
          if ( v8 < 0 )
          {
            v9 = 27;
            goto LABEL_12;
          }
        }
        (*(void (__fastcall **)(_QWORD *, _QWORD))*v42)(v42, 0);
        if ( v32 )
        {
          v16 = StateRepository::Statement::dal_step(v32);
          v8 = v16;
          if ( v16 == -2018574236 )
          {
            v18 = 1;
          }
          else
          {
            v18 = 0;
            if ( v16 != -2018574235 )
            {
              if ( v16 >= 0 )
                goto LABEL_31;
              goto LABEL_38;
            }
          }
          if ( !v18 )
            goto LABEL_36;
          v8 = StateRepository::Entity::ApplicationProperty::RowToObject(
                 (const struct StateRepository::Statement *)&v32,
                 (struct StateRepository::Entity::ApplicationProperty *)v36,
                 v17);
          if ( v8 >= 0 )
          {
LABEL_31:
            if ( v18 )
            {
              v33 = 0;
              v34 = 0;
              v35[0] = 0;
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
              v19 = SRDictionaryToPropertySet((unsigned int)v41, *((_QWORD *)&v40 + 1), &v33);
              v8 = v19;
              if ( v19 < 0 )
              {
                v20 = 1656;
LABEL_44:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v20,
                  (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
                  (const char *)(unsigned int)v19,
                  (int)bIgnoreCase);
                WindowsDeleteString(string);
                string = 0;
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                StateRepository::Entity::PublisherCacheFolder::~PublisherCacheFolder((StateRepository::Entity::PublisherCacheFolder *)v36);
                goto LABEL_15;
              }
              v19 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
                      &v33,
                      (__int64)&v34);
              v8 = v19;
              if ( v19 < 0 )
              {
                v20 = 1657;
                goto LABEL_44;
              }
              v22 = v34;
              v23 = *(__int64 (__fastcall **)(__int64, __int64, _QWORD *))(*(_QWORD *)v34 + 48LL);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
              v45 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"#text", 6u, 5u);
              v19 = v23(v22, v45, v35);
              v8 = v19;
              if ( v19 < 0 )
              {
                v20 = 1658;
                goto LABEL_44;
              }
              v24 = v35[0];
              v25 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v35[0] + 152LL);
              WindowsDeleteString(string);
              string = 0;
              v19 = v25(v24, &string);
              v8 = v19;
              if ( v19 < 0 )
              {
                v20 = 1659;
                goto LABEL_44;
              }
              StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
              if ( CompareStringOrdinal(StringRawBuffer, -1, a4, -1, 1) == 2 )
                *a5 = 1;
              WindowsDeleteString(string);
              string = 0;
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v35);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
              Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            }
LABEL_36:
            v8 = 0;
            goto LABEL_14;
          }
          v21 = 474;
LABEL_39:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v21,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationproperty.cpp",
            (const char *)(unsigned int)v8,
            (int)bIgnoreCase);
          v11 = 1647;
          goto LABEL_13;
        }
        v8 = -2147019873;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x3F,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)0x8007139FLL,
          (int)bIgnoreCase);
LABEL_38:
        v21 = 471;
        goto LABEL_39;
      }
      v32 = 0;
    }
    v10 = 0;
    goto LABEL_7;
  }
  v8 = -2147019873;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8007139FLL,
    (int)bIgnoreCase);
LABEL_4:
  v9 = 21;
LABEL_12:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)(unsigned int)v8,
    (int)bIgnoreCase);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)(unsigned int)v8,
    bIgnoreCaseb);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1B7,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationproperty.cpp",
    (const char *)(unsigned int)v8,
    bIgnoreCasec);
  (*(void (__fastcall **)(_QWORD *, _QWORD))*v42)(v42, 0);
  v11 = 1645;
LABEL_13:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
    (const char *)(unsigned int)v8,
    bIgnoreCasea);
LABEL_14:
  StateRepository::Blob::Reset((StateRepository::Blob *)((char *)&v40 + 8));
  StateRepository::TextA::Reset((StateRepository::TextA *)&v39);
LABEL_15:
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v32);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800242b8  mov     [rsp-8+arg_8], rbx
0x1800242bd  push    rbp
0x1800242be  push    rsi
0x1800242bf  push    rdi
0x1800242c0  push    r12
0x1800242c2  push    r13
0x1800242c4  push    r14
0x1800242c6  push    r15
0x1800242c8  lea     rbp, [rsp-70h]
0x1800242cd  sub     rsp, 170h
0x1800242d4  mov     rax, cs:__security_cookie
0x1800242db  xor     rax, rsp
0x1800242de  mov     [rbp+0A0h+var_40], rax
0x1800242e2  mov     r15, r9
0x1800242e5  mov     r14, [rbp+0A0h+arg_20]
0x1800242ec  xor     r12d, r12d
0x1800242ef  mov     [rsp+1A0h+var_168], r12
0x1800242f4  mov     [rsp+1A0h+var_140], r12
0x1800242f9  mov     [rsp+1A0h+var_138], r12
0x1800242fe  xorps   xmm0, xmm0
0x180024301  movdqa  [rsp+1A0h+var_130], xmm0
0x180024307  mov     [rbp+0A0h+var_120], r12d
0x18002430b  mov     [rbp+0A0h+var_118], r12
0x18002430f  movdqa  [rbp+0A0h+var_110], xmm0
0x180024314  xorps   xmm1, xmm1
0x180024317  movdqa  [rbp+0A0h+var_100], xmm1
0x18002431c  mov     [r14], r12b
0x18002431f  mov     [rsp+1A0h+var_160], r8
0x180024324  mov     [rsp+1A0h+var_158], rdx
0x180024329  mov     rcx, [rcx+18h]
0x18002432d  mov     rax, [rcx]
0x180024330  mov     rax, [rax+8]
0x180024334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024339  mov     rdi, rax
0x18002433c  lea     rax, off_180212310
0x180024343  mov     [rbp+0A0h+var_E8], rax
0x180024347  lea     rax, [rsp+1A0h+var_158]
0x18002434c  mov     [rbp+0A0h+var_E0], rax
0x180024350  lea     rax, [rsp+1A0h+var_160]
0x180024355  mov     [rbp+0A0h+var_D8], rax
0x180024359  lea     rax, [rbp+0A0h+var_E8]
0x18002435d  mov     [rbp+0A0h+var_F0], rax
0x180024361  lea     rsi, aSelectApplicat_0; "SELECT _ApplicationPropertyID, _Revisio"...
0x180024368  lea     r13, aSelectApplicat; "SELECT _ApplicationPropertyID, _Revisio"...
0x18002436f  xor     eax, eax
0x180024371  mov     dword ptr [rbp+0A0h+hstringHeader.Reserved+14h], eax
0x180024374  cmp     [rdi+8], r12
0x180024378  jnz     loc_1800244C7
0x18002437e  cmp     [rdi], r12
0x180024381  jnz     short loc_1800243AA
0x180024383  mov     rcx, [rbp+0A8h]; this
0x18002438a  mov     ebx, 8007139Fh
0x18002438f  mov     r9d, ebx; char *
0x180024392  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x180024399  mov     edx, 66Eh; void *
0x18002439e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800243a3  mov     edx, 15h
0x1800243a8  jmp     short loc_180024408
0x1800243aa  mov     rcx, [rsp+1A0h+var_168]; struct sqlite3_stmt *
0x1800243af  test    rcx, rcx
0x1800243b2  jnz     loc_1800244D8
0x1800243b8  mov     ebx, r12d
0x1800243bb  mov     rcx, [rbp+0A8h]; this
0x1800243c2  test    ebx, ebx
0x1800243c4  js      loc_180024551
0x1800243ca  lea     rcx, [rdi+28h]; this
0x1800243ce  lea     r8, [rsp+1A0h+var_168]; struct StateRepository::Statement *
0x1800243d3  mov     rdx, rsi; char *
0x1800243d6  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x1800243db  test    rax, rax
0x1800243de  jz      loc_18002451D
0x1800243e4  mov     rcx, [rbp+0A0h+var_F0]
0x1800243e8  mov     rax, [rcx]
0x1800243eb  lea     rdx, [rsp+1A0h+var_168]
0x1800243f0  mov     rax, [rax+8]
0x1800243f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243f9  mov     ebx, eax
0x1800243fb  test    eax, eax
0x1800243fd  jns     loc_1800244F1
0x180024403  mov     edx, 17h; void *
0x180024408  mov     rcx, [rbp+0A8h]; this
0x18002440f  mov     r9d, ebx; char *
0x180024412  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\staterepositor"...
0x180024419  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002441e  mov     rcx, [rbp+0A8h]; this
0x180024425  mov     r9d, ebx; char *
0x180024428  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\staterepositor"...
0x18002442f  mov     edx, 0E8h; void *
0x180024434  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024439  mov     rcx, [rbp+0A8h]; this
0x180024440  mov     r9d, ebx; char *
0x180024443  lea     r8, aOnecoreBaseApp_91; "onecore\\base\\appmodel\\staterepositor"...
0x18002444a  mov     edx, 1B7h; void *
0x18002444f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024454  mov     rcx, [rbp+0A0h+var_F0]
0x180024458  mov     rax, [rcx]
0x18002445b  xor     edx, edx
0x18002445d  mov     rax, [rax]
0x180024460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024465  mov     edx, 66Dh; void *
0x18002446a  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180024471  mov     r9d, ebx; char *
0x180024474  mov     rcx, [rbp+0A8h]; this
0x18002447b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024480  nop
0x180024481  lea     rcx, [rbp+0A0h+var_110+8]; this
0x180024485  call    ?Reset@Blob@StateRepository@@QEAAXXZ; StateRepository::Blob::Reset(void)
0x18002448a  lea     rcx, [rbp+0A0h+var_118]; this
0x18002448e  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180024493  nop
0x180024494  lea     rcx, [rsp+1A0h+var_168]; this
0x180024499  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18002449e  mov     eax, ebx
0x1800244a0  mov     rcx, [rbp+0A0h+var_40]
0x1800244a4  xor     rcx, rsp; StackCookie
0x1800244a7  call    __security_check_cookie
0x1800244ac  mov     rbx, [rsp+1A0h+arg_8]
0x1800244b4  add     rsp, 170h
0x1800244bb  pop     r15
0x1800244bd  pop     r14
0x1800244bf  pop     r13
0x1800244c1  pop     r12
0x1800244c3  pop     rdi
0x1800244c4  pop     rsi
0x1800244c5  pop     rbp
0x1800244c6  retn
0x1800244c7  test    r13, r13
0x1800244ca  jz      loc_18002437E
0x1800244d0  mov     rsi, r13
0x1800244d3  jmp     loc_18002437E
0x1800244d8  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x1800244dd  mov     ebx, eax
0x1800244df  test    eax, eax
0x1800244e1  js      loc_180024655
0x1800244e7  mov     [rsp+1A0h+var_168], r12
0x1800244ec  jmp     loc_1800243B8
0x1800244f1  test    r13, r13
0x1800244f4  jz      loc_180024580
0x1800244fa  mov     r8, [rdi+8]; __int64
0x1800244fe  mov     edx, 3; int
0x180024503  lea     rcx, [rsp+1A0h+var_168]; this
0x180024508  call    ?BindIfWorkInProgress@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::BindIfWorkInProgress(int,__int64)
0x18002450d  mov     ebx, eax
0x18002450f  test    eax, eax
0x180024511  jns     short loc_180024580
0x180024513  mov     edx, 1Bh
0x180024518  jmp     loc_180024408
0x18002451d  lea     rcx, [rsp+1A0h+var_168]; this
0x180024522  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x180024527  mov     rcx, [rbp+0A8h]; this
0x18002452e  test    eax, eax
0x180024530  js      short loc_18002456A
0x180024532  lea     r9, [rsp+1A0h+var_168]; struct sqlite3_stmt **
0x180024537  mov     rdx, rsi; char *
0x18002453a  mov     rcx, [rdi]; struct sqlite3 *
0x18002453d  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x180024542  mov     ebx, eax
0x180024544  test    eax, eax
0x180024546  jns     loc_1800243E4
0x18002454c  jmp     loc_1800243A3
0x180024551  mov     r9d, ebx; char *
0x180024554  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x18002455b  mov     edx, 679h; void *
0x180024560  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024565  jmp     loc_1800243CA
0x18002456a  mov     r9d, eax; char *
0x18002456d  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\StateRepositor"...
0x180024574  mov     edx, 127h; void *
0x180024579  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002457e  jmp     short loc_180024532
0x180024580  mov     rcx, [rbp+0A0h+var_F0]
0x180024584  mov     rax, [rcx]
0x180024587  xor     edx, edx
0x180024589  mov     rax, [rax]
0x18002458c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024591  mov     rcx, [rsp+1A0h+var_168]; struct sqlite3_stmt *
0x180024596  test    rcx, rcx
0x180024599  jz      short loc_180024610
0x18002459b  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x1800245a0  mov     ebx, eax
0x1800245a2  cmp     eax, 87AF0064h
0x1800245a7  jz      short loc_180024600
0x1800245a9  mov     dil, r12b
0x1800245ac  cmp     eax, 87AF0065h
0x1800245b1  jz      short loc_180024603
0x1800245b3  test    eax, eax
0x1800245b5  js      short loc_180024630
0x1800245b7  test    dil, dil
0x1800245ba  jz      short loc_180024608
0x1800245bc  mov     [rsp+1A0h+var_160], r12
0x1800245c1  mov     [rsp+1A0h+var_158], r12
0x1800245c6  mov     [rsp+1A0h+var_150], r12
0x1800245cb  mov     [rsp+1A0h+string], r12
0x1800245d0  lea     rcx, [rsp+1A0h+var_160]
0x1800245d5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800245da  lea     r8, [rsp+1A0h+var_160]
0x1800245df  mov     rdx, qword ptr [rbp+0A0h+var_110+8]
0x1800245e3  mov     ecx, dword ptr [rbp+0A0h+var_100]
0x1800245e6  call    cs:__imp_SRDictionaryToPropertySet
0x1800245ec  mov     ebx, eax
0x1800245ee  test    eax, eax
0x1800245f0  jns     loc_1800246F1
0x1800245f6  mov     edx, 678h
0x1800245fb  jmp     loc_18002469A
0x180024600  mov     dil, 1
0x180024603  test    dil, dil
0x180024606  jnz     short loc_180024675
0x180024608  mov     ebx, r12d
0x18002460b  jmp     loc_180024481
0x180024610  mov     rcx, [rbp+0A8h]; this
0x180024617  mov     ebx, 8007139Fh
0x18002461c  mov     r9d, ebx; char *
0x18002461f  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\staterepositor"...
0x180024626  mov     edx, 3Fh ; '?'; void *
0x18002462b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024630  mov     edx, 1D7h; void *
0x180024635  mov     r9d, ebx; char *
0x180024638  lea     r8, aOnecoreBaseApp_91; "onecore\\base\\appmodel\\staterepositor"...
0x18002463f  mov     rcx, [rbp+0A8h]; this
0x180024646  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002464b  mov     edx, 66Fh
0x180024650  jmp     loc_18002446A
0x180024655  mov     rcx, [rbp+0A8h]; this
0x18002465c  mov     r9d, eax; char *
0x18002465f  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\staterepositor"...
0x180024666  mov     edx, 7Bh ; '{'; void *
0x18002466b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024670  jmp     loc_1800243BB
0x180024675  lea     rdx, [rsp+1A0h+var_140]; struct StateRepository::Entity::ApplicationProperty *
0x18002467a  lea     rcx, [rsp+1A0h+var_168]; this
0x18002467f  call    ?RowToObject@ApplicationProperty@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::ApplicationProperty::RowToObject(StateRepository::Statement const &,StateRepository::Entity::ApplicationProperty &,__int64)
0x180024684  mov     ebx, eax
0x180024686  test    eax, eax
0x180024688  jns     loc_1800245B7
0x18002468e  mov     edx, 1DAh
0x180024693  jmp     short loc_180024635
0x180024695  mov     edx, 67Bh; void *
0x18002469a  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800246a1  mov     r9d, eax; char *
0x1800246a4  mov     rcx, [rbp+0A8h]; this
0x1800246ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800246b0  nop
0x1800246b1  mov     rcx, [rsp+1A0h+string]; string
0x1800246b6  call    cs:__imp_WindowsDeleteString
0x1800246bc  mov     [rsp+1A0h+string], r12
0x1800246c1  lea     rcx, [rsp+1A0h+var_150]
0x1800246c6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800246cb  nop
0x1800246cc  lea     rcx, [rsp+1A0h+var_158]
0x1800246d1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800246d6  nop
0x1800246d7  lea     rcx, [rsp+1A0h+var_160]
0x1800246dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800246e1  nop
0x1800246e2  lea     rcx, [rsp+1A0h+var_140]; this
0x1800246e7  call    ??1PublisherCacheFolder@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PublisherCacheFolder::~PublisherCacheFolder(void)
0x1800246ec  jmp     loc_180024494
0x1800246f1  lea     rdx, [rsp+1A0h+var_158]
0x1800246f6  lea     rcx, [rsp+1A0h+var_160]
0x1800246fb  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x180024700  mov     ebx, eax
0x180024702  test    eax, eax
0x180024704  jns     short loc_18002470D
0x180024706  mov     edx, 679h
0x18002470b  jmp     short loc_18002469A
0x18002470d  mov     rdi, [rsp+1A0h+var_158]
0x180024712  mov     rax, [rdi]
0x180024715  mov     rbx, [rax+30h]
0x180024719  lea     rcx, [rsp+1A0h+var_150]
0x18002471e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180024723  mov     [rbp+0A0h+var_48], r12
0x180024727  mov     r9d, 5; unsigned int
0x18002472d  lea     r8d, [r9+1]; unsigned int
0x180024731  lea     rdx, aText_0; "#text"
0x180024738  lea     rcx, [rbp+0A0h+hstringHeader]; hstringHeader
0x18002473c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180024741  nop
0x180024742  lea     r8, [rsp+1A0h+var_150]
0x180024747  mov     rdx, [rbp+0A0h+var_48]
0x18002474b  mov     rcx, rdi
0x18002474e  mov     rax, rbx
0x180024751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024756  mov     ebx, eax
0x180024758  test    eax, eax
0x18002475a  jns     short loc_180024766
0x18002475c  mov     edx, 67Ah
0x180024761  jmp     loc_18002469A
0x180024766  mov     rdi, [rsp+1A0h+var_150]
0x18002476b  mov     rax, [rdi]
0x18002476e  mov     rbx, [rax+98h]
0x180024775  mov     rcx, [rsp+1A0h+string]; string
0x18002477a  call    cs:__imp_WindowsDeleteString
0x180024780  mov     [rsp+1A0h+string], r12
0x180024785  lea     rdx, [rsp+1A0h+string]
0x18002478a  mov     rcx, rdi
0x18002478d  mov     rax, rbx
0x180024790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024795  mov     ebx, eax
0x180024797  test    eax, eax
0x180024799  js      loc_180024695
  ... truncated ...
```
