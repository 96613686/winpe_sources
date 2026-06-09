# StateRepository::Entity::CacheActivation::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1801715b0`
- end: `0x180171b31`
- name: `?Cache_CheckIntegrity@CacheActivation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1409`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x18004b338`
- `0x180062cd8`
- `0x180097ba8`
- `0x1800a5eb0`
- `0x1800ae890`
- `0x1801715b0`
- `0x180171b38`
- `0x18026544c`
- `0x18026db74`
- `0x18026e004`
- `0x18026e0cc`
- `0x18026e1ac`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801718d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171a7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171aaa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801718d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171a7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180171aaa`

## string_xrefs

- `0x18017162f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801716a4`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801717ea`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x1801718ad`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180171929`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180171a29`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180171a49`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180171b0e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheactivation.cpp`
- `0x180171892`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Activation.hpp`
- `0x180171830`: `CacheActivation`
- `0x180171ac3`: `CacheActivation`
- `0x180171980`: `SELECT EXISTS(SELECT 1 FROM CacheActivation WHERE _CacheActivationID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheActivation::Cache_CheckIntegrity(
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
  __int128 v60; // [rsp+E0h] [rbp-20h]
  __int128 v61; // [rsp+F0h] [rbp-10h] BYREF
  int v62; // [rsp+100h] [rbp+0h]
  __int64 v63; // [rsp+108h] [rbp+8h]
  __int128 v64; // [rsp+110h] [rbp+10h]
  __int128 v65; // [rsp+120h] [rbp+20h]
  __int64 v66; // [rsp+130h] [rbp+30h]
  __int128 v67; // [rsp+140h] [rbp+40h] BYREF
  __int64 v68; // [rsp+150h] [rbp+50h]
  int v69; // [rsp+158h] [rbp+58h]
  __int128 v70; // [rsp+160h] [rbp+60h]
  __int128 v71; // [rsp+170h] [rbp+70h]
  __int128 v72; // [rsp+180h] [rbp+80h]
  __int128 v73; // [rsp+190h] [rbp+90h]
  __int128 v74; // [rsp+1A0h] [rbp+A0h]
  __int128 v75; // [rsp+1B0h] [rbp+B0h]
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]
  bool v77; // [rsp+200h] [rbp+100h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v78; // [rsp+208h] [rbp+108h]
  _QWORD *v79; // [rsp+218h] [rbp+118h]

  v79 = a4;
  v78 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 601;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 602;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 603;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v48 = 0;
  v8 = StateRepository::Entity::CacheActivation::Find(a1, (struct StateRepository::Statement *)&v48);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x266,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
  v60 = 0;
  LODWORD(v54) = 0;
  v77 = 0;
  Next = StateRepository::Entity::CacheActivation::FindNext(
           (struct StateRepository::Statement *)&v48,
           (struct StateRepository::Entity::CacheActivation *)v52,
           &v77);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x269,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CacheActivation::~CacheActivation((StateRepository::Entity::CacheActivation *)v52);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v77 )
  {
    v41 = &v77;
    v61 = 0;
    v64 = 0;
    v65 = 0;
    v62 = 0;
    v63 = 0;
    v66 = 0;
    appended = StateRepository::Cache::Entity::Activation_NoThrow::Get(v4, v52[0], v11, &v61);
    if ( appended < 0 )
    {
      v19 = 622;
      goto LABEL_27;
    }
    if ( v77 )
    {
      v51 = 0;
      appended = StateRepository::Entity::CacheActivation::Cache_Check(
                   (const struct StateRepository::Entity::CacheActivation *)v52,
                   (const struct StateRepository::Cache::Entity::Activation_NoThrow *)&v61,
                   &v51);
      if ( appended < 0 )
      {
        v19 = 627;
        goto LABEL_27;
      }
      v18 = v51;
      if ( v51 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v17);
        if ( appended < 0 )
        {
          v19 = 631;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
            (const char *)(unsigned int)appended,
            (int)&v77);
          StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v61);
          StateRepository::Entity::CacheActivation::~CacheActivation((StateRepository::Entity::CacheActivation *)v52);
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
        v19 = 637;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheActivation::FindNext(
                 (struct StateRepository::Statement *)&v48,
                 (struct StateRepository::Entity::CacheActivation *)v52,
                 &v77);
    if ( appended < 0 )
    {
      v19 = 639;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)&v61);
    v4 = v78;
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheActivation",
      v20,
      *(__int64 *)v49);
  StateRepository::Entity::CacheActivation::~CacheActivation((StateRepository::Entity::CacheActivation *)v52);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
  StateRepository::TextA::Clear((StateRepository::TextA *)v49);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::ActivationIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::ActivationIterator_NoThrow *)&v45,
          v4);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x389,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x290,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
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
  LODWORD(v53) = 0;
  *(_OWORD *)v52 = 0;
  v55 = 0;
  v56 = 0;
  v54 = 0;
  *(_QWORD *)&v57 = 0;
  v77 = 0;
  v27 = StateRepository::Cache::Entity::ActivationIterator_NoThrow::Get(&v45, v22, v52, &v77);
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x293,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)v52);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v77 )
  {
    v67 = 0;
    v70 = 0;
    v71 = 0;
    v72 = 0;
    v73 = 0;
    v74 = 0;
    v75 = 0;
    v68 = 0;
    v69 = 0;
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheActivation WHERE _CacheActivationID=? LIMIT 1);",
            0,
            v52[0],
            (__int64)&v77,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 663;
      goto LABEL_50;
    }
    if ( !v77 )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v31);
      if ( v32 < 0 )
      {
        v33 = 668;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheactivation.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CacheActivation::~CacheActivation((StateRepository::Entity::CacheActivation *)&v67);
        StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)v52);
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
    v32 = StateRepository::Cache::Entity::ActivationIterator_NoThrow::Get(&v45, v30, v52, &v77);
    if ( v32 < 0 )
    {
      v33 = 670;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheActivation::~CacheActivation((StateRepository::Entity::CacheActivation *)&v67);
  }
  StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow((StateRepository::Cache::Entity::Activation_NoThrow *)v52);
  v39 = v45;
  v45 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheActivation",
      v28,
      *(__int64 *)v49);
  *v79 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v49);
  return 0;
}

