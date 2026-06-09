# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18001b308`
- end: `0x18001b5ef`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `743`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18001afd4`

## callees

- `0x180019f90`
- `0x18001a1f0`
- `0x18001b308`
- `0x18004b094`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001b542`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18001b542`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b366`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b366`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b38a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b3d9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b4d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b523`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b5a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b5ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b38a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b3d9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b4d0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b523`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b5a0`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001b5ca`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001b4ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001b4ac`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b474`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b5b5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b474`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001b5b5`

## string_xrefs

- `0x18001b39b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b4e1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b555`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001b3bb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b44d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001b501`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v21; // [rsp+28h] [rbp-D8h] BYREF
  int *v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  char v24; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+258h] [rbp+158h]
  __int64 v28; // [rsp+260h] [rbp+160h]
  _BYTE *v29; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v24 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v20 = 0;
  v22 = v20;
  v23 = 0;
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v23);
  if ( v24 )
  {
    v7 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v8 = 1128;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
LABEL_7:
    v9 = *(_QWORD *)v20;
    *(_QWORD *)v20 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return (unsigned int)v6;
  }
  if ( !*(_QWORD *)v20 )
  {
    v6 = -2140733422;
    v8 = 1129;
    goto LABEL_6;
  }
  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  v27 = 0;
  v29 = v26;
  v28 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v25, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v11,
      v20[0]);
