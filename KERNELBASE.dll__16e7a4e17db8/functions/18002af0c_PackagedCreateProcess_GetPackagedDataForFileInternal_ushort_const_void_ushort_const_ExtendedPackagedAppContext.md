# PackagedCreateProcess::GetPackagedDataForFileInternal(ushort const *,void *,ushort const *,ExtendedPackagedAppContext *)

- ea: `0x18002af0c`
- end: `0x18002bf5c`
- name: `?GetPackagedDataForFileInternal@PackagedCreateProcess@@CAJPEBGPEAX0PEAVExtendedPackagedAppContext@@@Z`
- size: `4176`
- prototype: `__int64 __fastcall(const unsigned __int16 *Source, void *, const unsigned __int16 *, struct ExtendedPackagedAppContext *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180028ee0`
- `0x180155a6c`

## callees

- `0x180020880`
- `0x1800220f0`
- `0x1800224a0`
- `0x180028d1c`
- `0x180029fe4`
- `0x18002a720`
- `0x18002ad78`
- `0x18002af0c`
- `0x18002bf64`
- `0x18002c724`
- `0x18002ca5c`
- `0x18002cd6c`
- `0x18002da14`
- `0x18002ddc0`
- `0x18002f738`
- `0x18002fd98`
- `0x180058768`
- `0x1800a7028`
- `0x1800a7118`
- `0x1800a9454`
- `0x1800b31d0`
- `0x1800dc350`
- `0x1800e665c`
- `0x1800e93e0`
- `0x18010c518`
- `0x180115590`
- `0x1801155f8`
- `0x18011f9a8`
- `0x180121cb0`
- `0x180123c30`
- `0x180155ec0`

## import_xrefs

- `ntdll!memcpy_s` at `0x18002b186`
- `ntdll!memcpy_s` at `0x18002b267`
- `ntdll!memcpy_s` at `0x18002b362`
- `ntdll!memcpy_s` at `0x18002b186`
- `ntdll!memcpy_s` at `0x18002b267`
- `ntdll!memcpy_s` at `0x18002b362`
- `ntdll!RtlFreeSid` at `0x18002b684`
- `ntdll!RtlFreeSid` at `0x18002ba40`
- `ntdll!RtlFreeSid` at `0x18002bbb2`
- `ntdll!RtlFreeSid` at `0x18002b684`
- `ntdll!RtlFreeSid` at `0x18002ba40`
- `ntdll!RtlFreeSid` at `0x18002bbb2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002b083`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18002b083`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002af62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Open` at `0x18002af62`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b49c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b4fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b596`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b5d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b82f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b855`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b95e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b9e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bc9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bd3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bea2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b49c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b4fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b596`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b5d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b82f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b855`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b95e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002b9e5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bc9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bd3a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002bea2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002af85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002afd4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b44e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b86a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b9fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bb1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bcb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bd4f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002af85`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002afd4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b44e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b5ed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b86a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002b9fa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bb1b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bcb8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x18002bd4f`

## string_xrefs

