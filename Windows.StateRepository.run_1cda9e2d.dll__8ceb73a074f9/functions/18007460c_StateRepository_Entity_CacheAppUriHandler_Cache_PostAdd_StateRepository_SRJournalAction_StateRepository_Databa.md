# StateRepository::Entity::CacheAppUriHandler::Cache_PostAdd(StateRepository::SRJournalAction,StateRepository::Database &,StateRepository::Cache::Manager_NoThrow &,StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Context_NoThrow &,StateRepository::ExecutionFlags)

- ea: `0x18007460c`
- end: `0x180074998`
- name: `?Cache_PostAdd@CacheAppUriHandler@Entity@StateRepository@@QEAAJW4SRJournalAction@3@AEAVDatabase@3@AEAVManager_NoThrow@Cache@3@AEAVContext_NoThrow@73@3W4ExecutionFlags@3@@Z`
- size: `908`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007325c`

## callees

- `0x18001a9e0`
- `0x180045878`
- `0x1800472dc`
- `0x1800485e0`
- `0x18004af98`
- `0x180072ee0`
- `0x180072f84`
- `0x18007460c`
- `0x180074eb0`
- `0x180086660`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074881`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800748e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074939`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074881`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800748e8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180074939`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800746a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800746d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074732`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800747b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800748fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007490b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074920`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007494e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007495c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074971`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800746a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800746d8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074732`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800747b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800748fd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007490b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074920`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007494e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18007495c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180074971`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_CreateSubContext` at `0x180074822`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_CreateSubContext` at `0x180074822`

## string_xrefs

- `0x18007483f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800746b5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler-custom.cpp`
- `0x180074714`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler-custom.cpp`
- `0x180074792`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler-custom.cpp`
- `0x18007485f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler-custom.cpp`
- `0x1800748c5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-cacheappurihandler-custom.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::CacheAppUriHandler::Cache_PostAdd(
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
  __int64 v10; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  const unsigned __int16 *v18; // rdx
  unsigned __int16 *v19; // rbx
  int v20; // eax
  unsigned int v21; // edi
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v29; // [rsp+28h] [rbp-D8h] BYREF
  int *v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v31; // [rsp+38h] [rbp-C8h] BYREF
  char v32; // [rsp+40h] [rbp-C0h]
  unsigned __int16 *v33[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v34[2]; // [rsp+58h] [rbp-A8h]
  __int64 v35; // [rsp+60h] [rbp-A0h]
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v37[512]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v38; // [rsp+278h] [rbp+178h]
  __int64 v39; // [rsp+280h] [rbp+180h]
  unsigned __int16 *v40; // [rsp+288h] [rbp+188h]
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v6 = (_WORD *)a1[1];
  if ( !v6 || *v6 != 42 )
    return 0;
  *(_QWORD *)v28 = 0;
  v30 = v28;
  v31 = 0;
  v32 = 1;
  Field_MultiString = StateRepository::Cache::Context_NoThrow::GetField_MultiString(a5, a2, &v31);
  if ( v32 )
  {
    v9 = *(_QWORD *)v30;
    *(_QWORD *)v30 = v31;
    if ( v9 )
      SRCache_Free(v9);
  }
  if ( Field_MultiString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v28[0]);
LABEL_8:
    v10 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v10 )
      SRCache_Free(v10);
    return (unsigned int)Field_MultiString;
  }
  *(_QWORD *)v34 = 0;
  v35 = 0;
  *(_OWORD *)v33 = 0;
  v12 = StateRepository::Cache::MultiKey_NoThrow::Attach(v33, v28);
  Field_MultiString = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler-custom.cpp",
      (const char *)(unsigned int)v12,
      v28[0]);
