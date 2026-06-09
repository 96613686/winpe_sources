# StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180017a00`
- end: `0x180017c94`
- name: `?Open@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001749c`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180017a00`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017ac8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017c66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017ac8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017c66`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ba6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017c51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017ba6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180017c51`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017a6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180017a6b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017bdc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180017bdc`

## string_xrefs

- `0x180017b46`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180017a8a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180017bfb`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180017aaa`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017b84`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017a55`: `PkgExtension\Data`
- `0x180017c1c`: `PkgExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PkgExtension\\Data", 0, &v24);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>((__int64 **)v23);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v17[0]);
    v9 = 311;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
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
    v9 = 312;
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
    v13 = 315;
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
    v13 = 316;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v17,
         L"PkgExtension\\Data");
  if ( v8 < 0 )
  {
    v13 = 318;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
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
0x180017a00  mov     [rsp-8+arg_10], rbx
0x180017a05  push    rbp
0x180017a06  push    rsi
0x180017a07  push    rdi
0x180017a08  push    r14
0x180017a0a  push    r15
0x180017a0c  lea     rbp, [rsp-180h]
0x180017a14  sub     rsp, 280h
0x180017a1b  mov     rax, cs:__security_cookie
0x180017a22  xor     rax, rsp
0x180017a25  mov     [rbp+1A0h+var_28], rax
0x180017a2c  mov     rcx, [rcx]
0x180017a2f  lea     rax, [rsp+2A0h+var_280]
0x180017a34  mov     rsi, r9
0x180017a37  mov     qword ptr [rbp+1A0h+var_50], rax
0x180017a3e  mov     rdi, r8
0x180017a41  mov     [rbp+1A0h+var_40], 1
0x180017a48  mov     r14, rdx
0x180017a4b  lea     r9, [rbp+1A0h+var_48]
0x180017a52  xor     r15d, r15d
0x180017a55  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x180017a5c  xor     r8d, r8d
0x180017a5f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180017a64  mov     [rbp+1A0h+var_48], r15
0x180017a6b  call    cs:__imp_SRCacheContext_Open
0x180017a71  lea     rcx, [rbp+1A0h+var_50]
0x180017a78  mov     ebx, eax
0x180017a7a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017a7f  test    ebx, ebx
0x180017a81  jns     short loc_180017AD5
0x180017a83  mov     rcx, [rbp+1A8h]; this
0x180017a8a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180017a91  mov     r9d, ebx; char *
0x180017a94  mov     edx, 18Ch; void *
0x180017a99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017a9e  mov     edx, 137h; void *
0x180017aa3  mov     rcx, [rbp+1A8h]; this
0x180017aaa  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017ab1  mov     r9d, ebx; char *
0x180017ab4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ab9  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180017abe  mov     qword ptr [rsp+2A0h+var_280], r15
0x180017ac3  test    rcx, rcx
0x180017ac6  jz      short loc_180017ACE
0x180017ac8  call    cs:__imp_SRCacheContext_Close
0x180017ace  mov     eax, ebx
0x180017ad0  jmp     loc_180017C6E
0x180017ad5  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180017ada  setnz   al
0x180017add  test    al, al
0x180017adf  jnz     short loc_180017AED
0x180017ae1  mov     ebx, 80670012h
0x180017ae6  mov     edx, 138h
0x180017aeb  jmp     short loc_180017AA3
0x180017aed  xor     edx, edx; Val
0x180017aef  mov     [rsp+2A0h+var_270], r15
0x180017af4  mov     r8d, 200h; Size
0x180017afa  lea     rcx, [rsp+2A0h+var_268]; void *
0x180017aff  call    memset_0
0x180017b04  mov     r9d, 10h
0x180017b0a  mov     [rbp+1A0h+var_68], r15
0x180017b11  lea     rax, [rsp+2A0h+var_268]
0x180017b16  mov     [rbp+1A0h+var_60], 100h
0x180017b21  lea     rdx, [rbp+1A0h+var_50]
0x180017b28  mov     [rbp+1A0h+var_58], rax
0x180017b2f  mov     rcx, r14
0x180017b32  lea     r8d, [r9+1]
0x180017b36  call    _o__ui64tow_s_0
0x180017b3b  test    eax, eax
0x180017b3d  jz      short loc_180017B61
0x180017b3f  mov     rcx, [rbp+1A8h]; this
0x180017b46  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180017b4d  mov     ebx, 8000FFFFh
0x180017b52  mov     edx, 166h; void *
0x180017b57  mov     r9d, ebx; char *
0x180017b5a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b5f  jmp     short loc_180017B78
0x180017b61  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180017b68  lea     rcx, [rsp+2A0h+var_270]; this
0x180017b6d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180017b72  mov     ebx, eax
0x180017b74  test    eax, eax
0x180017b76  jns     short loc_180017BB1
0x180017b78  mov     edx, 13Bh; void *
0x180017b7d  mov     rcx, [rbp+1A8h]; this
0x180017b84  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x180017b8b  mov     r9d, ebx; char *
0x180017b8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017b93  mov     rcx, [rsp+2A0h+var_270]
0x180017b98  mov     [rsp+2A0h+var_270], r15
0x180017b9d  test    rcx, rcx
0x180017ba0  jz      loc_180017AB9
0x180017ba6  call    cs:__imp_SRCache_Free
0x180017bac  jmp     loc_180017AB9
0x180017bb1  mov     rdx, [rbp+1A0h+var_58]
0x180017bb8  lea     r9, [rbp+1A0h+var_48]
0x180017bbf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180017bc4  xor     r8d, r8d
0x180017bc7  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180017bce  mov     [rbp+1A0h+var_48], r15
0x180017bd5  mov     [rbp+1A0h+var_40], 1
0x180017bdc  call    cs:__imp_SRCacheContext_OpenSubContext
0x180017be2  lea     rcx, [rbp+1A0h+var_50]
0x180017be9  mov     ebx, eax
0x180017beb  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180017bf0  test    ebx, ebx
0x180017bf2  jns     short loc_180017C19
0x180017bf4  mov     rcx, [rbp+1A8h]; this
0x180017bfb  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180017c02  mov     r9d, ebx; char *
0x180017c05  mov     edx, 1B0h; void *
0x180017c0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c0f  mov     edx, 13Ch
0x180017c14  jmp     loc_180017B7D
0x180017c19  cmp     [rdi], r15
0x180017c1c  lea     rdx, aPkgextensionDa; "PkgExtension\\Data"
0x180017c23  lea     rcx, [rsp+2A0h+var_280]; this
0x180017c28  setnz   al
0x180017c2b  mov     [rsi], al
0x180017c2d  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180017c32  mov     ebx, eax
0x180017c34  test    eax, eax
0x180017c36  jns     short loc_180017C42
0x180017c38  mov     edx, 13Eh
0x180017c3d  jmp     loc_180017B7D
0x180017c42  mov     rcx, [rsp+2A0h+var_270]
0x180017c47  mov     [rsp+2A0h+var_270], r15
0x180017c4c  test    rcx, rcx
0x180017c4f  jz      short loc_180017C57
0x180017c51  call    cs:__imp_SRCache_Free
0x180017c57  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180017c5c  mov     qword ptr [rsp+2A0h+var_280], r15
0x180017c61  test    rcx, rcx
0x180017c64  jz      short loc_180017C6C
0x180017c66  call    cs:__imp_SRCacheContext_Close
0x180017c6c  xor     eax, eax
0x180017c6e  mov     rcx, [rbp+1A0h+var_28]
0x180017c75  xor     rcx, rsp; StackCookie
0x180017c78  call    __security_check_cookie
0x180017c7d  mov     rbx, [rsp+2A0h+arg_10]
0x180017c85  add     rsp, 280h
0x180017c8c  pop     r15
0x180017c8e  pop     r14
0x180017c90  pop     rdi
0x180017c91  pop     rsi
0x180017c92  pop     rbp
0x180017c93  retn
```
