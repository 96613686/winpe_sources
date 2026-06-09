# StateRepository::Entity::CacheDependencyGraph::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180270220`
- end: `0x18027064f`
- name: `?Cache_CheckIntegrity@CacheDependencyGraph@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1071`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x18004e1dc`
- `0x180062cd8`
- `0x1800ae890`
- `0x18026544c`
- `0x18027007c`
- `0x180270220`
- `0x18027074c`
- `0x180270814`
- `0x1802708f4`
- `0x1802755a8`
- `0x180275b1c`
- `0x1802787c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802704aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802705a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802705c7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802704aa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802705a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1802705c7`

## string_xrefs

- `0x1802702f0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x1802703f1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18027048e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18027056e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x18027058b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x180270623`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph.cpp`
- `0x180270471`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DependencyGraph.hpp`
- `0x180270422`: `CacheDependencyGraph`
- `0x1802705df`: `CacheDependencyGraph`
- `0x18027050e`: `SELECT EXISTS(SELECT 1 FROM CacheDependencyGraph WHERE _CacheDependencyGraphID=? LIMIT 1);`
- `0x180270297`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedependencygraph-custom.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDependencyGraph::Cache_CheckIntegrity(
        StateRepository::Database *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        _QWORD *a4)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  __int64 v8; // rdx
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int Next; // eax
  int v13; // ecx
  __int64 v14; // r8
  __int64 v15; // rbx
  __int64 v16; // rdi
  __int64 v17; // r14
  int appended; // esi
  char v19; // r8
  char v20; // r8
  unsigned __int64 v21; // r15
  __int64 v22; // rdx
  __int64 v23; // rdi
  int v24; // eax
  __int64 v25; // rdx
  int v26; // edi
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdi
  int v30; // eax
  __int64 v31; // rdx
  char v32; // r8
  int v33; // esi
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rcx
  bool *v38; // [rsp+20h] [rbp-89h]
  int v39; // [rsp+20h] [rbp-89h]
  bool *v40; // [rsp+28h] [rbp-81h]
  __int64 v41; // [rsp+30h] [rbp-79h] BYREF
  __int64 v42[2]; // [rsp+38h] [rbp-71h] BYREF
  __int128 v43; // [rsp+48h] [rbp-61h]
  __int64 v44; // [rsp+58h] [rbp-51h]
  int v45[2]; // [rsp+60h] [rbp-49h] BYREF
  __int64 v46; // [rsp+68h] [rbp-41h]
  unsigned __int64 v47; // [rsp+70h] [rbp-39h] BYREF
  char *v48[2]; // [rsp+78h] [rbp-31h] BYREF
  __int128 v49; // [rsp+88h] [rbp-21h]
  __int64 v50; // [rsp+98h] [rbp-11h]
  _OWORD v51[2]; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v52; // [rsp+C0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  bool v54; // [rsp+110h] [rbp+67h] BYREF
  _QWORD *v55; // [rsp+128h] [rbp+7Fh]

  v55 = a4;
  if ( !*(_QWORD *)a1 )
  {
    v8 = 337;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v7 = -2140733429;
    v8 = 338;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)v7,
      (int)v38);
    return v7;
  }
  if ( !*(_QWORD *)a2 )
  {
    v8 = 339;
LABEL_62:
    v7 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v45 = 0;
  v46 = 0;
  v41 = 0;
  v9 = StateRepository::Entity::CacheDependencyGraph::FindByDependencyType(a1, v6, &v41);
  v7 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph-custom.cpp",
      (const char *)(unsigned int)v9,
      (int)v38);
    v10 = v7;
    v11 = 350;
    goto LABEL_9;
  }
  v44 = 0;
  v54 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  Next = StateRepository::Entity::CacheDependencyGraph::FindNext(
           (struct StateRepository::Statement *)&v41,
           (struct StateRepository::Entity::CacheDependencyGraph *)v42,
           &v54);
  v7 = Next;
  if ( Next < 0 )
  {
    v10 = (unsigned int)Next;
    v11 = 353;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)v10,
      (int)v38);
LABEL_29:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
    goto LABEL_53;
  }
  v15 = 0;
  v16 = 0;
  v17 = 0;
  while ( v54 )
  {
    v38 = &v54;
    v52 = 0;
    memset(v51, 0, sizeof(v51));
    appended = StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(a2, v42[0], v14, v51);
    if ( appended < 0 )
    {
      v22 = 358;
      goto LABEL_28;
    }
    if ( v54 )
    {
      v47 = 0;
      appended = StateRepository::Entity::CacheDependencyGraph::Cache_Check(
                   (const struct StateRepository::Entity::CacheDependencyGraph *)v42,
                   (const struct StateRepository::Cache::Entity::DependencyGraph_NoThrow *)v51,
                   &v47);
      if ( appended < 0 )
      {
        v22 = 363;
        goto LABEL_28;
      }
      v21 = v47;
      if ( v47 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v45, v42[0], v20);
        if ( appended < 0 )
        {
          v22 = 367;
LABEL_28:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
            (const char *)(unsigned int)appended,
            (int)&v54);
          v7 = appended;
          goto LABEL_29;
        }
        v15 += v21;
      }
      ++v17;
    }
    else
    {
      appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v45, v42[0], v19);
      if ( appended < 0 )
      {
        v22 = 373;
        goto LABEL_28;
      }
      ++v15;
    }
    appended = StateRepository::Entity::CacheDependencyGraph::FindNext(
                 (struct StateRepository::Statement *)&v41,
                 (struct StateRepository::Entity::CacheDependencyGraph *)v42,
                 &v54);
    if ( appended < 0 )
    {
      v22 = 375;
      goto LABEL_28;
    }
    ++v16;
  }
  v23 = v16 - v17;
  if ( v23 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v13,
      (unsigned int)&CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheDependencyGraph",
      v23,
      *(__int64 *)v45);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v41);
  StateRepository::TextA::Clear((StateRepository::TextA *)v45);
  v42[0] = 0;
  LODWORD(v42[1]) = 0;
  *(_QWORD *)&v43 = 0;
  v24 = StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow *)v42,
          a2);
  v26 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23F,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DependencyGraph.hpp",
      (const char *)(unsigned int)v24,
      (int)v38);
    v27 = 392;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v27,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
      (const char *)(unsigned int)v26,
      (int)v38);
    v28 = v42[0];
    v42[0] = 0;
    if ( v28 )
      SRCacheContext_Close(v28);
    v7 = v26;
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v45);
    return v7;
  }
  v50 = 0;
  v54 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  v26 = StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Get(v42, v25, v48, &v54);
  if ( v26 < 0 )
  {
    v27 = 395;
    goto LABEL_35;
  }
  v29 = 0;
  while ( v54 )
  {
    v30 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheDependencyGraph WHERE _CacheDependencyG"
                                                "raphID=? LIMIT 1);",
            0,
            v48[0],
            (__int64)&v54,
            v40);
    v33 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
        (const char *)(unsigned int)v30,
        v39);
      v34 = 399;
      goto LABEL_50;
    }
    if ( !v54 )
    {
      v33 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v45, (__int64)v48[0], v32);
      if ( v33 < 0 )
      {
        v34 = 404;
        goto LABEL_50;
      }
      ++v29;
      ++v15;
    }
    ++LODWORD(v42[1]);
    v33 = StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Get(v42, v31, v48, &v54);
    if ( v33 < 0 )
    {
      v34 = 406;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v34,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedependencygraph.cpp",
        (const char *)(unsigned int)v33,
        v39);
      v35 = v42[0];
      v42[0] = 0;
      if ( v35 )
        SRCacheContext_Close(v35);
      v7 = v33;
      goto LABEL_53;
    }
  }
  v36 = v42[0];
  v42[0] = 0;
  if ( v36 )
    SRCacheContext_Close(v36);
  if ( v29 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v36,
      (unsigned int)&CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheDependencyGraph",
      v29,
      *(__int64 *)v45);
  *v55 = v15;
  StateRepository::TextA::Reset((StateRepository::TextA *)v45);
  return 0;
}

```