LABEL_14:
    v12 = v25;
    v25 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_7;
  }
  v22 = (int *)&v21;
  v21 = 0;
  v23 = 0;
  v24 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v29, 0, &v23);
  if ( v24 )
  {
    v13 = *(_QWORD *)v22;
    *(_QWORD *)v22 = v23;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v14 = 1136;
    goto LABEL_21;
  }
  if ( v21 )
  {
    v16 = SRCacheContext_EnumerateData(v21, 0, a3);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v16,
        v20[0]);
      v14 = 1139;
      goto LABEL_21;
    }
  }
  v6 = StateRepository::Cache::Context_NoThrow::AddToCache(
         (StateRepository::Cache::Context_NoThrow *)v20,
         L"Package\\Index\\PackageFullName");
  if ( v6 < 0 )
  {
    v14 = 1142;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v6,
      v20[0]);
    v15 = v21;
    v21 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v17 = v21;
  v21 = 0;
  if ( v17 )
    SRCacheContext_Close(v17);
  v18 = v25;
  v25 = 0;
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
0x18001b308  push    rbp
0x18001b30a  push    rbx
0x18001b30b  push    rsi
0x18001b30c  push    rdi
0x18001b30d  push    r14
0x18001b30f  lea     rbp, [rsp-180h]
0x18001b317  sub     rsp, 280h
0x18001b31e  mov     rax, cs:__security_cookie
0x18001b325  xor     rax, rsp
0x18001b328  mov     [rbp+1A0h+var_30], rax
0x18001b32f  xor     r14d, r14d
0x18001b332  mov     [rsp+2A0h+var_260], 1
0x18001b337  mov     [r8], r14
0x18001b33a  lea     rax, [rsp+2A0h+var_280]
0x18001b33f  mov     rcx, [rcx]
0x18001b342  lea     r9, [rsp+2A0h+var_268]
0x18001b347  mov     rdi, r8
0x18001b34a  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18001b34f  mov     rsi, rdx
0x18001b352  mov     [rsp+2A0h+var_270], rax
0x18001b357  xor     r8d, r8d
0x18001b35a  mov     [rsp+2A0h+var_268], r14
0x18001b35f  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18001b366  call    cs:__imp_SRCacheContext_Open
0x18001b36c  mov     ebx, eax
0x18001b36e  cmp     [rsp+2A0h+var_260], r14b
0x18001b373  jz      short loc_18001B390
0x18001b375  mov     r8, [rsp+2A0h+var_270]
0x18001b37a  mov     rdx, [rsp+2A0h+var_268]
0x18001b37f  mov     rcx, [r8]
0x18001b382  mov     [r8], rdx
0x18001b385  test    rcx, rcx
0x18001b388  jz      short loc_18001B390
0x18001b38a  call    cs:__imp_SRCacheContext_Close
0x18001b390  test    ebx, ebx
0x18001b392  jns     short loc_18001B3E6
0x18001b394  mov     rcx, [rbp+1A8h]; this
0x18001b39b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b3a2  mov     r9d, ebx; char *
0x18001b3a5  mov     edx, 18Ch; void *
0x18001b3aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3af  mov     edx, 468h; void *
0x18001b3b4  mov     rcx, [rbp+1A8h]; this
0x18001b3bb  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b3c2  mov     r9d, ebx; char *
0x18001b3c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b3ca  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001b3cf  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001b3d4  test    rcx, rcx
0x18001b3d7  jz      short loc_18001B3DF
0x18001b3d9  call    cs:__imp_SRCacheContext_Close
0x18001b3df  mov     eax, ebx
0x18001b3e1  jmp     loc_18001B5D2
0x18001b3e6  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18001b3eb  setnz   al
0x18001b3ee  test    al, al
0x18001b3f0  jnz     short loc_18001B3FE
0x18001b3f2  mov     ebx, 80670012h
0x18001b3f7  mov     edx, 469h
0x18001b3fc  jmp     short loc_18001B3B4
0x18001b3fe  xor     edx, edx; Val
0x18001b400  mov     [rsp+2A0h+var_250], r14
0x18001b405  mov     r8d, 200h; Size
0x18001b40b  lea     rcx, [rsp+2A0h+var_248]; void *
0x18001b410  call    memset_0
0x18001b415  lea     rax, [rsp+2A0h+var_248]
0x18001b41a  mov     [rbp+1A0h+var_48], r14
0x18001b421  mov     rdx, rsi; unsigned __int16 *
0x18001b424  mov     [rbp+1A0h+var_38], rax
0x18001b42b  lea     rcx, [rsp+2A0h+var_250]; this
0x18001b430  mov     [rbp+1A0h+var_40], 100h
0x18001b43b  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18001b440  mov     ebx, eax
0x18001b442  test    eax, eax
0x18001b444  jns     short loc_18001B47F
0x18001b446  mov     rcx, [rbp+1A8h]; this
0x18001b44d  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b454  mov     r9d, eax; char *
0x18001b457  mov     edx, 46Ch; void *
0x18001b45c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b461  mov     rcx, [rsp+2A0h+var_250]
0x18001b466  mov     [rsp+2A0h+var_250], r14
0x18001b46b  test    rcx, rcx
0x18001b46e  jz      loc_18001B3CA
0x18001b474  call    cs:__imp_SRCache_Free
0x18001b47a  jmp     loc_18001B3CA
0x18001b47f  mov     rdx, [rbp+1A0h+var_38]
0x18001b486  lea     rax, [rsp+2A0h+var_278]
0x18001b48b  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001b490  lea     r9, [rsp+2A0h+var_268]
0x18001b495  xor     r8d, r8d
0x18001b498  mov     [rsp+2A0h+var_270], rax
0x18001b49d  mov     [rsp+2A0h+var_278], r14
0x18001b4a2  mov     [rsp+2A0h+var_268], r14
0x18001b4a7  mov     [rsp+2A0h+var_260], 1
0x18001b4ac  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001b4b2  mov     ebx, eax
0x18001b4b4  cmp     [rsp+2A0h+var_260], r14b
0x18001b4b9  jz      short loc_18001B4D6
0x18001b4bb  mov     r8, [rsp+2A0h+var_270]
0x18001b4c0  mov     rdx, [rsp+2A0h+var_268]
0x18001b4c5  mov     rcx, [r8]
0x18001b4c8  mov     [r8], rdx
0x18001b4cb  test    rcx, rcx
0x18001b4ce  jz      short loc_18001B4D6
0x18001b4d0  call    cs:__imp_SRCacheContext_Close
0x18001b4d6  test    ebx, ebx
0x18001b4d8  jns     short loc_18001B52E
0x18001b4da  mov     rcx, [rbp+1A8h]; this
0x18001b4e1  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b4e8  mov     r9d, ebx; char *
0x18001b4eb  mov     edx, 1B0h; void *
0x18001b4f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b4f5  mov     edx, 470h; void *
0x18001b4fa  mov     rcx, [rbp+1A8h]; this
0x18001b501  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b508  mov     r9d, ebx; char *
0x18001b50b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b510  mov     rcx, [rsp+2A0h+var_278]
0x18001b515  mov     [rsp+2A0h+var_278], r14
0x18001b51a  test    rcx, rcx
0x18001b51d  jz      loc_18001B461
0x18001b523  call    cs:__imp_SRCacheContext_Close
0x18001b529  jmp     loc_18001B461
0x18001b52e  mov     rcx, [rsp+2A0h+var_278]
0x18001b533  test    rcx, rcx
0x18001b536  setnz   al
0x18001b539  test    al, al
0x18001b53b  jz      short loc_18001B570
0x18001b53d  mov     r8, rdi
0x18001b540  xor     edx, edx
0x18001b542  call    cs:__imp_SRCacheContext_EnumerateData
0x18001b548  mov     ebx, eax
0x18001b54a  test    eax, eax
0x18001b54c  jns     short loc_18001B570
0x18001b54e  mov     rcx, [rbp+1A8h]; this
0x18001b555  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001b55c  mov     r9d, eax; char *
0x18001b55f  mov     edx, 2A6h; void *
0x18001b564  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b569  mov     edx, 473h
0x18001b56e  jmp     short loc_18001B4FA
0x18001b570  lea     rdx, aPackageIndexPa_0; "Package\\Index\\PackageFullName"
0x18001b577  lea     rcx, [rsp+2A0h+var_280]; this
0x18001b57c  call    ?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)
0x18001b581  mov     ebx, eax
0x18001b583  test    eax, eax
0x18001b585  jns     short loc_18001B591
0x18001b587  mov     edx, 476h
0x18001b58c  jmp     loc_18001B4FA
0x18001b591  mov     rcx, [rsp+2A0h+var_278]
0x18001b596  mov     [rsp+2A0h+var_278], r14
0x18001b59b  test    rcx, rcx
0x18001b59e  jz      short loc_18001B5A6
0x18001b5a0  call    cs:__imp_SRCacheContext_Close
0x18001b5a6  mov     rcx, [rsp+2A0h+var_250]
0x18001b5ab  mov     [rsp+2A0h+var_250], r14
0x18001b5b0  test    rcx, rcx
0x18001b5b3  jz      short loc_18001B5BB
0x18001b5b5  call    cs:__imp_SRCache_Free
0x18001b5bb  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001b5c0  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001b5c5  test    rcx, rcx
0x18001b5c8  jz      short loc_18001B5D0
0x18001b5ca  call    cs:__imp_SRCacheContext_Close
0x18001b5d0  xor     eax, eax
0x18001b5d2  mov     rcx, [rbp+1A0h+var_30]
0x18001b5d9  xor     rcx, rsp; StackCookie
0x18001b5dc  call    __security_check_cookie
0x18001b5e1  add     rsp, 280h
0x18001b5e8  pop     r14
0x18001b5ea  pop     rdi
0x18001b5eb  pop     rsi
0x18001b5ec  pop     rbx
0x18001b5ed  pop     rbp
0x18001b5ee  retn
```
