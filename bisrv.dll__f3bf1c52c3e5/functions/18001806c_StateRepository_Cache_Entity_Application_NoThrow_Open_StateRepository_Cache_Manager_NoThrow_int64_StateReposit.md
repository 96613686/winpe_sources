# StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001806c`
- end: `0x1800182f6`
- name: `?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `650`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001aa0c`

## callees

- `0x18001806c`
- `0x180018be0`
- `0x18001a1f0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800180cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x1800180cf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800180f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018142`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001822f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800182c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800180f3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018142`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001822f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800182c8`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001820b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001820b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800181dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800182b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800181dd`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x1800182b3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180018273`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180018273`

## string_xrefs

- `0x180018104`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180018240`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180018286`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180018124`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x1800181bb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  int *v21; // [rsp+28h] [rbp-D8h]
  __int64 v22; // [rsp+30h] [rbp-D0h] BYREF
  char v23; // [rsp+38h] [rbp-C8h]
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v25[512]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v26; // [rsp+248h] [rbp+148h]
  __int64 v27; // [rsp+250h] [rbp+150h]
  _BYTE *v28; // [rsp+258h] [rbp+158h]
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = *(_QWORD *)a1;
  v21 = v20;
  v23 = 1;
  *(_QWORD *)v20 = 0;
  v22 = 0;
  v8 = SRCacheContext_Open(v4, L"Application\\Data", 0, &v22);
  if ( v23 )
  {
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = v22;
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
      v20[0]);
    v10 = 433;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
LABEL_7:
    v11 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v11 )
      SRCacheContext_Close(v11);
    return (unsigned int)v8;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v10 = 434;
    goto LABEL_6;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v13 = 437;
    goto LABEL_14;
  }
  v21 = (int *)a3;
  v22 = 0;
  v23 = 1;
  v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
  if ( v23 )
  {
    v15 = *(_QWORD *)v21;
    *(_QWORD *)v21 = v22;
    if ( v15 )
      SRCacheContext_Close(v15);
  }
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v13 = 438;
    goto LABEL_14;
  }
  v16 = *(_QWORD *)v20;
  *a4 = *(_QWORD *)a3 != 0;
  v17 = SRCacheContext_AddToCache(v16, L"Application\\Data");
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v20[0]);
    v13 = 440;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    v14 = v24;
    v24 = 0;
    if ( v14 )
      SRCache_Free(v14);
    goto LABEL_7;
  }
  v18 = v24;
  v24 = 0;
  if ( v18 )
    SRCache_Free(v18);
  v19 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v19 )
    SRCacheContext_Close(v19);
  return 0;
}

