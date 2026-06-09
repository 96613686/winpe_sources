# StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x1800052b0`
- end: `0x180005514`
- name: `?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001880c`

## callees

- `0x1800052b0`
- `0x1800055d0`
- `0x180007c78`
- `0x1800093b0`
- `0x18000e960`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005310`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180005310`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000533a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000538f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800053db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800054e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000533a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000538f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800053db`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800054e6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800054cb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180005467`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800054cb`

## string_xrefs

- `0x180005351`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000536c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x1800053b5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x180005445`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v5; // r14d
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-C8h]
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  char v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2B8h] [rbp+1B8h]

  v4 = *(_QWORD *)a1;
  v5 = (int)a4;
  v22 = &v21;
  v24 = 1;
  v21 = 0;
  v23 = 0;
  v8 = SRCacheContext_Open(v4, L"Activation\\Data", 0, &v23);
  if ( v24 )
  {
    v9 = *v22;
    *v22 = v23;
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
      v19);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x187,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v20);
LABEL_6:
    v10 = v21;
    v21 = 0;
    if ( v10 )
      SRCacheContext_Close(v10);
    return (unsigned int)v8;
  }
  if ( !v21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)0x80670012LL,
      v19);
    v12 = v21;
    v21 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    return 2154233874LL;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  if ( v8 < 0 )
  {
    v13 = 395;
    goto LABEL_15;
  }
  v19 = v5;
  v8 = StateRepository::Cache::Context_NoThrow::OpenSubContext(a3, &v21, v29);
  if ( v8 < 0 )
  {
    v13 = 396;
    goto LABEL_15;
  }
  v8 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)&v21,
         L"Activation\\Data");
  if ( v8 < 0 )
  {
    v13 = 398;
LABEL_15:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)(unsigned int)v8,
      v19);
    v15 = v25;
    v25 = 0;
    if ( v15 )
      SRCache_Free(v15, v14);
    goto LABEL_6;
  }
  v17 = v25;
  v25 = 0;
  if ( v17 )
    SRCache_Free(v17, v16);
  v18 = v21;
  v21 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x1800052b0  push    rbp
