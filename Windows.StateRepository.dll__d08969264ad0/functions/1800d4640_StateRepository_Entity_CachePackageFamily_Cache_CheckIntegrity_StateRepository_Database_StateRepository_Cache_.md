# StateRepository::Entity::CachePackageFamily::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1800d4640`
- end: `0x1800d4b7f`
- name: `?Cache_CheckIntegrity@CachePackageFamily@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1343`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x18006c080`
- `0x18006d0e0`
- `0x18009887c`
- `0x1800ae890`
- `0x1800d4640`
- `0x1800d4b88`
- `0x18018f650`
- `0x180190234`
- `0x18026544c`
- `0x180265514`
- `0x180265888`
- `0x180265950`
- `0x180265a30`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d494b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d4abd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d4aec`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d494b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d4abd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800d4aec`

## string_xrefs

- `0x1800d46cf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4729`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4865`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4928`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d499c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4a6c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4a8c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d4b4d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepackagefamily.cpp`
- `0x1800d490d`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageFamily.hpp`
- `0x1800d48ab`: `CachePackageFamily`
- `0x1800d4b05`: `CachePackageFamily`
- `0x1800d49eb`: `SELECT EXISTS(SELECT 1 FROM CachePackageFamily WHERE _CachePackageFamilyID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePackageFamily::Cache_CheckIntegrity(
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
  __int64 v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // r15
  __int64 v14; // r8
  int appended; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r14
  __int64 v19; // rdx
  __int64 v20; // rdi
  int v21; // eax
  unsigned int v22; // edi
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // rdx
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
  bool v45[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v46; // [rsp+38h] [rbp-C8h] BYREF
  int v47; // [rsp+40h] [rbp-C0h]
  __int64 v48; // [rsp+48h] [rbp-B8h]
  __int64 v49; // [rsp+50h] [rbp-B0h] BYREF
  int v50[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v51; // [rsp+60h] [rbp-A0h]
  __int64 v52[2]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v53; // [rsp+80h] [rbp-80h]
  __int128 v54; // [rsp+90h] [rbp-70h]
  __int128 v55; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v56; // [rsp+B0h] [rbp-50h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v57; // [rsp+B8h] [rbp-48h]
  _QWORD *v58; // [rsp+C0h] [rbp-40h]
  char *v59[2]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v60[72]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v61; // [rsp+128h] [rbp+28h]
  __int64 v62; // [rsp+130h] [rbp+30h]
  __int128 v63; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v64[72]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v65; // [rsp+198h] [rbp+98h]
  __int64 v66; // [rsp+1A0h] [rbp+A0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v58 = a4;
  v4 = a2;
  v57 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 489;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 490;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 491;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v50 = 0;
  v51 = 0;
  v49 = 0;
  v8 = StateRepository::Entity::CachePackageFamily::Find(a1, (struct StateRepository::Statement *)&v49);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v49);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v50);
    return v6;
  }
  v45[0] = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  v54 = 0;
  v55 = 0;
  Next = StateRepository::Entity::CachePackageFamily::FindNext(
           (struct StateRepository::Statement *)&v49,
           (struct StateRepository::Entity::CachePackageFamily *)v52,
           v45);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CachePackageFamily::~CachePackageFamily((StateRepository::Entity::CachePackageFamily *)v52);
    goto LABEL_28;
  }
  v11 = 0;
  v12 = 0;
  v13 = 0;
  while ( v45[0] )
  {
    v63 = 0;
    memset_0(v64, 0, 0x44u);
    v41 = v45;
    v65 = 0;
    v66 = 0;
    appended = StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(v4, v52[0], v14, &v63);
    if ( appended < 0 )
    {
      v19 = 510;
      goto LABEL_27;
    }
    if ( v45[0] )
    {
      v56 = 0;
      appended = StateRepository::Entity::CachePackageFamily::Cache_Check(
                   (const struct StateRepository::Entity::CachePackageFamily *)v52,
                   (const struct StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v63,
                   &v56);
      if ( appended < 0 )
      {
        v19 = 515;
        goto LABEL_27;
      }
      v18 = v56;
      if ( v56 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v50, v52[0], v17);
        if ( appended < 0 )
        {
          v19 = 519;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
            (const char *)(unsigned int)appended,
            (int)v45);
          StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v63);
          StateRepository::Entity::CachePackageFamily::~CachePackageFamily((StateRepository::Entity::CachePackageFamily *)v52);
          v6 = appended;
          goto LABEL_28;
        }
        v11 += v18;
      }
      ++v13;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v50, v52[0], v16);
      if ( appended < 0 )
      {
        v19 = 525;
        goto LABEL_27;
      }
      ++v11;
    }
    appended = StateRepository::Entity::CachePackageFamily::FindNext(
                 (struct StateRepository::Statement *)&v49,
                 (struct StateRepository::Entity::CachePackageFamily *)v52,
                 v45);
    if ( appended < 0 )
    {
      v19 = 527;
      goto LABEL_27;
    }
    ++v12;
    StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)&v63);
    v4 = v57;
  }
  v20 = v12 - v13;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CachePackageFamily",
      v20,
      *(__int64 *)v50);
  StateRepository::Entity::CachePackageFamily::~CachePackageFamily((StateRepository::Entity::CachePackageFamily *)v52);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v49);
  StateRepository::TextA::Clear((StateRepository::TextA *)v50);
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v21 = StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow *)&v46,
          v4);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageFamily.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
      (const char *)v22,
      v42);