- `0x18002afb6`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b3e8`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b463`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b4d3`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b52f`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b550`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b696`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b6c6`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b79e`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b811`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b8e2`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b91f`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002baf5`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bb32`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bb95`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bbfa`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bc24`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bc57`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002bcca`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002be72`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18018d53e`: `onecore\base\appmodel\processcreation\src\packagedcreateprocess.cpp`
- `0x18002b4b8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002b50a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002bd8c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18002bd71`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18002af96`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-manager.hpp`
- `0x18002bf2e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002bf4a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002b7f1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18002bf1b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18018d4ba`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18018d4ca`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`
- `0x18018d509`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-DependencyGraph.hpp`

## pseudocode

```c
__int64 __fastcall PackagedCreateProcess::GetPackagedDataForFileInternal(
        const unsigned __int16 *Source,
        void *a2,
        const unsigned __int16 *a3,
        struct ExtendedPackagedAppContext *a4)
{
  const unsigned __int16 *v5; // r14
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v13; // eax
  int v14; // eax
  __int64 v15; // r13
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  rsize_t v18; // rdi
  char *v19; // rax
  char *v20; // rbx
  HLOCAL v21; // rbx
  int MatchingAppUserModelIdIfPresent; // eax
  HRESULT WindowsPplTrustLabelSid; // edi
  const WCHAR *v24; // rdx
  const WCHAR *v25; // rcx
  int v26; // eax
  const char *v27; // r9
  void *v28; // r15
  __int64 v29; // rcx
  char *v30; // rax
  rsize_t v31; // rsi
  WCHAR *v32; // rax
  WCHAR *v33; // rdi
  __int64 v34; // r8
  WCHAR *v35; // rsi
  int v36; // ecx
  void *v37; // rax
  __int64 v38; // rcx
  const char *v39; // r9
  char *v40; // rax
  rsize_t v41; // r14
  char *v42; // rax
  char *v43; // rdi
  _WORD *v44; // r9
  _WORD *v45; // r8
  __int64 v46; // rax
  __int64 v47; // rdx
  _WORD *v48; // rcx
  signed int v49; // r14d
  __int64 v50; // rcx
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rcx
  __int64 v59; // rcx
  bool v60; // r9
  __int64 v61; // rdx
  int v62; // eax
  void *v63; // r14
  int v64; // eax
  unsigned int v65; // r13d
  __int64 v66; // rdx
  int v67; // eax
  unsigned int v68; // esi
  __int64 v69; // rdx
  __int64 *v70; // rcx
  __int64 v71; // rcx
  __int64 v72; // rcx
  __int64 *v73; // rcx
  int Next; // eax
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int64 v77; // rcx
  int v78; // eax
  __int64 v79; // rcx
  __int64 v80; // rdx
  __int64 v81; // rcx
  __int64 v82; // rcx
  __int64 v83; // rcx
  __int64 v84; // rcx
  int v85; // eax
  __int64 *v86; // rcx
  int v87; // edx
  int v88; // eax
  __int64 v89; // r8
  __int64 v90; // rdx
  int v91; // eax
  __int64 v92; // r8
  __int64 v93; // rdx
  struct ExtendedPackagedAppContext *v94; // [rsp+28h] [rbp-E0h]
  int v95; // [rsp+28h] [rbp-E0h]
  int v96; // [rsp+28h] [rbp-E0h]
  int v97; // [rsp+28h] [rbp-E0h]
  int v98; // [rsp+28h] [rbp-E0h]
  bool v99[8]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v100; // [rsp+40h] [rbp-C8h] BYREF
  int v101[2]; // [rsp+48h] [rbp-C0h] BYREF
  void *Sourcea; // [rsp+50h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v104; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v105; // [rsp+68h] [rbp-A0h]
  __int64 v106; // [rsp+70h] [rbp-98h]
  __int64 *v107; // [rsp+78h] [rbp-90h] BYREF
  __int64 v108; // [rsp+80h] [rbp-88h] BYREF
  __int64 v109; // [rsp+88h] [rbp-80h]
  __int64 v110; // [rsp+90h] [rbp-78h] BYREF
  __int64 v111[2]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v112; // [rsp+A8h] [rbp-60h]
  __int64 v113; // [rsp+B0h] [rbp-58h]
  __int64 v114; // [rsp+B8h] [rbp-50h]
  __int64 v115; // [rsp+C0h] [rbp-48h]
  __int64 v116; // [rsp+C8h] [rbp-40h]
  __int64 v117; // [rsp+D0h] [rbp-38h]
  __int128 v118; // [rsp+D8h] [rbp-30h]
  int v119; // [rsp+E8h] [rbp-20h]
  __int64 v120; // [rsp+F0h] [rbp-18h]
  __int64 v121; // [rsp+F8h] [rbp-10h]
  __int64 v122; // [rsp+108h] [rbp+0h] BYREF
  __int128 v123; // [rsp+110h] [rbp+8h] BYREF
  __int128 v124; // [rsp+120h] [rbp+18h]
  __int64 v125; // [rsp+130h] [rbp+28h]
  __int128 v126; // [rsp+138h] [rbp+30h] BYREF
  __int64 v127; // [rsp+148h] [rbp+40h]
  __int128 v128; // [rsp+150h] [rbp+48h]
  __int64 v129; // [rsp+160h] [rbp+58h]
  __int64 v130; // [rsp+168h] [rbp+60h]
  __int64 v131; // [rsp+170h] [rbp+68h]
  __int128 v132; // [rsp+178h] [rbp+70h]
  int v133; // [rsp+188h] [rbp+80h]
  __int64 v134; // [rsp+190h] [rbp+88h]
  __int64 v135; // [rsp+198h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1E0h] [rbp+D8h]

  LOBYTE(v109) = 1;
  v5 = Source;
  v107 = &v100;
  v100 = 0;
  v108 = 0;
  v8 = SRCacheManager_Open(0, &v108);
  if ( (_BYTE)v109 )
  {
    v9 = *v107;
    *v107 = v108;
    if ( v9 )
      SRCacheManager_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-manager.hpp",
      (const char *)(unsigned int)v8,
      (int)v94);
    v10 = 375;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)v8,
      (int)v94);
    goto LABEL_7;
  }
  v122 = 0;
  v8 = StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(
         (struct StateRepository::Cache::Manager_NoThrow *)&v100,
         a3,
         &v122);
  if ( v8 < 0 )
  {
    v10 = 377;
    goto LABEL_6;
  }
  if ( !v122 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17A,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)0x80070057LL,
      (int)v94);
    v79 = v100;
    v100 = 0;
    if ( v79 )
      SRCacheManager_Close(v79);
    return 2147942487LL;
  }
  v104 = 0;
  LODWORD(v105) = 0;
  v106 = 0;
  v13 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(
          (StateRepository::Cache::Entity::PackageIndexIterator_NoThrow *)&v104,
          (struct StateRepository::Cache::Manager_NoThrow *)&v100,
          v122);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x81F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v13,
      (int)v94);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17E,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)v8,
      v95);
    goto LABEL_69;
  }
  *(_OWORD *)v111 = 0;
  v112 = 0;
  v113 = 0;
  v114 = 0;
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  v119 = 0;
  v120 = 0;
  v121 = 0;
  LOBYTE(v101[0]) = 0;
  if ( v104 )
  {
    Sourcea = 0;
    v14 = SRCacheContext_EnumerateData(v104, (unsigned int)v105, &Sourcea);
    v8 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v14,
        (int)v94);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x755,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v8,
        v97);
      v55 = 1901;
    }
    else
    {
      if ( !Sourcea )
        goto LABEL_17;
      v94 = (struct ExtendedPackagedAppContext *)v101;
      v8 = StateRepository::Cache::Entity::Package_NoThrow::Get(v106, Sourcea, 1853, v111);
      if ( v8 >= 0 )
        goto LABEL_17;
      v55 = 1906;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v55,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      (int)v94);
    v56 = 395;
LABEL_73:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v56,
      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
      (const char *)(unsigned int)v8,
      (int)v94);
    goto LABEL_74;
  }
LABEL_17:
  v110 = 0;
  v8 = StateRepository::Cache::Entity::User_NoThrow::GetByToken(
         (struct StateRepository::Cache::Manager_NoThrow *)&v100,
         a2,
         &v110);
  if ( v8 < 0 )
  {
    v56 = 398;
    goto LABEL_73;
  }
  v15 = 0x7FFFFFFF;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        if ( !LOBYTE(v101[0]) )
        {
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
          wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v104, 0);
          wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v100, 0);
          return 2147943568LL;
        }
        if ( (v113 & 0x21) != 0 )
          break;
