# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800ca4c8`
- end: `0x1800ca6f8`
- name: `?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `560`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800ca3e4`

## callees

- `0x18002f340`
- `0x180058768`
- `0x1800ca4c8`
- `0x1800caf60`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ca528`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800ca528`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca54c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca615`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca65e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca54c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca615`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800ca65e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ca600`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ca649`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ca600`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800ca649`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ca5e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800ca5e1`

## string_xrefs

- `0x1800ca514`: `ApplicationExtension\Data`
- `0x1800ca5da`: `ApplicationExtension\Data`
- `0x1800ca62b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800ca696`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800ca6ae`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x1800ca6dd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // esi
  int v8; // ebx
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rdx
  int v18; // [rsp+20h] [rbp-E0h]
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v20; // [rsp+38h] [rbp-C8h]
  __int64 v21; // [rsp+40h] [rbp-C0h] BYREF
  char v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v24[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v25; // [rsp+258h] [rbp+158h]
  __int64 v26; // [rsp+260h] [rbp+160h]
  _BYTE *v27; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v20 = &v19;
  v22 = 1;
  v19 = 0;
  v21 = 0;
  v8 = SRCacheContext_Open(v4, L"ApplicationExtension\\Data", 0, &v21);
  if ( v22 )
  {
    v9 = *v20;
    *v20 = v21;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v18);
    v17 = 364;
    goto LABEL_21;
  }
  if ( !v19 )
  {
    v8 = -2140733422;
    v17 = 365;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v8,
      v18);
    goto LABEL_17;
  }
  v23 = 0;
  memset_0(v24, 0, sizeof(v24));
  v25 = 0;
  v27 = v24;
  v26 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v23, a2);
  if ( v8 < 0 )
  {
    v14 = 368;
  }
  else
  {
    v18 = v5;
    v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v19, v27);
    if ( v8 < 0 )
    {
      v14 = 369;
    }
    else
    {
      v10 = SRCacheContext_AddToCache(v19, L"ApplicationExtension\\Data");
      v8 = v10;
      if ( v10 >= 0 )
      {
        v11 = v23;
        v23 = 0;
        if ( v11 )
          SRCache_Free(v11);
        v12 = v19;
        v19 = 0;
        if ( v12 )
          SRCacheContext_Close(v12);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v10,
        v5);
      v14 = 371;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)(unsigned int)v8,
    v18);
  v15 = v23;
  v23 = 0;
  if ( v15 )
    SRCache_Free(v15);
LABEL_17:
  v16 = v19;
  v19 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800ca4c8  push    rbp
