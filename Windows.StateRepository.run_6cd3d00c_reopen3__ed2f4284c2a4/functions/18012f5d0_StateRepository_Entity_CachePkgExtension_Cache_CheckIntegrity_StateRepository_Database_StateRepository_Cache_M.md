# StateRepository::Entity::CachePkgExtension::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18012f5d0`
- end: `0x18012fb43`
- name: `?Cache_CheckIntegrity@CachePkgExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1395`
- prototype: `static int __high(struct StateRepository::Database *, struct StateRepository::Cache::Manager_NoThrow *, enum StateRepository::ExecutionFlags, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x18002a20c`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800ae890`
- `0x1800da62c`
- `0x18012f5d0`
- `0x18012fb4c`
- `0x18026544c`
- `0x18027255c`
- `0x1802729e8`
- `0x180272a34`
- `0x180272aa4`
- `0x180272b6c`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f8e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012fa8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012fabc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012f8e9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012fa8c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012fabc`

## string_xrefs

- `0x18012f8ab`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PkgExtension.hpp`
- `0x18012f64f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012f6c0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012f803`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012f8c6`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012f93f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012fa3b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012fa5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012fb20`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachepkgextension.cpp`
- `0x18012f849`: `CachePkgExtension`
- `0x18012fad5`: `CachePkgExtension`
- `0x18012f996`: `SELECT EXISTS(SELECT 1 FROM CachePkgExtension WHERE _CachePkgExtensionID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CachePkgExtension::Cache_CheckIntegrity(
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
  v8 = StateRepository::Entity::CachePkgExtension::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x276,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
  Next = StateRepository::Entity::CachePkgExtension::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CachePkgExtension *)v46,
           &v59);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x279,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
    appended = StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(v4, v46[0], v11, v54);
    if ( appended < 0 )
    {
      v19 = 638;
      goto LABEL_27;
    }
    if ( v59 )
    {
      v45 = 0;
      appended = StateRepository::Entity::CachePkgExtension::Cache_Check(
                   (const struct StateRepository::Entity::CachePkgExtension *)v46,
                   (const struct StateRepository::Cache::Entity::PkgExtension_NoThrow *)v54,
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
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
    appended = StateRepository::Entity::CachePkgExtension::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CachePkgExtension *)v46,
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
      (unsigned int)"CachePkgExtension",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CacheAppExtension::~CacheAppExtension((StateRepository::Entity::CacheAppExtension *)v46);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow *)&v39,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
  v25 = StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Get(&v39, v22, v46, &v59);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A3,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CachePkgExtension WHERE _CachePkgExtensionID=? LIMIT 1);",
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
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachepkgextension.cpp",
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
    v30 = StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Get(&v39, v28, v46, &v59);
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
      (unsigned int)"CachePkgExtension",
      v26,
      *(__int64 *)v43);
  *v61 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x18012f5d0  mov     [rsp-8+arg_18], r9
0x18012f5d5  mov     [rsp-8+arg_8], rdx
0x18012f5da  push    rbp
0x18012f5db  push    rbx
0x18012f5dc  push    rsi
0x18012f5dd  push    rdi
0x18012f5de  push    r12
0x18012f5e0  push    r14
0x18012f5e2  push    r15
0x18012f5e4  lea     rbp, [rsp-0C0h]
0x18012f5ec  sub     rsp, 1C0h
0x18012f5f3  xor     r15d, r15d
0x18012f5f6  mov     rsi, rdx
0x18012f5f9  mov     r12, rcx
0x18012f5fc  cmp     [rcx], r15
0x18012f5ff  jz      loc_18012FB0F
0x18012f605  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18012f60a  test    al, al
0x18012f60c  jz      short loc_18012F61D
0x18012f60e  mov     ebx, 8067000Bh
0x18012f613  mov     edx, 26Ah
0x18012f618  jmp     loc_18012FB19
0x18012f61d  cmp     [rsi], r15
0x18012f620  jz      loc_18012FB08
0x18012f626  lea     rdx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x18012f62b  mov     qword ptr [rsp+1F0h+var_1A0], r15
0x18012f630  mov     rcx, r12; struct StateRepository::Database *
0x18012f633  mov     [rsp+1F0h+var_198], r15
0x18012f638  mov     [rsp+1F0h+var_1A8], r15
0x18012f63d  call    ?Find@CachePkgExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CachePkgExtension::Find(StateRepository::Database &,StateRepository::Statement &)
0x18012f642  mov     ebx, eax
0x18012f644  test    eax, eax
0x18012f646  jns     short loc_18012F668
0x18012f648  mov     rcx, [rbp+0F8h]; this
0x18012f64f  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012f656  mov     r9d, eax; char *
0x18012f659  mov     edx, 276h; void *
0x18012f65e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f663  jmp     loc_18012F827
0x18012f668  xorps   xmm0, xmm0
0x18012f66b  mov     [rbp+0F0h+var_110], r15
0x18012f66f  xorps   xmm1, xmm1
0x18012f672  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x18012f678  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18012f67f  movdqa  [rbp+0F0h+var_170], xmm1
0x18012f684  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePkgExtension *
0x18012f689  movdqa  [rbp+0F0h+var_160], xmm0
0x18012f68e  lea     rcx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x18012f693  movdqa  [rbp+0F0h+var_150], xmm1
0x18012f698  movdqa  [rbp+0F0h+var_140], xmm0
0x18012f69d  movdqa  [rbp+0F0h+var_130], xmm1
0x18012f6a2  movdqa  [rbp+0F0h+var_120], xmm0
0x18012f6a7  mov     [rbp+0F0h+arg_0], r15b
0x18012f6ae  call    ?FindNext@CachePkgExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePkgExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePkgExtension &,bool &)
0x18012f6b3  mov     ebx, eax
0x18012f6b5  test    eax, eax
0x18012f6b7  jns     short loc_18012F6E3
0x18012f6b9  mov     rcx, [rbp+0F8h]; this
0x18012f6c0  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012f6c7  mov     r9d, eax; char *
0x18012f6ca  mov     edx, 279h; void *
0x18012f6cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f6d4  lea     rcx, [rsp+1F0h+var_180]; this
0x18012f6d9  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18012f6de  jmp     loc_18012F827
0x18012f6e3  mov     rbx, r15
0x18012f6e6  mov     rdi, r15
0x18012f6e9  mov     r14, r15
0x18012f6ec  cmp     [rbp+0F0h+arg_0], r15b
0x18012f6f3  jz      loc_18012F836
0x18012f6f9  mov     rdx, [rsp+1F0h+var_180]
0x18012f6fe  lea     rax, [rbp+0F0h+arg_0]
0x18012f705  xorps   xmm0, xmm0
0x18012f708  mov     [rsp+1F0h+var_1D0], rax; int
0x18012f70d  xorps   xmm1, xmm1
0x18012f710  movdqa  [rbp+0F0h+var_100], xmm0
0x18012f715  lea     r9, [rbp+0F0h+var_100]
0x18012f719  movdqa  [rbp+0F0h+var_F0], xmm1
0x18012f71e  mov     rcx, rsi
0x18012f721  movdqa  [rbp+0F0h+var_E0], xmm0
0x18012f726  movdqa  [rbp+0F0h+var_D0], xmm1
0x18012f72b  mov     [rbp+0F0h+var_C0], r15d
0x18012f72f  call    ?Get@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x18012f734  mov     esi, eax
0x18012f736  test    eax, eax
0x18012f738  js      loc_18012F7F7
0x18012f73e  cmp     [rbp+0F0h+arg_0], r15b
0x18012f745  jz      short loc_18012F78F
0x18012f747  lea     r8, [rsp+1F0h+var_190]; unsigned __int64 *
0x18012f74c  mov     [rsp+1F0h+var_190], r15
0x18012f751  lea     rdx, [rbp+0F0h+var_100]; struct StateRepository::Cache::Entity::PkgExtension_NoThrow *
0x18012f755  lea     rcx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePkgExtension *
0x18012f75a  call    ?Cache_Check@CachePkgExtension@Entity@StateRepository@@CAJAEBV123@AEBVPkgExtension_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CachePkgExtension::Cache_Check(StateRepository::Entity::CachePkgExtension const &,StateRepository::Cache::Entity::PkgExtension_NoThrow const &,unsigned __int64 &)
0x18012f75f  mov     esi, eax
0x18012f761  test    eax, eax
0x18012f763  js      short loc_18012F7E2
0x18012f765  mov     r15, [rsp+1F0h+var_190]
0x18012f76a  test    r15, r15
0x18012f76d  jz      short loc_18012F787
0x18012f76f  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18012f774  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18012f779  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18012f77e  mov     esi, eax
0x18012f780  test    eax, eax
0x18012f782  js      short loc_18012F7DB
0x18012f784  add     rbx, r15
0x18012f787  inc     r14
0x18012f78a  xor     r15d, r15d
0x18012f78d  jmp     short loc_18012F7A7
0x18012f78f  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18012f794  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18012f799  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18012f79e  mov     esi, eax
0x18012f7a0  test    eax, eax
0x18012f7a2  js      short loc_18012F7F0
0x18012f7a4  inc     rbx
0x18012f7a7  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18012f7ae  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CachePkgExtension *
0x18012f7b3  lea     rcx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x18012f7b8  call    ?FindNext@CachePkgExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CachePkgExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CachePkgExtension &,bool &)
0x18012f7bd  mov     esi, eax
0x18012f7bf  test    eax, eax
0x18012f7c1  js      short loc_18012F7E9
0x18012f7c3  inc     rdi
0x18012f7c6  lea     rcx, [rbp+0F0h+var_100]; this
0x18012f7ca  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18012f7cf  mov     rsi, [rbp+0F0h+arg_8]
0x18012f7d6  jmp     loc_18012F6EC
0x18012f7db  mov     edx, 287h
0x18012f7e0  jmp     short loc_18012F7FC
0x18012f7e2  mov     edx, 283h
0x18012f7e7  jmp     short loc_18012F7FC
0x18012f7e9  mov     edx, 28Fh
0x18012f7ee  jmp     short loc_18012F7FC
0x18012f7f0  mov     edx, 28Dh
0x18012f7f5  jmp     short loc_18012F7FC
0x18012f7f7  mov     edx, 27Eh; void *
0x18012f7fc  mov     rcx, [rbp+0F8h]; this
0x18012f803  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012f80a  mov     r9d, esi; char *
0x18012f80d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f812  lea     rcx, [rbp+0F0h+var_100]; this
0x18012f816  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18012f81b  lea     rcx, [rsp+1F0h+var_180]; this
0x18012f820  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18012f825  mov     ebx, esi
0x18012f827  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18012f82c  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18012f831  jmp     loc_18012FA94
0x18012f836  sub     rdi, r14
0x18012f839  jz      short loc_18012F864
0x18012f83b  test    cs:byte_1804DF881, 20h
0x18012f842  jz      short loc_18012F864
0x18012f844  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x18012f849  lea     r8, aCachepkgextens; "CachePkgExtension"
0x18012f850  mov     r9, rdi
0x18012f853  mov     [rsp+1F0h+var_1D0], rax; int
0x18012f858  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18012f85f  call    McTemplateU0sxs_EventWriteTransfer
0x18012f864  lea     rcx, [rsp+1F0h+var_180]; this
0x18012f869  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18012f86e  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18012f873  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18012f878  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18012f87d  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18012f882  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18012f885  mov     [rsp+1F0h+var_1C0], r15
0x18012f88a  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18012f88f  mov     [rsp+1F0h+var_1B8], r15d
0x18012f894  mov     [rsp+1F0h+var_1B0], r15
0x18012f899  call    ?Open@PkgExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18012f89e  mov     edi, eax
0x18012f8a0  test    eax, eax
0x18012f8a2  jns     short loc_18012F8F6
0x18012f8a4  mov     rcx, [rbp+0F8h]; this
0x18012f8ab  lea     r8, aOnecoreBaseApp_415; "onecore\\base\\appmodel\\StateRepositor"...
0x18012f8b2  mov     r9d, eax; char *
0x18012f8b5  mov     edx, 2B9h; void *
0x18012f8ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f8bf  mov     rcx, [rbp+0F8h]; this
0x18012f8c6  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012f8cd  mov     r9d, edi; char *
0x18012f8d0  mov     edx, 2A0h; void *
0x18012f8d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f8da  mov     rcx, [rsp+1F0h+var_1C0]
0x18012f8df  mov     [rsp+1F0h+var_1C0], r15
0x18012f8e4  test    rcx, rcx
0x18012f8e7  jz      short loc_18012F8EF
0x18012f8e9  call    cs:__imp_SRCacheContext_Close
0x18012f8ef  mov     ebx, edi
0x18012f8f1  jmp     loc_18012FA94
0x18012f8f6  xorps   xmm0, xmm0
0x18012f8f9  mov     dword ptr [rbp+0F0h+var_140], r15d
0x18012f8fd  xorps   xmm1, xmm1
0x18012f900  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x18012f906  lea     r9, [rbp+0F0h+arg_0]
0x18012f90d  movdqa  [rbp+0F0h+var_170], xmm1
0x18012f912  lea     r8, [rsp+1F0h+var_180]
0x18012f917  movdqa  [rbp+0F0h+var_160], xmm0
0x18012f91c  lea     rcx, [rsp+1F0h+var_1C0]
0x18012f921  movdqa  [rbp+0F0h+var_150], xmm1
0x18012f926  mov     [rbp+0F0h+arg_0], r15b
0x18012f92d  call    ?Get@PkgExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x18012f932  mov     edi, eax
0x18012f934  test    eax, eax
0x18012f936  jns     short loc_18012F962
0x18012f938  mov     rcx, [rbp+0F8h]; this
0x18012f93f  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012f946  mov     r9d, eax; char *
0x18012f949  mov     edx, 2A3h; void *
0x18012f94e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012f953  lea     rcx, [rsp+1F0h+var_180]; this
0x18012f958  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18012f95d  jmp     loc_18012F8DA
0x18012f962  mov     rdi, r15
0x18012f965  cmp     [rbp+0F0h+arg_0], r15b
0x18012f96c  jz      loc_18012FAA3
0x18012f972  mov     r9, [rsp+1F0h+var_180]; char *
0x18012f977  lea     rax, [rbp+0F0h+arg_0]
0x18012f97e  xorps   xmm0, xmm0
0x18012f981  mov     [rsp+1F0h+var_1D0], rax; int
0x18012f986  xorps   xmm1, xmm1
0x18012f989  movdqa  [rbp+0F0h+var_B0], xmm0
0x18012f98e  xor     r8d, r8d; char *
0x18012f991  movdqa  [rbp+0F0h+var_A0], xmm1
0x18012f996  lea     rdx, aSelectExistsSe_127; "SELECT EXISTS(SELECT 1 FROM CachePkgExt"...
0x18012f99d  movdqa  [rbp+0F0h+var_90], xmm0
0x18012f9a2  mov     rcx, r12; this
0x18012f9a5  movdqa  [rbp+0F0h+var_80], xmm1
0x18012f9aa  movdqa  [rbp+0F0h+var_70], xmm0
0x18012f9b2  movdqa  [rbp+0F0h+var_60], xmm1
0x18012f9ba  movdqa  [rbp+0F0h+var_50], xmm0
0x18012f9c2  mov     [rbp+0F0h+var_40], r15
0x18012f9c9  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18012f9ce  mov     esi, eax
0x18012f9d0  test    eax, eax
0x18012f9d2  js      short loc_18012FA34
0x18012f9d4  cmp     [rbp+0F0h+arg_0], r15b
0x18012f9db  jnz     short loc_18012F9F8
0x18012f9dd  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18012f9e2  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18012f9e7  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18012f9ec  mov     esi, eax
0x18012f9ee  test    eax, eax
0x18012f9f0  js      short loc_18012FA26
0x18012f9f2  inc     rdi
0x18012f9f5  inc     rbx
0x18012f9f8  inc     [rsp+1F0h+var_1B8]
0x18012f9fc  lea     r9, [rbp+0F0h+arg_0]
0x18012fa03  lea     r8, [rsp+1F0h+var_180]
0x18012fa08  lea     rcx, [rsp+1F0h+var_1C0]
0x18012fa0d  call    ?Get@PkgExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@PkgExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::PkgExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)
0x18012fa12  mov     esi, eax
0x18012fa14  test    eax, eax
0x18012fa16  js      short loc_18012FA2D
0x18012fa18  lea     rcx, [rbp+0F0h+var_B0]; this
0x18012fa1c  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18012fa21  jmp     loc_18012F965
0x18012fa26  mov     edx, 2ACh
0x18012fa2b  jmp     short loc_18012FA54
0x18012fa2d  mov     edx, 2AEh
0x18012fa32  jmp     short loc_18012FA54
0x18012fa34  mov     rcx, [rbp+0F8h]; this
0x18012fa3b  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012fa42  mov     r9d, esi; char *
0x18012fa45  mov     edx, 0ABh; void *
0x18012fa4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fa4f  mov     edx, 2A7h; void *
0x18012fa54  mov     rcx, [rbp+0F8h]; this
0x18012fa5b  lea     r8, aOnecoreBaseApp_140; "onecore\\base\\appmodel\\staterepositor"...
0x18012fa62  mov     r9d, esi; char *
0x18012fa65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012fa6a  lea     rcx, [rbp+0F0h+var_B0]; this
0x18012fa6e  call    ??1CacheAppExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppExtension::~CacheAppExtension(void)
0x18012fa73  lea     rcx, [rsp+1F0h+var_180]; this
0x18012fa78  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18012fa7d  mov     rcx, [rsp+1F0h+var_1C0]
0x18012fa82  mov     [rsp+1F0h+var_1C0], r15
0x18012fa87  test    rcx, rcx
0x18012fa8a  jz      short loc_18012FA92
0x18012fa8c  call    cs:__imp_SRCacheContext_Close
0x18012fa92  mov     ebx, esi
0x18012fa94  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18012fa99  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18012fa9e  jmp     loc_18012FB2F
0x18012faa3  lea     rcx, [rsp+1F0h+var_180]; this
0x18012faa8  call    ??1PkgExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::PkgExtension_NoThrow::~PkgExtension_NoThrow(void)
0x18012faad  mov     rcx, [rsp+1F0h+var_1C0]
0x18012fab2  mov     [rsp+1F0h+var_1C0], r15
0x18012fab7  test    rcx, rcx
0x18012faba  jz      short loc_18012FAC2
0x18012fabc  call    cs:__imp_SRCacheContext_Close
0x18012fac2  test    rdi, rdi
0x18012fac5  jz      short loc_18012FAF0
0x18012fac7  test    cs:byte_1804DF881, 20h
0x18012face  jz      short loc_18012FAF0
0x18012fad0  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x18012fad5  lea     r8, aCachepkgextens; "CachePkgExtension"
0x18012fadc  mov     r9, rdi
0x18012fadf  mov     [rsp+1F0h+var_1D0], rax
  ... truncated ...
```
