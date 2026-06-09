# StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x180014ef0`
- end: `0x18001518a`
- name: `?GetByPackageFullName@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800155dc`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180009f64`
- `0x180014ef0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014fa9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800150db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001513b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015165`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014fa9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800150db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001513b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015165`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015044`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015150`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015044`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015150`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014f4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014f4e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001507c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001507c`

## string_xrefs

- `0x180014f6b`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180015099`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180014f8b`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x18001501d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x1800150b9`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  bool v10; // r8
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+28h] [rbp-D8h] BYREF
  __int64 *v20; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v21; // [rsp+38h] [rbp-C8h] BYREF
  char v22; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v22 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v18 = 0;
  v20 = (__int64 *)v18;
  v21 = 0;
  v6 = SRCacheContext_Open(v3, L"PackageMachineStatus\\Index\\PackageFullName", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v7 = 196;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
LABEL_4:
    v8 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v8 )
      SRCacheContext_Close(v8);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v18 )
  {
    v6 = -2140733422;
    v7 = 197;
    goto LABEL_3;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2, v10);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v11,
      v18[0]);
LABEL_11:
    v12 = v23;
    v23 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_4;
  }
  v20 = &v19;
  v19 = 0;
  v21 = 0;
  v22 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v27, 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v13 = 204;
    goto LABEL_15;
  }
  if ( v19 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v19, 0, a3);
    if ( v6 < 0 )
    {
      v13 = 207;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"PackageMachineStatus\\Index\\PackageFullName");
  if ( v6 < 0 )
  {
    v13 = 210;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v14 = v19;
    v19 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    goto LABEL_11;
  }
  v15 = v19;
  v19 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  v16 = v23;
  v23 = 0;
  if ( v16 )
    SRCache_Free(v16);
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  return 0;
}

