# OSIntegration::DEH::RuntimeExtensionHandler::CalculateLoaderSearchPath(__int64,ushort const *,ushort const *,Common::StringBuffer &)

- ea: `0x18002bf90`
- end: `0x18002ca6a`
- name: `?CalculateLoaderSearchPath@RuntimeExtensionHandler@DEH@OSIntegration@@IEAAJ_JPEBG1AEAVStringBuffer@Common@@@Z`
- size: `2778`
- prototype: `__int64 __fastcall(OSIntegration::DEH::RuntimeExtensionHandler *__hidden this, __int64, const unsigned __int16 *, const unsigned __int16 *, struct Common::StringBuffer *)`
- caller_count: `2`
- callee_count: `26`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180020b04`
- `0x18009406c`

## callees

- `0x18000b3bc`
- `0x180027364`
- `0x1800274d0`
- `0x18002788c`
- `0x180029278`
- `0x18002afe8`
- `0x18002bf90`
- `0x18002cb58`
- `0x18002cbe4`
- `0x18002cc90`
- `0x18002cda8`
- `0x18003b8d4`
- `0x18003b990`
- `0x180077608`
- `0x18007b440`
- `0x18008b6bc`
- `0x180098bf4`
- `0x1800a0f24`
- `0x1800a219c`
- `0x1800f0260`
- `0x18012504c`
- `0x1801256cc`
- `0x18012829c`
- `0x18017678c`
- `0x18017d1b0`
- `0x180211010`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x18002c369`
- `StateRepository.Core!sqlite3_bind_int64` at `0x18002c369`

## string_xrefs

