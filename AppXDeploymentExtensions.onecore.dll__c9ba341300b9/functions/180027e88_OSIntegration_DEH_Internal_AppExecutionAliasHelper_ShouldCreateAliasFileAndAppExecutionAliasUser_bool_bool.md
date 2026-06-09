# OSIntegration::DEH::Internal::AppExecutionAliasHelper::ShouldCreateAliasFileAndAppExecutionAliasUser(bool &,bool &)

- ea: `0x180027e88`
- end: `0x180028f8c`
- name: `?ShouldCreateAliasFileAndAppExecutionAliasUser@AppExecutionAliasHelper@Internal@DEH@OSIntegration@@AEAAJAEA_N0@Z`
- size: `4356`
- prototype: `__int64 __fastcall(struct sqlite3_stmt **this, bool *, bool *)`
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18015f3c0`

## callees

- `0x18001ee58`
- `0x1800212a8`
- `0x180025910`
- `0x180025ff8`
- `0x180026e08`
- `0x180026e3c`
- `0x180027364`
- `0x1800273e0`
- `0x1800274d0`
- `0x1800276b8`
- `0x1800276d0`
- `0x18002788c`
- `0x180027e88`
- `0x180029214`
- `0x180029278`
- `0x18002afe8`
- `0x18002faa0`
- `0x18002fff4`
- `0x18003012c`
- `0x1800306dc`
- `0x180030920`
- `0x18006c810`
- `0x18006cc28`
- `0x18008b414`
- `0x1800906d8`
- `0x1800911c4`
- `0x180092894`
- `0x180092ff4`
- `0x180098bf4`
- `0x1800a219c`
- `0x1800ad204`
- `0x1800bd0cc`
- `0x1800bfaac`
- `0x1800cb924`
- `0x1800cc82c`
- `0x1800ce098`
- `0x1800f0260`
- `0x1801841f8`
- `0x1801842a0`
- `0x1801843e8`
- `0x1801844b8`
- `0x180211010`

## import_xrefs

- `StateRepository.Core!sqlite3_bind_int64` at `0x180028809`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180028841`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180028809`
- `StateRepository.Core!sqlite3_bind_int64` at `0x180028841`

## string_xrefs

- `0x180028462`: `onecore\base\appmodel\staterepository\dataaccesslayer\statementexecution.cpp`
- `0x180028674`: `onecore\base\appmodel\staterepository\dataaccesslayer\database.cpp`
- `0x1800289b5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application.cpp`
- `0x18002805d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appexecutionalias-custom.cpp`
- `0x18002814e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appexecutionalias-custom.cpp`
- `0x18002800e`: `SELECT COUNT(*) FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE aea.Alias=?2 AND pu.User=?1 AND aea._WorkId=0 AND ae._WorkId=0 AND a._WorkId=0 AND p._WorkId=0 AND pu._WorkId=0;`
- `0x1800280ff`: `SELECT aea._AppExecutionAliasID, aea._Revision, aea._WorkId, aea.Alias, aea.Extension, aea.Flags, aea._Dictionary FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID LEFT JOIN ApplicationIdentity AS ai ON ai.ApplicationUserModelId=a.ApplicationUserModelId LEFT JOIN AppEx`
- `0x18002801c`: `SELECT COUNT(*) FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID WHERE aea.Alias=?2 AND pu.User=?1 AND (aea._WorkId=0 OR aea._WorkId=?3) AND (ae._WorkId=0 OR ae._WorkId=?3) AND (a._WorkId=0 OR a._WorkId=?3) AND (p._WorkId=0 OR p._WorkId=?3) AND (pu._WorkId=0 OR pu._Wo`
- `0x18002810d`: `SELECT aea._AppExecutionAliasID, aea._Revision, aea._WorkId, aea.Alias, aea.Extension, aea.Flags, aea._Dictionary FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Application INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Package=p._PackageID LEFT JOIN ApplicationIdentity AS ai ON ai.ApplicationUserModelId=a.ApplicationUserModelId LEFT JOIN AppEx`
- `0x180028f00`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appexecutionalias.cpp`
- `0x18002846e`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180028ee7`: `onecore\base\appmodel\staterepository\dataaccesslayer\statement.cpp`
- `0x180027f74`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-user.cpp`
- `0x1800287b5`: `SELECT _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _ApplicationExtensionID=? AND (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;`
- `0x1800287bc`: `SELECT _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _ApplicationExtensionID=? AND _WorkId=0;`
- `0x180028621`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appexecutionaliasuser.cpp`
- `0x1800286bd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appexecutionaliasuser.cpp`
- `0x18002852c`: `onecore\base\appmodel\StateRepository\DataAccessLayer\Statement.hpp`
- `0x18002892e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x180028c33`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x180028381`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationidentity.cpp`
- `0x1800283cc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationidentity.cpp`
- `0x180028410`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationidentity.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::Internal::AppExecutionAliasHelper::ShouldCreateAliasFileAndAppExecutionAliasUser(
        struct sqlite3_stmt **this,
        bool *a2,
        bool *a3)
{
  _QWORD *v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // r13
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v12; // rdi
  int v13; // eax
  int v14; // eax
  char v15; // bl
  int v16; // eax
  __int64 v17; // r8
  unsigned int v18; // edi
  __int64 v19; // rdx
  __int64 v20; // rax
  int Next; // eax
  int v22; // eax
  __int64 v23; // r8
  char v24; // r15
  int v25; // eax
  int v26; // eax
  int (*v27)(void *); // r9
  char v28; // r15
  int v29; // eax
  int v30; // r8d
  __int64 v31; // rdx
  int v32; // eax
  __int64 v33; // r8
  int v34; // eax
  int v35; // eax
  unsigned __int64 v36; // r9
  __int64 v37; // rdx
  int v38; // eax
  __int64 v39; // rdx
  const char *v40; // rdx
  int v41; // eax
  unsigned __int64 v42; // r9
  __int64 v43; // rdx
  __int64 v44; // r13
  int v45; // eax
  __int64 v46; // r8
  int v47; // eax
  int v48; // eax
  char v49; // r15
  int v50; // eax
  int v51; // eax
  unsigned __int64 v52; // r9
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rdx
  __int64 v56; // rdx
  int v57; // eax
  bool v58; // bl
  int v59; // eax
  unsigned int v60; // edi
  int v61; // eax
  int v62; // eax
  int v63; // eax
  __int64 v64; // rdx
  unsigned __int64 *v65; // [rsp+20h] [rbp-E0h]
  int v66; // [rsp+20h] [rbp-E0h]
  char **v67; // [rsp+20h] [rbp-E0h]
  int v68; // [rsp+20h] [rbp-E0h]
  int v69; // [rsp+20h] [rbp-E0h]
  int v70; // [rsp+20h] [rbp-E0h]
  char **v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+20h] [rbp-E0h]
  bool *v76; // [rsp+28h] [rbp-D8h]
  char *v77; // [rsp+30h] [rbp-D0h] BYREF
  struct sqlite3_stmt *v78; // [rsp+38h] [rbp-C8h] BYREF
  bool v79; // [rsp+40h] [rbp-C0h] BYREF
  struct sqlite3_stmt *v80; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v82; // [rsp+58h] [rbp-A8h] BYREF
  OSIntegration::DEH::Internal::AppExecutionAliasHelper *v83; // [rsp+60h] [rbp-A0h]
  struct sqlite3_stmt *v84; // [rsp+68h] [rbp-98h] BYREF
  __int64 v85; // [rsp+70h] [rbp-90h]
  _QWORD v86[2]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v87; // [rsp+88h] [rbp-78h] BYREF
  __int128 v88; // [rsp+98h] [rbp-68h] BYREF
  __int64 v89; // [rsp+A8h] [rbp-58h]
  int v90[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 (__fastcall **v91)(); // [rsp+B8h] [rbp-48h] BYREF
  __int128 v92; // [rsp+C0h] [rbp-40h]
  __int128 v93; // [rsp+D0h] [rbp-30h]
  int v94; // [rsp+E0h] [rbp-20h]
  __int64 v95; // [rsp+E8h] [rbp-18h]
  __int128 v96; // [rsp+F0h] [rbp-10h]
  _QWORD v97[2]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v98; // [rsp+150h] [rbp+50h]
  __int128 v99; // [rsp+160h] [rbp+60h] BYREF
  int v100; // [rsp+170h] [rbp+70h]
  __int64 v101; // [rsp+178h] [rbp+78h] BYREF
  __int128 v102; // [rsp+180h] [rbp+80h]
  _QWORD v103[2]; // [rsp+190h] [rbp+90h] BYREF
  __int128 v104; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v105; // [rsp+1B0h] [rbp+B0h]
  int v106; // [rsp+1C0h] [rbp+C0h]
  __int64 v107; // [rsp+1C8h] [rbp+C8h] BYREF
  __int128 v108; // [rsp+1D0h] [rbp+D0h]
  __int64 v109; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v110; // [rsp+1E8h] [rbp+E8h] BYREF
  _QWORD v111[2]; // [rsp+1F0h] [rbp+F0h] BYREF
  char v112; // [rsp+200h] [rbp+100h]
  _QWORD v113[3]; // [rsp+208h] [rbp+108h] BYREF
  __int64 v114[2]; // [rsp+220h] [rbp+120h] BYREF
  __int128 v115; // [rsp+230h] [rbp+130h]
  __int128 v116; // [rsp+240h] [rbp+140h]
  __int128 v117; // [rsp+250h] [rbp+150h]
  _BYTE v118[24]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v119; // [rsp+278h] [rbp+178h]
  _BYTE v120[64]; // [rsp+370h] [rbp+270h] BYREF
  unsigned __int16 *v121; // [rsp+3B0h] [rbp+2B0h]
  struct _GUID v122; // [rsp+530h] [rbp+430h] BYREF
  __int64 v123; // [rsp+540h] [rbp+440h]
  __int64 v124; // [rsp+550h] [rbp+450h] BYREF
  __int64 v125; // [rsp+558h] [rbp+458h]
  __int128 v126; // [rsp+560h] [rbp+460h]
  __int128 v127; // [rsp+570h] [rbp+470h]
  __int64 v128; // [rsp+580h] [rbp+480h]
  int v129; // [rsp+588h] [rbp+488h]
  __int64 v130; // [rsp+58Ch] [rbp+48Ch]
  int v131; // [rsp+594h] [rbp+494h]
  wil::details::in1diag3 *retaddr; // [rsp+5E8h] [rbp+4E8h]

  v83 = (OSIntegration::DEH::Internal::AppExecutionAliasHelper *)this;
  v6 = (_QWORD *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this[3] + 6) + 8LL))(*((_QWORD *)this[3] + 6));
  v111[1] = v6;
  v85 = v6[1];
  v7 = v85;
  v8 = 0;
  v6[1] = 0;
  v111[0] = v7;
  v112 = 0;
  v114[0] = 0;
  v114[1] = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  LOBYTE(v77) = 0;
  v9 = StateRepository::Entity::User::TryGetByUserSid(
         (struct StateRepository::Database *)v6,
         *((void **)this[3] + 98),
         (struct StateRepository::Entity::User *)v114,
         (bool *)&v77);
  if ( (v9 & 0x80000000) != 0 )
  {
    v10 = 191;
    goto LABEL_5;
  }
  if ( !(_BYTE)v77 )
  {
    v9 = -2147023728;
    v10 = 192;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-user.cpp",
      (const char *)v9,
      (int)v65);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1CF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)v9,
      v66);
    StateRepository::Entity::User::~User((StateRepository::Entity::User *)v114);
    if ( v7 )
      v6[1] = v7;
    return v9;
  }
  *a2 = 1;
  *a3 = 1;
  v82 = 0;
  v78 = this[18];
  v12 = v114[0];
  v81 = v114[0];
  v91 = &off_1802122A8;
  *(_QWORD *)&v92 = &v81;
  *((_QWORD *)&v92 + 1) = &v78;
  *(_QWORD *)v90 = &v91;
  *(_QWORD *)&v122.Data1 = "SELECT COUNT(*) FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._Ap"
                           "plicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Applica"
                           "tion INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Pac"
                           "kage=p._PackageID WHERE aea.Alias=?2 AND pu.User=?1 AND aea._WorkId=0 AND ae._WorkId=0 AND a."
                           "_WorkId=0 AND p._WorkId=0 AND pu._WorkId=0;";
  *(_QWORD *)v122.Data4 = "SELECT COUNT(*) FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae._App"
                          "licationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Applicati"
                          "on INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Packag"
                          "e=p._PackageID WHERE aea.Alias=?2 AND pu.User=?1 AND (aea._WorkId=0 OR aea._WorkId=?3) AND (ae"
                          "._WorkId=0 OR ae._WorkId=?3) AND (a._WorkId=0 OR a._WorkId=?3) AND (p._WorkId=0 OR p._WorkId=?"
                          "3) AND (pu._WorkId=0 OR pu._WorkId=?3);";
  v123 = 3;
  v13 = StateRepository::StatementExecution::PrepareAndBindAndCountBy(
          (StateRepository::StatementExecution *)v6,
          (struct StateRepository::Database *)&v122,
          (const struct StateRepository::StatementExecution::StatementDefinition *)v90,
          (struct StateRepository::StatementExecution::StatementBinderFunc *)&v82,
          v65);
  v9 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appexecutionalias-custom.cpp",
      (const char *)(unsigned int)v13,
      (int)v67);
    (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)v9,
      v68);
LABEL_155:
    StateRepository::Entity::User::~User((StateRepository::Entity::User *)v114);
    StateRepository::AutoRestoreWorkId::~AutoRestoreWorkId((StateRepository::AutoRestoreWorkId *)v111);
    return v9;
  }
  (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
  if ( !v82 )
  {
    *a2 = 1;
    v9 = 0;
    goto LABEL_155;
  }
  v80 = 0;
  v78 = this[18];
  v81 = v12;
  v91 = &off_180212298;
  *(_QWORD *)&v92 = &v81;
  *((_QWORD *)&v92 + 1) = &v78;
  *(_QWORD *)v90 = &v91;
  *(_QWORD *)&v122.Data1 = "SELECT aea._AppExecutionAliasID, aea._Revision, aea._WorkId, aea.Alias, aea.Extension, aea.Fl"
                           "ags, aea._Dictionary FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON a"
                           "e._ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Ap"
                           "plication INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON p"
                           "u.Package=p._PackageID LEFT JOIN ApplicationIdentity AS ai ON ai.ApplicationUserModelId=a.App"
                           "licationUserModelId LEFT JOIN AppExecutionAliasUser AS aeau ON aeau.ApplicationIdentity=ai._A"
                           "pplicationIdentityID AND aeau.Alias=aea.Alias WHERE aea.Alias=?2 AND pu.User=?1 AND IFNULL(ae"
                           "au.Status, 0)<>2 AND aea._WorkId=0 AND ae._WorkId=0 AND a._WorkId=0 AND p._WorkId=0 AND pu._W"
                           "orkId=0 ORDER BY IFNULL(aeau.Status, 0), pu.InstallTime;";
  *(_QWORD *)v122.Data4 = "SELECT aea._AppExecutionAliasID, aea._Revision, aea._WorkId, aea.Alias, aea.Extension, aea.Fla"
                          "gs, aea._Dictionary FROM AppExecutionAlias AS aea INNER JOIN ApplicationExtension AS ae ON ae."
                          "_ApplicationExtensionID=aea.Extension INNER JOIN Application AS a ON a._ApplicationID=ae.Appli"
                          "cation INNER JOIN Package AS p ON p._PackageID=a.Package INNER JOIN PackageUser AS pu ON pu.Pa"
                          "ckage=p._PackageID LEFT JOIN ApplicationIdentity AS ai ON ai.ApplicationUserModelId=a.Applicat"
                          "ionUserModelId LEFT JOIN AppExecutionAliasUser AS aeau ON aeau.ApplicationIdentity=ai._Applica"
                          "tionIdentityID AND aeau.Alias=aea.Alias WHERE aea.Alias=?2 AND pu.User=?1 AND IFNULL(aeau.Stat"
                          "us, 0)<>2 AND (aea._WorkId=0 OR aea._WorkId=?3) AND (ae._WorkId=0 OR ae._WorkId=?3) AND (a._Wo"
                          "rkId=0 OR a._WorkId=?3) AND (p._WorkId=0 OR p._WorkId=?3) AND (pu._WorkId=0 OR pu._WorkId=?3) "
                          "ORDER BY IFNULL(aeau.Status, 0), pu.InstallTime;";
  v123 = 3;
  v14 = StateRepository::StatementExecution::PrepareAndBindAndFindBy(
          (StateRepository::StatementExecution *)v6,
          (struct StateRepository::Database *)&v122,
          (const struct StateRepository::StatementExecution::StatementDefinition *)v90,
          (struct StateRepository::StatementExecution::StatementBinderFunc *)&v80,
          (struct StateRepository::Statement *)v67);
  v9 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appexecutionalias-custom.cpp",
      (const char *)(unsigned int)v14,
      v69);
    (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
      (const char *)v9,
      v70);
LABEL_154:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v80);
    goto LABEL_155;
  }
  (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
  v103[0] = 0;
  v103[1] = 0;
  v104 = 0;
  v105 = 0;
  v106 = 0;
  v107 = 0;
  v108 = 0;
  v15 = 0;
  LOBYTE(v77) = 0;
  if ( !v80 )
  {
    v18 = -2147019873;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
      (const char *)0x8007139FLL,
      v69);
    goto LABEL_159;
  }
  v16 = StateRepository::Statement::dal_step(v80);
  v18 = v16;
  if ( v16 != -2018574236 )
  {
    if ( v16 == -2018574235 )
    {
      v15 = 0;
      goto LABEL_19;
    }
    if ( v16 >= 0 )
    {
LABEL_23:
      v81 = 0;
      v20 = 0;
      if ( v15 )
        v20 = *((_QWORD *)&v105 + 1);
      *(_QWORD *)&v122.Data1 = v20;
      while ( v15 )
      {
        if ( (v106 & 1) == 0 )
          *a3 = 0;
        v81 = ++v8;
        Next = StateRepository::Entity::AppExecutionAlias::FindNext(
                 (struct StateRepository::Statement *)&v80,
                 (struct StateRepository::Entity::AppExecutionAlias *)v103,
                 (bool *)&v77);
        v9 = Next;
        if ( Next < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1F8,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
            (const char *)(unsigned int)Next,
            v69);
LABEL_153:
          StateRepository::Entity::AppExecutionAlias::~AppExecutionAlias((StateRepository::Entity::AppExecutionAlias *)v103);
          goto LABEL_154;
        }
        v15 = (char)v77;
      }
      if ( !v8 )
        *a2 = 0;
      v86[0] = 0;
      v86[1] = 0;
      v87 = 0;
      v88 = 0;
      v89 = 0;
      v97[0] = 0;
      v97[1] = 0;
      v98 = 0;
      v99 = 0;
      v100 = 0;
      v101 = 0;
      v102 = 0;
      LOBYTE(v77) = 0;
      v84 = this[28];
      v78 = 0;
      v91 = &off_1802122B8;
      *(_QWORD *)&v92 = &v84;
      *(_QWORD *)v90 = &v91;
      v113[0] = "SELECT _ApplicationIdentityID, _Revision, ApplicationUserModelId, _Dictionary FROM ApplicationIdentity W"
                "HERE ApplicationUserModelId=?;";
      v113[1] = 0;
      v113[2] = 0;
      v22 = StateRepository::StatementExecution::PrepareAndBindAndTryGetBy(
              (StateRepository::StatementExecution *)v6,
              (struct StateRepository::Database *)v113,
              (const struct StateRepository::StatementExecution::StatementDefinition *)v90,
              (struct StateRepository::StatementExecution::StatementBinderFunc *)&v78,
              (struct StateRepository::Statement *)&v77,
              v76);
      v9 = v22;
      v24 = (char)v77;
      if ( v22 >= 0 )
      {
        if ( (_BYTE)v77
          && (v25 = StateRepository::Entity::ApplicationIdentity::RowToObject(
                      (const struct StateRepository::Statement *)&v78,
                      (struct StateRepository::Entity::ApplicationIdentity *)v86,
                      v23),
              v9 = v25,
              v25 < 0) )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA7,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationidentity.cpp",
            (const char *)(unsigned int)v25,
            (int)v71);
          (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
        }
        else
        {
          if ( v78 )
            v26 = StateRepository::StatementCache::Add(
                    (StateRepository::StatementCache *)(v6 + 5),
                    (struct StateRepository::Statement *)&v78);
          else
            v26 = 0;
          if ( v26 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0xAA,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationidentity.cpp",
              (const char *)(unsigned int)v26,
              (int)v71);
          (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
          v9 = 0;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationidentity.cpp",
          (const char *)(unsigned int)v22,
          (int)v71);
        (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
      }
      StateRepository::Statement::~Statement((StateRepository::Statement *)&v78);
      if ( (v9 & 0x80000000) != 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x206,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
          (const char *)v9,
          (int)v71);
LABEL_152:
        StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v97);
        StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)v86);
        goto LABEL_153;
      }
      if ( !v24 )
        goto LABEL_82;
      v28 = 0;
      LOBYTE(v77) = 0;
      v110 = *((_QWORD *)v83 + 18);
      v109 = v114[0];
      v84 = (struct sqlite3_stmt *)v86[0];
      v78 = 0;
      v91 = off_180212300;
      *(_QWORD *)&v92 = &v84;
      *((_QWORD *)&v92 + 1) = &v109;
      *(_QWORD *)&v93 = &v110;
      *(_QWORD *)v90 = &v91;
      if ( *v6 )
      {
        if ( StateRepository::StatementCache::Get(
               (StateRepository::StatementCache *)(v6 + 5),
               "SELECT _AppExecutionAliasUserID, _Revision, User, ApplicationIdentity, Alias, Status, _Dictionary FROM Ap"
               "pExecutionAliasUser WHERE ApplicationIdentity=? AND User=? AND Alias=?;",
               (struct StateRepository::Statement *)&v78) )
        {
          goto LABEL_53;
        }
        v29 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v78);
        if ( v29 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x127,
            (unsigned int)"onecore\\base\\appmodel\\StateRepository\\DataAccessLayer\\Statement.hpp",
            (const char *)(unsigned int)v29,
            (int)v71);
        v9 = StateRepository::Database::dal_prepare_v2(
               (struct sqlite3 *)*v6,
               "SELECT _AppExecutionAliasUserID, _Revision, User, ApplicationIdentity, Alias, Status, _Dictionary FROM Ap"
               "pExecutionAliasUser WHERE ApplicationIdentity=? AND User=? AND Alias=?;",
               v30,
               &v78,
               (const char **)v71);
        if ( (v9 & 0x80000000) == 0 )
        {
LABEL_53:
          v9 = (*(__int64 (__fastcall **)(_QWORD, struct sqlite3_stmt **))(**(_QWORD **)v90 + 8LL))(
                 *(_QWORD *)v90,
                 &v78);
          if ( (v9 & 0x80000000) != 0 )
          {
            v31 = 23;
LABEL_74:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v31,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
              (const char *)v9,
              (int)v71);
            v39 = 199;
            goto LABEL_75;
          }
          if ( v78 )
          {
            v32 = StateRepository::Statement::dal_step(v78);
            v9 = v32;
            if ( v32 == -2018574236 )
            {
              v28 = 1;
              goto LABEL_59;
            }
            if ( v32 == -2018574235 )
            {
LABEL_59:
              LOBYTE(v77) = v28;
              if ( v28 )
              {
                v35 = StateRepository::Entity::AppExecutionAliasUser::RowToObject(
                        (const struct StateRepository::Statement *)&v78,
                        (struct StateRepository::Entity::AppExecutionAliasUser *)v97,
                        v33);
                v9 = v35;
                if ( v35 < 0 )
                {
                  v36 = (unsigned int)v35;
                  v37 = 374;
LABEL_76:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v37,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appexecutionaliasuser.cpp",
                    (const char *)v36,
                    (int)v71);
                  (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
                  goto LABEL_77;
                }
LABEL_67:
                v38 = StateRepository::Database::AddToCache(
                        (StateRepository::Database *)v6,
                        (struct StateRepository::Statement *)&v78);
                if ( v38 < 0 )
                  wil::details::in1diag3::_Log_Hr(
                    retaddr,
                    (void *)0x179,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appexecutionaliasuser.cpp",
                    (const char *)(unsigned int)v38,
                    (int)v71);
                (***(void (__fastcall ****)(_QWORD, _QWORD))v90)(*(_QWORD *)v90, 0);
                v9 = 0;
LABEL_77:
                StateRepository::Statement::~Statement((StateRepository::Statement *)&v78);
                if ( (v9 & 0x80000000) != 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x20A,
                    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
                    (const char *)v9,
                    (int)v71);
                  goto LABEL_79;
                }
                v8 = v81;
                if ( v28 )
                  goto LABEL_157;
LABEL_82:
                if ( v8 != v82 )
                  goto LABEL_142;
                if ( !v8 )
                  goto LABEL_157;
                StateRepository::Entity::ApplicationExtension::ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v118);
                v78 = 0;
                v40 = "SELECT _Revision, _WorkId, Application, \"Index\", Category, Activation, HostId, Executable, Entry"
                      "point, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, "
                      "Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _ApplicationExtensionID=? AN"
                      "D (_WorkId=0 OR _WorkId=?) ORDER BY _WorkId DESC;";
                if ( !v6[1] )
                  v40 = "SELECT _Revision, _WorkId, Application, \"Index\", Category, Activation, HostId, Executable, Ent"
                        "rypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPa"
                        "th, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE _ApplicationExtensionI"
                        "D=? AND _WorkId=0;";
                v41 = StateRepository::Database::PrepareFromCache(
                        (StateRepository::Database *)v6,
                        v40,
                        (struct StateRepository::Statement *)&v78);
                v9 = v41;
                if ( v41 < 0 )
                {
                  v42 = (unsigned int)v41;
                  v43 = 164;
LABEL_137:
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)v43,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
                    (const char *)v42,
                    (int)v71);
                  v52 = v9;
                  v53 = 769;
                  goto LABEL_138;
                }
                if ( v78 )
                {
                  v44 = *(_QWORD *)&v122.Data1;
                  v45 = sqlite3_bind_int64(v78, 1, *(_QWORD *)&v122.Data1);
                  v9 = v45;
                  if ( v45 > 0 )
                    v9 = (unsigned __int16)v45 | 0x87AF0000;
                  if ( (v9 & 0x80000000) == 0 )
                  {
                    v46 = v6[1];
                    if ( v46 )
                    {
                      if ( v78 )
                      {
                        v47 = sqlite3_bind_int64(v78, 2, v46);
                        v9 = v47;
                        if ( v47 > 0 )
                          v9 = (unsigned __int16)v47 | 0x87AF0000;
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0xC9,
                          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
                          (const char *)0x8007139FLL,
                          (int)v71);
                        v9 = -2147019873;
                      }
                      if ( (v9 & 0x80000000) != 0 )
                      {
                        v43 = 168;
LABEL_136:
                        v42 = v9;
                        goto LABEL_137;
                      }
                    }
                    if ( v78 )
                    {
                      v48 = StateRepository::Statement::dal_step(v78);
                      v9 = v48;
                      if ( v48 == -2018574236 )
                      {
                        v49 = 1;
                        goto LABEL_103;
                      }
                      v49 = 0;
                      if ( v48 == -2018574235 )
                      {
LABEL_103:
                        if ( v49 )
                          goto LABEL_108;
                        goto LABEL_106;
                      }
                      if ( v48 >= 0 )
                      {
LABEL_106:
                        v50 = StateRepository::Database::AddToCache(
                                (StateRepository::Database *)v6,
                                (struct StateRepository::Statement *)&v78);
                        if ( v50 < 0 )
                          wil::details::in1diag3::_Log_Hr(
                            retaddr,
                            (void *)0xAF,
                            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
                            (const char *)(unsigned int)v50,
                            (int)v71);
LABEL_108:
                        if ( v49 )
                        {
                          v51 = StateRepository::Entity::ApplicationExtension::RowToObject(
                                  (const struct StateRepository::Statement *)&v78,
                                  (struct StateRepository::Entity::ApplicationExtension *)v118,
                                  v44);
                          v9 = v51;
                          if ( v51 < 0 )
                          {
                            v52 = (unsigned int)v51;
                            v53 = 773;
LABEL_138:
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)v53,
                              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
                              (const char *)v52,
                              (int)v71);
                            v61 = StateRepository::Statement::Finalize((StateRepository::Statement *)&v78);
                            if ( v61 < 0 )
                              wil::details::in1diag3::_Log_Hr(
                                retaddr,
                                (void *)0x16,
                                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
                                (const char *)(unsigned int)v61,
                                (int)v71);
                            v55 = 759;
                            goto LABEL_141;
                          }
                        }
                        if ( v78 )
                          v54 = StateRepository::StatementCache::Add(
                                  (StateRepository::StatementCache *)(v6 + 5),
                                  (struct StateRepository::Statement *)&v78);
                        else
                          v54 = 0;
                        if ( v54 < 0 )
                          wil::details::in1diag3::_Log_Hr(
                            retaddr,
                            (void *)0x308,
                            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
                            (const char *)(unsigned int)v54,
                            (int)v71);
                        StateRepository::Statement::~Statement((StateRepository::Statement *)&v78);
                        if ( !v49 )
                        {
                          v9 = -2147023728;
                          v55 = 760;
LABEL_141:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v55,
                            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
                            (const char *)v9,
                            (int)v71);
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x218,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutio"
                                          "naliashelper.cpp",
                            (const char *)v9,
                            v73);
                          goto LABEL_125;
                        }
                        StateRepository::Entity::Application::Application((StateRepository::Entity::Application *)v120);
                        v79 = 0;
                        v9 = StateRepository::Entity::Application::TryGet(
                               (struct StateRepository::Database *)v6,
                               v119,
                               (struct Application *)v120,
                               &v79);
                        if ( (v9 & 0x80000000) != 0 )
                        {
                          v56 = 958;
LABEL_122:
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v56,
                            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application.cpp",
                            (const char *)v9,
                            (int)v71);
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x21B,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutio"
                                          "naliashelper.cpp",
                            (const char *)v9,
                            v72);
                          StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v120);
                          StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v118);
LABEL_79:
                          StateRepository::Blob::Reset((StateRepository::Blob *)&v101);
                          StateRepository::TextA::Reset((StateRepository::TextA *)&v99);
                          StateRepository::Blob::Reset((StateRepository::Blob *)&v88);
                          StateRepository::TextA::Reset((StateRepository::TextA *)&v87);
                          StateRepository::Blob::Reset((StateRepository::Blob *)&v107);
                          StateRepository::TextA::Reset((StateRepository::TextA *)((char *)&v104 + 8));
                          StateRepository::Statement::~Statement((StateRepository::Statement *)&v80);
                          StateRepository::Entity::User::~User((StateRepository::Entity::User *)v114);
                          if ( v85 )
                            v6[1] = v85;
                          return v9;
                        }
                        if ( !v79 )
                        {
                          v9 = -2147023728;
                          v56 = 959;
                          goto LABEL_122;
                        }
                        v124 = 0;
                        v125 = 0;
                        v126 = 0;
                        v127 = 0;
                        v128 = 0;
                        *(_QWORD *)v90 = 0;
                        v91 = 0;
                        v92 = 0;
                        v93 = 0;
                        v94 = 0;
                        v95 = 0;
                        v96 = 0;
                        v57 = StateRepository::Entity::ApplicationIdentity::TryGetByApplicationUserModelId(
                                (struct StateRepository::Database *)v6,
                                v121,
                                (struct StateRepository::Entity::ApplicationIdentity *)&v124,
                                (bool *)&v77);
                        v9 = v57;
                        if ( v57 < 0 )
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x21F,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutio"
                                          "naliashelper.cpp",
                            (const char *)(unsigned int)v57,
                            (int)v71);
                          StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v90);
                          StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)&v124);
                          StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v120);
LABEL_125:
                          StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v118);
                          goto LABEL_152;
                        }
                        v58 = 0;
                        if ( (_BYTE)v77 )
                        {
                          LOBYTE(v77) = 0;
                          v59 = StateRepository::Entity::AppExecutionAliasUser::TryGetByApplicationIdentityAndUserAndAlias(
                                  (struct StateRepository::Database *)v6,
                                  v124,
                                  v114[0],
                                  *((const unsigned __int16 **)v83 + 18),
                                  (struct StateRepository::Entity::AppExecutionAliasUser *)v90,
                                  (bool *)&v77);
                          v60 = v59;
                          if ( v59 < 0 )
                          {
                            wil::details::in1diag3::Return_Hr(
                              retaddr,
                              (void *)0x223,
                              (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecut"
                                            "ionaliashelper.cpp",
                              (const char *)(unsigned int)v59,
                              (int)v71);
                            StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v90);
                            StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)&v124);
                            StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v120);
                            StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v118);
                            StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v97);
                            StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)v86);
                            StateRepository::Entity::AppExecutionAlias::~AppExecutionAlias((StateRepository::Entity::AppExecutionAlias *)v103);
                            StateRepository::Statement::~Statement((StateRepository::Statement *)&v80);
                            v9 = v60;
                            goto LABEL_155;
                          }
                          v58 = (_BYTE)v77 != 0;
                        }
                        StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v90);
                        StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)&v124);
                        StateRepository::Entity::Application::~Application((StateRepository::Entity::Application *)v120);
                        StateRepository::Entity::ApplicationExtension::~ApplicationExtension((StateRepository::Entity::ApplicationExtension *)v118);
                        if ( !v58 )
                        {
LABEL_157:
                          StateRepository::Entity::AppExecutionAliasUser::~AppExecutionAliasUser((StateRepository::Entity::AppExecutionAliasUser *)v97);
                          StateRepository::Entity::ApplicationIdentity::~ApplicationIdentity((StateRepository::Entity::ApplicationIdentity *)v86);
                          StateRepository::Entity::AppExecutionAlias::~AppExecutionAlias((StateRepository::Entity::AppExecutionAlias *)v103);
                          StateRepository::Statement::~Statement((StateRepository::Statement *)&v80);
                          StateRepository::Entity::User::~User((StateRepository::Entity::User *)v114);
                          StateRepository::AutoRestoreWorkId::~AutoRestoreWorkId((StateRepository::AutoRestoreWorkId *)v111);
                          return 0;
                        }
LABEL_142:
                        v122.Data1 = 934457922;
                        *(_DWORD *)&v122.Data2 = 1160262579;
                        *(_DWORD *)v122.Data4 = -770685007;
                        *(_DWORD *)&v122.Data4[4] = 27409396;
                        v125 = 0;
                        v124 = 0;
                        v126 = 0u;
                        v127 = 0u;
                        v129 = 0;
                        v128 = 0;
                        v130 = 0;
                        v131 = 0;
                        v62 = StateRepository::Database::BeginTransaction(
                                (StateRepository::Database *)v6,
                                &v122,
                                (struct StateRepository::ResourcePriority::AutoPriority *)&v124,
                                v27,
                                v71);
                        v9 = v62;
                        if ( v62 >= 0 )
                        {
                          v78 = (struct sqlite3_stmt *)v6;
                          *((_QWORD *)&v98 + 1) = v86[0];
                          *(_QWORD *)&v98 = v114[0];
                          v100 = 2;
                          v63 = StateRepository::Entity::AppExecutionAliasUser::SetAlias(
                                  (StateRepository::Entity::AppExecutionAliasUser *)v97,
                                  *((const unsigned __int16 **)v83 + 18));
                          v9 = v63;
                          if ( v63 >= 0 )
                          {
                            v63 = StateRepository::Entity::AppExecutionAliasUser::Add(v97, v6);
                            v9 = v63;
                            if ( v63 >= 0 )
                            {
                              v63 = StateRepository::AutoTransaction::Commit((StateRepository::AutoTransaction *)&v78);
                              v9 = v63;
                              if ( v63 >= 0 )
                              {
                                StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v78);
                                StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)&v124);
                                goto LABEL_157;
                              }
                              v64 = 571;
                            }
                            else
                            {
                              v64 = 569;
                            }
                          }
                          else
                          {
                            v64 = 568;
                          }
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)v64,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutio"
                                          "naliashelper.cpp",
                            (const char *)(unsigned int)v63,
                            v74);
                          StateRepository::AutoTransaction::~AutoTransaction((StateRepository::AutoTransaction *)&v78);
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x232,
                            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutio"
                                          "naliashelper.cpp",
                            (const char *)(unsigned int)v62,
                            v74);
                        }
                        StateRepository::ResourcePriority::AutoPriority::~AutoPriority((StateRepository::ResourcePriority::AutoPriority *)&v124);
                        goto LABEL_152;
                      }
                    }
                    else
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x3F,
                        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
                        (const char *)0x8007139FLL,
                        (int)v71);
                      v9 = -2147019873;
                    }
                    v43 = 171;
                    goto LABEL_136;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0xC9,
                    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
                    (const char *)0x8007139FLL,
                    (int)v71);
                  v9 = -2147019873;
                }
                v43 = 165;
                goto LABEL_136;
              }
LABEL_62:
              v34 = StateRepository::Database::AddToCache(
                      (StateRepository::Database *)v6,
                      (struct StateRepository::Statement *)&v78);
              if ( v34 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xCD,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
                  (const char *)(unsigned int)v34,
                  (int)v71);
              goto LABEL_67;
            }
            if ( v32 >= 0 )
              goto LABEL_62;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x3F,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statement.cpp",
              (const char *)0x8007139FLL,
              (int)v71);
            v9 = -2147019873;
          }
          v39 = 201;
LABEL_75:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v39,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\statementexecution.cpp",
            (const char *)v9,
            (int)v71);
          v36 = v9;
          v37 = 371;
          goto LABEL_76;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66E,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\database.cpp",
          (const char *)0x8007139FLL,
          (int)v71);
        v9 = -2147019873;
      }
      v31 = 21;
      goto LABEL_74;
    }
LABEL_159:
    v19 = 411;
    goto LABEL_160;
  }
  v15 = 1;
LABEL_19:
  LOBYTE(v77) = v15;
  if ( !v15 )
    goto LABEL_23;
  v18 = StateRepository::Entity::AppExecutionAlias::RowToObject(
          (const struct StateRepository::Statement *)&v80,
          (struct StateRepository::Entity::AppExecutionAlias *)v103,
          v17);
  if ( (v18 & 0x80000000) == 0 )
    goto LABEL_23;
  v19 = 414;
LABEL_160:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v19,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appexecutionalias.cpp",
    (const char *)v18,
    v69);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1E7,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\appexecutionalias\\appexecutionaliashelper.cpp",
    (const char *)v18,
    v75);
  StateRepository::Entity::AppExecutionAlias::~AppExecutionAlias((StateRepository::Entity::AppExecutionAlias *)v103);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v80);
  StateRepository::Entity::User::~User((StateRepository::Entity::User *)v114);
  StateRepository::AutoRestoreWorkId::~AutoRestoreWorkId((StateRepository::AutoRestoreWorkId *)v111);
  return v18;
}

```

## disassembly

```asm
0x180027e88  mov     [rsp-8+arg_18], rbx
0x180027e8d  push    rbp
0x180027e8e  push    rsi
0x180027e8f  push    rdi
0x180027e90  push    r12
0x180027e92  push    r13
0x180027e94  push    r14
0x180027e96  push    r15
0x180027e98  lea     rbp, [rsp-4B0h]
0x180027ea0  sub     rsp, 5B0h
0x180027ea7  mov     rax, cs:__security_cookie
0x180027eae  xor     rax, rsp
0x180027eb1  mov     [rbp+4E0h+var_40], rax
0x180027eb8  mov     r15, r8
0x180027ebb  mov     r14, rdx
0x180027ebe  mov     r12, rcx
0x180027ec1  mov     [rsp+5E0h+var_580], rcx
0x180027ec6  mov     rax, [rcx+18h]
0x180027eca  mov     rcx, [rax+30h]
0x180027ece  mov     rax, [rcx]
0x180027ed1  mov     rax, [rax+8]
0x180027ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027eda  mov     rsi, rax
0x180027edd  mov     [rbp+4E0h+var_3E8], rax
0x180027ee4  mov     rdi, [rax+8]
0x180027ee8  mov     [rsp+5E0h+var_570], rdi
0x180027eed  xor     r13d, r13d
0x180027ef0  mov     [rax+8], r13
0x180027ef4  mov     [rbp+4E0h+var_3F0], rdi
0x180027efb  mov     [rbp+4E0h+var_3E0], r13b
0x180027f02  mov     [rbp+4E0h+var_3C0], r13
0x180027f09  mov     [rbp+4E0h+var_3B8], r13
0x180027f10  xorps   xmm0, xmm0
0x180027f13  movdqa  [rbp+4E0h+var_3B0], xmm0
0x180027f1b  xorps   xmm1, xmm1
0x180027f1e  movdqa  [rbp+4E0h+var_3A0], xmm1
0x180027f26  movdqa  [rbp+4E0h+var_390], xmm0
0x180027f2e  mov     byte ptr [rsp+5E0h+var_5B0], r13b
0x180027f33  mov     rdx, [r12+18h]
0x180027f38  lea     r9, [rsp+5E0h+var_5B0]; bool *
0x180027f3d  lea     r8, [rbp+4E0h+var_3C0]; struct StateRepository::Entity::User *
0x180027f44  mov     rdx, [rdx+310h]; void *
0x180027f4b  mov     rcx, rax; struct StateRepository::Database *
0x180027f4e  call    ?TryGetByUserSid@User@Entity@StateRepository@@SAJAEAVDatabase@3@PEAXAEAV123@AEA_N@Z; StateRepository::Entity::User::TryGetByUserSid(StateRepository::Database &,void *,StateRepository::Entity::User &,bool &)
0x180027f53  mov     ebx, eax
0x180027f55  test    eax, eax
0x180027f57  jns     short loc_180027F60
0x180027f59  mov     edx, 0BFh
0x180027f5e  jmp     short loc_180027F71
0x180027f60  cmp     byte ptr [rsp+5E0h+var_5B0], r13b
0x180027f65  jnz     short loc_180027FC0
0x180027f67  mov     ebx, 80070490h
0x180027f6c  mov     edx, 0C0h; void *
0x180027f71  mov     r9d, ebx; char *
0x180027f74  lea     r8, aOnecoreBaseApp_55; "onecore\\base\\appmodel\\staterepositor"...
0x180027f7b  mov     rcx, [rbp+4E8h]; this
0x180027f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027f87  mov     rcx, [rbp+4E8h]; this
0x180027f8e  mov     r9d, ebx; char *
0x180027f91  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180027f98  mov     edx, 1CFh; void *
0x180027f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027fa2  nop
0x180027fa3  lea     rcx, [rbp+4E0h+var_3C0]; this
0x180027faa  call    ??1User@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::User::~User(void)
0x180027faf  nop
0x180027fb0  test    rdi, rdi
0x180027fb3  jz      short loc_180027FB9
0x180027fb5  mov     [rsi+8], rdi
0x180027fb9  mov     eax, ebx
0x180027fbb  jmp     loc_180028F62
0x180027fc0  mov     eax, 1
0x180027fc5  mov     [r14], al
0x180027fc8  mov     [r15], al
0x180027fcb  mov     [rsp+5E0h+var_588], r13
0x180027fd0  mov     rax, [r12+90h]
0x180027fd8  mov     [rsp+5E0h+var_5A8], rax
0x180027fdd  mov     rdi, [rbp+4E0h+var_3C0]
0x180027fe4  mov     [rsp+5E0h+var_590], rdi
0x180027fe9  lea     rax, off_1802122A8
0x180027ff0  mov     [rbp+4E0h+var_528], rax
0x180027ff4  lea     rax, [rsp+5E0h+var_590]
0x180027ff9  mov     qword ptr [rbp+4E0h+var_520], rax
0x180027ffd  lea     rax, [rsp+5E0h+var_5A8]
0x180028002  mov     qword ptr [rbp+4E0h+var_520+8], rax
0x180028006  lea     rax, [rbp+4E0h+var_528]
0x18002800a  mov     qword ptr [rbp+4E0h+var_530], rax
0x18002800e  lea     rax, aSelectCountFro_12; "SELECT COUNT(*) FROM AppExecutionAlias "...
0x180028015  mov     qword ptr [rbp+4E0h+var_B0.Data1], rax
0x18002801c  lea     rax, aSelectCountFro_7; "SELECT COUNT(*) FROM AppExecutionAlias "...
0x180028023  mov     qword ptr [rbp+4E0h+var_B0.Data4], rax
0x18002802a  mov     [rbp+4E0h+var_A0], 3
0x180028035  lea     r9, [rsp+5E0h+var_588]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x18002803a  lea     r8, [rbp+4E0h+var_530]; struct StateRepository::StatementExecution::StatementDefinition *
0x18002803e  lea     rdx, [rbp+4E0h+var_B0]; struct StateRepository::Database *
0x180028045  mov     rcx, rsi; this
0x180028048  call    ?PrepareAndBindAndCountBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEA_K@Z; StateRepository::StatementExecution::PrepareAndBindAndCountBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,unsigned __int64 &)
0x18002804d  mov     ebx, eax
0x18002804f  test    eax, eax
0x180028051  jns     short loc_18002809F
0x180028053  mov     rcx, [rbp+4E8h]; this
0x18002805a  mov     r9d, eax; char *
0x18002805d  lea     r8, aOnecoreBaseApp_87; "onecore\\base\\appmodel\\staterepositor"...
0x180028064  mov     edx, 11Ah; void *
0x180028069  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002806e  mov     rcx, qword ptr [rbp+4E0h+var_530]
0x180028072  mov     rdx, [rcx]
0x180028075  mov     rax, [rdx]
0x180028078  xor     edx, edx
0x18002807a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002807f  mov     rcx, [rbp+4E8h]; this
0x180028086  mov     r9d, ebx; char *
0x180028089  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180028090  mov     edx, 1D7h; void *
0x180028095  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002809a  jmp     loc_180028E55
0x18002809f  mov     rcx, qword ptr [rbp+4E0h+var_530]
0x1800280a3  mov     rax, [rcx]
0x1800280a6  xor     edx, edx
0x1800280a8  mov     rax, [rax]
0x1800280ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280b0  cmp     [rsp+5E0h+var_588], r13
0x1800280b5  jnz     short loc_1800280C3
0x1800280b7  mov     byte ptr [r14], 1
0x1800280bb  mov     ebx, r13d
0x1800280be  jmp     loc_180028E55
0x1800280c3  mov     [rsp+5E0h+var_598], r13
0x1800280c8  mov     rax, [r12+90h]
0x1800280d0  mov     [rsp+5E0h+var_5A8], rax
0x1800280d5  mov     [rsp+5E0h+var_590], rdi
0x1800280da  lea     rax, off_180212298
0x1800280e1  mov     [rbp+4E0h+var_528], rax
0x1800280e5  lea     rax, [rsp+5E0h+var_590]
0x1800280ea  mov     qword ptr [rbp+4E0h+var_520], rax
0x1800280ee  lea     rax, [rsp+5E0h+var_5A8]
0x1800280f3  mov     qword ptr [rbp+4E0h+var_520+8], rax
0x1800280f7  lea     rax, [rbp+4E0h+var_528]
0x1800280fb  mov     qword ptr [rbp+4E0h+var_530], rax
0x1800280ff  lea     rax, aSelectAeaAppex_0; "SELECT aea._AppExecutionAliasID, aea._R"...
0x180028106  mov     qword ptr [rbp+4E0h+var_B0.Data1], rax
0x18002810d  lea     rax, aSelectAeaAppex; "SELECT aea._AppExecutionAliasID, aea._R"...
0x180028114  mov     qword ptr [rbp+4E0h+var_B0.Data4], rax
0x18002811b  mov     [rbp+4E0h+var_A0], 3
0x180028126  lea     r9, [rsp+5E0h+var_598]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x18002812b  lea     r8, [rbp+4E0h+var_530]; struct StateRepository::StatementExecution::StatementDefinition *
0x18002812f  lea     rdx, [rbp+4E0h+var_B0]; struct StateRepository::Database *
0x180028136  mov     rcx, rsi; this
0x180028139  call    ?PrepareAndBindAndFindBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFindBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x18002813e  mov     ebx, eax
0x180028140  test    eax, eax
0x180028142  jns     short loc_180028190
0x180028144  mov     rcx, [rbp+4E8h]; this
0x18002814b  mov     r9d, eax; char *
0x18002814e  lea     r8, aOnecoreBaseApp_87; "onecore\\base\\appmodel\\staterepositor"...
0x180028155  mov     edx, 0CBh; void *
0x18002815a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002815f  mov     rcx, qword ptr [rbp+4E0h+var_530]
0x180028163  mov     rdx, [rcx]
0x180028166  mov     rax, [rdx]
0x180028169  xor     edx, edx
0x18002816b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028170  mov     rcx, [rbp+4E8h]; this
0x180028177  mov     r9d, ebx; char *
0x18002817a  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180028181  mov     edx, 1E3h; void *
0x180028186  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002818b  jmp     loc_180028E4A
0x180028190  mov     rcx, qword ptr [rbp+4E0h+var_530]
0x180028194  mov     rax, [rcx]
0x180028197  xor     edx, edx
0x180028199  mov     rax, [rax]
0x18002819c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281a1  mov     [rbp+4E0h+var_450], r13
0x1800281a8  mov     [rbp+4E0h+var_448], r13
0x1800281af  xorps   xmm0, xmm0
0x1800281b2  movdqa  [rbp+4E0h+var_440], xmm0
0x1800281ba  xorps   xmm1, xmm1
0x1800281bd  movdqa  [rbp+4E0h+var_430], xmm1
0x1800281c5  mov     [rbp+4E0h+var_420], r13d
0x1800281cc  mov     [rbp+4E0h+var_418], r13
0x1800281d3  movdqa  [rbp+4E0h+var_410], xmm0
0x1800281db  mov     bl, r13b
0x1800281de  mov     byte ptr [rsp+5E0h+var_5B0], bl
0x1800281e2  mov     rcx, [rsp+5E0h+var_598]; struct sqlite3_stmt *
0x1800281e7  test    rcx, rcx
0x1800281ea  jz      loc_180028ED8
0x1800281f0  call    ?dal_step@Statement@StateRepository@@SAJPEAUsqlite3_stmt@@@Z; StateRepository::Statement::dal_step(sqlite3_stmt *)
0x1800281f5  mov     edi, eax
0x1800281f7  cmp     eax, 87AF0064h
0x1800281fc  jnz     short loc_180028202
0x1800281fe  mov     bl, 1
0x180028200  jmp     short loc_18002820C
0x180028202  cmp     eax, 87AF0065h
0x180028207  jnz     short loc_180028235
0x180028209  mov     bl, r13b
0x18002820c  mov     byte ptr [rsp+5E0h+var_5B0], bl
0x180028210  test    bl, bl
0x180028212  jz      short loc_18002823D
0x180028214  lea     rdx, [rbp+4E0h+var_450]; struct StateRepository::Entity::AppExecutionAlias *
0x18002821b  lea     rcx, [rsp+5E0h+var_598]; this
0x180028220  call    ?RowToObject@AppExecutionAlias@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::AppExecutionAlias::RowToObject(StateRepository::Statement const &,StateRepository::Entity::AppExecutionAlias &,__int64)
0x180028225  mov     edi, eax
0x180028227  test    eax, eax
0x180028229  jns     short loc_18002823D
0x18002822b  mov     edx, 19Eh
0x180028230  jmp     loc_180028EFD
0x180028235  test    eax, eax
0x180028237  js      loc_180028EF8
0x18002823d  mov     [rsp+5E0h+var_590], r13
0x180028242  xor     edi, edi
0x180028244  mov     eax, edi
0x180028246  test    bl, bl
0x180028248  cmovnz  rax, qword ptr [rbp+4E0h+var_430+8]
0x180028250  mov     qword ptr [rbp+4E0h+var_B0.Data1], rax
0x180028257  test    bl, bl
0x180028259  jz      short loc_1800282B5
0x18002825b  mov     eax, 1
0x180028260  test    byte ptr [rbp+4E0h+var_420], al
0x180028266  jnz     short loc_18002826B
0x180028268  mov     [r15], dil
0x18002826b  add     r13, rax
0x18002826e  mov     [rsp+5E0h+var_590], r13
0x180028273  lea     r8, [rsp+5E0h+var_5B0]; bool *
0x180028278  lea     rdx, [rbp+4E0h+var_450]; struct StateRepository::Entity::AppExecutionAlias *
0x18002827f  lea     rcx, [rsp+5E0h+var_598]; struct StateRepository::Statement *
0x180028284  call    ?FindNext@AppExecutionAlias@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::AppExecutionAlias::FindNext(StateRepository::Statement &,StateRepository::Entity::AppExecutionAlias &,bool &)
0x180028289  mov     ebx, eax
0x18002828b  test    eax, eax
0x18002828d  js      short loc_180028295
0x18002828f  mov     bl, byte ptr [rsp+5E0h+var_5B0]
0x180028293  jmp     short loc_180028257
0x180028295  mov     rcx, [rbp+4E8h]; this
0x18002829c  mov     r9d, eax; char *
0x18002829f  lea     r8, aOnecoreAdminAp_90; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x1800282a6  mov     edx, 1F8h; void *
0x1800282ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800282b0  jmp     loc_180028E3D
0x1800282b5  test    r13, r13
0x1800282b8  jnz     short loc_1800282BD
0x1800282ba  mov     [r14], dil
0x1800282bd  mov     [rsp+5E0h+var_568], rdi
0x1800282c2  mov     [rbp+4E0h+var_560], rdi
0x1800282c6  xorps   xmm0, xmm0
0x1800282c9  movdqu  [rbp+4E0h+var_558], xmm0
0x1800282ce  xorps   xmm1, xmm1
0x1800282d1  movdqu  [rbp+4E0h+var_548], xmm1
0x1800282d6  mov     [rbp+4E0h+var_538], rdi
0x1800282da  mov     [rbp+4E0h+var_4A0], rdi
0x1800282de  mov     [rbp+4E0h+var_498], rdi
0x1800282e2  movdqa  [rbp+4E0h+var_490], xmm0
0x1800282e7  movdqa  [rbp+4E0h+var_480], xmm1
0x1800282ec  mov     [rbp+4E0h+var_470], edi
0x1800282ef  mov     [rbp+4E0h+var_468], rdi
0x1800282f3  movdqa  [rbp+4E0h+var_460], xmm0
0x1800282fb  mov     byte ptr [rsp+5E0h+var_5B0], dil
0x180028300  mov     rax, [r12+0E0h]
0x180028308  mov     [rsp+5E0h+var_578], rax
0x18002830d  mov     [rsp+5E0h+var_5A8], rdi
0x180028312  lea     rax, off_1802122B8
0x180028319  mov     [rbp+4E0h+var_528], rax
0x18002831d  lea     rax, [rsp+5E0h+var_578]
0x180028322  mov     qword ptr [rbp+4E0h+var_520], rax
0x180028326  lea     rax, [rbp+4E0h+var_528]
0x18002832a  mov     qword ptr [rbp+4E0h+var_530], rax
0x18002832e  lea     rax, aSelectApplicat_4; "SELECT _ApplicationIdentityID, _Revisio"...
0x180028335  mov     [rbp+4E0h+var_3D8], rax
0x18002833c  mov     [rbp+4E0h+var_3D0], rdi
0x180028343  mov     [rbp+4E0h+var_3C8], rdi
0x18002834a  lea     rax, [rsp+5E0h+var_5B0]
0x18002834f  mov     [rsp+5E0h+var_5C0], rax; int
0x180028354  lea     r9, [rsp+5E0h+var_5A8]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x180028359  lea     r8, [rbp+4E0h+var_530]; struct StateRepository::StatementExecution::StatementDefinition *
0x18002835d  lea     rdx, [rbp+4E0h+var_3D8]; struct StateRepository::Database *
0x180028364  mov     rcx, rsi; this
0x180028367  call    ?PrepareAndBindAndTryGetBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@AEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndTryGetBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &,bool &)
0x18002836c  mov     ebx, eax
0x18002836e  mov     r15b, byte ptr [rsp+5E0h+var_5B0]
0x180028373  test    eax, eax
0x180028375  jns     short loc_1800283A8
0x180028377  mov     rcx, [rbp+4E8h]; this
0x18002837e  mov     r9d, eax; char *
0x180028381  lea     r8, aOnecoreBaseApp_86; "onecore\\base\\appmodel\\staterepositor"...
0x180028388  mov     edx, 0A4h; void *
0x18002838d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028392  mov     rcx, qword ptr [rbp+4E0h+var_530]
0x180028396  mov     rdx, [rcx]
0x180028399  mov     rax, [rdx]
0x18002839c  xor     edx, edx
0x18002839e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283a3  jmp     loc_180028434
0x1800283a8  test    r15b, r15b
0x1800283ab  jz      short loc_1800283E9
0x1800283ad  lea     rdx, [rsp+5E0h+var_568]; struct StateRepository::Entity::ApplicationIdentity *
0x1800283b2  lea     rcx, [rsp+5E0h+var_5A8]; this
0x1800283b7  call    ?RowToObject@ApplicationIdentity@Entity@StateRepository@@CAJAEBVStatement@3@AEAV123@_J@Z; StateRepository::Entity::ApplicationIdentity::RowToObject(StateRepository::Statement const &,StateRepository::Entity::ApplicationIdentity &,__int64)
0x1800283bc  mov     ebx, eax
0x1800283be  test    eax, eax
0x1800283c0  jns     short loc_1800283E9
0x1800283c2  mov     rcx, [rbp+4E8h]; this
0x1800283c9  mov     r9d, eax; char *
  ... truncated ...
```
