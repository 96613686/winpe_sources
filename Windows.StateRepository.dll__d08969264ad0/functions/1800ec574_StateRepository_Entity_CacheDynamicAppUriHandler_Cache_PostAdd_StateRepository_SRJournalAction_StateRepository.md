# StateRepository::Entity::CacheDynamicAppUriHandler::Cache_PostAdd(StateRepository::SRJournalAction,StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Context_NoThrow &,StateRepository::ExecutionFlags)

- ea: `0x1800ec574`
- end: `0x1800ec8e7`
- name: `?Cache_PostAdd@CacheDynamicAppUriHandler@Entity@StateRepository@@QEAAJW4SRJournalAction@3@AEAVDatabase@3@AEAVManager_NoThrow@Cache@3@AEAVContext_NoThrow@73@3W4ExecutionFlags@3@@Z`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180160b98`

## callees

- `0x18001a9e0`
- `0x180045878`
- `0x1800472dc`
- `0x1800485e0`
- `0x18004af98`
- `0x180072ee0`
- `0x180072f84`
- `0x180074eb0`
- `0x180086660`
- `0x18008bec0`
- `0x1800ec574`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec7d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec837`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec888`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec7d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec837`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ec888`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec681`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec703`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec84c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec86f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec8ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec8c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec681`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec703`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec84c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec85a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec86f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec89d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec8ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ec8c0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_CreateSubContext` at `0x1800ec771`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_CreateSubContext` at `0x1800ec771`

## string_xrefs

- `0x1800ec78e`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800ec605`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler-custom.cpp`
- `0x1800ec663`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler-custom.cpp`
- `0x1800ec6e1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler-custom.cpp`
- `0x1800ec7ae`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler-custom.cpp`
- `0x1800ec814`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cachedynamicappurihandler-custom.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheDynamicAppUriHandler::Cache_PostAdd(
        __int64 *a1,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4,
        StateRepository::Cache::Context_NoThrow *a5,
        __int64 *a6)
{
  _WORD *v6; // rax
  int Field_MultiString; // ebx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // r8
  __int64 v18; // rcx
  const unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // rbx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // r8
  unsigned int v24; // edi
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // rcx
  __int64 v28; // rcx
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rcx
  int v33[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v34; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v35[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v36[2]; // [rsp+40h] [rbp-C0h]
  __int64 v37; // [rsp+48h] [rbp-B8h]
  int *v38; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 *v39; // [rsp+58h] [rbp-A8h] BYREF
  char v40; // [rsp+60h] [rbp-A0h]
  __int64 v41; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v42[512]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v43; // [rsp+278h] [rbp+178h]
  __int64 v44; // [rsp+280h] [rbp+180h]
  unsigned __int16 *v45; // [rsp+288h] [rbp+188h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = (_WORD *)a1[2];
  if ( !v6 || *v6 != 42 )
    return 0;
  *(_QWORD *)v33 = 0;
  v38 = v33;
  v39 = 0;
  v40 = 1;
  Field_MultiString = StateRepository::Cache::Context_NoThrow::GetField_MultiString(a5, a2, &v39);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void (*)(void *),&void SRCache_Free(void *)>>>(&v38);
  if ( Field_MultiString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v33[0]);
LABEL_5:
    v9 = *(_QWORD *)v33;
    *(_QWORD *)v33 = 0;
    if ( v9 )
      SRCache_Free(v9);
    return (unsigned int)Field_MultiString;
  }
  *(_QWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)v35 = 0;
  v11 = StateRepository::Cache::MultiKey_NoThrow::Attach(v35, (__int64 *)v33);
  Field_MultiString = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler-custom.cpp",
      (const char *)(unsigned int)v11,
      v33[0]);
LABEL_10:
    if ( v35[0] )
      SRCache_Free(v35[0]);
    goto LABEL_5;
  }
  v41 = 0;
  memset_0(v42, 0, sizeof(v42));
  v43 = 0;
  v45 = (unsigned __int16 *)v42;
  v44 = 256;
  Field_MultiString = StateRepository::Cache::Key_NoThrow::Append(
                        (StateRepository::Cache::Key_NoThrow *)&v41,
                        L"*HostName\\*\\");
  if ( Field_MultiString < 0 )
  {
    v12 = 46;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v33[0]);
LABEL_15:
    v13 = v41;
    v41 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_10;
  }
  Field_MultiString = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v41, *a1);
  if ( Field_MultiString < 0 )
  {
    v12 = 47;
    goto LABEL_14;
  }
  Field_MultiString = StateRepository::Cache::MultiKey_NoThrow::Append(
                        (StateRepository::Cache::MultiKey_NoThrow *)v35,
                        v45);
  if ( Field_MultiString < 0 )
  {
    v12 = 48;
    goto LABEL_14;
  }
  v14 = *a6;
  v38 = (int *)&v34;
  v34 = 0;
  v39 = 0;
  v40 = 1;
  Field_MultiString = SRCacheContext_CreateSubContext(v14, v45, 0, &v39);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v38);
  if ( Field_MultiString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_MultiString,
      v33[0]);
    v15 = 50;
    goto LABEL_23;
  }
  Field_MultiString = StateRepository::Cache::MultiKey_NoThrow::End((StateRepository::Cache::MultiKey_NoThrow *)v35);
  if ( Field_MultiString < 0 )
  {
    v15 = 52;
LABEL_23:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v33[0]);
    v18 = v34;
    v34 = 0;
    if ( v18 )
      SRCacheContext_Close(v18, v16, v17);
    goto LABEL_15;
  }
  v20 = v35[0];
  v21 = StateRepository::Cache::Context_NoThrow::SetField_MultiString(a5, v19, v35[0]);
  v24 = v21;
  if ( v21 >= 0 )
  {
    v30 = v34;
    v34 = 0;
    if ( v30 )
      SRCacheContext_Close(v30, v22, v23);
    v31 = v41;
    v41 = 0;
    if ( v31 )
      SRCache_Free(v31);
    if ( v20 )
      SRCache_Free(v20);
    v32 = *(_QWORD *)v33;
    *(_QWORD *)v33 = 0;
    if ( v32 )
      SRCache_Free(v32);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cachedynamicappurihandler-custom.cpp",
    (const char *)(unsigned int)v21,
    v33[0]);
  v27 = v34;
  v34 = 0;
  if ( v27 )
    SRCacheContext_Close(v27, v25, v26);
  v28 = v41;
  v41 = 0;
  if ( v28 )
    SRCache_Free(v28);
  if ( v20 )
    SRCache_Free(v20);
  v29 = *(_QWORD *)v33;
  *(_QWORD *)v33 = 0;
  if ( v29 )
    SRCache_Free(v29);
  return v24;
}

```

