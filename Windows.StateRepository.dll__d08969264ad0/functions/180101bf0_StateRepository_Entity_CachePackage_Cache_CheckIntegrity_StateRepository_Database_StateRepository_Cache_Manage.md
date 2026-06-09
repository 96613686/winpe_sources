# StateRepository::Entity::CachePackage::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180101bf0`
- end: `0x1801021b9`
- name: `?Cache_CheckIntegrity@CachePackage@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1481`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x18005db74`
- `0x18005e990`
- `0x180062cd8`
- `0x1800ae890`
- `0x1800b2e20`
- `0x180101bf0`
- `0x1801021c0`
- `0x18026544c`
- `0x180265bf8`
- `0x180266254`
- `0x18026631c`
- `0x18026647c`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101f27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180102102`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180102132`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180101f27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180102102`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180102132`

## string_xrefs

- `0x180101c6f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180101cec`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180101e41`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180101f04`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180101f98`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x1801020b1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x1801020d1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180102196`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackage.cpp`
- `0x180101ee9`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Package.hpp`
- `0x180101e87`: `CachePackage`
- `0x18010214b`: `CachePackage`
- `0x180101ff2`: `SELECT EXISTS(SELECT 1 FROM CachePackage WHERE _CachePackageID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackage::Cache_CheckIntegrity(
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
  __int64 v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rcx
  int v27; // eax
  __int64 v28; // rdi
  int v29; // eax
  __int64 v30; // rdx
  char v31; // r8
  int v32; // esi
  __int64 v33; // rdx
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // rcx
  bool *v41; // [rsp+20h] [rbp-E0h]
  int v42; // [rsp+20h] [rbp-E0h]
  int v43; // [rsp+20h] [rbp-E0h]
  bool *v44; // [rsp+28h] [rbp-D8h]
  __int64 v45; // [rsp+30h] [rbp-D0h] BYREF
  int v46; // [rsp+38h] [rbp-C8h]
  __int64 v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h] BYREF
  int v49[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v50; // [rsp+58h] [rbp-A8h]
  unsigned __int64 v51; // [rsp+60h] [rbp-A0h] BYREF
  char *v52[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  __int64 v55; // [rsp+A0h] [rbp-60h]
  __int64 v56; // [rsp+A8h] [rbp-58h]
  __int128 v57; // [rsp+B0h] [rbp-50h]
  __int128 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  int v60; // [rsp+E0h] [rbp-20h]
  __int64 v61; // [rsp+E8h] [rbp-18h]
  __int128 v62; // [rsp+F0h] [rbp-10h]
  __int128 v63; // [rsp+100h] [rbp+0h] BYREF
  __int64 v64; // [rsp+110h] [rbp+10h]
  __int128 v65; // [rsp+118h] [rbp+18h]
  __int64 v66; // [rsp+128h] [rbp+28h]
  __int64 v67; // [rsp+130h] [rbp+30h]
  __int64 v68; // [rsp+138h] [rbp+38h]
  __int128 v69; // [rsp+140h] [rbp+40h]
  int v70; // [rsp+150h] [rbp+50h]
  __int64 v71; // [rsp+158h] [rbp+58h]
  __int64 v72; // [rsp+160h] [rbp+60h]
  _OWORD v73[3]; // [rsp+170h] [rbp+70h] BYREF
  __int64 v74; // [rsp+1A0h] [rbp+A0h]
  __int64 v75; // [rsp+1A8h] [rbp+A8h]
  __int128 v76; // [rsp+1B0h] [rbp+B0h]
  __int128 v77; // [rsp+1C0h] [rbp+C0h]
  __int128 v78; // [rsp+1D0h] [rbp+D0h]
  int v79; // [rsp+1E0h] [rbp+E0h]
  __int64 v80; // [rsp+1E8h] [rbp+E8h]
  __int128 v81; // [rsp+1F0h] [rbp+F0h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+138h]
  bool v83; // [rsp+240h] [rbp+140h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v84; // [rsp+248h] [rbp+148h]
  _QWORD *v85; // [rsp+258h] [rbp+158h]

  v85 = a4;
  v84 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 1409;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 1410;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 1411;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v48 = 0;
  v8 = StateRepository::Entity::CachePackage::Find(a1, (struct StateRepository::Statement *)&v48);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v49);
    return v6;
  }
  v55 = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  v54 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v62 = 0;
  v56 = 0;
  v60 = 0;
  v61 = 0;
  v83 = 0;
  Next = StateRepository::Entity::CachePackage::FindNext(
           (struct StateRepository::Statement *)&v48,
           (struct StateRepository::Entity::CachePackage *)v52,
           &v83);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x591,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CachePackage::~CachePackage((StateRepository::Entity::CachePackage *)v52);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v83 )
  {
    v41 = &v83;
    v63 = 0;
    v69 = 0;
    v64 = 0;
    v65 = 0;
    v66 = 0;
    v67 = 0;
    v68 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    appended = StateRepository::Cache::Entity::Package_NoThrow::Get(v4, v52[0], v11, &v63);
    if ( appended < 0 )
    {
      v19 = 1430;
      goto LABEL_27;
    }
    if ( v83 )
    {
      v51 = 0;
      appended = StateRepository::Entity::CachePackage::Cache_Check(
                   (const struct StateRepository::Entity::CachePackage *)v52,
                   (const struct StateRepository::Cache::Entity::Package_NoThrow *)&v63,
                   &v51);
      if ( appended < 0 )
      {
        v19 = 1435;
        goto LABEL_27;
      }
      v18 = v51;
      if ( v51 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v17);
        if ( appended < 0 )
        {
          v19 = 1439;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
            (const char *)(unsigned int)appended,
            (int)&v83);
          StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
          StateRepository::Entity::CachePackage::~CachePackage((StateRepository::Entity::CachePackage *)v52);
          v6 = appended;
          goto LABEL_28;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v16);
      if ( appended < 0 )
      {
        v19 = 1445;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CachePackage::FindNext(
                 (struct StateRepository::Statement *)&v48,
                 (struct StateRepository::Entity::CachePackage *)v52,
                 &v83);
    if ( appended < 0 )
    {
      v19 = 1447;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)&v63);
    v4 = v84;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackage",
      v20,
      *(__int64 *)v49);
  StateRepository::Entity::CachePackage::~CachePackage((StateRepository::Entity::CachePackage *)v52);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
  StateRepository::TextA::Clear((StateRepository::TextA *)v49);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::PackageIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageIterator_NoThrow *)&v45,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x816,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5B8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
      (const char *)v23,
      v42);