- `0x18002c0f4`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002c10c`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x18002c070`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18002c3ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x18002c153`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c28f`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c4d3`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c53f`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c593`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c5cd`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c64a`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c686`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c78e`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c8c8`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002c99b`: `onecore\admin\appmodel\osim\src\deh\appx\runtime\runtimeextensionhandler.cpp`
- `0x18002bfe8`: `windows.loaderSearchPathOverride`
- `0x18002c055`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x18002c127`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension.cpp`
- `0x18002c272`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension.cpp`
- `0x18002c035`: `SELECT _PackageExtensionID, _Revision, _WorkId, Package, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM PackageExtension WHERE Package=? AND Category=? AND _WorkId=0;`
- `0x18002c03c`: `SELECT _PackageExtensionID, _Revision, _WorkId, Package, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM PackageExtension WHERE Package=? AND Category=? AND (_WorkId=0 OR _WorkId=?);`
- `0x18002c208`: `SELECT _PackageExtensionID, _Revision, _WorkId, Package, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM PackageExtension WHERE Package=? AND Category=? AND (_WorkId=0 OR _WorkId=?);`
- `0x18002c3c7`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x18002c60f`: `LoaderSearchPathOverride`
- `0x18002c6c5`: `LoaderSearchPathEntry`
- `0x18002c738`: `LoaderSearchPathEntry`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall OSIntegration::DEH::RuntimeExtensionHandler::CalculateLoaderSearchPath(
        OSIntegration::DEH::RuntimeExtensionHandler *this,
        void *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        struct Common::StringBuffer *a5)
{
  __int64 v7; // rsi
  const char *v8; // rdi
  int v9; // ebx
  unsigned int v10; // edi
  unsigned int v11; // esi
  int v12; // eax
  int v14; // eax
  unsigned int v15; // ebx
  int v16; // ebx
  int v17; // eax
  char v18; // di
  __int64 v19; // rdx
  int v20; // eax
  int v21; // eax
  int v22; // eax
  int v23; // r8d
  int appended; // eax
  int v25; // eax
  void *v26; // rbx
  int v27; // edi
  _QWORD *p_hstringHeader; // rdx
  char v29; // al
  unsigned int v30; // r8d
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdi
  __int64 (__fastcall *v34)(__int64, __int64, __int64 *); // rbx
  int v35; // eax
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rdi
  __int64 (__fastcall *v39)(__int64, __int64, _BYTE *); // rbx
  __int64 v40; // rdi
  __int64 (__fastcall *v41)(__int64, __int64, char *); // rbx
  __int64 v42; // rdx
  unsigned __int64 v43; // r9
  int Type; // eax
  void *v45; // rdi
  OSIntegration::DEH::RuntimeExtensionHandler *v46; // rcx
  int v47; // eax
  unsigned __int64 v48; // r9
  __int64 v49; // rdx
  unsigned int i; // ebx
  int v51; // eax
  int v52; // edi
  const char **v53; // [rsp+20h] [rbp-E0h]
  int v54; // [rsp+20h] [rbp-E0h]
  int v55; // [rsp+20h] [rbp-E0h]
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+20h] [rbp-E0h]
  int v58; // [rsp+20h] [rbp-E0h]
  int v59; // [rsp+20h] [rbp-E0h]
  int v60; // [rsp+20h] [rbp-E0h]
  int v61; // [rsp+20h] [rbp-E0h]
  int v62; // [rsp+20h] [rbp-E0h]
  _BYTE v63[8]; // [rsp+30h] [rbp-D0h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v64; // [rsp+38h] [rbp-C8h] BYREF
  struct sqlite3_stmt *v65; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v66; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v67; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v68; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v69; // [rsp+60h] [rbp-A0h] BYREF
  void *v70; // [rsp+68h] [rbp-98h] BYREF
  char *v71; // [rsp+70h] [rbp-90h]
  const unsigned __int16 *v72; // [rsp+78h] [rbp-88h] BYREF
  int v73[2]; // [rsp+80h] [rbp-80h] BYREF
  struct Common::StringBuffer *v74; // [rsp+88h] [rbp-78h]
  struct Common::StringBuffer *v75; // [rsp+90h] [rbp-70h]
  _QWORD *v76; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v77[29]; // [rsp+A8h] [rbp-58h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+190h] [rbp+90h] BYREF
  __int64 v79; // [rsp+1A8h] [rbp+A8h]
  HSTRING_HEADER v80; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v81; // [rsp+1C8h] [rbp+C8h]
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v74 = a5;
  *(_QWORD *)v73 = &Common::StringBufferBuilder::`vftable';
  v75 = a5;
  v65 = 0;
  v72 = L"windows.loaderSearchPathOverride";
  v80.Reserved.Reserved1 = a2;
  v7 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  v77[0] = off_180212320;
  v77[1] = &v80;
  v77[2] = &v72;
  v76 = v77;
  v8 = "SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Category, Activation, HostId, Executable, Ent"
       "rypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM Pac"
       "kageExtension WHERE Package=? AND Category=? AND _WorkId=0;";
  *(_DWORD *)&hstringHeader.Reserved.Reserved2[20] = 0;
  if ( *(_QWORD *)(v7 + 8)
    && "SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Category, Activation, HostId, Executable, Ent"
       "rypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM Pac"
       "kageExtension WHERE Package=? AND Category=? AND (_WorkId=0 OR _WorkId=?);" )
  {
    v8 = "SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Category, Activation, HostId, Executable, E"
         "ntrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM"
         " PackageExtension WHERE Package=? AND Category=? AND (_WorkId=0 OR _WorkId=?);";
  }
  if ( *(_QWORD *)v7 )
  {
    if ( !StateRepository::StatementCache::Get(
            (StateRepository::StatementCache *)(v7 + 40),
            v8,
            (struct StateRepository::Statement *)&v65) )
    {
      v22 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v65);
      if ( v22 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x127,
          (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
          (const char *)(unsigned int)v22,
          (int)v53);
      v9 = StateRepository::Database::dal_prepare_v2(*(struct sqlite3 **)v7, v8, v23, &v65, v53);
      if ( v9 < 0 )
        goto LABEL_4;
    }
    v12 = (*(__int64 (__fastcall **)(_QWORD *, struct sqlite3_stmt **))(*v76 + 8LL))(v76, &v65);
    v10 = v12;
    if ( v12 < 0 )
    {
      v11 = 23;
      v9 = v12;
      goto LABEL_8;
    }
    v16 = -2147019873;
    if ( "SELECT _PackageExtensionID, _Revision, _WorkId, Package, \"Index\", Category, Activation, HostId, Executable, E"
         "ntrypoint, RuntimeType, StartPage, Flags, Parameters, CurrentDirectoryPath, Id, ResourceGroup, _Dictionary FROM"
         " PackageExtension WHERE Package=? AND Category=? AND (_WorkId=0 OR _WorkId=?);"
      && *(_QWORD *)(v7 + 8) )
    {
      if ( v65 )
      {
        v21 = sqlite3_bind_int64();
        v10 = v21;
        if ( v21 > 0 )
          v10 = (unsigned __int16)v21 | 0x87AF0000;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)0x8007139FLL,
          (int)v53);
        v10 = -2147019873;
      }
      if ( (v10 & 0x80000000) != 0 )
      {
        v11 = 27;
        v9 = v10;
        goto LABEL_8;
      }
    }
    (*(void (__fastcall **)(_QWORD *, _QWORD))*v76)(v76, 0);
    StateRepository::Entity::PackageExtension::PackageExtension((StateRepository::Entity::PackageExtension *)&v76);
    if ( !v65 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)0x8007139FLL,
        (int)v53);
      goto LABEL_20;
    }
    v17 = StateRepository::Statement::dal_step(v65);
    v16 = v17;
    if ( v17 == -2018574236 )
    {
      v18 = 1;
    }
    else
    {
      v18 = 0;
      if ( v17 != -2018574235 )
      {
        if ( v17 < 0 )
        {
LABEL_20:
          v19 = 806;
          goto LABEL_21;
        }
        goto LABEL_40;
      }
    }
    if ( !v18 )
      goto LABEL_41;
    v16 = StateRepository::Entity::PackageExtension::RowToObject(
            (const struct StateRepository::Statement *)&v65,
            (struct StateRepository::Entity::PackageExtension *)&v76,
            0);
    if ( v16 < 0 )
    {
      v19 = 809;
LABEL_21:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension.cpp",
        (const char *)(unsigned int)v16,
        (int)v53);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D4,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v16,
        v59);
      StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)&v76);
      v20 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v65);
      if ( v20 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x16,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
          (const char *)(unsigned int)v20,
          v60);
      return (unsigned int)v16;
    }
