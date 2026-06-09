# StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180017764`
- end: `0x1800179f8`
- name: `?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800172f4`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180017764`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001782c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800179ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001782c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800179ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001790a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800179b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001790a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800179b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800177cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800177cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017940`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017940`

## string_xrefs

- `0x1800178aa`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x1800177ee`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001795f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001780e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`
- `0x1800178e8`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`
- `0x1800177b9`: `PackageExtension\Data`
- `0x180017980`: `PackageExtension\Data`

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
  __int64 v10; // rcx
  bool v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v20; // [rsp+238h] [rbp+138h]
  __int64 v21; // [rsp+240h] [rbp+140h]
  _BYTE *v22; // [rsp+248h] [rbp+148h]
  unsigned __int16 v23[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v24; // [rsp+258h] [rbp+158h] BYREF
  char v25; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v23 = v17;
  v25 = 1;
  *(_QWORD *)v17 = 0;
  v24 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageExtension\\Data", 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v9 = 317;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
LABEL_4:
    v10 = *(_QWORD *)v17;
    *(_QWORD *)v17 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v17 )
  {
    v8 = -2140733422;
    v9 = 318;
    goto LABEL_3;
  }
  v18 = 0;
  memset_0(v19, 0, sizeof(v19));
  v20 = 0;
  v21 = 256;
  v22 = v19;
  if ( (unsigned int)o__ui64tow_s_0(a2, v23, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v17[0]);
LABEL_12:
    v13 = 321;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v18, v23, v12);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v23 = a3;
  v24 = 0;
  v25 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v17, v22, 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v13 = 322;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"PackageExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 324;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v14 = v18;
    v18 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_4;
  }
  v15 = v18;
  v18 = 0;
  if ( v15 )
    SRCache_Free(v15);
  v16 = *(_QWORD *)v17;
  *(_QWORD *)v17 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return 0;
}

