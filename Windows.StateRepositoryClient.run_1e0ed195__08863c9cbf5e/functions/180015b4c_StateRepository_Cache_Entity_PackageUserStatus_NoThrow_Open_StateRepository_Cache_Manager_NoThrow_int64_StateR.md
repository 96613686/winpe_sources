# StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180015b4c`
- end: `0x180015de0`
- name: `?Open@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180014de4`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180015b4c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015c14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015db2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015c14`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180015db2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015cf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015d9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015cf2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180015d9d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180015bb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180015bb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180015d28`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180015d28`

## string_xrefs

- `0x180015c92`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180015bd6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180015d47`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180015bf6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x180015cd0`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageUserStatus\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 352;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
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
    v9 = 353;
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
    v12 = 356;
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
    v12 = 357;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageUserStatus\\Data");
  if ( v8 < 0 )
  {
    v12 = 359;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
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
0x180015b4c  mov     [rsp-8+arg_10], rbx
0x180015b51  push    rbp
0x180015b52  push    rsi
0x180015b53  push    rdi
0x180015b54  push    r14
0x180015b56  push    r15
0x180015b58  lea     rbp, [rsp-180h]
0x180015b60  sub     rsp, 280h
0x180015b67  mov     rax, cs:__security_cookie
0x180015b6e  xor     rax, rsp
0x180015b71  mov     [rbp+1A0h+var_28], rax
0x180015b78  mov     rcx, [rcx]
0x180015b7b  lea     rax, [rsp+2A0h+var_280]
0x180015b80  mov     rsi, r9
0x180015b83  mov     qword ptr [rbp+1A0h+var_50], rax
0x180015b8a  mov     rdi, r8
0x180015b8d  mov     [rbp+1A0h+var_40], 1
0x180015b94  mov     r14, rdx
0x180015b97  lea     r9, [rbp+1A0h+var_48]
0x180015b9e  xor     r15d, r15d
0x180015ba1  lea     rdx, aPackageusersta; "PackageUserStatus\\Data"
0x180015ba8  xor     r8d, r8d
0x180015bab  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180015bb0  mov     [rbp+1A0h+var_48], r15
0x180015bb7  call    cs:__imp_SRCacheContext_Open
0x180015bbd  lea     rcx, [rbp+1A0h+var_50]
0x180015bc4  mov     ebx, eax
0x180015bc6  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180015bcb  test    ebx, ebx
0x180015bcd  jns     short loc_180015C21
0x180015bcf  mov     rcx, [rbp+1A8h]; this
0x180015bd6  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180015bdd  mov     r9d, ebx; char *
0x180015be0  mov     edx, 18Ch; void *
0x180015be5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015bea  mov     edx, 160h; void *
0x180015bef  mov     rcx, [rbp+1A8h]; this
0x180015bf6  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180015bfd  mov     r9d, ebx; char *
0x180015c00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015c05  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015c0a  mov     qword ptr [rsp+2A0h+var_280], r15
0x180015c0f  test    rcx, rcx
0x180015c12  jz      short loc_180015C1A
0x180015c14  call    cs:__imp_SRCacheContext_Close
0x180015c1a  mov     eax, ebx
0x180015c1c  jmp     loc_180015DBA
0x180015c21  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180015c26  setnz   al
0x180015c29  test    al, al
0x180015c2b  jnz     short loc_180015C39
0x180015c2d  mov     ebx, 80670012h
0x180015c32  mov     edx, 161h
0x180015c37  jmp     short loc_180015BEF
0x180015c39  xor     edx, edx; Val
0x180015c3b  mov     [rsp+2A0h+var_270], r15
0x180015c40  mov     r8d, 200h; Size
0x180015c46  lea     rcx, [rsp+2A0h+var_268]; void *
0x180015c4b  call    memset_0
0x180015c50  mov     r9d, 10h
0x180015c56  mov     [rbp+1A0h+var_68], r15
0x180015c5d  lea     rax, [rsp+2A0h+var_268]
0x180015c62  mov     [rbp+1A0h+var_60], 100h
0x180015c6d  lea     rdx, [rbp+1A0h+var_50]
0x180015c74  mov     [rbp+1A0h+var_58], rax
0x180015c7b  mov     rcx, r14
0x180015c7e  lea     r8d, [r9+1]
0x180015c82  call    _o__ui64tow_s_0
0x180015c87  test    eax, eax
0x180015c89  jz      short loc_180015CAD
0x180015c8b  mov     rcx, [rbp+1A8h]; this
0x180015c92  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180015c99  mov     ebx, 8000FFFFh
0x180015c9e  mov     edx, 166h; void *
0x180015ca3  mov     r9d, ebx; char *
0x180015ca6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cab  jmp     short loc_180015CC4
0x180015cad  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180015cb4  lea     rcx, [rsp+2A0h+var_270]; this
0x180015cb9  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180015cbe  mov     ebx, eax
0x180015cc0  test    eax, eax
0x180015cc2  jns     short loc_180015CFD
0x180015cc4  mov     edx, 164h; void *
0x180015cc9  mov     rcx, [rbp+1A8h]; this
0x180015cd0  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180015cd7  mov     r9d, ebx; char *
0x180015cda  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cdf  mov     rcx, [rsp+2A0h+var_270]
0x180015ce4  mov     [rsp+2A0h+var_270], r15
0x180015ce9  test    rcx, rcx
0x180015cec  jz      loc_180015C05
0x180015cf2  call    cs:__imp_SRCache_Free
0x180015cf8  jmp     loc_180015C05
0x180015cfd  mov     rdx, [rbp+1A0h+var_58]
0x180015d04  lea     r9, [rbp+1A0h+var_48]
0x180015d0b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015d10  xor     r8d, r8d
0x180015d13  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180015d1a  mov     [rbp+1A0h+var_48], r15
0x180015d21  mov     [rbp+1A0h+var_40], 1
0x180015d28  call    cs:__imp_SRCacheContext_OpenSubContext
0x180015d2e  lea     rcx, [rbp+1A0h+var_50]
0x180015d35  mov     ebx, eax
0x180015d37  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180015d3c  test    ebx, ebx
0x180015d3e  jns     short loc_180015D65
0x180015d40  mov     rcx, [rbp+1A8h]; this
0x180015d47  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180015d4e  mov     r9d, ebx; char *
0x180015d51  mov     edx, 1B0h; void *
0x180015d56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015d5b  mov     edx, 165h
0x180015d60  jmp     loc_180015CC9
0x180015d65  cmp     [rdi], r15
0x180015d68  lea     rdx, aPackageusersta; "PackageUserStatus\\Data"
0x180015d6f  lea     rcx, [rsp+2A0h+var_280]; this
0x180015d74  setnz   al
0x180015d77  mov     [rsi], al
0x180015d79  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180015d7e  mov     ebx, eax
0x180015d80  test    eax, eax
0x180015d82  jns     short loc_180015D8E
0x180015d84  mov     edx, 167h
0x180015d89  jmp     loc_180015CC9
0x180015d8e  mov     rcx, [rsp+2A0h+var_270]
0x180015d93  mov     [rsp+2A0h+var_270], r15
0x180015d98  test    rcx, rcx
0x180015d9b  jz      short loc_180015DA3
0x180015d9d  call    cs:__imp_SRCache_Free
0x180015da3  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180015da8  mov     qword ptr [rsp+2A0h+var_280], r15
0x180015dad  test    rcx, rcx
0x180015db0  jz      short loc_180015DB8
0x180015db2  call    cs:__imp_SRCacheContext_Close
0x180015db8  xor     eax, eax
0x180015dba  mov     rcx, [rbp+1A0h+var_28]
0x180015dc1  xor     rcx, rsp; StackCookie
0x180015dc4  call    __security_check_cookie
0x180015dc9  mov     rbx, [rsp+2A0h+arg_10]
0x180015dd1  add     rsp, 280h
0x180015dd8  pop     r15
0x180015dda  pop     r14
0x180015ddc  pop     rdi
0x180015ddd  pop     rsi
0x180015dde  pop     rbp
0x180015ddf  retn
```
