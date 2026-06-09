# StateRepository::Cache::Entity::PackageUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001424c`
- end: `0x1800144e0`
- name: `?Open@PackageUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `660`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180012fd0`

## callees

- `0x180002980`
- `0x1800035c4`
- `0x180003630`
- `0x1800075e4`
- `0x180009474`
- `0x1800097c0`
- `0x180009800`
- `0x18001424c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014314`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800144b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014314`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800144b2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800143f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001449d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800143f2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001449d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800142b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800142b7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180014428`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180014428`

## string_xrefs

- `0x180014392`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Key.hpp`
- `0x1800142d6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x180014447`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`
- `0x1800142f6`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x1800143d0`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"PackageUser\\Data", 0, &v23);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(v22);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16[0]);
    v9 = 298;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
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
    v9 = 299;
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
    v12 = 302;
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
    v12 = 303;
    goto LABEL_13;
  }
  *a4 = *(_QWORD *)a3 != 0;
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v16,
         L"PackageUser\\Data");
  if ( v8 < 0 )
  {
    v12 = 305;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
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
0x18001424c  mov     [rsp-8+arg_10], rbx
0x180014251  push    rbp
0x180014252  push    rsi
0x180014253  push    rdi
0x180014254  push    r14
0x180014256  push    r15
0x180014258  lea     rbp, [rsp-180h]
0x180014260  sub     rsp, 280h
0x180014267  mov     rax, cs:__security_cookie
0x18001426e  xor     rax, rsp
0x180014271  mov     [rbp+1A0h+var_28], rax
0x180014278  mov     rcx, [rcx]
0x18001427b  lea     rax, [rsp+2A0h+var_280]
0x180014280  mov     rsi, r9
0x180014283  mov     qword ptr [rbp+1A0h+var_50], rax
0x18001428a  mov     rdi, r8
0x18001428d  mov     [rbp+1A0h+var_40], 1
0x180014294  mov     r14, rdx
0x180014297  lea     r9, [rbp+1A0h+var_48]
0x18001429e  xor     r15d, r15d
0x1800142a1  lea     rdx, aPackageuserDat; "PackageUser\\Data"
0x1800142a8  xor     r8d, r8d
0x1800142ab  mov     qword ptr [rsp+2A0h+var_280], r15; int
0x1800142b0  mov     [rbp+1A0h+var_48], r15
0x1800142b7  call    cs:__imp_SRCacheContext_Open
0x1800142bd  lea     rcx, [rbp+1A0h+var_50]
0x1800142c4  mov     ebx, eax
0x1800142c6  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x1800142cb  test    ebx, ebx
0x1800142cd  jns     short loc_180014321
0x1800142cf  mov     rcx, [rbp+1A8h]; this
0x1800142d6  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800142dd  mov     r9d, ebx; char *
0x1800142e0  mov     edx, 18Ch; void *
0x1800142e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800142ea  mov     edx, 12Ah; void *
0x1800142ef  mov     rcx, [rbp+1A8h]; this
0x1800142f6  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x1800142fd  mov     r9d, ebx; char *
0x180014300  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014305  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001430a  mov     qword ptr [rsp+2A0h+var_280], r15
0x18001430f  test    rcx, rcx
0x180014312  jz      short loc_18001431A
0x180014314  call    cs:__imp_SRCacheContext_Close
0x18001431a  mov     eax, ebx
0x18001431c  jmp     loc_1800144BA
0x180014321  cmp     qword ptr [rsp+2A0h+var_280], r15
0x180014326  setnz   al
0x180014329  test    al, al
0x18001432b  jnz     short loc_180014339
0x18001432d  mov     ebx, 80670012h
0x180014332  mov     edx, 12Bh
0x180014337  jmp     short loc_1800142EF
0x180014339  xor     edx, edx; Val
0x18001433b  mov     [rsp+2A0h+var_270], r15
0x180014340  mov     r8d, 200h; Size
0x180014346  lea     rcx, [rsp+2A0h+var_268]; void *
0x18001434b  call    memset_0
0x180014350  mov     r9d, 10h
0x180014356  mov     [rbp+1A0h+var_68], r15
0x18001435d  lea     rax, [rsp+2A0h+var_268]
0x180014362  mov     [rbp+1A0h+var_60], 100h
0x18001436d  lea     rdx, [rbp+1A0h+var_50]
0x180014374  mov     [rbp+1A0h+var_58], rax
0x18001437b  mov     rcx, r14
0x18001437e  lea     r8d, [r9+1]
0x180014382  call    _o__ui64tow_s_0
0x180014387  test    eax, eax
0x180014389  jz      short loc_1800143AD
0x18001438b  mov     rcx, [rbp+1A8h]; this
0x180014392  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\StateRepositor"...
0x180014399  mov     ebx, 8000FFFFh
0x18001439e  mov     edx, 166h; void *
0x1800143a3  mov     r9d, ebx; char *
0x1800143a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800143ab  jmp     short loc_1800143C4
0x1800143ad  lea     rdx, [rbp+1A0h+var_50]; unsigned __int16 *
0x1800143b4  lea     rcx, [rsp+2A0h+var_270]; this
0x1800143b9  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800143be  mov     ebx, eax
0x1800143c0  test    eax, eax
0x1800143c2  jns     short loc_1800143FD
0x1800143c4  mov     edx, 12Eh; void *
0x1800143c9  mov     rcx, [rbp+1A8h]; this
0x1800143d0  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x1800143d7  mov     r9d, ebx; char *
0x1800143da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800143df  mov     rcx, [rsp+2A0h+var_270]
0x1800143e4  mov     [rsp+2A0h+var_270], r15
0x1800143e9  test    rcx, rcx
0x1800143ec  jz      loc_180014305
0x1800143f2  call    cs:__imp_SRCache_Free
0x1800143f8  jmp     loc_180014305
0x1800143fd  mov     rdx, [rbp+1A0h+var_58]
0x180014404  lea     r9, [rbp+1A0h+var_48]
0x18001440b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180014410  xor     r8d, r8d
0x180014413  mov     qword ptr [rbp+1A0h+var_50], rdi
0x18001441a  mov     [rbp+1A0h+var_48], r15
0x180014421  mov     [rbp+1A0h+var_40], 1
0x180014428  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001442e  lea     rcx, [rbp+1A0h+var_50]
0x180014435  mov     ebx, eax
0x180014437  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001443c  test    ebx, ebx
0x18001443e  jns     short loc_180014465
0x180014440  mov     rcx, [rbp+1A8h]; this
0x180014447  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18001444e  mov     r9d, ebx; char *
0x180014451  mov     edx, 1B0h; void *
0x180014456  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001445b  mov     edx, 12Fh
0x180014460  jmp     loc_1800143C9
0x180014465  cmp     [rdi], r15
0x180014468  lea     rdx, aPackageuserDat; "PackageUser\\Data"
0x18001446f  lea     rcx, [rsp+2A0h+var_280]; this
0x180014474  setnz   al
0x180014477  mov     [rsi], al
0x180014479  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001447e  mov     ebx, eax
0x180014480  test    eax, eax
0x180014482  jns     short loc_18001448E
0x180014484  mov     edx, 131h
0x180014489  jmp     loc_1800143C9
0x18001448e  mov     rcx, [rsp+2A0h+var_270]
0x180014493  mov     [rsp+2A0h+var_270], r15
0x180014498  test    rcx, rcx
0x18001449b  jz      short loc_1800144A3
0x18001449d  call    cs:__imp_SRCache_Free
0x1800144a3  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x1800144a8  mov     qword ptr [rsp+2A0h+var_280], r15
0x1800144ad  test    rcx, rcx
0x1800144b0  jz      short loc_1800144B8
0x1800144b2  call    cs:__imp_SRCacheContext_Close
0x1800144b8  xor     eax, eax
0x1800144ba  mov     rcx, [rbp+1A0h+var_28]
0x1800144c1  xor     rcx, rsp; StackCookie
0x1800144c4  call    __security_check_cookie
0x1800144c9  mov     rbx, [rsp+2A0h+arg_10]
0x1800144d1  add     rsp, 280h
0x1800144d8  pop     r15
0x1800144da  pop     r14
0x1800144dc  pop     rdi
0x1800144dd  pop     rsi
0x1800144de  pop     rbp
0x1800144df  retn
```