LABEL_13:
    if ( v33[0] )
      SRCache_Free(v33[0]);
    goto LABEL_8;
  }
  v36 = 0;
  memset_0(v37, 0, sizeof(v37));
  v38 = 0;
  v40 = (unsigned __int16 *)v37;
  v39 = 256;
  Field_MultiString = StateRepository::Cache::Key_NoThrow::Append(
                        (StateRepository::Cache::Key_NoThrow *)&v36,
                        L"*HostName\\*\\");
  if ( Field_MultiString < 0 )
  {
    v13 = 46;
LABEL_17:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v28[0]);
LABEL_18:
    v14 = v36;
    v36 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_13;
  }
  Field_MultiString = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v36, *a1);
  if ( Field_MultiString < 0 )
  {
    v13 = 47;
    goto LABEL_17;
  }
  Field_MultiString = StateRepository::Cache::MultiKey_NoThrow::Append(
                        (StateRepository::Cache::MultiKey_NoThrow *)v33,
                        v40);
  if ( Field_MultiString < 0 )
  {
    v13 = 48;
    goto LABEL_17;
  }
  v15 = *a6;
  v30 = (int *)&v29;
  v29 = 0;
  v31 = 0;
  v32 = 1;
  Field_MultiString = SRCacheContext_CreateSubContext(v15, v40, 0, &v31);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v30);
  if ( Field_MultiString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)Field_MultiString,
      v28[0]);
    v16 = 50;
    goto LABEL_26;
  }
  Field_MultiString = StateRepository::Cache::MultiKey_NoThrow::End((StateRepository::Cache::MultiKey_NoThrow *)v33);
  if ( Field_MultiString < 0 )
  {
    v16 = 52;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler-custom.cpp",
      (const char *)(unsigned int)Field_MultiString,
      v28[0]);
    v17 = v29;
    v29 = 0;
    if ( v17 )
      SRCacheContext_Close(v17);
    goto LABEL_18;
  }
  v19 = v33[0];
  v20 = StateRepository::Cache::Context_NoThrow::SetField_MultiString(a5, v18, v33[0]);
  v21 = v20;
  if ( v20 >= 0 )
  {
    v25 = v29;
    v29 = 0;
    if ( v25 )
      SRCacheContext_Close(v25);
    v26 = v36;
    v36 = 0;
    if ( v26 )
      SRCache_Free(v26);
    if ( v19 )
      SRCache_Free(v19);
    v27 = *(_QWORD *)v28;
    *(_QWORD *)v28 = 0;
    if ( v27 )
      SRCache_Free(v27);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x35,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-cacheappurihandler-custom.cpp",
    (const char *)(unsigned int)v20,
    v28[0]);
  v22 = v29;
  v29 = 0;
  if ( v22 )
    SRCacheContext_Close(v22);
  v23 = v36;
  v36 = 0;
  if ( v23 )
    SRCache_Free(v23);
  if ( v19 )
    SRCache_Free(v19);
  v24 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v24 )
    SRCache_Free(v24);
  return v21;
}

