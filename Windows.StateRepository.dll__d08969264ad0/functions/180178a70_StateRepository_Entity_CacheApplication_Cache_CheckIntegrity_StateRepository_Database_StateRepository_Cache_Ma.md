# StateRepository::Entity::CacheApplication::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180178a70`
- end: `0x180178fad`
- name: `?Cache_CheckIntegrity@CacheApplication@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1341`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x18009415c`
- `0x180094550`
- `0x1800945b0`
- `0x18009b878`
- `0x1800ae890`
- `0x180178a70`
- `0x180178fb4`
- `0x18026544c`
- `0x180266578`
- `0x180266b98`
- `0x180266c60`
- `0x180266d40`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178eed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178f1d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178d6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178eed`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180178f1d`

## string_xrefs

- `0x180178af1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178b3e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178c87`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178d4a`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178dd0`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178e9c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178ebc`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178f81`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheapplication.cpp`
- `0x180178d2f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Application.hpp`
- `0x180178ccd`: `CacheApplication`
- `0x180178f36`: `CacheApplication`
- `0x180178e20`: `SELECT EXISTS(SELECT 1 FROM CacheApplication WHERE _CacheApplicationID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheApplication::Cache_CheckIntegrity(
        StateRepository::Database *a1,
        struct StateRepository::Cache::Manager_NoThrow *a2,
        __int64 a3,
        _QWORD *a4)
{
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
  __int128 v59; // [rsp+110h] [rbp+10h] BYREF
  __int64 v60; // [rsp+120h] [rbp+20h]
  __int64 v61; // [rsp+128h] [rbp+28h]
  __int128 v62; // [rsp+130h] [rbp+30h]
  __int128 v63; // [rsp+140h] [rbp+40h]
  __int128 v64; // [rsp+150h] [rbp+50h]
  __int128 v65; // [rsp+160h] [rbp+60h]
  _BYTE v66[208]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+148h]
  bool v68; // [rsp+250h] [rbp+150h] BYREF
  _QWORD *v69; // [rsp+268h] [rbp+168h]

  v69 = a4;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 780;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 781;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)v6,
      (int)v41);
    return v6;
  }
  if ( !*(_QWORD *)a2 )
  {
    v7 = 782;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v49 = 0;
  v50 = 0;
  v48 = 0;
  v8 = StateRepository::Entity::CacheApplication::Find(a1, (struct StateRepository::Statement *)&v48);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x319,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v8,
      (int)v41);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v49);
    return v6;
  }
  StateRepository::Entity::CacheApplication::CacheApplication((StateRepository::Entity::CacheApplication *)v52);
  v68 = 0;
  Next = StateRepository::Entity::CacheApplication::FindNext(
           (struct StateRepository::Statement *)&v48,
           (struct StateRepository::Entity::CacheApplication *)v52,
           &v68);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)Next,
      (int)v41);
    StateRepository::Entity::CacheApplication::~CacheApplication((StateRepository::Entity::CacheApplication *)v52);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v68 )
  {
    v41 = &v68;
    v59 = 0;
    v62 = 0;
    v63 = 0;
    v64 = 0;
    v65 = 0;
    v60 = 0;
    v61 = 0;
    appended = StateRepository::Cache::Entity::Application_NoThrow::Get(a2, v52[0], v11, &v59);
    if ( appended < 0 )
    {
      v19 = 801;
      goto LABEL_27;
    }
    if ( v68 )
    {
      v51 = 0;
      appended = StateRepository::Entity::CacheApplication::Cache_Check(
                   (const struct StateRepository::Entity::CacheApplication *)v52,
                   (const struct StateRepository::Cache::Entity::Application_NoThrow *)&v59,
                   &v51);
      if ( appended < 0 )
      {
        v19 = 806;
        goto LABEL_27;
      }
      v18 = v51;
      if ( v51 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v17);
        if ( appended < 0 )
        {
          v19 = 810;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
            (const char *)(unsigned int)appended,
            (int)&v68);
          StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v59);
          StateRepository::Entity::CacheApplication::~CacheApplication((StateRepository::Entity::CacheApplication *)v52);
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
        v19 = 816;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheApplication::FindNext(
                 (struct StateRepository::Statement *)&v48,
                 (struct StateRepository::Entity::CacheApplication *)v52,
                 &v68);
    if ( appended < 0 )
    {
      v19 = 818;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)&v59);
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheApplication",
      v20,
      *(__int64 *)v49);
  StateRepository::Entity::CacheApplication::~CacheApplication((StateRepository::Entity::CacheApplication *)v52);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v48);
  StateRepository::TextA::Clear((StateRepository::TextA *)v49);
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v21 = StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::ApplicationIterator_NoThrow *)&v45,
          a2);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x472,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v21,
      (int)v41);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x343,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
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
  v57 = 0;
  v58 = 0;
  v54 = 0;
  v68 = 0;
  v27 = StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Get(&v45, v22, v52, &v68);
  v23 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x346,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
      (const char *)(unsigned int)v27,
      (int)v41);
    StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v52);
    goto LABEL_34;
  }
  v28 = 0;
  while ( v68 )
  {
    StateRepository::Entity::CacheApplication::CacheApplication((StateRepository::Entity::CacheApplication *)v66);
    v29 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheApplication WHERE _CacheApplicationID=? LIMIT 1);",
            0,
            v52[0],
            (__int64)&v68,
            v44);
    v32 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x140,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
        (const char *)(unsigned int)v29,
        v43);
      v33 = 842;
      goto LABEL_50;
    }
    if ( !v68 )
    {
      v32 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v49, (__int64)v52[0], v31);
      if ( v32 < 0 )
      {
        v33 = 847;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v33,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheapplication.cpp",
          (const char *)(unsigned int)v32,
          v43);
        StateRepository::Entity::CacheApplication::~CacheApplication((StateRepository::Entity::CacheApplication *)v66);
        StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v52);
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
    v32 = StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Get(&v45, v30, v52, &v68);
    if ( v32 < 0 )
    {
      v33 = 849;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheApplication::~CacheApplication((StateRepository::Entity::CacheApplication *)v66);
  }
  StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow((StateRepository::Cache::Entity::Application_NoThrow *)v52);
  v39 = v45;
  v45 = 0;
  if ( v39 )
    SRCacheContext_Close(v39, v37, v38);
  if ( v28 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v39,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheApplication",
      v28,
      *(__int64 *)v49);
  *v69 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v49);
  return 0;
}

```

