# StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(StateRepository::Cache::Manager_NoThrow &,ushort const *,__int64 &)

- ea: `0x18004ec78`
- end: `0x18004ef9d`
- name: `?GetByPackageFullName@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@PEBGAEA_J@Z`
- size: `805`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, const unsigned __int16 *, __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18004d9a8`

## callees

- `0x18004ec78`
- `0x18004fb30`
- `0x180098bf4`
- `0x1800f0260`
- `0x1800f10e4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18004ede2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18004ede2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18004eec6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x18004eec6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ecfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004edb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ecfa`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004edb5`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee33`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee5b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18004ee9c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004ecd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18004ecd6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18004ed91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18004ed91`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ef87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ef92`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ef87`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18004ef92`

## string_xrefs

- `0x18004ee15`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18004ef02`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18004ef2c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18004edf5`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004eedd`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004ef47`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`
- `0x18004ef6c`: `onecore\base\appmodel\StateRepository\Cache\Inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::GetByPackageFullName(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        const unsigned __int16 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  unsigned int v6; // ebx
  __int64 v7; // rcx
  int v8; // eax
  __int64 v9; // rcx
  int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rdx
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
  v6 = SRCacheContext_Open(v3, L"Package\\Index\\PackageFullName", 0, &v24);
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v20 = 1128;
    goto LABEL_32;
  }
  if ( !*(_QWORD *)v21 )
  {
    v6 = -2140733422;
    v20 = 1129;
LABEL_32:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
LABEL_18:
    v14 = *(_QWORD *)v21;
    *(_QWORD *)v21 = 0;
    if ( v14 )
      SRCacheContext_Close(v14);
    return v6;
  }
  v26 = 0;
  memset_0(v27, 0, sizeof(v27));
  v28 = 0;
  v30 = v27;
  v29 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v26, a2);
  v6 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x46C,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)(unsigned int)v8,
      v21[0]);
LABEL_16:
    v13 = v26;
    v26 = 0;
    if ( v13 )
      SRCache_Free();
    goto LABEL_18;
  }
  v23 = (int *)&v22;
  v22 = 0;
  v24 = 0;
  v25 = 1;
  v6 = SRCacheContext_OpenSubContext(*(_QWORD *)v21, v30, 0, &v24);
  if ( v25 )
  {
    v9 = *(_QWORD *)v23;
    *(_QWORD *)v23 = v24;
    if ( v9 )
      SRCacheContext_Close(v9);
  }
  if ( (v6 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B0,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)v6,
      v21[0]);
    v11 = 1136;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
      (const char *)v6,
      v21[0]);
    v12 = v22;
    v22 = 0;
    if ( v12 )
      SRCacheContext_Close(v12);
    goto LABEL_16;
  }
  if ( v22 )
  {
    v19 = SRCacheContext_EnumerateData(v22, 0, a3);
    v6 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A6,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
        (const char *)(unsigned int)v19,
        v21[0]);
      v11 = 1139;
      goto LABEL_14;
    }
  }
  v10 = SRCacheContext_AddToCache(*(_QWORD *)v21, L"Package\\Index\\PackageFullName");
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\Inc\\SRCache-Context.hpp",
      (const char *)(unsigned int)v10,
      v21[0]);
    v11 = 1142;
    goto LABEL_14;
  }
  v16 = v22;
  v22 = 0;
  if ( v16 )
    SRCacheContext_Close(v16);
  v17 = v26;
  v26 = 0;
  if ( v17 )
    SRCache_Free();
  v18 = *(_QWORD *)v21;
  *(_QWORD *)v21 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return 0;
}

```

## disassembly