LABEL_40:
    if ( !v18 )
    {
LABEL_41:
      if ( !a4 || !*a4 )
        a4 = a3;
      appended = Common::StringBuilder::AppendString((Common::StringBuilder *)v73, a4);
      v16 = appended;
      if ( appended >= 0 )
      {
        StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)&v76);
        v25 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v65);
        if ( v25 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x16,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
            (const char *)(unsigned int)v25,
            (int)v53);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)appended,
        (int)v53);
LABEL_78:
      StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)&v76);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v65);
      return (unsigned int)v16;
    }
    v64 = 0;
    v68 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
    v31 = StateRepository::DictionarySerialization::WinRTReader::DeserializeAsPropertySet(
            (StateRepository::DictionarySerialization::WinRTReader *)&v68,
            v77[27],
            (const void *)v77[26],
            &v64,
            (struct IInspectable *)v53);
    v16 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E3,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v31,
        v61);
LABEL_77:
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      goto LABEL_78;
    }
    v67 = 0;
    v32 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v64,
            &v67);
    v16 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v32,
        v61);
LABEL_76:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      goto LABEL_77;
    }
    v66 = 0;
    v33 = v67;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v67 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"LoaderSearchPathOverride",
      0x19u,
      0x18u);
    v35 = v34(v33, v79, &v66);
    v16 = v35;
    if ( v35 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4EC,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v35,
        v61);
LABEL_75:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      goto LABEL_76;
    }
    v69 = 0;
    v36 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            &v66,
            &v69);
    v16 = v36;
    if ( v36 < 0 )
    {
      v37 = 1263;
LABEL_66:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v36,
        v61);