LABEL_129:
        Next = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v104, 1853, v111, v101);
        v8 = Next;
        if ( Next < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x212,
            (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
            (const char *)(unsigned int)Next,
            (int)v94);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
          wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>::reset(&v104, 0);
          wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>::reset(&v100, 0);
          return (unsigned int)v8;
        }
      }
      v99[0] = 0;
      v8 = StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(
             (struct StateRepository::Cache::Manager_NoThrow *)&v100,
             v110,
             v111[0],
             v99);
      if ( v8 < 0 )
      {
        v56 = 407;
        goto LABEL_73;
      }
      if ( !v99[0] )
        goto LABEL_129;
      *((_DWORD *)a4 + 137) = 0;
      hMem = 0;
      if ( v5 )
        break;
      if ( (int)PackagedCreateProcess::GetNewFilePathIfPresent(
                  *((PCWSTR *)a4 + 75),
                  *((_DWORD *)a4 + 157),
                  (__int64)&hMem) >= 0 )
        goto LABEL_30;
      v78 = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(&v104, 1853, v111, v101);
      v8 = v78;
      if ( v78 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1A6,
          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
          (const char *)(unsigned int)v78,
          (int)v94);
        if ( hMem )
          LocalFree(hMem);
LABEL_74:
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
LABEL_69:
        v54 = v104;
        v104 = 0;
        if ( v54 )
          SRCacheContext_Close(v54);
LABEL_7:
        v11 = v100;
        v100 = 0;
        if ( v11 )
          SRCacheManager_Close(v11);
        return (unsigned int)v8;
      }
      if ( hMem )
        LocalFree(hMem);
    }
    v16 = 0x7FFFFFFF;
    v17 = v5;
    do
    {
      if ( !*v17 )
        break;
      ++v17;
      --v16;
    }
    while ( v16 );
    v18 = 2 * (v17 - v5);
    v19 = (char *)LocalAlloc(0, v18 + 2);
    v20 = v19;
    if ( v19 )
    {
      memcpy_s(v19, v18 + 2, v5, v18);
      *(_WORD *)&v20[v18] = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &hMem,
      v20);
LABEL_30:
    v21 = hMem;
    if ( !hMem )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AA,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v94);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&hMem);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
      v52 = v104;
      v104 = 0;
      if ( v52 )
        SRCacheContext_Close(v52);
      v53 = v100;
      v100 = 0;
      goto LABEL_81;
    }
    MatchingAppUserModelIdIfPresent = PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(
                                        (const unsigned __int16 *)hMem,
                                        (const struct StateRepository::Cache::Entity::Package_NoThrow *)v111,
                                        v110,
                                        (struct StateRepository::Cache::Manager_NoThrow *)&v100,
                                        a4);
    WindowsPplTrustLabelSid = MatchingAppUserModelIdIfPresent;
    if ( MatchingAppUserModelIdIfPresent < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1AC,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)MatchingAppUserModelIdIfPresent,
        (int)v94);
LABEL_133:
      LocalFree(v21);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
      v75 = v104;
      v104 = 0;
      if ( v75 )
        SRCacheContext_Close(v75);
      v59 = v100;
      v100 = 0;
      goto LABEL_87;
    }
    if ( !*((_DWORD *)a4 + 137) )
    {
      v107 = 0;
      LODWORD(v108) = 0;
      v109 = 0;
      v67 = StateRepository::Cache::Entity::DependencyGraphIndexIterator_NoThrow::OpenByUserAndDependentPackageAndDependencyType(
              &v107,
              &v100,
              v110,
              v111[0]);
      v68 = v67;
      if ( v67 >= 0 )
      {
        v123 = 0;
        v125 = 0;
        v124 = 0;
        v99[0] = 0;
        if ( !v107 )
          goto LABEL_192;
        Sourcea = 0;
        v91 = StateRepository::Cache::Context_NoThrow::EnumerateData(
                (StateRepository::Cache::Context_NoThrow *)&v107,
                v108,
                (__int64 *)&Sourcea);
        v68 = v91;
        if ( v91 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
            (const char *)(unsigned int)v91,
            (int)v94);
          v93 = 402;
        }
        else
        {
          if ( !Sourcea
            || (v94 = (struct ExtendedPackagedAppContext *)v99,
                v68 = StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(v109, Sourcea, v92, &v123),
                (v68 & 0x80000000) == 0) )
          {
            while ( 1 )
            {
LABEL_192:
              if ( !v99[0] )
                goto LABEL_125;
              v94 = (struct ExtendedPackagedAppContext *)v99;
              v126 = 0;
              v132 = 0;
              v127 = 0;
              v129 = 0;
              v128 = 0;
              v130 = 0;
              v131 = 0;
              v133 = 0;
              v134 = 0;
              v135 = 0;
              v99[0] = 0;
              StateRepository::Cache::Entity::Package_NoThrow::Get(&v100, *((_QWORD *)&v124 + 1), 1853, &v126);
              if ( v99[0] )
              {
                v85 = PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(
                        (const unsigned __int16 *)v21,
                        (const struct StateRepository::Cache::Entity::Package_NoThrow *)&v126,
                        v110,
                        (struct StateRepository::Cache::Manager_NoThrow *)&v100,
                        a4);
                WindowsPplTrustLabelSid = v85;
                if ( v85 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x1C1,
                    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                    (const char *)(unsigned int)v85,
                    (int)v94);
                  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v126);
                  v86 = v107;
                  v107 = 0;
                  if ( v86 )
                    SRCacheContext_Close(v86);
                  goto LABEL_133;
                }
                if ( *((_DWORD *)a4 + 137) )
                  break;
              }
              v87 = v108 + 1;
              v99[0] = 0;
              LODWORD(v108) = v108 + 1;
              if ( v107 )
              {
                Sourcea = 0;
                v88 = StateRepository::Cache::Context_NoThrow::EnumerateData(
                        (StateRepository::Cache::Context_NoThrow *)&v107,
                        v87,
                        (__int64 *)&Sourcea);
                v68 = v88;
                if ( v88 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x17A,
                    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
                    (const char *)(unsigned int)v88,
                    (int)v94);
                  v90 = 402;
                  goto LABEL_213;
                }
                if ( Sourcea )
                {
                  v94 = (struct ExtendedPackagedAppContext *)v99;
                  v68 = StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(v109, Sourcea, v89, &v123);
                  if ( (v68 & 0x80000000) != 0 )
                  {
                    v90 = 407;
LABEL_213:
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)v90,
                      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
                      (const char *)v68,
                      (int)v94);
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x1C8,
                      (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
                      (const char *)v68,
                      v98);
                    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v126);
                    goto LABEL_116;
                  }
                }
              }
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v126);
            }
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v126);
LABEL_125:
            v73 = v107;
            v107 = 0;
            if ( v73 )
              SRCacheContext_Close(v73);
            if ( !*((_DWORD *)a4 + 137) )
            {
              LocalFree(v21);
              goto LABEL_129;
            }
            goto LABEL_33;
          }
          v93 = 407;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v93,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
          (const char *)v68,
          (int)v94);
        v69 = 439;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24A,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-DependencyGraph.hpp",
          (const char *)(unsigned int)v67,
          (int)v94);
        v69 = 434;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v69,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)v68,
        v96);
