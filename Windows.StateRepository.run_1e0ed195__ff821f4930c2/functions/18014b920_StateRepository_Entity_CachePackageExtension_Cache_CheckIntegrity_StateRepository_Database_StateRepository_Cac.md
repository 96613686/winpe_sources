# StateRepository::Entity::CachePackageExtension::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18014b920`
- end: `0x18014be82`
- name: `?Cache_CheckIntegrity@CachePackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1378`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800768cc`
- `0x1800a001c`
- `0x1800ae890`
- `0x1800b38e8`
- `0x18014b920`
- `0x18014be88`
- `0x18026544c`
- `0x1802677e8`
- `0x180267c14`
- `0x180267cdc`
- `0x180267dbc`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bc33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bdcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bdfb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bc33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bdcb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014bdfb`

## string_xrefs

- `0x18014b99c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014ba07`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bb4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bc10`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bc8c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bd7a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bd9a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014be5f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageextension.cpp`
- `0x18014bbf5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageExtension.hpp`
- `0x18014bb93`: `CachePackageExtension`
- `0x18014be14`: `CachePackageExtension`
- `0x18014bce3`: `SELECT EXISTS(SELECT 1 FROM CachePackageExtension WHERE _CachePackageExtensionID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageExtension::Cache_CheckIntegrity(
        StateRepository::Database *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        _QWORD *a4)
{
  struct StateRepository::Cache::Manager_NoThrow *v4; // rsi
  unsigned int v6; // ebx
  __int64 v7; // rdx
  int v8; // eax
  int Next; // eax
  int v10; // ecx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  int appended; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r15
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // eax
  __int64 v22; // rdx
  unsigned int v23; // edi
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rdi
  int v27; // eax
  __int64 v28; // rdx
  char v29; // r8
  int v30; // esi
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rcx
  bool *v35; // [rsp+20h] [rbp-E0h]
  int v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  bool *v38; // [rsp+28h] [rbp-D8h]
  __int64 v39; // [rsp+30h] [rbp-D0h] BYREF
  int v40; // [rsp+38h] [rbp-C8h]
  __int64 v41; // [rsp+40h] [rbp-C0h]
  __int64 v42; // [rsp+48h] [rbp-B8h] BYREF
  int v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v44; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v45; // [rsp+60h] [rbp-A0h] BYREF
  char *v46[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v47; // [rsp+80h] [rbp-80h]
  __int64 v48; // [rsp+88h] [rbp-78h]
  __int128 v49; // [rsp+90h] [rbp-70h]
  __int128 v50; // [rsp+A0h] [rbp-60h]
  __int128 v51; // [rsp+B0h] [rbp-50h]
  __int128 v52; // [rsp+C0h] [rbp-40h]
  __int128 v53; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v54; // [rsp+E0h] [rbp-20h]
  __int64 v55; // [rsp+E8h] [rbp-18h]
  __int128 v56; // [rsp+F0h] [rbp-10h]
  __int128 v57; // [rsp+100h] [rbp+0h]
  __int128 v58; // [rsp+110h] [rbp+10h] BYREF
  __int64 v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]
  __int128 v61; // [rsp+130h] [rbp+30h]
  __int128 v62; // [rsp+140h] [rbp+40h]
  __int128 v63; // [rsp+150h] [rbp+50h]
  __int128 v64; // [rsp+160h] [rbp+60h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  bool v66; // [rsp+1B0h] [rbp+B0h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v67; // [rsp+1B8h] [rbp+B8h]
  _QWORD *v68; // [rsp+1C8h] [rbp+C8h]

  v68 = a4;
  v67 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 657;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 658;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 659;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v43 = 0;
  v44 = 0;
  v42 = 0;
  v8 = StateRepository::Entity::CachePackageExtension::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v43);
    return v6;
  }
  v47 = 0;
  *(_OWORD *)v46 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v48 = 0;
  v66 = 0;
  Next = StateRepository::Entity::CachePackageExtension::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CachePackageExtension *)v46,
           &v66);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Entity::CachePackageExtension::~CachePackageExtension((StateRepository::Entity::CachePackageExtension *)v46);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v66 )
  {
    v35 = &v66;
    v53 = 0;
    v56 = 0;
    v57 = 0;
    v54 = 0;
    v55 = 0;
    appended = StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(v4, v46[0], v11, &v53);
    if ( appended < 0 )
    {
      v19 = 678;
      goto LABEL_27;
    }
    if ( v66 )
    {
      v45 = 0;
      appended = StateRepository::Entity::CachePackageExtension::Cache_Check(
                   (const struct StateRepository::Entity::CachePackageExtension *)v46,
                   (const struct StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v53,
                   &v45);
      if ( appended < 0 )
      {
        v19 = 683;
        goto LABEL_27;
      }
      v18 = v45;
      if ( v45 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v46[0], v17);
        if ( appended < 0 )
        {
          v19 = 687;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
            (const char *)(unsigned int)appended,
            (int)&v66);
          StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v53);
          StateRepository::Entity::CachePackageExtension::~CachePackageExtension((StateRepository::Entity::CachePackageExtension *)v46);
          v6 = appended;
          goto LABEL_28;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v46[0], v16);
      if ( appended < 0 )
      {
        v19 = 693;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CachePackageExtension::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CachePackageExtension *)v46,
                 &v66);
    if ( appended < 0 )
    {
      v19 = 695;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)&v53);
    v4 = v67;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageExtension",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CachePackageExtension::~CachePackageExtension((StateRepository::Entity::CachePackageExtension *)v46);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x375,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2C8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
      (const char *)v23,
      v36);
LABEL_34:
    v24 = v39;
    v39 = 0;
    if ( v24 )
      SRCacheContext_Close(v24);
    v6 = v23;
    goto LABEL_53;
  }
  v47 = 0;
  *(_OWORD *)v46 = 0;
  v49 = 0;
  v50 = 0;
  v48 = 0;
  v66 = 0;
  v25 = StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Get(&v39, v22, v46, &v66);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2CB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
      (const char *)(unsigned int)v25,
      (int)v35);
    StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46);
    goto LABEL_34;
  }
  v26 = 0;
  while ( v66 )
  {
    v58 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v59 = 0;
    v60 = 0;
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageExtension WHERE _CachePackageExt"
                                                "ensionID=? LIMIT 1);",
            0,
            v46[0],
            (__int64)&v66,
            v38);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
        (const char *)(unsigned int)v27,
        v37);
      v31 = 719;
      goto LABEL_50;
    }
    if ( !v66 )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v46[0], v29);
      if ( v30 < 0 )
      {
        v31 = 724;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageextension.cpp",
          (const char *)(unsigned int)v30,
          v37);
        StateRepository::Entity::CachePackageExtension::~CachePackageExtension((StateRepository::Entity::CachePackageExtension *)&v58);
        StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46);
        v32 = v39;
        v39 = 0;
        if ( v32 )
          SRCacheContext_Close(v32);
        v6 = v30;
        goto LABEL_53;
      }
      ++v26;
      ++v12;
    }
    ++v40;
    v30 = StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Get(&v39, v28, v46, &v66);
    if ( v30 < 0 )
    {
      v31 = 726;
      goto LABEL_50;
    }
    StateRepository::Entity::CachePackageExtension::~CachePackageExtension((StateRepository::Entity::CachePackageExtension *)&v58);
  }
  StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow((StateRepository::Cache::Entity::PackageExtension_NoThrow *)v46);
  v33 = v39;
  v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackageExtension",
      v26,
      *(__int64 *)v43);
  *v68 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x18014b920  mov     [rsp-8+arg_18], r9
0x18014b925  mov     [rsp-8+arg_8], rdx
0x18014b92a  push    rbp
0x18014b92b  push    rbx
0x18014b92c  push    rsi
0x18014b92d  push    rdi
0x18014b92e  push    r12
0x18014b930  push    r14
0x18014b932  push    r15
0x18014b934  lea     rbp, [rsp-70h]
0x18014b939  sub     rsp, 170h
0x18014b940  xor     r15d, r15d
0x18014b943  mov     rsi, rdx
0x18014b946  mov     r12, rcx
0x18014b949  cmp     [rcx], r15
0x18014b94c  jz      loc_18014BE4E
0x18014b952  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18014b957  test    al, al
0x18014b959  jz      short loc_18014B96A
0x18014b95b  mov     ebx, 8067000Bh
0x18014b960  mov     edx, 292h
0x18014b965  jmp     loc_18014BE58
0x18014b96a  cmp     [rsi], r15
0x18014b96d  jz      loc_18014BE47
0x18014b973  lea     rdx, [rsp+1A0h+var_158]; struct StateRepository::Statement *
0x18014b978  mov     qword ptr [rsp+1A0h+var_150], r15
0x18014b97d  mov     rcx, r12; struct StateRepository::Database *
0x18014b980  mov     [rsp+1A0h+var_148], r15
0x18014b985  mov     [rsp+1A0h+var_158], r15
0x18014b98a  call    ?Find@CachePackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageExtension::Find(StateRepository::Database &,StateRepository::Statement &)
0x18014b98f  mov     ebx, eax
0x18014b991  test    eax, eax
0x18014b993  jns     short loc_18014B9B5
0x18014b995  mov     rcx, [rbp+0A8h]; this
0x18014b99c  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014b9a3  mov     r9d, eax; char *
0x18014b9a6  mov     edx, 29Eh; void *
0x18014b9ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014b9b0  jmp     loc_18014BB71
0x18014b9b5  xorps   xmm0, xmm0
0x18014b9b8  mov     [rbp+0A0h+var_120], r15
0x18014b9bc  xorps   xmm1, xmm1
0x18014b9bf  movdqa  xmmword ptr [rsp+1A0h+var_130], xmm0
0x18014b9c5  lea     r8, [rbp+0A0h+arg_0]; bool *
0x18014b9cc  movdqa  [rbp+0A0h+var_110], xmm0
0x18014b9d1  lea     rdx, [rsp+1A0h+var_130]; struct StateRepository::Entity::CachePackageExtension *
0x18014b9d6  movdqa  [rbp+0A0h+var_100], xmm1
0x18014b9db  lea     rcx, [rsp+1A0h+var_158]; this
0x18014b9e0  movdqa  [rbp+0A0h+var_F0], xmm0
0x18014b9e5  movdqa  [rbp+0A0h+var_E0], xmm1
0x18014b9ea  mov     [rbp+0A0h+var_118], r15
0x18014b9ee  mov     [rbp+0A0h+arg_0], r15b
0x18014b9f5  call    ?FindNext@CachePackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageExtension &,bool &)
0x18014b9fa  mov     ebx, eax
0x18014b9fc  test    eax, eax
0x18014b9fe  jns     short loc_18014BA2A
0x18014ba00  mov     rcx, [rbp+0A8h]; this
0x18014ba07  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014ba0e  mov     r9d, eax; char *
0x18014ba11  mov     edx, 2A1h; void *
0x18014ba16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014ba1b  lea     rcx, [rsp+1A0h+var_130]; this
0x18014ba20  call    ??1CachePackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageExtension::~CachePackageExtension(void)
0x18014ba25  jmp     loc_18014BB71
0x18014ba2a  mov     rbx, r15
0x18014ba2d  mov     rdi, r15
0x18014ba30  mov     r14, r15
0x18014ba33  cmp     [rbp+0A0h+arg_0], r15b
0x18014ba3a  jz      loc_18014BB80
0x18014ba40  mov     rdx, [rsp+1A0h+var_130]
0x18014ba45  lea     rax, [rbp+0A0h+arg_0]
0x18014ba4c  xorps   xmm0, xmm0
0x18014ba4f  mov     [rsp+1A0h+var_180], rax; int
0x18014ba54  xorps   xmm1, xmm1
0x18014ba57  movdqa  [rbp+0A0h+var_D0], xmm0
0x18014ba5c  lea     r9, [rbp+0A0h+var_D0]
0x18014ba60  movdqa  [rbp+0A0h+var_B0], xmm0
0x18014ba65  mov     rcx, rsi
0x18014ba68  movdqa  [rbp+0A0h+var_A0], xmm1
0x18014ba6d  mov     [rbp+0A0h+var_C0], 0
0x18014ba75  mov     [rbp+0A0h+var_B8], r15
0x18014ba79  call    ?Get@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18014ba7e  mov     esi, eax
0x18014ba80  test    eax, eax
0x18014ba82  js      loc_18014BB41
0x18014ba88  cmp     [rbp+0A0h+arg_0], r15b
0x18014ba8f  jz      short loc_18014BAD9
0x18014ba91  lea     r8, [rsp+1A0h+var_140]; unsigned __int64 *
0x18014ba96  mov     [rsp+1A0h+var_140], r15
0x18014ba9b  lea     rdx, [rbp+0A0h+var_D0]; struct StateRepository::Cache::Entity::PackageExtension_NoThrow *
0x18014ba9f  lea     rcx, [rsp+1A0h+var_130]; struct StateRepository::Entity::CachePackageExtension *
0x18014baa4  call    ?Cache_Check@CachePackageExtension@Entity@StateRepository@@CAJAEBV123@AEBVPackageExtension_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageExtension::Cache_Check(StateRepository::Entity::CachePackageExtension const &,StateRepository::Cache::Entity::PackageExtension_NoThrow const &,unsigned __int64 &)
0x18014baa9  mov     esi, eax
0x18014baab  test    eax, eax
0x18014baad  js      short loc_18014BB2C
0x18014baaf  mov     r15, [rsp+1A0h+var_140]
0x18014bab4  test    r15, r15
0x18014bab7  jz      short loc_18014BAD1
0x18014bab9  mov     rdx, [rsp+1A0h+var_130]; __int64
0x18014babe  lea     rcx, [rsp+1A0h+var_150]; this
0x18014bac3  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18014bac8  mov     esi, eax
0x18014baca  test    eax, eax
0x18014bacc  js      short loc_18014BB25
0x18014bace  add     rbx, r15
0x18014bad1  inc     r14
0x18014bad4  xor     r15d, r15d
0x18014bad7  jmp     short loc_18014BAF1
0x18014bad9  mov     rdx, [rsp+1A0h+var_130]; __int64
0x18014bade  lea     rcx, [rsp+1A0h+var_150]; this
0x18014bae3  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18014bae8  mov     esi, eax
0x18014baea  test    eax, eax
0x18014baec  js      short loc_18014BB3A
0x18014baee  inc     rbx
0x18014baf1  lea     r8, [rbp+0A0h+arg_0]; bool *
0x18014baf8  lea     rdx, [rsp+1A0h+var_130]; struct StateRepository::Entity::CachePackageExtension *
0x18014bafd  lea     rcx, [rsp+1A0h+var_158]; this
0x18014bb02  call    ?FindNext@CachePackageExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageExtension &,bool &)
0x18014bb07  mov     esi, eax
0x18014bb09  test    eax, eax
0x18014bb0b  js      short loc_18014BB33
0x18014bb0d  inc     rdi
0x18014bb10  lea     rcx, [rbp+0A0h+var_D0]; this
0x18014bb14  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18014bb19  mov     rsi, [rbp+0A0h+arg_8]
0x18014bb20  jmp     loc_18014BA33
0x18014bb25  mov     edx, 2AFh
0x18014bb2a  jmp     short loc_18014BB46
0x18014bb2c  mov     edx, 2ABh
0x18014bb31  jmp     short loc_18014BB46
0x18014bb33  mov     edx, 2B7h
0x18014bb38  jmp     short loc_18014BB46
0x18014bb3a  mov     edx, 2B5h
0x18014bb3f  jmp     short loc_18014BB46
0x18014bb41  mov     edx, 2A6h; void *
0x18014bb46  mov     rcx, [rbp+0A8h]; this
0x18014bb4d  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014bb54  mov     r9d, esi; char *
0x18014bb57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bb5c  lea     rcx, [rbp+0A0h+var_D0]; this
0x18014bb60  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18014bb65  lea     rcx, [rsp+1A0h+var_130]; this
0x18014bb6a  call    ??1CachePackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageExtension::~CachePackageExtension(void)
0x18014bb6f  mov     ebx, esi
0x18014bb71  lea     rcx, [rsp+1A0h+var_158]; this
0x18014bb76  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18014bb7b  jmp     loc_18014BDD3
0x18014bb80  sub     rdi, r14
0x18014bb83  jz      short loc_18014BBAE
0x18014bb85  test    cs:byte_1804DF881, 20h
0x18014bb8c  jz      short loc_18014BBAE
0x18014bb8e  mov     rax, qword ptr [rsp+1A0h+var_150]
0x18014bb93  lea     r8, aCachepackageex; "CachePackageExtension"
0x18014bb9a  mov     r9, rdi
0x18014bb9d  mov     [rsp+1A0h+var_180], rax; int
0x18014bba2  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18014bba9  call    McTemplateU0sxs_EventWriteTransfer
0x18014bbae  lea     rcx, [rsp+1A0h+var_130]; this
0x18014bbb3  call    ??1CachePackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageExtension::~CachePackageExtension(void)
0x18014bbb8  lea     rcx, [rsp+1A0h+var_158]; this
0x18014bbbd  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18014bbc2  lea     rcx, [rsp+1A0h+var_150]; this
0x18014bbc7  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18014bbcc  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18014bbcf  mov     [rsp+1A0h+var_170], r15
0x18014bbd4  lea     rcx, [rsp+1A0h+var_170]; this
0x18014bbd9  mov     [rsp+1A0h+var_168], r15d
0x18014bbde  mov     [rsp+1A0h+var_160], r15
0x18014bbe3  call    ?Open@PackageExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18014bbe8  mov     edi, eax
0x18014bbea  test    eax, eax
0x18014bbec  jns     short loc_18014BC40
0x18014bbee  mov     rcx, [rbp+0A8h]; this
0x18014bbf5  lea     r8, aOnecoreBaseApp_151; "onecore\\base\\appmodel\\StateRepositor"...
0x18014bbfc  mov     r9d, eax; char *
0x18014bbff  mov     edx, 375h; void *
0x18014bc04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bc09  mov     rcx, [rbp+0A8h]; this
0x18014bc10  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014bc17  mov     r9d, edi; char *
0x18014bc1a  mov     edx, 2C8h; void *
0x18014bc1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bc24  mov     rcx, [rsp+1A0h+var_170]
0x18014bc29  mov     [rsp+1A0h+var_170], r15
0x18014bc2e  test    rcx, rcx
0x18014bc31  jz      short loc_18014BC39
0x18014bc33  call    cs:__imp_SRCacheContext_Close
0x18014bc39  mov     ebx, edi
0x18014bc3b  jmp     loc_18014BDD3
0x18014bc40  xorps   xmm0, xmm0
0x18014bc43  mov     [rbp+0A0h+var_120], 0
0x18014bc4b  xorps   xmm1, xmm1
0x18014bc4e  movdqa  xmmword ptr [rsp+1A0h+var_130], xmm0
0x18014bc54  lea     r9, [rbp+0A0h+arg_0]
0x18014bc5b  movdqa  [rbp+0A0h+var_110], xmm0
0x18014bc60  lea     r8, [rsp+1A0h+var_130]
0x18014bc65  movdqa  [rbp+0A0h+var_100], xmm1
0x18014bc6a  lea     rcx, [rsp+1A0h+var_170]
0x18014bc6f  mov     [rbp+0A0h+var_118], r15
0x18014bc73  mov     [rbp+0A0h+arg_0], r15b
0x18014bc7a  call    ?Get@PackageExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18014bc7f  mov     edi, eax
0x18014bc81  test    eax, eax
0x18014bc83  jns     short loc_18014BCAF
0x18014bc85  mov     rcx, [rbp+0A8h]; this
0x18014bc8c  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014bc93  mov     r9d, eax; char *
0x18014bc96  mov     edx, 2CBh; void *
0x18014bc9b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bca0  lea     rcx, [rsp+1A0h+var_130]; this
0x18014bca5  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18014bcaa  jmp     loc_18014BC24
0x18014bcaf  mov     rdi, r15
0x18014bcb2  cmp     [rbp+0A0h+arg_0], r15b
0x18014bcb9  jz      loc_18014BDE2
0x18014bcbf  mov     r9, [rsp+1A0h+var_130]; char *
0x18014bcc4  lea     rax, [rbp+0A0h+arg_0]
0x18014bccb  xorps   xmm0, xmm0
0x18014bcce  mov     [rsp+1A0h+var_180], rax; int
0x18014bcd3  xorps   xmm1, xmm1
0x18014bcd6  movdqa  [rbp+0A0h+var_90], xmm0
0x18014bcdb  xor     r8d, r8d; char *
0x18014bcde  movdqa  [rbp+0A0h+var_70], xmm0
0x18014bce3  lea     rdx, aSelectExistsSe_216; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x18014bcea  movdqa  [rbp+0A0h+var_60], xmm1
0x18014bcef  mov     rcx, r12; this
0x18014bcf2  movdqa  [rbp+0A0h+var_50], xmm0
0x18014bcf7  movdqa  [rbp+0A0h+var_40], xmm1
0x18014bcfc  mov     [rbp+0A0h+var_80], 0
0x18014bd04  mov     [rbp+0A0h+var_78], r15
0x18014bd08  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18014bd0d  mov     esi, eax
0x18014bd0f  test    eax, eax
0x18014bd11  js      short loc_18014BD73
0x18014bd13  cmp     [rbp+0A0h+arg_0], r15b
0x18014bd1a  jnz     short loc_18014BD37
0x18014bd1c  mov     rdx, [rsp+1A0h+var_130]; __int64
0x18014bd21  lea     rcx, [rsp+1A0h+var_150]; this
0x18014bd26  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18014bd2b  mov     esi, eax
0x18014bd2d  test    eax, eax
0x18014bd2f  js      short loc_18014BD65
0x18014bd31  inc     rdi
0x18014bd34  inc     rbx
0x18014bd37  inc     [rsp+1A0h+var_168]
0x18014bd3b  lea     r9, [rbp+0A0h+arg_0]
0x18014bd42  lea     r8, [rsp+1A0h+var_130]
0x18014bd47  lea     rcx, [rsp+1A0h+var_170]
0x18014bd4c  call    ?Get@PackageExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)
0x18014bd51  mov     esi, eax
0x18014bd53  test    eax, eax
0x18014bd55  js      short loc_18014BD6C
0x18014bd57  lea     rcx, [rbp+0A0h+var_90]; this
0x18014bd5b  call    ??1CachePackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageExtension::~CachePackageExtension(void)
0x18014bd60  jmp     loc_18014BCB2
0x18014bd65  mov     edx, 2D4h
0x18014bd6a  jmp     short loc_18014BD93
0x18014bd6c  mov     edx, 2D6h
0x18014bd71  jmp     short loc_18014BD93
0x18014bd73  mov     rcx, [rbp+0A8h]; this
0x18014bd7a  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014bd81  mov     r9d, esi; char *
0x18014bd84  mov     edx, 0F6h; void *
0x18014bd89  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bd8e  mov     edx, 2CFh; void *
0x18014bd93  mov     rcx, [rbp+0A8h]; this
0x18014bd9a  lea     r8, aOnecoreBaseApp_311; "onecore\\base\\appmodel\\staterepositor"...
0x18014bda1  mov     r9d, esi; char *
0x18014bda4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014bda9  lea     rcx, [rbp+0A0h+var_90]; this
0x18014bdad  call    ??1CachePackageExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageExtension::~CachePackageExtension(void)
0x18014bdb2  lea     rcx, [rsp+1A0h+var_130]; this
0x18014bdb7  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18014bdbc  mov     rcx, [rsp+1A0h+var_170]
0x18014bdc1  mov     [rsp+1A0h+var_170], r15
0x18014bdc6  test    rcx, rcx
0x18014bdc9  jz      short loc_18014BDD1
0x18014bdcb  call    cs:__imp_SRCacheContext_Close
0x18014bdd1  mov     ebx, esi
0x18014bdd3  lea     rcx, [rsp+1A0h+var_150]; this
0x18014bdd8  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18014bddd  jmp     loc_18014BE6E
0x18014bde2  lea     rcx, [rsp+1A0h+var_130]; this
0x18014bde7  call    ??1PackageExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageExtension_NoThrow::~PackageExtension_NoThrow(void)
0x18014bdec  mov     rcx, [rsp+1A0h+var_170]
0x18014bdf1  mov     [rsp+1A0h+var_170], r15
0x18014bdf6  test    rcx, rcx
0x18014bdf9  jz      short loc_18014BE01
0x18014bdfb  call    cs:__imp_SRCacheContext_Close
0x18014be01  test    rdi, rdi
0x18014be04  jz      short loc_18014BE2F
0x18014be06  test    cs:byte_1804DF881, 20h
0x18014be0d  jz      short loc_18014BE2F
0x18014be0f  mov     rax, qword ptr [rsp+1A0h+var_150]
0x18014be14  lea     r8, aCachepackageex; "CachePackageExtension"
0x18014be1b  mov     r9, rdi
0x18014be1e  mov     [rsp+1A0h+var_180], rax
0x18014be23  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x18014be2a  call    McTemplateU0sxs_EventWriteTransfer
  ... truncated ...
```
