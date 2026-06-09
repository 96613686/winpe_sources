# StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001d56c`
- end: `0x18001d75c`
- name: `?Open@PackageExternalLocation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `496`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180031ba0`

## callees

- `0x180004cb0`
- `0x18000720c`
- `0x18000b840`
- `0x18000bb40`
- `0x18000dee0`
- `0x18001d56c`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d6c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d720`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d6c2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001d720`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d627`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001d735`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001d5cc`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001d5cc`

## string_xrefs

- `0x18001d5e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001d609`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`
- `0x18001d6a0`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageExternalLocation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExternalLocation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // esi
  int v8; // ebx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // [rsp+20h] [rbp-E0h]
  __int64 v17; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+48h] [rbp-B8h]
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v23; // [rsp+258h] [rbp+158h]
  __int64 v24; // [rsp+260h] [rbp+160h]
  _BYTE *v25; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v18 = &v17;
  v20 = 1;
  v17 = 0;
  v19 = 0;
  v8 = SRCacheContext_Open(v4, L"PackageExternalLocation\\Data", 0, &v19);
  wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(&v18);
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v16);
    v9 = 250;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v16);
LABEL_4:
    v10 = v17;
    v17 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v17 )
  {
    v8 = -2140733422;
    v9 = 251;
    goto LABEL_3;
  }
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v23 = 0;
  v25 = v22;
  v24 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v21, a2);
  if ( v8 < 0 )
  {
    v12 = 254;
    goto LABEL_11;
  }
  v16 = v5;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v17, v25);
  if ( v8 < 0 )
  {
    v12 = 255;
    goto LABEL_11;
  }
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v17,
         L"PackageExternalLocation\\Data");
  if ( v8 < 0 )
  {
    v12 = 257;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageExternalLocation.hpp",
      (const char *)(unsigned int)v8,
      v16);
    v13 = v21;
    v21 = 0;
    if ( v13 )
      SRCache_Free(v13);
    goto LABEL_4;
  }
  v14 = v21;
  v21 = 0;
  if ( v14 )
    SRCache_Free(v14);
  v15 = v17;
  v17 = 0;
  if ( v15 )
    SRCacheContext_Close(v15);
  return 0;
}

```

## disassembly

