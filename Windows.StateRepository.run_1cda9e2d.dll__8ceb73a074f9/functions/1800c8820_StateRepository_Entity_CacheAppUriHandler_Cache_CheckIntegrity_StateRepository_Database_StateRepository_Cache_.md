# StateRepository::Entity::CacheAppUriHandler::Cache_CheckIntegrity(StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::ExecutionFlags,unsigned __int64 &)

- ea: `0x1800c8820`
- end: `0x1800c8d39`
- name: `?Cache_CheckIntegrity@CacheAppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVManager_NoThrow@Cache@3@W4ExecutionFlags@3@AEA_K@Z`
- size: `1305`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180007a40`
- `0x18001a9e0`
- `0x1800337a4`
- `0x180062cd8`
- `0x18007322c`
- `0x18009e5dc`
- `0x1800ae890`
- `0x1800b8874`
- `0x1800c8820`
- `0x1800c8d40`
- `0x18026544c`
- `0x18026862c`
- `0x180268938`
- `0x180268a00`
- `0x180268ae0`
- `0x1802755a8`
- `0x180275b1c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8b08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8c7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8cac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8b08`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8c7c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800c8cac`

## string_xrefs

- `0x1800c889b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c88fb`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8a28`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8ae5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8b53`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8c2e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8c4b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8d0d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler.cpp`
- `0x1800c8acd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppUriHandler.hpp`
- `0x1800c8a6e`: `CacheAppUriHandler`
- `0x1800c8cc5`: `CacheAppUriHandler`
- `0x1800c8ba7`: `SELECT EXISTS(SELECT 1 FROM CacheAppUriHandler WHERE _CacheAppUriHandlerID=? LIMIT 1);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheAppUriHandler::Cache_CheckIntegrity(
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
  __int128 v46; // [rsp+70h] [rbp-90h]
  __int128 v47; // [rsp+80h] [rbp-80h]
  __int128 v48; // [rsp+90h] [rbp-70h]
  __int64 v49; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v50; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v51[3]; // [rsp+B8h] [rbp-48h] BYREF
  _OWORD v52[4]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+130h] [rbp+30h]
  wil::details::in1diag3 *retaddr; // [rsp+178h] [rbp+78h]
  bool v55; // [rsp+180h] [rbp+80h] BYREF
  _QWORD *v56; // [rsp+198h] [rbp+98h]

  v56 = a4;
  if ( !*(_QWORD *)a1 )
  {
    v7 = 791;
    goto LABEL_62;
  }
  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v6 = -2140733429;
    v7 = 792;
LABEL_63:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
      (const char *)v6,
      (int)v35);
    return v6;
  }
  if ( !*(_QWORD *)a2 )
  {
    v7 = 793;
LABEL_62:
    v6 = -2147019873;
    goto LABEL_63;
  }
  *(_QWORD *)v43 = 0;
  v44 = 0;
  v42 = 0;
  v8 = StateRepository::Entity::CacheAppUriHandler::Find(a1, (struct StateRepository::Statement *)&v42);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x324,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
      (const char *)(unsigned int)v8,
      (int)v35);
