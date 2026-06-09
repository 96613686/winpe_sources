# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18029429c`
- end: `0x180294531`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `661`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18028ff20`

## callees

- `0x180064e8c`
- `0x18020aac0`
- `0x18020bab8`
- `0x18028605c`
- `0x18028784c`
- `0x18028788c`
- `0x18029429c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802943d2`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1802943d2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180294443`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802944ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180294443`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1802944ee`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180294307`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180294307`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180294364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180294503`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180294364`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180294503`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180294479`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180294479`

## string_xrefs

- `0x1802943e3`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180294326`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180294498`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180294346`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x180294421`: `OneCore\private\Base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

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
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v20[512]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v21; // [rsp+238h] [rbp+138h]
  __int64 v22; // [rsp+240h] [rbp+140h]
  _BYTE *v23; // [rsp+248h] [rbp+148h]
  wchar_t v24[4]; // [rsp+250h] [rbp+150h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h] BYREF
  char v26; // [rsp+260h] [rbp+160h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v4 = *(_QWORD *)a1;
  *(_QWORD *)v24 = v18;
  v26 = 1;
  *(_QWORD *)v18 = 0;
  v25 = 0;
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v9 = 1192;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
LABEL_4:
    v11 = *(_QWORD *)v18;
    *(_QWORD *)v18 = 0;
    if ( v11 )
      SRCacheContext_Close(v11, v10);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v18 )
  {
    v8 = -2140733422;
    v9 = 1193;
    goto LABEL_3;
  }
  v19 = 0;
  memset_0(v20, 0, sizeof(v20));
  v21 = 0;
  v22 = 256;
  v23 = v20;
  if ( (unsigned int)_o__ui64tow_s(a2, v24, 17) )
  {
    v8 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v18[0]);
LABEL_12:
    v13 = 1196;
    goto LABEL_13;
  }
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v19, v24);
  if ( v8 < 0 )
    goto LABEL_12;
  *(_QWORD *)v24 = a3;
  v25 = 0;
  v26 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v18, v23, 0, &v25);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v24);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v13 = 1197;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v18,
         L"Package\\Data");
  if ( v8 < 0 )
  {
    v13 = 1199;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"OneCore\\private\\Base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v18[0]);
    v14 = v19;
    v19 = 0;
    if ( v14 )
      SRCache_Free();
    goto LABEL_4;
  }
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCache_Free();
  v17 = *(_QWORD *)v18;
  *(_QWORD *)v18 = 0;
  if ( v17 )
    SRCacheContext_Close(v17, v15);
  return 0;
}