## disassembly

```asm
0x1800ec574  push    rbp
0x1800ec576  push    rbx
0x1800ec577  push    rsi
0x1800ec578  push    rdi
0x1800ec579  push    r14
0x1800ec57b  push    r15
0x1800ec57d  lea     rbp, [rsp-1A8h]
0x1800ec585  sub     rsp, 2A8h
0x1800ec58c  mov     rax, cs:__security_cookie
0x1800ec593  xor     rax, rsp
0x1800ec596  mov     [rbp+1D0h+var_40], rax
0x1800ec59d  mov     rax, [rcx+10h]
0x1800ec5a1  xor     r15d, r15d
0x1800ec5a4  mov     rsi, [rbp+1D0h+arg_20]
0x1800ec5ab  mov     rdi, rcx
0x1800ec5ae  mov     r14, [rbp+1D0h+arg_28]
0x1800ec5b5  test    rax, rax
0x1800ec5b8  jz      loc_1800EC8C6
0x1800ec5be  cmp     word ptr [rax], 2Ah ; '*'
0x1800ec5c2  jnz     loc_1800EC8C6
0x1800ec5c8  lea     rax, [rsp+2D0h+var_2B0]
0x1800ec5cd  mov     qword ptr [rsp+2D0h+var_2B0], r15; int
0x1800ec5d2  lea     r8, [rsp+2D0h+var_278]; unsigned __int16 **
0x1800ec5d7  mov     [rsp+2D0h+var_280], rax
0x1800ec5dc  mov     rcx, rsi; this
0x1800ec5df  mov     [rsp+2D0h+var_278], r15
0x1800ec5e4  mov     [rsp+2D0h+var_270], 1
0x1800ec5e9  call    ?GetField_MultiString@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField_MultiString(ushort const *,ushort * *)
0x1800ec5ee  lea     rcx, [rsp+2D0h+var_280]
0x1800ec5f3  mov     ebx, eax
0x1800ec5f5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>>>(void)
0x1800ec5fa  test    ebx, ebx
0x1800ec5fc  jns     short loc_1800EC634
0x1800ec5fe  mov     rcx, [rbp+1D8h]; this
0x1800ec605  lea     r8, aOnecoreBaseApp_196; "onecore\\base\\appmodel\\staterepositor"...
0x1800ec60c  mov     r9d, ebx; char *
0x1800ec60f  lea     edx, [r15+29h]; void *
0x1800ec613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec618  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800ec61d  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x1800ec622  test    rcx, rcx
0x1800ec625  jz      short loc_1800EC62D
0x1800ec627  call    cs:__imp_SRCache_Free
0x1800ec62d  mov     eax, ebx
0x1800ec62f  jmp     loc_1800EC8C8
0x1800ec634  xorps   xmm0, xmm0
0x1800ec637  mov     qword ptr [rsp+2D0h+var_290], r15
0x1800ec63c  lea     rdx, [rsp+2D0h+var_2B0]
0x1800ec641  mov     [rsp+2D0h+var_288], r15
0x1800ec646  lea     rcx, [rsp+2D0h+var_2A0]
0x1800ec64b  movdqu  xmmword ptr [rsp+2D0h+var_2A0], xmm0
0x1800ec651  call    ?Attach@MultiKey_NoThrow@Cache@StateRepository@@QEAAJAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@Z; StateRepository::Cache::MultiKey_NoThrow::Attach(wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>> &)
0x1800ec656  mov     ebx, eax
0x1800ec658  test    eax, eax
0x1800ec65a  jns     short loc_1800EC689
0x1800ec65c  mov     rcx, [rbp+1D8h]; this
0x1800ec663  lea     r8, aOnecoreBaseApp_196; "onecore\\base\\appmodel\\staterepositor"...
0x1800ec66a  mov     r9d, eax; char *
0x1800ec66d  mov     edx, 2Bh ; '+'; void *
0x1800ec672  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec677  mov     rcx, [rsp+2D0h+var_2A0]
0x1800ec67c  test    rcx, rcx
0x1800ec67f  jz      short loc_1800EC618
0x1800ec681  call    cs:__imp_SRCache_Free
0x1800ec687  jmp     short loc_1800EC618
0x1800ec689  xor     edx, edx; Val
0x1800ec68b  mov     [rsp+2D0h+var_260], r15
0x1800ec690  mov     r8d, 200h; Size
0x1800ec696  lea     rcx, [rsp+2D0h+var_258]; void *
0x1800ec69b  call    memset_0
0x1800ec6a0  lea     rax, [rsp+2D0h+var_258]
0x1800ec6a5  mov     [rbp+1D0h+var_58], r15
0x1800ec6ac  lea     rdx, aHostname_0; "*HostName\\*\\"
0x1800ec6b3  mov     [rbp+1D0h+var_48], rax
0x1800ec6ba  lea     rcx, [rsp+2D0h+var_260]; this
0x1800ec6bf  mov     [rbp+1D0h+var_50], 100h
0x1800ec6ca  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800ec6cf  mov     ebx, eax
0x1800ec6d1  test    eax, eax
0x1800ec6d3  jns     short loc_1800EC70E
0x1800ec6d5  mov     edx, 2Eh ; '.'; void *
0x1800ec6da  mov     rcx, [rbp+1D8h]; this
0x1800ec6e1  lea     r8, aOnecoreBaseApp_196; "onecore\\base\\appmodel\\staterepositor"...
0x1800ec6e8  mov     r9d, ebx; char *
0x1800ec6eb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec6f0  mov     rcx, [rsp+2D0h+var_260]
0x1800ec6f5  mov     [rsp+2D0h+var_260], r15
0x1800ec6fa  test    rcx, rcx
0x1800ec6fd  jz      loc_1800EC677
0x1800ec703  call    cs:__imp_SRCache_Free
0x1800ec709  jmp     loc_1800EC677
0x1800ec70e  mov     rdx, [rdi]; unsigned __int64
0x1800ec711  lea     rcx, [rsp+2D0h+var_260]; this
0x1800ec716  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800ec71b  mov     ebx, eax
0x1800ec71d  test    eax, eax
0x1800ec71f  jns     short loc_1800EC728
0x1800ec721  mov     edx, 2Fh ; '/'
0x1800ec726  jmp     short loc_1800EC6DA
0x1800ec728  mov     rdx, [rbp+1D0h+var_48]; unsigned __int16 *
0x1800ec72f  lea     rcx, [rsp+2D0h+var_2A0]; this
0x1800ec734  call    ?Append@MultiKey_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::MultiKey_NoThrow::Append(ushort const *)
0x1800ec739  mov     ebx, eax
0x1800ec73b  test    eax, eax
0x1800ec73d  jns     short loc_1800EC746
0x1800ec73f  mov     edx, 30h ; '0'
0x1800ec744  jmp     short loc_1800EC6DA
0x1800ec746  mov     rdx, [rbp+1D0h+var_48]
0x1800ec74d  lea     rax, [rsp+2D0h+var_2A8]
0x1800ec752  mov     rcx, [r14]
0x1800ec755  lea     r9, [rsp+2D0h+var_278]
0x1800ec75a  xor     r8d, r8d
0x1800ec75d  mov     [rsp+2D0h+var_280], rax
0x1800ec762  mov     [rsp+2D0h+var_2A8], r15
0x1800ec767  mov     [rsp+2D0h+var_278], r15
0x1800ec76c  mov     [rsp+2D0h+var_270], 1
0x1800ec771  call    cs:__imp_SRCacheContext_CreateSubContext
0x1800ec777  lea     rcx, [rsp+2D0h+var_280]
0x1800ec77c  mov     ebx, eax
0x1800ec77e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ec783  test    ebx, ebx
0x1800ec785  jns     short loc_1800EC7DB
0x1800ec787  mov     rcx, [rbp+1D8h]; this
0x1800ec78e  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ec795  mov     r9d, ebx; char *
0x1800ec798  mov     edx, 1E6h; void *
0x1800ec79d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec7a2  mov     edx, 32h ; '2'; void *
0x1800ec7a7  mov     rcx, [rbp+1D8h]; this
0x1800ec7ae  lea     r8, aOnecoreBaseApp_196; "onecore\\base\\appmodel\\staterepositor"...
0x1800ec7b5  mov     r9d, ebx; char *
0x1800ec7b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec7bd  mov     rcx, [rsp+2D0h+var_2A8]
0x1800ec7c2  mov     [rsp+2D0h+var_2A8], r15
0x1800ec7c7  test    rcx, rcx
0x1800ec7ca  jz      loc_1800EC6F0
0x1800ec7d0  call    cs:__imp_SRCacheContext_Close
0x1800ec7d6  jmp     loc_1800EC6F0
0x1800ec7db  lea     rcx, [rsp+2D0h+var_2A0]; this
0x1800ec7e0  call    ?End@MultiKey_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::MultiKey_NoThrow::End(void)
0x1800ec7e5  mov     ebx, eax
0x1800ec7e7  test    eax, eax
0x1800ec7e9  jns     short loc_1800EC7F2
0x1800ec7eb  mov     edx, 34h ; '4'
0x1800ec7f0  jmp     short loc_1800EC7A7
0x1800ec7f2  mov     rbx, [rsp+2D0h+var_2A0]
0x1800ec7f7  mov     rcx, rsi; this
0x1800ec7fa  mov     r9d, [rsp+2D0h+var_290]; unsigned int
0x1800ec7ff  mov     r8, rbx; unsigned __int16 *
0x1800ec802  call    ?SetField_MultiString@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG0I@Z; StateRepository::Cache::Context_NoThrow::SetField_MultiString(ushort const *,ushort const *,uint)
0x1800ec807  mov     edi, eax
0x1800ec809  test    eax, eax
0x1800ec80b  jns     short loc_1800EC879
0x1800ec80d  mov     rcx, [rbp+1D8h]; this
0x1800ec814  lea     r8, aOnecoreBaseApp_196; "onecore\\base\\appmodel\\staterepositor"...
0x1800ec81b  mov     r9d, eax; char *
0x1800ec81e  mov     edx, 35h ; '5'; void *
0x1800ec823  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ec828  mov     rcx, [rsp+2D0h+var_2A8]
0x1800ec82d  mov     [rsp+2D0h+var_2A8], r15
0x1800ec832  test    rcx, rcx
0x1800ec835  jz      short loc_1800EC83D
0x1800ec837  call    cs:__imp_SRCacheContext_Close
0x1800ec83d  mov     rcx, [rsp+2D0h+var_260]
0x1800ec842  mov     [rsp+2D0h+var_260], r15
0x1800ec847  test    rcx, rcx
0x1800ec84a  jz      short loc_1800EC852
0x1800ec84c  call    cs:__imp_SRCache_Free
0x1800ec852  test    rbx, rbx
0x1800ec855  jz      short loc_1800EC860
0x1800ec857  mov     rcx, rbx
0x1800ec85a  call    cs:__imp_SRCache_Free
0x1800ec860  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800ec865  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x1800ec86a  test    rcx, rcx
0x1800ec86d  jz      short loc_1800EC875
0x1800ec86f  call    cs:__imp_SRCache_Free
0x1800ec875  mov     eax, edi
0x1800ec877  jmp     short loc_1800EC8C8
0x1800ec879  mov     rcx, [rsp+2D0h+var_2A8]
0x1800ec87e  mov     [rsp+2D0h+var_2A8], r15
0x1800ec883  test    rcx, rcx
0x1800ec886  jz      short loc_1800EC88E
0x1800ec888  call    cs:__imp_SRCacheContext_Close
0x1800ec88e  mov     rcx, [rsp+2D0h+var_260]
0x1800ec893  mov     [rsp+2D0h+var_260], r15
0x1800ec898  test    rcx, rcx
0x1800ec89b  jz      short loc_1800EC8A3
0x1800ec89d  call    cs:__imp_SRCache_Free
0x1800ec8a3  test    rbx, rbx
0x1800ec8a6  jz      short loc_1800EC8B1
0x1800ec8a8  mov     rcx, rbx
0x1800ec8ab  call    cs:__imp_SRCache_Free
0x1800ec8b1  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800ec8b6  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x1800ec8bb  test    rcx, rcx
0x1800ec8be  jz      short loc_1800EC8C6
0x1800ec8c0  call    cs:__imp_SRCache_Free
0x1800ec8c6  xor     eax, eax
0x1800ec8c8  mov     rcx, [rbp+1D0h+var_40]
0x1800ec8cf  xor     rcx, rsp; StackCookie
0x1800ec8d2  call    __security_check_cookie
0x1800ec8d7  add     rsp, 2A8h
0x1800ec8de  pop     r15
0x1800ec8e0  pop     r14
0x1800ec8e2  pop     rdi
0x1800ec8e3  pop     rsi
0x1800ec8e4  pop     rbx
0x1800ec8e5  pop     rbp
0x1800ec8e6  retn
```
