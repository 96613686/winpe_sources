# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ebbd4`
- end: `0x1800ebe11`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `573`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180267cdc`

## callees

- `0x18001a9e0`
- `0x1800472dc`
- `0x180074eb0`
- `0x18007b950`
- `0x1800ebbd4`
- `0x18018f650`
- `0x180190234`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ebd5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800ebd5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ebc92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ebde3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ebc92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ebde3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ebd2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ebdce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ebd2d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ebdce`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ebc37`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ebc37`

## string_xrefs

- `0x1800ebc23`: `PackageExtension\Data`
- `0x1800ebd99`: `PackageExtension\Data`
- `0x1800ebc54`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800ebd78`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x1800ebc74`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageExtension.hpp`
- `0x1800ebd0b`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageExtension\\Data", 0, &v22);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v21);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageExtension.hpp",
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
    v9 = 318;
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
    v14 = 321;
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
    v14 = 322;
    goto LABEL_11;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v14 = 324;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Entity-PackageExtension.hpp",
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
0x1800ebbd4  mov     [rsp-8+arg_10], rbx
0x1800ebbd9  push    rbp
0x1800ebbda  push    rsi
0x1800ebbdb  push    rdi
0x1800ebbdc  push    r14
0x1800ebbde  push    r15
0x1800ebbe0  lea     rbp, [rsp-170h]
0x1800ebbe8  sub     rsp, 270h
0x1800ebbef  mov     rax, cs:__security_cookie
0x1800ebbf6  xor     rax, rsp
0x1800ebbf9  mov     [rbp+190h+var_30], rax
0x1800ebc00  mov     rcx, [rcx]
0x1800ebc03  lea     rax, [rsp+290h+var_270]
0x1800ebc08  mov     rsi, r9
0x1800ebc0b  mov     [rsp+290h+var_268], rax
0x1800ebc10  mov     rdi, r8
0x1800ebc13  mov     [rsp+290h+var_258], 1
0x1800ebc18  mov     r14, rdx
0x1800ebc1b  lea     r9, [rsp+290h+var_260]
0x1800ebc20  xor     r15d, r15d
0x1800ebc23  lea     rdx, aPackageextensi_10; "PackageExtension\\Data"
0x1800ebc2a  xor     r8d, r8d
0x1800ebc2d  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800ebc32  mov     [rsp+290h+var_260], r15
0x1800ebc37  call    cs:__imp_SRCacheContext_Open
0x1800ebc3d  lea     rcx, [rsp+290h+var_268]
0x1800ebc42  mov     ebx, eax
0x1800ebc44  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ebc49  test    ebx, ebx
0x1800ebc4b  jns     short loc_1800EBC9F
0x1800ebc4d  mov     rcx, [rbp+198h]; this
0x1800ebc54  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ebc5b  mov     r9d, ebx; char *
0x1800ebc5e  mov     edx, 18Ch; void *
0x1800ebc63  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebc68  mov     edx, 13Dh; void *
0x1800ebc6d  mov     rcx, [rbp+198h]; this
0x1800ebc74  lea     r8, aOnecoreBaseApp_151; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ebc7b  mov     r9d, ebx; char *
0x1800ebc7e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebc83  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ebc88  mov     qword ptr [rsp+290h+var_270], r15
0x1800ebc8d  test    rcx, rcx
0x1800ebc90  jz      short loc_1800EBC98
0x1800ebc92  call    cs:__imp_SRCacheContext_Close
0x1800ebc98  mov     eax, ebx
0x1800ebc9a  jmp     loc_1800EBDEB
0x1800ebc9f  cmp     qword ptr [rsp+290h+var_270], r15
0x1800ebca4  setnz   al
0x1800ebca7  test    al, al
0x1800ebca9  jnz     short loc_1800EBCB7
0x1800ebcab  mov     ebx, 80670012h
0x1800ebcb0  mov     edx, 13Eh
0x1800ebcb5  jmp     short loc_1800EBC6D
0x1800ebcb7  xor     edx, edx; Val
0x1800ebcb9  mov     [rsp+290h+var_250], r15
0x1800ebcbe  mov     r8d, 200h; Size
0x1800ebcc4  lea     rcx, [rsp+290h+var_248]; void *
0x1800ebcc9  call    memset_0
0x1800ebcce  lea     rax, [rsp+290h+var_248]
0x1800ebcd3  mov     [rbp+190h+var_48], r15
0x1800ebcda  mov     rdx, r14; unsigned __int64
0x1800ebcdd  mov     [rbp+190h+var_38], rax
0x1800ebce4  lea     rcx, [rsp+290h+var_250]; this
0x1800ebce9  mov     [rbp+190h+var_40], 100h
0x1800ebcf4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800ebcf9  mov     ebx, eax
0x1800ebcfb  test    eax, eax
0x1800ebcfd  jns     short loc_1800EBD38
0x1800ebcff  mov     edx, 141h; void *
0x1800ebd04  mov     rcx, [rbp+198h]; this
0x1800ebd0b  lea     r8, aOnecoreBaseApp_151; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ebd12  mov     r9d, ebx; char *
0x1800ebd15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebd1a  mov     rcx, [rsp+290h+var_250]
0x1800ebd1f  mov     [rsp+290h+var_250], r15
0x1800ebd24  test    rcx, rcx
0x1800ebd27  jz      loc_1800EBC83
0x1800ebd2d  call    cs:__imp_SRCache_Free
0x1800ebd33  jmp     loc_1800EBC83
0x1800ebd38  mov     rdx, [rbp+190h+var_38]
0x1800ebd3f  lea     r9, [rsp+290h+var_260]
0x1800ebd44  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ebd49  xor     r8d, r8d
0x1800ebd4c  mov     [rsp+290h+var_268], rdi
0x1800ebd51  mov     [rsp+290h+var_260], r15
0x1800ebd56  mov     [rsp+290h+var_258], 1
0x1800ebd5b  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800ebd61  lea     rcx, [rsp+290h+var_268]
0x1800ebd66  mov     ebx, eax
0x1800ebd68  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800ebd6d  test    ebx, ebx
0x1800ebd6f  jns     short loc_1800EBD96
0x1800ebd71  mov     rcx, [rbp+198h]; this
0x1800ebd78  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\StateRepositor"...
0x1800ebd7f  mov     r9d, ebx; char *
0x1800ebd82  mov     edx, 1B0h; void *
0x1800ebd87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ebd8c  mov     edx, 142h
0x1800ebd91  jmp     loc_1800EBD04
0x1800ebd96  cmp     [rdi], r15
0x1800ebd99  lea     rdx, aPackageextensi_10; "PackageExtension\\Data"
0x1800ebda0  lea     rcx, [rsp+290h+var_270]; this
0x1800ebda5  setnz   al
0x1800ebda8  mov     [rsi], al
0x1800ebdaa  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800ebdaf  mov     ebx, eax
0x1800ebdb1  test    eax, eax
0x1800ebdb3  jns     short loc_1800EBDBF
0x1800ebdb5  mov     edx, 144h
0x1800ebdba  jmp     loc_1800EBD04
0x1800ebdbf  mov     rcx, [rsp+290h+var_250]
0x1800ebdc4  mov     [rsp+290h+var_250], r15
0x1800ebdc9  test    rcx, rcx
0x1800ebdcc  jz      short loc_1800EBDD4
0x1800ebdce  call    cs:__imp_SRCache_Free
0x1800ebdd4  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800ebdd9  mov     qword ptr [rsp+290h+var_270], r15
0x1800ebdde  test    rcx, rcx
0x1800ebde1  jz      short loc_1800EBDE9
0x1800ebde3  call    cs:__imp_SRCacheContext_Close
0x1800ebde9  xor     eax, eax
0x1800ebdeb  mov     rcx, [rbp+190h+var_30]
0x1800ebdf2  xor     rcx, rsp; StackCookie
0x1800ebdf5  call    __security_check_cookie
0x1800ebdfa  mov     rbx, [rsp+290h+arg_10]
0x1800ebe02  add     rsp, 270h
0x1800ebe09  pop     r15
0x1800ebe0b  pop     r14
0x1800ebe0d  pop     rdi
0x1800ebe0e  pop     rsi
0x1800ebe0f  pop     rbp
0x1800ebe10  retn
```
