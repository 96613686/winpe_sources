# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18000a1c4`
- end: `0x18000a45e`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b20c`
- `0x18000bf90`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180009f64`
- `0x18000a1c4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a27d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a3af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a40f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a27d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a3af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a40f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a439`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a318`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a318`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000a424`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a222`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000a222`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a350`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000a350`

## string_xrefs

- `0x18000a23f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000a36d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000a25f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x18000a2f1`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x18000a38d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+28h] [rbp-D8h] BYREF
  int *v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v20; // [rsp+38h] [rbp-C8h] BYREF
  char v21; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h]
  __int64 v25; // [rsp+260h] [rbp+160h]
  _BYTE *v26; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v21 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v17 = 0;
  v19 = v17;
  v20 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v7 = 1128;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
LABEL_4:
    v8 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v17 )
  {
    v6 = -2140733422;
    v7 = 1129;
    goto LABEL_3;
  }
  v22 = 0;
  memset_0(v23, 0, sizeof(v23));
  v24 = 0;
  v26 = v23;
  v25 = 256;
  v10 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v22, a2);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v10,
      v17[0]);
LABEL_11:
    v11 = v22;
    v22 = 0;
    if ( v11 )
      SRCache_Free();
    goto LABEL_4;
  }
  v19 = (int *)&v18;
  v18 = 0;
  v20 = 0;
  v21 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v26, 0, &v20);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v19);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v12 = 1136;
    goto LABEL_15;
  }
  if ( v18 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v18, 0, a3);
    if ( v6 < 0 )
    {
      v12 = 1139;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"Package\\Index\\PackageFullName");
  if ( v6 < 0 )
  {
    v12 = 1142;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v17[0]);
    v13 = v18;
    v18 = 0;
    if ( v13 )
      SRCacheContext_Close(v13);
    goto LABEL_11;
  }
  v14 = v18;
  v18 = 0;
  if ( v14 )
    SRCacheContext_Close(v14);
  v15 = v22;
  v22 = 0;
  if ( v15 )
    SRCache_Free();
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x18000a1c4  push    rbp
0x18000a1c6  push    rbx
0x18000a1c7  push    rsi
0x18000a1c8  push    rdi
0x18000a1c9  push    r14
0x18000a1cb  lea     rbp, [rsp-180h]
0x18000a1d3  sub     rsp, 280h
0x18000a1da  mov     rax, cs:__security_cookie
0x18000a1e1  xor     rax, rsp
0x18000a1e4  mov     [rbp+1A0h+var_30], rax
0x18000a1eb  xor     r14d, r14d
0x18000a1ee  mov     [rsp+2A0h+var_260], 1
0x18000a1f3  mov     [r8], r14
0x18000a1f6  lea     rax, [rsp+2A0h+var_280]
0x18000a1fb  mov     rcx, [rcx]
0x18000a1fe  lea     r9, [rsp+2A0h+var_268]
0x18000a203  mov     rdi, r8
0x18000a206  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18000a20b  mov     rsi, rdx
0x18000a20e  mov     [rsp+2A0h+var_270], rax
0x18000a213  xor     r8d, r8d
0x18000a216  mov     [rsp+2A0h+var_268], r14
0x18000a21b  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18000a222  call    cs:__imp_SRCacheContext_Open
0x18000a228  lea     rcx, [rsp+2A0h+var_270]
0x18000a22d  mov     ebx, eax
0x18000a22f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000a234  test    ebx, ebx
0x18000a236  jns     short loc_18000A28A
0x18000a238  mov     rcx, [rbp+1A8h]; this
0x18000a23f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a246  mov     r9d, ebx; char *
0x18000a249  mov     edx, 18Ch; void *
0x18000a24e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a253  mov     edx, 468h; void *
0x18000a258  mov     rcx, [rbp+1A8h]; this
0x18000a25f  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a266  mov     r9d, ebx; char *
0x18000a269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a26e  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000a273  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000a278  test    rcx, rcx
0x18000a27b  jz      short loc_18000A283
0x18000a27d  call    cs:__imp_SRCacheContext_Close
0x18000a283  mov     eax, ebx
0x18000a285  jmp     loc_18000A441
0x18000a28a  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18000a28f  setnz   al
0x18000a292  test    al, al
0x18000a294  jnz     short loc_18000A2A2
0x18000a296  mov     ebx, 80670012h
0x18000a29b  mov     edx, 469h
0x18000a2a0  jmp     short loc_18000A258
0x18000a2a2  xor     edx, edx; Val
0x18000a2a4  mov     [rsp+2A0h+var_250], r14
0x18000a2a9  mov     r8d, 200h; Size
0x18000a2af  lea     rcx, [rsp+2A0h+var_248]; void *
0x18000a2b4  call    memset_0
0x18000a2b9  lea     rax, [rsp+2A0h+var_248]
0x18000a2be  mov     [rbp+1A0h+var_48], r14
0x18000a2c5  mov     rdx, rsi; unsigned __int16 *
0x18000a2c8  mov     [rbp+1A0h+var_38], rax
0x18000a2cf  lea     rcx, [rsp+2A0h+var_250]; this
0x18000a2d4  mov     [rbp+1A0h+var_40], 100h
0x18000a2df  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000a2e4  mov     ebx, eax
0x18000a2e6  test    eax, eax
0x18000a2e8  jns     short loc_18000A323
0x18000a2ea  mov     rcx, [rbp+1A8h]; this
0x18000a2f1  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a2f8  mov     r9d, eax; char *
0x18000a2fb  mov     edx, 46Ch; void *
0x18000a300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a305  mov     rcx, [rsp+2A0h+var_250]
0x18000a30a  mov     [rsp+2A0h+var_250], r14
0x18000a30f  test    rcx, rcx
0x18000a312  jz      loc_18000A26E
0x18000a318  call    cs:__imp_SRCache_Free
0x18000a31e  jmp     loc_18000A26E
0x18000a323  mov     rdx, [rbp+1A0h+var_38]
0x18000a32a  lea     rax, [rsp+2A0h+var_278]
0x18000a32f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000a334  lea     r9, [rsp+2A0h+var_268]
0x18000a339  xor     r8d, r8d
0x18000a33c  mov     [rsp+2A0h+var_270], rax
0x18000a341  mov     [rsp+2A0h+var_278], r14
0x18000a346  mov     [rsp+2A0h+var_268], r14
0x18000a34b  mov     [rsp+2A0h+var_260], 1
0x18000a350  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000a356  lea     rcx, [rsp+2A0h+var_270]
0x18000a35b  mov     ebx, eax
0x18000a35d  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000a362  test    ebx, ebx
0x18000a364  jns     short loc_18000A3BA
0x18000a366  mov     rcx, [rbp+1A8h]; this
0x18000a36d  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a374  mov     r9d, ebx; char *
0x18000a377  mov     edx, 1B0h; void *
0x18000a37c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a381  mov     edx, 470h; void *
0x18000a386  mov     rcx, [rbp+1A8h]; this
0x18000a38d  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a394  mov     r9d, ebx; char *
0x18000a397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a39c  mov     rcx, [rsp+2A0h+var_278]
0x18000a3a1  mov     [rsp+2A0h+var_278], r14
0x18000a3a6  test    rcx, rcx
0x18000a3a9  jz      loc_18000A305
0x18000a3af  call    cs:__imp_SRCacheContext_Close
0x18000a3b5  jmp     loc_18000A305
0x18000a3ba  cmp     [rsp+2A0h+var_278], r14
0x18000a3bf  setnz   al
0x18000a3c2  test    al, al
0x18000a3c4  jz      short loc_18000A3E2
0x18000a3c6  mov     r8, rdi; __int64 *
0x18000a3c9  lea     rcx, [rsp+2A0h+var_278]; this
0x18000a3ce  xor     edx, edx; int
0x18000a3d0  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18000a3d5  mov     ebx, eax
0x18000a3d7  test    eax, eax
0x18000a3d9  jns     short loc_18000A3E2
0x18000a3db  mov     edx, 473h
0x18000a3e0  jmp     short loc_18000A386
0x18000a3e2  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18000a3e9  lea     rcx, [rsp+2A0h+var_280]; this
0x18000a3ee  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000a3f3  mov     ebx, eax
0x18000a3f5  test    eax, eax
0x18000a3f7  jns     short loc_18000A400
0x18000a3f9  mov     edx, 476h
0x18000a3fe  jmp     short loc_18000A386
0x18000a400  mov     rcx, [rsp+2A0h+var_278]
0x18000a405  mov     [rsp+2A0h+var_278], r14
0x18000a40a  test    rcx, rcx
0x18000a40d  jz      short loc_18000A415
0x18000a40f  call    cs:__imp_SRCacheContext_Close
0x18000a415  mov     rcx, [rsp+2A0h+var_250]
0x18000a41a  mov     [rsp+2A0h+var_250], r14
0x18000a41f  test    rcx, rcx
0x18000a422  jz      short loc_18000A42A
0x18000a424  call    cs:__imp_SRCache_Free
0x18000a42a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000a42f  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000a434  test    rcx, rcx
0x18000a437  jz      short loc_18000A43F
0x18000a439  call    cs:__imp_SRCacheContext_Close
0x18000a43f  xor     eax, eax
0x18000a441  mov     rcx, [rbp+1A0h+var_30]
0x18000a448  xor     rcx, rsp; StackCookie
0x18000a44b  call    __security_check_cookie
0x18000a450  add     rsp, 280h
0x18000a457  pop     r14
0x18000a459  pop     rdi
0x18000a45a  pop     rsi
0x18000a45b  pop     rbx
0x18000a45c  pop     rbp
0x18000a45d  retn
```