LABEL_34:
    v26 = v45;
    v45 = 0;
    if ( v26 )
      SRCacheContext_Close(v26, v24, v25);
    v6 = v23;
    goto LABEL_53;
  }
  v53 = 0u;
  *(_OWORD *)v52 = 0;
  v57 = 0;
  v54 = 0u;
  v55 = 0;
  v56 = 0;
  LODWORD(v58) = 0;
  *((_QWORD *)&v58 + 1) = 0;
  *(_QWORD *)&v59 = 0;
  v83 = 0;
  v27 = StateRepository::Cache::Entity::PackageIterator_NoThrow::Get(&v45, v22, v52, &v83);
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BB,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v52);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v83 )
  {
    memset(v73, 0, sizeof(v73));
    v76 = 0;
    v77 = 0;
    v74 = 0;
    v78 = 0;
    v81 = 0;
    v75 = 0;
    v79 = 0;
    v80 = 0;
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackage WHERE _CachePackageID=? LIMIT 1);",
            0,
            v52[0],
            (__int64)&v83,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x431,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 1471;
      goto LABEL_50;
    }
    if ( !v83 )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v31);
      if ( v32 < 0 )
      {
        v33 = 1476;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackage.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CachePackage::~CachePackage((StateRepository::Entity::CachePackage *)v73);
        StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v52);
        v36 = v45;
        v45 = 0;
        if ( v36 )
          SRCacheContext_Close(v36, v34, v35);
        v6 = v32;
        goto LABEL_53;
      }
      ++v28;
      ++v12;
    }
    ++v46;
    v32 = StateRepository::Cache::Entity::PackageIterator_NoThrow::Get(&v45, v30, v52, &v83);
    if ( v32 < 0 )
    {
      v33 = 1478;
      goto LABEL_50;
    }
    StateRepository::Entity::CachePackage::~CachePackage((StateRepository::Entity::CachePackage *)v73);
  }
  StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow((StateRepository::Cache::Entity::Package_NoThrow *)v52);
  v39 = v45;
  v45 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackage",
      v28,
      *(__int64 *)v49);
  *v85 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v49);
  return 0;
}