LABEL_116:
      v70 = v107;
      v107 = 0;
      if ( v70 )
        SRCacheContext_Close(v70);
      LocalFree(v21);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
      v71 = v104;
      v104 = 0;
      if ( v71 )
        SRCacheContext_Close(v71);
      v72 = v100;
      v100 = 0;
      if ( v72 )
        SRCacheManager_Close(v72);
      return v68;
    }
LABEL_33:
    v24 = (const WCHAR *)*((_QWORD *)a4 + 75);
    v25 = (const WCHAR *)*((_QWORD *)a4 + 74);
    Sourcea = 0;
    v26 = PathAllocCombine(v25, v24, 1u, (unsigned __int16 **)&Sourcea);
    WindowsPplTrustLabelSid = v26;
    if ( v26 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)v26,
        (int)v94);
      if ( Sourcea )
        LocalFree(Sourcea);
      goto LABEL_133;
    }
    v28 = Sourcea;
    if ( !Sourcea )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v27);
    v29 = 0x7FFFFFFF;
    v30 = (char *)Sourcea;
    do
    {
      if ( !*(_WORD *)v30 )
        break;
      v30 += 2;
      --v29;
    }
    while ( v29 );
    v31 = 2 * ((v30 - (_BYTE *)Sourcea) >> 1);
    v32 = (WCHAR *)LocalAlloc(0, v31 + 2);
    v33 = v32;
    if ( !v32 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D3,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v94);
LABEL_76:
      if ( v28 )
        LocalFree(v28);
      LocalFree(v21);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
      v57 = v104;
      v104 = 0;
      if ( v57 )
        SRCacheContext_Close(v57);
      v53 = v100;
      v100 = 0;