```

## disassembly

```asm
0x18001806c  mov     [rsp-8+arg_10], rbx
0x180018071  push    rbp
0x180018072  push    rsi
0x180018073  push    rdi
0x180018074  push    r14
0x180018076  push    r15
0x180018078  lea     rbp, [rsp-170h]
0x180018080  sub     rsp, 270h
0x180018087  mov     rax, cs:__security_cookie
0x18001808e  xor     rax, rsp
0x180018091  mov     [rbp+190h+var_30], rax
0x180018098  mov     rcx, [rcx]
0x18001809b  lea     rax, [rsp+290h+var_270]
0x1800180a0  mov     r14, r9
0x1800180a3  mov     [rsp+290h+var_268], rax
0x1800180a8  mov     rdi, r8
0x1800180ab  mov     [rsp+290h+var_258], 1
0x1800180b0  mov     rsi, rdx
0x1800180b3  lea     r9, [rsp+290h+var_260]
0x1800180b8  xor     r15d, r15d
0x1800180bb  lea     rdx, aApplicationDat; "Application\\Data"
0x1800180c2  xor     r8d, r8d
0x1800180c5  mov     qword ptr [rsp+290h+var_270], r15; int
0x1800180ca  mov     [rsp+290h+var_260], r15
0x1800180cf  call    cs:__imp_SRCacheContext_Open
0x1800180d5  mov     ebx, eax
0x1800180d7  cmp     [rsp+290h+var_258], r15b
0x1800180dc  jz      short loc_1800180F9
0x1800180de  mov     r8, [rsp+290h+var_268]
0x1800180e3  mov     rdx, [rsp+290h+var_260]
0x1800180e8  mov     rcx, [r8]
0x1800180eb  mov     [r8], rdx
0x1800180ee  test    rcx, rcx
0x1800180f1  jz      short loc_1800180F9
0x1800180f3  call    cs:__imp_SRCacheContext_Close
0x1800180f9  test    ebx, ebx
0x1800180fb  jns     short loc_18001814F
0x1800180fd  mov     rcx, [rbp+198h]; this
0x180018104  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001810b  mov     r9d, ebx; char *
0x18001810e  mov     edx, 18Ch; void *
0x180018113  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018118  mov     edx, 1B1h; void *
0x18001811d  mov     rcx, [rbp+198h]; this
0x180018124  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001812b  mov     r9d, ebx; char *
0x18001812e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018133  mov     rcx, qword ptr [rsp+290h+var_270]
0x180018138  mov     qword ptr [rsp+290h+var_270], r15
0x18001813d  test    rcx, rcx
0x180018140  jz      short loc_180018148
0x180018142  call    cs:__imp_SRCacheContext_Close
0x180018148  mov     eax, ebx
0x18001814a  jmp     loc_1800182D0
0x18001814f  cmp     qword ptr [rsp+290h+var_270], r15
0x180018154  setnz   al
0x180018157  test    al, al
0x180018159  jnz     short loc_180018167
0x18001815b  mov     ebx, 80670012h
0x180018160  mov     edx, 1B2h
0x180018165  jmp     short loc_18001811D
0x180018167  xor     edx, edx; Val
0x180018169  mov     [rsp+290h+var_250], r15
0x18001816e  mov     r8d, 200h; Size
0x180018174  lea     rcx, [rsp+290h+var_248]; void *
0x180018179  call    memset_0
0x18001817e  lea     rax, [rsp+290h+var_248]
0x180018183  mov     [rbp+190h+var_48], r15
0x18001818a  mov     rdx, rsi; unsigned __int64
0x18001818d  mov     [rbp+190h+var_38], rax
0x180018194  lea     rcx, [rsp+290h+var_250]; this
0x180018199  mov     [rbp+190h+var_40], 100h
0x1800181a4  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x1800181a9  mov     ebx, eax
0x1800181ab  test    eax, eax
0x1800181ad  jns     short loc_1800181E8
0x1800181af  mov     edx, 1B5h; void *
0x1800181b4  mov     rcx, [rbp+198h]; this
0x1800181bb  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800181c2  mov     r9d, ebx; char *
0x1800181c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800181ca  mov     rcx, [rsp+290h+var_250]
0x1800181cf  mov     [rsp+290h+var_250], r15
0x1800181d4  test    rcx, rcx
0x1800181d7  jz      loc_180018133
0x1800181dd  call    cs:__imp_SRCache_Free
0x1800181e3  jmp     loc_180018133
0x1800181e8  mov     rdx, [rbp+190h+var_38]
0x1800181ef  lea     r9, [rsp+290h+var_260]
0x1800181f4  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800181f9  xor     r8d, r8d
0x1800181fc  mov     [rsp+290h+var_268], rdi
0x180018201  mov     [rsp+290h+var_260], r15
0x180018206  mov     [rsp+290h+var_258], 1
0x18001820b  call    cs:__imp_SRCacheContext_OpenSubContext
0x180018211  mov     ebx, eax
0x180018213  cmp     [rsp+290h+var_258], r15b
0x180018218  jz      short loc_180018235
0x18001821a  mov     r8, [rsp+290h+var_268]
0x18001821f  mov     rdx, [rsp+290h+var_260]
0x180018224  mov     rcx, [r8]
0x180018227  mov     [r8], rdx
0x18001822a  test    rcx, rcx
0x18001822d  jz      short loc_180018235
0x18001822f  call    cs:__imp_SRCacheContext_Close
0x180018235  test    ebx, ebx
0x180018237  jns     short loc_18001825E
0x180018239  mov     rcx, [rbp+198h]; this
0x180018240  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018247  mov     r9d, ebx; char *
0x18001824a  mov     edx, 1B0h; void *
0x18001824f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018254  mov     edx, 1B6h
0x180018259  jmp     loc_1800181B4
0x18001825e  cmp     [rdi], r15
0x180018261  lea     rdx, aApplicationDat; "Application\\Data"
0x180018268  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001826d  setnz   al
0x180018270  mov     [r14], al
0x180018273  call    cs:__imp_SRCacheContext_AddToCache
0x180018279  mov     ebx, eax
0x18001827b  test    eax, eax
0x18001827d  jns     short loc_1800182A4
0x18001827f  mov     rcx, [rbp+198h]; this
0x180018286  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001828d  mov     r9d, eax; char *
0x180018290  mov     edx, 1A6h; void *
0x180018295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001829a  mov     edx, 1B8h
0x18001829f  jmp     loc_1800181B4
0x1800182a4  mov     rcx, [rsp+290h+var_250]
0x1800182a9  mov     [rsp+290h+var_250], r15
0x1800182ae  test    rcx, rcx
0x1800182b1  jz      short loc_1800182B9
0x1800182b3  call    cs:__imp_SRCache_Free
0x1800182b9  mov     rcx, qword ptr [rsp+290h+var_270]
0x1800182be  mov     qword ptr [rsp+290h+var_270], r15
0x1800182c3  test    rcx, rcx
0x1800182c6  jz      short loc_1800182CE
0x1800182c8  call    cs:__imp_SRCacheContext_Close
0x1800182ce  xor     eax, eax
0x1800182d0  mov     rcx, [rbp+190h+var_30]
0x1800182d7  xor     rcx, rsp; StackCookie
0x1800182da  call    __security_check_cookie
0x1800182df  mov     rbx, [rsp+290h+arg_10]
0x1800182e7  add     rsp, 270h
0x1800182ee  pop     r15
0x1800182f0  pop     r14
0x1800182f2  pop     rdi
0x1800182f3  pop     rsi
0x1800182f4  pop     rbp
0x1800182f5  retn
```
