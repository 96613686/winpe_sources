# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180013fb0`
- end: `0x180014244`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180012ef0`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x180013fb0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014216`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014078`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014216`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014156`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014201`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014156`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180014201`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001401b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001401b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001418c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001418c`

## string_xrefs

- `0x1800140f6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x18001403a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x1800141ab`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x18001405a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Application.hpp`
- `0x180014134`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 433;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Application.hpp",
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
    v9 = 434;
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
    v12 = 437;
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
    v12 = 438;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"Application\\Data");
  if ( v8 < 0 )
  {
    v12 = 440;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Application.hpp",
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
0x180013fb0  mov     [rsp-8+arg_10], rbx
0x180013fb5  push    rbp
0x180013fb6  push    rsi
0x180013fb7  push    rdi
0x180013fb8  push    r14
0x180013fba  push    r15
0x180013fbc  lea     rbp, [rsp-180h]
0x180013fc4  sub     rsp, 280h
0x180013fcb  mov     rax, cs:__security_cookie
0x180013fd2  xor     rax, rsp
0x180013fd5  mov     [rbp+1A0h+var_28], rax
0x180013fdc  mov     rcx, [rcx]
0x180013fdf  lea     rax, [rsp+2A0h+var_280]
0x180013fe4  mov     rsi, r9
0x180013fe7  mov     qword ptr [rbp+1A0h+var_50], rax
0x180013fee  mov     rdi, r8
0x180013ff1  mov     [rbp+1A0h+var_40], 1
0x180013ff8  mov     r14, rdx
0x180013ffb  lea     r9, [rbp+1A0h+var_48]
0x180014002  xor     r15d, r15d
0x180014005  lea     rdx, aApplicationDat; "Application\\Data"
0x18001400c  xor     r8d, r8d
0x18001400f  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x180014014  mov     [rbp+1A0h+var_48], r15
0x18001401b  call    cs:__imp_SRCacheContext_Open
0x180014021  lea     rcx, [rbp+1A0h+var_50]
0x180014028  mov     ebx, eax
0x18001402a  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001402f  test    ebx, ebx
0x180014031  jns     short loc_180014085
0x180014033  mov     rcx, [rbp+1A8h]; this
0x18001403a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180014041  mov     r9d, ebx; char *
0x180014044  mov     edx, 18Ch; void *
0x180014049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001404e  mov     edx, 1B1h; void *
0x180014053  mov     rcx, [rbp+1A8h]; this
0x18001405a  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\StateRepositor"...
0x180014061  mov     r9d, ebx; char *
0x180014064  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014069  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001406e  mov     qword ptr [rsp+2A0h+var_280], r15
0x180014073  test    rcx, rcx
0x180014076  jz      short loc_18001407E
0x180014078  call    cs:__imp_SRCacheContext_Close
0x18001407e  mov     eax, ebx
0x180014080  jmp     loc_18001421E
0x180014085  cmp     qword ptr [rsp+2A0h+var_280], r15
0x18001408a  setnz   al
0x18001408d  test    al, al
0x18001408f  jnz     short loc_18001409D
0x180014091  mov     ebx, 80670012h
0x180014096  mov     edx, 1B2h
0x18001409b  jmp     short loc_180014053
0x18001409d  xor     edx, edx; Val
0x18001409f  mov     [rsp+2A0h+var_270], r15
0x1800140a4  mov     r8d, 200h; Size
0x1800140aa  lea     rcx, [rsp+2A0h+var_268]; void *
0x1800140af  call    memset_0
0x1800140b4  mov     r9d, 10h
0x1800140ba  mov     [rbp+1A0h+var_68], r15
0x1800140c1  lea     rax, [rsp+2A0h+var_268]
0x1800140c6  mov     [rbp+1A0h+var_60], 100h
0x1800140d1  lea     rdx, [rbp+1A0h+var_50]
0x1800140d8  mov     [rbp+1A0h+var_58], rax
0x1800140df  mov     rcx, r14
0x1800140e2  lea     r8d, [r9+1]
0x1800140e6  call    _o__ui64tow_s_0
0x1800140eb  test    eax, eax
0x1800140ed  jz      short loc_180014111
0x1800140ef  mov     rcx, [rbp+1A8h]; this
0x1800140f6  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x1800140fd  mov     ebx, 8000FFFFh
0x180014102  mov     edx, 166h; void *
0x180014107  mov     r9d, ebx; char *
0x18001410a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001410f  jmp     short loc_180014128
0x180014111  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x180014118  lea     rcx, [rsp+2A0h+var_270]; this
0x18001411d  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x180014122  mov     ebx, eax
0x180014124  test    eax, eax
0x180014126  jns     short loc_180014161
0x180014128  mov     edx, 1B5h; void *
0x18001412d  mov     rcx, [rbp+1A8h]; this
0x180014134  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\StateRepositor"...
0x18001413b  mov     r9d, ebx; char *
0x18001413e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014143  mov     rcx, [rsp+2A0h+var_270]
0x180014148  mov     [rsp+2A0h+var_270], r15
0x18001414d  test    rcx, rcx
0x180014150  jz      loc_180014069
0x180014156  call    cs:__imp_SRCache_Free
0x18001415c  jmp     loc_180014069
0x180014161  mov     rdx, [rbp+1A0h+var_58]
0x180014168  lea     r9, [rbp+1A0h+var_48]
0x18001416f  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180014174  xor     r8d, r8d
0x180014177  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18001417e  mov     [rbp+1A0h+var_48], r15
0x180014185  mov     [rbp+1A0h+var_40], 1
0x18001418c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180014192  lea     rcx, [rbp+1A0h+var_50]
0x180014199  mov     ebx, eax
0x18001419b  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800141a0  test    ebx, ebx
0x1800141a2  jns     short loc_1800141C9
0x1800141a4  mov     rcx, [rbp+1A8h]; this
0x1800141ab  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800141b2  mov     r9d, ebx; char *
0x1800141b5  mov     edx, 1B0h; void *
0x1800141ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800141bf  mov     edx, 1B6h
0x1800141c4  jmp     loc_18001412D
0x1800141c9  cmp     [rdi], r15
0x1800141cc  lea     rdx, aApplicationDat; "Application\\Data"
0x1800141d3  lea     rcx, [rsp+2A0h+var_280]; this
0x1800141d8  setnz   al
0x1800141db  mov     [rsi], al
0x1800141dd  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800141e2  mov     ebx, eax
0x1800141e4  test    eax, eax
0x1800141e6  jns     short loc_1800141F2
0x1800141e8  mov     edx, 1B8h
0x1800141ed  jmp     loc_18001412D
0x1800141f2  mov     rcx, [rsp+2A0h+var_270]
0x1800141f7  mov     [rsp+2A0h+var_270], r15
0x1800141fc  test    rcx, rcx
0x1800141ff  jz      short loc_180014207
0x180014201  call    cs:__imp_SRCache_Free
0x180014207  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001420c  mov     qword ptr [rsp+2A0h+var_280], r15
0x180014211  test    rcx, rcx
0x180014214  jz      short loc_18001421C
0x180014216  call    cs:__imp_SRCacheContext_Close
0x18001421c  xor     eax, eax
0x18001421e  mov     rcx, [rbp+1A0h+var_28]
0x180014225  xor     rcx, rsp; StackCookie
0x180014228  call    __security_check_cookie
0x18001422d  mov     rbx, [rsp+2A0h+arg_10]
0x180014235  add     rsp, 280h
0x18001423c  pop     r15
0x18001423e  pop     r14
0x180014240  pop     rdi
0x180014241  pop     rsi
0x180014242  pop     rbp
0x180014243  retn
```
