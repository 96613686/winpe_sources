# StateRepository::Entity::CachePackageProperty::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180189840`
- end: `0x180189d6e`
- name: `?Cache_CheckIntegrity@CachePackageProperty@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1326`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x180022d58`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800ae890`
- `0x1800becac`
- `0x1800bf0e4`
- `0x180189840`
- `0x180189d74`
- `0x18026544c`
- `0x180271120`
- `0x180271438`
- `0x180271500`
- `0x1802715e0`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189b38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189cba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189cea`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189b38`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189cba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180189cea`

## string_xrefs

- `0x1801898b9`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x18018991d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189a58`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189b15`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189b8b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189c6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189c89`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189d4b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackageproperty.cpp`
- `0x180189afd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageProperty.hpp`
- `0x180189a9e`: `CachePackageProperty`
- `0x180189d03`: `CachePackageProperty`
- `0x180189bda`: `SELECT EXISTS(SELECT 1 FROM CachePackageProperty WHERE _CachePackagePropertyID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageProperty::Cache_CheckIntegrity(
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
  char *v45[2]; // [rsp+60h] [rbp-A0h] BYREF
  int v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  __int64 v48; // [rsp+80h] [rbp-80h]
  __int64 v49; // [rsp+88h] [rbp-78h]
  __int128 v50; // [rsp+90h] [rbp-70h]
  __int64 v51; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v52; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-48h] BYREF
  int v54; // [rsp+C8h] [rbp-38h]
  __int64 v55; // [rsp+D0h] [rbp-30h]
  int v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  int v58; // [rsp+E8h] [rbp-18h]
  __int128 v59; // [rsp+F0h] [rbp-10h] BYREF
  int v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  __int64 v62; // [rsp+110h] [rbp+10h]
  int v63; // [rsp+118h] [rbp+18h]
  __int128 v64; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  bool v67; // [rsp+180h] [rbp+80h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v68; // [rsp+188h] [rbp+88h]
  _QWORD *v69; // [rsp+198h] [rbp+98h]

  v69 = a4;
  v68 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 543;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 544;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 545;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v43 = 0;
  v44 = 0;
  v42 = 0;
  v8 = StateRepository::Entity::CachePackageProperty::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v43);
    return v6;
  }
  v46 = 0;
  *(_OWORD *)v45 = 0;
  v50 = 0;
  v47 = 0;
  v48 = 0;
  LODWORD(v49) = 0;
  v51 = 0;
  v67 = 0;
  Next = StateRepository::Entity::CachePackageProperty::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CachePackageProperty *)v45,
           &v67);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x22F,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Entity::CachePackageProperty::~CachePackageProperty((StateRepository::Entity::CachePackageProperty *)v45);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v67 )
  {
    v35 = &v67;
    v54 = 0;
    v55 = 0;
    v53 = 0;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    appended = StateRepository::Cache::Entity::PackageProperty_NoThrow::Get(v4, v45[0], v11, &v53);
    if ( appended < 0 )
    {
      v19 = 564;
      goto LABEL_27;
    }
    if ( v67 )
    {
      v52 = 0;
      appended = StateRepository::Entity::CachePackageProperty::Cache_Check(
                   (const struct StateRepository::Entity::CachePackageProperty *)v45,
                   (const struct StateRepository::Cache::Entity::PackageProperty_NoThrow *)&v53,
                   &v52);
      if ( appended < 0 )
      {
        v19 = 569;
        goto LABEL_27;
      }
      v18 = v52;
      if ( v52 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v17);
        if ( appended < 0 )
        {
          v19 = 573;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
            (const char *)(unsigned int)appended,
            (int)&v67);
          StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow((StateRepository::Cache::Entity::PackageProperty_NoThrow *)&v53);
          StateRepository::Entity::CachePackageProperty::~CachePackageProperty((StateRepository::Entity::CachePackageProperty *)v45);
          v6 = appended;
          goto LABEL_28;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v16);
      if ( appended < 0 )
      {
        v19 = 579;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CachePackageProperty::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CachePackageProperty *)v45,
                 &v67);
    if ( appended < 0 )
    {
      v19 = 581;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow((StateRepository::Cache::Entity::PackageProperty_NoThrow *)&v53);
    v4 = v68;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageProperty",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CachePackageProperty::~CachePackageProperty((StateRepository::Entity::CachePackageProperty *)v45);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AD,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageProperty.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x256,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
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
  v46 = 0;
  v47 = 0;
  LODWORD(v48) = 0;
  v49 = 0;
  *(_OWORD *)v45 = 0;
  LODWORD(v50) = 0;
  v67 = 0;
  v25 = StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Get(&v39, v22, v45, &v67);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x259,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
      (const char *)(unsigned int)v25,
      (int)v35);
    StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow((StateRepository::Cache::Entity::PackageProperty_NoThrow *)v45);
    goto LABEL_34;
  }
  v26 = 0;
  while ( v67 )
  {
    v59 = 0;
    v64 = 0;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v63 = 0;
    v65 = 0;
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageProperty WHERE _CachePackageProp"
                                                "ertyID=? LIMIT 1);",
            0,
            v45[0],
            (__int64)&v67,
            v38);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
        (const char *)(unsigned int)v27,
        v37);
      v31 = 605;
      goto LABEL_50;
    }
    if ( !v67 )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v29);
      if ( v30 < 0 )
      {
        v31 = 610;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackageproperty.cpp",
          (const char *)(unsigned int)v30,
          v37);
        StateRepository::Entity::CachePackageProperty::~CachePackageProperty((StateRepository::Entity::CachePackageProperty *)&v59);
        StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow((StateRepository::Cache::Entity::PackageProperty_NoThrow *)v45);
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
    v30 = StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Get(&v39, v28, v45, &v67);
    if ( v30 < 0 )
    {
      v31 = 612;
      goto LABEL_50;
    }
    StateRepository::Entity::CachePackageProperty::~CachePackageProperty((StateRepository::Entity::CachePackageProperty *)&v59);
  }
  StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow((StateRepository::Cache::Entity::PackageProperty_NoThrow *)v45);
  v33 = v39;
  v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackageProperty",
      v26,
      *(__int64 *)v43);
  *v69 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x180189840  mov     [rsp-8+arg_18], r9
