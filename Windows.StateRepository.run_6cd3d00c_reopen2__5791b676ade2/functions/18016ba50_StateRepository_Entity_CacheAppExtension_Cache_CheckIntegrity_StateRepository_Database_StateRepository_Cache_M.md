# StateRepository::Entity::CacheAppExtension::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18016ba50`
- end: `0x18016bfc3`
- name: `?Cache_CheckIntegrity@CacheAppExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1395`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x18002a20c`
- `0x18002b1e4`
- `0x18002bcec`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800ae890`
- `0x18012fb4c`
- `0x18016ba50`
- `0x18026544c`
- `0x1802709f0`
- `0x180270e7c`
- `0x180270f44`
- `0x180271024`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bd69`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bf0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bf3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bd69`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bf0c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016bf3c`

## string_xrefs

- `0x18016bacf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bb40`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bc83`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bd46`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bdbf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bebb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bedb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bfa0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappextension.cpp`
- `0x18016bd2b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppExtension.hpp`
- `0x18016bcc9`: `CacheAppExtension`
- `0x18016bf55`: `CacheAppExtension`
- `0x18016be16`: `SELECT EXISTS(SELECT 1 FROM CacheAppExtension WHERE _CacheAppExtensionID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheAppExtension::Cache_CheckIntegrity(
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
  __int128 v47; // [rsp+80h] [rbp-80h]
  __int128 v48; // [rsp+90h] [rbp-70h]
  __int128 v49; // [rsp+A0h] [rbp-60h]
  __int128 v50; // [rsp+B0h] [rbp-50h]
  __int128 v51; // [rsp+C0h] [rbp-40h]
  __int128 v52; // [rsp+D0h] [rbp-30h]
  __int64 v53; // [rsp+E0h] [rbp-20h]
  _OWORD v54[4]; // [rsp+F0h] [rbp-10h] BYREF
  int v55; // [rsp+130h] [rbp+30h]
  _OWORD v56[7]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v57; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  bool v59; // [rsp+200h] [rbp+100h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v60; // [rsp+208h] [rbp+108h]
  _QWORD *v61; // [rsp+218h] [rbp+118h]

  v61 = a4;
  v60 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 617;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 618;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 619;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v43 = 0;
  v44 = 0;
  v42 = 0;
  v8 = StateRepository::Entity::CacheAppExtension::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v43);
    return v6;
  }
  v53 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v59 = 0;
  Next = StateRepository::Entity::CacheAppExtension::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CacheAppExtension *)v46,
           &v59);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v46);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v59 )
  {
    v35 = &v59;
    memset(v54, 0, sizeof(v54));
    v55 = 0;
    appended = StateRepository::Cache::Entity::AppExtension_NoThrow::Get(v4, v46[0], v11, v54);
    if ( appended < 0 )
    {
      v19 = 638;
      goto LABEL_27;
    }
    if ( v59 )
    {
      v45 = 0;
      appended = StateRepository::Entity::CacheAppExtension::Cache_Check(
                   (const struct StateRepository::Entity::CacheAppExtension *)v46,
                   (const struct StateRepository::Cache::Entity::AppExtension_NoThrow *)v54,
                   &v45);
      if ( appended < 0 )
      {
        v19 = 643;
        goto LABEL_27;
      }
      v18 = v45;
      if ( v45 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v46[0], v17);
        if ( appended < 0 )
        {
          v19 = 647;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
            (const char *)(unsigned int)appended,
            (int)&v59);
          StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v54);
          StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v46);
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
        v19 = 653;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheAppExtension::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CacheAppExtension *)v46,
                 &v59);
    if ( appended < 0 )
    {
      v19 = 655;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v54);
    v4 = v60;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheAppExtension",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v46);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::AppExtensionIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
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
  LODWORD(v50) = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v59 = 0;
  v25 = StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Get(&v39, v22, v46, &v59);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
      (const char *)(unsigned int)v25,
      (int)v35);
    StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v46);
    goto LABEL_34;
  }
  v26 = 0;
  while ( v59 )
  {
    memset(v56, 0, sizeof(v56));
    v57 = 0;
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheAppExtension WHERE _CacheAppExtensionID=? LIMIT 1);",
            0,
            v46[0],
            (__int64)&v59,
            v38);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
        (const char *)(unsigned int)v27,
        v37);
      v31 = 679;
      goto LABEL_50;
    }
    if ( !v59 )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v46[0], v29);
      if ( v30 < 0 )
      {
        v31 = 684;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappextension.cpp",
          (const char *)(unsigned int)v30,
          v37);
        StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v56);
        StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v46);
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
    v30 = StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Get(&v39, v28, v46, &v59);
    if ( v30 < 0 )
    {
      v31 = 686;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v56);
  }
  StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow((StateRepository::Cache::Entity::PkgExtension_NoThrow *)v46);
  v33 = v39;
  v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheAppExtension",
      v26,
      *(__int64 *)v43);
  *v61 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x18016ba50  mov     [rsp-8+arg_18], r9
0x18016ba55  mov     [rsp-8+arg_8], rdx
0x18016ba5a  push    rbp
0x18016ba5b  push    rbx
0x18016ba5c  push    rsi
0x18016ba5d  push    rdi
0x18016ba5e  push    r12
0x18016ba60  push    r14
0x18016ba62  push    r15
0x18016ba64  lea     rbp, [rsp-0C0h]
0x18016ba6c  sub     rsp, 1C0h
0x18016ba73  xor     r15d, r15d
0x18016ba76  mov     rsi, rdx
0x18016ba79  mov     r12, rcx
0x18016ba7c  cmp     [rcx], r15
0x18016ba7f  jz      loc_18016BF8F
0x18016ba85  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18016ba8a  test    al, al
0x18016ba8c  jz      short loc_18016BA9D
0x18016ba8e  mov     ebx, 8067000Bh
0x18016ba93  mov     edx, 26Ah
0x18016ba98  jmp     loc_18016BF99
0x18016ba9d  cmp     [rsi], r15
0x18016baa0  jz      loc_18016BF88
0x18016baa6  lea     rdx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x18016baab  mov     qword ptr [rsp+1F0h+var_1A0], r15
0x18016bab0  mov     rcx, r12; struct StateRepository::Database *
0x18016bab3  mov     [rsp+1F0h+var_198], r15
0x18016bab8  mov     [rsp+1F0h+var_1A8], r15
0x18016babd  call    ?Find@CacheAppExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheAppExtension::Find(StateRepository::Database &,StateRepository::Statement &)
0x18016bac2  mov     ebx, eax
0x18016bac4  test    eax, eax
0x18016bac6  jns     short loc_18016BAE8
0x18016bac8  mov     rcx, [rbp+0F8h]; this
0x18016bacf  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bad6  mov     r9d, eax; char *
0x18016bad9  mov     edx, 276h; void *
0x18016bade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bae3  jmp     loc_18016BCA7
0x18016bae8  xorps   xmm0, xmm0
0x18016baeb  mov     [rbp+0F0h+var_110], r15
0x18016baef  xorps   xmm1, xmm1
0x18016baf2  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x18016baf8  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18016baff  movdqa  [rbp+0F0h+var_170], xmm1
0x18016bb04  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheAppExtension *
0x18016bb09  movdqa  [rbp+0F0h+var_160], xmm0
0x18016bb0e  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18016bb13  movdqa  [rbp+0F0h+var_150], xmm1
0x18016bb18  movdqa  [rbp+0F0h+var_140], xmm0
0x18016bb1d  movdqa  [rbp+0F0h+var_130], xmm1
0x18016bb22  movdqa  [rbp+0F0h+var_120], xmm0
0x18016bb27  mov     [rbp+0F0h+arg_0], r15b
0x18016bb2e  call    ?FindNext@CacheAppExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppExtension &,bool &)
0x18016bb33  mov     ebx, eax
0x18016bb35  test    eax, eax
0x18016bb37  jns     short loc_18016BB63
0x18016bb39  mov     rcx, [rbp+0F8h]; this
0x18016bb40  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bb47  mov     r9d, eax; char *
0x18016bb4a  mov     edx, 279h; void *
0x18016bb4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bb54  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bb59  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18016bb5e  jmp     loc_18016BCA7
0x18016bb63  mov     rbx, r15
0x18016bb66  mov     rdi, r15
0x18016bb69  mov     r14, r15
0x18016bb6c  cmp     [rbp+0F0h+arg_0], r15b
0x18016bb73  jz      loc_18016BCB6
0x18016bb79  mov     rdx, [rsp+1F0h+var_180]
0x18016bb7e  lea     rax, [rbp+0F0h+arg_0]
0x18016bb85  xorps   xmm0, xmm0
0x18016bb88  mov     [rsp+1F0h+var_1D0], rax; int
0x18016bb8d  xorps   xmm1, xmm1
0x18016bb90  movdqa  [rbp+0F0h+var_100], xmm0
0x18016bb95  lea     r9, [rbp+0F0h+var_100]
0x18016bb99  movdqa  [rbp+0F0h+var_F0], xmm1
0x18016bb9e  mov     rcx, rsi
0x18016bba1  movdqa  [rbp+0F0h+var_E0], xmm0
0x18016bba6  movdqa  [rbp+0F0h+var_D0], xmm1
0x18016bbab  mov     [rbp+0F0h+var_C0], r15d
0x18016bbaf  call    ?Get@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)
0x18016bbb4  mov     esi, eax
0x18016bbb6  test    eax, eax
0x18016bbb8  js      loc_18016BC77
0x18016bbbe  cmp     [rbp+0F0h+arg_0], r15b
0x18016bbc5  jz      short loc_18016BC0F
0x18016bbc7  lea     r8, [rsp+1F0h+var_190]; unsigned __int64 *
0x18016bbcc  mov     [rsp+1F0h+var_190], r15
0x18016bbd1  lea     rdx, [rbp+0F0h+var_100]; struct StateRepository::Cache::Entity::AppExtension_NoThrow *
0x18016bbd5  lea     rcx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheAppExtension *
0x18016bbda  call    ?Cache_Check@CacheAppExtension@Entity@StateRepository@@CAJAEBV123@AEBVAppExtension_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheAppExtension::Cache_Check(StateRepository::Entity::CacheAppExtension const &,StateRepository::Cache::Entity::AppExtension_NoThrow const &,unsigned __int64 &)
0x18016bbdf  mov     esi, eax
0x18016bbe1  test    eax, eax
0x18016bbe3  js      short loc_18016BC62
0x18016bbe5  mov     r15, [rsp+1F0h+var_190]
0x18016bbea  test    r15, r15
0x18016bbed  jz      short loc_18016BC07
0x18016bbef  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18016bbf4  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18016bbf9  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18016bbfe  mov     esi, eax
0x18016bc00  test    eax, eax
0x18016bc02  js      short loc_18016BC5B
0x18016bc04  add     rbx, r15
0x18016bc07  inc     r14
0x18016bc0a  xor     r15d, r15d
0x18016bc0d  jmp     short loc_18016BC27
0x18016bc0f  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18016bc14  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18016bc19  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18016bc1e  mov     esi, eax
0x18016bc20  test    eax, eax
0x18016bc22  js      short loc_18016BC70
0x18016bc24  inc     rbx
0x18016bc27  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18016bc2e  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheAppExtension *
0x18016bc33  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18016bc38  call    ?FindNext@CacheAppExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppExtension &,bool &)
0x18016bc3d  mov     esi, eax
0x18016bc3f  test    eax, eax
0x18016bc41  js      short loc_18016BC69
0x18016bc43  inc     rdi
0x18016bc46  lea     rcx, [rbp+0F0h+var_100]; this
0x18016bc4a  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18016bc4f  mov     rsi, [rbp+0F0h+arg_8]
0x18016bc56  jmp     loc_18016BB6C
0x18016bc5b  mov     edx, 287h
0x18016bc60  jmp     short loc_18016BC7C
0x18016bc62  mov     edx, 283h
0x18016bc67  jmp     short loc_18016BC7C
0x18016bc69  mov     edx, 28Fh
0x18016bc6e  jmp     short loc_18016BC7C
0x18016bc70  mov     edx, 28Dh
0x18016bc75  jmp     short loc_18016BC7C
0x18016bc77  mov     edx, 27Eh; void *
0x18016bc7c  mov     rcx, [rbp+0F8h]; this
0x18016bc83  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bc8a  mov     r9d, esi; char *
0x18016bc8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bc92  lea     rcx, [rbp+0F0h+var_100]; this
0x18016bc96  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18016bc9b  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bca0  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18016bca5  mov     ebx, esi
0x18016bca7  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18016bcac  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18016bcb1  jmp     loc_18016BF14
0x18016bcb6  sub     rdi, r14
0x18016bcb9  jz      short loc_18016BCE4
0x18016bcbb  test    cs:byte_1804DF881, 20h
0x18016bcc2  jz      short loc_18016BCE4
0x18016bcc4  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x18016bcc9  lea     r8, aCacheappextens; "CacheAppExtension"
0x18016bcd0  mov     r9, rdi
0x18016bcd3  mov     [rsp+1F0h+var_1D0], rax; int
0x18016bcd8  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18016bcdf  call    McTemplateU0sxs_EventWriteTransfer
0x18016bce4  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bce9  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18016bcee  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18016bcf3  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18016bcf8  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18016bcfd  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18016bd02  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18016bd05  mov     [rsp+1F0h+var_1C0], r15
0x18016bd0a  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18016bd0f  mov     [rsp+1F0h+var_1B8], r15d
0x18016bd14  mov     [rsp+1F0h+var_1B0], r15
0x18016bd19  call    ?Open@AppExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18016bd1e  mov     edi, eax
0x18016bd20  test    eax, eax
0x18016bd22  jns     short loc_18016BD76
0x18016bd24  mov     rcx, [rbp+0F8h]; this
0x18016bd2b  lea     r8, aOnecoreBaseApp_284; "onecore\\base\\appmodel\\StateRepositor"...
0x18016bd32  mov     r9d, eax; char *
0x18016bd35  mov     edx, 2B9h; void *
0x18016bd3a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bd3f  mov     rcx, [rbp+0F8h]; this
0x18016bd46  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bd4d  mov     r9d, edi; char *
0x18016bd50  mov     edx, 2A0h; void *
0x18016bd55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bd5a  mov     rcx, [rsp+1F0h+var_1C0]
0x18016bd5f  mov     [rsp+1F0h+var_1C0], r15
0x18016bd64  test    rcx, rcx
0x18016bd67  jz      short loc_18016BD6F
0x18016bd69  call    cs:__imp_SRCacheContext_Close
0x18016bd6f  mov     ebx, edi
0x18016bd71  jmp     loc_18016BF14
0x18016bd76  xorps   xmm0, xmm0
0x18016bd79  mov     dword ptr [rbp+0F0h+var_140], r15d
0x18016bd7d  xorps   xmm1, xmm1
0x18016bd80  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x18016bd86  lea     r9, [rbp+0F0h+arg_0]
0x18016bd8d  movdqa  [rbp+0F0h+var_170], xmm1
0x18016bd92  lea     r8, [rsp+1F0h+var_180]
0x18016bd97  movdqa  [rbp+0F0h+var_160], xmm0
0x18016bd9c  lea     rcx, [rsp+1F0h+var_1C0]
0x18016bda1  movdqa  [rbp+0F0h+var_150], xmm1
0x18016bda6  mov     [rbp+0F0h+arg_0], r15b
0x18016bdad  call    ?Get@AppExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)
0x18016bdb2  mov     edi, eax
0x18016bdb4  test    eax, eax
0x18016bdb6  jns     short loc_18016BDE2
0x18016bdb8  mov     rcx, [rbp+0F8h]; this
0x18016bdbf  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bdc6  mov     r9d, eax; char *
0x18016bdc9  mov     edx, 2A3h; void *
0x18016bdce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016bdd3  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bdd8  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18016bddd  jmp     loc_18016BD5A
0x18016bde2  mov     rdi, r15
0x18016bde5  cmp     [rbp+0F0h+arg_0], r15b
0x18016bdec  jz      loc_18016BF23
0x18016bdf2  mov     r9, [rsp+1F0h+var_180]; char *
0x18016bdf7  lea     rax, [rbp+0F0h+arg_0]
0x18016bdfe  xorps   xmm0, xmm0
0x18016be01  mov     [rsp+1F0h+var_1D0], rax; int
0x18016be06  xorps   xmm1, xmm1
0x18016be09  movdqa  [rbp+0F0h+var_B0], xmm0
0x18016be0e  xor     r8d, r8d; char *
0x18016be11  movdqa  [rbp+0F0h+var_A0], xmm1
0x18016be16  lea     rdx, aSelectExistsSe_311; "SELECT EXISTS(SELECT 1 FROM CacheAppExt"...
0x18016be1d  movdqa  [rbp+0F0h+var_90], xmm0
0x18016be22  mov     rcx, r12; this
0x18016be25  movdqa  [rbp+0F0h+var_80], xmm1
0x18016be2a  movdqa  [rbp+0F0h+var_70], xmm0
0x18016be32  movdqa  [rbp+0F0h+var_60], xmm1
0x18016be3a  movdqa  [rbp+0F0h+var_50], xmm0
0x18016be42  mov     [rbp+0F0h+var_40], r15
0x18016be49  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18016be4e  mov     esi, eax
0x18016be50  test    eax, eax
0x18016be52  js      short loc_18016BEB4
0x18016be54  cmp     [rbp+0F0h+arg_0], r15b
0x18016be5b  jnz     short loc_18016BE78
0x18016be5d  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18016be62  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18016be67  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18016be6c  mov     esi, eax
0x18016be6e  test    eax, eax
0x18016be70  js      short loc_18016BEA6
0x18016be72  inc     rdi
0x18016be75  inc     rbx
0x18016be78  inc     [rsp+1F0h+var_1B8]
0x18016be7c  lea     r9, [rbp+0F0h+arg_0]
0x18016be83  lea     r8, [rsp+1F0h+var_180]
0x18016be88  lea     rcx, [rsp+1F0h+var_1C0]
0x18016be8d  call    ?Get@AppExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)
0x18016be92  mov     esi, eax
0x18016be94  test    eax, eax
0x18016be96  js      short loc_18016BEAD
0x18016be98  lea     rcx, [rbp+0F0h+var_B0]; this
0x18016be9c  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18016bea1  jmp     loc_18016BDE5
0x18016bea6  mov     edx, 2ACh
0x18016beab  jmp     short loc_18016BED4
0x18016bead  mov     edx, 2AEh
0x18016beb2  jmp     short loc_18016BED4
0x18016beb4  mov     rcx, [rbp+0F8h]; this
0x18016bebb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bec2  mov     r9d, esi; char *
0x18016bec5  mov     edx, 0ABh; void *
0x18016beca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016becf  mov     edx, 2A7h; void *
0x18016bed4  mov     rcx, [rbp+0F8h]; this
0x18016bedb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18016bee2  mov     r9d, esi; char *
0x18016bee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016beea  lea     rcx, [rbp+0F0h+var_B0]; this
0x18016beee  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18016bef3  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bef8  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18016befd  mov     rcx, [rsp+1F0h+var_1C0]
0x18016bf02  mov     [rsp+1F0h+var_1C0], r15
0x18016bf07  test    rcx, rcx
0x18016bf0a  jz      short loc_18016BF12
0x18016bf0c  call    cs:__imp_SRCacheContext_Close
0x18016bf12  mov     ebx, esi
0x18016bf14  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18016bf19  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18016bf1e  jmp     loc_18016BFAF
0x18016bf23  lea     rcx, [rsp+1F0h+var_180]; this
0x18016bf28  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18016bf2d  mov     rcx, [rsp+1F0h+var_1C0]
0x18016bf32  mov     [rsp+1F0h+var_1C0], r15
0x18016bf37  test    rcx, rcx
0x18016bf3a  jz      short loc_18016BF42
0x18016bf3c  call    cs:__imp_SRCacheContext_Close
0x18016bf42  test    rdi, rdi
0x18016bf45  jz      short loc_18016BF70
0x18016bf47  test    cs:byte_1804DF881, 20h
0x18016bf4e  jz      short loc_18016BF70
0x18016bf50  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x18016bf55  lea     r8, aCacheappextens; "CacheAppExtension"
0x18016bf5c  mov     r9, rdi
0x18016bf5f  mov     [rsp+1F0h+var_1D0], rax
  ... truncated ...
```
