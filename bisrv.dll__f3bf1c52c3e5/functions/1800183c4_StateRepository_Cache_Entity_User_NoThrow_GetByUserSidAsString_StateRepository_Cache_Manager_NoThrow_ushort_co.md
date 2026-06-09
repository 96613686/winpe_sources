# StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x1800183c4`
- end: `0x1800186c7`
- name: `?GetByUserSidAsString@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `771`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x180018eb8`

## callees

- `0x1800183c4`
- `0x180019f90`
- `0x18001a1f0`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800185fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x1800185fe`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180018422`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180018422`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018446`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018495`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001858c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800185df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018678`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800186a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018446`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018495`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001858c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800185df`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180018678`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800186a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180018568`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180018568`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018530`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001868d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018530`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001868d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180018638`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180018638`

## string_xrefs

- `0x180018457`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001859d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180018611`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001864b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180018477`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180018509`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x1800185bd`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x18001841b`: `User\Index\UserSid`
- `0x180018631`: `User\Index\UserSid`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::GetByUserSidAsString(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rcx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+28h] [rbp-D8h] BYREF
  int *v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  char v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v27[512]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+258h] [rbp+158h]
  __int64 v29; // [rsp+260h] [rbp+160h]
  _BYTE *v30; // [rsp+268h] [rbp+168h]
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  v25 = 1;
  *a3 = 0;
  v3 = *(_QWORD *)a1;
  *(_QWORD *)v21 = 0;
  v23 = v21;
  v24 = 0;
  v6 = SRCacheContext_Open(v3, L"User\\Index\\UserSid", 0, &v24);
  if ( v25 )
  {
    v7 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v7 )
      SRCacheContext_Close(v7);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v8 = 185;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v21[0]);
LABEL_7:
    v9 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v9 )
      SRCacheContext_Close(v9);
    return v6;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v8 = 186;
    goto LABEL_6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v11 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v11,
      v21[0]);
LABEL_14:
    v12 = v26;
    v26 = 0;
    if ( v12 )
      SRCache_Free(v12);
    goto LABEL_7;
  }
  v23 = (int *)&v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
  if ( v25 )
  {
    v13 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v13 )
      SRCacheContext_Close(v13);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v14 = 193;
    goto LABEL_21;
  }
  if ( v22 )
  {
    v16 = SRCacheContext_EnumerateData(v22, 0, a3);
    v6 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v16,
        v21[0]);
      v14 = 196;
      goto LABEL_21;
    }
  }
  v17 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"User\\Index\\UserSid");
  v6 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v21[0]);
    v14 = 199;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)v6,
      v21[0]);
    v15 = v22;
    v22 = 0;
    if ( v15 )
      SRCacheContext_Close(v15);
    goto LABEL_14;
  }
  v18 = v22;
  v22 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  v19 = v26;
  v26 = 0;
  if ( v19 )
    SRCache_Free(v19);
  v20 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v20 )
    SRCacheContext_Close(v20);
  return 0;
}

```

## disassembly

