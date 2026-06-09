# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800144e8`
- end: `0x18001477c`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800130b0`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x1800144e8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800145b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001474e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800145b0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001474e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001468e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014739`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001468e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014739`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180014553`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800146c4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x1800146c4`

## string_xrefs

- `0x18001462e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180014572`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x1800146e3`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180014592`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x18001466c`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
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
  int v16[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v18[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+238h] [rbp+138h]
  __int64 v20; // [rsp+240h] [rbp+140h]
  _BYTE *v21; // [rsp+248h] [rbp+148h]
  unsigned __int16 v22[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h] BYREF
  char v24; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v22 = v16;
  v24 = 1;
  *(_QWORD *)v16 = 0;
  v23 = 0;
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 267;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
    v9 = 268;
    goto LABEL_3;
  }
  v17 = 0;
  memset_0(v18, 0, sizeof(v18));
  v19 = 0;
  v20 = 256;
  v21 = v18;
  if ( (unsigned int)o__ui64tow_s_0(a2, v22, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v16[0]);
LABEL_12:
    v12 = 271;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v17, v22);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v22 = a3;
  v23 = 0;
  v24 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v16, v21, 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v12 = 272;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"User\\Data");
  if ( v8 < 0 )
  {
    v12 = 274;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v13 = v17;
    v17 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_4;
  }
  v14 = v17;
  v17 = 0;
  if ( v14 )
    SRCache_Free();
  v15 = *(_QWORD *)v16;
  *(_QWORD *)v16 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x1800144e8  mov     [rsp-8+arg_10], rbx