LABEL_74:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      goto LABEL_75;
    }
    v63[0] = 0;
    v38 = v69;
    v39 = *(__int64 (__fastcall **)(__int64, __int64, _BYTE *))(*(_QWORD *)v69 + 64LL);
    v79 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"LoaderSearchPathEntry", 0x16u, 0x15u);
    v36 = v39(v38, v79, v63);
    v16 = v36;
    if ( v36 < 0 )
    {
      v37 = 1271;
      goto LABEL_66;
    }
    if ( !v63[0] )
    {
LABEL_101:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
      wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v68);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
      StateRepository::Entity::PackageExtension::~PackageExtension((StateRepository::Entity::PackageExtension *)&v76);
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v65);
      return 0;
    }
    v70 = 0;
    LODWORD(v71) = 0;
    v40 = v69;
    v41 = *(__int64 (__fastcall **)(__int64, __int64, char *))(*(_QWORD *)v69 + 48LL);
    hstringHeader.Reserved.Reserved1 = &v70;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    v81 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v80, L"LoaderSearchPathEntry", 0x16u, 0x15u);
    v16 = v41(v40, v81, &hstringHeader.Reserved.Reserved2[8]);
    v81 = 0;
    RoVariant::Attach(
      (RoVariant *)hstringHeader.Reserved.Reserved1,
      *(struct IInspectable **)&hstringHeader.Reserved.Reserved2[8]);
    if ( v16 < 0 )
    {
      v42 = 1278;
LABEL_71:
      v43 = (unsigned int)v16;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v42,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)v43,
        v61);
      goto LABEL_73;
    }
    LODWORD(v72) = 0;
    hstringHeader.Reserved.Reserved1 = v70;
    *(_DWORD *)&hstringHeader.Reserved.Reserved2[8] = (_DWORD)v71;
    Type = RoVariant::Accessor::get_Type(
             (RoVariant::Accessor *)&hstringHeader,
             (enum Windows::Foundation::PropertyType *)&v72);
    v16 = Type;
    if ( Type < 0 )
    {
      v43 = (unsigned int)Type;
      v42 = 1281;
      goto LABEL_72;
    }
    if ( (_DWORD)v72 == 13 )
    {
      v80.Reserved.Reserved1 = 0;
      v45 = v70;
      v16 = (int)v71;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
      v80.Reserved.Reserved1 = 0;
      if ( v16 >= 0 )
      {
        if ( v16 && ((v16 - 1) & 0xFFFFFFFD) == 0 )
        {
          v80.Reserved.Reserved1 = v45;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 8LL))(v45);
          v47 = OSIntegration::DEH::RuntimeExtensionHandler::AddEntryToLoaderSearchPath(
                  v46,
                  (struct IInspectable *)v80.Reserved.Reserved1,
                  a3,
                  a4,
                  (struct Common::StringBufferBuilder *)v73);
          v16 = v47;
          if ( v47 < 0 )
          {
            v48 = (unsigned int)v47;
            v49 = 1290;
LABEL_89:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v49,
              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
              (const char *)v48,
              v61);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
            goto LABEL_73;
          }
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v80);
          goto LABEL_100;
        }
        v16 = -2147316576;
      }
      v48 = (unsigned int)v16;
      v49 = 1287;
      goto LABEL_89;
    }
    if ( (_DWORD)v72 != 1037 )
    {
      v16 = -2147418113;
      v42 = 1308;
      goto LABEL_71;
    }
    *(_OWORD *)&hstringHeader.Reserved.Reserved1 = 0u;
    v26 = v70;
    v27 = (int)v71;
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&hstringHeader);
    p_hstringHeader = &hstringHeader;
    v80.Reserved.Reserved1 = &hstringHeader;
    v29 = 1;
    v80.Reserved.Reserved2[12] = 1;
    v30 = 0;
    *(_DWORD *)&v80.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved1 = 0;
    if ( v27 == 7 )
    {
      v16 = (*(__int64 (__fastcall **)(void *, char *, HSTRING_HEADER *))(*(_QWORD *)v26 + 304LL))(
              v26,
              &v80.Reserved.Reserved2[8],
              &hstringHeader);
      v29 = v80.Reserved.Reserved2[12];
      v30 = *(_DWORD *)&v80.Reserved.Reserved2[8];
      p_hstringHeader = v80.Reserved.Reserved1;
    }
    else
    {
      v16 = -2147316576;
      if ( v27 < 0 )
        v16 = v27;
    }
    if ( v29 )
      p_hstringHeader[1] = v30;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x512,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
        (const char *)(unsigned int)v16,
        v61);
      wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&hstringHeader);
LABEL_73:
      RoVariant::~RoVariant((RoVariant *)&v70);
      goto LABEL_74;
    }
    for ( i = 0; (unsigned __int64)i < *(_QWORD *)&hstringHeader.Reserved.Reserved2[8]; ++i )
    {
      v51 = OSIntegration::DEH::RuntimeExtensionHandler::AddEntryToLoaderSearchPath(
              (OSIntegration::DEH::RuntimeExtensionHandler *)v73,
              *((struct IInspectable **)hstringHeader.Reserved.Reserved1 + i),
              a3,
              a4,
              (struct Common::StringBufferBuilder *)v73);
      v52 = v51;
      if ( v51 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x517,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
          (const char *)(unsigned int)v51,
          v62);
        wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&hstringHeader);
        RoVariant::~RoVariant((RoVariant *)&v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v69);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v66);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v67);
        wil::com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IMap<_GUID,OSIntegration::DEH::Internal::ComClassRegistrationCombinedProperties *>,wil::err_returncode_policy>(&v68);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v64);
        v16 = v52;
        goto LABEL_78;
      }
    }
    wil::unique_any_array_ptr<IInspectable *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::com_unknown_deleter,unsigned __int64>::reset(&hstringHeader);