LABEL_81:
      if ( v53 )
        SRCacheManager_Close(v53);
      return 2147942414LL;
    }
    memcpy_s(v32, v31 + 2, v28, v31);
    v34 = 0x7FFFFFFF;
    v33[v31 / 2] = 0;
    v35 = v33;
    do
    {
      if ( !*v33 )
        break;
      ++v33;
      --v34;
    }
    while ( v34 );
    WindowsPplTrustLabelSid = v34 == 0 ? 0x80070057 : 0;
    if ( !v34 )
    {
      v61 = 469;
      goto LABEL_99;
    }
    WindowsPplTrustLabelSid = PathCchRemoveFileSpec(
                                v35,
                                (0x7FFFFFFF - v34) & ((unsigned __int128)-(__int128)(unsigned __int64)v34 >> 64));
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v61 = 470;
LABEL_99:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v61,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)(unsigned int)WindowsPplTrustLabelSid,
        (int)v94);
      goto LABEL_100;
    }
    v36 = HIDWORD(v113);
    *((_BYTE *)a4 + 624) = BYTE4(v113) & 1;
    *((_BYTE *)a4 + 625) = (v36 & 0x800) != 0;
    v37 = (void *)v111[1];
    *((_BYTE *)a4 + 626) = (v36 & 0x400000) != 0;
    v38 = *((unsigned int *)a4 + 157);
    Sourcea = v37;
    if ( !(unsigned __int8)PackagedCreateProcess::IsTrustLabelAceSupported(v38) )
      goto LABEL_45;
    if ( !HIDWORD(v114) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1E6,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x80070490LL,
        (int)v94);
      LocalFree(v35);
      if ( v28 )
        LocalFree(v28);
      LocalFree(v21);
      StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
      v81 = v104;
      v104 = 0;
      if ( v81 )
        SRCacheContext_Close(v81);
      v82 = v100;
      v100 = 0;
      if ( v82 )
        SRCacheManager_Close(v82);
      return 2147943568LL;
    }
    if ( HIDWORD(v114) != 3 )
      goto LABEL_45;
    v99[0] = 0;
    hMem = 0;
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(&hMem);
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v80 = 493;
      goto LABEL_163;
    }
    WindowsPplTrustLabelSid = TrustLabelAceHelpers::IsFileSystemObjectTrustable(
                                (const unsigned __int16 *)v28,
                                hMem,
                                0,
                                v60,
                                1,
                                v99);
    if ( WindowsPplTrustLabelSid < 0 )
      break;
    if ( v99[0] )
    {
      if ( hMem )
        RtlFreeSid(hMem);
LABEL_45:
      *(_BYTE *)a4 = 1;
      if ( !v28 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xF89,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v39);
      v40 = (char *)v28;
      do
      {
        if ( !*(_WORD *)v40 )
          break;
        v40 += 2;
        --v15;
      }
      while ( v15 );
      v41 = 2 * ((v40 - (_BYTE *)v28) >> 1);
      v42 = (char *)LocalAlloc(0, v41 + 2);
      v43 = v42;
      if ( v42 )
      {
        memcpy_s(v42, v41 + 2, v28, v41);
        *(_WORD *)&v43[v41] = 0;
        if ( *((_DWORD *)a4 + 137) == 1 )
        {
          Sourcea = 0;
          hMem = 0;
          v62 = wil::GetSystemDirectoryW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(&Sourcea);
          v49 = v62;
          if ( v62 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x201,
              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
              (const char *)(unsigned int)v62,
              (int)v94);
            if ( Sourcea )
              LocalFree(Sourcea);
            goto LABEL_59;
          }
          v63 = Sourcea;
          v64 = wil::str_concat_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,unsigned short *,unsigned short [23]>(
                  &hMem,
                  &Sourcea);
          v65 = v64;
          if ( v64 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x202,
              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
              (const char *)(unsigned int)v64,
              (int)v94);
            if ( hMem )
              LocalFree(hMem);
            if ( v63 )
              LocalFree(v63);
            LocalFree(v43);
            LocalFree(v35);
            LocalFree(v28);
            LocalFree(v21);
            StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
            v83 = v104;
            v104 = 0;
            if ( v83 )
              SRCacheContext_Close(v83);
            v84 = v100;
            v100 = 0;
            if ( v84 )
              SRCacheManager_Close(v84);
            return v65;
          }
          Sourcea = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &Sourcea,
            hMem);
          hMem = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &hMem,
            v43);
          if ( hMem )
            LocalFree(hMem);
          if ( v63 )
            LocalFree(v63);
          v43 = (char *)Sourcea;
        }
        else
        {
          v44 = Sourcea;
          v45 = (_WORD *)((char *)a4 + 262);
          v46 = 2147483646;
          v47 = 128;
          do
          {
            if ( !v46 )
              break;
            if ( !*v44 )
              break;
            *v45++ = *v44++;
            --v46;
            --v47;
          }
          while ( v47 );
          v48 = v45 - 1;
          v49 = v47 == 0 ? 0x8007007A : 0;
          if ( v47 )
            v48 = v45;
          *v48 = 0;
          if ( !v47 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x207,
              (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
              (const char *)(unsigned int)v49,
              (int)v94);
            goto LABEL_59;
          }
        }
        v49 = ExtendedPackagedAppContext::SetFinalPath(a4, (unsigned __int16 *)v43);
        if ( v49 >= 0 )
        {
          v49 = ExtendedPackagedAppContext::SetCurrentDirectoryW(a4, v35);
          if ( v49 < 0 )
          {
            v66 = 523;
          }
          else
          {
            v49 = ExtendedPackagedAppContext::SetPackageFamilyName(a4, a3);
            if ( v49 >= 0 )
            {
              if ( v43 )
                LocalFree(v43);
              LocalFree(v35);
              LocalFree(v28);
              LocalFree(v21);
              StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
              v76 = v104;
              v104 = 0;
              if ( v76 )
                SRCacheContext_Close(v76);
              v77 = v100;
              v100 = 0;
              if ( v77 )
                SRCacheManager_Close(v77);
              return 0;
            }
            v66 = 524;
          }
        }
        else
        {
          v66 = 522;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v66,
          (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
          (const char *)(unsigned int)v49,
          (int)v94);
        if ( !v43 )
        {
LABEL_60:
          LocalFree(v35);
          LocalFree(v28);
          LocalFree(v21);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
          v50 = v104;
          v104 = 0;
          if ( v50 )
            SRCacheContext_Close(v50);
          v51 = v100;
          v100 = 0;
          if ( v51 )
            SRCacheManager_Close(v51);
          return (unsigned int)v49;
        }
LABEL_59:
        LocalFree(v43);
        goto LABEL_60;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1FC,
        (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
        (const char *)0x8007000ELL,
        (int)v94);
      LocalFree(v35);
      goto LABEL_76;
    }
    WindowsPplTrustLabelSid = StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::GetNext(
                                &v104,
                                1853,
                                v111,
                                v101);
    if ( WindowsPplTrustLabelSid < 0 )
    {
      v80 = 500;
      goto LABEL_163;
    }
    if ( hMem )
      RtlFreeSid(hMem);
    LocalFree(v35);
    if ( v28 )
      LocalFree(v28);
    LocalFree(v21);
    v5 = Source;
  }
  v80 = 495;
LABEL_163:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v80,
    (unsigned int)"onecore\\base\\appmodel\\processcreation\\src\\packagedcreateprocess.cpp",
    (const char *)(unsigned int)WindowsPplTrustLabelSid,
    (int)v94);
  if ( hMem )
    RtlFreeSid(hMem);
LABEL_100:
  LocalFree(v35);
  if ( v28 )
    LocalFree(v28);
  LocalFree(v21);
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v111);
  v58 = v104;
  v104 = 0;
  if ( v58 )
    SRCacheContext_Close(v58);
  v59 = v100;
  v100 = 0;
LABEL_87:
  if ( v59 )
    SRCacheManager_Close(v59);
  return (unsigned int)WindowsPplTrustLabelSid;
}