```

## disassembly

```asm
0x18029429c  mov     [rsp-8+arg_10], rbx
0x1802942a1  push    rbp
0x1802942a2  push    rsi
0x1802942a3  push    rdi
0x1802942a4  push    r14
0x1802942a6  push    r15
0x1802942a8  lea     rbp, [rsp-180h]
0x1802942b0  sub     rsp, 280h
0x1802942b7  mov     rax, cs:__security_cookie
0x1802942be  xor     rax, rsp
0x1802942c1  mov     [rbp+1A0h+var_28], rax
0x1802942c8  mov     rcx, [rcx]
0x1802942cb  lea     rax, [rsp+2A0h+var_280]
0x1802942d0  mov     rsi, r9
0x1802942d3  mov     qword ptr [rbp+1A0h+var_50], rax
0x1802942da  mov     rdi, r8
0x1802942dd  mov     [rbp+1A0h+var_40], 1
0x1802942e4  mov     r14, rdx
0x1802942e7  lea     r9, [rbp+1A0h+var_48]
0x1802942ee  xor     r15d, r15d
0x1802942f1  lea     rdx, aPackageData; "Package\\Data"
0x1802942f8  xor     r8d, r8d
0x1802942fb  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180294300  mov     [rbp+1A0h+var_48], r15
0x180294307  call    cs:__imp_SRCacheContext_Open
0x18029430d  lea     rcx, [rbp+1A0h+var_50]
0x180294314  mov     ebx, eax
0x180294316  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18029431b  test    ebx, ebx
0x18029431d  jns     short loc_180294371
0x18029431f  mov     rcx, [rbp+1A8h]; this
0x180294326  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x18029432d  mov     r9d, ebx; char *
0x180294330  mov     edx, 18Ch; void *
0x180294335  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18029433a  mov     edx, 4A8h; void *
0x18029433f  mov     rcx, [rbp+1A8h]; this
0x180294346  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x18029434d  mov     r9d, ebx; char *
0x180294350  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294355  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18029435a  mov     qword ptr [rsp+2A0h+var_280], r15
0x18029435f  test    rcx, rcx
0x180294362  jz      short loc_18029436A
0x180294364  call    cs:__imp_SRCacheContext_Close
0x18029436a  mov     eax, ebx
0x18029436c  jmp     loc_18029450B
0x180294371  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180294376  setnz   al
0x180294379  test    al, al
0x18029437b  jnz     short loc_180294389
0x18029437d  mov     ebx, 80670012h
0x180294382  mov     edx, 4A9h
0x180294387  jmp     short loc_18029433F
0x180294389  xor     edx, edx; Val
0x18029438b  mov     [rsp+2A0h+var_270], r15
0x180294390  mov     r8d, 200h; Size
0x180294396  lea     rcx, [rsp+2A0h+var_268]; void *
0x18029439b  call    memset_0
0x1802943a0  mov     r9d, 10h
0x1802943a6  mov     [rbp+1A0h+var_68], r15
0x1802943ad  lea     rax, [rsp+2A0h+var_268]
0x1802943b2  mov     [rbp+1A0h+var_60], 100h
0x1802943bd  lea     rdx, [rbp+1A0h+var_50]
0x1802943c4  mov     [rbp+1A0h+var_58], rax
0x1802943cb  mov     rcx, r14
0x1802943ce  lea     r8d, [r9+1]
0x1802943d2  call    cs:__imp__o__ui64tow_s
0x1802943d8  test    eax, eax
0x1802943da  jz      short loc_1802943FE
0x1802943dc  mov     rcx, [rbp+1A8h]; this
0x1802943e3  lea     r8, aOnecorePrivate_2; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x1802943ea  mov     ebx, 8000FFFFh
0x1802943ef  mov     edx, 166h; void *
0x1802943f4  mov     r9d, ebx; char *
0x1802943f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802943fc  jmp     short loc_180294415
0x1802943fe  lea     rdx, [rbp+1A0h+var_50]; wchar_t *
0x180294405  lea     rcx, [rsp+2A0h+var_270]; this
0x18029440a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Key_NoThrow::Append(wchar_t const *)
0x18029440f  mov     ebx, eax
0x180294411  test    eax, eax
0x180294413  jns     short loc_18029444E
0x180294415  mov     edx, 4ACh; void *
0x18029441a  mov     rcx, [rbp+1A8h]; this
0x180294421  lea     r8, aOnecorePrivate_0; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x180294428  mov     r9d, ebx; char *
0x18029442b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180294430  mov     rcx, [rsp+2A0h+var_270]
0x180294435  mov     [rsp+2A0h+var_270], r15
0x18029443a  test    rcx, rcx
0x18029443d  jz      loc_180294355
0x180294443  call    cs:__imp_SRCache_Free
0x180294449  jmp     loc_180294355
0x18029444e  mov     rdx, [rbp+1A0h+var_58]
0x180294455  lea     r9, [rbp+1A0h+var_48]
0x18029445c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180294461  xor     r8d, r8d
0x180294464  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18029446b  mov     [rbp+1A0h+var_48], r15
0x180294472  mov     [rbp+1A0h+var_40], 1
0x180294479  call    cs:__imp_SRCacheContext_OpenSubContext
0x18029447f  lea     rcx, [rbp+1A0h+var_50]
0x180294486  mov     ebx, eax
0x180294488  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18029448d  test    ebx, ebx
0x18029448f  jns     short loc_1802944B6
0x180294491  mov     rcx, [rbp+1A8h]; this
0x180294498  lea     r8, aOnecorePrivate_1; "OneCore\\private\\Base\\inc\\appmodel\\"...
0x18029449f  mov     r9d, ebx; char *
0x1802944a2  mov     edx, 1B0h; void *
0x1802944a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1802944ac  mov     edx, 4ADh
0x1802944b1  jmp     loc_18029441A
0x1802944b6  cmp     [rdi], r15
0x1802944b9  lea     rdx, aPackageData; "Package\\Data"
0x1802944c0  lea     rcx, [rsp+2A0h+var_280]; this
0x1802944c5  setnz   al
0x1802944c8  mov     [rsi], al
0x1802944ca  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEB_W@Z; StateRepository::Cache::Context_NoThrow::AddToCache(wchar_t const *)
0x1802944cf  mov     ebx, eax
0x1802944d1  test    eax, eax
0x1802944d3  jns     short loc_1802944DF
0x1802944d5  mov     edx, 4AFh
0x1802944da  jmp     loc_18029441A
0x1802944df  mov     rcx, [rsp+2A0h+var_270]
0x1802944e4  mov     [rsp+2A0h+var_270], r15
0x1802944e9  test    rcx, rcx
0x1802944ec  jz      short loc_1802944F4
0x1802944ee  call    cs:__imp_SRCache_Free
0x1802944f4  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1802944f9  mov     qword ptr [rsp+2A0h+var_280], r15
0x1802944fe  test    rcx, rcx
0x180294501  jz      short loc_180294509
0x180294503  call    cs:__imp_SRCacheContext_Close
0x180294509  xor     eax, eax
0x18029450b  mov     rcx, [rbp+1A0h+var_28]
0x180294512  xor     rcx, rsp; StackCookie
0x180294515  call    __security_check_cookie
0x18029451a  mov     rbx, [rsp+2A0h+arg_10]
0x180294522  add     rsp, 280h
0x180294529  pop     r15
0x18029452b  pop     r14
0x18029452d  pop     rdi
0x18029452e  pop     rsi
0x18029452f  pop     rbp
0x180294530  retn
```