```

## disassembly

```asm
0x1801715b0  mov     [rsp-8+arg_18], r9
0x1801715b5  mov     [rsp-8+arg_8], rdx
0x1801715ba  push    rbp
0x1801715bb  push    rbx
0x1801715bc  push    rsi
0x1801715bd  push    rdi
0x1801715be  push    r12
0x1801715c0  push    r14
0x1801715c2  push    r15
0x1801715c4  lea     rbp, [rsp-0C0h]
0x1801715cc  sub     rsp, 1C0h
0x1801715d3  xor     r15d, r15d
0x1801715d6  mov     rsi, rdx
0x1801715d9  mov     r12, rcx
0x1801715dc  cmp     [rcx], r15
0x1801715df  jz      loc_180171AFD
0x1801715e5  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1801715ea  test    al, al
0x1801715ec  jz      short loc_1801715FD
0x1801715ee  mov     ebx, 8067000Bh
0x1801715f3  mov     edx, 25Ah
0x1801715f8  jmp     loc_180171B07
0x1801715fd  cmp     [rsi], r15
0x180171600  jz      loc_180171AF6
0x180171606  lea     rdx, [rsp+1F0h+var_1A8]; struct StateRepository::Statement *
0x18017160b  mov     qword ptr [rsp+1F0h+var_1A0], r15
0x180171610  mov     rcx, r12; struct StateRepository::Database *
0x180171613  mov     [rsp+1F0h+var_198], r15
0x180171618  mov     [rsp+1F0h+var_1A8], r15
0x18017161d  call    ?Find@CacheActivation@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheActivation::Find(StateRepository::Database &,StateRepository::Statement &)
0x180171622  mov     ebx, eax
0x180171624  test    eax, eax
0x180171626  jns     short loc_180171648
0x180171628  mov     rcx, [rbp+0F8h]; this
0x18017162f  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180171636  mov     r9d, eax; char *
0x180171639  mov     edx, 266h; void *
0x18017163e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171643  jmp     loc_18017180E
0x180171648  xorps   xmm0, xmm0
0x18017164b  mov     [rbp+0F0h+var_170], r15
0x18017164f  xorps   xmm1, xmm1
0x180171652  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x180171658  lea     r8, [rbp+0F0h+arg_0]; bool *
0x18017165f  movdqa  [rbp+0F0h+var_160], xmm0
0x180171664  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheActivation *
0x180171669  movdqa  [rbp+0F0h+var_150], xmm1
0x18017166e  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180171673  movdqa  [rbp+0F0h+var_140], xmm0
0x180171678  movdqa  [rbp+0F0h+var_130], xmm1
0x18017167d  movdqa  [rbp+0F0h+var_120], xmm0
0x180171682  movdqa  [rbp+0F0h+var_110], xmm1
0x180171687  mov     dword ptr [rbp+0F0h+var_168], r15d
0x18017168b  mov     [rbp+0F0h+arg_0], r15b
0x180171692  call    ?FindNext@CacheActivation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheActivation::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheActivation &,bool &)
0x180171697  mov     ebx, eax
0x180171699  test    eax, eax
0x18017169b  jns     short loc_1801716C7
0x18017169d  mov     rcx, [rbp+0F8h]; this
0x1801716a4  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801716ab  mov     r9d, eax; char *
0x1801716ae  mov     edx, 269h; void *
0x1801716b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801716b8  lea     rcx, [rsp+1F0h+var_180]; this
0x1801716bd  call    ??1CacheActivation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheActivation::~CacheActivation(void)
0x1801716c2  jmp     loc_18017180E
0x1801716c7  mov     rbx, r15
0x1801716ca  mov     rdi, r15
0x1801716cd  mov     r14, r15
0x1801716d0  cmp     [rbp+0F0h+arg_0], r15b
0x1801716d7  jz      loc_18017181D
0x1801716dd  mov     rdx, [rsp+1F0h+var_180]
0x1801716e2  lea     rax, [rbp+0F0h+arg_0]
0x1801716e9  xorps   xmm0, xmm0
0x1801716ec  mov     [rsp+1F0h+var_1D0], rax; int
0x1801716f1  xorps   xmm1, xmm1
0x1801716f4  movdqa  [rbp+0F0h+var_100], xmm0
0x1801716f9  lea     r9, [rbp+0F0h+var_100]
0x1801716fd  movdqa  [rbp+0F0h+var_E0], xmm0
0x180171702  mov     rcx, rsi
0x180171705  movdqa  [rbp+0F0h+var_D0], xmm1
0x18017170a  mov     [rbp+0F0h+var_F0], r15d
0x18017170e  mov     [rbp+0F0h+var_E8], r15
0x180171712  mov     [rbp+0F0h+var_C0], r15
0x180171716  call    ?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18017171b  mov     esi, eax
0x18017171d  test    eax, eax
0x18017171f  js      loc_1801717DE
0x180171725  cmp     [rbp+0F0h+arg_0], r15b
0x18017172c  jz      short loc_180171776
0x18017172e  lea     r8, [rsp+1F0h+var_190]; unsigned __int64 *
0x180171733  mov     [rsp+1F0h+var_190], r15
0x180171738  lea     rdx, [rbp+0F0h+var_100]; struct StateRepository::Cache::Entity::Activation_NoThrow *
0x18017173c  lea     rcx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheActivation *
0x180171741  call    ?Cache_Check@CacheActivation@Entity@StateRepository@@CAJAEBV123@AEBVActivation_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheActivation::Cache_Check(StateRepository::Entity::CacheActivation const &,StateRepository::Cache::Entity::Activation_NoThrow const &,unsigned __int64 &)
0x180171746  mov     esi, eax
0x180171748  test    eax, eax
0x18017174a  js      short loc_1801717C9
0x18017174c  mov     r15, [rsp+1F0h+var_190]
0x180171751  test    r15, r15
0x180171754  jz      short loc_18017176E
0x180171756  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18017175b  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180171760  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180171765  mov     esi, eax
0x180171767  test    eax, eax
0x180171769  js      short loc_1801717C2
0x18017176b  add     rbx, r15
0x18017176e  inc     r14
0x180171771  xor     r15d, r15d
0x180171774  jmp     short loc_18017178E
0x180171776  mov     rdx, [rsp+1F0h+var_180]; __int64
0x18017177b  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180171780  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180171785  mov     esi, eax
0x180171787  test    eax, eax
0x180171789  js      short loc_1801717D7
0x18017178b  inc     rbx
0x18017178e  lea     r8, [rbp+0F0h+arg_0]; bool *
0x180171795  lea     rdx, [rsp+1F0h+var_180]; struct StateRepository::Entity::CacheActivation *
0x18017179a  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18017179f  call    ?FindNext@CacheActivation@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheActivation::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheActivation &,bool &)
0x1801717a4  mov     esi, eax
0x1801717a6  test    eax, eax
0x1801717a8  js      short loc_1801717D0
0x1801717aa  inc     rdi
0x1801717ad  lea     rcx, [rbp+0F0h+var_100]; this
0x1801717b1  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x1801717b6  mov     rsi, [rbp+0F0h+arg_8]
0x1801717bd  jmp     loc_1801716D0
0x1801717c2  mov     edx, 277h
0x1801717c7  jmp     short loc_1801717E3
0x1801717c9  mov     edx, 273h
0x1801717ce  jmp     short loc_1801717E3
0x1801717d0  mov     edx, 27Fh
0x1801717d5  jmp     short loc_1801717E3
0x1801717d7  mov     edx, 27Dh
0x1801717dc  jmp     short loc_1801717E3
0x1801717de  mov     edx, 26Eh; void *
0x1801717e3  mov     rcx, [rbp+0F8h]; this
0x1801717ea  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801717f1  mov     r9d, esi; char *
0x1801717f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801717f9  lea     rcx, [rbp+0F0h+var_100]; this
0x1801717fd  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180171802  lea     rcx, [rsp+1F0h+var_180]; this
0x180171807  call    ??1CacheActivation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheActivation::~CacheActivation(void)
0x18017180c  mov     ebx, esi
0x18017180e  lea     rcx, [rsp+1F0h+var_1A8]; this
0x180171813  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180171818  jmp     loc_180171A82
0x18017181d  sub     rdi, r14
0x180171820  jz      short loc_18017184B
0x180171822  test    cs:byte_1804DF881, 20h
0x180171829  jz      short loc_18017184B
0x18017182b  mov     rax, qword ptr [rsp+1F0h+var_1A0]
0x180171830  lea     r8, aCacheactivatio; "CacheActivation"
0x180171837  mov     r9, rdi
0x18017183a  mov     [rsp+1F0h+var_1D0], rax; int
0x18017183f  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180171846  call    McTemplateU0sxs_EventWriteTransfer
0x18017184b  lea     rcx, [rsp+1F0h+var_180]; this
0x180171850  call    ??1CacheActivation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheActivation::~CacheActivation(void)
0x180171855  lea     rcx, [rsp+1F0h+var_1A8]; this
0x18017185a  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18017185f  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180171864  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180171869  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18017186c  mov     [rsp+1F0h+var_1C0], r15
0x180171871  lea     rcx, [rsp+1F0h+var_1C0]; this
0x180171876  mov     [rsp+1F0h+var_1B8], r15d
0x18017187b  mov     [rsp+1F0h+var_1B0], r15
0x180171880  call    ?Open@ActivationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::ActivationIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180171885  mov     edi, eax
0x180171887  test    eax, eax
0x180171889  jns     short loc_1801718DD
0x18017188b  mov     rcx, [rbp+0F8h]; this
0x180171892  lea     r8, aOnecoreBaseApp_110; "onecore\\base\\appmodel\\StateRepositor"...
0x180171899  mov     r9d, eax; char *
0x18017189c  mov     edx, 389h; void *
0x1801718a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801718a6  mov     rcx, [rbp+0F8h]; this
0x1801718ad  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x1801718b4  mov     r9d, edi; char *
0x1801718b7  mov     edx, 290h; void *
0x1801718bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801718c1  mov     rcx, [rsp+1F0h+var_1C0]
0x1801718c6  mov     [rsp+1F0h+var_1C0], r15
0x1801718cb  test    rcx, rcx
0x1801718ce  jz      short loc_1801718D6
0x1801718d0  call    cs:__imp_SRCacheContext_Close
0x1801718d6  mov     ebx, edi
0x1801718d8  jmp     loc_180171A82
0x1801718dd  xorps   xmm0, xmm0
0x1801718e0  mov     dword ptr [rbp+0F0h+var_170], r15d
0x1801718e4  xorps   xmm1, xmm1
0x1801718e7  movdqa  xmmword ptr [rsp+1F0h+var_180], xmm0
0x1801718ed  lea     r9, [rbp+0F0h+arg_0]
0x1801718f4  movdqa  [rbp+0F0h+var_160], xmm0
0x1801718f9  lea     r8, [rsp+1F0h+var_180]
0x1801718fe  movdqa  [rbp+0F0h+var_150], xmm1
0x180171903  lea     rcx, [rsp+1F0h+var_1C0]
0x180171908  mov     [rbp+0F0h+var_168], r15
0x18017190c  mov     qword ptr [rbp+0F0h+var_140], r15
0x180171910  mov     [rbp+0F0h+arg_0], r15b
0x180171917  call    ?Get@ActivationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Activation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ActivationIterator_NoThrow::Get(StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x18017191c  mov     edi, eax
0x18017191e  test    eax, eax
0x180171920  jns     short loc_18017194C
0x180171922  mov     rcx, [rbp+0F8h]; this
0x180171929  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180171930  mov     r9d, eax; char *
0x180171933  mov     edx, 293h; void *
0x180171938  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18017193d  lea     rcx, [rsp+1F0h+var_180]; this
0x180171942  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180171947  jmp     loc_1801718C1
0x18017194c  mov     rdi, r15
0x18017194f  cmp     [rbp+0F0h+arg_0], r15b
0x180171956  jz      loc_180171A91
0x18017195c  mov     r9, [rsp+1F0h+var_180]; char *
0x180171961  lea     rax, [rbp+0F0h+arg_0]
0x180171968  xorps   xmm0, xmm0
0x18017196b  mov     [rsp+1F0h+var_1D0], rax; int
0x180171970  xorps   xmm1, xmm1
0x180171973  movdqa  [rbp+0F0h+var_B0], xmm0
0x180171978  xor     r8d, r8d; char *
0x18017197b  movdqa  [rbp+0F0h+var_90], xmm0
0x180171980  lea     rdx, aSelectExistsSe_375; "SELECT EXISTS(SELECT 1 FROM CacheActiva"...
0x180171987  movdqa  [rbp+0F0h+var_80], xmm1
0x18017198c  mov     rcx, r12; this
0x18017198f  movdqa  [rbp+0F0h+var_70], xmm0
0x180171997  movdqa  [rbp+0F0h+var_60], xmm1
0x18017199f  movdqa  [rbp+0F0h+var_50], xmm0
0x1801719a7  movdqa  [rbp+0F0h+var_40], xmm1
0x1801719af  mov     [rbp+0F0h+var_A0], r15
0x1801719b3  mov     [rbp+0F0h+var_98], r15d
0x1801719b7  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x1801719bc  mov     esi, eax
0x1801719be  test    eax, eax
0x1801719c0  js      short loc_180171A22
0x1801719c2  cmp     [rbp+0F0h+arg_0], r15b
0x1801719c9  jnz     short loc_1801719E6
0x1801719cb  mov     rdx, [rsp+1F0h+var_180]; __int64
0x1801719d0  lea     rcx, [rsp+1F0h+var_1A0]; this
0x1801719d5  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1801719da  mov     esi, eax
0x1801719dc  test    eax, eax
0x1801719de  js      short loc_180171A14
0x1801719e0  inc     rdi
0x1801719e3  inc     rbx
0x1801719e6  inc     [rsp+1F0h+var_1B8]
0x1801719ea  lea     r9, [rbp+0F0h+arg_0]
0x1801719f1  lea     r8, [rsp+1F0h+var_180]
0x1801719f6  lea     rcx, [rsp+1F0h+var_1C0]
0x1801719fb  call    ?Get@ActivationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Activation_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ActivationIterator_NoThrow::Get(StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)
0x180171a00  mov     esi, eax
0x180171a02  test    eax, eax
0x180171a04  js      short loc_180171A1B
0x180171a06  lea     rcx, [rbp+0F0h+var_B0]; this
0x180171a0a  call    ??1CacheActivation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheActivation::~CacheActivation(void)
0x180171a0f  jmp     loc_18017194F
0x180171a14  mov     edx, 29Ch
0x180171a19  jmp     short loc_180171A42
0x180171a1b  mov     edx, 29Eh
0x180171a20  jmp     short loc_180171A42
0x180171a22  mov     rcx, [rbp+0F8h]; this
0x180171a29  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180171a30  mov     r9d, esi; char *
0x180171a33  mov     edx, 139h; void *
0x180171a38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171a3d  mov     edx, 297h; void *
0x180171a42  mov     rcx, [rbp+0F8h]; this
0x180171a49  lea     r8, aOnecoreBaseApp_8; "onecore\\base\\appmodel\\staterepositor"...
0x180171a50  mov     r9d, esi; char *
0x180171a53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180171a58  lea     rcx, [rbp+0F0h+var_B0]; this
0x180171a5c  call    ??1CacheActivation@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheActivation::~CacheActivation(void)
0x180171a61  lea     rcx, [rsp+1F0h+var_180]; this
0x180171a66  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180171a6b  mov     rcx, [rsp+1F0h+var_1C0]
0x180171a70  mov     [rsp+1F0h+var_1C0], r15
0x180171a75  test    rcx, rcx
0x180171a78  jz      short loc_180171A80
0x180171a7a  call    cs:__imp_SRCacheContext_Close
0x180171a80  mov     ebx, esi
0x180171a82  lea     rcx, [rsp+1F0h+var_1A0]; this
0x180171a87  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180171a8c  jmp     loc_180171B1D
0x180171a91  lea     rcx, [rsp+1F0h+var_180]; this
0x180171a96  call    ??1Activation_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Activation_NoThrow::~Activation_NoThrow(void)
0x180171a9b  mov     rcx, [rsp+1F0h+var_1C0]
0x180171aa0  mov     [rsp+1F0h+var_1C0], r15
0x180171aa5  test    rcx, rcx
0x180171aa8  jz      short loc_180171AB0
0x180171aaa  call    cs:__imp_SRCacheContext_Close
0x180171ab0  test    rdi, rdi
0x180171ab3  jz      short loc_180171ADE
0x180171ab5  test    cs:byte_1804DF881, 20h
0x180171abc  jz      short loc_180171ADE
  ... truncated ...
```
