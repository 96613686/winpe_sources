# StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1801132cc`
- end: `0x180113509`
- name: `?Open@DynamicAppUriHandlerGroup_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18026b354`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1801132cc`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180113453`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180113453`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18011338a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801134db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18011338a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801134db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180113425`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801134c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180113425`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801134c6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18011332f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18011332f`

## string_xrefs

- `0x18011334c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180113470`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18011331b`: `DynamicAppUriHandlerGroup\Data`
- `0x180113491`: `DynamicAppUriHandlerGroup\Data`
- `0x18011336c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`
- `0x180113403`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-DynamicAppUriHandlerGroup.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::DynamicAppUriHandlerGroup_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v21; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v21 = v20;
  v23 = 1;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v8 = SRCacheContext_Open(v4, L"DynamicAppUriHandlerGroup\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 261;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
LABEL_4:
    v12 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v12 )
      SRCacheContext_Close(v12, v10, v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v9 = 262;
    goto LABEL_3;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v14 = 265;
    goto LABEL_11;
  }
  v21 = (int *)a3;
  v22 = 0;
  v23 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v14 = 266;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"DynamicAppUriHandlerGroup\\Data");
  if ( v8 < 0 )
  {
    v14 = 268;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-DynamicAppUriHandlerGroup.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v15 = v24;
    v24 = 0;
    if ( v15 )
      SRCache_Free(v15);
    goto LABEL_4;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19, v16, v17);
  return 0;
}

```

## disassembly

