# StateRepository::Entity::CacheAppUriHandlerGroup::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x180268d10`
- end: `0x1802691f5`
- name: `?Cache_CheckIntegrity@CacheAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1253`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x1800a6be8`
- `0x1800ae890`
- `0x180183aac`
- `0x18026544c`
- `0x180268bdc`
- `0x180268d10`
- `0x180269298`
- `0x180269308`
- `0x1802693d0`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180268fef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180269140`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180269176`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180268fef`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180269140`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180269176`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180268ec2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180268f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180269048`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026912d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180269163`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180268ec2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180268f2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180269048`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18026912d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180269163`

## string_xrefs

- `0x180268fb6`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppUriHandlerGroup.hpp`
- `0x180268d85`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180268dcd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180268ed1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180268f11`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180268fce`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180269027`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x1802690eb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180269108`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x1802691d2`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandlergroup.cpp`
- `0x180268f5e`: `CacheAppUriHandlerGroup`
- `0x18026918e`: `CacheAppUriHandlerGroup`
- `0x180269070`: `SELECT EXISTS(SELECT 1 FROM CacheAppUriHandlerGroup WHERE _CacheAppUriHandlerGroupID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheAppUriHandlerGroup::Cache_CheckIntegrity(
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
  char *v32; // rcx
  __int64 v33; // rdi
  int v34; // eax
  __int64 v35; // rdx
  char v36; // r8
  int v37; // esi
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r8
  char *v41; // rcx
  __int64 v42; // rcx
  char *v43; // rcx
  __int64 v44; // rcx
  bool *v46; // [rsp+20h] [rbp-79h]
  int v47; // [rsp+20h] [rbp-79h]
  int v48; // [rsp+20h] [rbp-79h]
  bool *v49; // [rsp+28h] [rbp-71h]
  char *v50[2]; // [rsp+30h] [rbp-69h] BYREF
  __int128 v51; // [rsp+40h] [rbp-59h]
  __int64 v52; // [rsp+50h] [rbp-49h] BYREF
  int v53; // [rsp+58h] [rbp-41h]
  __int64 v54; // [rsp+60h] [rbp-39h]
  __int64 v55; // [rsp+68h] [rbp-31h] BYREF
  __int128 v56; // [rsp+70h] [rbp-29h] BYREF
  __int64 v57; // [rsp+80h] [rbp-19h]
  int v58[2]; // [rsp+88h] [rbp-11h] BYREF
  __int64 v59; // [rsp+90h] [rbp-9h]
  unsigned __int64 v60[11]; // [rsp+98h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  bool v62; // [rsp+100h] [rbp+67h] BYREF
  struct StateRepository::Cache::Manager_NoThrow *v63; // [rsp+108h] [rbp+6Fh]
  _QWORD *v64; // [rsp+118h] [rbp+7Fh]

  v64 = a4;
  v63 = a2;
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
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
  v8 = StateRepository::Entity::CacheAppUriHandlerGroup::Find(a1, (struct StateRepository::Statement *)&v55);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x207,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
      (const char *)(unsigned int)v8,
      (int)v46);
LABEL_32:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v55);
LABEL_60:
    StateRepository::TextA::Reset((StateRepository::TextA *)v58);
    return v6;
  }
  v62 = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  Next = StateRepository::Entity::CacheAppUriHandlerGroup::FindNext(
           (struct StateRepository::Statement *)&v55,
           (struct StateRepository::Entity::CacheAppUriHandlerGroup *)v50,
           &v62);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
      (const char *)(unsigned int)Next,
      (int)v46);
    StateRepository::TextA::Reset((StateRepository::TextA *)&v50[1]);
    goto LABEL_32;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v62 )
  {
    v46 = &v62;
    v57 = 0;
    v56 = 0;
    v15 = StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Get(v4, v50[0], v11, &v56);
    if ( v15 < 0 )
    {
      v21 = 527;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v21,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
        (const char *)(unsigned int)v15,
        (int)&v62);
      v20 = *((_QWORD *)&v56 + 1);
      *((_QWORD *)&v56 + 1) = 0;
LABEL_29:
      if ( v20 )
        SRCache_Free(v20);
      StateRepository::TextA::Reset((StateRepository::TextA *)&v50[1]);
      v6 = v15;
      goto LABEL_32;
    }
    if ( v62 )
    {
      v60[0] = 0;
      v15 = StateRepository::Entity::CacheAppUriHandlerGroup::Cache_Check(
              (const struct StateRepository::Entity::CacheAppUriHandlerGroup *)v50,
              (const struct StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow *)&v56,
              v60);
      if ( v15 < 0 )
      {
        v21 = 532;
        goto LABEL_28;
      }
      v18 = v60[0];
      if ( v60[0] )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v50[0], v17);
        v15 = appended;
        if ( appended < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x218,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
            (const char *)(unsigned int)appended,
            (int)&v62);
          v20 = *((_QWORD *)&v56 + 1);
          *((_QWORD *)&v56 + 1) = 0;
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
    v15 = StateRepository::Entity::CacheAppUriHandlerGroup::FindNext(
            (struct StateRepository::Statement *)&v55,
            (struct StateRepository::Entity::CacheAppUriHandlerGroup *)v50,
            &v62);
    if ( v15 < 0 )
    {
      v21 = 544;
      goto LABEL_28;
    }
    v10 = *((_QWORD *)&v56 + 1);
    ++v13;
    v4 = v63;
    *((_QWORD *)&v56 + 1) = 0;
    if ( v10 )
      SRCache_Free(v10);
  }
  v22 = v13 - v14;
  if ( v22 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheAppUriHandlerGroup",
      v22,
      *(__int64 *)v58);
  StateRepository::TextA::Reset((StateRepository::TextA *)&v50[1]);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v55);
  StateRepository::TextA::Clear((StateRepository::TextA *)v58);
  v52 = 0;
  v53 = 0;
  v54 = 0;
  v23 = StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow *)&v52,
          v4);
  v25 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x275,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v23,
      (int)v46);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x231,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
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
  v62 = 0;
  *(_OWORD *)v50 = 0;
  v29 = StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Get(&v52, v24, v50, &v62);
  v25 = v29;
  if ( v29 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x234,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
      (const char *)(unsigned int)v29,
      (int)v46);
    v32 = v50[1];
    v50[1] = 0;
    if ( v32 )
      SRCache_Free(v32);
    goto LABEL_38;
  }
  v33 = 0;
  while ( v62 )
  {
    memset(&v60[1], 0, 32);
    v34 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheAppUriHandlerGroup WHERE _CacheAppUriHa"
                                                "ndlerGroupID=? LIMIT 1);",
            0,
            v50[0],
            (__int64)&v62,
            v49);
    v37 = v34;
    if ( v34 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x46,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
        (const char *)(unsigned int)v34,
        v48);
      v38 = 568;
      goto LABEL_55;
    }
    if ( !v62 )
    {
      v37 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v58, (__int64)v50[0], v36);
      if ( v37 < 0 )
      {
        v38 = 573;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v38,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandlergroup.cpp",
          (const char *)(unsigned int)v37,
          v48);
        StateRepository::TextA::Reset((StateRepository::TextA *)&v60[2]);
        v41 = v50[1];
        v50[1] = 0;
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
    v37 = StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Get(&v52, v35, v50, &v62);
    if ( v37 < 0 )
    {
      v38 = 575;
      goto LABEL_55;
    }
    StateRepository::TextA::Reset((StateRepository::TextA *)&v60[2]);
  }
  v43 = v50[1];
  v50[1] = 0;
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
      (unsigned int)"CacheAppUriHandlerGroup",
      v33,
      *(__int64 *)v58);
  *v64 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v58);
  return 0;
}