LABEL_100:
    RoVariant::~RoVariant((RoVariant *)&v70);
    goto LABEL_101;
  }
  v9 = -2147019873;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x66E,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
    (const char *)0x8007139FLL,
    (int)v53);
LABEL_4:
  v10 = v9;
  v11 = 21;
LABEL_8:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v11,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)(unsigned int)v9,
    (int)v53);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE8,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
    (const char *)v10,
    v54);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x31D,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension.cpp",
    (const char *)v10,
    v55);
  (*(void (__fastcall **)(_QWORD *, _QWORD))*v76)(v76, 0);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4D0,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\runtime\\runtimeextensionhandler.cpp",
    (const char *)v10,
    v56);
  if ( v65 )
  {
    v14 = StateRepository::Statement::dal_finalize(v65);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)(unsigned int)v14,
        v57);
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x16,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
        (const char *)v15,
        v58);
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002bf90  mov     [rsp-8+arg_8], rbx
0x18002bf95  push    rbp
0x18002bf96  push    rsi
0x18002bf97  push    rdi
0x18002bf98  push    r12
0x18002bf9a  push    r13
0x18002bf9c  push    r14
0x18002bf9e  push    r15
0x18002bfa0  lea     rbp, [rsp-0E0h]
0x18002bfa8  sub     rsp, 1E0h
0x18002bfaf  mov     rax, cs:__security_cookie
0x18002bfb6  xor     rax, rsp
0x18002bfb9  mov     [rbp+110h+var_40], rax
0x18002bfc0  mov     r14, r9
0x18002bfc3  mov     r15, r8
0x18002bfc6  mov     rax, [rbp+110h+arg_20]
0x18002bfcd  mov     [rbp+110h+var_188], rax
0x18002bfd1  lea     r8, ??_7StringBufferBuilder@Common@@6B@; const Common::StringBufferBuilder::`vftable'
0x18002bfd8  mov     qword ptr [rbp+110h+var_190], r8
0x18002bfdc  mov     [rbp+110h+var_180], rax
0x18002bfe0  xor     r12d, r12d
0x18002bfe3  mov     [rsp+210h+var_1D0], r12
0x18002bfe8  lea     rax, ?ExtensionCategoryLoaderSearchPathOverride@Attribute@Manifest@Packaging@Appx@@3QBGB; "windows.loaderSearchPathOverride"
0x18002bfef  mov     [rsp+210h+var_198], rax
0x18002bff4  mov     qword ptr [rbp+110h+var_60.Reserved], rdx
0x18002bffb  mov     rcx, [rcx+18h]
0x18002bfff  mov     rax, [rcx]
0x18002c002  mov     rax, [rax+8]
0x18002c006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c00b  mov     rsi, rax
0x18002c00e  lea     rax, off_180212320
0x18002c015  mov     [rbp+110h+var_168], rax
0x18002c019  lea     rax, [rbp+110h+var_60]
0x18002c020  mov     [rbp+110h+var_160], rax
0x18002c024  lea     rax, [rsp+210h+var_198]
0x18002c029  mov     [rbp+110h+var_158], rax
0x18002c02d  lea     rax, [rbp+110h+var_168]
0x18002c031  mov     [rbp+110h+var_170], rax
0x18002c035  lea     rdi, aSelectPackagee_2; "SELECT _PackageExtensionID, _Revision, "...
0x18002c03c  lea     rcx, aSelectPackagee; "SELECT _PackageExtensionID, _Revision, "...
0x18002c043  xor     eax, eax
0x18002c045  mov     dword ptr [rbp+110h+hstringHeader.Reserved+14h], eax
0x18002c04b  cmp     [rsi+8], r12
0x18002c04f  jnz     loc_18002C19B
0x18002c055  lea     r13, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\staterepositor"...
0x18002c05c  cmp     [rsi], r12
0x18002c05f  jnz     short loc_18002C08A
0x18002c061  mov     rcx, [rbp+118h]; this
0x18002c068  mov     ebx, 8007139Fh
0x18002c06d  mov     r9d, ebx; char *
0x18002c070  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x18002c077  mov     edx, 66Eh; void *
0x18002c07c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c081  mov     edi, ebx
0x18002c083  mov     esi, 15h
0x18002c088  jmp     short loc_18002C0EA
0x18002c08a  mov     rcx, [rsp+210h+var_1D0]; struct sqlite3_stmt *
0x18002c08f  test    rcx, rcx
0x18002c092  jnz     loc_18002C1AC
0x18002c098  mov     ebx, r12d
0x18002c09b  mov     rcx, [rbp+118h]; this
0x18002c0a2  test    ebx, ebx
0x18002c0a4  js      loc_18002C3AB
0x18002c0aa  lea     rcx, [rsi+28h]; this
0x18002c0ae  lea     r8, [rsp+210h+var_1D0]; struct StateRepository::Statement *
0x18002c0b3  mov     rdx, rdi; char *
0x18002c0b6  call    ?Get@StatementCache@StateRepository@@QEAAPEAVStatement@2@PEBDAEAV32@@Z; StateRepository::StatementCache::Get(char const *,StateRepository::Statement &)
0x18002c0bb  test    rax, rax
0x18002c0be  jz      loc_18002C377
0x18002c0c4  mov     rcx, [rbp+110h+var_170]
0x18002c0c8  mov     rax, [rcx]
0x18002c0cb  lea     rdx, [rsp+210h+var_1D0]
0x18002c0d0  mov     rax, [rax+8]
0x18002c0d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c0d9  mov     edi, eax
0x18002c0db  test    eax, eax
0x18002c0dd  jns     loc_18002C203
0x18002c0e3  mov     esi, 17h
0x18002c0e8  mov     ebx, eax
0x18002c0ea  mov     rcx, [rbp+118h]; this
0x18002c0f1  mov     r9d, ebx; char *
0x18002c0f4  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\staterepositor"...
0x18002c0fb  mov     edx, esi; void *
0x18002c0fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c102  mov     rcx, [rbp+118h]; this
0x18002c109  mov     r9d, edi; char *
0x18002c10c  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\staterepositor"...
0x18002c113  mov     edx, 0E8h; void *
0x18002c118  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c11d  mov     rcx, [rbp+118h]; this
0x18002c124  mov     r9d, edi; char *
0x18002c127  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18002c12e  mov     edx, 31Dh; void *
0x18002c133  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c138  mov     rcx, [rbp+110h+var_170]
0x18002c13c  mov     rax, [rcx]
0x18002c13f  xor     edx, edx
0x18002c141  mov     rax, [rax]
0x18002c144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c149  mov     rcx, [rbp+118h]; this
0x18002c150  mov     r9d, edi; char *
0x18002c153  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002c15a  mov     edx, 4D0h; void *
0x18002c15f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c164  nop
0x18002c165  mov     rcx, [rsp+210h+var_1D0]; struct sqlite3_stmt *
0x18002c16a  test    rcx, rcx
0x18002c16d  jnz     short loc_18002C1C5
0x18002c16f  mov     eax, edi
0x18002c171  mov     rcx, [rbp+110h+var_40]
0x18002c178  xor     rcx, rsp; StackCookie
0x18002c17b  call    __security_check_cookie
0x18002c180  mov     rbx, [rsp+210h+arg_8]
0x18002c188  add     rsp, 1E0h
0x18002c18f  pop     r15
0x18002c191  pop     r14
0x18002c193  pop     r13
0x18002c195  pop     r12
0x18002c197  pop     rdi
0x18002c198  pop     rsi
0x18002c199  pop     rbp
0x18002c19a  retn
0x18002c19b  test    rcx, rcx
0x18002c19e  jz      loc_18002C055
0x18002c1a4  mov     rdi, rcx
0x18002c1a7  jmp     loc_18002C055
0x18002c1ac  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x18002c1b1  mov     ebx, eax
0x18002c1b3  test    eax, eax
0x18002c1b5  js      loc_18002C4F6
0x18002c1bb  mov     [rsp+210h+var_1D0], r12
0x18002c1c0  jmp     loc_18002C098
0x18002c1c5  call    ?dal_finalize@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_finalize(sqlite3_stmt *)
0x18002c1ca  mov     ebx, eax
0x18002c1cc  test    eax, eax
0x18002c1ce  jns     short loc_18002C16F
0x18002c1d0  mov     rcx, [rbp+118h]; this
0x18002c1d7  mov     r9d, eax; char *
0x18002c1da  mov     r8, r13; unsigned int
0x18002c1dd  mov     edx, 7Bh ; '{'; void *
0x18002c1e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c1e7  mov     rcx, [rbp+118h]; this
0x18002c1ee  mov     r9d, ebx; char *
0x18002c1f1  mov     r8, r13; unsigned int
0x18002c1f4  mov     edx, 16h; void *
0x18002c1f9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c1fe  jmp     loc_18002C16F
0x18002c203  mov     ebx, 8007139Fh
0x18002c208  lea     rax, aSelectPackagee; "SELECT _PackageExtensionID, _Revision, "...
0x18002c20f  test    rax, rax
0x18002c212  jz      short loc_18002C221
0x18002c214  mov     r8, [rsi+8]
0x18002c218  test    r8, r8
0x18002c21b  jnz     loc_18002C30E
0x18002c221  mov     rcx, [rbp+110h+var_170]
0x18002c225  mov     rax, [rcx]
0x18002c228  xor     edx, edx
0x18002c22a  mov     rax, [rax]
0x18002c22d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c232  lea     rcx, [rbp+110h+var_170]; this
0x18002c236  call    ??0PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::PackageExtension(void)
0x18002c23b  nop
0x18002c23c  mov     rcx, [rsp+210h+var_1D0]; struct sqlite3_stmt *
0x18002c241  test    rcx, rcx
0x18002c244  jz      short loc_18002C2C4
0x18002c246  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x18002c24b  mov     ebx, eax
0x18002c24d  cmp     eax, 87AF0064h
0x18002c252  jz      loc_18002C2DD
0x18002c258  mov     dil, r12b
0x18002c25b  cmp     eax, 87AF0065h
0x18002c260  jz      short loc_18002C2E0
0x18002c262  test    eax, eax
0x18002c264  jns     loc_18002C3F6
0x18002c26a  mov     edx, 326h; void *
0x18002c26f  mov     r9d, ebx; char *
0x18002c272  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18002c279  mov     rcx, [rbp+118h]; this
0x18002c280  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c285  mov     rcx, [rbp+118h]; this
0x18002c28c  mov     r9d, ebx; char *
0x18002c28f  lea     r8, aOnecoreAdminAp_1; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18002c296  mov     edx, 4D4h; void *
0x18002c29b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c2a0  nop
0x18002c2a1  lea     rcx, [rbp+110h+var_170]; this
0x18002c2a5  call    ??1PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::~PackageExtension(void)
0x18002c2aa  nop
0x18002c2ab  lea     rcx, [rsp+210h+var_1D0]; this
0x18002c2b0  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18002c2b5  test    eax, eax
0x18002c2b7  js      loc_18002C3DA
0x18002c2bd  mov     eax, ebx
0x18002c2bf  jmp     loc_18002C171
0x18002c2c4  mov     rcx, [rbp+118h]; this
0x18002c2cb  mov     r9d, ebx; char *
0x18002c2ce  mov     r8, r13; unsigned int
0x18002c2d1  mov     edx, 3Fh ; '?'; void *
0x18002c2d6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c2db  jmp     short loc_18002C26A
0x18002c2dd  mov     dil, 1
0x18002c2e0  test    dil, dil
0x18002c2e3  jz      loc_18002C3FF
0x18002c2e9  xor     r8d, r8d; __int64
0x18002c2ec  lea     rdx, [rbp+110h+var_170]; struct StateRepository::Entity::PackageExtension *
0x18002c2f0  lea     rcx, [rsp+210h+var_1D0]; this
0x18002c2f5  call    ?RowToObject@PackageExtension@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::PackageExtension::RowToObject(StateRepository::Statement const &,StateRepository::Entity::PackageExtension &,__int64)
0x18002c2fa  mov     ebx, eax
0x18002c2fc  test    eax, eax
0x18002c2fe  jns     loc_18002C3F6
0x18002c304  mov     edx, 329h
0x18002c309  jmp     loc_18002C26F
0x18002c30e  mov     rcx, [rbp+118h]; this
0x18002c315  mov     edx, 3
0x18002c31a  mov     eax, edx
0x18002c31c  shr     eax, 1Fh
0x18002c31f  test    al, al
0x18002c321  jnz     loc_18002C512
0x18002c327  mov     rcx, [rsp+210h+var_1D0]
0x18002c32c  test    rcx, rcx
0x18002c32f  jnz     short loc_18002C369
0x18002c331  mov     rcx, [rbp+118h]; this
0x18002c338  mov     r9d, ebx; char *
0x18002c33b  mov     r8, r13; unsigned int
0x18002c33e  mov     edx, 0C9h; void *
0x18002c343  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c348  mov     edi, ebx
0x18002c34a  jmp     short loc_18002C355
0x18002c34c  movzx   edi, ax
0x18002c34f  or      edi, 87AF0000h
0x18002c355  test    edi, edi
0x18002c357  jns     loc_18002C221
0x18002c35d  mov     esi, 1Bh
0x18002c362  mov     ebx, edi
0x18002c364  jmp     loc_18002C0EA
0x18002c369  call    cs:__imp_sqlite3_bind_int64
0x18002c36f  mov     edi, eax
0x18002c371  test    eax, eax
0x18002c373  jg      short loc_18002C34C
0x18002c375  jmp     short loc_18002C355
0x18002c377  lea     rcx, [rsp+210h+var_1D0]; this
0x18002c37c  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18002c381  mov     rcx, [rbp+118h]; this
0x18002c388  test    eax, eax
0x18002c38a  js      short loc_18002C3C4
0x18002c38c  lea     r9, [rsp+210h+var_1D0]; struct sqlite3_stmt **
0x18002c391  mov     rdx, rdi; char *
0x18002c394  mov     rcx, [rsi]; struct sqlite3 *
0x18002c397  call    ?dal_prepare_v2@Database@StateRepository@@SAJPEAUsqlite3@@PEBDHPEAPEAUsqlite3_stmt@@PEAPEBD@Z; StateRepository::Database::dal_prepare_v2(sqlite3 *,char const *,int,sqlite3_stmt * *,char const * *)
0x18002c39c  mov     ebx, eax
0x18002c39e  test    eax, eax
0x18002c3a0  jns     loc_18002C0C4
0x18002c3a6  jmp     loc_18002C081
0x18002c3ab  mov     r9d, ebx; char *
0x18002c3ae  lea     r8, aOnecoreBaseApp_92; "onecore\\base\\appmodel\\staterepositor"...
0x18002c3b5  mov     edx, 679h; void *
0x18002c3ba  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c3bf  jmp     loc_18002C0AA
0x18002c3c4  mov     r9d, eax; char *
0x18002c3c7  lea     r8, aOnecoreBaseApp_37; "onecore\\base\\appmodel\\StateRepositor"...
0x18002c3ce  mov     edx, 127h; void *
0x18002c3d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c3d8  jmp     short loc_18002C38C
0x18002c3da  mov     rcx, [rbp+118h]; this
0x18002c3e1  mov     r9d, eax; char *
0x18002c3e4  mov     r8, r13; unsigned int
0x18002c3e7  mov     edx, 16h; void *
0x18002c3ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c3f1  jmp     loc_18002C2BD
0x18002c3f6  test    dil, dil
0x18002c3f9  jnz     loc_18002C555
0x18002c3ff  test    r14, r14
0x18002c402  jnz     loc_18002C526
0x18002c408  mov     r14, r15
0x18002c40b  mov     rdx, r14; unsigned __int16 *
0x18002c40e  lea     rcx, [rbp+110h+var_190]; this
0x18002c412  call    ?AppendString@StringBuilder@Common@@QEAAJPEBG@Z; Common::StringBuilder::AppendString(ushort const *)
0x18002c417  mov     ebx, eax
0x18002c419  test    eax, eax
0x18002c41b  js      loc_18002C535
0x18002c421  lea     rcx, [rbp+110h+var_170]; this
0x18002c425  call    ??1PackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::PackageExtension::~PackageExtension(void)
0x18002c42a  nop
0x18002c42b  lea     rcx, [rsp+210h+var_1D0]; this
0x18002c430  call    ?Finalize@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::Finalize(void)
0x18002c435  test    eax, eax
0x18002c437  js      short loc_18002C440
0x18002c439  xor     eax, eax
0x18002c43b  jmp     loc_18002C171
0x18002c440  mov     rcx, [rbp+118h]; this
0x18002c447  mov     r9d, eax; char *
0x18002c44a  mov     r8, r13; unsigned int
0x18002c44d  mov     edx, 16h; void *
0x18002c452  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002c457  jmp     short loc_18002C439
0x18002c459  mov     qword ptr [rbp+110h+hstringHeader.Reserved], r12
0x18002c460  mov     qword ptr [rbp+110h+hstringHeader.Reserved+8], r12
0x18002c467  mov     rbx, [rsp+210h+var_1A8]
0x18002c46c  mov     edi, dword ptr [rsp+210h+var_1A0]
0x18002c470  lea     rcx, [rbp+110h+hstringHeader]
  ... truncated ...
```