0x1800144ed  push    rbp
0x1800144ee  push    rsi
0x1800144ef  push    rdi
0x1800144f0  push    r14
0x1800144f2  push    r15
0x1800144f4  lea     rbp, [rsp-180h]
0x1800144fc  sub     rsp, 280h
0x180014503  mov     rax, cs:__security_cookie
0x18001450a  xor     rax, rsp
0x18001450d  mov     [rbp+1A0h+var_28], rax
0x180014514  mov     rcx, [rcx]
0x180014517  lea     rax, [rsp+2A0h+var_280]
0x18001451c  mov     rsi, r9
0x18001451f  mov     qword ptr [rbp+1A0h+var_50], rax
0x180014526  mov     rdi, r8
0x180014529  mov     [rbp+1A0h+var_40], 1
0x180014530  mov     r14, rdx
0x180014533  lea     r9, [rbp+1A0h+var_48]
0x18001453a  xor     r15d, r15d
0x18001453d  lea     rdx, aUserData; "User\\Data"
0x180014544  xor     r8d, r8d
0x180014547  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x18001454c  mov     [rbp+1A0h+var_48], r15
0x180014553  call    cs:__imp_SRCacheContext_Open
0x180014559  lea     rcx, [rbp+1A0h+var_50]
0x180014560  mov     ebx, eax
0x180014562  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180014567  test    ebx, ebx
0x180014569  jns     short loc_1800145BD
0x18001456b  mov     rcx, [rbp+1A8h]; this
0x180014572  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180014579  mov     r9d, ebx; char *
0x18001457c  mov     edx, 18Ch; void *
0x180014581  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014586  mov     edx, 10Bh; void *
0x18001458b  mov     rcx, [rbp+1A8h]; this
0x180014592  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x180014599  mov     r9d, ebx; char *
0x18001459c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800145a1  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800145a6  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800145ab  test    rcx, rcx
0x1800145ae  jz      short loc_1800145B6
0x1800145b0  call    cs:__imp_SRCacheContext_Close
0x1800145b6  mov     eax, ebx
0x1800145b8  jmp     loc_180014756
0x1800145bd  cmp     qword ptr [rsp+2A0h+var_280], r15
0x1800145c2  setnz   al
0x1800145c5  test    al, al
0x1800145c7  jnz     short loc_1800145D5
0x1800145c9  mov     ebx, 80670012h
0x1800145ce  mov     edx, 10Ch
0x1800145d3  jmp     short loc_18001458B
0x1800145d5  xor     edx, edx; Val
0x1800145d7  mov     [rsp+2A0h+var_270], r15
0x1800145dc  mov     r8d, 200h; Size
0x1800145e2  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800145e7  call    memset_0
0x1800145ec  mov     r9d, 10h
0x1800145f2  mov     [rbp+1A0h+var_68], r15
0x1800145f9  lea     rax, [rsp+2A0h+var_268]
0x1800145fe  mov     [rbp+1A0h+var_60], 100h
0x180014609  lea     rdx, [rbp+1A0h+var_50]
0x180014610  mov     [rbp+1A0h+var_58], rax
0x180014617  mov     rcx, r14
0x18001461a  lea     r8d, [r9+1]
0x18001461e  call    _o__ui64tow_s_0
0x180014623  test    eax, eax
0x180014625  jz      short loc_180014649
0x180014627  mov     rcx, [rbp+1A8h]; this
0x18001462e  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180014635  mov     ebx, 8000FFFFh
0x18001463a  mov     edx, 166h; void *
0x18001463f  mov     r9d, ebx; char *
0x180014642  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014647  jmp     short loc_180014660
0x180014649  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180014650  lea     rcx, [rsp+2A0h+var_270]; this
0x180014655  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001465a  mov     ebx, eax
0x18001465c  test    eax, eax
0x18001465e  jns     short loc_180014699
0x180014660  mov     edx, 10Fh; void *
0x180014665  mov     rcx, [rbp+1A8h]; this
0x18001466c  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x180014673  mov     r9d, ebx; char *
0x180014676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001467b  mov     rcx, [rsp+2A0h+var_270]
0x180014680  mov     [rsp+2A0h+var_270], r15
0x180014685  test    rcx, rcx
0x180014688  jz      loc_1800145A1
0x18001468e  call    cs:__imp_SRCache_Free
0x180014694  jmp     loc_1800145A1
0x180014699  mov     rdx, [rbp+1A0h+var_58]
0x1800146a0  lea     r9, [rbp+1A0h+var_48]
0x1800146a7  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800146ac  xor     r8d, r8d
0x1800146af  mov     qword ptr [rbp+1A0h+var_50], rdi
0x1800146b6  mov     [rbp+1A0h+var_48], r15
0x1800146bd  mov     [rbp+1A0h+var_40], 1
0x1800146c4  call    cs:__imp_SRCacheContext_OpenSubContext
0x1800146ca  lea     rcx, [rbp+1A0h+var_50]
0x1800146d1  mov     ebx, eax
0x1800146d3  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800146d8  test    ebx, ebx
0x1800146da  jns     short loc_180014701
0x1800146dc  mov     rcx, [rbp+1A8h]; this
0x1800146e3  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800146ea  mov     r9d, ebx; char *
0x1800146ed  mov     edx, 1B0h; void *
0x1800146f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800146f7  mov     edx, 110h
0x1800146fc  jmp     loc_180014665
0x180014701  cmp     [rdi], r15
0x180014704  lea     rdx, aUserData; "User\\Data"
0x18001470b  lea     rcx, [rsp+2A0h+var_280]; this
0x180014710  setnz   al
0x180014713  mov     [rsi], al
0x180014715  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001471a  mov     ebx, eax
0x18001471c  test    eax, eax
0x18001471e  jns     short loc_18001472A
0x180014720  mov     edx, 112h
0x180014725  jmp     loc_180014665
0x18001472a  mov     rcx, [rsp+2A0h+var_270]
0x18001472f  mov     [rsp+2A0h+var_270], r15
0x180014734  test    rcx, rcx
0x180014737  jz      short loc_18001473F
0x180014739  call    cs:__imp_SRCache_Free
0x18001473f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180014744  mov     qword ptr [rsp+2A0h+var_280], r15
0x180014749  test    rcx, rcx
0x18001474c  jz      short loc_180014754
0x18001474e  call    cs:__imp_SRCacheContext_Close
0x180014754  xor     eax, eax
0x180014756  mov     rcx, [rbp+1A0h+var_28]
0x18001475d  xor     rcx, rsp; StackCookie
0x180014760  call    __security_check_cookie
0x180014765  mov     rbx, [rsp+2A0h+arg_10]
0x18001476d  add     rsp, 280h
0x180014774  pop     r15
0x180014776  pop     r14
0x180014778  pop     rdi
0x180014779  pop     rsi
0x18001477a  pop     rbp
0x18001477b  retn
```