LABEL_28:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
LABEL_53:
    StateRepository::TextA::Reset((StateRepository::TextA *)v43);
    return v6;
  }
  v49 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v55 = 0;
  Next = StateRepository::Entity::CacheAppUriHandler::FindNext(
           (struct StateRepository::Statement *)&v42,
           (struct StateRepository::Entity::CacheAppUriHandler *)v45,
           &v55);
  v6 = Next;
  if ( Next < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x327,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
      (const char *)(unsigned int)Next,
      (int)v35);
    StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler((StateRepository::Entity::CacheAppUriHandler *)v45);
    goto LABEL_28;
  }
  v12 = 0;
  v13 = 0;
  v14 = 0;
  while ( v55 )
  {
    v35 = &v55;
    memset(v51, 0, sizeof(v51));
    appended = StateRepository::Cache::Entity::AppUriHandler_NoThrow::Get(a2, v45[0], v11, v51);
    if ( appended < 0 )
    {
      v19 = 812;
      goto LABEL_27;
    }
    if ( v55 )
    {
      v50 = 0;
      appended = StateRepository::Entity::CacheAppUriHandler::Cache_Check(
                   (const struct StateRepository::Entity::CacheAppUriHandler *)v45,
                   (const struct StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v51,
                   &v50);
      if ( appended < 0 )
      {
        v19 = 817;
        goto LABEL_27;
      }
      v18 = v50;
      if ( v50 )
      {
        appended = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v17);
        if ( appended < 0 )
        {
          v19 = 821;
LABEL_27:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
            (const char *)(unsigned int)appended,
            (int)&v55);
          StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v51);
          StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler((StateRepository::Entity::CacheAppUriHandler *)v45);
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
        v19 = 827;
        goto LABEL_27;
      }
      ++v12;
    }
    appended = StateRepository::Entity::CacheAppUriHandler::FindNext(
                 (struct StateRepository::Statement *)&v42,
                 (struct StateRepository::Entity::CacheAppUriHandler *)v45,
                 &v55);
    if ( appended < 0 )
    {
      v19 = 829;
      goto LABEL_27;
    }
    ++v13;
    StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v51);
  }
  v20 = v13 - v14;
  if ( v20 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v10,
      (unsigned int)&CacheIntegrity_MissingCacheEntries,
      (unsigned int)"CacheAppUriHandler",
      v20,
      *(__int64 *)v43);
  StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler((StateRepository::Entity::CacheAppUriHandler *)v45);
  StateRepository::Statement::~Statement((StateRepository::Statement *)&v42);
  StateRepository::TextA::Clear((StateRepository::TextA *)v43);
  v39 = 0;
  v40 = 0;
  v41 = 0;
  v21 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Open(
          (StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow *)&v39,
          a2);
  v23 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BD,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppUriHandler.hpp",
      (const char *)(unsigned int)v21,
      (int)v35);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
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
  v55 = 0;
  *(_OWORD *)v45 = 0;
  v46 = 0;
  v47 = 0;
  v25 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(&v39, v22, v45, &v55);
  v23 = v25;
  if ( v25 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x351,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
      (const char *)(unsigned int)v25,
      (int)v35);
    StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v45);
    goto LABEL_34;
  }
  v26 = 0;
  while ( v55 )
  {
    memset(v52, 0, sizeof(v52));
    v53 = 0;
    v27 = StateRepository::StatementExecution::PrepareAndBindAndExists(
            a1,
            (struct StateRepository::Database *)"SELECT EXISTS(SELECT 1 FROM CacheAppUriHandler WHERE _CacheAppUriHandlerID=? LIMIT 1);",
            0,
            v45[0],
            (__int64)&v55,
            v38);
    v30 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
        (const char *)(unsigned int)v27,
        v37);
      v31 = 853;
      goto LABEL_50;
    }
    if ( !v55 )
    {
      v30 = StateRepository::TextA::AppendDelimited((StateRepository::TextA *)v43, (__int64)v45[0], v29);
      if ( v30 < 0 )
      {
        v31 = 858;
LABEL_50:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler.cpp",
          (const char *)(unsigned int)v30,
          v37);
        StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler((StateRepository::Entity::CacheAppUriHandler *)v52);
        StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v45);
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
    v30 = StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(&v39, v28, v45, &v55);
    if ( v30 < 0 )
    {
      v31 = 860;
      goto LABEL_50;
    }
    StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler((StateRepository::Entity::CacheAppUriHandler *)v52);
  }
  StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow((StateRepository::Cache::Entity::AppUriHandler_NoThrow *)v45);
  v33 = v39;
  v39 = 0;
  if ( v33 )
    SRCacheContext_Close(v33);
  if ( v26 && (byte_1804DF881 & 0x20) != 0 )
    McTemplateU0sxs_EventWriteTransfer(
      v33,
      (unsigned int)&CacheIntegrity_UnexpectedCacheEntries,
      (unsigned int)"CacheAppUriHandler",
      v26,
      *(__int64 *)v43);
  *v56 = v12;
  StateRepository::TextA::Reset((StateRepository::TextA *)v43);
  return 0;
}

