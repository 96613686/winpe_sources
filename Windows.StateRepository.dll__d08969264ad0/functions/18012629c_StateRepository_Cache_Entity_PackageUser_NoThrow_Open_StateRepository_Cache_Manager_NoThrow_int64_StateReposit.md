# StateRepository::Cache::Entity::PackageUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18012629c`
- end: `0x1801264d9`
- name: `?Open@PackageUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026760c`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18012629c`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180126423`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180126423`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012635a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801264ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18012635a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1801264ab`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801263f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180126496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1801263f5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180126496`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801262ff`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1801262ff`

## string_xrefs

- `0x18012631c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180126440`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18012633c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageUser.hpp`
- `0x1801263d3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageUser\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 298;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageUser.hpp",
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
    v9 = 299;
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
    v14 = 302;
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
    v14 = 303;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"PackageUser\\Data");
  if ( v8 < 0 )
  {
    v14 = 305;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageUser.hpp",
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
0x18012629c  mov     [rsp-8+arg_10], rbx
0x1801262a1  push    rbp
0x1801262a2  push    rsi
0x1801262a3  push    rdi
0x1801262a4  push    r14
0x1801262a6  push    r15
0x1801262a8  lea     rbp, [rsp-170h]
0x1801262b0  sub     rsp, 270h
0x1801262b7  mov     rax, cs:__security_cookie
0x1801262be  xor     rax, rsp
0x1801262c1  mov     [rbp+190h+var_30], rax
0x1801262c8  mov     rcx, [rcx]
0x1801262cb  lea     rax, [rsp+290h+var_270]
0x1801262d0  mov     rsi, r9
0x1801262d3  mov     [rsp+290h+var_268], rax
0x1801262d8  mov     rdi, r8
0x1801262db  mov     [rsp+290h+var_258], 1
0x1801262e0  mov     r14, rdx
0x1801262e3  lea     r9, [rsp+290h+var_260]
0x1801262e8  xor     r15d, r15d
0x1801262eb  lea     rdx, aPackageuserDat; "PackageUser\\Data"
0x1801262f2  xor     r8d, r8d
0x1801262f5  mov     qword ptr [rsp+290h+var_270], r15; int
0x1801262fa  mov     [rsp+290h+var_260], r15
0x1801262ff  call    cs:__imp_SRCacheContext_Open
0x180126305  lea     rcx, [rsp+290h+var_268]
0x18012630a  mov     ebx, eax
0x18012630c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180126311  test    ebx, ebx
0x180126313  jns     short loc_180126367
0x180126315  mov     rcx, [rbp+198h]; this
0x18012631c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180126323  mov     r9d, ebx; char *
0x180126326  mov     edx, 18Ch; void *
0x18012632b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126330  mov     edx, 12Ah; void *
0x180126335  mov     rcx, [rbp+198h]; this
0x18012633c  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\StateRepositor"...
0x180126343  mov     r9d, ebx; char *
0x180126346  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18012634b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180126350  mov     qword ptr [rsp+290h+var_270], r15
0x180126355  test    rcx, rcx
0x180126358  jz      short loc_180126360
0x18012635a  call    cs:__imp_SRCacheContext_Close
0x180126360  mov     eax, ebx
0x180126362  jmp     loc_1801264B3
0x180126367  cmp     qword ptr [rsp+290h+var_270], r15
0x18012636c  setnz   al
0x18012636f  test    al, al
0x180126371  jnz     short loc_18012637F
0x180126373  mov     ebx, 80670012h
0x180126378  mov     edx, 12Bh
0x18012637d  jmp     short loc_180126335
0x18012637f  xor     edx, edx; Val
0x180126381  mov     [rsp+290h+var_250], r15
0x180126386  mov     r8d, 200h; Size
0x18012638c  lea     rcx, [rsp+290h+var_248]; void *
0x180126391  call    memset_0
0x180126396  lea     rax, [rsp+290h+var_248]
0x18012639b  mov     [rbp+190h+var_48], r15
0x1801263a2  mov     rdx, r14; unsigned __int64
0x1801263a5  mov     [rbp+190h+var_38], rax
0x1801263ac  lea     rcx, [rsp+290h+var_250]; this
0x1801263b1  mov     [rbp+190h+var_40], 100h
0x1801263bc  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1801263c1  mov     ebx, eax
0x1801263c3  test    eax, eax
0x1801263c5  jns     short loc_180126400
0x1801263c7  mov     edx, 12Eh; void *
0x1801263cc  mov     rcx, [rbp+198h]; this
0x1801263d3  lea     r8, aOnecoreBaseApp_64; "onecore\\base\\appmodel\\StateRepositor"...
0x1801263da  mov     r9d, ebx; char *
0x1801263dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801263e2  mov     rcx, [rsp+290h+var_250]
0x1801263e7  mov     [rsp+290h+var_250], r15
0x1801263ec  test    rcx, rcx
0x1801263ef  jz      loc_18012634B
0x1801263f5  call    cs:__imp_SRCache_Free
0x1801263fb  jmp     loc_18012634B
0x180126400  mov     rdx, [rbp+190h+var_38]
0x180126407  lea     r9, [rsp+290h+var_260]
0x18012640c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180126411  xor     r8d, r8d
0x180126414  mov     [rsp+290h+var_268], rdi
0x180126419  mov     [rsp+290h+var_260], r15
0x18012641e  mov     [rsp+290h+var_258], 1
0x180126423  call    cs:__imp_SRCacheContext_OpenSubContext
0x180126429  lea     rcx, [rsp+290h+var_268]
0x18012642e  mov     ebx, eax
0x180126430  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180126435  test    ebx, ebx
0x180126437  jns     short loc_18012645E
0x180126439  mov     rcx, [rbp+198h]; this
0x180126440  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180126447  mov     r9d, ebx; char *
0x18012644a  mov     edx, 1B0h; void *
0x18012644f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180126454  mov     edx, 12Fh
0x180126459  jmp     loc_1801263CC
0x18012645e  cmp     [rdi], r15
0x180126461  lea     rdx, aPackageuserDat; "PackageUser\\Data"
0x180126468  lea     rcx, [rsp+290h+var_270]; this
0x18012646d  setnz   al
0x180126470  mov     [rsi], al
0x180126472  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180126477  mov     ebx, eax
0x180126479  test    eax, eax
0x18012647b  jns     short loc_180126487
0x18012647d  mov     edx, 131h
0x180126482  jmp     loc_1801263CC
0x180126487  mov     rcx, [rsp+290h+var_250]
0x18012648c  mov     [rsp+290h+var_250], r15
0x180126491  test    rcx, rcx
0x180126494  jz      short loc_18012649C
0x180126496  call    cs:__imp_SRCache_Free
0x18012649c  mov     rcx, qword ptr [rsp+290h+var_270]
0x1801264a1  mov     qword ptr [rsp+290h+var_270], r15
0x1801264a6  test    rcx, rcx
0x1801264a9  jz      short loc_1801264B1
0x1801264ab  call    cs:__imp_SRCacheContext_Close
0x1801264b1  xor     eax, eax
0x1801264b3  mov     rcx, [rbp+190h+var_30]
0x1801264ba  xor     rcx, rsp; StackCookie
0x1801264bd  call    __security_check_cookie
0x1801264c2  mov     rbx, [rsp+290h+arg_10]
0x1801264ca  add     rsp, 270h
0x1801264d1  pop     r15
0x1801264d3  pop     r14
0x1801264d5  pop     rdi
0x1801264d6  pop     rsi
0x1801264d7  pop     rbp
0x1801264d8  retn
```