0x180189845  mov     [rsp-8+arg_8], rdx
0x18018984a  push    rbp
0x18018984b  push    rbx
0x18018984c  push    rsi
0x18018984d  push    rdi
0x18018984e  push    r12
0x180189850  push    r14
0x180189852  push    r15
0x180189854  lea     rbp, [rsp-40h]
0x180189859  sub     rsp, 140h
0x180189860  xor     r15d, r15d
0x180189863  mov     rsi, rdx
0x180189866  mov     r12, rcx
0x180189869  cmp     [rcx], r15
0x18018986c  jz      loc_180189D3D
0x180189872  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180189877  test    al, al
0x180189879  jz      short loc_18018988A
0x18018987b  mov     ebx, 8067000Bh
0x180189880  mov     edx, 220h
0x180189885  jmp     loc_180189D47
0x18018988a  cmp     [rsi], r15
0x18018988d  jz      loc_180189D36
0x180189893  lea     rdx, [rsp+170h+var_128]; struct StateRepository::Statement *
0x180189898  mov     qword ptr [rsp+170h+var_120], r15
0x18018989d  mov     rcx, r12; struct StateRepository::Database *
0x1801898a0  mov     [rsp+170h+var_118], r15
0x1801898a5  mov     [rsp+170h+var_128], r15
0x1801898aa  call    ?Find@CachePackageProperty@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageProperty::Find(StateRepository::Database &,StateRepository::Statement &)
0x1801898af  mov     ebx, eax
0x1801898b1  test    eax, eax
0x1801898b3  jns     short loc_1801898D2
0x1801898b5  mov     rcx, [rbp+78h]; this
0x1801898b9  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x1801898c0  mov     r9d, eax; char *
0x1801898c3  mov     edx, 22Ch; void *
0x1801898c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801898cd  jmp     loc_180189A7C
0x1801898d2  xorps   xmm0, xmm0
0x1801898d5  mov     [rsp+170h+var_100], r15d
0x1801898da  lea     r8, [rbp+70h+arg_0]; bool *
0x1801898e1  movdqa  xmmword ptr [rsp+170h+var_110], xmm0
0x1801898e7  lea     rdx, [rsp+170h+var_110]; struct StateRepository::Entity::CachePackageProperty *
0x1801898ec  movdqa  [rbp+70h+var_E0], xmm0
0x1801898f1  lea     rcx, [rsp+170h+var_128]; this
0x1801898f6  mov     [rsp+170h+var_F8], r15
0x1801898fb  mov     [rbp+70h+var_F0], r15
0x1801898ff  mov     dword ptr [rbp+70h+var_E8], r15d
0x180189903  mov     [rbp+70h+var_D0], r15
0x180189907  mov     [rbp+70h+arg_0], r15b
0x18018990e  call    ?FindNext@CachePackageProperty@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageProperty::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageProperty &,bool &)
0x180189913  mov     ebx, eax
0x180189915  test    eax, eax
0x180189917  jns     short loc_180189940
0x180189919  mov     rcx, [rbp+78h]; this
0x18018991d  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189924  mov     r9d, eax; char *
0x180189927  mov     edx, 22Fh; void *
0x18018992c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189931  lea     rcx, [rsp+170h+var_110]; this
0x180189936  call    ??1CachePackageProperty@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageProperty::~CachePackageProperty(void)
0x18018993b  jmp     loc_180189A7C
0x180189940  mov     rbx, r15
0x180189943  mov     rdi, r15
0x180189946  mov     r14, r15
0x180189949  cmp     [rbp+70h+arg_0], r15b
0x180189950  jz      loc_180189A8B
0x180189956  mov     rdx, [rsp+170h+var_110]
0x18018995b  lea     rax, [rbp+70h+arg_0]
0x180189962  xorps   xmm0, xmm0
0x180189965  mov     [rsp+170h+var_150], rax; int
0x18018996a  lea     r9, [rbp+70h+var_B8]
0x18018996e  mov     [rbp+70h+var_A8], r15d
0x180189972  mov     rcx, rsi
0x180189975  mov     [rbp+70h+var_A0], r15
0x180189979  movdqu  [rbp+70h+var_B8], xmm0
0x18018997e  mov     [rbp+70h+var_98], r15d
0x180189982  mov     [rbp+70h+var_90], r15
0x180189986  mov     [rbp+70h+var_88], r15d
0x18018998a  call    ?Get@PackageProperty_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageProperty_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageProperty_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageProperty_NoThrow &,bool &)
0x18018998f  mov     esi, eax
0x180189991  test    eax, eax
0x180189993  js      loc_180189A4F
0x180189999  cmp     [rbp+70h+arg_0], r15b
0x1801899a0  jz      short loc_1801899E7
0x1801899a2  lea     r8, [rbp+70h+var_C0]; unsigned __int64 *
0x1801899a6  mov     [rbp+70h+var_C0], r15
0x1801899aa  lea     rdx, [rbp+70h+var_B8]; struct StateRepository::Cache::Entity::PackageProperty_NoThrow *
0x1801899ae  lea     rcx, [rsp+170h+var_110]; struct StateRepository::Entity::CachePackageProperty *
0x1801899b3  call    ?Cache_Check@CachePackageProperty@Entity@StateRepository@@CAJAEBV123@AEBVPackageProperty_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageProperty::Cache_Check(StateRepository::Entity::CachePackageProperty const &,StateRepository::Cache::Entity::PackageProperty_NoThrow const &,unsigned __int64 &)
0x1801899b8  mov     esi, eax
0x1801899ba  test    eax, eax
0x1801899bc  js      short loc_180189A3A
0x1801899be  mov     r15, [rbp+70h+var_C0]
0x1801899c2  test    r15, r15
0x1801899c5  jz      short loc_1801899DF
0x1801899c7  mov     rdx, [rsp+170h+var_110]; __int64
0x1801899cc  lea     rcx, [rsp+170h+var_120]; this
0x1801899d1  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1801899d6  mov     esi, eax
0x1801899d8  test    eax, eax
0x1801899da  js      short loc_180189A33
0x1801899dc  add     rbx, r15
0x1801899df  inc     r14
0x1801899e2  xor     r15d, r15d
0x1801899e5  jmp     short loc_1801899FF
0x1801899e7  mov     rdx, [rsp+170h+var_110]; __int64
0x1801899ec  lea     rcx, [rsp+170h+var_120]; this
0x1801899f1  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1801899f6  mov     esi, eax
0x1801899f8  test    eax, eax
0x1801899fa  js      short loc_180189A48
0x1801899fc  inc     rbx
0x1801899ff  lea     r8, [rbp+70h+arg_0]; bool *
0x180189a06  lea     rdx, [rsp+170h+var_110]; struct StateRepository::Entity::CachePackageProperty *
0x180189a0b  lea     rcx, [rsp+170h+var_128]; this
0x180189a10  call    ?FindNext@CachePackageProperty@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageProperty::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageProperty &,bool &)
0x180189a15  mov     esi, eax
0x180189a17  test    eax, eax
0x180189a19  js      short loc_180189A41
0x180189a1b  inc     rdi
0x180189a1e  lea     rcx, [rbp+70h+var_B8]; this
0x180189a22  call    ??1PackageProperty_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow(void)
0x180189a27  mov     rsi, [rbp+70h+arg_8]
0x180189a2e  jmp     loc_180189949
0x180189a33  mov     edx, 23Dh
0x180189a38  jmp     short loc_180189A54
0x180189a3a  mov     edx, 239h
0x180189a3f  jmp     short loc_180189A54
0x180189a41  mov     edx, 245h
0x180189a46  jmp     short loc_180189A54
0x180189a48  mov     edx, 243h
0x180189a4d  jmp     short loc_180189A54
0x180189a4f  mov     edx, 234h; void *
0x180189a54  mov     rcx, [rbp+78h]; this
0x180189a58  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189a5f  mov     r9d, esi; char *
0x180189a62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189a67  lea     rcx, [rbp+70h+var_B8]; this
0x180189a6b  call    ??1PackageProperty_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow(void)
0x180189a70  lea     rcx, [rsp+170h+var_110]; this
0x180189a75  call    ??1CachePackageProperty@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageProperty::~CachePackageProperty(void)
0x180189a7a  mov     ebx, esi
0x180189a7c  lea     rcx, [rsp+170h+var_128]; this
0x180189a81  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180189a86  jmp     loc_180189CC2
0x180189a8b  sub     rdi, r14
0x180189a8e  jz      short loc_180189AB9
0x180189a90  test    cs:byte_1804DF881, 20h
0x180189a97  jz      short loc_180189AB9
0x180189a99  mov     rax, qword ptr [rsp+170h+var_120]
0x180189a9e  lea     r8, aCachepackagepr; "CachePackageProperty"
0x180189aa5  mov     r9, rdi
0x180189aa8  mov     [rsp+170h+var_150], rax; int
0x180189aad  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180189ab4  call    McTemplateU0sxs_EventWriteTransfer
0x180189ab9  lea     rcx, [rsp+170h+var_110]; this
0x180189abe  call    ??1CachePackageProperty@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageProperty::~CachePackageProperty(void)
0x180189ac3  lea     rcx, [rsp+170h+var_128]; this
0x180189ac8  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180189acd  lea     rcx, [rsp+170h+var_120]; this
0x180189ad2  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180189ad7  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180189ada  mov     [rsp+170h+var_140], r15
0x180189adf  lea     rcx, [rsp+170h+var_140]; this
0x180189ae4  mov     [rsp+170h+var_138], r15d
0x180189ae9  mov     [rsp+170h+var_130], r15
0x180189aee  call    ?Open@PackagePropertyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180189af3  mov     edi, eax
0x180189af5  test    eax, eax
0x180189af7  jns     short loc_180189B45
0x180189af9  mov     rcx, [rbp+78h]; this
0x180189afd  lea     r8, aOnecoreBaseApp_101; "onecore\\base\\appmodel\\StateRepositor"...
0x180189b04  mov     r9d, eax; char *
0x180189b07  mov     edx, 2ADh; void *
0x180189b0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189b11  mov     rcx, [rbp+78h]; this
0x180189b15  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189b1c  mov     r9d, edi; char *
0x180189b1f  mov     edx, 256h; void *
0x180189b24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189b29  mov     rcx, [rsp+170h+var_140]
0x180189b2e  mov     [rsp+170h+var_140], r15
0x180189b33  test    rcx, rcx
0x180189b36  jz      short loc_180189B3E
0x180189b38  call    cs:__imp_SRCacheContext_Close
0x180189b3e  mov     ebx, edi
0x180189b40  jmp     loc_180189CC2
0x180189b45  xorps   xmm0, xmm0
0x180189b48  mov     [rsp+170h+var_100], r15d
0x180189b4d  lea     r9, [rbp+70h+arg_0]
0x180189b54  mov     [rsp+170h+var_F8], r15
0x180189b59  lea     r8, [rsp+170h+var_110]
0x180189b5e  mov     dword ptr [rbp+70h+var_F0], r15d
0x180189b62  lea     rcx, [rsp+170h+var_140]
0x180189b67  mov     [rbp+70h+var_E8], r15
0x180189b6b  movdqu  xmmword ptr [rsp+170h+var_110], xmm0
0x180189b71  mov     dword ptr [rbp+70h+var_E0], r15d
0x180189b75  mov     [rbp+70h+arg_0], r15b
0x180189b7c  call    ?Get@PackagePropertyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageProperty_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageProperty_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageProperty_NoThrow &,bool &)
0x180189b81  mov     edi, eax
0x180189b83  test    eax, eax
0x180189b85  jns     short loc_180189BAE
0x180189b87  mov     rcx, [rbp+78h]; this
0x180189b8b  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189b92  mov     r9d, eax; char *
0x180189b95  mov     edx, 259h; void *
0x180189b9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189b9f  lea     rcx, [rsp+170h+var_110]; this
0x180189ba4  call    ??1PackageProperty_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow(void)
0x180189ba9  jmp     loc_180189B29
0x180189bae  mov     rdi, r15
0x180189bb1  cmp     [rbp+70h+arg_0], r15b
0x180189bb8  jz      loc_180189CD1
0x180189bbe  mov     r9, [rsp+170h+var_110]; char *
0x180189bc3  lea     rax, [rbp+70h+arg_0]
0x180189bca  xorps   xmm0, xmm0
0x180189bcd  mov     [rsp+170h+var_150], rax; int
0x180189bd2  xor     r8d, r8d; char *
0x180189bd5  movdqa  [rbp+70h+var_80], xmm0
0x180189bda  lea     rdx, aSelectExistsSe_222; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x180189be1  movdqa  [rbp+70h+var_50], xmm0
0x180189be6  mov     rcx, r12; this
0x180189be9  mov     [rbp+70h+var_70], r15d
0x180189bed  mov     [rbp+70h+var_68], r15
0x180189bf1  mov     [rbp+70h+var_60], r15
0x180189bf5  mov     [rbp+70h+var_58], r15d
0x180189bf9  mov     [rbp+70h+var_40], r15
0x180189bfd  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180189c02  mov     esi, eax
0x180189c04  test    eax, eax
0x180189c06  js      short loc_180189C68
0x180189c08  cmp     [rbp+70h+arg_0], r15b
0x180189c0f  jnz     short loc_180189C2C
0x180189c11  mov     rdx, [rsp+170h+var_110]; __int64
0x180189c16  lea     rcx, [rsp+170h+var_120]; this
0x180189c1b  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180189c20  mov     esi, eax
0x180189c22  test    eax, eax
0x180189c24  js      short loc_180189C5A
0x180189c26  inc     rdi
0x180189c29  inc     rbx
0x180189c2c  inc     [rsp+170h+var_138]
0x180189c30  lea     r9, [rbp+70h+arg_0]
0x180189c37  lea     r8, [rsp+170h+var_110]
0x180189c3c  lea     rcx, [rsp+170h+var_140]
0x180189c41  call    ?Get@PackagePropertyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageProperty_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackagePropertyIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageProperty_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageProperty_NoThrow &,bool &)
0x180189c46  mov     esi, eax
0x180189c48  test    eax, eax
0x180189c4a  js      short loc_180189C61
0x180189c4c  lea     rcx, [rbp+70h+var_80]; this
0x180189c50  call    ??1CachePackageProperty@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageProperty::~CachePackageProperty(void)
0x180189c55  jmp     loc_180189BB1
0x180189c5a  mov     edx, 262h
0x180189c5f  jmp     short loc_180189C85
0x180189c61  mov     edx, 264h
0x180189c66  jmp     short loc_180189C85
0x180189c68  mov     rcx, [rbp+78h]; this
0x180189c6c  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189c73  mov     r9d, esi; char *
0x180189c76  mov     edx, 8Ah; void *
0x180189c7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189c80  mov     edx, 25Dh; void *
0x180189c85  mov     rcx, [rbp+78h]; this
0x180189c89  lea     r8, aOnecoreBaseApp_177; "onecore\\base\\appmodel\\staterepositor"...
0x180189c90  mov     r9d, esi; char *
0x180189c93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180189c98  lea     rcx, [rbp+70h+var_80]; this
0x180189c9c  call    ??1CachePackageProperty@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageProperty::~CachePackageProperty(void)
0x180189ca1  lea     rcx, [rsp+170h+var_110]; this
0x180189ca6  call    ??1PackageProperty_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow(void)
0x180189cab  mov     rcx, [rsp+170h+var_140]
0x180189cb0  mov     [rsp+170h+var_140], r15
0x180189cb5  test    rcx, rcx
0x180189cb8  jz      short loc_180189CC0
0x180189cba  call    cs:__imp_SRCacheContext_Close
0x180189cc0  mov     ebx, esi
0x180189cc2  lea     rcx, [rsp+170h+var_120]; this
0x180189cc7  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180189ccc  jmp     loc_180189D5A
0x180189cd1  lea     rcx, [rsp+170h+var_110]; this
0x180189cd6  call    ??1PackageProperty_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageProperty_NoThrow::~PackageProperty_NoThrow(void)
0x180189cdb  mov     rcx, [rsp+170h+var_140]
0x180189ce0  mov     [rsp+170h+var_140], r15
0x180189ce5  test    rcx, rcx
0x180189ce8  jz      short loc_180189CF0
0x180189cea  call    cs:__imp_SRCacheContext_Close
0x180189cf0  test    rdi, rdi
0x180189cf3  jz      short loc_180189D1E
0x180189cf5  test    cs:byte_1804DF881, 20h
0x180189cfc  jz      short loc_180189D1E
0x180189cfe  mov     rax, qword ptr [rsp+170h+var_120]
0x180189d03  lea     r8, aCachepackagepr; "CachePackageProperty"
0x180189d0a  mov     r9, rdi
0x180189d0d  mov     [rsp+170h+var_150], rax
0x180189d12  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x180189d19  call    McTemplateU0sxs_EventWriteTransfer
0x180189d1e  mov     rax, [rbp+70h+arg_18]
0x180189d25  lea     rcx, [rsp+170h+var_120]; this
  ... truncated ...
```
