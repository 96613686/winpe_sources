# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18015cf34`
- end: `0x18015d171`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18026631c`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18015cf34`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18015d0bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18015d0bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015cff2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015d143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015cff2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18015d143`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015d08d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015d12e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015d08d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18015d12e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18015cf97`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18015cf97`

## string_xrefs

- `0x18015cfb4`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18015d0d8`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18015cfd4`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Package.hpp`
- `0x18015d06b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v17; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  char v19; // [rsp+38h] [rbp-C8h]
  __int64 v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+248h] [rbp+148h]
  __int64 v23; // [rsp+250h] [rbp+150h]
  _BYTE *v24; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v17 = v16;
  v19 = 1;
  *(_QWORD *)v16 = 0;
  v18 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
LABEL_4:
    v10 = *(_QWORD *)v16;
    *(_QWORD *)v16 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v16 )
  {
    v8 = -2140733422;
    v9 = 1193;
    goto LABEL_3;
  }
  v20 = 0;
  memset_0(v21, 0, sizeof(v21));
  v22 = 0;
  v24 = v21;
  v23 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v20, a2);
  if ( v8 < 0 )
  {
    v12 = 1196;
    goto LABEL_11;
  }
  v17 = (int *)a3;
  v18 = 0;
  v19 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v24, 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 1197;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Package\\Data");
  if ( v8 < 0 )
  {
    v12 = 1199;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v20;
    v20 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v20;
  v20 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18015cf34  mov     [rsp-8+arg_10], rbx
0x18015cf39  push    rbp
0x18015cf3a  push    rsi
0x18015cf3b  push    rdi
0x18015cf3c  push    r14
0x18015cf3e  push    r15
0x18015cf40  lea     rbp, [rsp-170h]
0x18015cf48  sub     rsp, 270h
0x18015cf4f  mov     rax, cs:__security_cookie
0x18015cf56  xor     rax, rsp
0x18015cf59  mov     [rbp+190h+var_30], rax
0x18015cf60  mov     rcx, [rcx]
0x18015cf63  lea     rax, [rsp+290h+var_270]
0x18015cf68  mov     rsi, r9
0x18015cf6b  mov     [rsp+290h+var_268], rax
0x18015cf70  mov     rdi, r8
0x18015cf73  mov     [rsp+290h+var_258], 1
0x18015cf78  mov     r14, rdx
0x18015cf7b  lea     r9, [rsp+290h+var_260]
0x18015cf80  xor     r15d, r15d
0x18015cf83  lea     rdx, aPackageData; "Package\\Data"
0x18015cf8a  xor     r8d, r8d
0x18015cf8d  mov     qword ptr [rsp+290h+var_270], r15; int
0x18015cf92  mov     [rsp+290h+var_260], r15
0x18015cf97  call    cs:__imp_SRCacheContext_Open
0x18015cf9d  lea     rcx, [rsp+290h+var_268]
0x18015cfa2  mov     ebx, eax
0x18015cfa4  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18015cfa9  test    ebx, ebx
0x18015cfab  jns     short loc_18015CFFF
0x18015cfad  mov     rcx, [rbp+198h]; this
0x18015cfb4  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18015cfbb  mov     r9d, ebx; char *
0x18015cfbe  mov     edx, 18Ch; void *
0x18015cfc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015cfc8  mov     edx, 4A8h; void *
0x18015cfcd  mov     rcx, [rbp+198h]; this
0x18015cfd4  lea     r8, aOnecoreBaseApp_484; "onecore\\base\\appmodel\\StateRepositor"...
0x18015cfdb  mov     r9d, ebx; char *
0x18015cfde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015cfe3  mov     rcx, qword ptr [rsp+290h+var_270]
0x18015cfe8  mov     qword ptr [rsp+290h+var_270], r15
0x18015cfed  test    rcx, rcx
0x18015cff0  jz      short loc_18015CFF8
0x18015cff2  call    cs:__imp_SRCacheContext_Close
0x18015cff8  mov     eax, ebx
0x18015cffa  jmp     loc_18015D14B
0x18015cfff  cmp     qword ptr [rsp+290h+var_270], r15
0x18015d004  setnz   al
0x18015d007  test    al, al
0x18015d009  jnz     short loc_18015D017
0x18015d00b  mov     ebx, 80670012h
0x18015d010  mov     edx, 4A9h
0x18015d015  jmp     short loc_18015CFCD
0x18015d017  xor     edx, edx; Val
0x18015d019  mov     [rsp+290h+var_250], r15
0x18015d01e  mov     r8d, 200h; Size
0x18015d024  lea     rcx, [rsp+290h+var_248]; void *
0x18015d029  call    memset_0
0x18015d02e  lea     rax, [rsp+290h+var_248]
0x18015d033  mov     [rbp+190h+var_48], r15
0x18015d03a  mov     rdx, r14; unsigned __int64
0x18015d03d  mov     [rbp+190h+var_38], rax
0x18015d044  lea     rcx, [rsp+290h+var_250]; this
0x18015d049  mov     [rbp+190h+var_40], 100h
0x18015d054  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18015d059  mov     ebx, eax
0x18015d05b  test    eax, eax
0x18015d05d  jns     short loc_18015D098
0x18015d05f  mov     edx, 4ACh; void *
0x18015d064  mov     rcx, [rbp+198h]; this
0x18015d06b  lea     r8, aOnecoreBaseApp_484; "onecore\\base\\appmodel\\StateRepositor"...
0x18015d072  mov     r9d, ebx; char *
0x18015d075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015d07a  mov     rcx, [rsp+290h+var_250]
0x18015d07f  mov     [rsp+290h+var_250], r15
0x18015d084  test    rcx, rcx
0x18015d087  jz      loc_18015CFE3
0x18015d08d  call    cs:__imp_SRCache_Free
0x18015d093  jmp     loc_18015CFE3
0x18015d098  mov     rdx, [rbp+190h+var_38]
0x18015d09f  lea     r9, [rsp+290h+var_260]
0x18015d0a4  mov     rcx, qword ptr [rsp+290h+var_270]
0x18015d0a9  xor     r8d, r8d
0x18015d0ac  mov     [rsp+290h+var_268], rdi
0x18015d0b1  mov     [rsp+290h+var_260], r15
0x18015d0b6  mov     [rsp+290h+var_258], 1
0x18015d0bb  call    cs:__imp_SRCacheContext_OpenSubContext
0x18015d0c1  lea     rcx, [rsp+290h+var_268]
0x18015d0c6  mov     ebx, eax
0x18015d0c8  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18015d0cd  test    ebx, ebx
0x18015d0cf  jns     short loc_18015D0F6
0x18015d0d1  mov     rcx, [rbp+198h]; this
0x18015d0d8  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18015d0df  mov     r9d, ebx; char *
0x18015d0e2  mov     edx, 1B0h; void *
0x18015d0e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18015d0ec  mov     edx, 4ADh
0x18015d0f1  jmp     loc_18015D064
0x18015d0f6  cmp     [rdi], r15
0x18015d0f9  lea     rdx, aPackageData; "Package\\Data"
0x18015d100  lea     rcx, [rsp+290h+var_270]; this
0x18015d105  setnz   al
0x18015d108  mov     [rsi], al
0x18015d10a  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18015d10f  mov     ebx, eax
0x18015d111  test    eax, eax
0x18015d113  jns     short loc_18015D11F
0x18015d115  mov     edx, 4AFh
0x18015d11a  jmp     loc_18015D064
0x18015d11f  mov     rcx, [rsp+290h+var_250]
0x18015d124  mov     [rsp+290h+var_250], r15
0x18015d129  test    rcx, rcx
0x18015d12c  jz      short loc_18015D134
0x18015d12e  call    cs:__imp_SRCache_Free
0x18015d134  mov     rcx, qword ptr [rsp+290h+var_270]
0x18015d139  mov     qword ptr [rsp+290h+var_270], r15
0x18015d13e  test    rcx, rcx
0x18015d141  jz      short loc_18015D149
0x18015d143  call    cs:__imp_SRCacheContext_Close
0x18015d149  xor     eax, eax
0x18015d14b  mov     rcx, [rbp+190h+var_30]
0x18015d152  xor     rcx, rsp; StackCookie
0x18015d155  call    __security_check_cookie
0x18015d15a  mov     rbx, [rsp+290h+arg_10]
0x18015d162  add     rsp, 270h
0x18015d169  pop     r15
0x18015d16b  pop     r14
0x18015d16d  pop     rdi
0x18015d16e  pop     rsi
0x18015d16f  pop     rbp
0x18015d170  retn
```