```asm
0x18004ec78  push    rbp
0x18004ec7a  push    rbx
0x18004ec7b  push    rsi
0x18004ec7c  push    rdi
0x18004ec7d  push    r14
0x18004ec7f  lea     rbp, [rsp-180h]
0x18004ec87  sub     rsp, 280h
0x18004ec8e  mov     rax, cs:__security_cookie
0x18004ec95  xor     rax, rsp
0x18004ec98  mov     [rbp+1A0h+var_30], rax
0x18004ec9f  xor     r14d, r14d
0x18004eca2  mov     [rsp+2A0h+var_260], 1
0x18004eca7  mov     [r8], r14
0x18004ecaa  lea     rax, [rsp+2A0h+var_280]
0x18004ecaf  mov     rcx, [rcx]
0x18004ecb2  lea     r9, [rsp+2A0h+var_268]
0x18004ecb7  mov     rdi, r8
0x18004ecba  mov     qword ptr [rsp+2A0h+var_280], r14; int
0x18004ecbf  mov     rsi, rdx
0x18004ecc2  mov     [rsp+2A0h+var_270], rax
0x18004ecc7  xor     r8d, r8d
0x18004ecca  mov     [rsp+2A0h+var_268], r14
0x18004eccf  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18004ecd6  call    cs:__imp_SRCacheContext_Open
0x18004ecdc  mov     ebx, eax
0x18004ecde  cmp     [rsp+2A0h+var_260], r14b
0x18004ece3  jz      short loc_18004ED00
0x18004ece5  mov     r8, [rsp+2A0h+var_270]
0x18004ecea  mov     rdx, [rsp+2A0h+var_268]
0x18004ecef  mov     rcx, [r8]
0x18004ecf2  mov     [r8], rdx
0x18004ecf5  test    rcx, rcx
0x18004ecf8  jz      short loc_18004ED00
0x18004ecfa  call    cs:__imp_SRCacheContext_Close
0x18004ed00  test    ebx, ebx
0x18004ed02  js      loc_18004EF65
0x18004ed08  cmp     qword ptr [rsp+2A0h+var_280], r14
0x18004ed0d  setnz   al
0x18004ed10  test    al, al
0x18004ed12  jz      loc_18004EF1B
0x18004ed18  xor     edx, edx; Val
0x18004ed1a  mov     [rsp+2A0h+var_250], r14
0x18004ed1f  mov     r8d, 200h; Size
0x18004ed25  lea     rcx, [rsp+2A0h+var_248]; void *
0x18004ed2a  call    memset_0
0x18004ed2f  lea     rax, [rsp+2A0h+var_248]
0x18004ed34  mov     [rbp+1A0h+var_48], r14
0x18004ed3b  mov     rdx, rsi; unsigned __int16 *
0x18004ed3e  mov     [rbp+1A0h+var_38], rax
0x18004ed45  lea     rcx, [rsp+2A0h+var_250]; this
0x18004ed4a  mov     [rbp+1A0h+var_40], 100h
0x18004ed55  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z; StateRepository::Cache::Key_NoThrow::Append(ushort const *)
0x18004ed5a  mov     ebx, eax
0x18004ed5c  test    eax, eax
0x18004ed5e  js      loc_18004EEFB
0x18004ed64  mov     rdx, [rbp+1A0h+var_38]
0x18004ed6b  lea     rax, [rsp+2A0h+var_278]
0x18004ed70  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004ed75  lea     r9, [rsp+2A0h+var_268]
0x18004ed7a  xor     r8d, r8d
0x18004ed7d  mov     [rsp+2A0h+var_270], rax
0x18004ed82  mov     [rsp+2A0h+var_278], r14
0x18004ed87  mov     [rsp+2A0h+var_268], r14
0x18004ed8c  mov     [rsp+2A0h+var_260], 1
0x18004ed91  call    cs:__imp_SRCacheContext_OpenSubContext
0x18004ed97  mov     ebx, eax
0x18004ed99  cmp     [rsp+2A0h+var_260], r14b
0x18004ed9e  jz      short loc_18004EDBB
0x18004eda0  mov     r8, [rsp+2A0h+var_270]
0x18004eda5  mov     rdx, [rsp+2A0h+var_268]
0x18004edaa  mov     rcx, [r8]
0x18004edad  mov     [r8], rdx
0x18004edb0  test    rcx, rcx
0x18004edb3  jz      short loc_18004EDBB
0x18004edb5  call    cs:__imp_SRCacheContext_Close
0x18004edbb  test    ebx, ebx
0x18004edbd  js      loc_18004EF40
0x18004edc3  mov     rcx, [rsp+2A0h+var_278]
0x18004edc8  test    rcx, rcx
0x18004edcb  setnz   al
0x18004edce  test    al, al
0x18004edd0  jnz     loc_18004EEC1
0x18004edd6  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004eddb  lea     rdx, aPackageIndexPa; "Package\\Index\\PackageFullName"
0x18004ede2  call    cs:__imp_SRCacheContext_AddToCache
0x18004ede8  mov     ebx, eax
0x18004edea  test    eax, eax
0x18004edec  jns     short loc_18004EE65
0x18004edee  mov     rcx, [rbp+1A8h]; this
0x18004edf5  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18004edfc  mov     r9d, eax; char *
0x18004edff  mov     edx, 1A6h; void *
0x18004ee04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee09  mov     edx, 476h; void *
0x18004ee0e  mov     rcx, [rbp+1A8h]; this
0x18004ee15  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004ee1c  mov     r9d, ebx; char *
0x18004ee1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ee24  mov     rcx, [rsp+2A0h+var_278]
0x18004ee29  mov     [rsp+2A0h+var_278], r14
0x18004ee2e  test    rcx, rcx
0x18004ee31  jz      short loc_18004EE39
0x18004ee33  call    cs:__imp_SRCacheContext_Close
0x18004ee39  mov     rcx, [rsp+2A0h+var_250]
0x18004ee3e  mov     [rsp+2A0h+var_250], r14
0x18004ee43  test    rcx, rcx
0x18004ee46  jnz     loc_18004EF87
0x18004ee4c  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004ee51  mov     qword ptr [rsp+2A0h+var_280], r14
0x18004ee56  test    rcx, rcx
0x18004ee59  jz      short loc_18004EE61
0x18004ee5b  call    cs:__imp_SRCacheContext_Close
0x18004ee61  mov     eax, ebx
0x18004ee63  jmp     short loc_18004EEA4
0x18004ee65  mov     rcx, [rsp+2A0h+var_278]
0x18004ee6a  mov     [rsp+2A0h+var_278], r14
0x18004ee6f  test    rcx, rcx
0x18004ee72  jz      short loc_18004EE7A
0x18004ee74  call    cs:__imp_SRCacheContext_Close
0x18004ee7a  mov     rcx, [rsp+2A0h+var_250]
0x18004ee7f  mov     [rsp+2A0h+var_250], r14
0x18004ee84  test    rcx, rcx
0x18004ee87  jnz     loc_18004EF92
0x18004ee8d  mov     rcx, qword ptr [rsp+2A0h+var_280]
0x18004ee92  mov     qword ptr [rsp+2A0h+var_280], r14
0x18004ee97  test    rcx, rcx
0x18004ee9a  jz      short loc_18004EEA2
0x18004ee9c  call    cs:__imp_SRCacheContext_Close
0x18004eea2  xor     eax, eax
0x18004eea4  mov     rcx, [rbp+1A0h+var_30]
0x18004eeab  xor     rcx, rsp; StackCookie
0x18004eeae  call    __security_check_cookie
0x18004eeb3  add     rsp, 280h
0x18004eeba  pop     r14
0x18004eebc  pop     rdi
0x18004eebd  pop     rsi
0x18004eebe  pop     rbx
0x18004eebf  pop     rbp
0x18004eec0  retn
0x18004eec1  mov     r8, rdi
0x18004eec4  xor     edx, edx
0x18004eec6  call    cs:__imp_SRCacheContext_EnumerateData
0x18004eecc  mov     ebx, eax
0x18004eece  test    eax, eax
0x18004eed0  jns     loc_18004EDD6
0x18004eed6  mov     rcx, [rbp+1A8h]; this
0x18004eedd  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18004eee4  mov     r9d, eax; char *
0x18004eee7  mov     edx, 2A6h; void *
0x18004eeec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eef1  mov     edx, 473h
0x18004eef6  jmp     loc_18004EE0E
0x18004eefb  mov     rcx, [rbp+1A8h]; this
0x18004ef02  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004ef09  mov     r9d, ebx; char *
0x18004ef0c  mov     edx, 46Ch; void *
0x18004ef11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef16  jmp     loc_18004EE39
0x18004ef1b  mov     ebx, 80670012h
0x18004ef20  mov     edx, 469h; void *
0x18004ef25  mov     rcx, [rbp+1A8h]; this
0x18004ef2c  lea     r8, aOnecorePrivate_17; "onecore\\private\\base\\inc\\appmodel\\"...
0x18004ef33  mov     r9d, ebx; char *
0x18004ef36  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef3b  jmp     loc_18004EE4C
0x18004ef40  mov     rcx, [rbp+1A8h]; this
0x18004ef47  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18004ef4e  mov     r9d, ebx; char *
0x18004ef51  mov     edx, 1B0h; void *
0x18004ef56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef5b  mov     edx, 470h
0x18004ef60  jmp     loc_18004EE0E
0x18004ef65  mov     rcx, [rbp+1A8h]; this
0x18004ef6c  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\StateRepositor"...
0x18004ef73  mov     r9d, ebx; char *
0x18004ef76  mov     edx, 18Ch; void *
0x18004ef7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ef80  mov     edx, 468h
0x18004ef85  jmp     short loc_18004EF25
0x18004ef87  call    cs:__imp_SRCache_Free
0x18004ef8d  jmp     loc_18004EE4C
0x18004ef92  call    cs:__imp_SRCache_Free
0x18004ef98  jmp     loc_18004EE8D
```