```

## disassembly

```asm
0x180268d10  mov     [rsp-8+arg_18], r9
0x180268d15  mov     [rsp-8+arg_8], rdx
0x180268d1a  push    rbp
0x180268d1b  push    rbx
0x180268d1c  push    rsi
0x180268d1d  push    rdi
0x180268d1e  push    r13
0x180268d20  push    r14
0x180268d22  push    r15
0x180268d24  lea     rbp, [rsp-27h]
0x180268d29  sub     rsp, 0C0h
0x180268d30  xor     r15d, r15d
0x180268d33  mov     rsi, rdx
0x180268d36  mov     r13, rcx
0x180268d39  cmp     [rcx], r15
0x180268d3c  jz      loc_1802691C4
0x180268d42  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180268d47  test    al, al
0x180268d49  jz      short loc_180268D5A
0x180268d4b  mov     ebx, 8067000Bh
0x180268d50  mov     edx, 1FBh
0x180268d55  jmp     loc_1802691CE
0x180268d5a  cmp     [rsi], r15
0x180268d5d  jz      loc_1802691BD
0x180268d63  lea     rdx, [rbp+57h+var_88]; struct StateRepository::Statement *
0x180268d67  mov     qword ptr [rbp+57h+var_68], r15
0x180268d6b  mov     rcx, r13; struct StateRepository::Database *
0x180268d6e  mov     [rbp+57h+var_60], r15
0x180268d72  mov     [rbp+57h+var_88], r15
0x180268d76  call    ?Find@CacheAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheAppUriHandlerGroup::Find(StateRepository::Database &,StateRepository::Statement &)
0x180268d7b  mov     ebx, eax
0x180268d7d  test    eax, eax
0x180268d7f  jns     short loc_180268D9E
0x180268d81  mov     rcx, [rbp+5Fh]; this
0x180268d85  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x180268d8c  mov     r9d, eax; char *
0x180268d8f  mov     edx, 207h; void *
0x180268d94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268d99  jmp     loc_180268F3E
0x180268d9e  xorps   xmm0, xmm0
0x180268da1  mov     [rbp+57h+arg_0], r15b
0x180268da5  xorps   xmm1, xmm1
0x180268da8  lea     r8, [rbp+57h+arg_0]; bool *
0x180268dac  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheAppUriHandlerGroup *
0x180268db0  lea     rcx, [rbp+57h+var_88]; struct StateRepository::Statement *
0x180268db4  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180268db9  movdqu  [rbp+57h+var_B0], xmm1
0x180268dbe  call    ?FindNext@CacheAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppUriHandlerGroup::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppUriHandlerGroup &,bool &)
0x180268dc3  mov     ebx, eax
0x180268dc5  test    eax, eax
0x180268dc7  jns     short loc_180268DEF
0x180268dc9  mov     rcx, [rbp+5Fh]; this
0x180268dcd  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x180268dd4  mov     r9d, eax; char *
0x180268dd7  mov     edx, 20Ah; void *
0x180268ddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268de1  lea     rcx, [rbp+57h+var_C0+8]; this
0x180268de5  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180268dea  jmp     loc_180268F3E
0x180268def  mov     rbx, r15
0x180268df2  mov     rdi, r15
0x180268df5  mov     r14, r15
0x180268df8  cmp     [rbp+57h+arg_0], r15b
0x180268dfc  jz      loc_180268F4C
0x180268e02  mov     rdx, [rbp+57h+var_C0]
0x180268e06  lea     rax, [rbp+57h+arg_0]
0x180268e0a  xorps   xmm0, xmm0
0x180268e0d  mov     [rsp+0F0h+var_D0], rax; int
0x180268e12  lea     r9, [rbp+57h+var_80]
0x180268e16  mov     [rbp+57h+var_70], r15
0x180268e1a  mov     rcx, rsi
0x180268e1d  movdqu  [rbp+57h+var_80], xmm0
0x180268e22  call    ?Get@AppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow &,bool &)
0x180268e27  mov     esi, eax
0x180268e29  test    eax, eax
0x180268e2b  js      loc_180268F08
0x180268e31  cmp     [rbp+57h+arg_0], r15b
0x180268e35  jz      short loc_180268E7D
0x180268e37  lea     r8, [rbp+57h+var_58]; unsigned __int64 *
0x180268e3b  mov     [rbp+57h+var_58], r15
0x180268e3f  lea     rdx, [rbp+57h+var_80]; struct StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow *
0x180268e43  lea     rcx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheAppUriHandlerGroup *
0x180268e47  call    ?Cache_Check@CacheAppUriHandlerGroup@Entity@StateRepository@@CAJAEBV123@AEBVAppUriHandlerGroup_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheAppUriHandlerGroup::Cache_Check(StateRepository::Entity::CacheAppUriHandlerGroup const &,StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow const &,unsigned __int64 &)
0x180268e4c  mov     esi, eax
0x180268e4e  test    eax, eax
0x180268e50  js      loc_180268EF3
0x180268e56  mov     r15, [rbp+57h+var_58]
0x180268e5a  test    r15, r15
0x180268e5d  jz      short loc_180268E75
0x180268e5f  mov     rdx, [rbp+57h+var_C0]; __int64
0x180268e63  lea     rcx, [rbp+57h+var_68]; this
0x180268e67  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180268e6c  mov     esi, eax
0x180268e6e  test    eax, eax
0x180268e70  js      short loc_180268ECD
0x180268e72  add     rbx, r15
0x180268e75  inc     r14
0x180268e78  xor     r15d, r15d
0x180268e7b  jmp     short loc_180268E93
0x180268e7d  mov     rdx, [rbp+57h+var_C0]; __int64
0x180268e81  lea     rcx, [rbp+57h+var_68]; this
0x180268e85  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x180268e8a  mov     esi, eax
0x180268e8c  test    eax, eax
0x180268e8e  js      short loc_180268F01
0x180268e90  inc     rbx
0x180268e93  lea     r8, [rbp+57h+arg_0]; bool *
0x180268e97  lea     rdx, [rbp+57h+var_C0]; struct StateRepository::Entity::CacheAppUriHandlerGroup *
0x180268e9b  lea     rcx, [rbp+57h+var_88]; struct StateRepository::Statement *
0x180268e9f  call    ?FindNext@CacheAppUriHandlerGroup@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppUriHandlerGroup::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppUriHandlerGroup &,bool &)
0x180268ea4  mov     esi, eax
0x180268ea6  test    eax, eax
0x180268ea8  js      short loc_180268EFA
0x180268eaa  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180268eae  inc     rdi
0x180268eb1  mov     rsi, [rbp+57h+arg_8]
0x180268eb5  mov     qword ptr [rbp+57h+var_80+8], r15
0x180268eb9  test    rcx, rcx
0x180268ebc  jz      loc_180268DF8
0x180268ec2  call    cs:__imp_SRCache_Free
0x180268ec8  jmp     loc_180268DF8
0x180268ecd  mov     rcx, [rbp+5Fh]; this
0x180268ed1  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x180268ed8  mov     r9d, esi; char *
0x180268edb  mov     edx, 218h; void *
0x180268ee0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268ee5  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180268ee9  mov     qword ptr [rbp+57h+var_80+8], 0
0x180268ef1  jmp     short loc_180268F28
0x180268ef3  mov     edx, 214h
0x180268ef8  jmp     short loc_180268F0D
0x180268efa  mov     edx, 220h
0x180268eff  jmp     short loc_180268F0D
0x180268f01  mov     edx, 21Eh
0x180268f06  jmp     short loc_180268F0D
0x180268f08  mov     edx, 20Fh; void *
0x180268f0d  mov     rcx, [rbp+5Fh]; this
0x180268f11  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x180268f18  mov     r9d, esi; char *
0x180268f1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268f20  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x180268f24  mov     qword ptr [rbp+57h+var_80+8], r15
0x180268f28  test    rcx, rcx
0x180268f2b  jz      short loc_180268F33
0x180268f2d  call    cs:__imp_SRCache_Free
0x180268f33  lea     rcx, [rbp+57h+var_C0+8]; this
0x180268f37  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180268f3c  mov     ebx, esi
0x180268f3e  lea     rcx, [rbp+57h+var_88]; this
0x180268f42  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180268f47  jmp     loc_180269148
0x180268f4c  sub     rdi, r14
0x180268f4f  jz      short loc_180268F79
0x180268f51  test    cs:byte_1804DF881, 20h
0x180268f58  jz      short loc_180268F79
0x180268f5a  mov     rax, qword ptr [rbp+57h+var_68]
0x180268f5e  lea     r8, aCacheappurihan_0; "CacheAppUriHandlerGroup"
0x180268f65  mov     r9, rdi
0x180268f68  mov     [rsp+0F0h+var_D0], rax; int
0x180268f6d  lea     rdx, CacheIntegrity_MissingCacheEntries
0x180268f74  call    McTemplateU0sxs_EventWriteTransfer
0x180268f79  lea     rcx, [rbp+57h+var_C0+8]; this
0x180268f7d  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180268f82  lea     rcx, [rbp+57h+var_88]; this
0x180268f86  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180268f8b  lea     rcx, [rbp+57h+var_68]; this
0x180268f8f  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x180268f94  mov     rdx, rsi; struct StateRepository::Cache::Manager_NoThrow *
0x180268f97  mov     [rbp+57h+var_A0], r15
0x180268f9b  lea     rcx, [rbp+57h+var_A0]; this
0x180268f9f  mov     [rbp+57h+var_98], r15d
0x180268fa3  mov     [rbp+57h+var_90], r15
0x180268fa7  call    ?Open@AppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x180268fac  mov     edi, eax
0x180268fae  test    eax, eax
0x180268fb0  jns     short loc_180268FFC
0x180268fb2  mov     rcx, [rbp+5Fh]; this
0x180268fb6  lea     r8, aOnecoreBaseApp_116; "onecore\\base\\appmodel\\StateRepositor"...
0x180268fbd  mov     r9d, eax; char *
0x180268fc0  mov     edx, 275h; void *
0x180268fc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268fca  mov     rcx, [rbp+5Fh]; this
0x180268fce  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x180268fd5  mov     r9d, edi; char *
0x180268fd8  mov     edx, 231h; void *
0x180268fdd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180268fe2  mov     rcx, [rbp+57h+var_A0]
0x180268fe6  mov     [rbp+57h+var_A0], r15
0x180268fea  test    rcx, rcx
0x180268fed  jz      short loc_180268FF5
0x180268fef  call    cs:__imp_SRCacheContext_Close
0x180268ff5  mov     ebx, edi
0x180268ff7  jmp     loc_180269148
0x180268ffc  xorps   xmm0, xmm0
0x180268fff  mov     qword ptr [rbp+57h+var_B0], r15
0x180269003  lea     r9, [rbp+57h+arg_0]
0x180269007  mov     [rbp+57h+arg_0], r15b
0x18026900b  lea     r8, [rbp+57h+var_C0]
0x18026900f  lea     rcx, [rbp+57h+var_A0]
0x180269013  movdqu  xmmword ptr [rbp+57h+var_C0], xmm0
0x180269018  call    ?Get@AppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow &,bool &)
0x18026901d  mov     edi, eax
0x18026901f  test    eax, eax
0x180269021  jns     short loc_180269050
0x180269023  mov     rcx, [rbp+5Fh]; this
0x180269027  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18026902e  mov     r9d, eax; char *
0x180269031  mov     edx, 234h; void *
0x180269036  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18026903b  mov     rcx, [rbp+57h+var_C0+8]
0x18026903f  mov     [rbp+57h+var_C0+8], r15
0x180269043  test    rcx, rcx
0x180269046  jz      short loc_180268FE2
0x180269048  call    cs:__imp_SRCache_Free
0x18026904e  jmp     short loc_180268FE2
0x180269050  mov     rdi, r15
0x180269053  cmp     [rbp+57h+arg_0], r15b
0x180269057  jz      loc_180269156
0x18026905d  mov     r9, [rbp+57h+var_C0]; char *
0x180269061  lea     rax, [rbp+57h+arg_0]
0x180269065  xorps   xmm0, xmm0
0x180269068  mov     [rsp+0F0h+var_D0], rax; int
0x18026906d  xorps   xmm1, xmm1
0x180269070  lea     rdx, aSelectExistsSe_708; "SELECT EXISTS(SELECT 1 FROM CacheAppUri"...
0x180269077  xor     r8d, r8d; char *
0x18026907a  mov     rcx, r13; this
0x18026907d  movdqu  [rbp+57h+var_50], xmm0
0x180269082  movdqu  [rbp+57h+var_40], xmm1
0x180269087  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x18026908c  mov     esi, eax
0x18026908e  test    eax, eax
0x180269090  js      short loc_1802690E7
0x180269092  cmp     [rbp+57h+arg_0], r15b
0x180269096  jnz     short loc_1802690B1
0x180269098  mov     rdx, [rbp+57h+var_C0]; __int64
0x18026909c  lea     rcx, [rbp+57h+var_68]; this
0x1802690a0  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1802690a5  mov     esi, eax
0x1802690a7  test    eax, eax
0x1802690a9  js      short loc_1802690D9
0x1802690ab  inc     rdi
0x1802690ae  inc     rbx
0x1802690b1  inc     [rbp+57h+var_98]
0x1802690b4  lea     r9, [rbp+57h+arg_0]
0x1802690b8  lea     r8, [rbp+57h+var_C0]
0x1802690bc  lea     rcx, [rbp+57h+var_A0]
0x1802690c0  call    ?Get@AppUriHandlerGroupIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandlerGroup_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerGroupIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandlerGroup_NoThrow &,bool &)
0x1802690c5  mov     esi, eax
0x1802690c7  test    eax, eax
0x1802690c9  js      short loc_1802690E0
0x1802690cb  lea     rcx, [rbp+57h+var_50+8]; this
0x1802690cf  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1802690d4  jmp     loc_180269053
0x1802690d9  mov     edx, 23Dh
0x1802690de  jmp     short loc_180269104
0x1802690e0  mov     edx, 23Fh
0x1802690e5  jmp     short loc_180269104
0x1802690e7  mov     rcx, [rbp+5Fh]; this
0x1802690eb  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x1802690f2  mov     r9d, esi; char *
0x1802690f5  mov     edx, 46h ; 'F'; void *
0x1802690fa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802690ff  mov     edx, 238h; void *
0x180269104  mov     rcx, [rbp+5Fh]; this
0x180269108  lea     r8, aOnecoreBaseApp_384; "onecore\\base\\appmodel\\staterepositor"...
0x18026910f  mov     r9d, esi; char *
0x180269112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180269117  lea     rcx, [rbp+57h+var_50+8]; this
0x18026911b  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180269120  mov     rcx, [rbp+57h+var_C0+8]
0x180269124  mov     [rbp+57h+var_C0+8], r15
0x180269128  test    rcx, rcx
0x18026912b  jz      short loc_180269133
0x18026912d  call    cs:__imp_SRCache_Free
0x180269133  mov     rcx, [rbp+57h+var_A0]
0x180269137  mov     [rbp+57h+var_A0], r15
0x18026913b  test    rcx, rcx
0x18026913e  jz      short loc_180269146
0x180269140  call    cs:__imp_SRCacheContext_Close
0x180269146  mov     ebx, esi
0x180269148  lea     rcx, [rbp+57h+var_68]; this
0x18026914c  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180269151  jmp     loc_1802691E1
0x180269156  mov     rcx, [rbp+57h+var_C0+8]
0x18026915a  mov     [rbp+57h+var_C0+8], r15
0x18026915e  test    rcx, rcx
0x180269161  jz      short loc_180269169
0x180269163  call    cs:__imp_SRCache_Free
0x180269169  mov     rcx, [rbp+57h+var_A0]
0x18026916d  mov     [rbp+57h+var_A0], r15
0x180269171  test    rcx, rcx
0x180269174  jz      short loc_18026917C
0x180269176  call    cs:__imp_SRCacheContext_Close
0x18026917c  test    rdi, rdi
0x18026917f  jz      short loc_1802691A9
0x180269181  test    cs:byte_1804DF881, 20h
0x180269188  jz      short loc_1802691A9
0x18026918a  mov     rax, qword ptr [rbp+57h+var_68]
0x18026918e  lea     r8, aCacheappurihan_0; "CacheAppUriHandlerGroup"
0x180269195  mov     r9, rdi
  ... truncated ...
```