LABEL_34:
    v25 = v46;
    v46 = 0;
    if ( v25 )
      SRCacheContext_Close(v25, v23, v24);
    v6 = v22;
    goto LABEL_53;
  }
  *(_OWORD *)v59 = 0;
  memset_0(v60, 0, 0x44u);
  v61 = 0;
  v62 = 0;
  v45[0] = 0;
  v27 = StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Get(&v46, v26, v59, v45);
  v22 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x223,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)v59);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v45[0] )
  {
    *(_OWORD *)v52 = 0;
    v53 = 0;
    v54 = 0;
    v55 = 0;
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePackageFamily WHERE _CachePackageFamilyID=? LIMIT 1);",
            0,
            v59[0],
            (__int64)v45,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x73,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 551;
      goto LABEL_50;
    }
    if ( !v45[0] )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v50, (__int64)v59[0], v31);
      if ( v32 < 0 )
      {
        v33 = 556;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepackagefamily.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CachePackageFamily::~CachePackageFamily((StateRepository::Entity::CachePackageFamily *)v52);
        StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)v59);
        v36 = v46;
        v46 = 0;
        if ( v36 )
          SRCacheContext_Close(v36, v34, v35);
        v6 = v32;
        goto LABEL_53;
      }
      ++v28;
      ++v11;
    }
    ++v47;
    v32 = StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Get(&v46, v30, v59, v45);
    if ( v32 < 0 )
    {
      v33 = 558;
      goto LABEL_50;
    }
    StateRepository::Entity::CachePackageFamily::~CachePackageFamily((StateRepository::Entity::CachePackageFamily *)v52);
  }
  StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow((StateRepository::Cache::Entity::PackageFamily_NoThrow *)v59);
  v39 = v46;
  v46 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CachePackageFamily",
      v28,
      *(__int64 *)v50);
  *v58 = v11;
  StateRepository::TextA::Reset((StateRepository::TextA *)v50);
  return 0;
}