```

## disassembly

```asm
0x180017764  mov     [rsp-8+arg_10], rbx
0x180017769  push    rbp
0x18001776a  push    rsi
0x18001776b  push    rdi
0x18001776c  push    r14
0x18001776e  push    r15
0x180017770  lea     rbp, [rsp-180h]
0x180017778  sub     rsp, 280h
0x18001777f  mov     rax, cs:__security_cookie
0x180017786  xor     rax, rsp
0x180017789  mov     [rbp+1A0h+var_28], rax
0x180017790  mov     rcx, [rcx]
0x180017793  lea     rax, [rsp+2A0h+var_280]
0x180017798  mov     rsi, r9
0x18001779b  mov     qword ptr [rbp+1A0h+var_50], rax
0x1800177a2  mov     rdi, r8
0x1800177a5  mov     [rbp+1A0h+var_40], 1
0x1800177ac  mov     r14, rdx
0x1800177af  lea     r9, [rbp+1A0h+var_48]
0x1800177b6  xor     r15d, r15d
0x1800177b9  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x1800177c0  xor     r8d, r8d
0x1800177c3  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800177c8  mov     [rbp+1A0h+var_48], r15
0x1800177cf  call    cs:__imp_SRCacheContext_Open
0x1800177d5  lea     rcx, [rbp+1A0h+var_50]
0x1800177dc  mov     ebx, eax
0x1800177de  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800177e3  test    ebx, ebx
0x1800177e5  jns     short loc_180017839
0x1800177e7  mov     rcx, [rbp+1A8h]; this
0x1800177ee  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800177f5  mov     r9d, ebx; char *
0x1800177f8  mov     edx, 18Ch; void *
0x1800177fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017802  mov     edx, 13Dh; void *
0x180017807  mov     rcx, [rbp+1A8h]; this
0x18001780e  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x180017815  mov     r9d, ebx; char *
0x180017818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001781d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180017822  mov     qword ptr [rsp+2A0h+var_280], r15
0x180017827  test    rcx, rcx
0x18001782a  jz      short loc_180017832
0x18001782c  call    cs:__imp_SRCacheContext_Close
0x180017832  mov     eax, ebx
0x180017834  jmp     loc_1800179D2
0x180017839  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18001783e  setnz   al
0x180017841  test    al, al
0x180017843  jnz     short loc_180017851
0x180017845  mov     ebx, 80670012h
0x18001784a  mov     edx, 13Eh
0x18001784f  jmp     short loc_180017807
0x180017851  xor     edx, edx; Val
0x180017853  mov     [rsp+2A0h+var_270], r15
0x180017858  mov     r8d, 200h; Size
0x18001785e  lea     rcx, [rsp+2A0h+var_268]; void *
0x180017863  call    memset_0
0x180017868  mov     r9d, 10h
0x18001786e  mov     [rbp+1A0h+var_68], r15
0x180017875  lea     rax, [rsp+2A0h+var_268]
0x18001787a  mov     [rbp+1A0h+var_60], 100h
0x180017885  lea     rdx, [rbp+1A0h+var_50]
0x18001788c  mov     [rbp+1A0h+var_58], rax
0x180017893  mov     rcx, r14
0x180017896  lea     r8d, [r9+1]
0x18001789a  call    _o__ui64tow_s_0
0x18001789f  test    eax, eax
0x1800178a1  jz      short loc_1800178C5
0x1800178a3  mov     rcx, [rbp+1A8h]; this
0x1800178aa  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x1800178b1  mov     ebx, 8000FFFFh
0x1800178b6  mov     edx, 166h; void *
0x1800178bb  mov     r9d, ebx; char *
0x1800178be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178c3  jmp     short loc_1800178DC
0x1800178c5  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800178cc  lea     rcx, [rsp+2A0h+var_270]; this
0x1800178d1  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800178d6  mov     ebx, eax
0x1800178d8  test    eax, eax
0x1800178da  jns     short loc_180017915
0x1800178dc  mov     edx, 141h; void *
0x1800178e1  mov     rcx, [rbp+1A8h]; this
0x1800178e8  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x1800178ef  mov     r9d, ebx; char *
0x1800178f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800178f7  mov     rcx, [rsp+2A0h+var_270]
0x1800178fc  mov     [rsp+2A0h+var_270], r15
0x180017901  test    rcx, rcx
0x180017904  jz      loc_18001781D
0x18001790a  call    cs:__imp_SRCache_Free
0x180017910  jmp     loc_18001781D
0x180017915  mov     rdx, [rbp+1A0h+var_58]
0x18001791c  lea     r9, [rbp+1A0h+var_48]
0x180017923  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180017928  xor     r8d, r8d
0x18001792b  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180017932  mov     [rbp+1A0h+var_48], r15
0x180017939  mov     [rbp+1A0h+var_40], 1
0x180017940  call    cs:__imp_SRCacheContext_OpenSubContext
0x180017946  lea     rcx, [rbp+1A0h+var_50]
0x18001794d  mov     ebx, eax
0x18001794f  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017954  test    ebx, ebx
0x180017956  jns     short loc_18001797D
0x180017958  mov     rcx, [rbp+1A8h]; this
0x18001795f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180017966  mov     r9d, ebx; char *
0x180017969  mov     edx, 1B0h; void *
0x18001796e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017973  mov     edx, 142h
0x180017978  jmp     loc_1800178E1
0x18001797d  cmp     [rdi], r15
0x180017980  lea     rdx, aPackageextensi; "PackageExtension\\Data"
0x180017987  lea     rcx, [rsp+2A0h+var_280]; this
0x18001798c  setnz   al
0x18001798f  mov     [rsi], al
0x180017991  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180017996  mov     ebx, eax
0x180017998  test    eax, eax
0x18001799a  jns     short loc_1800179A6
0x18001799c  mov     edx, 144h
0x1800179a1  jmp     loc_1800178E1
0x1800179a6  mov     rcx, [rsp+2A0h+var_270]
0x1800179ab  mov     [rsp+2A0h+var_270], r15
0x1800179b0  test    rcx, rcx
0x1800179b3  jz      short loc_1800179BB
0x1800179b5  call    cs:__imp_SRCache_Free
0x1800179bb  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800179c0  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800179c5  test    rcx, rcx
0x1800179c8  jz      short loc_1800179D0
0x1800179ca  call    cs:__imp_SRCacheContext_Close
0x1800179d0  xor     eax, eax
0x1800179d2  mov     rcx, [rbp+1A0h+var_28]
0x1800179d9  xor     rcx, rsp; StackCookie
0x1800179dc  call    __security_check_cookie
0x1800179e1  mov     rbx, [rsp+2A0h+arg_10]
0x1800179e9  add     rsp, 280h
0x1800179f0  pop     r15
0x1800179f2  pop     r14
0x1800179f4  pop     rdi
0x1800179f5  pop     rsi
0x1800179f6  pop     rbp
0x1800179f7  retn
```
