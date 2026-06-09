# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180013d14`
- end: `0x180013fa8`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180012e10`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180013d14`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013ddc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013ddc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013eba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013f65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013eba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180013f65`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013d7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180013d7f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180013ef0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180013ef0`

## string_xrefs

- `0x180013e5a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x180013d9e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180013f0f`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180013dbe`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x180013e98`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x180013d69`: `ApplicationExtension\Data`
- `0x180013f30`: `ApplicationExtension\Data`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 364;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
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
    v9 = 365;
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
    v12 = 368;
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
    v12 = 369;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"ApplicationExtension\\Data");
  if ( v8 < 0 )
  {
    v12 = 371;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
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
0x180013d14  mov     [rsp-8+arg_10], rbx
0x180013d19  push    rbp
0x180013d1a  push    rsi
0x180013d1b  push    rdi
0x180013d1c  push    r14
0x180013d1e  push    r15
0x180013d20  lea     rbp, [rsp-180h]
0x180013d28  sub     rsp, 280h
0x180013d2f  mov     rax, cs:__security_cookie
0x180013d36  xor     rax, rsp
0x180013d39  mov     [rbp+1A0h+var_28], rax
0x180013d40  mov     rcx, [rcx]
0x180013d43  lea     rax, [rsp+2A0h+var_280]
0x180013d48  mov     rsi, r9
0x180013d4b  mov     qword ptr [rbp+1A0h+var_50], rax
0x180013d52  mov     rdi, r8
0x180013d55  mov     [rbp+1A0h+var_40], 1
0x180013d5c  mov     r14, rdx
0x180013d5f  lea     r9, [rbp+1A0h+var_48]
0x180013d66  xor     r15d, r15d
0x180013d69  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x180013d70  xor     r8d, r8d
0x180013d73  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180013d78  mov     [rbp+1A0h+var_48], r15
0x180013d7f  call    cs:__imp_SRCacheContext_Open
0x180013d85  lea     rcx, [rbp+1A0h+var_50]
0x180013d8c  mov     ebx, eax
0x180013d8e  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180013d93  test    ebx, ebx
0x180013d95  jns     short loc_180013DE9
0x180013d97  mov     rcx, [rbp+1A8h]; this
0x180013d9e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180013da5  mov     r9d, ebx; char *
0x180013da8  mov     edx, 18Ch; void *
0x180013dad  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013db2  mov     edx, 16Ch; void *
0x180013db7  mov     rcx, [rbp+1A8h]; this
0x180013dbe  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180013dc5  mov     r9d, ebx; char *
0x180013dc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013dcd  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013dd2  mov     qword ptr [rsp+2A0h+var_280], r15
0x180013dd7  test    rcx, rcx
0x180013dda  jz      short loc_180013DE2
0x180013ddc  call    cs:__imp_SRCacheContext_Close
0x180013de2  mov     eax, ebx
0x180013de4  jmp     loc_180013F82
0x180013de9  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180013dee  setnz   al
0x180013df1  test    al, al
0x180013df3  jnz     short loc_180013E01
0x180013df5  mov     ebx, 80670012h
0x180013dfa  mov     edx, 16Dh
0x180013dff  jmp     short loc_180013DB7
0x180013e01  xor     edx, edx; Val
0x180013e03  mov     [rsp+2A0h+var_270], r15
0x180013e08  mov     r8d, 200h; Size
0x180013e0e  lea     rcx, [rsp+2A0h+var_268]; void *
0x180013e13  call    memset_0
0x180013e18  mov     r9d, 10h
0x180013e1e  mov     [rbp+1A0h+var_68], r15
0x180013e25  lea     rax, [rsp+2A0h+var_268]
0x180013e2a  mov     [rbp+1A0h+var_60], 100h
0x180013e35  lea     rdx, [rbp+1A0h+var_50]
0x180013e3c  mov     [rbp+1A0h+var_58], rax
0x180013e43  mov     rcx, r14
0x180013e46  lea     r8d, [r9+1]
0x180013e4a  call    _o__ui64tow_s_0
0x180013e4f  test    eax, eax
0x180013e51  jz      short loc_180013E75
0x180013e53  mov     rcx, [rbp+1A8h]; this
0x180013e5a  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180013e61  mov     ebx, 8000FFFFh
0x180013e66  mov     edx, 166h; void *
0x180013e6b  mov     r9d, ebx; char *
0x180013e6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013e73  jmp     short loc_180013E8C
0x180013e75  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180013e7c  lea     rcx, [rsp+2A0h+var_270]; this
0x180013e81  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180013e86  mov     ebx, eax
0x180013e88  test    eax, eax
0x180013e8a  jns     short loc_180013EC5
0x180013e8c  mov     edx, 170h; void *
0x180013e91  mov     rcx, [rbp+1A8h]; this
0x180013e98  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180013e9f  mov     r9d, ebx; char *
0x180013ea2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013ea7  mov     rcx, [rsp+2A0h+var_270]
0x180013eac  mov     [rsp+2A0h+var_270], r15
0x180013eb1  test    rcx, rcx
0x180013eb4  jz      loc_180013DCD
0x180013eba  call    cs:__imp_SRCache_Free
0x180013ec0  jmp     loc_180013DCD
0x180013ec5  mov     rdx, [rbp+1A0h+var_58]
0x180013ecc  lea     r9, [rbp+1A0h+var_48]
0x180013ed3  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013ed8  xor     r8d, r8d
0x180013edb  mov     qword ptr [rbp+1A0h+var_50], rdi
0x180013ee2  mov     [rbp+1A0h+var_48], r15
0x180013ee9  mov     [rbp+1A0h+var_40], 1
0x180013ef0  call    cs:__imp_SRCacheContext_OpenSubContext
0x180013ef6  lea     rcx, [rbp+1A0h+var_50]
0x180013efd  mov     ebx, eax
0x180013eff  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x180013f04  test    ebx, ebx
0x180013f06  jns     short loc_180013F2D
0x180013f08  mov     rcx, [rbp+1A8h]; this
0x180013f0f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180013f16  mov     r9d, ebx; char *
0x180013f19  mov     edx, 1B0h; void *
0x180013f1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013f23  mov     edx, 171h
0x180013f28  jmp     loc_180013E91
0x180013f2d  cmp     [rdi], r15
0x180013f30  lea     rdx, aApplicationext; "ApplicationExtension\\Data"
0x180013f37  lea     rcx, [rsp+2A0h+var_280]; this
0x180013f3c  setnz   al
0x180013f3f  mov     [rsi], al
0x180013f41  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x180013f46  mov     ebx, eax
0x180013f48  test    eax, eax
0x180013f4a  jns     short loc_180013F56
0x180013f4c  mov     edx, 173h
0x180013f51  jmp     loc_180013E91
0x180013f56  mov     rcx, [rsp+2A0h+var_270]
0x180013f5b  mov     [rsp+2A0h+var_270], r15
0x180013f60  test    rcx, rcx
0x180013f63  jz      short loc_180013F6B
0x180013f65  call    cs:__imp_SRCache_Free
0x180013f6b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180013f70  mov     qword ptr [rsp+2A0h+var_280], r15
0x180013f75  test    rcx, rcx
0x180013f78  jz      short loc_180013F80
0x180013f7a  call    cs:__imp_SRCacheContext_Close
0x180013f80  xor     eax, eax
0x180013f82  mov     rcx, [rbp+1A0h+var_28]
0x180013f89  xor     rcx, rsp; StackCookie
0x180013f8c  call    __security_check_cookie
0x180013f91  mov     rbx, [rsp+2A0h+arg_10]
0x180013f99  add     rsp, 280h
0x180013fa0  pop     r15
0x180013fa2  pop     r14
0x180013fa4  pop     rdi
0x180013fa5  pop     rsi
0x180013fa6  pop     rbp
0x180013fa7  retn
```
