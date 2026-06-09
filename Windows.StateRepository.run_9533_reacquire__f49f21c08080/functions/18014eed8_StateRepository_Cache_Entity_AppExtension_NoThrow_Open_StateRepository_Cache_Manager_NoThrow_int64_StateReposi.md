# StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18014eed8`
- end: `0x18014f115`
- name: `?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180270f44`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18014eed8`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18014f05f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18014f05f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014ef96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f0e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014ef96`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18014f0e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18014f031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18014f0d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18014f031`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18014f0d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18014ef3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18014ef3b`

## string_xrefs

- `0x18014ef27`: `AppExtension\Data`
- `0x18014f09d`: `AppExtension\Data`
- `0x18014ef58`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014f07c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18014ef78`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppExtension.hpp`
- `0x18014f00f`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-AppExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
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
  v8 = SRCacheContext_Open(v4, L"AppExtension\\Data", 0, &v18);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v17);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppExtension.hpp",
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
    v9 = 312;
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
    v12 = 315;
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
    v12 = 316;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"AppExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 318;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-AppExtension.hpp",
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
0x18014eed8  mov     [rsp-8+arg_10], rbx
0x18014eedd  push    rbp
0x18014eede  push    rsi
0x18014eedf  push    rdi
0x18014eee0  push    r14
0x18014eee2  push    r15
0x18014eee4  lea     rbp, [rsp-170h]
0x18014eeec  sub     rsp, 270h
0x18014eef3  mov     rax, cs:__security_cookie
0x18014eefa  xor     rax, rsp
0x18014eefd  mov     [rbp+190h+var_30], rax
0x18014ef04  mov     rcx, [rcx]
0x18014ef07  lea     rax, [rsp+290h+var_270]
0x18014ef0c  mov     rsi, r9
0x18014ef0f  mov     [rsp+290h+var_268], rax
0x18014ef14  mov     rdi, r8
0x18014ef17  mov     [rsp+290h+var_258], 1
0x18014ef1c  mov     r14, rdx
0x18014ef1f  lea     r9, [rsp+290h+var_260]
0x18014ef24  xor     r15d, r15d
0x18014ef27  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x18014ef2e  xor     r8d, r8d
0x18014ef31  mov     qword ptr [rsp+290h+var_270], r15; int
0x18014ef36  mov     [rsp+290h+var_260], r15
0x18014ef3b  call    cs:__imp_SRCacheContext_Open
0x18014ef41  lea     rcx, [rsp+290h+var_268]
0x18014ef46  mov     ebx, eax
0x18014ef48  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014ef4d  test    ebx, ebx
0x18014ef4f  jns     short loc_18014EFA3
0x18014ef51  mov     rcx, [rbp+198h]; this
0x18014ef58  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014ef5f  mov     r9d, ebx; char *
0x18014ef62  mov     edx, 18Ch; void *
0x18014ef67  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014ef6c  mov     edx, 137h; void *
0x18014ef71  mov     rcx, [rbp+198h]; this
0x18014ef78  lea     r8, aOnecoreBaseApp_284; "onecore\\base\\appmodel\\StateRepositor"...
0x18014ef7f  mov     r9d, ebx; char *
0x18014ef82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014ef87  mov     rcx, qword ptr [rsp+290h+var_270]
0x18014ef8c  mov     qword ptr [rsp+290h+var_270], r15
0x18014ef91  test    rcx, rcx
0x18014ef94  jz      short loc_18014EF9C
0x18014ef96  call    cs:__imp_SRCacheContext_Close
0x18014ef9c  mov     eax, ebx
0x18014ef9e  jmp     loc_18014F0EF
0x18014efa3  cmp     qword ptr [rsp+290h+var_270], r15
0x18014efa8  setnz   al
0x18014efab  test    al, al
0x18014efad  jnz     short loc_18014EFBB
0x18014efaf  mov     ebx, 80670012h
0x18014efb4  mov     edx, 138h
0x18014efb9  jmp     short loc_18014EF71
0x18014efbb  xor     edx, edx; Val
0x18014efbd  mov     [rsp+290h+var_250], r15
0x18014efc2  mov     r8d, 200h; Size
0x18014efc8  lea     rcx, [rsp+290h+var_248]; void *
0x18014efcd  call    memset_0
0x18014efd2  lea     rax, [rsp+290h+var_248]
0x18014efd7  mov     [rbp+190h+var_48], r15
0x18014efde  mov     rdx, r14; unsigned __int64
0x18014efe1  mov     [rbp+190h+var_38], rax
0x18014efe8  lea     rcx, [rsp+290h+var_250]; this
0x18014efed  mov     [rbp+190h+var_40], 100h
0x18014eff8  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18014effd  mov     ebx, eax
0x18014efff  test    eax, eax
0x18014f001  jns     short loc_18014F03C
0x18014f003  mov     edx, 13Bh; void *
0x18014f008  mov     rcx, [rbp+198h]; this
0x18014f00f  lea     r8, aOnecoreBaseApp_284; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f016  mov     r9d, ebx; char *
0x18014f019  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f01e  mov     rcx, [rsp+290h+var_250]
0x18014f023  mov     [rsp+290h+var_250], r15
0x18014f028  test    rcx, rcx
0x18014f02b  jz      loc_18014EF87
0x18014f031  call    cs:__imp_SRCache_Free
0x18014f037  jmp     loc_18014EF87
0x18014f03c  mov     rdx, [rbp+190h+var_38]
0x18014f043  lea     r9, [rsp+290h+var_260]
0x18014f048  mov     rcx, qword ptr [rsp+290h+var_270]
0x18014f04d  xor     r8d, r8d
0x18014f050  mov     [rsp+290h+var_268], rdi
0x18014f055  mov     [rsp+290h+var_260], r15
0x18014f05a  mov     [rsp+290h+var_258], 1
0x18014f05f  call    cs:__imp_SRCacheContext_OpenSubContext
0x18014f065  lea     rcx, [rsp+290h+var_268]
0x18014f06a  mov     ebx, eax
0x18014f06c  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18014f071  test    ebx, ebx
0x18014f073  jns     short loc_18014F09A
0x18014f075  mov     rcx, [rbp+198h]; this
0x18014f07c  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18014f083  mov     r9d, ebx; char *
0x18014f086  mov     edx, 1B0h; void *
0x18014f08b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014f090  mov     edx, 13Ch
0x18014f095  jmp     loc_18014F008
0x18014f09a  cmp     [rdi], r15
0x18014f09d  lea     rdx, aAppextensionDa; "AppExtension\\Data"
0x18014f0a4  lea     rcx, [rsp+290h+var_270]; this
0x18014f0a9  setnz   al
0x18014f0ac  mov     [rsi], al
0x18014f0ae  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18014f0b3  mov     ebx, eax
0x18014f0b5  test    eax, eax
0x18014f0b7  jns     short loc_18014F0C3
0x18014f0b9  mov     edx, 13Eh
0x18014f0be  jmp     loc_18014F008
0x18014f0c3  mov     rcx, [rsp+290h+var_250]
0x18014f0c8  mov     [rsp+290h+var_250], r15
0x18014f0cd  test    rcx, rcx
0x18014f0d0  jz      short loc_18014F0D8
0x18014f0d2  call    cs:__imp_SRCache_Free
0x18014f0d8  mov     rcx, qword ptr [rsp+290h+var_270]
0x18014f0dd  mov     qword ptr [rsp+290h+var_270], r15
0x18014f0e2  test    rcx, rcx
0x18014f0e5  jz      short loc_18014F0ED
0x18014f0e7  call    cs:__imp_SRCacheContext_Close
0x18014f0ed  xor     eax, eax
0x18014f0ef  mov     rcx, [rbp+190h+var_30]
0x18014f0f6  xor     rcx, rsp; StackCookie
0x18014f0f9  call    __security_check_cookie
0x18014f0fe  mov     rbx, [rsp+290h+arg_10]
0x18014f106  add     rsp, 270h
0x18014f10d  pop     r15
0x18014f10f  pop     r14
0x18014f111  pop     rdi
0x18014f112  pop     rsi
0x18014f113  pop     rbp
0x18014f114  retn
```
