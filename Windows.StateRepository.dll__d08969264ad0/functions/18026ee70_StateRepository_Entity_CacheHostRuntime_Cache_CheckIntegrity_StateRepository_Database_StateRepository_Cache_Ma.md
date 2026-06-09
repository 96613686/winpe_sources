# StateRepository::Entity::CacheHostRuntime::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x18026ee70`
- end: `0x18026f355`
- name: `?Cache_CheckIntegrity@CacheHostRuntime@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x18004e3b0`
- `0x180062cd8`
- `0x1800a6778`
- `0x1800ae890`
- `0x18026544c`
- `0x18026ed38`
- `0x18026ee70`
- `0x18026f3f8`
- `0x18026f4c0`
- `0x18026f5a0`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f14f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f2a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f2d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f14f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f2a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18026f2d6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f022`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f08d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f1a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f28d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f2c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f022`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f08d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f1a8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f28d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026f2c3`

## string_xrefs

- `0x18026eee5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026ef2d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f031`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f071`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f12e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f187`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f24b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f268`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f332`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachehostruntime.cpp`
- `0x18026f116`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-HostRuntime.hpp`
- `0x18026f0be`: `CacheHostRuntime`
- `0x18026f2ee`: `CacheHostRuntime`
- `0x18026f1d0`: `SELECT EXISTS(SELECT 1 FROM CacheHostRuntime WHERE _CacheHostRuntimeID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheHostRuntime::Cache_CheckIntegrity(
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
  __int64 v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  int v15; // esi
  char v16; // r8
  char v17; // r8
  unsigned __int64 v18; // r15
  int appended; // eax
  __int64 v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rdx
  unsigned int v25; // edi
  __int64 v26; // rdx
  __int64 v27; // r8
  __int64 v28; // rcx
  int v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // rcx
  __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // rdx
  char v36; // r8
  int v37; // esi
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 v44; // rcx
  bool *v46; // [rsp+20h] [rbp-79h]
  int v47; // [rsp+20h] [rbp-79h]
  int v48; // [rsp+20h] [rbp-79h]
  bool *v49; // [rsp+28h] [rbp-71h]
  char *v50[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v51; // [rsp+40h] [rbp-59h] BYREF
  __int64 v52; // [rsp+50h] [rbp-49h] BYREF
  int v53; // [rsp+58h] [rbp-41h]
  __int64 v54; // [rsp+60h] [rbp-39h]
  __int64 v55; // [rsp+68h] [rbp-31h] BYREF
  __int128 v56; // [rsp+70h] [rbp-29h] BYREF
  __int64 v57; // [rsp+80h] [rbp-19h]
  int v58[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v59; // [rsp+90h] [rbp-9h]
  unsigned __int64 v60; // [rsp+98h] [rbp-1h] BYREF
  __int128 v61; // [rsp+A0h] [rbp+7h]
  _OWORD v62[4]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  bool v64; // [rsp+100h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v65; // [rsp+108h] [rbp+6Fh]
  _QWORD *v66; // [rsp+118h] [rbp+7Fh]

  v66 = a4;
  v65 = a2;
  v4 = a2;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 506;
    goto LABEL_71;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 507;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
      (const char *)v6,
      (int)v46);
    return v6;
  }
  if ( !*(_QWORD *)v4 )
  {
    v7 = 508;
LABEL_71:
    v6 = -2147019873;
    goto LABEL_72;
  }
  *(_QWORD *)v58 = 0;
  v59 = 0;
  v55 = 0;
  v8 = StateRepository::Entity::CacheHostRuntime::Find(a1, (struct StateRepository::Statement *)&v55);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v55);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v58);
    return v6;
  }
  v64 = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  Next = StateRepository::Entity::CacheHostRuntime::FindNext(
           (struct StateRepository::Statement *)&v55,
           (struct StateRepository::Entity::CacheHostRuntime *)v50,
           &v64);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
      (const char *)(unsigned int)Next,
      (int)v46);
    StateRepository::TextA::Reset((StateRepository::TextA *)&v51);
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v64 )
  {
    v46 = &v64;
    v57 = 0;
    v56 = 0;
    v15 = StateRepository::Cache::Entity::HostRuntime_NoThrow::Get(v4, v50[0], v11, &v56);
    if ( v15 < 0 )
    {
      v21 = 527;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
        (const char *)(unsigned int)v15,
        (int)&v64);
      v20 = v57;
      v57 = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)&v51);
      v6 = v15;
      goto LABEL_32;
    }
    if ( v64 )
    {
      v60 = 0;
      v15 = StateRepository::Entity::CacheHostRuntime::Cache_Check(
              (const struct StateRepository::Entity::CacheHostRuntime *)v50,
              (const struct StateRepository::Cache::Entity::HostRuntime_NoThrow *)&v56,
              &v60);
      if ( v15 < 0 )
      {
        v21 = 532;
        goto LABEL_28;
      }
      v18 = v60;
      if ( v60 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v50[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x218,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
            (const char *)(unsigned int)appended,
            (int)&v64);
          v20 = v57;
          v57 = 0;
          goto LABEL_29;
        }
        v12 += v18;
      }
      ++v14;
    }
    else
    {
      v15 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v50[0], v16);
      if ( v15 < 0 )
      {
        v21 = 542;
        goto LABEL_28;
      }
      ++v12;
    }
    v15 = StateRepository::Entity::CacheHostRuntime::FindNext(
            (struct StateRepository::Statement *)&v55,
            (struct StateRepository::Entity::CacheHostRuntime *)v50,
            &v64);
    if ( v15 < 0 )
    {
      v21 = 544;
      goto LABEL_28;
    }
    v10 = v57;
    ++v13;
    v4 = v65;
    v57 = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheHostRuntime",
      v22,
      *(__int64 *)v58);
  StateRepository::TextA::Reset((StateRepository::TextA *)&v51);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v55);
  StateRepository::TextA::Clear((StateRepository::TextA *)v58);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v23 = StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow *)&v52,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-HostRuntime.hpp",
      (const char *)(unsigned int)v23,
      (int)v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
      (const char *)v25,
      v47);
