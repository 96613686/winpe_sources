# StateRepository::Cache::Entity::OptionalBundle_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18027476c`
- end: `0x1802749a9`
- name: `?Open@OptionalBundle_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180274564`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18018f650`
- `0x180190234`
- `0x18027476c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802748f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1802748f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027482a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027497b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027482a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18027497b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802748c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180274966`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802748c5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180274966`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802747cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1802747cf`

## string_xrefs

- `0x1802747ec`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x180274910`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18027480c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-OptionalBundle.hpp`
- `0x1802748a3`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-OptionalBundle.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::OptionalBundle_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"OptionalBundle\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 131;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-OptionalBundle.hpp",
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
    v9 = 132;
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
    v14 = 135;
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
    v14 = 136;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"OptionalBundle\\Data");
  if ( v8 < 0 )
  {
    v14 = 138;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-OptionalBundle.hpp",
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
0x18027476c  mov     [rsp-8+arg_10], rbx
0x180274771  push    rbp
0x180274772  push    rsi
0x180274773  push    rdi
0x180274774  push    r14
0x180274776  push    r15
0x180274778  lea     rbp, [rsp-170h]
0x180274780  sub     rsp, 270h
0x180274787  mov     rax, cs:__security_cookie
0x18027478e  xor     rax, rsp
0x180274791  mov     [rbp+190h+var_30], rax
0x180274798  mov     rcx, [rcx]
0x18027479b  lea     rax, [rsp+290h+var_270]
0x1802747a0  mov     rsi, r9
0x1802747a3  mov     [rsp+290h+var_268], rax
0x1802747a8  mov     rdi, r8
0x1802747ab  mov     [rsp+290h+var_258], 1
0x1802747b0  mov     r14, rdx
0x1802747b3  lea     r9, [rsp+290h+var_260]
0x1802747b8  xor     r15d, r15d
0x1802747bb  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x1802747c2  xor     r8d, r8d
0x1802747c5  mov     qword ptr [rsp+290h+var_270], r15; int
0x1802747ca  mov     [rsp+290h+var_260], r15
0x1802747cf  call    cs:__imp_SRCacheContext_Open
0x1802747d5  lea     rcx, [rsp+290h+var_268]
0x1802747da  mov     ebx, eax
0x1802747dc  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1802747e1  test    ebx, ebx
0x1802747e3  jns     short loc_180274837
0x1802747e5  mov     rcx, [rbp+198h]; this
0x1802747ec  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1802747f3  mov     r9d, ebx; char *
0x1802747f6  mov     edx, 18Ch; void *
0x1802747fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274800  mov     edx, 83h; void *
0x180274805  mov     rcx, [rbp+198h]; this
0x18027480c  lea     r8, aOnecoreBaseApp_447; "onecore\\base\\appmodel\\StateRepositor"...
0x180274813  mov     r9d, ebx; char *
0x180274816  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027481b  mov     rcx, qword ptr [rsp+290h+var_270]
0x180274820  mov     qword ptr [rsp+290h+var_270], r15
0x180274825  test    rcx, rcx
0x180274828  jz      short loc_180274830
0x18027482a  call    cs:__imp_SRCacheContext_Close
0x180274830  mov     eax, ebx
0x180274832  jmp     loc_180274983
0x180274837  cmp     qword ptr [rsp+290h+var_270], r15
0x18027483c  setnz   al
0x18027483f  test    al, al
0x180274841  jnz     short loc_18027484F
0x180274843  mov     ebx, 80670012h
0x180274848  mov     edx, 84h
0x18027484d  jmp     short loc_180274805
0x18027484f  xor     edx, edx; Val
0x180274851  mov     [rsp+290h+var_250], r15
0x180274856  mov     r8d, 200h; Size
0x18027485c  lea     rcx, [rsp+290h+var_248]; void *
0x180274861  call    memset_0
0x180274866  lea     rax, [rsp+290h+var_248]
0x18027486b  mov     [rbp+190h+var_48], r15
0x180274872  mov     rdx, r14; unsigned __int64
0x180274875  mov     [rbp+190h+var_38], rax
0x18027487c  lea     rcx, [rsp+290h+var_250]; this
0x180274881  mov     [rbp+190h+var_40], 100h
0x18027488c  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180274891  mov     ebx, eax
0x180274893  test    eax, eax
0x180274895  jns     short loc_1802748D0
0x180274897  mov     edx, 87h; void *
0x18027489c  mov     rcx, [rbp+198h]; this
0x1802748a3  lea     r8, aOnecoreBaseApp_447; "onecore\\base\\appmodel\\StateRepositor"...
0x1802748aa  mov     r9d, ebx; char *
0x1802748ad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802748b2  mov     rcx, [rsp+290h+var_250]
0x1802748b7  mov     [rsp+290h+var_250], r15
0x1802748bc  test    rcx, rcx
0x1802748bf  jz      loc_18027481B
0x1802748c5  call    cs:__imp_SRCache_Free
0x1802748cb  jmp     loc_18027481B
0x1802748d0  mov     rdx, [rbp+190h+var_38]
0x1802748d7  lea     r9, [rsp+290h+var_260]
0x1802748dc  mov     rcx, qword ptr [rsp+290h+var_270]
0x1802748e1  xor     r8d, r8d
0x1802748e4  mov     [rsp+290h+var_268], rdi
0x1802748e9  mov     [rsp+290h+var_260], r15
0x1802748ee  mov     [rsp+290h+var_258], 1
0x1802748f3  call    cs:__imp_SRCacheContext_OpenSubContext
0x1802748f9  lea     rcx, [rsp+290h+var_268]
0x1802748fe  mov     ebx, eax
0x180274900  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180274905  test    ebx, ebx
0x180274907  jns     short loc_18027492E
0x180274909  mov     rcx, [rbp+198h]; this
0x180274910  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x180274917  mov     r9d, ebx; char *
0x18027491a  mov     edx, 1B0h; void *
0x18027491f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180274924  mov     edx, 88h
0x180274929  jmp     loc_18027489C
0x18027492e  cmp     [rdi], r15
0x180274931  lea     rdx, aOptionalbundle_0; "OptionalBundle\\Data"
0x180274938  lea     rcx, [rsp+290h+var_270]; this
0x18027493d  setnz   al
0x180274940  mov     [rsi], al
0x180274942  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180274947  mov     ebx, eax
0x180274949  test    eax, eax
0x18027494b  jns     short loc_180274957
0x18027494d  mov     edx, 8Ah
0x180274952  jmp     loc_18027489C
0x180274957  mov     rcx, [rsp+290h+var_250]
0x18027495c  mov     [rsp+290h+var_250], r15
0x180274961  test    rcx, rcx
0x180274964  jz      short loc_18027496C
0x180274966  call    cs:__imp_SRCache_Free
0x18027496c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180274971  mov     qword ptr [rsp+290h+var_270], r15
0x180274976  test    rcx, rcx
0x180274979  jz      short loc_180274981
0x18027497b  call    cs:__imp_SRCacheContext_Close
0x180274981  xor     eax, eax
0x180274983  mov     rcx, [rbp+190h+var_30]
0x18027498a  xor     rcx, rsp; StackCookie
0x18027498d  call    __security_check_cookie
0x180274992  mov     rbx, [rsp+290h+arg_10]
0x18027499a  add     rsp, 270h
0x1802749a1  pop     r15
0x1802749a3  pop     r14
0x1802749a5  pop     rdi
0x1802749a6  pop     rsi
0x1802749a7  pop     rbp
0x1802749a8  retn
```