```

## disassembly

```asm
0x1800c8820  mov     [rsp-8+arg_8], rbx
0x1800c8825  mov     [rsp-8+arg_18], r9
0x1800c882a  push    rbp
0x1800c882b  push    rsi
0x1800c882c  push    rdi
0x1800c882d  push    r12
0x1800c882f  push    r13
0x1800c8831  push    r14
0x1800c8833  push    r15
0x1800c8835  lea     rbp, [rsp-40h]
0x1800c883a  sub     rsp, 140h
0x1800c8841  xor     r15d, r15d
0x1800c8844  mov     r13, rdx
0x1800c8847  mov     r12, rcx
0x1800c884a  cmp     [rcx], r15
0x1800c884d  jz      loc_1800C8CFF
0x1800c8853  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x1800c8858  test    al, al
0x1800c885a  jz      short loc_1800C886B
0x1800c885c  mov     ebx, 8067000Bh
0x1800c8861  mov     edx, 318h
0x1800c8866  jmp     loc_1800C8D09
0x1800c886b  cmp     [r13+0], r15
0x1800c886f  jz      loc_1800C8CF8
0x1800c8875  lea     rdx, [rsp+170h+var_128]; struct StateRepository::Statement *
0x1800c887a  mov     qword ptr [rsp+170h+var_120], r15
0x1800c887f  mov     rcx, r12; struct StateRepository::Database *
0x1800c8882  mov     [rsp+170h+var_118], r15
0x1800c8887  mov     [rsp+170h+var_128], r15
0x1800c888c  call    ?Find@CacheAppUriHandler@Entity@StateRepository@@SAJAEAVDatabase@3@AEAVStatement@3@@Z; StateRepository::Entity::CacheAppUriHandler::Find(StateRepository::Database &,StateRepository::Statement &)
0x1800c8891  mov     ebx, eax
0x1800c8893  test    eax, eax
0x1800c8895  jns     short loc_1800C88B4
0x1800c8897  mov     rcx, [rbp+78h]; this
0x1800c889b  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c88a2  mov     r9d, eax; char *
0x1800c88a5  mov     edx, 324h; void *
0x1800c88aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c88af  jmp     loc_1800C8A4C
0x1800c88b4  xorps   xmm0, xmm0
0x1800c88b7  mov     [rbp+70h+var_D0], r15
0x1800c88bb  xorps   xmm1, xmm1
0x1800c88be  movdqa  xmmword ptr [rsp+170h+var_110], xmm0
0x1800c88c4  lea     r8, [rbp+70h+arg_0]; bool *
0x1800c88cb  movdqa  [rsp+170h+var_100], xmm1
0x1800c88d1  lea     rdx, [rsp+170h+var_110]; struct StateRepository::Entity::CacheAppUriHandler *
0x1800c88d6  movdqa  [rbp+70h+var_F0], xmm0
0x1800c88db  lea     rcx, [rsp+170h+var_128]; this
0x1800c88e0  movdqa  [rbp+70h+var_E0], xmm1
0x1800c88e5  mov     [rbp+70h+arg_0], r15b
0x1800c88ec  call    ?FindNext@CacheAppUriHandler@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppUriHandler::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppUriHandler &,bool &)
0x1800c88f1  mov     ebx, eax
0x1800c88f3  test    eax, eax
0x1800c88f5  jns     short loc_1800C891E
0x1800c88f7  mov     rcx, [rbp+78h]; this
0x1800c88fb  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8902  mov     r9d, eax; char *
0x1800c8905  mov     edx, 327h; void *
0x1800c890a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c890f  lea     rcx, [rsp+170h+var_110]; this
0x1800c8914  call    ??1CacheAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler(void)
0x1800c8919  jmp     loc_1800C8A4C
0x1800c891e  mov     rbx, r15
0x1800c8921  mov     rdi, r15
0x1800c8924  mov     r14, r15
0x1800c8927  cmp     [rbp+70h+arg_0], r15b
0x1800c892e  jz      loc_1800C8A5B
0x1800c8934  mov     rdx, [rsp+170h+var_110]
0x1800c8939  lea     rax, [rbp+70h+arg_0]
0x1800c8940  xorps   xmm0, xmm0
0x1800c8943  mov     [rsp+170h+var_150], rax; int
0x1800c8948  xorps   xmm1, xmm1
0x1800c894b  lea     r9, [rbp+70h+var_B8]
0x1800c894f  mov     rcx, r13
0x1800c8952  movdqu  [rbp+70h+var_B8], xmm0
0x1800c8957  movdqu  [rbp+70h+var_A8], xmm1
0x1800c895c  movdqu  [rbp+70h+var_98], xmm0
0x1800c8961  call    ?Get@AppUriHandler_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandler_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,bool &)
0x1800c8966  mov     esi, eax
0x1800c8968  test    eax, eax
0x1800c896a  js      loc_1800C8A1F
0x1800c8970  cmp     [rbp+70h+arg_0], r15b
0x1800c8977  jz      short loc_1800C89BE
0x1800c8979  lea     r8, [rbp+70h+var_C0]; unsigned __int64 *
0x1800c897d  mov     [rbp+70h+var_C0], r15
0x1800c8981  lea     rdx, [rbp+70h+var_B8]; struct StateRepository::Cache::Entity::AppUriHandler_NoThrow *
0x1800c8985  lea     rcx, [rsp+170h+var_110]; struct StateRepository::Entity::CacheAppUriHandler *
0x1800c898a  call    ?Cache_Check@CacheAppUriHandler@Entity@StateRepository@@CAJAEBV123@AEBVAppUriHandler_NoThrow@2Cache@3@AEA_K@Z; StateRepository::Entity::CacheAppUriHandler::Cache_Check(StateRepository::Entity::CacheAppUriHandler const &,StateRepository::Cache::Entity::AppUriHandler_NoThrow const &,unsigned __int64 &)
0x1800c898f  mov     esi, eax
0x1800c8991  test    eax, eax
0x1800c8993  js      short loc_1800C8A0A
0x1800c8995  mov     r15, [rbp+70h+var_C0]
0x1800c8999  test    r15, r15
0x1800c899c  jz      short loc_1800C89B6
0x1800c899e  mov     rdx, [rsp+170h+var_110]; __int64
0x1800c89a3  lea     rcx, [rsp+170h+var_120]; this
0x1800c89a8  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800c89ad  mov     esi, eax
0x1800c89af  test    eax, eax
0x1800c89b1  js      short loc_1800C8A03
0x1800c89b3  add     rbx, r15
0x1800c89b6  inc     r14
0x1800c89b9  xor     r15d, r15d
0x1800c89bc  jmp     short loc_1800C89D6
0x1800c89be  mov     rdx, [rsp+170h+var_110]; __int64
0x1800c89c3  lea     rcx, [rsp+170h+var_120]; this
0x1800c89c8  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800c89cd  mov     esi, eax
0x1800c89cf  test    eax, eax
0x1800c89d1  js      short loc_1800C8A18
0x1800c89d3  inc     rbx
0x1800c89d6  lea     r8, [rbp+70h+arg_0]; bool *
0x1800c89dd  lea     rdx, [rsp+170h+var_110]; struct StateRepository::Entity::CacheAppUriHandler *
0x1800c89e2  lea     rcx, [rsp+170h+var_128]; this
0x1800c89e7  call    ?FindNext@CacheAppUriHandler@Entity@StateRepository@@SAJAEAVStatement@3@AEAV123@AEA_N@Z; StateRepository::Entity::CacheAppUriHandler::FindNext(StateRepository::Statement &,StateRepository::Entity::CacheAppUriHandler &,bool &)
0x1800c89ec  mov     esi, eax
0x1800c89ee  test    eax, eax
0x1800c89f0  js      short loc_1800C8A11
0x1800c89f2  inc     rdi
0x1800c89f5  lea     rcx, [rbp+70h+var_B8]; this
0x1800c89f9  call    ??1AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow(void)
0x1800c89fe  jmp     loc_1800C8927
0x1800c8a03  mov     edx, 335h
0x1800c8a08  jmp     short loc_1800C8A24
0x1800c8a0a  mov     edx, 331h
0x1800c8a0f  jmp     short loc_1800C8A24
0x1800c8a11  mov     edx, 33Dh
0x1800c8a16  jmp     short loc_1800C8A24
0x1800c8a18  mov     edx, 33Bh
0x1800c8a1d  jmp     short loc_1800C8A24
0x1800c8a1f  mov     edx, 32Ch; void *
0x1800c8a24  mov     rcx, [rbp+78h]; this
0x1800c8a28  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8a2f  mov     r9d, esi; char *
0x1800c8a32  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8a37  lea     rcx, [rbp+70h+var_B8]; this
0x1800c8a3b  call    ??1AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow(void)
0x1800c8a40  lea     rcx, [rsp+170h+var_110]; this
0x1800c8a45  call    ??1CacheAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler(void)
0x1800c8a4a  mov     ebx, esi
0x1800c8a4c  lea     rcx, [rsp+170h+var_128]; this
0x1800c8a51  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800c8a56  jmp     loc_1800C8C84
0x1800c8a5b  sub     rdi, r14
0x1800c8a5e  jz      short loc_1800C8A89
0x1800c8a60  test    cs:byte_1804DF881, 20h
0x1800c8a67  jz      short loc_1800C8A89
0x1800c8a69  mov     rax, qword ptr [rsp+170h+var_120]
0x1800c8a6e  lea     r8, aCacheappurihan; "CacheAppUriHandler"
0x1800c8a75  mov     r9, rdi
0x1800c8a78  mov     [rsp+170h+var_150], rax; int
0x1800c8a7d  lea     rdx, CacheIntegrity_MissingCacheEntries
0x1800c8a84  call    McTemplateU0sxs_EventWriteTransfer
0x1800c8a89  lea     rcx, [rsp+170h+var_110]; this
0x1800c8a8e  call    ??1CacheAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler(void)
0x1800c8a93  lea     rcx, [rsp+170h+var_128]; this
0x1800c8a98  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x1800c8a9d  lea     rcx, [rsp+170h+var_120]; this
0x1800c8aa2  call    ?Clear@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Clear(void)
0x1800c8aa7  mov     rdx, r13; struct StateRepository::Cache::Manager_NoThrow *
0x1800c8aaa  mov     [rsp+170h+var_140], r15
0x1800c8aaf  lea     rcx, [rsp+170h+var_140]; this
0x1800c8ab4  mov     [rsp+170h+var_138], r15d
0x1800c8ab9  mov     [rsp+170h+var_130], r15
0x1800c8abe  call    ?Open@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJAEAVManager_NoThrow@34@@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &)
0x1800c8ac3  mov     edi, eax
0x1800c8ac5  test    eax, eax
0x1800c8ac7  jns     short loc_1800C8B15
0x1800c8ac9  mov     rcx, [rbp+78h]; this
0x1800c8acd  lea     r8, aOnecoreBaseApp_336; "onecore\\base\\appmodel\\StateRepositor"...
0x1800c8ad4  mov     r9d, eax; char *
0x1800c8ad7  mov     edx, 3BDh; void *
0x1800c8adc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8ae1  mov     rcx, [rbp+78h]; this
0x1800c8ae5  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8aec  mov     r9d, edi; char *
0x1800c8aef  mov     edx, 34Eh; void *
0x1800c8af4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8af9  mov     rcx, [rsp+170h+var_140]
0x1800c8afe  mov     [rsp+170h+var_140], r15
0x1800c8b03  test    rcx, rcx
0x1800c8b06  jz      short loc_1800C8B0E
0x1800c8b08  call    cs:__imp_SRCacheContext_Close
0x1800c8b0e  mov     ebx, edi
0x1800c8b10  jmp     loc_1800C8C84
0x1800c8b15  xorps   xmm0, xmm0
0x1800c8b18  mov     [rbp+70h+arg_0], r15b
0x1800c8b1f  xorps   xmm1, xmm1
0x1800c8b22  lea     r9, [rbp+70h+arg_0]
0x1800c8b29  lea     r8, [rsp+170h+var_110]
0x1800c8b2e  lea     rcx, [rsp+170h+var_140]
0x1800c8b33  movdqu  xmmword ptr [rsp+170h+var_110], xmm0
0x1800c8b39  movdqu  [rsp+170h+var_100], xmm1
0x1800c8b3f  movdqu  [rbp+70h+var_F0], xmm0
0x1800c8b44  call    ?Get@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,bool &)
0x1800c8b49  mov     edi, eax
0x1800c8b4b  test    eax, eax
0x1800c8b4d  jns     short loc_1800C8B73
0x1800c8b4f  mov     rcx, [rbp+78h]; this
0x1800c8b53  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8b5a  mov     r9d, eax; char *
0x1800c8b5d  mov     edx, 351h; void *
0x1800c8b62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8b67  lea     rcx, [rsp+170h+var_110]; this
0x1800c8b6c  call    ??1AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow(void)
0x1800c8b71  jmp     short loc_1800C8AF9
0x1800c8b73  mov     rdi, r15
0x1800c8b76  cmp     [rbp+70h+arg_0], r15b
0x1800c8b7d  jz      loc_1800C8C93
0x1800c8b83  mov     r9, [rsp+170h+var_110]; char *
0x1800c8b88  lea     rax, [rbp+70h+arg_0]
0x1800c8b8f  xorps   xmm0, xmm0
0x1800c8b92  mov     [rsp+170h+var_150], rax; int
0x1800c8b97  xorps   xmm1, xmm1
0x1800c8b9a  movdqa  [rbp+70h+var_80], xmm0
0x1800c8b9f  xor     r8d, r8d; char *
0x1800c8ba2  movdqa  [rbp+70h+var_70], xmm1
0x1800c8ba7  lea     rdx, aSelectExistsSe_748; "SELECT EXISTS(SELECT 1 FROM CacheAppUri"...
0x1800c8bae  movdqa  [rbp+70h+var_60], xmm0
0x1800c8bb3  mov     rcx, r12; this
0x1800c8bb6  movdqa  [rbp+70h+var_50], xmm1
0x1800c8bbb  mov     [rbp+70h+var_40], r15
0x1800c8bbf  call    ?PrepareAndBindAndExists@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_JAEA_N@Z; StateRepository::StatementExecution::PrepareAndBindAndExists(StateRepository::Database &,char const *,char const *,__int64,bool &)
0x1800c8bc4  mov     esi, eax
0x1800c8bc6  test    eax, eax
0x1800c8bc8  js      short loc_1800C8C2A
0x1800c8bca  cmp     [rbp+70h+arg_0], r15b
0x1800c8bd1  jnz     short loc_1800C8BEE
0x1800c8bd3  mov     rdx, [rsp+170h+var_110]; __int64
0x1800c8bd8  lea     rcx, [rsp+170h+var_120]; this
0x1800c8bdd  call    ?AppendDelimited@TextA@StateRepository@@QEAAJ_JD@Z; StateRepository::TextA::AppendDelimited(__int64,char)
0x1800c8be2  mov     esi, eax
0x1800c8be4  test    eax, eax
0x1800c8be6  js      short loc_1800C8C1C
0x1800c8be8  inc     rdi
0x1800c8beb  inc     rbx
0x1800c8bee  inc     [rsp+170h+var_138]
0x1800c8bf2  lea     r9, [rbp+70h+arg_0]
0x1800c8bf9  lea     r8, [rsp+170h+var_110]
0x1800c8bfe  lea     rcx, [rsp+170h+var_140]
0x1800c8c03  call    ?Get@AppUriHandlerIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@AppUriHandler_NoThrow@234@AEAV6234@AEA_N@Z; StateRepository::Cache::Entity::AppUriHandlerIterator_NoThrow::Get(StateRepository::Cache::Entity::AppUriHandler_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppUriHandler_NoThrow &,bool &)
0x1800c8c08  mov     esi, eax
0x1800c8c0a  test    eax, eax
0x1800c8c0c  js      short loc_1800C8C23
0x1800c8c0e  lea     rcx, [rbp+70h+var_80]; this
0x1800c8c12  call    ??1CacheAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler(void)
0x1800c8c17  jmp     loc_1800C8B76
0x1800c8c1c  mov     edx, 35Ah
0x1800c8c21  jmp     short loc_1800C8C47
0x1800c8c23  mov     edx, 35Ch
0x1800c8c28  jmp     short loc_1800C8C47
0x1800c8c2a  mov     rcx, [rbp+78h]; this
0x1800c8c2e  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8c35  mov     r9d, esi; char *
0x1800c8c38  mov     edx, 80h; void *
0x1800c8c3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8c42  mov     edx, 355h; void *
0x1800c8c47  mov     rcx, [rbp+78h]; this
0x1800c8c4b  lea     r8, aOnecoreBaseApp_487; "onecore\\base\\appmodel\\staterepositor"...
0x1800c8c52  mov     r9d, esi; char *
0x1800c8c55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8c5a  lea     rcx, [rbp+70h+var_80]; this
0x1800c8c5e  call    ??1CacheAppUriHandler@Entity@StateRepository@@QEAA@XZ; StateRepository::Entity::CacheAppUriHandler::~CacheAppUriHandler(void)
0x1800c8c63  lea     rcx, [rsp+170h+var_110]; this
0x1800c8c68  call    ??1AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow(void)
0x1800c8c6d  mov     rcx, [rsp+170h+var_140]
0x1800c8c72  mov     [rsp+170h+var_140], r15
0x1800c8c77  test    rcx, rcx
0x1800c8c7a  jz      short loc_1800C8C82
0x1800c8c7c  call    cs:__imp_SRCacheContext_Close
0x1800c8c82  mov     ebx, esi
0x1800c8c84  lea     rcx, [rsp+170h+var_120]; this
0x1800c8c89  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800c8c8e  jmp     loc_1800C8D1C
0x1800c8c93  lea     rcx, [rsp+170h+var_110]; this
0x1800c8c98  call    ??1AppUriHandler_NoThrow@Entity@Cache@StateRepository@@QEAA@XZ; StateRepository::Cache::Entity::AppUriHandler_NoThrow::~AppUriHandler_NoThrow(void)
0x1800c8c9d  mov     rcx, [rsp+170h+var_140]
0x1800c8ca2  mov     [rsp+170h+var_140], r15
0x1800c8ca7  test    rcx, rcx
0x1800c8caa  jz      short loc_1800C8CB2
0x1800c8cac  call    cs:__imp_SRCacheContext_Close
0x1800c8cb2  test    rdi, rdi
0x1800c8cb5  jz      short loc_1800C8CE0
0x1800c8cb7  test    cs:byte_1804DF881, 20h
0x1800c8cbe  jz      short loc_1800C8CE0
0x1800c8cc0  mov     rax, qword ptr [rsp+170h+var_120]
0x1800c8cc5  lea     r8, aCacheappurihan; "CacheAppUriHandler"
0x1800c8ccc  mov     r9, rdi
0x1800c8ccf  mov     [rsp+170h+var_150], rax
0x1800c8cd4  lea     rdx, CacheIntegrity_UnexpectedCacheEntries
0x1800c8cdb  call    McTemplateU0sxs_EventWriteTransfer
0x1800c8ce0  mov     rax, [rbp+70h+arg_18]
0x1800c8ce7  lea     rcx, [rsp+170h+var_120]; this
0x1800c8cec  mov     [rax], rbx
0x1800c8cef  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x1800c8cf4  xor     eax, eax
0x1800c8cf6  jmp     short loc_1800C8D1E
0x1800c8cf8  mov     edx, 319h
0x1800c8cfd  jmp     short loc_1800C8D04
0x1800c8cff  mov     edx, 317h; void *
  ... truncated ...
```