```

## disassembly

```asm
0x18002af0c  mov     rax, rsp
0x18002af0f  mov     [rax+10h], rbx
0x18002af13  mov     [rax+18h], r8
0x18002af17  mov     [rax+8], rcx
0x18002af1b  push    rbp
0x18002af1c  push    rsi
0x18002af1d  push    rdi
0x18002af1e  push    r12
0x18002af20  push    r13
0x18002af22  push    r14
0x18002af24  push    r15
0x18002af26  lea     rbp, [rax-0D8h]
0x18002af2d  sub     rsp, 1A0h
0x18002af34  mov     rdi, rdx
0x18002af37  mov     byte ptr [rbp+0D0h+var_150], 1
0x18002af3b  mov     r14, rcx
0x18002af3e  lea     rax, [rsp+1D0h+var_198]
0x18002af43  xor     r15d, r15d
0x18002af46  mov     [rsp+1D0h+var_160], rax
0x18002af4b  lea     rdx, [rsp+1D0h+var_158]
0x18002af50  mov     [rsp+1D0h+var_198], r15
0x18002af55  xor     ecx, ecx
0x18002af57  mov     [rsp+1D0h+var_158], r15
0x18002af5c  mov     r12, r9
0x18002af5f  mov     rsi, r8
0x18002af62  call    cs:__imp_SRCacheManager_Open
0x18002af68  mov     ebx, eax
0x18002af6a  cmp     byte ptr [rbp+0D0h+var_150], r15b
0x18002af6e  jz      short loc_18002AF8B
0x18002af70  mov     r8, [rsp+1D0h+var_160]
0x18002af75  mov     rdx, [rsp+1D0h+var_158]
0x18002af7a  mov     rcx, [r8]
0x18002af7d  mov     [r8], rdx
0x18002af80  test    rcx, rcx
0x18002af83  jz      short loc_18002AF8B
0x18002af85  call    cs:__imp_SRCacheManager_Close
0x18002af8b  test    ebx, ebx
0x18002af8d  jns     short loc_18002AFE1
0x18002af8f  mov     rcx, [rbp+0D8h]; this
0x18002af96  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002af9d  mov     r9d, ebx; char *
0x18002afa0  mov     edx, 0A5h; void *
0x18002afa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afaa  mov     edx, 177h; void *
0x18002afaf  mov     rcx, [rbp+0D8h]; this
0x18002afb6  lea     r8, aOnecoreBaseApp_17; "onecore\\base\\appmodel\\processcreatio"...
0x18002afbd  mov     r9d, ebx; char *
0x18002afc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afc5  mov     rcx, [rsp+1D0h+var_198]
0x18002afca  mov     [rsp+1D0h+var_198], r15
0x18002afcf  test    rcx, rcx
0x18002afd2  jz      short loc_18002AFDA
0x18002afd4  call    cs:__imp_SRCacheManager_Close
0x18002afda  mov     eax, ebx
0x18002afdc  jmp     loc_18002B5F5
0x18002afe1  lea     r8, [rbp+0D0h+var_D0]; __int64 *
0x18002afe5  mov     [rbp+0D0h+var_D0], r15
0x18002afe9  mov     rdx, rsi; unsigned __int16 *
0x18002afec  lea     rcx, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18002aff1  call    ?GetByPackageFamilyName@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::GetByPackageFamilyName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)
0x18002aff6  mov     ebx, eax
0x18002aff8  test    eax, eax
0x18002affa  js      loc_18002BBBD
0x18002b000  mov     r8, [rbp+0D0h+var_D0]; __int64
0x18002b004  test    r8, r8
0x18002b007  jz      loc_18002BAEE
0x18002b00d  lea     rdx, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18002b012  mov     [rsp+1D0h+var_178], r15
0x18002b017  lea     rcx, [rsp+1D0h+var_178]; this
0x18002b01c  mov     dword ptr [rsp+1D0h+var_170], r15d
0x18002b021  mov     [rsp+1D0h+var_168], r15
0x18002b026  call    ?OpenByPackageFamily@PackageIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@_J@Z; StateRepository::Cache::Entity::PackageIndexIterator_NoThrow::OpenByPackageFamily(StateRepository::Cache::Manager_NoThrow &,__int64)
0x18002b02b  mov     ebx, eax
0x18002b02d  test    eax, eax
0x18002b02f  js      loc_18002B4B1
0x18002b035  mov     rcx, [rsp+1D0h+var_178]
0x18002b03a  xorps   xmm0, xmm0
0x18002b03d  movdqa  xmmword ptr [rbp+0D0h+var_140], xmm0
0x18002b042  mov     [rbp+0D0h+var_130], r15
0x18002b046  mov     [rbp+0D0h+var_128], r15
0x18002b04a  mov     [rbp+0D0h+var_120], r15
0x18002b04e  mov     [rbp+0D0h+var_118], r15
0x18002b052  mov     [rbp+0D0h+var_110], r15
0x18002b056  mov     [rbp+0D0h+var_108], r15
0x18002b05a  movdqa  [rbp+0D0h+var_100], xmm0
0x18002b05f  mov     [rbp+0D0h+var_F0], r15d
0x18002b063  mov     [rbp+0D0h+var_E8], r15
0x18002b067  mov     [rbp+0D0h+var_E0], r15
0x18002b06b  mov     byte ptr [rsp+1D0h+var_190], r15b
0x18002b070  test    rcx, rcx
0x18002b073  jz      short loc_18002B0C5
0x18002b075  mov     edx, dword ptr [rsp+1D0h+var_170]
0x18002b079  lea     r8, [rsp+1D0h+Source]
0x18002b07e  mov     [rsp+1D0h+Source], r15
0x18002b083  call    cs:__imp_SRCacheContext_EnumerateData
0x18002b089  mov     ebx, eax
0x18002b08b  test    eax, eax
0x18002b08d  js      loc_18002BD6A
0x18002b093  mov     rdx, [rsp+1D0h+Source]
0x18002b098  test    rdx, rdx
0x18002b09b  jz      short loc_18002B0C5
0x18002b09d  mov     rcx, [rsp+1D0h+var_168]
0x18002b0a2  lea     rax, [rsp+1D0h+var_190]
0x18002b0a7  lea     r9, [rbp+0D0h+var_140]
0x18002b0ab  mov     [rsp+1D0h+var_1B0], rax; int
0x18002b0b0  mov     r8d, 73Dh
0x18002b0b6  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x18002b0bb  mov     ebx, eax
0x18002b0bd  test    eax, eax
0x18002b0bf  js      loc_18002B505
0x18002b0c5  lea     r8, [rbp+0D0h+var_148]; __int64 *
0x18002b0c9  mov     [rbp+0D0h+var_148], r15
0x18002b0cd  mov     rdx, rdi; void *
0x18002b0d0  lea     rcx, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18002b0d5  call    ?GetByToken@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEAXAEA_J@Z; StateRepository::Cache::Entity::User_NoThrow::GetByToken(StateRepository::Cache::Manager_NoThrow &,void *,__int64 &)
0x18002b0da  mov     ebx, eax
0x18002b0dc  test    eax, eax
0x18002b0de  js      loc_18002BBC7
0x18002b0e4  mov     r13d, 7FFFFFFFh
0x18002b0ea  cmp     byte ptr [rsp+1D0h+var_190], r15b
0x18002b0ef  jz      loc_18002BB5E
0x18002b0f5  test    byte ptr [rbp+0D0h+var_128], 21h
0x18002b0f9  jz      loc_18002B8B9
0x18002b0ff  mov     r8, [rbp+0D0h+var_140]; __int64
0x18002b103  lea     r9, [rsp+1D0h+var_1A0]; bool *
0x18002b108  mov     rdx, [rbp+0D0h+var_148]; __int64
0x18002b10c  lea     rcx, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18002b111  mov     [rsp+1D0h+var_1A0], r15b
0x18002b116  call    ?ExistsByUserAndPackage@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_J1AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ExistsByUserAndPackage(StateRepository::Cache::Manager_NoThrow &,__int64,__int64,bool &)
0x18002b11b  mov     ebx, eax
0x18002b11d  test    eax, eax
0x18002b11f  js      loc_18002BC13
0x18002b125  cmp     [rsp+1D0h+var_1A0], r15b
0x18002b12a  jz      loc_18002B8B9
0x18002b130  mov     [r12+224h], r15d
0x18002b138  mov     [rsp+1D0h+hMem], r15
0x18002b13d  test    r14, r14
0x18002b140  jz      loc_18002BA72
0x18002b146  mov     rcx, r13
0x18002b149  mov     rax, r14
0x18002b14c  cmp     [rax], r15w
0x18002b150  jz      short loc_18002B15C
0x18002b152  add     rax, 2
0x18002b156  sub     rcx, 1
0x18002b15a  jnz     short loc_18002B14C
0x18002b15c  sub     rax, r14
0x18002b15f  xor     ecx, ecx; uFlags
0x18002b161  sar     rax, 1
0x18002b164  lea     rdi, [rax+rax]
0x18002b168  lea     rdx, [rdi+2]; uBytes
0x18002b16c  call    LocalAlloc
0x18002b171  mov     rbx, rax
0x18002b174  test    rax, rax
0x18002b177  jz      short loc_18002B191
0x18002b179  mov     r9, rdi; SourceSize
0x18002b17c  lea     rdx, [rdi+2]; DestinationSize
0x18002b180  mov     r8, r14; Source
0x18002b183  mov     rcx, rax; Destination
0x18002b186  call    cs:__imp_memcpy_s
0x18002b18c  mov     [rbx+rdi], r15w
0x18002b191  mov     rdx, rbx
0x18002b194  lea     rcx, [rsp+1D0h+hMem]
0x18002b199  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002b19e  mov     rbx, [rsp+1D0h+hMem]
0x18002b1a3  test    rbx, rbx
0x18002b1a6  jz      loc_18002B45C
0x18002b1ac  mov     r8, [rbp+0D0h+var_148]; __int64
0x18002b1b0  lea     r9, [rsp+1D0h+var_198]; struct StateRepository::Cache::Manager_NoThrow *
0x18002b1b5  lea     rdx, [rbp+0D0h+var_140]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x18002b1b9  mov     [rsp+1D0h+var_1B0], r12; int
0x18002b1be  mov     rcx, rbx; unsigned __int16 *
0x18002b1c1  call    ?GetMatchingAppUserModelIdIfPresent@PackagedCreateProcess@@CAJPEBGAEBVPackage_NoThrow@Entity@Cache@StateRepository@@_JAEAVManager_NoThrow@45@PEAVExtendedPackagedAppContext@@@Z; PackagedCreateProcess::GetMatchingAppUserModelIdIfPresent(ushort const *,StateRepository::Cache::Entity::Package_NoThrow const &,__int64,StateRepository::Cache::Manager_NoThrow &,ExtendedPackagedAppContext *)
0x18002b1c6  mov     edi, eax
0x18002b1c8  test    eax, eax
0x18002b1ca  js      loc_18002BBF3
0x18002b1d0  cmp     [r12+224h], r15d
0x18002b1d8  jz      loc_18002B7BB
0x18002b1de  mov     rdx, [r12+258h]; pszMore
0x18002b1e6  lea     r9, [rsp+1D0h+Source]; unsigned __int16 **
0x18002b1eb  mov     rcx, [r12+250h]; pszPathIn
0x18002b1f3  mov     r8d, 1; dwFlags
0x18002b1f9  mov     [rsp+1D0h+Source], r15
0x18002b1fe  call    ?PathAllocCombine@@YAJPEBG0W4PATHCCH_OPTIONS@@PEAPEAG@Z; PathAllocCombine(ushort const *,ushort const *,PATHCCH_OPTIONS,ushort * *)
0x18002b203  mov     rcx, [rbp+0D8h]; this
0x18002b20a  mov     edi, eax
0x18002b20c  test    eax, eax
0x18002b20e  js      loc_18002B91C
0x18002b214  mov     r15, [rsp+1D0h+Source]
0x18002b219  xor     edx, edx
0x18002b21b  test    r15, r15
0x18002b21e  jz      loc_18002BF4A
0x18002b224  mov     rcx, r13
0x18002b227  mov     rax, r15
0x18002b22a  cmp     [rax], dx
0x18002b22d  jz      short loc_18002B239
0x18002b22f  add     rax, 2
0x18002b233  sub     rcx, 1
0x18002b237  jnz     short loc_18002B22A
0x18002b239  sub     rax, r15
0x18002b23c  xor     ecx, ecx; uFlags
0x18002b23e  sar     rax, 1
0x18002b241  lea     rsi, [rax+rax]
0x18002b245  lea     rdx, [rsi+2]; uBytes
0x18002b249  call    LocalAlloc
0x18002b24e  mov     rdi, rax
0x18002b251  test    rax, rax
0x18002b254  jz      loc_18002B549
0x18002b25a  mov     r9, rsi; SourceSize
0x18002b25d  lea     rdx, [rsi+2]; DestinationSize
0x18002b261  mov     r8, r15; Source
0x18002b264  mov     rcx, rax; Destination
0x18002b267  call    cs:__imp_memcpy_s
0x18002b26d  xor     r14d, r14d
0x18002b270  mov     r8, r13
0x18002b273  mov     [rsi+rdi], r14w
0x18002b278  mov     rsi, rdi
0x18002b27b  cmp     [rdi], r14w
0x18002b27f  jz      short loc_18002B28B
0x18002b281  add     rdi, 2
0x18002b285  sub     r8, 1
0x18002b289  jnz     short loc_18002B27B
0x18002b28b  mov     rax, r8
0x18002b28e  mov     rcx, r13
0x18002b291  neg     rax
0x18002b294  mov     rax, r8
0x18002b297  sbb     edi, edi
0x18002b299  sub     rcx, r8
0x18002b29c  not     edi
0x18002b29e  and     edi, 80070057h
0x18002b2a4  neg     rax
0x18002b2a7  sbb     rdx, rdx
0x18002b2aa  and     rdx, rcx; cchPath
0x18002b2ad  test    r8, r8
0x18002b2b0  jz      loc_18002BF40
0x18002b2b6  mov     rcx, rsi; pszPath
0x18002b2b9  call    PathCchRemoveFileSpec
0x18002b2be  mov     edi, eax
0x18002b2c0  test    eax, eax
0x18002b2c2  js      loc_18002B6BA
0x18002b2c8  mov     al, byte ptr [rbp+0D0h+var_128+4]
0x18002b2cb  mov     ecx, dword ptr [rbp+0D0h+var_128+4]
0x18002b2ce  and     al, 1
0x18002b2d0  mov     [r12+270h], al
0x18002b2d8  mov     eax, ecx
0x18002b2da  shr     eax, 0Bh
0x18002b2dd  shr     ecx, 16h
0x18002b2e0  and     al, 1
0x18002b2e2  and     cl, 1
0x18002b2e5  mov     [r12+271h], al
0x18002b2ed  mov     rax, [rbp+0D0h+var_140+8]
0x18002b2f1  mov     [r12+272h], cl
0x18002b2f9  mov     ecx, [r12+274h]
0x18002b301  mov     [rsp+1D0h+Source], rax
0x18002b306  call    ?IsTrustLabelAceSupported@PackagedCreateProcess@@CA_NW4PackagePathType@@@Z; PackagedCreateProcess::IsTrustLabelAceSupported(PackagePathType)
0x18002b30b  test    al, al
0x18002b30d  jnz     loc_18002B610
0x18002b313  mov     byte ptr [r12], 1
0x18002b318  test    r15, r15
0x18002b31b  jz      loc_18002BF27
0x18002b321  mov     rax, r15
0x18002b324  cmp     [rax], r14w
0x18002b328  jz      short loc_18002B334
0x18002b32a  add     rax, 2
0x18002b32e  sub     r13, 1
0x18002b332  jnz     short loc_18002B324
0x18002b334  sub     rax, r15
0x18002b337  xor     ecx, ecx; uFlags
0x18002b339  sar     rax, 1
0x18002b33c  lea     r14, [rax+rax]
0x18002b340  lea     rdx, [r14+2]; uBytes
0x18002b344  call    LocalAlloc
0x18002b349  mov     rdi, rax
0x18002b34c  test    rax, rax
0x18002b34f  jz      loc_18002B68F
0x18002b355  mov     r9, r14; SourceSize
0x18002b358  lea     rdx, [r14+2]; DestinationSize
0x18002b35c  mov     r8, r15; Source
0x18002b35f  mov     rcx, rax; Destination
0x18002b362  call    cs:__imp_memcpy_s
0x18002b368  xor     r13d, r13d
0x18002b36b  mov     [r14+rdi], r13w
0x18002b370  cmp     dword ptr [r12+224h], 1
0x18002b379  jz      loc_18002B6F3
0x18002b37f  mov     r9, [rsp+1D0h+Source]
0x18002b384  lea     r8, [r12+106h]
0x18002b38c  mov     eax, 7FFFFFFEh
0x18002b391  mov     edx, 80h
0x18002b396  test    rax, rax
0x18002b399  jz      short loc_18002B3B9
0x18002b39b  movzx   ecx, word ptr [r9]
0x18002b39f  test    cx, cx
0x18002b3a2  jz      short loc_18002B3B9
0x18002b3a4  mov     [r8], cx
0x18002b3a8  add     r9, 2
0x18002b3ac  add     r8, 2
0x18002b3b0  dec     rax
0x18002b3b3  sub     rdx, 1
0x18002b3b7  jnz     short loc_18002B396
0x18002b3b9  mov     rax, rdx
0x18002b3bc  lea     rcx, [r8-2]
  ... truncated ...
```