```asm
0x18001d56c  push    rbp
0x18001d56e  push    rbx
0x18001d56f  push    rsi
0x18001d570  push    rdi
0x18001d571  push    r14
0x18001d573  push    r15
0x18001d575  lea     rbp, [rsp-188h]
0x18001d57d  sub     rsp, 288h
0x18001d584  mov     rax, cs:__security_cookie
0x18001d58b  xor     rax, rsp
0x18001d58e  mov     [rbp+1B0h+var_40], rax
0x18001d595  mov     rcx, [rcx]
0x18001d598  lea     rax, [rsp+2B0h+var_280]
0x18001d59d  mov     rsi, r9
0x18001d5a0  mov     [rsp+2B0h+var_278], rax
0x18001d5a5  mov     rdi, r8
0x18001d5a8  mov     [rsp+2B0h+var_268], 1
0x18001d5ad  mov     r14, rdx
0x18001d5b0  lea     r9, [rsp+2B0h+var_270]
0x18001d5b5  xor     r15d, r15d
0x18001d5b8  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18001d5bf  xor     r8d, r8d
0x18001d5c2  mov     [rsp+2B0h+var_280], r15
0x18001d5c7  mov     [rsp+2B0h+var_270], r15
0x18001d5cc  call    cs:__imp_SRCacheContext_Open
0x18001d5d2  lea     rcx, [rsp+2B0h+var_278]
0x18001d5d7  mov     ebx, eax
0x18001d5d9  call    ??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)
0x18001d5de  test    ebx, ebx
0x18001d5e0  jns     short loc_18001D634
0x18001d5e2  mov     rcx, [rbp+1B8h]; this
0x18001d5e9  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d5f0  mov     r9d, ebx; char *
0x18001d5f3  mov     edx, 18Ch; void *
0x18001d5f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d5fd  mov     edx, 0FAh; void *
0x18001d602  mov     rcx, [rbp+1B8h]; this
0x18001d609  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d610  mov     r9d, ebx; char *
0x18001d613  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d618  mov     rcx, [rsp+2B0h+var_280]
0x18001d61d  mov     [rsp+2B0h+var_280], r15
0x18001d622  test    rcx, rcx
0x18001d625  jz      short loc_18001D62D
0x18001d627  call    cs:__imp_SRCacheContext_Close
0x18001d62d  mov     eax, ebx
0x18001d62f  jmp     loc_18001D73D
0x18001d634  cmp     [rsp+2B0h+var_280], r15
0x18001d639  setnz   al
0x18001d63c  test    al, al
0x18001d63e  jnz     short loc_18001D64C
0x18001d640  mov     ebx, 80670012h
0x18001d645  mov     edx, 0FBh
0x18001d64a  jmp     short loc_18001D602
0x18001d64c  xor     edx, edx; Val
0x18001d64e  mov     [rsp+2B0h+var_260], r15
0x18001d653  mov     r8d, 200h; Size
0x18001d659  lea     rcx, [rsp+2B0h+var_258]; void *
0x18001d65e  call    memset_0
0x18001d663  lea     rax, [rsp+2B0h+var_258]
0x18001d668  mov     [rbp+1B0h+var_58], r15
0x18001d66f  mov     rdx, r14; unsigned __int64
0x18001d672  mov     [rbp+1B0h+var_48], rax
0x18001d679  lea     rcx, [rsp+2B0h+var_260]; this
0x18001d67e  mov     [rbp+1B0h+var_50], 100h
0x18001d689  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001d68e  mov     ebx, eax
0x18001d690  test    eax, eax
0x18001d692  jns     short loc_18001D6CD
0x18001d694  mov     edx, 0FEh; void *
0x18001d699  mov     rcx, [rbp+1B8h]; this
0x18001d6a0  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001d6a7  mov     r9d, ebx; char *
0x18001d6aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d6af  mov     rcx, [rsp+2B0h+var_260]
0x18001d6b4  mov     [rsp+2B0h+var_260], r15
0x18001d6b9  test    rcx, rcx
0x18001d6bc  jz      loc_18001D618
0x18001d6c2  call    cs:__imp_SRCache_Free
0x18001d6c8  jmp     loc_18001D618
0x18001d6cd  mov     r8, [rbp+1B0h+var_48]
0x18001d6d4  lea     rdx, [rsp+2B0h+var_280]
0x18001d6d9  mov     rcx, rdi
0x18001d6dc  mov     qword ptr [rsp+2B0h+var_290], rsi
0x18001d6e1  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x18001d6e6  mov     ebx, eax
0x18001d6e8  test    eax, eax
0x18001d6ea  jns     short loc_18001D6F3
0x18001d6ec  mov     edx, 0FFh
0x18001d6f1  jmp     short loc_18001D699
0x18001d6f3  lea     rdx, aPackageexterna; "PackageExternalLocation\\Data"
0x18001d6fa  lea     rcx, [rsp+2B0h+var_280]; this
0x18001d6ff  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001d704  mov     ebx, eax
0x18001d706  test    eax, eax
0x18001d708  jns     short loc_18001D711
0x18001d70a  mov     edx, 101h
0x18001d70f  jmp     short loc_18001D699
0x18001d711  mov     rcx, [rsp+2B0h+var_260]
0x18001d716  mov     [rsp+2B0h+var_260], r15
0x18001d71b  test    rcx, rcx
0x18001d71e  jz      short loc_18001D726
0x18001d720  call    cs:__imp_SRCache_Free
0x18001d726  mov     rcx, [rsp+2B0h+var_280]
0x18001d72b  mov     [rsp+2B0h+var_280], r15
0x18001d730  test    rcx, rcx
0x18001d733  jz      short loc_18001D73B
0x18001d735  call    cs:__imp_SRCacheContext_Close
0x18001d73b  xor     eax, eax
0x18001d73d  mov     rcx, [rbp+1B0h+var_40]
0x18001d744  xor     rcx, rsp; StackCookie
0x18001d747  call    __security_check_cookie
0x18001d74c  add     rsp, 288h
0x18001d753  pop     r15
0x18001d755  pop     r14
0x18001d757  pop     rdi
0x18001d758  pop     rsi
0x18001d759  pop     rbx
0x18001d75a  pop     rbp
0x18001d75b  retn
```