0x1800ca4ca  push    rbx
0x1800ca4cb  push    rsi
0x1800ca4cc  push    rdi
0x1800ca4cd  push    r14
0x1800ca4cf  push    r15
0x1800ca4d1  lea     rbp, [rsp-188h]
0x1800ca4d9  sub     rsp, 288h
0x1800ca4e0  mov     rax, cs:__security_cookie
0x1800ca4e7  xor     rax, rsp
0x1800ca4ea  mov     [rbp+1B0h+var_40], rax
0x1800ca4f1  mov     rcx, [rcx]
0x1800ca4f4  lea     rax, [rsp+2B0h+var_280]
0x1800ca4f9  mov     rsi, r9
0x1800ca4fc  mov     [rsp+2B0h+var_278], rax
0x1800ca501  mov     rdi, r8
0x1800ca504  mov     [rsp+2B0h+var_268], 1
0x1800ca509  mov     r14, rdx
0x1800ca50c  lea     r9, [rsp+2B0h+var_270]
0x1800ca511  xor     r15d, r15d
0x1800ca514  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800ca51b  xor     r8d, r8d
0x1800ca51e  mov     [rsp+2B0h+var_280], r15
0x1800ca523  mov     [rsp+2B0h+var_270], r15
0x1800ca528  call    cs:__imp_SRCacheContext_Open
0x1800ca52e  mov     ebx, eax
0x1800ca530  cmp     [rsp+2B0h+var_268], r15b
0x1800ca535  jz      short loc_1800CA552
0x1800ca537  mov     r8, [rsp+2B0h+var_278]
0x1800ca53c  mov     rdx, [rsp+2B0h+var_270]
0x1800ca541  mov     rcx, [r8]
0x1800ca544  mov     [r8], rdx
0x1800ca547  test    rcx, rcx
0x1800ca54a  jz      short loc_1800CA552
0x1800ca54c  call    cs:__imp_SRCacheContext_Close
0x1800ca552  test    ebx, ebx
0x1800ca554  js      loc_1800CA6D6
0x1800ca55a  cmp     [rsp+2B0h+var_280], r15
0x1800ca55f  setnz   al
0x1800ca562  test    al, al
0x1800ca564  jz      loc_1800CA685
0x1800ca56a  xor     edx, edx; Val
0x1800ca56c  mov     [rsp+2B0h+var_260], r15
0x1800ca571  mov     r8d, 200h; Size
0x1800ca577  lea     rcx, [rsp+2B0h+var_258]; void *
0x1800ca57c  call    memset_0
0x1800ca581  lea     rax, [rsp+2B0h+var_258]
0x1800ca586  mov     [rbp+1B0h+var_58], r15
0x1800ca58d  mov     rdx, r14; unsigned __int64
0x1800ca590  mov     [rbp+1B0h+var_48], rax
0x1800ca597  lea     rcx, [rsp+2B0h+var_260]; this
0x1800ca59c  mov     [rbp+1B0h+var_50], 100h
0x1800ca5a7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800ca5ac  mov     ebx, eax
0x1800ca5ae  test    eax, eax
0x1800ca5b0  js      short loc_1800CA61F
0x1800ca5b2  mov     r8, [rbp+1B0h+var_48]
0x1800ca5b9  lea     rdx, [rsp+2B0h+var_280]
0x1800ca5be  mov     rcx, rdi
0x1800ca5c1  mov     qword ptr [rsp+2B0h+var_290], rsi; int
0x1800ca5c6  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x1800ca5cb  mov     ebx, eax
0x1800ca5cd  test    eax, eax
0x1800ca5cf  js      loc_1800CA6CC
0x1800ca5d5  mov     rcx, [rsp+2B0h+var_280]
0x1800ca5da  lea     rdx, aApplicationext_0; "ApplicationExtension\\Data"
0x1800ca5e1  call    cs:__imp_SRCacheContext_AddToCache
0x1800ca5e7  mov     ebx, eax
0x1800ca5e9  test    eax, eax
0x1800ca5eb  js      loc_1800CA6A7
0x1800ca5f1  mov     rcx, [rsp+2B0h+var_260]
0x1800ca5f6  mov     [rsp+2B0h+var_260], r15
0x1800ca5fb  test    rcx, rcx
0x1800ca5fe  jz      short loc_1800CA606
0x1800ca600  call    cs:__imp_SRCache_Free
0x1800ca606  mov     rcx, [rsp+2B0h+var_280]
0x1800ca60b  mov     [rsp+2B0h+var_280], r15
0x1800ca610  test    rcx, rcx
0x1800ca613  jz      short loc_1800CA61B
0x1800ca615  call    cs:__imp_SRCacheContext_Close
0x1800ca61b  xor     eax, eax
0x1800ca61d  jmp     short loc_1800CA666
0x1800ca61f  mov     edx, 170h; void *
0x1800ca624  mov     rcx, [rbp+1B8h]; this
0x1800ca62b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ca632  mov     r9d, ebx; char *
0x1800ca635  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca63a  mov     rcx, [rsp+2B0h+var_260]
0x1800ca63f  mov     [rsp+2B0h+var_260], r15
0x1800ca644  test    rcx, rcx
0x1800ca647  jz      short loc_1800CA64F
0x1800ca649  call    cs:__imp_SRCache_Free
0x1800ca64f  mov     rcx, [rsp+2B0h+var_280]
0x1800ca654  mov     [rsp+2B0h+var_280], r15
0x1800ca659  test    rcx, rcx
0x1800ca65c  jz      short loc_1800CA664
0x1800ca65e  call    cs:__imp_SRCacheContext_Close
0x1800ca664  mov     eax, ebx
0x1800ca666  mov     rcx, [rbp+1B0h+var_40]
0x1800ca66d  xor     rcx, rsp; StackCookie
0x1800ca670  call    __security_check_cookie
0x1800ca675  add     rsp, 288h
0x1800ca67c  pop     r15
0x1800ca67e  pop     r14
0x1800ca680  pop     rdi
0x1800ca681  pop     rsi
0x1800ca682  pop     rbx
0x1800ca683  pop     rbp
0x1800ca684  retn
0x1800ca685  mov     ebx, 80670012h
0x1800ca68a  mov     edx, 16Dh; void *
0x1800ca68f  mov     rcx, [rbp+1B8h]; this
0x1800ca696  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ca69d  mov     r9d, ebx; char *
0x1800ca6a0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca6a5  jmp     short loc_1800CA64F
0x1800ca6a7  mov     rcx, [rbp+1B8h]; this
0x1800ca6ae  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ca6b5  mov     r9d, ebx; char *
0x1800ca6b8  mov     edx, 1A6h; void *
0x1800ca6bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca6c2  mov     edx, 173h
0x1800ca6c7  jmp     loc_1800CA624
0x1800ca6cc  mov     edx, 171h
0x1800ca6d1  jmp     loc_1800CA624
0x1800ca6d6  mov     rcx, [rbp+1B8h]; this
0x1800ca6dd  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800ca6e4  mov     r9d, ebx; char *
0x1800ca6e7  mov     edx, 18Ch; void *
0x1800ca6ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800ca6f1  mov     edx, 16Ch
0x1800ca6f6  jmp     short loc_1800CA68F
```
