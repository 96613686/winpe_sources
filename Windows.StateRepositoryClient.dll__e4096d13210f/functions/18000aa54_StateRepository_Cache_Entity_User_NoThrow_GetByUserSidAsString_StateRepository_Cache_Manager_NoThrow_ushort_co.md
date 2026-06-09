# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18000aa54`
- end: `0x18000acee`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18000a9bc`
- `0x18001370c`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180009f64`
- `0x18000aa54`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000acc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ab0d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac3f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000ac9f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000acc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aba8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000acb4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000aba8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000acb4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000aab2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18000aab2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000abe0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18000abe0`

## string_xrefs

- `0x18000aacf`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000abfd`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18000aaef`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x18000ab81`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x18000ac1d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x18000aaab`: `User\Index\UserSid`
- `0x18000ac72`: `User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
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
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v21);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v20);
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v18[0]);
    v7 = 185;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
    v7 = 186;
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
      (void *)0xBD,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
    v13 = 193;
    goto LABEL_15;
  }
  if ( v19 )
  {
    v6 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)&v19, 0, a3);
    if ( v6 < 0 )
    {
      v13 = 196;
      goto LABEL_15;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"User\\Index\\UserSid");
  if ( v6 < 0 )
  {
    v13 = 199;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
0x18000aa54  push    rbp
0x18000aa56  push    rbx
0x18000aa57  push    rsi
0x18000aa58  push    rdi
0x18000aa59  push    r14
0x18000aa5b  lea     rbp, [rsp-180h]
0x18000aa63  sub     rsp, 280h
0x18000aa6a  mov     rax, cs:__security_cookie
0x18000aa71  xor     rax, rsp
0x18000aa74  mov     [rbp+1A0h+var_30], rax
0x18000aa7b  xor     r14d, r14d
0x18000aa7e  mov     [rsp+2A0h+var_260], 1
0x18000aa83  mov     [r8], r14
0x18000aa86  lea     rax, [rsp+2A0h+var_280]
0x18000aa8b  mov     rcx, [rcx]
0x18000aa8e  lea     r9, [rsp+2A0h+var_268]
0x18000aa93  mov     rdi, r8
0x18000aa96  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18000aa9b  mov     rsi, rdx
0x18000aa9e  mov     [rsp+2A0h+var_270], rax
0x18000aaa3  xor     r8d, r8d
0x18000aaa6  mov     [rsp+2A0h+var_268], r14
0x18000aaab  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000aab2  call    cs:__imp_SRCacheContext_Open
0x18000aab8  lea     rcx, [rsp+2A0h+var_270]
0x18000aabd  mov     ebx, eax
0x18000aabf  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000aac4  test    ebx, ebx
0x18000aac6  jns     short loc_18000AB1A
0x18000aac8  mov     rcx, [rbp+1A8h]; this
0x18000aacf  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000aad6  mov     r9d, ebx; char *
0x18000aad9  mov     edx, 18Ch; void *
0x18000aade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aae3  mov     edx, 0B9h; void *
0x18000aae8  mov     rcx, [rbp+1A8h]; this
0x18000aaef  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18000aaf6  mov     r9d, ebx; char *
0x18000aaf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aafe  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000ab03  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000ab08  test    rcx, rcx
0x18000ab0b  jz      short loc_18000AB13
0x18000ab0d  call    cs:__imp_SRCacheContext_Close
0x18000ab13  mov     eax, ebx
0x18000ab15  jmp     loc_18000ACD1
0x18000ab1a  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18000ab1f  setnz   al
0x18000ab22  test    al, al
0x18000ab24  jnz     short loc_18000AB32
0x18000ab26  mov     ebx, 80670012h
0x18000ab2b  mov     edx, 0BAh
0x18000ab30  jmp     short loc_18000AAE8
0x18000ab32  xor     edx, edx; Val
0x18000ab34  mov     [rsp+2A0h+var_250], r14
0x18000ab39  mov     r8d, 200h; Size
0x18000ab3f  lea     rcx, [rsp+2A0h+var_248]; void *
0x18000ab44  call    memset_0
0x18000ab49  lea     rax, [rsp+2A0h+var_248]
0x18000ab4e  mov     [rbp+1A0h+var_48], r14
0x18000ab55  mov     rdx, rsi; unsigned __int16 *
0x18000ab58  mov     [rbp+1A0h+var_38], rax
0x18000ab5f  lea     rcx, [rsp+2A0h+var_250]; this
0x18000ab64  mov     [rbp+1A0h+var_40], 100h
0x18000ab6f  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18000ab74  mov     ebx, eax
0x18000ab76  test    eax, eax
0x18000ab78  jns     short loc_18000ABB3
0x18000ab7a  mov     rcx, [rbp+1A8h]; this
0x18000ab81  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18000ab88  mov     r9d, eax; char *
0x18000ab8b  mov     edx, 0BDh; void *
0x18000ab90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab95  mov     rcx, [rsp+2A0h+var_250]
0x18000ab9a  mov     [rsp+2A0h+var_250], r14
0x18000ab9f  test    rcx, rcx
0x18000aba2  jz      loc_18000AAFE
0x18000aba8  call    cs:__imp_SRCache_Free
0x18000abae  jmp     loc_18000AAFE
0x18000abb3  mov     rdx, [rbp+1A0h+var_38]
0x18000abba  lea     rax, [rsp+2A0h+var_278]
0x18000abbf  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000abc4  lea     r9, [rsp+2A0h+var_268]
0x18000abc9  xor     r8d, r8d
0x18000abcc  mov     [rsp+2A0h+var_270], rax
0x18000abd1  mov     [rsp+2A0h+var_278], r14
0x18000abd6  mov     [rsp+2A0h+var_268], r14
0x18000abdb  mov     [rsp+2A0h+var_260], 1
0x18000abe0  call    cs:__imp_SRCacheContext_OpenSubContext
0x18000abe6  lea     rcx, [rsp+2A0h+var_270]
0x18000abeb  mov     ebx, eax
0x18000abed  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18000abf2  test    ebx, ebx
0x18000abf4  jns     short loc_18000AC4A
0x18000abf6  mov     rcx, [rbp+1A8h]; this
0x18000abfd  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000ac04  mov     r9d, ebx; char *
0x18000ac07  mov     edx, 1B0h; void *
0x18000ac0c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac11  mov     edx, 0C1h; void *
0x18000ac16  mov     rcx, [rbp+1A8h]; this
0x18000ac1d  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18000ac24  mov     r9d, ebx; char *
0x18000ac27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac2c  mov     rcx, [rsp+2A0h+var_278]
0x18000ac31  mov     [rsp+2A0h+var_278], r14
0x18000ac36  test    rcx, rcx
0x18000ac39  jz      loc_18000AB95
0x18000ac3f  call    cs:__imp_SRCacheContext_Close
0x18000ac45  jmp     loc_18000AB95
0x18000ac4a  cmp     [rsp+2A0h+var_278], r14
0x18000ac4f  setnz   al
0x18000ac52  test    al, al
0x18000ac54  jz      short loc_18000AC72
0x18000ac56  mov     r8, rdi; __int64 *
0x18000ac59  lea     rcx, [rsp+2A0h+var_278]; this
0x18000ac5e  xor     edx, edx; int
0x18000ac60  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x18000ac65  mov     ebx, eax
0x18000ac67  test    eax, eax
0x18000ac69  jns     short loc_18000AC72
0x18000ac6b  mov     edx, 0C4h
0x18000ac70  jmp     short loc_18000AC16
0x18000ac72  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x18000ac79  lea     rcx, [rsp+2A0h+var_280]; this
0x18000ac7e  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18000ac83  mov     ebx, eax
0x18000ac85  test    eax, eax
0x18000ac87  jns     short loc_18000AC90
0x18000ac89  mov     edx, 0C7h
0x18000ac8e  jmp     short loc_18000AC16
0x18000ac90  mov     rcx, [rsp+2A0h+var_278]
0x18000ac95  mov     [rsp+2A0h+var_278], r14
0x18000ac9a  test    rcx, rcx
0x18000ac9d  jz      short loc_18000ACA5
0x18000ac9f  call    cs:__imp_SRCacheContext_Close
0x18000aca5  mov     rcx, [rsp+2A0h+var_250]
0x18000acaa  mov     [rsp+2A0h+var_250], r14
0x18000acaf  test    rcx, rcx
0x18000acb2  jz      short loc_18000ACBA
0x18000acb4  call    cs:__imp_SRCache_Free
0x18000acba  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18000acbf  mov     qword ptr [rsp+2A0h+var_280], r14
0x18000acc4  test    rcx, rcx
0x18000acc7  jz      short loc_18000ACCF
0x18000acc9  call    cs:__imp_SRCacheContext_Close
0x18000accf  xor     eax, eax
0x18000acd1  mov     rcx, [rbp+1A0h+var_30]
0x18000acd8  xor     rcx, rsp; StackCookie
0x18000acdb  call    __security_check_cookie
0x18000ace0  add     rsp, 280h
0x18000ace7  pop     r14
0x18000ace9  pop     rdi
0x18000acea  pop     rsi
0x18000aceb  pop     rbx
0x18000acec  pop     rbp
0x18000aced  retn
```