0x1800052b2  push    rbx
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  push    r14
0x1800052b7  push    r15
0x1800052b9  lea     rbp, [rsp-188h]
0x1800052c1  sub     rsp, 288h
0x1800052c8  mov     rax, cs:__security_cookie
0x1800052cf  xor     rax, rsp
0x1800052d2  mov     [rbp+1B0h+var_40], rax
0x1800052d9  mov     rcx, [rcx]
0x1800052dc  lea     rax, [rsp+2B0h+var_280]
0x1800052e1  mov     r14, r9
0x1800052e4  mov     [rsp+2B0h+var_278], rax
0x1800052e9  mov     rsi, r8
0x1800052ec  mov     [rsp+2B0h+var_268], 1
0x1800052f1  mov     rdi, rdx
0x1800052f4  lea     r9, [rsp+2B0h+var_270]
0x1800052f9  xor     r15d, r15d
0x1800052fc  lea     rdx, aActivationData; "Activation\\Data"
0x180005303  xor     r8d, r8d
0x180005306  mov     [rsp+2B0h+var_280], r15
0x18000530b  mov     [rsp+2B0h+var_270], r15
0x180005310  call    cs:__imp_SRCacheContext_Open
0x180005317  nop     dword ptr [rax+rax+00h]
0x18000531c  mov     ebx, eax
0x18000531e  cmp     [rsp+2B0h+var_268], r15b
0x180005323  jz      short loc_180005346
0x180005325  mov     r8, [rsp+2B0h+var_278]
0x18000532a  mov     rdx, [rsp+2B0h+var_270]
0x18000532f  mov     rcx, [r8]
0x180005332  mov     [r8], rdx
0x180005335  test    rcx, rcx
0x180005338  jz      short loc_180005346
0x18000533a  call    cs:__imp_SRCacheContext_Close
0x180005341  nop     dword ptr [rax+rax+00h]
0x180005346  test    ebx, ebx
0x180005348  jns     short loc_1800053A2
0x18000534a  mov     rcx, [rbp+1B8h]; this
0x180005351  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005358  mov     r9d, ebx; char *
0x18000535b  mov     edx, 18Ch; void *
0x180005360  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005365  mov     rcx, [rbp+1B8h]; this
0x18000536c  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005373  mov     r9d, ebx; char *
0x180005376  mov     edx, 187h; void *
0x18000537b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005380  mov     rcx, [rsp+2B0h+var_280]
0x180005385  mov     [rsp+2B0h+var_280], r15
0x18000538a  test    rcx, rcx
0x18000538d  jz      short loc_18000539B
0x18000538f  call    cs:__imp_SRCacheContext_Close
0x180005396  nop     dword ptr [rax+rax+00h]
0x18000539b  mov     eax, ebx
0x18000539d  jmp     loc_1800054F4
0x1800053a2  cmp     [rsp+2B0h+var_280], r15
0x1800053a7  setnz   al
0x1800053aa  test    al, al
0x1800053ac  jnz     short loc_1800053F1
0x1800053ae  mov     rcx, [rbp+1B8h]; this
0x1800053b5  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800053bc  mov     r9d, 80670012h; char *
0x1800053c2  mov     edx, 188h; void *
0x1800053c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800053cc  mov     rcx, [rsp+2B0h+var_280]
0x1800053d1  mov     [rsp+2B0h+var_280], r15
0x1800053d6  test    rcx, rcx
0x1800053d9  jz      short loc_1800053E7
0x1800053db  call    cs:__imp_SRCacheContext_Close
0x1800053e2  nop     dword ptr [rax+rax+00h]
0x1800053e7  mov     eax, 80670012h
0x1800053ec  jmp     loc_1800054F4
0x1800053f1  xor     edx, edx; Val
0x1800053f3  mov     [rsp+2B0h+var_260], r15
0x1800053f8  mov     r8d, 200h; Size
0x1800053fe  lea     rcx, [rsp+2B0h+var_258]; void *
0x180005403  call    memset_0
0x180005408  lea     rax, [rsp+2B0h+var_258]
0x18000540d  mov     [rbp+1B0h+var_58], r15
0x180005414  mov     rdx, rdi; unsigned __int64
0x180005417  mov     [rbp+1B0h+var_48], rax
0x18000541e  lea     rcx, [rsp+2B0h+var_260]; this
0x180005423  mov     [rbp+1B0h+var_50], 100h
0x18000542e  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180005433  mov     ebx, eax
0x180005435  test    eax, eax
0x180005437  jns     short loc_180005478
0x180005439  mov     edx, 18Bh; void *
0x18000543e  mov     rcx, [rbp+1B8h]; this
0x180005445  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000544c  mov     r9d, ebx; char *
0x18000544f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005454  mov     rcx, [rsp+2B0h+var_260]
0x180005459  mov     [rsp+2B0h+var_260], r15
0x18000545e  test    rcx, rcx
0x180005461  jz      loc_180005380
0x180005467  call    cs:__imp_SRCache_Free
0x18000546e  nop     dword ptr [rax+rax+00h]
0x180005473  jmp     loc_180005380
0x180005478  mov     r8, [rbp+1B0h+var_48]
0x18000547f  lea     rdx, [rsp+2B0h+var_280]
0x180005484  mov     rcx, rsi
0x180005487  mov     qword ptr [rsp+2B0h+var_290], r14
0x18000548c  call    ?OpenSubContext@Context_NoThrow@Cache@StateRepository@@QEAAJAEAV123@PEBGW4SRCacheFlags@@AEA_N@Z; StateRepository::Cache::Context_NoThrow::OpenSubContext(StateRepository::Cache::Context_NoThrow &,ushort const *,SRCacheFlags,bool &)
0x180005491  mov     ebx, eax
0x180005493  test    eax, eax
0x180005495  jns     short loc_18000549E
0x180005497  mov     edx, 18Ch
0x18000549c  jmp     short loc_18000543E
0x18000549e  lea     rdx, aActivationData; "Activation\\Data"
0x1800054a5  lea     rcx, [rsp+2B0h+var_280]; this
0x1800054aa  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x1800054af  mov     ebx, eax
0x1800054b1  test    eax, eax
0x1800054b3  jns     short loc_1800054BC
0x1800054b5  mov     edx, 18Eh
0x1800054ba  jmp     short loc_18000543E
0x1800054bc  mov     rcx, [rsp+2B0h+var_260]
0x1800054c1  mov     [rsp+2B0h+var_260], r15
0x1800054c6  test    rcx, rcx
0x1800054c9  jz      short loc_1800054D7
0x1800054cb  call    cs:__imp_SRCache_Free
0x1800054d2  nop     dword ptr [rax+rax+00h]
0x1800054d7  mov     rcx, [rsp+2B0h+var_280]
0x1800054dc  mov     [rsp+2B0h+var_280], r15
0x1800054e1  test    rcx, rcx
0x1800054e4  jz      short loc_1800054F2
0x1800054e6  call    cs:__imp_SRCacheContext_Close
0x1800054ed  nop     dword ptr [rax+rax+00h]
0x1800054f2  xor     eax, eax
0x1800054f4  mov     rcx, [rbp+1B0h+var_40]
0x1800054fb  xor     rcx, rsp; StackCookie
0x1800054fe  call    __security_check_cookie
0x180005503  add     rsp, 288h
0x18000550a  pop     r15
0x18000550c  pop     r14
0x18000550e  pop     rdi
0x18000550f  pop     rsi
0x180005510  pop     rbx
0x180005511  pop     rbp
0x180005512  retn
```