```

## disassembly

```asm
0x1800d4640  push    rbp
0x1800d4642  push    rbx
0x1800d4643  push    rsi
0x1800d4644  push    rdi
0x1800d4645  push    r13
0x1800d4647  push    r14
0x1800d4649  push    r15
0x1800d464b  lea     rbp, [rsp-0C0h]
0x1800d4653  sub     rsp, 1C0h
0x1800d465a  mov     rax, cs:__security_cookie
0x1800d4661  xor     rax, rsp
0x1800d4664  mov     [rbp+0F0h+var_40], rax
0x1800d466b  xor     r14d, r14d
0x1800d466e  mov     [rbp+0F0h+var_130], r9
0x1800d4672  mov     rsi, rdx
0x1800d4675  mov     [rbp+0F0h+var_138], rdx
0x1800d4679  mov     r13, rcx
0x1800d467c  cmp     [rcx], r14
0x1800d467f  jz      loc_1800D4B3C
0x1800d4685  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800d468a  test    al, al
0x1800d468c  jz      short loc_1800D469D
0x1800d468e  mov     ebx, 8067000Bh
0x1800d4693  mov     edx, 1EAh
0x1800d4698  jmp     loc_1800D4B46
0x1800d469d  cmp     [rsi], r14
0x1800d46a0  jz      loc_1800D4B35
0x1800d46a6  lea     rdx, [rsp+1F0h+var_1A0]; struct StateRepository::Statement *
0x1800d46ab  mov     qword ptr [rsp+1F0h+var_198], r14
0x1800d46b0  mov     rcx, r13; struct StateRepository::Database *
0x1800d46b3  mov     [rsp+1F0h+var_190], r14
0x1800d46b8  mov     [rsp+1F0h+var_1A0], r14
0x1800d46bd  call    ?Find@CachePackageFamily@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePackageFamily::Find(StateRepository::Database &,StateRepository::Statement &)
0x1800d46c2  mov     ebx, eax
0x1800d46c4  test    eax, eax
0x1800d46c6  jns     short loc_1800D46E8
0x1800d46c8  mov     rcx, [rbp+0F8h]; this
0x1800d46cf  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d46d6  mov     r9d, eax; char *
0x1800d46d9  mov     edx, 1F6h; void *
0x1800d46de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d46e3  jmp     loc_1800D4889
0x1800d46e8  xorps   xmm0, xmm0
0x1800d46eb  mov     [rsp+1F0h+var_1C0], r14b
0x1800d46f0  xorps   xmm1, xmm1
0x1800d46f3  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x1800d46f9  lea     r8, [rsp+1F0h+var_1C0]; bool *
0x1800d46fe  movdqa  [rbp+0F0h+var_170], xmm1
0x1800d4703  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePackageFamily *
0x1800d4708  movdqa  [rbp+0F0h+var_160], xmm0
0x1800d470d  lea     rcx, [rsp+1F0h+var_1A0]; struct StateRepository::Statement *
0x1800d4712  movdqa  [rbp+0F0h+var_150], xmm1
0x1800d4717  call    ?FindNext@CachePackageFamily@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageFamily::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageFamily &,bool &)
0x1800d471c  mov     ebx, eax
0x1800d471e  test    eax, eax
0x1800d4720  jns     short loc_1800D474C
0x1800d4722  mov     rcx, [rbp+0F8h]; this
0x1800d4729  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d4730  mov     r9d, eax; char *
0x1800d4733  mov     edx, 1F9h; void *
0x1800d4738  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d473d  lea     rcx, [rsp+1F0h+var_180]; this
0x1800d4742  call    ??1CachePackageFamily@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageFamily::~CachePackageFamily(void)
0x1800d4747  jmp     loc_1800D4889
0x1800d474c  mov     rbx, r14
0x1800d474f  mov     rdi, r14
0x1800d4752  mov     r15, r14
0x1800d4755  cmp     [rsp+1F0h+var_1C0], r14b
0x1800d475a  jz      loc_1800D4898
0x1800d4760  xor     edx, edx; Val
0x1800d4762  lea     rcx, [rbp+0F0h+var_A0]; void *
0x1800d4766  xorps   xmm0, xmm0
0x1800d4769  movdqa  [rbp+0F0h+var_B0], xmm0
0x1800d476e  lea     r8d, [rdx+44h]; Size
0x1800d4772  call    memset_0
0x1800d4777  mov     rdx, [rsp+1F0h+var_180]
0x1800d477c  lea     rax, [rsp+1F0h+var_1C0]
0x1800d4781  lea     r9, [rbp+0F0h+var_B0]
0x1800d4785  mov     [rsp+1F0h+var_1D0], rax; int
0x1800d478a  mov     rcx, rsi
0x1800d478d  mov     [rbp+0F0h+var_58], r14
0x1800d4794  mov     [rbp+0F0h+var_50], r14
0x1800d479b  call    ?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x1800d47a0  mov     esi, eax
0x1800d47a2  test    eax, eax
0x1800d47a4  js      loc_1800D4859
0x1800d47aa  cmp     [rsp+1F0h+var_1C0], r14b
0x1800d47af  jz      short loc_1800D47F6
0x1800d47b1  lea     r8, [rbp+0F0h+var_140]; unsigned __int64 *
0x1800d47b5  mov     [rbp+0F0h+var_140], r14
0x1800d47b9  lea     rdx, [rbp+0F0h+var_B0]; struct StateRepository::Cache::Entity::PackageFamily_NoThrow *
0x1800d47bd  lea     rcx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePackageFamily *
0x1800d47c2  call    ?Cache_Check@CachePackageFamily@Entity@StateRepository@@CAJAEBV123@AEBVPackageFamily_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePackageFamily::Cache_Check(StateRepository::Entity::CachePackageFamily const &,StateRepository::Cache::Entity::PackageFamily_NoThrow const &,unsigned __int64 &)
0x1800d47c7  mov     esi, eax
0x1800d47c9  test    eax, eax
0x1800d47cb  js      short loc_1800D4844
0x1800d47cd  mov     r14, [rbp+0F0h+var_140]
0x1800d47d1  test    r14, r14
0x1800d47d4  jz      short loc_1800D47EE
0x1800d47d6  mov     rdx, [rsp+1F0h+var_180]; __int64
0x1800d47db  lea     rcx, [rsp+1F0h+var_198]; this
0x1800d47e0  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800d47e5  mov     esi, eax
0x1800d47e7  test    eax, eax
0x1800d47e9  js      short loc_1800D483D
0x1800d47eb  add     rbx, r14
0x1800d47ee  inc     r15
0x1800d47f1  xor     r14d, r14d
0x1800d47f4  jmp     short loc_1800D480E
0x1800d47f6  mov     rdx, [rsp+1F0h+var_180]; __int64
0x1800d47fb  lea     rcx, [rsp+1F0h+var_198]; this
0x1800d4800  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800d4805  mov     esi, eax
0x1800d4807  test    eax, eax
0x1800d4809  js      short loc_1800D4852
0x1800d480b  inc     rbx
0x1800d480e  lea     r8, [rsp+1F0h+var_1C0]; bool *
0x1800d4813  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePackageFamily *
0x1800d4818  lea     rcx, [rsp+1F0h+var_1A0]; struct StateRepository::Statement *
0x1800d481d  call    ?FindNext@CachePackageFamily@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePackageFamily::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePackageFamily &,bool &)
0x1800d4822  mov     esi, eax
0x1800d4824  test    eax, eax
0x1800d4826  js      short loc_1800D484B
0x1800d4828  inc     rdi
0x1800d482b  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800d482f  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800d4834  mov     rsi, [rbp+0F0h+var_138]
0x1800d4838  jmp     loc_1800D4755
0x1800d483d  mov     edx, 207h
0x1800d4842  jmp     short loc_1800D485E
0x1800d4844  mov     edx, 203h
0x1800d4849  jmp     short loc_1800D485E
0x1800d484b  mov     edx, 20Fh
0x1800d4850  jmp     short loc_1800D485E
0x1800d4852  mov     edx, 20Dh
0x1800d4857  jmp     short loc_1800D485E
0x1800d4859  mov     edx, 1FEh; void *
0x1800d485e  mov     rcx, [rbp+0F8h]; this
0x1800d4865  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d486c  mov     r9d, esi; char *
0x1800d486f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4874  lea     rcx, [rbp+0F0h+var_B0]; this
0x1800d4878  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800d487d  lea     rcx, [rsp+1F0h+var_180]; this
0x1800d4882  call    ??1CachePackageFamily@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageFamily::~CachePackageFamily(void)
0x1800d4887  mov     ebx, esi
0x1800d4889  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800d488e  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800d4893  jmp     loc_1800D4AC5
0x1800d4898  sub     rdi, r15
0x1800d489b  jz      short loc_1800D48C6
0x1800d489d  test    cs:byte_1804DF881, 20h
0x1800d48a4  jz      short loc_1800D48C6
0x1800d48a6  mov     rax, qword ptr [rsp+1F0h+var_198]
0x1800d48ab  lea     r8, aCachepackagefa; "CachePackageFamily"
0x1800d48b2  mov     r9, rdi
0x1800d48b5  mov     [rsp+1F0h+var_1D0], rax; int
0x1800d48ba  lea     rdx, CacheIntegrity_MissingCacheEntries
0x1800d48c1  call    McTemplateU0sxs_EventWriteTransfer
0x1800d48c6  lea     rcx, [rsp+1F0h+var_180]; this
0x1800d48cb  call    ??1CachePackageFamily@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageFamily::~CachePackageFamily(void)
0x1800d48d0  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1800d48d5  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800d48da  lea     rcx, [rsp+1F0h+var_198]; this
0x1800d48df  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x1800d48e4  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x1800d48e7  mov     [rsp+1F0h+var_1B8], r14
0x1800d48ec  lea     rcx, [rsp+1F0h+var_1B8]; this
0x1800d48f1  mov     [rsp+1F0h+var_1B0], r14d
0x1800d48f6  mov     [rsp+1F0h+var_1A8], r14
0x1800d48fb  call    ?Open@PackageFamilyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x1800d4900  mov     edi, eax
0x1800d4902  test    eax, eax
0x1800d4904  jns     short loc_1800D4958
0x1800d4906  mov     rcx, [rbp+0F8h]; this
0x1800d490d  lea     r8, aOnecoreBaseApp_94; "onecore\\base\\appmodel\\StateRepositor"...
0x1800d4914  mov     r9d, eax; char *
0x1800d4917  mov     edx, 2F2h; void *
0x1800d491c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4921  mov     rcx, [rbp+0F8h]; this
0x1800d4928  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d492f  mov     r9d, edi; char *
0x1800d4932  mov     edx, 220h; void *
0x1800d4937  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d493c  mov     rcx, [rsp+1F0h+var_1B8]
0x1800d4941  mov     [rsp+1F0h+var_1B8], r14
0x1800d4946  test    rcx, rcx
0x1800d4949  jz      short loc_1800D4951
0x1800d494b  call    cs:__imp_SRCacheContext_Close
0x1800d4951  mov     ebx, edi
0x1800d4953  jmp     loc_1800D4AC5
0x1800d4958  xor     edx, edx; Val
0x1800d495a  lea     rcx, [rbp+0F0h+var_110]; void *
0x1800d495e  xorps   xmm0, xmm0
0x1800d4961  movdqa  xmmword ptr [rbp+0F0h+var_120], xmm0
0x1800d4966  lea     r8d, [rdx+44h]; Size
0x1800d496a  call    memset_0
0x1800d496f  lea     r9, [rsp+1F0h+var_1C0]
0x1800d4974  mov     [rbp+0F0h+var_C8], r14
0x1800d4978  lea     r8, [rbp+0F0h+var_120]
0x1800d497c  mov     [rbp+0F0h+var_C0], r14
0x1800d4980  lea     rcx, [rsp+1F0h+var_1B8]
0x1800d4985  mov     [rsp+1F0h+var_1C0], r14b
0x1800d498a  call    ?Get@PackageFamilyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageFamily_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x1800d498f  mov     edi, eax
0x1800d4991  test    eax, eax
0x1800d4993  jns     short loc_1800D49BB
0x1800d4995  mov     rcx, [rbp+0F8h]; this
0x1800d499c  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d49a3  mov     r9d, eax; char *
0x1800d49a6  mov     edx, 223h; void *
0x1800d49ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d49b0  lea     rcx, [rbp+0F0h+var_120]; this
0x1800d49b4  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800d49b9  jmp     short loc_1800D493C
0x1800d49bb  mov     rdi, r14
0x1800d49be  cmp     [rsp+1F0h+var_1C0], r14b
0x1800d49c3  jz      loc_1800D4AD4
0x1800d49c9  mov     r9, [rbp+0F0h+var_120]; char *
0x1800d49cd  lea     rax, [rsp+1F0h+var_1C0]
0x1800d49d2  xorps   xmm0, xmm0
0x1800d49d5  mov     [rsp+1F0h+var_1D0], rax; int
0x1800d49da  xorps   xmm1, xmm1
0x1800d49dd  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x1800d49e3  xor     r8d, r8d; char *
0x1800d49e6  movdqa  [rbp+0F0h+var_170], xmm1
0x1800d49eb  lea     rdx, aSelectExistsSe_646; "SELECT EXISTS(SELECT 1 FROM CachePackag"...
0x1800d49f2  movdqa  [rbp+0F0h+var_160], xmm0
0x1800d49f7  mov     rcx, r13; this
0x1800d49fa  movdqa  [rbp+0F0h+var_150], xmm1
0x1800d49ff  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x1800d4a04  mov     esi, eax
0x1800d4a06  test    eax, eax
0x1800d4a08  js      short loc_1800D4A65
0x1800d4a0a  cmp     [rsp+1F0h+var_1C0], r14b
0x1800d4a0f  jnz     short loc_1800D4A2B
0x1800d4a11  mov     rdx, [rbp+0F0h+var_120]; __int64
0x1800d4a15  lea     rcx, [rsp+1F0h+var_198]; this
0x1800d4a1a  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800d4a1f  mov     esi, eax
0x1800d4a21  test    eax, eax
0x1800d4a23  js      short loc_1800D4A57
0x1800d4a25  inc     rdi
0x1800d4a28  inc     rbx
0x1800d4a2b  inc     [rsp+1F0h+var_1B0]
0x1800d4a2f  lea     r9, [rsp+1F0h+var_1C0]
0x1800d4a34  lea     r8, [rbp+0F0h+var_120]
0x1800d4a38  lea     rcx, [rsp+1F0h+var_1B8]
0x1800d4a3d  call    ?Get@PackageFamilyIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PackageFamily_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PackageFamilyIterator_NoThrow::Get(StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)
0x1800d4a42  mov     esi, eax
0x1800d4a44  test    eax, eax
0x1800d4a46  js      short loc_1800D4A5E
0x1800d4a48  lea     rcx, [rsp+1F0h+var_180]; this
0x1800d4a4d  call    ??1CachePackageFamily@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageFamily::~CachePackageFamily(void)
0x1800d4a52  jmp     loc_1800D49BE
0x1800d4a57  mov     edx, 22Ch
0x1800d4a5c  jmp     short loc_1800D4A85
0x1800d4a5e  mov     edx, 22Eh
0x1800d4a63  jmp     short loc_1800D4A85
0x1800d4a65  mov     rcx, [rbp+0F8h]; this
0x1800d4a6c  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d4a73  mov     r9d, esi; char *
0x1800d4a76  mov     edx, 73h ; 's'; void *
0x1800d4a7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4a80  mov     edx, 227h; void *
0x1800d4a85  mov     rcx, [rbp+0F8h]; this
0x1800d4a8c  lea     r8, aOnecoreBaseApp_360; "onecore\\base\\appmodel\\staterepositor"...
0x1800d4a93  mov     r9d, esi; char *
0x1800d4a96  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4a9b  lea     rcx, [rsp+1F0h+var_180]; this
0x1800d4aa0  call    ??1CachePackageFamily@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CachePackageFamily::~CachePackageFamily(void)
0x1800d4aa5  lea     rcx, [rbp+0F0h+var_120]; this
0x1800d4aa9  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800d4aae  mov     rcx, [rsp+1F0h+var_1B8]
0x1800d4ab3  mov     [rsp+1F0h+var_1B8], r14
0x1800d4ab8  test    rcx, rcx
0x1800d4abb  jz      short loc_1800D4AC3
0x1800d4abd  call    cs:__imp_SRCacheContext_Close
0x1800d4ac3  mov     ebx, esi
0x1800d4ac5  lea     rcx, [rsp+1F0h+var_198]; this
0x1800d4aca  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800d4acf  jmp     loc_1800D4B5C
0x1800d4ad4  lea     rcx, [rbp+0F0h+var_120]; this
0x1800d4ad8  call    ??1PackageFamily_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PackageFamily_NoThrow::~PackageFamily_NoThrow(void)
0x1800d4add  mov     rcx, [rsp+1F0h+var_1B8]
0x1800d4ae2  mov     [rsp+1F0h+var_1B8], r14
0x1800d4ae7  test    rcx, rcx
0x1800d4aea  jz      short loc_1800D4AF2
0x1800d4aec  call    cs:__imp_SRCacheContext_Close
0x1800d4af2  test    rdi, rdi
0x1800d4af5  jz      short loc_1800D4B20
0x1800d4af7  test    cs:byte_1804DF881, 20h
0x1800d4afe  jz      short loc_1800D4B20
0x1800d4b00  mov     rax, qword ptr [rsp+1F0h+var_198]
0x1800d4b05  lea     r8, aCachepackagefa; "CachePackageFamily"
0x1800d4b0c  mov     r9, rdi
0x1800d4b0f  mov     [rsp+1F0h+var_1D0], rax
0x1800d4b14  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x1800d4b1b  call    McTemplateU0sxs_EventWriteTransfer
0x1800d4b20  mov     rax, [rbp+0F0h+var_130]
  ... truncated ...
```