```asm
0x1801132cc  mov     [rsp-8+arg_10], rbx
0x1801132d1  push    rbp
0x1801132d2  push    rsi
0x1801132d3  push    rdi
0x1801132d4  push    r14
0x1801132d6  push    r15
0x1801132d8  lea     rbp, [rsp-170h]
0x1801132e0  sub     rsp, 270h
0x1801132e7  mov     rax, cs:__security_cookie
0x1801132ee  xor     rax, rsp
0x1801132f1  mov     [rbp+190h+var_30], rax
0x1801132f8  mov     rcx, [rcx]
0x1801132fb  lea     rax, [rsp+290h+var_270]
0x180113300  mov     rsi, r9
0x180113303  mov     [rsp+290h+var_268], rax
0x180113308  mov     rdi, r8
0x18011330b  mov     [rsp+290h+var_258], 1
0x180113310  mov     r14, rdx
0x180113313  lea     r9, [rsp+290h+var_260]
0x180113318  xor     r15d, r15d
0x18011331b  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandlerGroup\\Data"
0x180113322  xor     r8d, r8d
0x180113325  mov     qword ptr [rsp+290h+var_270], r15; int
0x18011332a  mov     [rsp+290h+var_260], r15
0x18011332f  call    cs:__imp_SRCacheContext_Open
0x180113335  lea     rcx, [rsp+290h+var_268]
0x18011333a  mov     ebx, eax
0x18011333c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180113341  test    ebx, ebx
0x180113343  jns     short loc_180113397
0x180113345  mov     rcx, [rbp+198h]; this
0x18011334c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180113353  mov     r9d, ebx; char *
0x180113356  mov     edx, 18Ch; void *
0x18011335b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113360  mov     edx, 105h; void *
0x180113365  mov     rcx, [rbp+198h]; this
0x18011336c  lea     r8, aOnecoreBaseApp_133; "onecore\\base\\appmodel\\StateRepositor"...
0x180113373  mov     r9d, ebx; char *
0x180113376  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18011337b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180113380  mov     qword ptr [rsp+290h+var_270], r15
0x180113385  test    rcx, rcx
0x180113388  jz      short loc_180113390
0x18011338a  call    cs:__imp_SRCacheContext_Close
0x180113390  mov     eax, ebx
0x180113392  jmp     loc_1801134E3
0x180113397  cmp     qword ptr [rsp+290h+var_270], r15
0x18011339c  setnz   al
0x18011339f  test    al, al
0x1801133a1  jnz     short loc_1801133AF
0x1801133a3  mov     ebx, 80670012h
0x1801133a8  mov     edx, 106h
0x1801133ad  jmp     short loc_180113365
0x1801133af  xor     edx, edx; Val
0x1801133b1  mov     [rsp+290h+var_250], r15
0x1801133b6  mov     r8d, 200h; Size
0x1801133bc  lea     rcx, [rsp+290h+var_248]; void *
0x1801133c1  call    memset_0
0x1801133c6  lea     rax, [rsp+290h+var_248]
0x1801133cb  mov     [rbp+190h+var_48], r15
0x1801133d2  mov     rdx, r14; unsigned __int64
0x1801133d5  mov     [rbp+190h+var_38], rax
0x1801133dc  lea     rcx, [rsp+290h+var_250]; this
0x1801133e1  mov     [rbp+190h+var_40], 100h
0x1801133ec  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801133f1  mov     ebx, eax
0x1801133f3  test    eax, eax
0x1801133f5  jns     short loc_180113430
0x1801133f7  mov     edx, 109h; void *
0x1801133fc  mov     rcx, [rbp+198h]; this
0x180113403  lea     r8, aOnecoreBaseApp_133; "onecore\\base\\appmodel\\StateRepositor"...
0x18011340a  mov     r9d, ebx; char *
0x18011340d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113412  mov     rcx, [rsp+290h+var_250]
0x180113417  mov     [rsp+290h+var_250], r15
0x18011341c  test    rcx, rcx
0x18011341f  jz      loc_18011337B
0x180113425  call    cs:__imp_SRCache_Free
0x18011342b  jmp     loc_18011337B
0x180113430  mov     rdx, [rbp+190h+var_38]
0x180113437  lea     r9, [rsp+290h+var_260]
0x18011343c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180113441  xor     r8d, r8d
0x180113444  mov     [rsp+290h+var_268], rdi
0x180113449  mov     [rsp+290h+var_260], r15
0x18011344e  mov     [rsp+290h+var_258], 1
0x180113453  call    cs:__imp_SRCacheContext_OpenSubContext
0x180113459  lea     rcx, [rsp+290h+var_268]
0x18011345e  mov     ebx, eax
0x180113460  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180113465  test    ebx, ebx
0x180113467  jns     short loc_18011348E
0x180113469  mov     rcx, [rbp+198h]; this
0x180113470  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180113477  mov     r9d, ebx; char *
0x18011347a  mov     edx, 1B0h; void *
0x18011347f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180113484  mov     edx, 10Ah
0x180113489  jmp     loc_1801133FC
0x18011348e  cmp     [rdi], r15
0x180113491  lea     rdx, aDynamicappurih_6; "DynamicAppUriHandlerGroup\\Data"
0x180113498  lea     rcx, [rsp+290h+var_270]; this
0x18011349d  setnz   al
0x1801134a0  mov     [rsi], al
0x1801134a2  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1801134a7  mov     ebx, eax
0x1801134a9  test    eax, eax
0x1801134ab  jns     short loc_1801134B7
0x1801134ad  mov     edx, 10Ch
0x1801134b2  jmp     loc_1801133FC
0x1801134b7  mov     rcx, [rsp+290h+var_250]
0x1801134bc  mov     [rsp+290h+var_250], r15
0x1801134c1  test    rcx, rcx
0x1801134c4  jz      short loc_1801134CC
0x1801134c6  call    cs:__imp_SRCache_Free
0x1801134cc  mov     rcx, qword ptr [rsp+290h+var_270]
0x1801134d1  mov     qword ptr [rsp+290h+var_270], r15
0x1801134d6  test    rcx, rcx
0x1801134d9  jz      short loc_1801134E1
0x1801134db  call    cs:__imp_SRCacheContext_Close
0x1801134e1  xor     eax, eax
0x1801134e3  mov     rcx, [rbp+190h+var_30]
0x1801134ea  xor     rcx, rsp; StackCookie
0x1801134ed  call    __security_check_cookie
0x1801134f2  mov     rbx, [rsp+290h+arg_10]
0x1801134fa  add     rsp, 270h
0x180113501  pop     r15
0x180113503  pop     r14
0x180113505  pop     rdi
0x180113506  pop     rsi
0x180113507  pop     rbp
0x180113508  retn
```