```

## disassembly

```asm
0x180014ef0  push    rbp
0x180014ef2  push    rbx
0x180014ef3  push    rsi
0x180014ef4  push    rdi
0x180014ef5  push    r14
0x180014ef7  lea     rbp, [rsp-180h]
0x180014eff  sub     rsp, 280h
0x180014f06  mov     rax, cs:__security_cookie
0x180014f0d  xor     rax, rsp
0x180014f10  mov     [rbp+1A0h+var_30], rax
0x180014f17  xor     r14d, r14d
0x180014f1a  mov     [rsp+2A0h+var_260], 1
0x180014f1f  mov     [r8], r14
0x180014f22  lea     rax, [rsp+2A0h+var_280]
0x180014f27  mov     rcx, [rcx]
0x180014f2a  lea     r9, [rsp+2A0h+var_268]
0x180014f2f  mov     rdi, r8
0x180014f32  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x180014f37  mov     rsi, rdx
0x180014f3a  mov     [rsp+2A0h+var_270], rax
0x180014f3f  xor     r8d, r8d
0x180014f42  mov     [rsp+2A0h+var_268], r14
0x180014f47  lea     rdx, aPackagemachine; "PackageMachineStatus\\Index\\PackageFul"...
0x180014f4e  call    cs:__imp_SRCacheContext_Open
0x180014f54  lea     rcx, [rsp+2A0h+var_270]
0x180014f59  mov     ebx, eax
0x180014f5b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180014f60  test    ebx, ebx
0x180014f62  jns     short loc_180014FB6
0x180014f64  mov     rcx, [rbp+1A8h]; this
0x180014f6b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180014f72  mov     r9d, ebx; char *
0x180014f75  mov     edx, 18Ch; void *
0x180014f7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f7f  mov     edx, 0C4h; void *
0x180014f84  mov     rcx, [rbp+1A8h]; this
0x180014f8b  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180014f92  mov     r9d, ebx; char *
0x180014f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014f9a  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180014f9f  mov     qword ptr [rsp+2A0h+var_280], r14
0x180014fa4  test    rcx, rcx
0x180014fa7  jz      short loc_180014FAF
0x180014fa9  call    cs:__imp_SRCacheContext_Close
0x180014faf  mov     eax, ebx
0x180014fb1  jmp     loc_18001516D
0x180014fb6  cmp     qword ptr [rsp+2A0h+var_280], r14
0x180014fbb  setnz   al
0x180014fbe  test    al, al
0x180014fc0  jnz     short loc_180014FCE
0x180014fc2  mov     ebx, 80670012h
0x180014fc7  mov     edx, 0C5h
0x180014fcc  jmp     short loc_180014F84
0x180014fce  xor     edx, edx; Val
0x180014fd0  mov     [rsp+2A0h+var_250], r14
0x180014fd5  mov     r8d, 200h; Size
0x180014fdb  lea     rcx, [rsp+2A0h+var_248]; void *
0x180014fe0  call    memset_0
0x180014fe5  lea     rax, [rsp+2A0h+var_248]
0x180014fea  mov     [rbp+1A0h+var_48], r14
0x180014ff1  mov     rdx, rsi; unsigned __int16 *
0x180014ff4  mov     [rbp+1A0h+var_38], rax
0x180014ffb  lea     rcx, [rsp+2A0h+var_250]; this
0x180015000  mov     [rbp+1A0h+var_40], 100h
0x18001500b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180015010  mov     ebx, eax
0x180015012  test    eax, eax
0x180015014  jns     short loc_18001504F
0x180015016  mov     rcx, [rbp+1A8h]; this
0x18001501d  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180015024  mov     r9d, eax; char *
0x180015027  mov     edx, 0C8h; void *
0x18001502c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015031  mov     rcx, [rsp+2A0h+var_250]
0x180015036  mov     [rsp+2A0h+var_250], r14
0x18001503b  test    rcx, rcx
0x18001503e  jz      loc_180014F9A
0x180015044  call    cs:__imp_SRCache_Free
0x18001504a  jmp     loc_180014F9A
0x18001504f  mov     rdx, [rbp+1A0h+var_38]
0x180015056  lea     rax, [rsp+2A0h+var_278]
0x18001505b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015060  lea     r9, [rsp+2A0h+var_268]
0x180015065  xor     r8d, r8d
0x180015068  mov     [rsp+2A0h+var_270], rax
0x18001506d  mov     [rsp+2A0h+var_278], r14
0x180015072  mov     [rsp+2A0h+var_268], r14
0x180015077  mov     [rsp+2A0h+var_260], 1
0x18001507c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180015082  lea     rcx, [rsp+2A0h+var_270]
0x180015087  mov     ebx, eax
0x180015089  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001508e  test    ebx, ebx
0x180015090  jns     short loc_1800150E6
0x180015092  mov     rcx, [rbp+1A8h]; this
0x180015099  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800150a0  mov     r9d, ebx; char *
0x1800150a3  mov     edx, 1B0h; void *
0x1800150a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150ad  mov     edx, 0CCh; void *
0x1800150b2  mov     rcx, [rbp+1A8h]; this
0x1800150b9  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x1800150c0  mov     r9d, ebx; char *
0x1800150c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150c8  mov     rcx, [rsp+2A0h+var_278]
0x1800150cd  mov     [rsp+2A0h+var_278], r14
0x1800150d2  test    rcx, rcx
0x1800150d5  jz      loc_180015031
0x1800150db  call    cs:__imp_SRCacheContext_Close
0x1800150e1  jmp     loc_180015031
0x1800150e6  cmp     [rsp+2A0h+var_278], r14
0x1800150eb  setnz   al
0x1800150ee  test    al, al
0x1800150f0  jz      short loc_18001510E
0x1800150f2  mov     r8, rdi; __int64 *
0x1800150f5  lea     rcx, [rsp+2A0h+var_278]; this
0x1800150fa  xor     edx, edx; int
0x1800150fc  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180015101  mov     ebx, eax
0x180015103  test    eax, eax
0x180015105  jns     short loc_18001510E
0x180015107  mov     edx, 0CFh
0x18001510c  jmp     short loc_1800150B2
0x18001510e  lea     rdx, aPackagemachine; "PackageMachineStatus\\Index\\PackageFul"...
0x180015115  lea     rcx, [rsp+2A0h+var_280]; this
0x18001511a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001511f  mov     ebx, eax
0x180015121  test    eax, eax
0x180015123  jns     short loc_18001512C
0x180015125  mov     edx, 0D2h
0x18001512a  jmp     short loc_1800150B2
0x18001512c  mov     rcx, [rsp+2A0h+var_278]
0x180015131  mov     [rsp+2A0h+var_278], r14
0x180015136  test    rcx, rcx
0x180015139  jz      short loc_180015141
0x18001513b  call    cs:__imp_SRCacheContext_Close
0x180015141  mov     rcx, [rsp+2A0h+var_250]
0x180015146  mov     [rsp+2A0h+var_250], r14
0x18001514b  test    rcx, rcx
0x18001514e  jz      short loc_180015156
0x180015150  call    cs:__imp_SRCache_Free
0x180015156  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001515b  mov     qword ptr [rsp+2A0h+var_280], r14
0x180015160  test    rcx, rcx
0x180015163  jz      short loc_18001516B
0x180015165  call    cs:__imp_SRCacheContext_Close
0x18001516b  xor     eax, eax
0x18001516d  mov     rcx, [rbp+1A0h+var_30]
0x180015174  xor     rcx, rsp; StackCookie
0x180015177  call    __security_check_cookie
0x18001517c  add     rsp, 280h
0x180015183  pop     r14
0x180015185  pop     rdi
0x180015186  pop     rsi
0x180015187  pop     rbx
0x180015188  pop     rbp
0x180015189  retn
```