## disassembly

```asm
0x180270220  mov     [rsp-8+arg_8], rbx
0x180270225  mov     [rsp-8+arg_18], r9
0x18027022a  push    rbp
0x18027022b  push    rsi
0x18027022c  push    rdi
0x18027022d  push    r12
0x18027022f  push    r13
0x180270231  push    r14
0x180270233  push    r15
0x180270235  lea     rbp, [rsp-27h]
0x18027023a  sub     rsp, 0D0h
0x180270241  xor     r15d, r15d
0x180270244  mov     r13, rdx
0x180270247  mov     r12, rcx
0x18027024a  cmp     [rcx], r15
0x18027024d  jz      loc_180270615
0x180270253  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180270258  test    al, al
0x18027025a  jz      short loc_18027026B
0x18027025c  mov     ebx, 8067000Bh
0x180270261  mov     edx, 152h
0x180270266  jmp     loc_18027061F
0x18027026b  cmp     [r13+0], r15
0x18027026f  jz      loc_18027060E
0x180270275  lea     r8, [rbp+57h+var_D0]
0x180270279  mov     qword ptr [rbp+57h+var_A0], r15
0x18027027d  mov     rcx, r12
0x180270280  mov     [rbp+57h+var_98], r15
0x180270284  mov     [rbp+57h+var_D0], r15
0x180270288  call    ?FindByDependencyType@CacheDependencyGraph@Entity@StateRepository@@SAJAEAVDatabase@3@W4DependencyGraphType@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheDependencyGraph::FindByDependencyType(StateRepository::Database &,StateRepository::DependencyGraphType,StateRepository::Statement &)
0x18027028d  mov     ebx, eax
0x18027028f  test    eax, eax
0x180270291  jns     short loc_1802702B5
0x180270293  mov     rcx, [rbp+5Fh]; this
0x180270297  lea     r8, aOnecoreBaseApp_401; "onecore\\base\\appmodel\\staterepositor"...
0x18027029e  mov     r9d, eax; char *
0x1802702a1  mov     edx, 0Fh; void *
0x1802702a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802702ab  mov     r9d, ebx
0x1802702ae  mov     edx, 15Eh
0x1802702b3  jmp     short loc_1802702EC
0x1802702b5  xorps   xmm0, xmm0
0x1802702b8  mov     [rbp+57h+var_A8], r15
0x1802702bc  xorps   xmm1, xmm1
0x1802702bf  mov     [rbp+57h+arg_0], r15b
0x1802702c3  lea     r8, [rbp+57h+arg_0]; bool *
0x1802702c7  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDependencyGraph *
0x1802702cb  lea     rcx, [rbp+57h+var_D0]; struct StateRepository::Statement *
0x1802702cf  movdqu  xmmword ptr [rbp+57h+var_C8], xmm0
0x1802702d4  movdqu  [rbp+57h+var_B8], xmm1
0x1802702d9  call    ?FindNext@CacheDependencyGraph@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDependencyGraph::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDependencyGraph &,bool &)
0x1802702de  mov     ebx, eax
0x1802702e0  test    eax, eax
0x1802702e2  jns     short loc_180270301
0x1802702e4  mov     r9d, eax; char *
0x1802702e7  mov     edx, 161h; void *
0x1802702ec  mov     rcx, [rbp+5Fh]; this
0x1802702f0  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x1802702f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802702fc  jmp     loc_180270402
0x180270301  mov     rbx, r15
0x180270304  mov     rdi, r15
0x180270307  mov     r14, r15
0x18027030a  cmp     [rbp+57h+arg_0], r15b
0x18027030e  jz      loc_180270410
0x180270314  mov     rdx, [rbp+57h+var_C8]
0x180270318  lea     rax, [rbp+57h+arg_0]
0x18027031c  xorps   xmm0, xmm0
0x18027031f  mov     [rsp+100h+var_E0], rax; int
0x180270324  xorps   xmm1, xmm1
0x180270327  mov     [rbp+57h+var_40], 0
0x18027032f  lea     r9, [rbp+57h+var_60]
0x180270333  mov     rcx, r13
0x180270336  movdqu  [rbp+57h+var_60], xmm0
0x18027033b  movdqu  [rbp+57h+var_50], xmm1
0x180270340  call    ?Get@DependencyGraph_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::DependencyGraph_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::DependencyGraph_NoThrow::CacheFlags,StateRepository::Cache::Entity::DependencyGraph_NoThrow &,bool &)
0x180270345  mov     esi, eax
0x180270347  test    eax, eax
0x180270349  js      loc_1802703E8
0x18027034f  cmp     [rbp+57h+arg_0], r15b
0x180270353  jz      short loc_180270397
0x180270355  lea     r8, [rbp+57h+var_90]; unsigned __int64 *
0x180270359  mov     [rbp+57h+var_90], r15
0x18027035d  lea     rdx, [rbp+57h+var_60]; struct StateRepository::Cache::Entity::DependencyGraph_NoThrow *
0x180270361  lea     rcx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDependencyGraph *
0x180270365  call    ?Cache_Check@CacheDependencyGraph@Entity@StateRepository@@CAJAEBV123@AEBVDependencyGraph_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheDependencyGraph::Cache_Check(StateRepository::Entity::CacheDependencyGraph const &,StateRepository::Cache::Entity::DependencyGraph_NoThrow const &,unsigned __int64 &)
0x18027036a  mov     esi, eax
0x18027036c  test    eax, eax
0x18027036e  js      short loc_1802703D3
0x180270370  mov     r15, [rbp+57h+var_90]
0x180270374  test    r15, r15
0x180270377  jz      short loc_18027038F
0x180270379  mov     rdx, [rbp+57h+var_C8]; __int64
0x18027037d  lea     rcx, [rbp+57h+var_A0]; this
0x180270381  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180270386  mov     esi, eax
0x180270388  test    eax, eax
0x18027038a  js      short loc_1802703CC
0x18027038c  add     rbx, r15
0x18027038f  inc     r14
0x180270392  xor     r15d, r15d
0x180270395  jmp     short loc_1802703AD
0x180270397  mov     rdx, [rbp+57h+var_C8]; __int64
0x18027039b  lea     rcx, [rbp+57h+var_A0]; this
0x18027039f  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1802703a4  mov     esi, eax
0x1802703a6  test    eax, eax
0x1802703a8  js      short loc_1802703E1
0x1802703aa  inc     rbx
0x1802703ad  lea     r8, [rbp+57h+arg_0]; bool *
0x1802703b1  lea     rdx, [rbp+57h+var_C8]; struct StateRepository::Entity::CacheDependencyGraph *
0x1802703b5  lea     rcx, [rbp+57h+var_D0]; struct StateRepository::Statement *
0x1802703b9  call    ?FindNext@CacheDependencyGraph@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheDependencyGraph::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheDependencyGraph &,bool &)
0x1802703be  mov     esi, eax
0x1802703c0  test    eax, eax
0x1802703c2  js      short loc_1802703DA
0x1802703c4  inc     rdi
0x1802703c7  jmp     loc_18027030A
0x1802703cc  mov     edx, 16Fh
0x1802703d1  jmp     short loc_1802703ED
0x1802703d3  mov     edx, 16Bh
0x1802703d8  jmp     short loc_1802703ED
0x1802703da  mov     edx, 177h
0x1802703df  jmp     short loc_1802703ED
0x1802703e1  mov     edx, 175h
0x1802703e6  jmp     short loc_1802703ED
0x1802703e8  mov     edx, 166h; void *
0x1802703ed  mov     rcx, [rbp+5Fh]; this
0x1802703f1  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x1802703f8  mov     r9d, esi; char *
0x1802703fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270400  mov     ebx, esi
0x180270402  lea     rcx, [rbp+57h+var_D0]; this
0x180270406  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18027040b  jmp     loc_1802705AF
0x180270410  sub     rdi, r14
0x180270413  jz      short loc_18027043D
0x180270415  test    cs:byte_1804DF881, 20h
0x18027041c  jz      short loc_18027043D
0x18027041e  mov     rax, qword ptr [rbp+57h+var_A0]
0x180270422  lea     r8, aCachedependenc; "CacheDependencyGraph"
0x180270429  mov     r9, rdi
0x18027042c  mov     [rsp+100h+var_E0], rax; int
0x180270431  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180270438  call    McTemplateU0sxs_EventWriteTransfer
0x18027043d  lea     rcx, [rbp+57h+var_D0]; this
0x180270441  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180270446  lea     rcx, [rbp+57h+var_A0]; this
0x18027044a  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18027044f  mov     rdx, r13; struct StateRepository::Cache::Manager_NoThrow *
0x180270452  mov     [rbp+57h+var_C8], r15
0x180270456  lea     rcx, [rbp+57h+var_C8]; this
0x18027045a  mov     dword ptr [rbp+57h+var_C8+8], r15d
0x18027045e  mov     qword ptr [rbp+57h+var_B8], r15
0x180270462  call    ?Open@DependencyGraphIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180270467  mov     edi, eax
0x180270469  test    eax, eax
0x18027046b  jns     short loc_1802704B7
0x18027046d  mov     rcx, [rbp+5Fh]; this
0x180270471  lea     r8, aOnecoreBaseApp_296; "onecore\\base\\appmodel\\StateRepositor"...
0x180270478  mov     r9d, eax; char *
0x18027047b  mov     edx, 23Fh; void *
0x180270480  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270485  mov     edx, 188h; void *
0x18027048a  mov     rcx, [rbp+5Fh]; this
0x18027048e  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x180270495  mov     r9d, edi; char *
0x180270498  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027049d  mov     rcx, [rbp+57h+var_C8]
0x1802704a1  mov     [rbp+57h+var_C8], r15
0x1802704a5  test    rcx, rcx
0x1802704a8  jz      short loc_1802704B0
0x1802704aa  call    cs:__imp_SRCacheContext_Close
0x1802704b0  mov     ebx, edi
0x1802704b2  jmp     loc_1802705AF
0x1802704b7  xorps   xmm0, xmm0
0x1802704ba  mov     [rbp+57h+var_68], 0
0x1802704c2  xorps   xmm1, xmm1
0x1802704c5  mov     [rbp+57h+arg_0], r15b
0x1802704c9  lea     r9, [rbp+57h+arg_0]
0x1802704cd  lea     r8, [rbp+57h+var_88]
0x1802704d1  lea     rcx, [rbp+57h+var_C8]
0x1802704d5  movdqu  xmmword ptr [rbp+57h+var_88], xmm0
0x1802704da  movdqu  [rbp+57h+var_78], xmm1
0x1802704df  call    ?Get@DependencyGraphIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DependencyGraph_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Get(StateRepository::Cache::Entity::DependencyGraph_NoThrow::CacheFlags,StateRepository::Cache::Entity::DependencyGraph_NoThrow &,bool &)
0x1802704e4  mov     edi, eax
0x1802704e6  test    eax, eax
0x1802704e8  jns     short loc_1802704F1
0x1802704ea  mov     edx, 18Bh
0x1802704ef  jmp     short loc_18027048A
0x1802704f1  mov     rdi, r15
0x1802704f4  cmp     [rbp+57h+arg_0], r15b
0x1802704f8  jz      loc_1802705BA
0x1802704fe  mov     r9, [rbp+57h+var_88]; char *
0x180270502  lea     rax, [rbp+57h+arg_0]
0x180270506  xor     r8d, r8d; char *
0x180270509  mov     [rsp+100h+var_E0], rax; int
0x18027050e  lea     rdx, aSelectExistsSe_381; "SELECT EXISTS(SELECT 1 FROM CacheDepend"...
0x180270515  mov     rcx, r12; this
0x180270518  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18027051d  mov     esi, eax
0x18027051f  test    eax, eax
0x180270521  js      short loc_18027056A
0x180270523  cmp     [rbp+57h+arg_0], r15b
0x180270527  jnz     short loc_180270542
0x180270529  mov     rdx, [rbp+57h+var_88]; __int64
0x18027052d  lea     rcx, [rbp+57h+var_A0]; this
0x180270531  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180270536  mov     esi, eax
0x180270538  test    eax, eax
0x18027053a  js      short loc_180270563
0x18027053c  inc     rdi
0x18027053f  inc     rbx
0x180270542  inc     dword ptr [rbp+57h+var_C8+8]
0x180270545  lea     r9, [rbp+57h+arg_0]
0x180270549  lea     r8, [rbp+57h+var_88]
0x18027054d  lea     rcx, [rbp+57h+var_C8]
0x180270551  call    ?Get@DependencyGraphIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@DependencyGraph_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::DependencyGraphIterator_NoThrow::Get(StateRepository::Cache::Entity::DependencyGraph_NoThrow::CacheFlags,StateRepository::Cache::Entity::DependencyGraph_NoThrow &,bool &)
0x180270556  mov     esi, eax
0x180270558  test    eax, eax
0x18027055a  jns     short loc_1802704F4
0x18027055c  mov     edx, 196h
0x180270561  jmp     short loc_180270587
0x180270563  mov     edx, 194h
0x180270568  jmp     short loc_180270587
0x18027056a  mov     rcx, [rbp+5Fh]; this
0x18027056e  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x180270575  mov     r9d, esi; char *
0x180270578  mov     edx, 68h ; 'h'; void *
0x18027057d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270582  mov     edx, 18Fh; void *
0x180270587  mov     rcx, [rbp+5Fh]; this
0x18027058b  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x180270592  mov     r9d, esi; char *
0x180270595  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027059a  mov     rcx, [rbp+57h+var_C8]
0x18027059e  mov     [rbp+57h+var_C8], r15
0x1802705a2  test    rcx, rcx
0x1802705a5  jz      short loc_1802705AD
0x1802705a7  call    cs:__imp_SRCacheContext_Close
0x1802705ad  mov     ebx, esi
0x1802705af  lea     rcx, [rbp+57h+var_A0]; this
0x1802705b3  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1802705b8  jmp     short loc_180270632
0x1802705ba  mov     rcx, [rbp+57h+var_C8]
0x1802705be  mov     [rbp+57h+var_C8], r15
0x1802705c2  test    rcx, rcx
0x1802705c5  jz      short loc_1802705CD
0x1802705c7  call    cs:__imp_SRCacheContext_Close
0x1802705cd  test    rdi, rdi
0x1802705d0  jz      short loc_1802705FA
0x1802705d2  test    cs:byte_1804DF881, 20h
0x1802705d9  jz      short loc_1802705FA
0x1802705db  mov     rax, qword ptr [rbp+57h+var_A0]
0x1802705df  lea     r8, aCachedependenc; "CacheDependencyGraph"
0x1802705e6  mov     r9, rdi
0x1802705e9  mov     [rsp+100h+var_E0], rax
0x1802705ee  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x1802705f5  call    McTemplateU0sxs_EventWriteTransfer
0x1802705fa  mov     rax, [rbp+57h+arg_18]
0x1802705fe  lea     rcx, [rbp+57h+var_A0]; this
0x180270602  mov     [rax], rbx
0x180270605  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18027060a  xor     eax, eax
0x18027060c  jmp     short loc_180270634
0x18027060e  mov     edx, 153h
0x180270613  jmp     short loc_18027061A
0x180270615  mov     edx, 151h; void *
0x18027061a  mov     ebx, 8007139Fh
0x18027061f  mov     rcx, [rbp+5Fh]; this
0x180270623  lea     r8, aOnecoreBaseApp_96; "onecore\\base\\appmodel\\staterepositor"...
0x18027062a  mov     r9d, ebx; char *
0x18027062d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180270632  mov     eax, ebx
0x180270634  mov     rbx, [rsp+100h+arg_8]
0x18027063c  add     rsp, 0D0h
0x180270643  pop     r15
0x180270645  pop     r14
0x180270647  pop     r13
0x180270649  pop     r12
0x18027064b  pop     rdi
0x18027064c  pop     rsi
0x18027064d  pop     rbp
0x18027064e  retn
```
