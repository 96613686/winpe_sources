# StateRepository::Cache::Entity::PackageProperty_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18016ced0`
- end: `0x18016d10d`
- name: `?Open@PackageProperty_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180271500`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x18016ced0`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18016d057`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18016d057`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016cf8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016d0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016cf8e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18016d0df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016d029`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016d0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016d029`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18016d0ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016cf33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18016cf33`

## string_xrefs

- `0x18016cf50`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016d074`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18016cf70`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageProperty.hpp`
- `0x18016d007`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageProperty.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageProperty_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageProperty\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 225;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageProperty.hpp",
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
    v9 = 226;
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
    v14 = 229;
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
    v14 = 230;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"PackageProperty\\Data");
  if ( v8 < 0 )
  {
    v14 = 232;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageProperty.hpp",
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
0x18016ced0  mov     [rsp-8+arg_10], rbx
0x18016ced5  push    rbp
0x18016ced6  push    rsi
0x18016ced7  push    rdi
0x18016ced8  push    r14
0x18016ceda  push    r15
0x18016cedc  lea     rbp, [rsp-170h]
0x18016cee4  sub     rsp, 270h
0x18016ceeb  mov     rax, cs:__security_cookie
0x18016cef2  xor     rax, rsp
0x18016cef5  mov     [rbp+190h+var_30], rax
0x18016cefc  mov     rcx, [rcx]
0x18016ceff  lea     rax, [rsp+290h+var_270]
0x18016cf04  mov     rsi, r9
0x18016cf07  mov     [rsp+290h+var_268], rax
0x18016cf0c  mov     rdi, r8
0x18016cf0f  mov     [rsp+290h+var_258], 1
0x18016cf14  mov     r14, rdx
0x18016cf17  lea     r9, [rsp+290h+var_260]
0x18016cf1c  xor     r15d, r15d
0x18016cf1f  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x18016cf26  xor     r8d, r8d
0x18016cf29  mov     qword ptr [rsp+290h+var_270], r15; int
0x18016cf2e  mov     [rsp+290h+var_260], r15
0x18016cf33  call    cs:__imp_SRCacheContext_Open
0x18016cf39  lea     rcx, [rsp+290h+var_268]
0x18016cf3e  mov     ebx, eax
0x18016cf40  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016cf45  test    ebx, ebx
0x18016cf47  jns     short loc_18016CF9B
0x18016cf49  mov     rcx, [rbp+198h]; this
0x18016cf50  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016cf57  mov     r9d, ebx; char *
0x18016cf5a  mov     edx, 18Ch; void *
0x18016cf5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cf64  mov     edx, 0E1h; void *
0x18016cf69  mov     rcx, [rbp+198h]; this
0x18016cf70  lea     r8, aOnecoreBaseApp_101; "onecore\\base\\appmodel\\StateRepositor"...
0x18016cf77  mov     r9d, ebx; char *
0x18016cf7a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016cf7f  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016cf84  mov     qword ptr [rsp+290h+var_270], r15
0x18016cf89  test    rcx, rcx
0x18016cf8c  jz      short loc_18016CF94
0x18016cf8e  call    cs:__imp_SRCacheContext_Close
0x18016cf94  mov     eax, ebx
0x18016cf96  jmp     loc_18016D0E7
0x18016cf9b  cmp     qword ptr [rsp+290h+var_270], r15
0x18016cfa0  setnz   al
0x18016cfa3  test    al, al
0x18016cfa5  jnz     short loc_18016CFB3
0x18016cfa7  mov     ebx, 80670012h
0x18016cfac  mov     edx, 0E2h
0x18016cfb1  jmp     short loc_18016CF69
0x18016cfb3  xor     edx, edx; Val
0x18016cfb5  mov     [rsp+290h+var_250], r15
0x18016cfba  mov     r8d, 200h; Size
0x18016cfc0  lea     rcx, [rsp+290h+var_248]; void *
0x18016cfc5  call    memset_0
0x18016cfca  lea     rax, [rsp+290h+var_248]
0x18016cfcf  mov     [rbp+190h+var_48], r15
0x18016cfd6  mov     rdx, r14; unsigned __int64
0x18016cfd9  mov     [rbp+190h+var_38], rax
0x18016cfe0  lea     rcx, [rsp+290h+var_250]; this
0x18016cfe5  mov     [rbp+190h+var_40], 100h
0x18016cff0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18016cff5  mov     ebx, eax
0x18016cff7  test    eax, eax
0x18016cff9  jns     short loc_18016D034
0x18016cffb  mov     edx, 0E5h; void *
0x18016d000  mov     rcx, [rbp+198h]; this
0x18016d007  lea     r8, aOnecoreBaseApp_101; "onecore\\base\\appmodel\\StateRepositor"...
0x18016d00e  mov     r9d, ebx; char *
0x18016d011  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016d016  mov     rcx, [rsp+290h+var_250]
0x18016d01b  mov     [rsp+290h+var_250], r15
0x18016d020  test    rcx, rcx
0x18016d023  jz      loc_18016CF7F
0x18016d029  call    cs:__imp_SRCache_Free
0x18016d02f  jmp     loc_18016CF7F
0x18016d034  mov     rdx, [rbp+190h+var_38]
0x18016d03b  lea     r9, [rsp+290h+var_260]
0x18016d040  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016d045  xor     r8d, r8d
0x18016d048  mov     [rsp+290h+var_268], rdi
0x18016d04d  mov     [rsp+290h+var_260], r15
0x18016d052  mov     [rsp+290h+var_258], 1
0x18016d057  call    cs:__imp_SRCacheContext_OpenSubContext
0x18016d05d  lea     rcx, [rsp+290h+var_268]
0x18016d062  mov     ebx, eax
0x18016d064  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18016d069  test    ebx, ebx
0x18016d06b  jns     short loc_18016D092
0x18016d06d  mov     rcx, [rbp+198h]; this
0x18016d074  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x18016d07b  mov     r9d, ebx; char *
0x18016d07e  mov     edx, 1B0h; void *
0x18016d083  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016d088  mov     edx, 0E6h
0x18016d08d  jmp     loc_18016D000
0x18016d092  cmp     [rdi], r15
0x18016d095  lea     rdx, aPackagepropert_7; "PackageProperty\\Data"
0x18016d09c  lea     rcx, [rsp+290h+var_270]; this
0x18016d0a1  setnz   al
0x18016d0a4  mov     [rsi], al
0x18016d0a6  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18016d0ab  mov     ebx, eax
0x18016d0ad  test    eax, eax
0x18016d0af  jns     short loc_18016D0BB
0x18016d0b1  mov     edx, 0E8h
0x18016d0b6  jmp     loc_18016D000
0x18016d0bb  mov     rcx, [rsp+290h+var_250]
0x18016d0c0  mov     [rsp+290h+var_250], r15
0x18016d0c5  test    rcx, rcx
0x18016d0c8  jz      short loc_18016D0D0
0x18016d0ca  call    cs:__imp_SRCache_Free
0x18016d0d0  mov     rcx, qword ptr [rsp+290h+var_270]
0x18016d0d5  mov     qword ptr [rsp+290h+var_270], r15
0x18016d0da  test    rcx, rcx
0x18016d0dd  jz      short loc_18016D0E5
0x18016d0df  call    cs:__imp_SRCacheContext_Close
0x18016d0e5  xor     eax, eax
0x18016d0e7  mov     rcx, [rbp+190h+var_30]
0x18016d0ee  xor     rcx, rsp; StackCookie
0x18016d0f1  call    __security_check_cookie
0x18016d0f6  mov     rbx, [rsp+290h+arg_10]
0x18016d0fe  add     rsp, 270h
0x18016d105  pop     r15
0x18016d107  pop     r14
0x18016d109  pop     rdi
0x18016d10a  pop     rsi
0x18016d10b  pop     rbp
0x18016d10c  retn
```
