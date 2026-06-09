# StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x18001b988`
- end: `0x18001bc12`
- name: `?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `650`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001afd4`

## callees

- `0x180018be0`
- `0x18001a1f0`
- `0x18001b988`
- `0x18009467a`
- `0x1800946a0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b9eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x18001b9eb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ba0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ba5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bb4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bbe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ba0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001ba5e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bb4b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001bbe4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bb27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x18001bb27`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001baf9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bbcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001baf9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18001bbcf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001bb8f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18001bb8f`

## string_xrefs

- `0x18001ba20`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bb5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001bba2`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18001ba40`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`
- `0x18001bad7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Open(
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
  v8 = SRCacheContext_Open(v4, L"Package\\Data", 0, &v22);
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
    v10 = 1192;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
    v10 = 1193;
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
    v13 = 1196;
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
    v13 = 1197;
    goto LABEL_14;
  }
  v16 = *(_QWORD *)v20;
  *a4 = *(_QWORD *)a3 != 0;
  v17 = SRCacheContext_AddToCache(v16, L"Package\\Data");
  v8 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A6,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
      (const char *)(unsigned int)v17,
      v20[0]);
    v13 = 1199;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Package.hpp",
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
0x18001b988  mov     [rsp-8+arg_10], rbx
0x18001b98d  push    rbp
0x18001b98e  push    rsi
0x18001b98f  push    rdi
0x18001b990  push    r14
0x18001b992  push    r15
0x18001b994  lea     rbp, [rsp-170h]
0x18001b99c  sub     rsp, 270h
0x18001b9a3  mov     rax, cs:__security_cookie
0x18001b9aa  xor     rax, rsp
0x18001b9ad  mov     [rbp+190h+var_30], rax
0x18001b9b4  mov     rcx, [rcx]
0x18001b9b7  lea     rax, [rsp+290h+var_270]
0x18001b9bc  mov     r14, r9
0x18001b9bf  mov     [rsp+290h+var_268], rax
0x18001b9c4  mov     rdi, r8
0x18001b9c7  mov     [rsp+290h+var_258], 1
0x18001b9cc  mov     rsi, rdx
0x18001b9cf  lea     r9, [rsp+290h+var_260]
0x18001b9d4  xor     r15d, r15d
0x18001b9d7  lea     rdx, aPackageData; "Package\\Data"
0x18001b9de  xor     r8d, r8d
0x18001b9e1  mov     qword ptr [rsp+290h+var_270], r15; int
0x18001b9e6  mov     [rsp+290h+var_260], r15
0x18001b9eb  call    cs:__imp_SRCacheContext_Open
0x18001b9f1  mov     ebx, eax
0x18001b9f3  cmp     [rsp+290h+var_258], r15b
0x18001b9f8  jz      short loc_18001BA15
0x18001b9fa  mov     r8, [rsp+290h+var_268]
0x18001b9ff  mov     rdx, [rsp+290h+var_260]
0x18001ba04  mov     rcx, [r8]
0x18001ba07  mov     [r8], rdx
0x18001ba0a  test    rcx, rcx
0x18001ba0d  jz      short loc_18001BA15
0x18001ba0f  call    cs:__imp_SRCacheContext_Close
0x18001ba15  test    ebx, ebx
0x18001ba17  jns     short loc_18001BA6B
0x18001ba19  mov     rcx, [rbp+198h]; this
0x18001ba20  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ba27  mov     r9d, ebx; char *
0x18001ba2a  mov     edx, 18Ch; void *
0x18001ba2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba34  mov     edx, 4A8h; void *
0x18001ba39  mov     rcx, [rbp+198h]; this
0x18001ba40  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001ba47  mov     r9d, ebx; char *
0x18001ba4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ba4f  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001ba54  mov     qword ptr [rsp+290h+var_270], r15
0x18001ba59  test    rcx, rcx
0x18001ba5c  jz      short loc_18001BA64
0x18001ba5e  call    cs:__imp_SRCacheContext_Close
0x18001ba64  mov     eax, ebx
0x18001ba66  jmp     loc_18001BBEC
0x18001ba6b  cmp     qword ptr [rsp+290h+var_270], r15
0x18001ba70  setnz   al
0x18001ba73  test    al, al
0x18001ba75  jnz     short loc_18001BA83
0x18001ba77  mov     ebx, 80670012h
0x18001ba7c  mov     edx, 4A9h
0x18001ba81  jmp     short loc_18001BA39
0x18001ba83  xor     edx, edx; Val
0x18001ba85  mov     [rsp+290h+var_250], r15
0x18001ba8a  mov     r8d, 200h; Size
0x18001ba90  lea     rcx, [rsp+290h+var_248]; void *
0x18001ba95  call    memset_0
0x18001ba9a  lea     rax, [rsp+290h+var_248]
0x18001ba9f  mov     [rbp+190h+var_48], r15
0x18001baa6  mov     rdx, rsi; unsigned __int64
0x18001baa9  mov     [rbp+190h+var_38], rax
0x18001bab0  lea     rcx, [rsp+290h+var_250]; this
0x18001bab5  mov     [rbp+190h+var_40], 100h
0x18001bac0  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x18001bac5  mov     ebx, eax
0x18001bac7  test    eax, eax
0x18001bac9  jns     short loc_18001BB04
0x18001bacb  mov     edx, 4ACh; void *
0x18001bad0  mov     rcx, [rbp+198h]; this
0x18001bad7  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bade  mov     r9d, ebx; char *
0x18001bae1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bae6  mov     rcx, [rsp+290h+var_250]
0x18001baeb  mov     [rsp+290h+var_250], r15
0x18001baf0  test    rcx, rcx
0x18001baf3  jz      loc_18001BA4F
0x18001baf9  call    cs:__imp_SRCache_Free
0x18001baff  jmp     loc_18001BA4F
0x18001bb04  mov     rdx, [rbp+190h+var_38]
0x18001bb0b  lea     r9, [rsp+290h+var_260]
0x18001bb10  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bb15  xor     r8d, r8d
0x18001bb18  mov     [rsp+290h+var_268], rdi
0x18001bb1d  mov     [rsp+290h+var_260], r15
0x18001bb22  mov     [rsp+290h+var_258], 1
0x18001bb27  call    cs:__imp_SRCacheContext_OpenSubContext
0x18001bb2d  mov     ebx, eax
0x18001bb2f  cmp     [rsp+290h+var_258], r15b
0x18001bb34  jz      short loc_18001BB51
0x18001bb36  mov     r8, [rsp+290h+var_268]
0x18001bb3b  mov     rdx, [rsp+290h+var_260]
0x18001bb40  mov     rcx, [r8]
0x18001bb43  mov     [r8], rdx
0x18001bb46  test    rcx, rcx
0x18001bb49  jz      short loc_18001BB51
0x18001bb4b  call    cs:__imp_SRCacheContext_Close
0x18001bb51  test    ebx, ebx
0x18001bb53  jns     short loc_18001BB7A
0x18001bb55  mov     rcx, [rbp+198h]; this
0x18001bb5c  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bb63  mov     r9d, ebx; char *
0x18001bb66  mov     edx, 1B0h; void *
0x18001bb6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb70  mov     edx, 4ADh
0x18001bb75  jmp     loc_18001BAD0
0x18001bb7a  cmp     [rdi], r15
0x18001bb7d  lea     rdx, aPackageData; "Package\\Data"
0x18001bb84  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bb89  setnz   al
0x18001bb8c  mov     [r14], al
0x18001bb8f  call    cs:__imp_SRCacheContext_AddToCache
0x18001bb95  mov     ebx, eax
0x18001bb97  test    eax, eax
0x18001bb99  jns     short loc_18001BBC0
0x18001bb9b  mov     rcx, [rbp+198h]; this
0x18001bba2  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001bba9  mov     r9d, eax; char *
0x18001bbac  mov     edx, 1A6h; void *
0x18001bbb1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bbb6  mov     edx, 4AFh
0x18001bbbb  jmp     loc_18001BAD0
0x18001bbc0  mov     rcx, [rsp+290h+var_250]
0x18001bbc5  mov     [rsp+290h+var_250], r15
0x18001bbca  test    rcx, rcx
0x18001bbcd  jz      short loc_18001BBD5
0x18001bbcf  call    cs:__imp_SRCache_Free
0x18001bbd5  mov     rcx, qword ptr [rsp+290h+var_270]
0x18001bbda  mov     qword ptr [rsp+290h+var_270], r15
0x18001bbdf  test    rcx, rcx
0x18001bbe2  jz      short loc_18001BBEA
0x18001bbe4  call    cs:__imp_SRCacheContext_Close
0x18001bbea  xor     eax, eax
0x18001bbec  mov     rcx, [rbp+190h+var_30]
0x18001bbf3  xor     rcx, rsp; StackCookie
0x18001bbf6  call    __security_check_cookie
0x18001bbfb  mov     rbx, [rsp+290h+arg_10]
0x18001bc03  add     rsp, 270h
0x18001bc0a  pop     r15
0x18001bc0c  pop     r14
0x18001bc0e  pop     rdi
0x18001bc0f  pop     rsi
0x18001bc10  pop     rbp
0x18001bc11  retn
```