```

## disassembly

```asm
0x18007460c  push    rbp
0x18007460e  push    rbx
0x18007460f  push    rsi
0x180074610  push    rdi
0x180074611  push    r14
0x180074613  push    r15
0x180074615  lea     rbp, [rsp-1A8h]
0x18007461d  sub     rsp, 2A8h
0x180074624  mov     rax, cs:__security_cookie
0x18007462b  xor     rax, rsp
0x18007462e  mov     [rbp+1D0h+var_40], rax
0x180074635  mov     rax, [rcx+8]
0x180074639  xor     r15d, r15d
0x18007463c  mov     rsi, [rbp+1D0h+arg_20]
0x180074643  mov     rdi, rcx
0x180074646  mov     r14, [rbp+1D0h+arg_28]
0x18007464d  test    rax, rax
0x180074650  jz      loc_180074977
0x180074656  cmp     word ptr [rax], 2Ah ; '*'
0x18007465a  jnz     loc_180074977
0x180074660  lea     rax, [rsp+2D0h+var_2B0]
0x180074665  mov     qword ptr [rsp+2D0h+var_2B0], r15; int
0x18007466a  lea     r8, [rsp+2D0h+var_298]; unsigned __int16 **
0x18007466f  mov     [rsp+2D0h+var_2A0], rax
0x180074674  mov     rcx, rsi; this
0x180074677  mov     [rsp+2D0h+var_298], r15
0x18007467c  mov     [rsp+2D0h+var_290], 1
0x180074681  call    ?GetField_MultiString@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z; StateRepository::Cache::Context_NoThrow::GetField_MultiString(ushort const *,ushort * *)
0x180074686  mov     ebx, eax
0x180074688  cmp     [rsp+2D0h+var_290], r15b
0x18007468d  jz      short loc_1800746AA
0x18007468f  mov     r8, [rsp+2D0h+var_2A0]
0x180074694  mov     rdx, [rsp+2D0h+var_298]
0x180074699  mov     rcx, [r8]
0x18007469c  mov     [r8], rdx
0x18007469f  test    rcx, rcx
0x1800746a2  jz      short loc_1800746AA
0x1800746a4  call    cs:__imp_SRCache_Free
0x1800746aa  test    ebx, ebx
0x1800746ac  jns     short loc_1800746E5
0x1800746ae  mov     rcx, [rbp+1D8h]; this
0x1800746b5  lea     r8, aOnecoreBaseApp_326; "onecore\\base\\appmodel\\staterepositor"...
0x1800746bc  mov     r9d, ebx; char *
0x1800746bf  mov     edx, 29h ; ')'; void *
0x1800746c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800746c9  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x1800746ce  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x1800746d3  test    rcx, rcx
0x1800746d6  jz      short loc_1800746DE
0x1800746d8  call    cs:__imp_SRCache_Free
0x1800746de  mov     eax, ebx
0x1800746e0  jmp     loc_180074979
0x1800746e5  xorps   xmm0, xmm0
0x1800746e8  mov     qword ptr [rsp+2D0h+var_278], r15
0x1800746ed  lea     rdx, [rsp+2D0h+var_2B0]
0x1800746f2  mov     [rsp+2D0h+var_270], r15
0x1800746f7  lea     rcx, [rsp+2D0h+var_288]
0x1800746fc  movdqu  xmmword ptr [rsp+2D0h+var_288], xmm0
0x180074702  call    ?Attach@MultiKey_NoThrow@Cache@StateRepository@@QEAAJAEAV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?SRCache_Free@@YAX0@Z@wil@@@wistd@@@Z; StateRepository::Cache::MultiKey_NoThrow::Attach(wistd::unique_ptr<ushort [0],wil::function_deleter<void (*)(void *),&SRCache_Free(void *)>> &)
0x180074707  mov     ebx, eax
0x180074709  test    eax, eax
0x18007470b  jns     short loc_18007473A
0x18007470d  mov     rcx, [rbp+1D8h]; this
0x180074714  lea     r8, aOnecoreBaseApp_326; "onecore\\base\\appmodel\\staterepositor"...
0x18007471b  mov     r9d, eax; char *
0x18007471e  mov     edx, 2Bh ; '+'; void *
0x180074723  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074728  mov     rcx, [rsp+2D0h+var_288]
0x18007472d  test    rcx, rcx
0x180074730  jz      short loc_1800746C9
0x180074732  call    cs:__imp_SRCache_Free
0x180074738  jmp     short loc_1800746C9
0x18007473a  xor     edx, edx; Val
0x18007473c  mov     [rsp+2D0h+var_260], r15
0x180074741  mov     r8d, 200h; Size
0x180074747  lea     rcx, [rsp+2D0h+var_258]; void *
0x18007474c  call    memset_0
0x180074751  lea     rax, [rsp+2D0h+var_258]
0x180074756  mov     [rbp+1D0h+var_58], r15
0x18007475d  lea     rdx, aHostname_0; "*HostName\\*\\"
0x180074764  mov     [rbp+1D0h+var_48], rax
0x18007476b  lea     rcx, [rsp+2D0h+var_260]; this
0x180074770  mov     [rbp+1D0h+var_50], 100h
0x18007477b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180074780  mov     ebx, eax
0x180074782  test    eax, eax
0x180074784  jns     short loc_1800747BF
0x180074786  mov     edx, 2Eh ; '.'; void *
0x18007478b  mov     rcx, [rbp+1D8h]; this
0x180074792  lea     r8, aOnecoreBaseApp_326; "onecore\\base\\appmodel\\staterepositor"...
0x180074799  mov     r9d, ebx; char *
0x18007479c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800747a1  mov     rcx, [rsp+2D0h+var_260]
0x1800747a6  mov     [rsp+2D0h+var_260], r15
0x1800747ab  test    rcx, rcx
0x1800747ae  jz      loc_180074728
0x1800747b4  call    cs:__imp_SRCache_Free
0x1800747ba  jmp     loc_180074728
0x1800747bf  mov     rdx, [rdi]; unsigned __int64
0x1800747c2  lea     rcx, [rsp+2D0h+var_260]; this
0x1800747c7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800747cc  mov     ebx, eax
0x1800747ce  test    eax, eax
0x1800747d0  jns     short loc_1800747D9
0x1800747d2  mov     edx, 2Fh ; '/'
0x1800747d7  jmp     short loc_18007478B
0x1800747d9  mov     rdx, [rbp+1D0h+var_48]; unsigned __int16 *
0x1800747e0  lea     rcx, [rsp+2D0h+var_288]; this
0x1800747e5  call    ?Append@MultiKey_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::MultiKey_NoThrow::Append(ushort const *)
0x1800747ea  mov     ebx, eax
0x1800747ec  test    eax, eax
0x1800747ee  jns     short loc_1800747F7
0x1800747f0  mov     edx, 30h ; '0'
0x1800747f5  jmp     short loc_18007478B
0x1800747f7  mov     rdx, [rbp+1D0h+var_48]
0x1800747fe  lea     rax, [rsp+2D0h+var_2A8]
0x180074803  mov     rcx, [r14]
0x180074806  lea     r9, [rsp+2D0h+var_298]
0x18007480b  xor     r8d, r8d
0x18007480e  mov     [rsp+2D0h+var_2A0], rax
0x180074813  mov     [rsp+2D0h+var_2A8], r15
0x180074818  mov     [rsp+2D0h+var_298], r15
0x18007481d  mov     [rsp+2D0h+var_290], 1
0x180074822  call    cs:__imp_SRCacheContext_CreateSubContext
0x180074828  lea     rcx, [rsp+2D0h+var_2A0]
0x18007482d  mov     ebx, eax
0x18007482f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180074834  test    ebx, ebx
0x180074836  jns     short loc_18007488C
0x180074838  mov     rcx, [rbp+1D8h]; this
0x18007483f  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180074846  mov     r9d, ebx; char *
0x180074849  mov     edx, 1E6h; void *
0x18007484e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180074853  mov     edx, 32h ; '2'; void *
0x180074858  mov     rcx, [rbp+1D8h]; this
0x18007485f  lea     r8, aOnecoreBaseApp_326; "onecore\\base\\appmodel\\staterepositor"...
0x180074866  mov     r9d, ebx; char *
0x180074869  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007486e  mov     rcx, [rsp+2D0h+var_2A8]
0x180074873  mov     [rsp+2D0h+var_2A8], r15
0x180074878  test    rcx, rcx
0x18007487b  jz      loc_1800747A1
0x180074881  call    cs:__imp_SRCacheContext_Close
0x180074887  jmp     loc_1800747A1
0x18007488c  lea     rcx, [rsp+2D0h+var_288]; this
0x180074891  call    ?End@MultiKey_NoThrow@Cache@StateRepository@@QEAAJXZ; StateRepository::Cache::MultiKey_NoThrow::End(void)
0x180074896  mov     ebx, eax
0x180074898  test    eax, eax
0x18007489a  jns     short loc_1800748A3
0x18007489c  mov     edx, 34h ; '4'
0x1800748a1  jmp     short loc_180074858
0x1800748a3  mov     rbx, [rsp+2D0h+var_288]
0x1800748a8  mov     rcx, rsi; this
0x1800748ab  mov     r9d, [rsp+2D0h+var_278]; unsigned int
0x1800748b0  mov     r8, rbx; unsigned __int16 *
0x1800748b3  call    ?SetField_MultiString@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG0I@Z; StateRepository::Cache::Context_NoThrow::SetField_MultiString(ushort const *,ushort const *,uint)
0x1800748b8  mov     edi, eax
0x1800748ba  test    eax, eax
0x1800748bc  jns     short loc_18007492A
0x1800748be  mov     rcx, [rbp+1D8h]; this
0x1800748c5  lea     r8, aOnecoreBaseApp_326; "onecore\\base\\appmodel\\staterepositor"...
0x1800748cc  mov     r9d, eax; char *
0x1800748cf  mov     edx, 35h ; '5'; void *
0x1800748d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800748d9  mov     rcx, [rsp+2D0h+var_2A8]
0x1800748de  mov     [rsp+2D0h+var_2A8], r15
0x1800748e3  test    rcx, rcx
0x1800748e6  jz      short loc_1800748EE
0x1800748e8  call    cs:__imp_SRCacheContext_Close
0x1800748ee  mov     rcx, [rsp+2D0h+var_260]
0x1800748f3  mov     [rsp+2D0h+var_260], r15
0x1800748f8  test    rcx, rcx
0x1800748fb  jz      short loc_180074903
0x1800748fd  call    cs:__imp_SRCache_Free
0x180074903  test    rbx, rbx
0x180074906  jz      short loc_180074911
0x180074908  mov     rcx, rbx
0x18007490b  call    cs:__imp_SRCache_Free
0x180074911  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x180074916  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18007491b  test    rcx, rcx
0x18007491e  jz      short loc_180074926
0x180074920  call    cs:__imp_SRCache_Free
0x180074926  mov     eax, edi
0x180074928  jmp     short loc_180074979
0x18007492a  mov     rcx, [rsp+2D0h+var_2A8]
0x18007492f  mov     [rsp+2D0h+var_2A8], r15
0x180074934  test    rcx, rcx
0x180074937  jz      short loc_18007493F
0x180074939  call    cs:__imp_SRCacheContext_Close
0x18007493f  mov     rcx, [rsp+2D0h+var_260]
0x180074944  mov     [rsp+2D0h+var_260], r15
0x180074949  test    rcx, rcx
0x18007494c  jz      short loc_180074954
0x18007494e  call    cs:__imp_SRCache_Free
0x180074954  test    rbx, rbx
0x180074957  jz      short loc_180074962
0x180074959  mov     rcx, rbx
0x18007495c  call    cs:__imp_SRCache_Free
0x180074962  mov     rcx, qword ptr [rsp+2D0h+var_2B0]
0x180074967  mov     qword ptr [rsp+2D0h+var_2B0], r15
0x18007496c  test    rcx, rcx
0x18007496f  jz      short loc_180074977
0x180074971  call    cs:__imp_SRCache_Free
0x180074977  xor     eax, eax
0x180074979  mov     rcx, [rbp+1D0h+var_40]
0x180074980  xor     rcx, rsp; StackCookie
0x180074983  call    __security_check_cookie
0x180074988  add     rsp, 2A8h
0x18007498f  pop     r15
0x180074991  pop     r14
0x180074993  pop     rdi
0x180074994  pop     rsi
0x180074995  pop     rbx
0x180074996  pop     rbp
0x180074997  retn
```