```

## disassembly

```asm
0x180101bf0  mov     [rsp-8+arg_18], r9
0x180101bf5  mov     [rsp-8+arg_8], rdx
0x180101bfa  push    rbp
0x180101bfb  push    rbx
0x180101bfc  push    rsi
0x180101bfd  push    rdi
0x180101bfe  push    r12
0x180101c00  push    r14
0x180101c02  push    r15
0x180101c04  lea     rbp, [rsp-100h]
0x180101c0c  sub     rsp, 200h
0x180101c13  xor     r15d, r15d
0x180101c16  mov     rsi, rdx
0x180101c19  mov     r12, rcx
0x180101c1c  cmp     [rcx], r15
0x180101c1f  jz      loc_180102185
0x180101c25  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180101c2a  test    al, al
0x180101c2c  jz      short loc_180101C3D
0x180101c2e  mov     ebx, 8067000Bh
0x180101c33  mov     edx, 582h
0x180101c38  jmp     loc_18010218F
0x180101c3d  cmp     [rsi], r15
0x180101c40  jz      loc_18010217E
0x180101c46  lea     rdx, [rsp+230h+var_1E8]; struct StateRepository::Statement *
0x180101c4b  mov     qword ptr [rsp+230h+var_1E0], r15
0x180101c50  mov     rcx, r12; struct StateRepository::Database *
0x180101c53  mov     [rsp+230h+var_1D8], r15
0x180101c58  mov     [rsp+230h+var_1E8], r15
0x180101c5d  call    ?Find@CachePackage@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackage::Find(StateRepository::Database &,StateRepository::Statement &)
0x180101c62  mov     ebx, eax
0x180101c64  test    eax, eax
0x180101c66  jns     short loc_180101C88
0x180101c68  mov     rcx, [rbp+138h]; this
0x180101c6f  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x180101c76  mov     r9d, eax; char *
0x180101c79  mov     edx, 58Eh; void *
0x180101c7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101c83  jmp     loc_180101E65
0x180101c88  xorps   xmm0, xmm0
0x180101c8b  mov     [rbp+130h+var_190], r15
0x180101c8f  xorps   xmm1, xmm1
0x180101c92  movdqa  xmmword ptr [rsp+230h+var_1C0], xmm0
0x180101c98  lea     r8, [rbp+130h+arg_0]; bool *
0x180101c9f  movdqa  [rbp+130h+var_1B0], xmm1
0x180101ca4  lea     rdx, [rsp+230h+var_1C0]; struct StateRepository::Entity::CachePackage *
0x180101ca9  movdqa  [rbp+130h+var_1A0], xmm0
0x180101cae  lea     rcx, [rsp+230h+var_1E8]; struct StateRepository::Statement *
0x180101cb3  movdqa  [rbp+130h+var_180], xmm0
0x180101cb8  movdqa  [rbp+130h+var_170], xmm1
0x180101cbd  movdqa  [rbp+130h+var_160], xmm0
0x180101cc2  movdqa  [rbp+130h+var_140], xmm0
0x180101cc7  mov     [rbp+130h+var_188], r15
0x180101ccb  mov     [rbp+130h+var_150], r15d
0x180101ccf  mov     [rbp+130h+var_148], r15
0x180101cd3  mov     [rbp+130h+arg_0], r15b
0x180101cda  call    ?FindNext@CachePackage@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackage::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackage &,bool &)
0x180101cdf  mov     ebx, eax
0x180101ce1  test    eax, eax
0x180101ce3  jns     short loc_180101D0F
0x180101ce5  mov     rcx, [rbp+138h]; this
0x180101cec  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x180101cf3  mov     r9d, eax; char *
0x180101cf6  mov     edx, 591h; void *
0x180101cfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101d00  lea     rcx, [rsp+230h+var_1C0]; this
0x180101d05  call    ??1CachePackage@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackage::~CachePackage(void)
0x180101d0a  jmp     loc_180101E65
0x180101d0f  mov     rbx, r15
0x180101d12  mov     rdi, r15
0x180101d15  mov     r14, r15
0x180101d18  cmp     [rbp+130h+arg_0], r15b
0x180101d1f  jz      loc_180101E74
0x180101d25  mov     rdx, [rsp+230h+var_1C0]
0x180101d2a  lea     rax, [rbp+130h+arg_0]
0x180101d31  xorps   xmm0, xmm0
0x180101d34  mov     [rsp+230h+var_210], rax; int
0x180101d39  xorps   xmm1, xmm1
0x180101d3c  movdqa  [rbp+130h+var_130], xmm0
0x180101d41  lea     r9, [rbp+130h+var_130]
0x180101d45  movdqa  [rbp+130h+var_F0], xmm0
0x180101d4a  mov     rcx, rsi
0x180101d4d  mov     [rbp+130h+var_120], r15
0x180101d51  movups  [rbp+130h+var_118], xmm1
0x180101d55  mov     [rbp+130h+var_108], r15
0x180101d59  mov     [rbp+130h+var_100], r15
0x180101d5d  mov     [rbp+130h+var_F8], r15
0x180101d61  mov     [rbp+130h+var_E0], r15d
0x180101d65  mov     [rbp+130h+var_D8], r15
0x180101d69  mov     [rbp+130h+var_D0], r15
0x180101d6d  call    ?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180101d72  mov     esi, eax
0x180101d74  test    eax, eax
0x180101d76  js      loc_180101E35
0x180101d7c  cmp     [rbp+130h+arg_0], r15b
0x180101d83  jz      short loc_180101DCD
0x180101d85  lea     r8, [rsp+230h+var_1D0]; unsigned __int64 *
0x180101d8a  mov     [rsp+230h+var_1D0], r15
0x180101d8f  lea     rdx, [rbp+130h+var_130]; struct StateRepository::Cache::Entity::Package_NoThrow *
0x180101d93  lea     rcx, [rsp+230h+var_1C0]; struct StateRepository::Entity::CachePackage *
0x180101d98  call    ?Cache_Check@CachePackage@Entity@StateRepository@@CAJAEBV123@AEBVPackage_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackage::Cache_Check(StateRepository::Entity::CachePackage const &,StateRepository::Cache::Entity::Package_NoThrow const &,unsigned __int64 &)
0x180101d9d  mov     esi, eax
0x180101d9f  test    eax, eax
0x180101da1  js      short loc_180101E20
0x180101da3  mov     r15, [rsp+230h+var_1D0]
0x180101da8  test    r15, r15
0x180101dab  jz      short loc_180101DC5
0x180101dad  mov     rdx, [rsp+230h+var_1C0]; __int64
0x180101db2  lea     rcx, [rsp+230h+var_1E0]; this
0x180101db7  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180101dbc  mov     esi, eax
0x180101dbe  test    eax, eax
0x180101dc0  js      short loc_180101E19
0x180101dc2  add     rbx, r15
0x180101dc5  inc     r14
0x180101dc8  xor     r15d, r15d
0x180101dcb  jmp     short loc_180101DE5
0x180101dcd  mov     rdx, [rsp+230h+var_1C0]; __int64
0x180101dd2  lea     rcx, [rsp+230h+var_1E0]; this
0x180101dd7  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180101ddc  mov     esi, eax
0x180101dde  test    eax, eax
0x180101de0  js      short loc_180101E2E
0x180101de2  inc     rbx
0x180101de5  lea     r8, [rbp+130h+arg_0]; bool *
0x180101dec  lea     rdx, [rsp+230h+var_1C0]; struct StateRepository::Entity::CachePackage *
0x180101df1  lea     rcx, [rsp+230h+var_1E8]; struct StateRepository::Statement *
0x180101df6  call    ?FindNext@CachePackage@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackage::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackage &,bool &)
0x180101dfb  mov     esi, eax
0x180101dfd  test    eax, eax
0x180101dff  js      short loc_180101E27
0x180101e01  inc     rdi
0x180101e04  lea     rcx, [rbp+130h+var_130]; this
0x180101e08  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180101e0d  mov     rsi, [rbp+130h+arg_8]
0x180101e14  jmp     loc_180101D18
0x180101e19  mov     edx, 59Fh
0x180101e1e  jmp     short loc_180101E3A
0x180101e20  mov     edx, 59Bh
0x180101e25  jmp     short loc_180101E3A
0x180101e27  mov     edx, 5A7h
0x180101e2c  jmp     short loc_180101E3A
0x180101e2e  mov     edx, 5A5h
0x180101e33  jmp     short loc_180101E3A
0x180101e35  mov     edx, 596h; void *
0x180101e3a  mov     rcx, [rbp+138h]; this
0x180101e41  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x180101e48  mov     r9d, esi; char *
0x180101e4b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101e50  lea     rcx, [rbp+130h+var_130]; this
0x180101e54  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180101e59  lea     rcx, [rsp+230h+var_1C0]; this
0x180101e5e  call    ??1CachePackage@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackage::~CachePackage(void)
0x180101e63  mov     ebx, esi
0x180101e65  lea     rcx, [rsp+230h+var_1E8]; this
0x180101e6a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180101e6f  jmp     loc_18010210A
0x180101e74  sub     rdi, r14
0x180101e77  jz      short loc_180101EA2
0x180101e79  test    cs:byte_1804DF881, 20h
0x180101e80  jz      short loc_180101EA2
0x180101e82  mov     rax, qword ptr [rsp+230h+var_1E0]
0x180101e87  lea     r8, aCachepackage; "CachePackage"
0x180101e8e  mov     r9, rdi
0x180101e91  mov     [rsp+230h+var_210], rax; int
0x180101e96  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180101e9d  call    McTemplateU0sxs_EventWriteTransfer
0x180101ea2  lea     rcx, [rsp+230h+var_1C0]; this
0x180101ea7  call    ??1CachePackage@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackage::~CachePackage(void)
0x180101eac  lea     rcx, [rsp+230h+var_1E8]; this
0x180101eb1  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180101eb6  lea     rcx, [rsp+230h+var_1E0]; this
0x180101ebb  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180101ec0  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180101ec3  mov     [rsp+230h+var_200], r15
0x180101ec8  lea     rcx, [rsp+230h+var_200]; this
0x180101ecd  mov     [rsp+230h+var_1F8], r15d
0x180101ed2  mov     [rsp+230h+var_1F0], r15
0x180101ed7  call    ?Open@PackageIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180101edc  mov     edi, eax
0x180101ede  test    eax, eax
0x180101ee0  jns     short loc_180101F34
0x180101ee2  mov     rcx, [rbp+138h]; this
0x180101ee9  lea     r8, aOnecoreBaseApp_484; "onecore\\base\\appmodel\\StateRepositor"...
0x180101ef0  mov     r9d, eax; char *
0x180101ef3  mov     edx, 816h; void *
0x180101ef8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101efd  mov     rcx, [rbp+138h]; this
0x180101f04  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x180101f0b  mov     r9d, edi; char *
0x180101f0e  mov     edx, 5B8h; void *
0x180101f13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101f18  mov     rcx, [rsp+230h+var_200]
0x180101f1d  mov     [rsp+230h+var_200], r15
0x180101f22  test    rcx, rcx
0x180101f25  jz      short loc_180101F2D
0x180101f27  call    cs:__imp_SRCacheContext_Close
0x180101f2d  mov     ebx, edi
0x180101f2f  jmp     loc_18010210A
0x180101f34  xorps   xmm0, xmm0
0x180101f37  mov     qword ptr [rbp+130h+var_1B0], r15
0x180101f3b  lea     r9, [rbp+130h+arg_0]
0x180101f42  movdqa  xmmword ptr [rsp+230h+var_1C0], xmm0
0x180101f48  lea     r8, [rsp+230h+var_1C0]
0x180101f4d  movdqa  [rbp+130h+var_180], xmm0
0x180101f52  lea     rcx, [rsp+230h+var_200]
0x180101f57  mov     qword ptr [rbp+130h+var_1B0+8], 0
0x180101f5f  mov     qword ptr [rbp+130h+var_1A0], 0
0x180101f67  mov     qword ptr [rbp+130h+var_1A0+8], r15
0x180101f6b  mov     [rbp+130h+var_190], r15
0x180101f6f  mov     [rbp+130h+var_188], r15
0x180101f73  mov     dword ptr [rbp+130h+var_170], r15d
0x180101f77  mov     qword ptr [rbp+130h+var_170+8], r15
0x180101f7b  mov     qword ptr [rbp+130h+var_160], r15
0x180101f7f  mov     [rbp+130h+arg_0], r15b
0x180101f86  call    ?Get@PackageIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180101f8b  mov     edi, eax
0x180101f8d  test    eax, eax
0x180101f8f  jns     short loc_180101FBB
0x180101f91  mov     rcx, [rbp+138h]; this
0x180101f98  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x180101f9f  mov     r9d, eax; char *
0x180101fa2  mov     edx, 5BBh; void *
0x180101fa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180101fac  lea     rcx, [rsp+230h+var_1C0]; this
0x180101fb1  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x180101fb6  jmp     loc_180101F18
0x180101fbb  mov     rdi, r15
0x180101fbe  cmp     [rbp+130h+arg_0], r15b
0x180101fc5  jz      loc_180102119
0x180101fcb  mov     r9, [rsp+230h+var_1C0]; char *
0x180101fd0  lea     rax, [rbp+130h+arg_0]
0x180101fd7  xorps   xmm0, xmm0
0x180101fda  mov     [rsp+230h+var_210], rax; int
0x180101fdf  xorps   xmm1, xmm1
0x180101fe2  movdqa  [rbp+130h+var_C0], xmm0
0x180101fe7  xor     r8d, r8d; char *
0x180101fea  movdqa  [rbp+130h+var_B0], xmm1
0x180101ff2  lea     rdx, aSelectExistsSe_245; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x180101ff9  movdqa  [rbp+130h+var_80], xmm0
0x180102001  mov     rcx, r12; this
0x180102004  movdqa  [rbp+130h+var_70], xmm1
0x18010200c  movups  [rbp+130h+var_A0], xmm0
0x180102013  mov     [rbp+130h+var_90], r15
0x18010201a  movdqa  [rbp+130h+var_60], xmm0
0x180102022  movdqa  [rbp+130h+var_40], xmm0
0x18010202a  mov     [rbp+130h+var_88], r15
0x180102031  mov     [rbp+130h+var_50], r15d
0x180102038  mov     [rbp+130h+var_48], r15
0x18010203f  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180102044  mov     esi, eax
0x180102046  test    eax, eax
0x180102048  js      short loc_1801020AA
0x18010204a  cmp     [rbp+130h+arg_0], r15b
0x180102051  jnz     short loc_18010206E
0x180102053  mov     rdx, [rsp+230h+var_1C0]; __int64
0x180102058  lea     rcx, [rsp+230h+var_1E0]; this
0x18010205d  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180102062  mov     esi, eax
0x180102064  test    eax, eax
0x180102066  js      short loc_18010209C
0x180102068  inc     rdi
0x18010206b  inc     rbx
0x18010206e  inc     [rsp+230h+var_1F8]
0x180102072  lea     r9, [rbp+130h+arg_0]
0x180102079  lea     r8, [rsp+230h+var_1C0]
0x18010207e  lea     rcx, [rsp+230h+var_200]
0x180102083  call    ?Get@PackageIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Package_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageIterator_NoThrow::Get(StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)
0x180102088  mov     esi, eax
0x18010208a  test    eax, eax
0x18010208c  js      short loc_1801020A3
0x18010208e  lea     rcx, [rbp+130h+var_C0]; this
0x180102092  call    ??1CachePackage@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackage::~CachePackage(void)
0x180102097  jmp     loc_180101FBE
0x18010209c  mov     edx, 5C4h
0x1801020a1  jmp     short loc_1801020CA
0x1801020a3  mov     edx, 5C6h
0x1801020a8  jmp     short loc_1801020CA
0x1801020aa  mov     rcx, [rbp+138h]; this
0x1801020b1  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x1801020b8  mov     r9d, esi; char *
0x1801020bb  mov     edx, 431h; void *
0x1801020c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801020c5  mov     edx, 5BFh; void *
0x1801020ca  mov     rcx, [rbp+138h]; this
0x1801020d1  lea     r8, aOnecoreBaseApp_233; "onecore\\base\\appmodel\\staterepositor"...
0x1801020d8  mov     r9d, esi; char *
0x1801020db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801020e0  lea     rcx, [rbp+130h+var_C0]; this
0x1801020e4  call    ??1CachePackage@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackage::~CachePackage(void)
0x1801020e9  lea     rcx, [rsp+230h+var_1C0]; this
0x1801020ee  call    ??1Package_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Package_NoThrow::~Package_NoThrow(void)
0x1801020f3  mov     rcx, [rsp+230h+var_200]
0x1801020f8  mov     [rsp+230h+var_200], r15
0x1801020fd  test    rcx, rcx
0x180102100  jz      short loc_180102108
0x180102102  call    cs:__imp_SRCacheContext_Close
0x180102108  mov     ebx, esi
0x18010210a  lea     rcx, [rsp+230h+var_1E0]; this
0x18010210f  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
  ... truncated ...
```
