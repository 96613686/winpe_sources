# StateRepository::Entity::CacheApplicationExtension::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180147f70`
- end: `0x180148503`
- name: `?Cache_CheckIntegrity@CacheApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1427`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x18002621c`
- `0x1800337a4`
- `0x180062cd8`
- `0x180092bdc`
- `0x1800a63c0`
- `0x1800ae890`
- `0x180147f70`
- `0x18014850c`
- `0x18026544c`
- `0x180267eb8`
- `0x180268340`
- `0x180268408`
- `0x180268530`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180148297`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014844c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014847c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180148297`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014844c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014847c`

## string_xrefs

- `0x180147fef`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x180148063`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x1801481b1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x180148274`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x1801482f8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x1801483fb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x18014841b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x1801484e0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplicationextension.cpp`
- `0x180148259`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x1801481f7`: `CacheApplicationExtension`
- `0x180148495`: `CacheApplicationExtension`
- `0x18014834f`: `SELECT EXISTS(SELECT 1 FROM CacheApplicationExtension WHERE _CacheApplicationExtensionID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheApplicationExtension::Cache_CheckIntegrity(
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
  __int64 v53; // [rsp+80h] [rbp-80h]
  __int64 v54; // [rsp+88h] [rbp-78h]
  __int128 v55; // [rsp+90h] [rbp-70h]
  __int128 v56; // [rsp+A0h] [rbp-60h]
  __int128 v57; // [rsp+B0h] [rbp-50h]
  __int128 v58; // [rsp+C0h] [rbp-40h]
  __int128 v59; // [rsp+D0h] [rbp-30h]
  __int64 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  __int128 v64; // [rsp+110h] [rbp+10h]
  __int128 v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  int v67; // [rsp+138h] [rbp+38h]
  __int128 v68; // [rsp+140h] [rbp+40h] BYREF
  __int64 v69; // [rsp+150h] [rbp+50h]
  __int64 v70; // [rsp+158h] [rbp+58h]
  __int128 v71; // [rsp+160h] [rbp+60h]
  __int128 v72; // [rsp+170h] [rbp+70h]
  __int128 v73; // [rsp+180h] [rbp+80h]
  __int128 v74; // [rsp+190h] [rbp+90h]
  __int128 v75; // [rsp+1A0h] [rbp+A0h]
  __int64 v76; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  bool v78; // [rsp+200h] [rbp+100h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v79; // [rsp+208h] [rbp+108h]
  _QWORD *v80; // [rsp+218h] [rbp+118h]

  v80 = a4;
  v79 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 716;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 717;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 718;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v48 = 0;
  v8 = StateRepository::Entity::CacheApplicationExtension::Find(a1, (struct StateRepository::Statement *)&v48);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D9,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v49);
    return v6;
  }
  v53 = 0;
  *(_OWORD *)v52 = 0;
  v55 = 0;
  v56 = 0;
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v54 = 0;
  v60 = 0;
  v78 = 0;
  Next = StateRepository::Entity::CacheApplicationExtension::FindNext(
           (struct StateRepository::Statement *)&v48,
           (struct StateRepository::Entity::CacheApplicationExtension *)v52,
           &v78);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2DC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension((StateRepository::Entity::CacheApplicationExtension *)v52);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v78 )
  {
    v41 = &v78;
    v61 = 0;
    v64 = 0;
    v65 = 0;
    v62 = 0;
    v63 = 0;
    v66 = 0;
    v67 = 0;
    appended = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(v4, v52[0], v11, &v61);
    if ( appended < 0 )
    {
      v19 = 737;
      goto LABEL_27;
    }
    if ( v78 )
    {
      v51 = 0;
      appended = StateRepository::Entity::CacheApplicationExtension::Cache_Check(
                   (const struct StateRepository::Entity::CacheApplicationExtension *)v52,
                   (const struct StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v61,
                   &v51);
      if ( appended < 0 )
      {
        v19 = 742;
        goto LABEL_27;
      }
      v18 = v51;
      if ( v51 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v17);
        if ( appended < 0 )
        {
          v19 = 746;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
            (const char *)(unsigned int)appended,
            (int)&v78);
          StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v61);
          StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension((StateRepository::Entity::CacheApplicationExtension *)v52);
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
        v19 = 752;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheApplicationExtension::FindNext(
                 (struct StateRepository::Statement *)&v48,
                 (struct StateRepository::Entity::CacheApplicationExtension *)v52,
                 &v78);
    if ( appended < 0 )
    {
      v19 = 754;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)&v61);
    v4 = v79;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheApplicationExtension",
      v20,
      *(__int64 *)v49);
  StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension((StateRepository::Entity::CacheApplicationExtension *)v52);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
  StateRepository::TextA::Clear((StateRepository::TextA *)v49);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow *)&v45,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x303,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
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
  v53 = 0;
  *(_OWORD *)v52 = 0;
  v55 = 0;
  v56 = 0;
  v54 = 0;
  *(_QWORD *)&v57 = 0;
  DWORD2(v57) = 0;
  v78 = 0;
  v27 = StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Get(&v45, v22, v52, &v78);
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x306,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)v52);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v78 )
  {
    v68 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v69 = 0;
    v70 = 0;
    v76 = 0;
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheApplicationExtension WHERE _CacheApplic"
                                                "ationExtensionID=? LIMIT 1);",
            0,
            v52[0],
            (__int64)&v78,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12F,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 778;
      goto LABEL_50;
    }
    if ( !v78 )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v31);
      if ( v32 < 0 )
      {
        v33 = 783;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplicationextension.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension((StateRepository::Entity::CacheApplicationExtension *)&v68);
        StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)v52);
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
    v32 = StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Get(&v45, v30, v52, &v78);
    if ( v32 < 0 )
    {
      v33 = 785;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension((StateRepository::Entity::CacheApplicationExtension *)&v68);
  }
  StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow((StateRepository::Cache::Entity::ApplicationExtension_NoThrow *)v52);
  v39 = v45;
  v45 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheApplicationExtension",
      v28,
      *(__int64 *)v49);
  *v80 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v49);
  return 0;
}

```