LABEL_38:
    v28 = v52;
    v52 = 0;
    if ( v28 )
      SRCacheContext_Close(v28, v26, v27);
    v6 = v25;
    goto LABEL_60;
  }
  *(_QWORD *)&v51 = 0;
  v64 = 0;
  *(_OWORD *)v50 = 0;
  v29 = StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Get(&v52, v24, v50, &v64);
  v25 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v32 = v51;
    *(_QWORD *)&v51 = 0;
    if ( v32 )
      SRCache_Free(v32);
    goto LABEL_38;
  }
  v33 = 0;
  while ( v64 )
  {
    v61 = 0;
    v62[0] = 0;
    v34 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheHostRuntime WHERE _CacheHostRuntimeID=? LIMIT 1);",
            0,
            v50[0],
            (__int64)&v64,
            v49);
    v37 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
        (const char *)(unsigned int)v34,
        v48);
      v38 = 568;
      goto LABEL_55;
    }
    if ( !v64 )
    {
      v37 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v50[0], v36);
      if ( v37 < 0 )
      {
        v38 = 573;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachehostruntime.cpp",
          (const char *)(unsigned int)v37,
          v48);
        StateRepository::TextA::Reset((StateRepository::TextA *)v62);
        v41 = v51;
        *(_QWORD *)&v51 = 0;
        if ( v41 )
          SRCache_Free(v41);
        v42 = v52;
        v52 = 0;
        if ( v42 )
          SRCacheContext_Close(v42, v39, v40);
        v6 = v37;
        goto LABEL_60;
      }
      ++v33;
      ++v12;
    }
    ++v53;
    v37 = StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Get(&v52, v35, v50, &v64);
    if ( v37 < 0 )
    {
      v38 = 575;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)v62);
  }
  v43 = v51;
  *(_QWORD *)&v51 = 0;
  if ( v43 )
    SRCache_Free(v43);
  v44 = v52;
  v52 = 0;
  if ( v44 )
    SRCacheContext_Close(v44, v30, v31);
  if ( v33 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v44,
      (unsigned int)CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheHostRuntime",
      v33,
      *(__int64 *)v58);
  *v66 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v58);
  return 0;
}