```asm
0x1800183c4  push    rbp
0x1800183c6  push    rbx
0x1800183c7  push    rsi
0x1800183c8  push    rdi
0x1800183c9  push    r14
0x1800183cb  lea     rbp, [rsp-180h]
0x1800183d3  sub     rsp, 280h
0x1800183da  mov     rax, cs:__security_cookie
0x1800183e1  xor     rax, rsp
0x1800183e4  mov     [rbp+1A0h+var_30], rax
0x1800183eb  xor     r14d, r14d
0x1800183ee  mov     [rsp+2A0h+var_260], 1
0x1800183f3  mov     [r8], r14
0x1800183f6  lea     rax, [rsp+2A0h+var_280]
0x1800183fb  mov     rcx, [rcx]
0x1800183fe  lea     r9, [rsp+2A0h+var_268]
0x180018403  mov     rdi, r8
0x180018406  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18001840b  mov     rsi, rdx
0x18001840e  mov     [rsp+2A0h+var_270], rax
0x180018413  xor     r8d, r8d
0x180018416  mov     [rsp+2A0h+var_268], r14
0x18001841b  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x180018422  call    cs:__imp_SRCacheContext_Open
0x180018428  mov     ebx, eax
0x18001842a  cmp     [rsp+2A0h+var_260], r14b
0x18001842f  jz      short loc_18001844C
0x180018431  mov     r8, [rsp+2A0h+var_270]
0x180018436  mov     rdx, [rsp+2A0h+var_268]
0x18001843b  mov     rcx, [r8]
0x18001843e  mov     [r8], rdx
0x180018441  test    rcx, rcx
0x180018444  jz      short loc_18001844C
0x180018446  call    cs:__imp_SRCacheContext_Close
0x18001844c  test    ebx, ebx
0x18001844e  jns     short loc_1800184A2
0x180018450  mov     rcx, [rbp+1A8h]; this
0x180018457  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001845e  mov     r9d, ebx; char *
0x180018461  mov     edx, 18Ch; void *
0x180018466  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001846b  mov     edx, 0B9h; void *
0x180018470  mov     rcx, [rbp+1A8h]; this
0x180018477  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001847e  mov     r9d, ebx; char *
0x180018481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018486  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001848b  mov     qword ptr [rsp+2A0h+var_280], r14
0x180018490  test    rcx, rcx
0x180018493  jz      short loc_18001849B
0x180018495  call    cs:__imp_SRCacheContext_Close
0x18001849b  mov     eax, ebx
0x18001849d  jmp     loc_1800186AA
0x1800184a2  cmp     qword ptr [rsp+2A0h+var_280], r14
0x1800184a7  setnz   al
0x1800184aa  test    al, al
0x1800184ac  jnz     short loc_1800184BA
0x1800184ae  mov     ebx, 80670012h
0x1800184b3  mov     edx, 0BAh
0x1800184b8  jmp     short loc_180018470
0x1800184ba  xor     edx, edx; Val
0x1800184bc  mov     [rsp+2A0h+var_250], r14
0x1800184c1  mov     r8d, 200h; Size
0x1800184c7  lea     rcx, [rsp+2A0h+var_248]; void *
0x1800184cc  call    memset_0
0x1800184d1  lea     rax, [rsp+2A0h+var_248]
0x1800184d6  mov     [rbp+1A0h+var_48], r14
0x1800184dd  mov     rdx, rsi; unsigned __int16 *
0x1800184e0  mov     [rbp+1A0h+var_38], rax
0x1800184e7  lea     rcx, [rsp+2A0h+var_250]; this
0x1800184ec  mov     [rbp+1A0h+var_40], 100h
0x1800184f7  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x1800184fc  mov     ebx, eax
0x1800184fe  test    eax, eax
0x180018500  jns     short loc_18001853B
0x180018502  mov     rcx, [rbp+1A8h]; this
0x180018509  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018510  mov     r9d, eax; char *
0x180018513  mov     edx, 0BDh; void *
0x180018518  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001851d  mov     rcx, [rsp+2A0h+var_250]
0x180018522  mov     [rsp+2A0h+var_250], r14
0x180018527  test    rcx, rcx
0x18001852a  jz      loc_180018486
0x180018530  call    cs:__imp_SRCache_Free
0x180018536  jmp     loc_180018486
0x18001853b  mov     rdx, [rbp+1A0h+var_38]
0x180018542  lea     rax, [rsp+2A0h+var_278]
0x180018547  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18001854c  lea     r9, [rsp+2A0h+var_268]
0x180018551  xor     r8d, r8d
0x180018554  mov     [rsp+2A0h+var_270], rax
0x180018559  mov     [rsp+2A0h+var_278], r14
0x18001855e  mov     [rsp+2A0h+var_268], r14
0x180018563  mov     [rsp+2A0h+var_260], 1
0x180018568  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001856e  mov     ebx, eax
0x180018570  cmp     [rsp+2A0h+var_260], r14b
0x180018575  jz      short loc_180018592
0x180018577  mov     r8, [rsp+2A0h+var_270]
0x18001857c  mov     rdx, [rsp+2A0h+var_268]
0x180018581  mov     rcx, [r8]
0x180018584  mov     [r8], rdx
0x180018587  test    rcx, rcx
0x18001858a  jz      short loc_180018592
0x18001858c  call    cs:__imp_SRCacheContext_Close
0x180018592  test    ebx, ebx
0x180018594  jns     short loc_1800185EA
0x180018596  mov     rcx, [rbp+1A8h]; this
0x18001859d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800185a4  mov     r9d, ebx; char *
0x1800185a7  mov     edx, 1B0h; void *
0x1800185ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185b1  mov     edx, 0C1h; void *
0x1800185b6  mov     rcx, [rbp+1A8h]; this
0x1800185bd  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800185c4  mov     r9d, ebx; char *
0x1800185c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800185cc  mov     rcx, [rsp+2A0h+var_278]
0x1800185d1  mov     [rsp+2A0h+var_278], r14
0x1800185d6  test    rcx, rcx
0x1800185d9  jz      loc_18001851D
0x1800185df  call    cs:__imp_SRCacheContext_Close
0x1800185e5  jmp     loc_18001851D
0x1800185ea  mov     rcx, [rsp+2A0h+var_278]
0x1800185ef  test    rcx, rcx
0x1800185f2  setnz   al
0x1800185f5  test    al, al
0x1800185f7  jz      short loc_18001862C
0x1800185f9  mov     r8, rdi
0x1800185fc  xor     edx, edx
0x1800185fe  call    cs:__imp_SRCacheContext_EnumerateData
0x180018604  mov     ebx, eax
0x180018606  test    eax, eax
0x180018608  jns     short loc_18001862C
0x18001860a  mov     rcx, [rbp+1A8h]; this
0x180018611  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018618  mov     r9d, eax; char *
0x18001861b  mov     edx, 2A6h; void *
0x180018620  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018625  mov     edx, 0C4h
0x18001862a  jmp     short loc_1800185B6
0x18001862c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180018631  lea     rdx, aUserIndexUsers; "User\\Index\\UserSid"
0x180018638  call    cs:__imp_SRCacheContext_AddToCache
0x18001863e  mov     ebx, eax
0x180018640  test    eax, eax
0x180018642  jns     short loc_180018669
0x180018644  mov     rcx, [rbp+1A8h]; this
0x18001864b  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018652  mov     r9d, eax; char *
0x180018655  mov     edx, 1A6h; void *
0x18001865a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001865f  mov     edx, 0C7h
0x180018664  jmp     loc_1800185B6
0x180018669  mov     rcx, [rsp+2A0h+var_278]
0x18001866e  mov     [rsp+2A0h+var_278], r14
0x180018673  test    rcx, rcx
0x180018676  jz      short loc_18001867E
0x180018678  call    cs:__imp_SRCacheContext_Close
0x18001867e  mov     rcx, [rsp+2A0h+var_250]
0x180018683  mov     [rsp+2A0h+var_250], r14
0x180018688  test    rcx, rcx
0x18001868b  jz      short loc_180018693
0x18001868d  call    cs:__imp_SRCache_Free
0x180018693  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x180018698  mov     qword ptr [rsp+2A0h+var_280], r14
0x18001869d  test    rcx, rcx
0x1800186a0  jz      short loc_1800186A8
0x1800186a2  call    cs:__imp_SRCacheContext_Close
0x1800186a8  xor     eax, eax
0x1800186aa  mov     rcx, [rbp+1A0h+var_30]
0x1800186b1  xor     rcx, rsp; StackCookie
0x1800186b4  call    __security_check_cookie
0x1800186b9  add     rsp, 280h
0x1800186c0  pop     r14
0x1800186c2  pop     rdi
0x1800186c3  pop     rsi
0x1800186c4  pop     rbx
0x1800186c5  pop     rbp
0x1800186c6  retn
```