## disassembly

```asm
0x180178a70  mov     [rsp-8+arg_8], rbx
0x180178a75  mov     [rsp-8+arg_18], r9
0x180178a7a  push    rbp
0x180178a7b  push    rsi
0x180178a7c  push    rdi
0x180178a7d  push    r12
0x180178a7f  push    r13
0x180178a81  push    r14
0x180178a83  push    r15
0x180178a85  lea     rbp, [rsp-110h]
0x180178a8d  sub     rsp, 210h
0x180178a94  xor     r15d, r15d
0x180178a97  mov     r13, rdx
0x180178a9a  mov     r12, rcx
0x180178a9d  cmp     [rcx], r15
0x180178aa0  jz      loc_180178F70
0x180178aa6  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180178aab  test    al, al
0x180178aad  jz      short loc_180178ABE
0x180178aaf  mov     ebx, 8067000Bh
0x180178ab4  mov     edx, 30Dh
0x180178ab9  jmp     loc_180178F7A
0x180178abe  cmp     [r13+0], r15
0x180178ac2  jz      loc_180178F69
0x180178ac8  lea     rdx, [rsp+240h+var_1F8]; struct StateRepository::Statement *
0x180178acd  mov     qword ptr [rsp+240h+var_1F0], r15
0x180178ad2  mov     rcx, r12; struct StateRepository::Database *
0x180178ad5  mov     [rsp+240h+var_1E8], r15
0x180178ada  mov     [rsp+240h+var_1F8], r15
0x180178adf  call    ?Find@CacheApplication@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheApplication::Find(StateRepository::Database &,StateRepository::Statement &)
0x180178ae4  mov     ebx, eax
0x180178ae6  test    eax, eax
0x180178ae8  jns     short loc_180178B0A
0x180178aea  mov     rcx, [rbp+148h]; this
0x180178af1  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178af8  mov     r9d, eax; char *
0x180178afb  mov     edx, 319h; void *
0x180178b00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178b05  jmp     loc_180178CAB
0x180178b0a  lea     rcx, [rsp+240h+var_1D0]; this
0x180178b0f  call    ??0CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::CacheApplication(void)
0x180178b14  lea     r8, [rbp+140h+arg_0]; bool *
0x180178b1b  mov     [rbp+140h+arg_0], r15b
0x180178b22  lea     rdx, [rsp+240h+var_1D0]; struct StateRepository::Entity::CacheApplication *
0x180178b27  lea     rcx, [rsp+240h+var_1F8]; this
0x180178b2c  call    ?FindNext@CacheApplication@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplication::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplication &,bool &)
0x180178b31  mov     ebx, eax
0x180178b33  test    eax, eax
0x180178b35  jns     short loc_180178B61
0x180178b37  mov     rcx, [rbp+148h]; this
0x180178b3e  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178b45  mov     r9d, eax; char *
0x180178b48  mov     edx, 31Ch; void *
0x180178b4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178b52  lea     rcx, [rsp+240h+var_1D0]; this
0x180178b57  call    ??1CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::~CacheApplication(void)
0x180178b5c  jmp     loc_180178CAB
0x180178b61  mov     rbx, r15
0x180178b64  mov     rdi, r15
0x180178b67  mov     r14, r15
0x180178b6a  cmp     [rbp+140h+arg_0], r15b
0x180178b71  jz      loc_180178CBA
0x180178b77  mov     rdx, [rsp+240h+var_1D0]
0x180178b7c  lea     rax, [rbp+140h+arg_0]
0x180178b83  xorps   xmm0, xmm0
0x180178b86  mov     [rsp+240h+var_220], rax; int
0x180178b8b  xorps   xmm1, xmm1
0x180178b8e  movdqa  [rbp+140h+var_130], xmm0
0x180178b93  lea     r9, [rbp+140h+var_130]
0x180178b97  movdqa  [rbp+140h+var_110], xmm0
0x180178b9c  mov     rcx, r13
0x180178b9f  movdqa  [rbp+140h+var_100], xmm1
0x180178ba4  movdqa  [rbp+140h+var_F0], xmm0
0x180178ba9  movdqa  [rbp+140h+var_E0], xmm1
0x180178bae  mov     [rbp+140h+var_120], 0
0x180178bb6  mov     [rbp+140h+var_118], r15
0x180178bba  call    ?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180178bbf  mov     esi, eax
0x180178bc1  test    eax, eax
0x180178bc3  js      loc_180178C7B
0x180178bc9  cmp     [rbp+140h+arg_0], r15b
0x180178bd0  jz      short loc_180178C1A
0x180178bd2  lea     r8, [rsp+240h+var_1E0]; unsigned __int64 *
0x180178bd7  mov     [rsp+240h+var_1E0], r15
0x180178bdc  lea     rdx, [rbp+140h+var_130]; struct StateRepository::Cache::Entity::Application_NoThrow *
0x180178be0  lea     rcx, [rsp+240h+var_1D0]; struct StateRepository::Entity::CacheApplication *
0x180178be5  call    ?Cache_Check@CacheApplication@Entity@StateRepository@@CAJAEBV123@AEBVApplication_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheApplication::Cache_Check(StateRepository::Entity::CacheApplication const &,StateRepository::Cache::Entity::Application_NoThrow const &,unsigned __int64 &)
0x180178bea  mov     esi, eax
0x180178bec  test    eax, eax
0x180178bee  js      short loc_180178C66
0x180178bf0  mov     r15, [rsp+240h+var_1E0]
0x180178bf5  test    r15, r15
0x180178bf8  jz      short loc_180178C12
0x180178bfa  mov     rdx, [rsp+240h+var_1D0]; __int64
0x180178bff  lea     rcx, [rsp+240h+var_1F0]; this
0x180178c04  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180178c09  mov     esi, eax
0x180178c0b  test    eax, eax
0x180178c0d  js      short loc_180178C5F
0x180178c0f  add     rbx, r15
0x180178c12  inc     r14
0x180178c15  xor     r15d, r15d
0x180178c18  jmp     short loc_180178C32
0x180178c1a  mov     rdx, [rsp+240h+var_1D0]; __int64
0x180178c1f  lea     rcx, [rsp+240h+var_1F0]; this
0x180178c24  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180178c29  mov     esi, eax
0x180178c2b  test    eax, eax
0x180178c2d  js      short loc_180178C74
0x180178c2f  inc     rbx
0x180178c32  lea     r8, [rbp+140h+arg_0]; bool *
0x180178c39  lea     rdx, [rsp+240h+var_1D0]; struct StateRepository::Entity::CacheApplication *
0x180178c3e  lea     rcx, [rsp+240h+var_1F8]; this
0x180178c43  call    ?FindNext@CacheApplication@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheApplication::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheApplication &,bool &)
0x180178c48  mov     esi, eax
0x180178c4a  test    eax, eax
0x180178c4c  js      short loc_180178C6D
0x180178c4e  inc     rdi
0x180178c51  lea     rcx, [rbp+140h+var_130]; this
0x180178c55  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180178c5a  jmp     loc_180178B6A
0x180178c5f  mov     edx, 32Ah
0x180178c64  jmp     short loc_180178C80
0x180178c66  mov     edx, 326h
0x180178c6b  jmp     short loc_180178C80
0x180178c6d  mov     edx, 332h
0x180178c72  jmp     short loc_180178C80
0x180178c74  mov     edx, 330h
0x180178c79  jmp     short loc_180178C80
0x180178c7b  mov     edx, 321h; void *
0x180178c80  mov     rcx, [rbp+148h]; this
0x180178c87  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178c8e  mov     r9d, esi; char *
0x180178c91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178c96  lea     rcx, [rbp+140h+var_130]; this
0x180178c9a  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180178c9f  lea     rcx, [rsp+240h+var_1D0]; this
0x180178ca4  call    ??1CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::~CacheApplication(void)
0x180178ca9  mov     ebx, esi
0x180178cab  lea     rcx, [rsp+240h+var_1F8]; this
0x180178cb0  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180178cb5  jmp     loc_180178EF5
0x180178cba  sub     rdi, r14
0x180178cbd  jz      short loc_180178CE8
0x180178cbf  test    cs:byte_1804DF881, 20h
0x180178cc6  jz      short loc_180178CE8
0x180178cc8  mov     rax, qword ptr [rsp+240h+var_1F0]
0x180178ccd  lea     r8, aCacheapplicati_0; "CacheApplication"
0x180178cd4  mov     r9, rdi
0x180178cd7  mov     [rsp+240h+var_220], rax; int
0x180178cdc  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180178ce3  call    McTemplateU0sxs_EventWriteTransfer
0x180178ce8  lea     rcx, [rsp+240h+var_1D0]; this
0x180178ced  call    ??1CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::~CacheApplication(void)
0x180178cf2  lea     rcx, [rsp+240h+var_1F8]; this
0x180178cf7  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180178cfc  lea     rcx, [rsp+240h+var_1F0]; this
0x180178d01  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180178d06  mov     rdx, r13; struct StateRepository::Cache::Manager_NoThrow *
0x180178d09  mov     [rsp+240h+var_210], r15
0x180178d0e  lea     rcx, [rsp+240h+var_210]; this
0x180178d13  mov     [rsp+240h+var_208], r15d
0x180178d18  mov     [rsp+240h+var_200], r15
0x180178d1d  call    ?Open@ApplicationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180178d22  mov     edi, eax
0x180178d24  test    eax, eax
0x180178d26  jns     short loc_180178D7A
0x180178d28  mov     rcx, [rbp+148h]; this
0x180178d2f  lea     r8, aOnecoreBaseApp_457; "onecore\\base\\appmodel\\StateRepositor"...
0x180178d36  mov     r9d, eax; char *
0x180178d39  mov     edx, 472h; void *
0x180178d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178d43  mov     rcx, [rbp+148h]; this
0x180178d4a  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178d51  mov     r9d, edi; char *
0x180178d54  mov     edx, 343h; void *
0x180178d59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178d5e  mov     rcx, [rsp+240h+var_210]
0x180178d63  mov     [rsp+240h+var_210], r15
0x180178d68  test    rcx, rcx
0x180178d6b  jz      short loc_180178D73
0x180178d6d  call    cs:__imp_SRCacheContext_Close
0x180178d73  mov     ebx, edi
0x180178d75  jmp     loc_180178EF5
0x180178d7a  xorps   xmm0, xmm0
0x180178d7d  mov     [rbp+140h+var_1C0], 0
0x180178d85  xorps   xmm1, xmm1
0x180178d88  movdqa  xmmword ptr [rsp+240h+var_1D0], xmm0
0x180178d8e  lea     r9, [rbp+140h+arg_0]
0x180178d95  movdqa  [rbp+140h+var_1B0], xmm0
0x180178d9a  lea     r8, [rsp+240h+var_1D0]
0x180178d9f  movdqa  [rbp+140h+var_1A0], xmm1
0x180178da4  lea     rcx, [rsp+240h+var_210]
0x180178da9  movdqa  [rbp+140h+var_190], xmm0
0x180178dae  movdqa  [rbp+140h+var_180], xmm1
0x180178db3  mov     [rbp+140h+var_1B8], r15
0x180178db7  mov     [rbp+140h+arg_0], r15b
0x180178dbe  call    ?Get@ApplicationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180178dc3  mov     edi, eax
0x180178dc5  test    eax, eax
0x180178dc7  jns     short loc_180178DF3
0x180178dc9  mov     rcx, [rbp+148h]; this
0x180178dd0  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178dd7  mov     r9d, eax; char *
0x180178dda  mov     edx, 346h; void *
0x180178ddf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178de4  lea     rcx, [rsp+240h+var_1D0]; this
0x180178de9  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180178dee  jmp     loc_180178D5E
0x180178df3  mov     rdi, r15
0x180178df6  cmp     [rbp+140h+arg_0], r15b
0x180178dfd  jz      loc_180178F04
0x180178e03  lea     rcx, [rbp+140h+var_D0]; this
0x180178e07  call    ??0CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::CacheApplication(void)
0x180178e0c  mov     r9, [rsp+240h+var_1D0]; char *
0x180178e11  lea     rax, [rbp+140h+arg_0]
0x180178e18  xor     r8d, r8d; char *
0x180178e1b  mov     [rsp+240h+var_220], rax; int
0x180178e20  lea     rdx, aSelectExistsSe_508; "SELECT EXISTS(SELECT 1 FROM CacheApplic"...
0x180178e27  mov     rcx, r12; this
0x180178e2a  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x180178e2f  mov     esi, eax
0x180178e31  test    eax, eax
0x180178e33  js      short loc_180178E95
0x180178e35  cmp     [rbp+140h+arg_0], r15b
0x180178e3c  jnz     short loc_180178E59
0x180178e3e  mov     rdx, [rsp+240h+var_1D0]; __int64
0x180178e43  lea     rcx, [rsp+240h+var_1F0]; this
0x180178e48  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180178e4d  mov     esi, eax
0x180178e4f  test    eax, eax
0x180178e51  js      short loc_180178E87
0x180178e53  inc     rdi
0x180178e56  inc     rbx
0x180178e59  inc     [rsp+240h+var_208]
0x180178e5d  lea     r9, [rbp+140h+arg_0]
0x180178e64  lea     r8, [rsp+240h+var_1D0]
0x180178e69  lea     rcx, [rsp+240h+var_210]
0x180178e6e  call    ?Get@ApplicationIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@Application_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::ApplicationIterator_NoThrow::Get(StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)
0x180178e73  mov     esi, eax
0x180178e75  test    eax, eax
0x180178e77  js      short loc_180178E8E
0x180178e79  lea     rcx, [rbp+140h+var_D0]; this
0x180178e7d  call    ??1CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::~CacheApplication(void)
0x180178e82  jmp     loc_180178DF6
0x180178e87  mov     edx, 34Fh
0x180178e8c  jmp     short loc_180178EB5
0x180178e8e  mov     edx, 351h
0x180178e93  jmp     short loc_180178EB5
0x180178e95  mov     rcx, [rbp+148h]; this
0x180178e9c  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178ea3  mov     r9d, esi; char *
0x180178ea6  mov     edx, 140h; void *
0x180178eab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178eb0  mov     edx, 34Ah; void *
0x180178eb5  mov     rcx, [rbp+148h]; this
0x180178ebc  lea     r8, aOnecoreBaseApp_352; "onecore\\base\\appmodel\\staterepositor"...
0x180178ec3  mov     r9d, esi; char *
0x180178ec6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180178ecb  lea     rcx, [rbp+140h+var_D0]; this
0x180178ecf  call    ??1CacheApplication@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheApplication::~CacheApplication(void)
0x180178ed4  lea     rcx, [rsp+240h+var_1D0]; this
0x180178ed9  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180178ede  mov     rcx, [rsp+240h+var_210]
0x180178ee3  mov     [rsp+240h+var_210], r15
0x180178ee8  test    rcx, rcx
0x180178eeb  jz      short loc_180178EF3
0x180178eed  call    cs:__imp_SRCacheContext_Close
0x180178ef3  mov     ebx, esi
0x180178ef5  lea     rcx, [rsp+240h+var_1F0]; this
0x180178efa  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180178eff  jmp     loc_180178F90
0x180178f04  lea     rcx, [rsp+240h+var_1D0]; this
0x180178f09  call    ??1Application_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::Application_NoThrow::~Application_NoThrow(void)
0x180178f0e  mov     rcx, [rsp+240h+var_210]
0x180178f13  mov     [rsp+240h+var_210], r15
0x180178f18  test    rcx, rcx
0x180178f1b  jz      short loc_180178F23
0x180178f1d  call    cs:__imp_SRCacheContext_Close
0x180178f23  test    rdi, rdi
0x180178f26  jz      short loc_180178F51
0x180178f28  test    cs:byte_1804DF881, 20h
0x180178f2f  jz      short loc_180178F51
0x180178f31  mov     rax, qword ptr [rsp+240h+var_1F0]
0x180178f36  lea     r8, aCacheapplicati_0; "CacheApplication"
0x180178f3d  mov     r9, rdi
0x180178f40  mov     [rsp+240h+var_220], rax
0x180178f45  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x180178f4c  call    McTemplateU0sxs_EventWriteTransfer
0x180178f51  mov     rax, [rbp+140h+arg_18]
0x180178f58  lea     rcx, [rsp+240h+var_1F0]; this
0x180178f5d  mov     [rax], rbx
0x180178f60  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180178f65  xor     eax, eax
0x180178f67  jmp     short loc_180178F92
0x180178f69  mov     edx, 30Eh
0x180178f6e  jmp     short loc_180178F75
0x180178f70  mov     edx, 30Ch; void *
0x180178f75  mov     ebx, 8007139Fh
0x180178f7a  mov     rcx, [rbp+148h]; this
  ... truncated ...
```