## disassembly

```asm
0x180147f70  mov     [rsp-8+arg_18], r9
0x180147f75  mov     [rsp-8+arg_8], rdx
0x180147f7a  push    rbp
0x180147f7b  push    rbx
0x180147f7c  push    rsi
0x180147f7d  push    rdi
0x180147f7e  push    r12
0x180147f80  push    r14
0x180147f82  push    r15
0x180147f84  lea     rbp, [rsp-0C0h]
0x180147f8c  sub     rsp, 1C0h
0x180147f93  xor     r15d, r15d
0x180147f96  mov     rsi, rdx
0x180147f99  mov     r12, rcx
0x180147f9c  cmp     [rcx], r15
0x180147f9f  jz      loc_1801484CF
0x180147fa5  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180147faa  test    al, al
0x180147fac  jz      short loc_180147FBD
0x180147fae  mov     ebx, 8067000Bh
0x180147fb3  mov     edx, 2CDh
0x180147fb8  jmp     loc_1801484D9
0x180147fbd  cmp     [rsi], r15
0x180147fc0  jz      loc_1801484C8
0x180147fc6  lea     rdx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x180147fcb  mov     qword ptr [rsp+1F0h+var_1A0], r15
0x180147fd0  mov     rcx, r12; struct StateRepository::Database *
0x180147fd3  mov     [rsp+1F0h+var_198], r15
0x180147fd8  mov     [rsp+1F0h+var_1A8], r15
0x180147fdd  call    ?Find@CacheApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheApplicationExtension::Find(StateRepository::Database &,StateRepository::Statement &)
0x180147fe2  mov     ebx, eax
0x180147fe4  test    eax, eax
0x180147fe6  jns     short loc_180148008
0x180147fe8  mov     rcx, [rbp+0F8h]; this
0x180147fef  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x180147ff6  mov     r9d, eax; char *
0x180147ff9  mov     edx, 2D9h; void *
0x180147ffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148003  jmp     loc_1801481D5
0x180148008  xorps   xmm0, xmm0
0x18014800b  mov     [rbp+0F0h+var_170], r15
0x18014800f  xorps   xmm1, xmm1
0x180148012  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x180148018  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18014801f  movdqa  [rbp+0F0h+var_160], xmm0
0x180148024  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheApplicationExtension *
0x180148029  movdqa  [rbp+0F0h+var_150], xmm1
0x18014802e  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180148033  movdqa  [rbp+0F0h+var_140], xmm0
0x180148038  movdqa  [rbp+0F0h+var_130], xmm1
0x18014803d  movdqa  [rbp+0F0h+var_120], xmm0
0x180148042  mov     [rbp+0F0h+var_168], r15
0x180148046  mov     [rbp+0F0h+var_110], r15
0x18014804a  mov     [rbp+0F0h+arg_0], r15b
0x180148051  call    ?FindNext@CacheApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplicationExtension &,bool &)
0x180148056  mov     ebx, eax
0x180148058  test    eax, eax
0x18014805a  jns     short loc_180148086
0x18014805c  mov     rcx, [rbp+0F8h]; this
0x180148063  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x18014806a  mov     r9d, eax; char *
0x18014806d  mov     edx, 2DCh; void *
0x180148072  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148077  lea     rcx, [rsp+1F0h+var_180]; this
0x18014807c  call    ??1CacheApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension(void)
0x180148081  jmp     loc_1801481D5
0x180148086  mov     rbx, r15
0x180148089  mov     rdi, r15
0x18014808c  mov     r14, r15
0x18014808f  cmp     [rbp+0F0h+arg_0], r15b
0x180148096  jz      loc_1801481E4
0x18014809c  mov     rdx, [rsp+1F0h+var_180]
0x1801480a1  lea     rax, [rbp+0F0h+arg_0]
0x1801480a8  xorps   xmm0, xmm0
0x1801480ab  mov     [rsp+1F0h+var_1D0], rax; int
0x1801480b0  xorps   xmm1, xmm1
0x1801480b3  movdqa  [rbp+0F0h+var_100], xmm0
0x1801480b8  lea     r9, [rbp+0F0h+var_100]
0x1801480bc  movdqa  [rbp+0F0h+var_E0], xmm0
0x1801480c1  mov     rcx, rsi
0x1801480c4  movdqa  [rbp+0F0h+var_D0], xmm1
0x1801480c9  mov     [rbp+0F0h+var_F0], 0
0x1801480d1  mov     [rbp+0F0h+var_E8], r15
0x1801480d5  mov     [rbp+0F0h+var_C0], r15
0x1801480d9  mov     [rbp+0F0h+var_B8], r15d
0x1801480dd  call    ?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1801480e2  mov     esi, eax
0x1801480e4  test    eax, eax
0x1801480e6  js      loc_1801481A5
0x1801480ec  cmp     [rbp+0F0h+arg_0], r15b
0x1801480f3  jz      short loc_18014813D
0x1801480f5  lea     r8, [rsp+1F0h+var_190]; unsigned __int64 *
0x1801480fa  mov     [rsp+1F0h+var_190], r15
0x1801480ff  lea     rdx, [rbp+0F0h+var_100]; struct StateRepository::Cache::Entity::ApplicationExtension_NoThrow *
0x180148103  lea     rcx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheApplicationExtension *
0x180148108  call    ?Cache_Check@CacheApplicationExtension@Entity@StateRepository@@CAJAEBV123@AEBVApplicationExtension_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheApplicationExtension::Cache_Check(StateRepository::Entity::CacheApplicationExtension const &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow const &,unsigned __int64 &)
0x18014810d  mov     esi, eax
0x18014810f  test    eax, eax
0x180148111  js      short loc_180148190
0x180148113  mov     r15, [rsp+1F0h+var_190]
0x180148118  test    r15, r15
0x18014811b  jz      short loc_180148135
0x18014811d  mov     rdx, [rsp+1F0h+var_180]; __int64
0x180148122  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180148127  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18014812c  mov     esi, eax
0x18014812e  test    eax, eax
0x180148130  js      short loc_180148189
0x180148132  add     rbx, r15
0x180148135  inc     r14
0x180148138  xor     r15d, r15d
0x18014813b  jmp     short loc_180148155
0x18014813d  mov     rdx, [rsp+1F0h+var_180]; __int64
0x180148142  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180148147  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18014814c  mov     esi, eax
0x18014814e  test    eax, eax
0x180148150  js      short loc_18014819E
0x180148152  inc     rbx
0x180148155  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18014815c  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheApplicationExtension *
0x180148161  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180148166  call    ?FindNext@CacheApplicationExtension@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplicationExtension::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplicationExtension &,bool &)
0x18014816b  mov     esi, eax
0x18014816d  test    eax, eax
0x18014816f  js      short loc_180148197
0x180148171  inc     rdi
0x180148174  lea     rcx, [rbp+0F0h+var_100]; this
0x180148178  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18014817d  mov     rsi, [rbp+0F0h+arg_8]
0x180148184  jmp     loc_18014808F
0x180148189  mov     edx, 2EAh
0x18014818e  jmp     short loc_1801481AA
0x180148190  mov     edx, 2E6h
0x180148195  jmp     short loc_1801481AA
0x180148197  mov     edx, 2F2h
0x18014819c  jmp     short loc_1801481AA
0x18014819e  mov     edx, 2F0h
0x1801481a3  jmp     short loc_1801481AA
0x1801481a5  mov     edx, 2E1h; void *
0x1801481aa  mov     rcx, [rbp+0F8h]; this
0x1801481b1  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x1801481b8  mov     r9d, esi; char *
0x1801481bb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801481c0  lea     rcx, [rbp+0F0h+var_100]; this
0x1801481c4  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x1801481c9  lea     rcx, [rsp+1F0h+var_180]; this
0x1801481ce  call    ??1CacheApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension(void)
0x1801481d3  mov     ebx, esi
0x1801481d5  lea     rcx, [rsp+1F0h+var_1A8]; this
0x1801481da  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1801481df  jmp     loc_180148454
0x1801481e4  sub     rdi, r14
0x1801481e7  jz      short loc_180148212
0x1801481e9  test    cs:byte_1804DF881, 20h
0x1801481f0  jz      short loc_180148212
0x1801481f2  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x1801481f7  lea     r8, aCacheapplicati; "CacheApplicationExtension"
0x1801481fe  mov     r9, rdi
0x180148201  mov     [rsp+1F0h+var_1D0], rax; int
0x180148206  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18014820d  call    McTemplateU0sxs_EventWriteTransfer
0x180148212  lea     rcx, [rsp+1F0h+var_180]; this
0x180148217  call    ??1CacheApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension(void)
0x18014821c  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180148221  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180148226  lea     rcx, [rsp+1F0h+var_1A0]; this
0x18014822b  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180148230  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180148233  mov     [rsp+1F0h+var_1C0], r15
0x180148238  lea     rcx, [rsp+1F0h+var_1C0]; this
0x18014823d  mov     [rsp+1F0h+var_1B8], r15d
0x180148242  mov     [rsp+1F0h+var_1B0], r15
0x180148247  call    ?Open@ApplicationExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18014824c  mov     edi, eax
0x18014824e  test    eax, eax
0x180148250  jns     short loc_1801482A4
0x180148252  mov     rcx, [rbp+0F8h]; this
0x180148259  lea     r8, aOnecoreBaseApp_294; "onecore\\base\\appmodel\\StateRepositor"...
0x180148260  mov     r9d, eax; char *
0x180148263  mov     edx, 3A6h; void *
0x180148268  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014826d  mov     rcx, [rbp+0F8h]; this
0x180148274  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x18014827b  mov     r9d, edi; char *
0x18014827e  mov     edx, 303h; void *
0x180148283  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180148288  mov     rcx, [rsp+1F0h+var_1C0]
0x18014828d  mov     [rsp+1F0h+var_1C0], r15
0x180148292  test    rcx, rcx
0x180148295  jz      short loc_18014829D
0x180148297  call    cs:__imp_SRCacheContext_Close
0x18014829d  mov     ebx, edi
0x18014829f  jmp     loc_180148454
0x1801482a4  xorps   xmm0, xmm0
0x1801482a7  mov     [rbp+0F0h+var_170], 0
0x1801482af  xorps   xmm1, xmm1
0x1801482b2  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x1801482b8  lea     r9, [rbp+0F0h+arg_0]
0x1801482bf  movdqa  [rbp+0F0h+var_160], xmm0
0x1801482c4  lea     r8, [rsp+1F0h+var_180]
0x1801482c9  movdqa  [rbp+0F0h+var_150], xmm1
0x1801482ce  lea     rcx, [rsp+1F0h+var_1C0]
0x1801482d3  mov     [rbp+0F0h+var_168], r15
0x1801482d7  mov     qword ptr [rbp+0F0h+var_140], r15
0x1801482db  mov     dword ptr [rbp+0F0h+var_140+8], r15d
0x1801482df  mov     [rbp+0F0h+arg_0], r15b
0x1801482e6  call    ?Get@ApplicationExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1801482eb  mov     edi, eax
0x1801482ed  test    eax, eax
0x1801482ef  jns     short loc_18014831B
0x1801482f1  mov     rcx, [rbp+0F8h]; this
0x1801482f8  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x1801482ff  mov     r9d, eax; char *
0x180148302  mov     edx, 306h; void *
0x180148307  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014830c  lea     rcx, [rsp+1F0h+var_180]; this
0x180148311  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x180148316  jmp     loc_180148288
0x18014831b  mov     rdi, r15
0x18014831e  cmp     [rbp+0F0h+arg_0], r15b
0x180148325  jz      loc_180148463
0x18014832b  mov     r9, [rsp+1F0h+var_180]; char *
0x180148330  lea     rax, [rbp+0F0h+arg_0]
0x180148337  xorps   xmm0, xmm0
0x18014833a  mov     [rsp+1F0h+var_1D0], rax; int
0x18014833f  xorps   xmm1, xmm1
0x180148342  movdqa  [rbp+0F0h+var_B0], xmm0
0x180148347  xor     r8d, r8d; char *
0x18014834a  movdqa  [rbp+0F0h+var_90], xmm0
0x18014834f  lea     rdx, aSelectExistsSe_648; "SELECT EXISTS(SELECT 1 FROM CacheApplic"...
0x180148356  movdqa  [rbp+0F0h+var_80], xmm1
0x18014835b  mov     rcx, r12; this
0x18014835e  movdqa  [rbp+0F0h+var_70], xmm0
0x180148366  movdqa  [rbp+0F0h+var_60], xmm1
0x18014836e  movdqa  [rbp+0F0h+var_50], xmm0
0x180148376  mov     [rbp+0F0h+var_A0], 0
0x18014837e  mov     [rbp+0F0h+var_98], r15
0x180148382  mov     [rbp+0F0h+var_40], r15
0x180148389  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18014838e  mov     esi, eax
0x180148390  test    eax, eax
0x180148392  js      short loc_1801483F4
0x180148394  cmp     [rbp+0F0h+arg_0], r15b
0x18014839b  jnz     short loc_1801483B8
0x18014839d  mov     rdx, [rsp+1F0h+var_180]; __int64
0x1801483a2  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1801483a7  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1801483ac  mov     esi, eax
0x1801483ae  test    eax, eax
0x1801483b0  js      short loc_1801483E6
0x1801483b2  inc     rdi
0x1801483b5  inc     rbx
0x1801483b8  inc     [rsp+1F0h+var_1B8]
0x1801483bc  lea     r9, [rbp+0F0h+arg_0]
0x1801483c3  lea     r8, [rsp+1F0h+var_180]
0x1801483c8  lea     rcx, [rsp+1F0h+var_1C0]
0x1801483cd  call    ?Get@ApplicationExtensionIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtensionIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)
0x1801483d2  mov     esi, eax
0x1801483d4  test    eax, eax
0x1801483d6  js      short loc_1801483ED
0x1801483d8  lea     rcx, [rbp+0F0h+var_B0]; this
0x1801483dc  call    ??1CacheApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension(void)
0x1801483e1  jmp     loc_18014831E
0x1801483e6  mov     edx, 30Fh
0x1801483eb  jmp     short loc_180148414
0x1801483ed  mov     edx, 311h
0x1801483f2  jmp     short loc_180148414
0x1801483f4  mov     rcx, [rbp+0F8h]; this
0x1801483fb  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x180148402  mov     r9d, esi; char *
0x180148405  mov     edx, 12Fh; void *
0x18014840a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014840f  mov     edx, 30Ah; void *
0x180148414  mov     rcx, [rbp+0F8h]; this
0x18014841b  lea     r8, aOnecoreBaseApp_405; "onecore\\base\\appmodel\\staterepositor"...
0x180148422  mov     r9d, esi; char *
0x180148425  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014842a  lea     rcx, [rbp+0F0h+var_B0]; this
0x18014842e  call    ??1CacheApplicationExtension@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplicationExtension::~CacheApplicationExtension(void)
0x180148433  lea     rcx, [rsp+1F0h+var_180]; this
0x180148438  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18014843d  mov     rcx, [rsp+1F0h+var_1C0]
0x180148442  mov     [rsp+1F0h+var_1C0], r15
0x180148447  test    rcx, rcx
0x18014844a  jz      short loc_180148452
0x18014844c  call    cs:__imp_SRCacheContext_Close
0x180148452  mov     ebx, esi
0x180148454  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180148459  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18014845e  jmp     loc_1801484EF
0x180148463  lea     rcx, [rsp+1F0h+var_180]; this
0x180148468  call    ??1ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::~ApplicationExtension_NoThrow(void)
0x18014846d  mov     rcx, [rsp+1F0h+var_1C0]
0x180148472  mov     [rsp+1F0h+var_1C0], r15
0x180148477  test    rcx, rcx
0x18014847a  jz      short loc_180148482
0x18014847c  call    cs:__imp_SRCacheContext_Close
0x180148482  test    rdi, rdi
0x180148485  jz      short loc_1801484B0
  ... truncated ...
```