```

## disassembly

```asm
0x18026ee70  mov     [rsp-8+arg_18], r9
0x18026ee75  mov     [rsp-8+arg_8], rdx
0x18026ee7a  push    rbp
0x18026ee7b  push    rbx
0x18026ee7c  push    rsi
0x18026ee7d  push    rdi
0x18026ee7e  push    r13
0x18026ee80  push    r14
0x18026ee82  push    r15
0x18026ee84  lea     rbp, [rsp-27h]
0x18026ee89  sub     rsp, 0C0h
0x18026ee90  xor     r15d, r15d
0x18026ee93  mov     rsi, rdx
0x18026ee96  mov     r13, rcx
0x18026ee99  cmp     [rcx], r15
0x18026ee9c  jz      loc_18026F324
0x18026eea2  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18026eea7  test    al, al
0x18026eea9  jz      short loc_18026EEBA
0x18026eeab  mov     ebx, 8067000Bh
0x18026eeb0  mov     edx, 1FBh
0x18026eeb5  jmp     loc_18026F32E
0x18026eeba  cmp     [rsi], r15
0x18026eebd  jz      loc_18026F31D
0x18026eec3  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Statement *
0x18026eec7  mov     qword ptr [rbp+57h+var_68], r15
0x18026eecb  mov     rcx, r13; struct StateRepository::Database *
0x18026eece  mov     [rbp+57h+var_60], r15
0x18026eed2  mov     [rbp+57h+var_88], r15
0x18026eed6  call    ?Find@CacheHostRuntime@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheHostRuntime::Find(StateRepository::Database &,StateRepository::Statement &)
0x18026eedb  mov     ebx, eax
0x18026eedd  test    eax, eax
0x18026eedf  jns     short loc_18026EEFE
0x18026eee1  mov     rcx, [rbp+5Fh]; this
0x18026eee5  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026eeec  mov     r9d, eax; char *
0x18026eeef  mov     edx, 207h; void *
0x18026eef4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026eef9  jmp     loc_18026F09E
0x18026eefe  xorps   xmm0, xmm0
0x18026ef01  mov     [rbp+57h+arg_0], r15b
0x18026ef05  xorps   xmm1, xmm1
0x18026ef08  lea     r8, [rbp+57h+arg_0]; bool *
0x18026ef0c  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheHostRuntime *
0x18026ef10  lea     rcx, [rbp+57h+var_88]; this
0x18026ef14  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x18026ef19  movdqu  [rbp+57h+var_B0], xmm1
0x18026ef1e  call    ?FindNext@CacheHostRuntime@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheHostRuntime::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheHostRuntime &,bool &)
0x18026ef23  mov     ebx, eax
0x18026ef25  test    eax, eax
0x18026ef27  jns     short loc_18026EF4F
0x18026ef29  mov     rcx, [rbp+5Fh]; this
0x18026ef2d  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026ef34  mov     r9d, eax; char *
0x18026ef37  mov     edx, 20Ah; void *
0x18026ef3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026ef41  lea     rcx, [rbp+57h+var_B0]; this
0x18026ef45  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026ef4a  jmp     loc_18026F09E
0x18026ef4f  mov     rbx, r15
0x18026ef52  mov     rdi, r15
0x18026ef55  mov     r14, r15
0x18026ef58  cmp     [rbp+57h+arg_0], r15b
0x18026ef5c  jz      loc_18026F0AC
0x18026ef62  mov     rdx, [rbp+57h+var_C0]
0x18026ef66  lea     rax, [rbp+57h+arg_0]
0x18026ef6a  xorps   xmm0, xmm0
0x18026ef6d  mov     [rsp+0F0h+var_D0], rax; int
0x18026ef72  lea     r9, [rbp+57h+var_80]
0x18026ef76  mov     [rbp+57h+var_70], r15
0x18026ef7a  mov     rcx, rsi
0x18026ef7d  movdqu  [rbp+57h+var_80], xmm0
0x18026ef82  call    ?Get@HostRuntime_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::HostRuntime_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::HostRuntime_NoThrow::CacheFlags,StateRepository::Cache::Entity::HostRuntime_NoThrow &,bool &)
0x18026ef87  mov     esi, eax
0x18026ef89  test    eax, eax
0x18026ef8b  js      loc_18026F068
0x18026ef91  cmp     [rbp+57h+arg_0], r15b
0x18026ef95  jz      short loc_18026EFDD
0x18026ef97  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x18026ef9b  mov     [rbp+57h+var_58], r15
0x18026ef9f  lea     rdx, [rbp+57h+var_80]; struct StateRepository::Cache::Entity::HostRuntime_NoThrow *
0x18026efa3  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheHostRuntime *
0x18026efa7  call    ?Cache_Check@CacheHostRuntime@Entity@StateRepository@@CAJAEBV123@AEBVHostRuntime_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheHostRuntime::Cache_Check(StateRepository::Entity::CacheHostRuntime const &,StateRepository::Cache::Entity::HostRuntime_NoThrow const &,unsigned __int64 &)
0x18026efac  mov     esi, eax
0x18026efae  test    eax, eax
0x18026efb0  js      loc_18026F053
0x18026efb6  mov     r15, [rbp+57h+var_58]
0x18026efba  test    r15, r15
0x18026efbd  jz      short loc_18026EFD5
0x18026efbf  mov     rdx, [rbp+57h+var_C0]; __int64
0x18026efc3  lea     rcx, [rbp+57h+var_68]; this
0x18026efc7  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026efcc  mov     esi, eax
0x18026efce  test    eax, eax
0x18026efd0  js      short loc_18026F02D
0x18026efd2  add     rbx, r15
0x18026efd5  inc     r14
0x18026efd8  xor     r15d, r15d
0x18026efdb  jmp     short loc_18026EFF3
0x18026efdd  mov     rdx, [rbp+57h+var_C0]; __int64
0x18026efe1  lea     rcx, [rbp+57h+var_68]; this
0x18026efe5  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026efea  mov     esi, eax
0x18026efec  test    eax, eax
0x18026efee  js      short loc_18026F061
0x18026eff0  inc     rbx
0x18026eff3  lea     r8, [rbp+57h+arg_0]; bool *
0x18026eff7  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheHostRuntime *
0x18026effb  lea     rcx, [rbp+57h+var_88]; this
0x18026efff  call    ?FindNext@CacheHostRuntime@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheHostRuntime::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheHostRuntime &,bool &)
0x18026f004  mov     esi, eax
0x18026f006  test    eax, eax
0x18026f008  js      short loc_18026F05A
0x18026f00a  mov     rcx, [rbp+57h+var_70]
0x18026f00e  inc     rdi
0x18026f011  mov     rsi, [rbp+57h+arg_8]
0x18026f015  mov     [rbp+57h+var_70], r15
0x18026f019  test    rcx, rcx
0x18026f01c  jz      loc_18026EF58
0x18026f022  call    cs:__imp_SRCache_Free
0x18026f028  jmp     loc_18026EF58
0x18026f02d  mov     rcx, [rbp+5Fh]; this
0x18026f031  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f038  mov     r9d, esi; char *
0x18026f03b  mov     edx, 218h; void *
0x18026f040  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f045  mov     rcx, [rbp+57h+var_70]
0x18026f049  mov     [rbp+57h+var_70], 0
0x18026f051  jmp     short loc_18026F088
0x18026f053  mov     edx, 214h
0x18026f058  jmp     short loc_18026F06D
0x18026f05a  mov     edx, 220h
0x18026f05f  jmp     short loc_18026F06D
0x18026f061  mov     edx, 21Eh
0x18026f066  jmp     short loc_18026F06D
0x18026f068  mov     edx, 20Fh; void *
0x18026f06d  mov     rcx, [rbp+5Fh]; this
0x18026f071  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f078  mov     r9d, esi; char *
0x18026f07b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f080  mov     rcx, [rbp+57h+var_70]
0x18026f084  mov     [rbp+57h+var_70], r15
0x18026f088  test    rcx, rcx
0x18026f08b  jz      short loc_18026F093
0x18026f08d  call    cs:__imp_SRCache_Free
0x18026f093  lea     rcx, [rbp+57h+var_B0]; this
0x18026f097  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026f09c  mov     ebx, esi
0x18026f09e  lea     rcx, [rbp+57h+var_88]; this
0x18026f0a2  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026f0a7  jmp     loc_18026F2A8
0x18026f0ac  sub     rdi, r14
0x18026f0af  jz      short loc_18026F0D9
0x18026f0b1  test    cs:byte_1804DF881, 20h
0x18026f0b8  jz      short loc_18026F0D9
0x18026f0ba  mov     rax, qword ptr [rbp+57h+var_68]
0x18026f0be  lea     r8, aCachehostrunti; "CacheHostRuntime"
0x18026f0c5  mov     r9, rdi
0x18026f0c8  mov     [rsp+0F0h+var_D0], rax; int
0x18026f0cd  lea     rdx, CacheIntegrity_MissingCacheEntries
0x18026f0d4  call    McTemplateU0sxs_EventWriteTransfer
0x18026f0d9  lea     rcx, [rbp+57h+var_B0]; this
0x18026f0dd  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026f0e2  lea     rcx, [rbp+57h+var_88]; this
0x18026f0e6  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18026f0eb  lea     rcx, [rbp+57h+var_68]; this
0x18026f0ef  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x18026f0f4  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x18026f0f7  mov     [rbp+57h+var_A0], r15
0x18026f0fb  lea     rcx, [rbp+57h+var_A0]; this
0x18026f0ff  mov     [rbp+57h+var_98], r15d
0x18026f103  mov     [rbp+57h+var_90], r15
0x18026f107  call    ?Open@HostRuntimeIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x18026f10c  mov     edi, eax
0x18026f10e  test    eax, eax
0x18026f110  jns     short loc_18026F15C
0x18026f112  mov     rcx, [rbp+5Fh]; this
0x18026f116  lea     r8, aOnecoreBaseApp_402; "onecore\\base\\appmodel\\StateRepositor"...
0x18026f11d  mov     r9d, eax; char *
0x18026f120  mov     edx, 275h; void *
0x18026f125  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f12a  mov     rcx, [rbp+5Fh]; this
0x18026f12e  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f135  mov     r9d, edi; char *
0x18026f138  mov     edx, 231h; void *
0x18026f13d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f142  mov     rcx, [rbp+57h+var_A0]
0x18026f146  mov     [rbp+57h+var_A0], r15
0x18026f14a  test    rcx, rcx
0x18026f14d  jz      short loc_18026F155
0x18026f14f  call    cs:__imp_SRCacheContext_Close
0x18026f155  mov     ebx, edi
0x18026f157  jmp     loc_18026F2A8
0x18026f15c  xorps   xmm0, xmm0
0x18026f15f  mov     qword ptr [rbp+57h+var_B0], r15
0x18026f163  lea     r9, [rbp+57h+arg_0]
0x18026f167  mov     [rbp+57h+arg_0], r15b
0x18026f16b  lea     r8, [rbp+57h+var_C0]
0x18026f16f  lea     rcx, [rbp+57h+var_A0]
0x18026f173  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x18026f178  call    ?Get@HostRuntimeIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@HostRuntime_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Get(StateRepository::Cache::Entity::HostRuntime_NoThrow::CacheFlags,StateRepository::Cache::Entity::HostRuntime_NoThrow &,bool &)
0x18026f17d  mov     edi, eax
0x18026f17f  test    eax, eax
0x18026f181  jns     short loc_18026F1B0
0x18026f183  mov     rcx, [rbp+5Fh]; this
0x18026f187  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f18e  mov     r9d, eax; char *
0x18026f191  mov     edx, 234h; void *
0x18026f196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f19b  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18026f19f  mov     qword ptr [rbp+57h+var_B0], r15
0x18026f1a3  test    rcx, rcx
0x18026f1a6  jz      short loc_18026F142
0x18026f1a8  call    cs:__imp_SRCache_Free
0x18026f1ae  jmp     short loc_18026F142
0x18026f1b0  mov     rdi, r15
0x18026f1b3  cmp     [rbp+57h+arg_0], r15b
0x18026f1b7  jz      loc_18026F2B6
0x18026f1bd  mov     r9, [rbp+57h+var_C0]; char *
0x18026f1c1  lea     rax, [rbp+57h+arg_0]
0x18026f1c5  xorps   xmm0, xmm0
0x18026f1c8  mov     [rsp+0F0h+var_D0], rax; int
0x18026f1cd  xorps   xmm1, xmm1
0x18026f1d0  lea     rdx, aSelectExistsSe_72; "SELECT EXISTS(SELECT 1 FROM CacheHostRu"...
0x18026f1d7  xor     r8d, r8d; char *
0x18026f1da  mov     rcx, r13; this
0x18026f1dd  movdqu  [rbp+57h+var_50], xmm0
0x18026f1e2  movdqu  [rbp+57h+var_40], xmm1
0x18026f1e7  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026f1ec  mov     esi, eax
0x18026f1ee  test    eax, eax
0x18026f1f0  js      short loc_18026F247
0x18026f1f2  cmp     [rbp+57h+arg_0], r15b
0x18026f1f6  jnz     short loc_18026F211
0x18026f1f8  mov     rdx, [rbp+57h+var_C0]; __int64
0x18026f1fc  lea     rcx, [rbp+57h+var_68]; this
0x18026f200  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x18026f205  mov     esi, eax
0x18026f207  test    eax, eax
0x18026f209  js      short loc_18026F239
0x18026f20b  inc     rdi
0x18026f20e  inc     rbx
0x18026f211  inc     [rbp+57h+var_98]
0x18026f214  lea     r9, [rbp+57h+arg_0]
0x18026f218  lea     r8, [rbp+57h+var_C0]
0x18026f21c  lea     rcx, [rbp+57h+var_A0]
0x18026f220  call    ?Get@HostRuntimeIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@HostRuntime_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::HostRuntimeIterator_NoThrow::Get(StateRepository::Cache::Entity::HostRuntime_NoThrow::CacheFlags,StateRepository::Cache::Entity::HostRuntime_NoThrow &,bool &)
0x18026f225  mov     esi, eax
0x18026f227  test    eax, eax
0x18026f229  js      short loc_18026F240
0x18026f22b  lea     rcx, [rbp+57h+var_40]; this
0x18026f22f  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026f234  jmp     loc_18026F1B3
0x18026f239  mov     edx, 23Dh
0x18026f23e  jmp     short loc_18026F264
0x18026f240  mov     edx, 23Fh
0x18026f245  jmp     short loc_18026F264
0x18026f247  mov     rcx, [rbp+5Fh]; this
0x18026f24b  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f252  mov     r9d, esi; char *
0x18026f255  mov     edx, 46h ; 'F'; void *
0x18026f25a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f25f  mov     edx, 238h; void *
0x18026f264  mov     rcx, [rbp+5Fh]; this
0x18026f268  lea     r8, aOnecoreBaseApp_246; "onecore\\base\\appmodel\\staterepositor"...
0x18026f26f  mov     r9d, esi; char *
0x18026f272  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026f277  lea     rcx, [rbp+57h+var_40]; this
0x18026f27b  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026f280  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18026f284  mov     qword ptr [rbp+57h+var_B0], r15
0x18026f288  test    rcx, rcx
0x18026f28b  jz      short loc_18026F293
0x18026f28d  call    cs:__imp_SRCache_Free
0x18026f293  mov     rcx, [rbp+57h+var_A0]
0x18026f297  mov     [rbp+57h+var_A0], r15
0x18026f29b  test    rcx, rcx
0x18026f29e  jz      short loc_18026F2A6
0x18026f2a0  call    cs:__imp_SRCacheContext_Close
0x18026f2a6  mov     ebx, esi
0x18026f2a8  lea     rcx, [rbp+57h+var_68]; this
0x18026f2ac  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x18026f2b1  jmp     loc_18026F341
0x18026f2b6  mov     rcx, qword ptr [rbp+57h+var_B0]
0x18026f2ba  mov     qword ptr [rbp+57h+var_B0], r15
0x18026f2be  test    rcx, rcx
0x18026f2c1  jz      short loc_18026F2C9
0x18026f2c3  call    cs:__imp_SRCache_Free
0x18026f2c9  mov     rcx, [rbp+57h+var_A0]
0x18026f2cd  mov     [rbp+57h+var_A0], r15
0x18026f2d1  test    rcx, rcx
0x18026f2d4  jz      short loc_18026F2DC
0x18026f2d6  call    cs:__imp_SRCacheContext_Close
0x18026f2dc  test    rdi, rdi
0x18026f2df  jz      short loc_18026F309
0x18026f2e1  test    cs:byte_1804DF881, 20h
0x18026f2e8  jz      short loc_18026F309
0x18026f2ea  mov     rax, qword ptr [rbp+57h+var_68]
0x18026f2ee  lea     r8, aCachehostrunti; "CacheHostRuntime"
0x18026f2f5  mov     r9, rdi
  ... truncated ...
```
