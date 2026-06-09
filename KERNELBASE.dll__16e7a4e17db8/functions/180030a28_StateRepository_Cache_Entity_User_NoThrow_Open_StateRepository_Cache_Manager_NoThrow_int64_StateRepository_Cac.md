# StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)

- ea: `0x180030a28`
- end: `0x180030cb5`
- name: `?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z`
- size: `653`
- prototype: `static int(struct StateRepository::Cache::Manager_NoThrow *, __int64, struct StateRepository::Cache::Context_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002d000`

## callees

- `0x18002f340`
- `0x180030a28`
- `0x180058768`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030b3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_OpenSubContext` at `0x180030b3c`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030a8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Open` at `0x180030a8b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030aaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030b60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030bb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030c3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030aaf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030b60`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030bb3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180030c3b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030c26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030b9e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180030c26`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180030b83`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x180030b83`

## string_xrefs

- `0x180030c08`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180030c82`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-User.hpp`
- `0x180030be8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030c56`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x180030c9a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Open(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        struct StateRepository::Cache::Context_NoThrow *a3,
        bool *a4)
{
  __int64 v4; // rcx
  int v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rcx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rdx
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
  v8 = SRCacheContext_Open(v4, L"User\\Data", 0, &v22);
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
    v19 = 267;
    goto LABEL_26;
  }
  if ( !*(_QWORD *)v20 )
  {
    v8 = -2140733422;
    v19 = 268;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
      (const char *)(unsigned int)v8,
      v20[0]);
    goto LABEL_20;
  }
  v24 = 0;
  memset_0(v25, 0, sizeof(v25));
  v26 = 0;
  v28 = v25;
  v27 = 256;
  v8 = StateRepository::Cache::Key_NoThrow::Append((StateRepository::Cache::Key_NoThrow *)&v24, a2);
  if ( v8 < 0 )
  {
    v16 = 271;
  }
  else
  {
    v21 = (int *)a3;
    v22 = 0;
    v23 = 1;
    v8 = SRCacheContext_OpenSubContext(*(_QWORD *)v20, v28, 0, &v22);
    if ( v23 )
    {
      v10 = *(_QWORD *)v21;
      *(_QWORD *)v21 = v22;
      if ( v10 )
        SRCacheContext_Close(v10);
    }
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1B0,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v8,
        v20[0]);
      v16 = 272;
    }
    else
    {
      v11 = *(_QWORD *)v20;
      *a4 = *(_QWORD *)a3 != 0;
      v12 = SRCacheContext_AddToCache(v11, L"User\\Data");
      v8 = v12;
      if ( v12 >= 0 )
      {
        v13 = v24;
        v24 = 0;
        if ( v13 )
          SRCache_Free(v13);
        v14 = *(_QWORD *)v20;
        *(_QWORD *)v20 = 0;
        if ( v14 )
          SRCacheContext_Close(v14);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A6,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)v12,
        v20[0]);
      v16 = 274;
    }
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v16,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-User.hpp",
    (const char *)(unsigned int)v8,
    v20[0]);
  v17 = v24;
  v24 = 0;
  if ( v17 )
    SRCache_Free(v17);
LABEL_20:
  v18 = *(_QWORD *)v20;
  *(_QWORD *)v20 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180030a28  mov     [rsp-8+arg_10], rbx
0x180030a2d  push    rbp
0x180030a2e  push    rsi
0x180030a2f  push    rdi
0x180030a30  push    r14
0x180030a32  push    r15
0x180030a34  lea     rbp, [rsp-170h]
0x180030a3c  sub     rsp, 270h
0x180030a43  mov     rax, cs:__security_cookie
0x180030a4a  xor     rax, rsp
0x180030a4d  mov     [rbp+190h+var_30], rax
0x180030a54  mov     rcx, [rcx]
0x180030a57  lea     rax, [rsp+290h+var_270]
0x180030a5c  mov     r14, r9
0x180030a5f  mov     [rsp+290h+var_268], rax
0x180030a64  mov     rdi, r8
0x180030a67  mov     [rsp+290h+var_258], 1
0x180030a6c  mov     rsi, rdx
0x180030a6f  lea     r9, [rsp+290h+var_260]
0x180030a74  xor     r15d, r15d
0x180030a77  lea     rdx, aUserData; "User\\Data"
0x180030a7e  xor     r8d, r8d
0x180030a81  mov     qword ptr [rsp+290h+var_270], r15; int
0x180030a86  mov     [rsp+290h+var_260], r15
0x180030a8b  call    cs:__imp_SRCacheContext_Open
0x180030a91  mov     ebx, eax
0x180030a93  cmp     [rsp+290h+var_258], r15b
0x180030a98  jz      short loc_180030AB5
0x180030a9a  mov     r8, [rsp+290h+var_268]
0x180030a9f  mov     rdx, [rsp+290h+var_260]
0x180030aa4  mov     rcx, [r8]
0x180030aa7  mov     [r8], rdx
0x180030aaa  test    rcx, rcx
0x180030aad  jz      short loc_180030AB5
0x180030aaf  call    cs:__imp_SRCacheContext_Close
0x180030ab5  test    ebx, ebx
0x180030ab7  js      loc_180030C93
0x180030abd  cmp     qword ptr [rsp+290h+var_270], r15
0x180030ac2  setnz   al
0x180030ac5  test    al, al
0x180030ac7  jz      loc_180030C71
0x180030acd  xor     edx, edx; Val
0x180030acf  mov     [rsp+290h+var_250], r15
0x180030ad4  mov     r8d, 200h; Size
0x180030ada  lea     rcx, [rsp+290h+var_248]; void *
0x180030adf  call    memset_0
0x180030ae4  lea     rax, [rsp+290h+var_248]
0x180030ae9  mov     [rbp+190h+var_48], r15
0x180030af0  mov     rdx, rsi; unsigned __int64
0x180030af3  mov     [rbp+190h+var_38], rax
0x180030afa  lea     rcx, [rsp+290h+var_250]; this
0x180030aff  mov     [rbp+190h+var_40], 100h
0x180030b0a  call    ?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z; StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)
0x180030b0f  mov     ebx, eax
0x180030b11  test    eax, eax
0x180030b13  js      loc_180030C48
0x180030b19  mov     rdx, [rbp+190h+var_38]
0x180030b20  lea     r9, [rsp+290h+var_260]
0x180030b25  mov     rcx, qword ptr [rsp+290h+var_270]
0x180030b2a  xor     r8d, r8d
0x180030b2d  mov     [rsp+290h+var_268], rdi
0x180030b32  mov     [rsp+290h+var_260], r15
0x180030b37  mov     [rsp+290h+var_258], 1
0x180030b3c  call    cs:__imp_SRCacheContext_OpenSubContext
0x180030b42  mov     ebx, eax
0x180030b44  cmp     [rsp+290h+var_258], r15b
0x180030b49  jz      short loc_180030B66
0x180030b4b  mov     r8, [rsp+290h+var_268]
0x180030b50  mov     rdx, [rsp+290h+var_260]
0x180030b55  mov     rcx, [r8]
0x180030b58  mov     [r8], rdx
0x180030b5b  test    rcx, rcx
0x180030b5e  jz      short loc_180030B66
0x180030b60  call    cs:__imp_SRCacheContext_Close
0x180030b66  test    ebx, ebx
0x180030b68  js      loc_180030C4F
0x180030b6e  cmp     [rdi], r15
0x180030b71  lea     rdx, aUserData; "User\\Data"
0x180030b78  mov     rcx, qword ptr [rsp+290h+var_270]
0x180030b7d  setnz   al
0x180030b80  mov     [r14], al
0x180030b83  call    cs:__imp_SRCacheContext_AddToCache
0x180030b89  mov     ebx, eax
0x180030b8b  test    eax, eax
0x180030b8d  js      short loc_180030BE1
0x180030b8f  mov     rcx, [rsp+290h+var_250]
0x180030b94  mov     [rsp+290h+var_250], r15
0x180030b99  test    rcx, rcx
0x180030b9c  jz      short loc_180030BA4
0x180030b9e  call    cs:__imp_SRCache_Free
0x180030ba4  mov     rcx, qword ptr [rsp+290h+var_270]
0x180030ba9  mov     qword ptr [rsp+290h+var_270], r15
0x180030bae  test    rcx, rcx
0x180030bb1  jz      short loc_180030BB9
0x180030bb3  call    cs:__imp_SRCacheContext_Close
0x180030bb9  xor     eax, eax
0x180030bbb  mov     rcx, [rbp+190h+var_30]
0x180030bc2  xor     rcx, rsp; StackCookie
0x180030bc5  call    __security_check_cookie
0x180030bca  mov     rbx, [rsp+290h+arg_10]
0x180030bd2  add     rsp, 270h
0x180030bd9  pop     r15
0x180030bdb  pop     r14
0x180030bdd  pop     rdi
0x180030bde  pop     rsi
0x180030bdf  pop     rbp
0x180030be0  retn
0x180030be1  mov     rcx, [rbp+198h]; this
0x180030be8  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030bef  mov     r9d, ebx; char *
0x180030bf2  mov     edx, 1A6h; void *
0x180030bf7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030bfc  mov     edx, 112h; void *
0x180030c01  mov     rcx, [rbp+198h]; this
0x180030c08  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030c0f  mov     r9d, ebx; char *
0x180030c12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c17  mov     rcx, [rsp+290h+var_250]
0x180030c1c  mov     [rsp+290h+var_250], r15
0x180030c21  test    rcx, rcx
0x180030c24  jz      short loc_180030C2C
0x180030c26  call    cs:__imp_SRCache_Free
0x180030c2c  mov     rcx, qword ptr [rsp+290h+var_270]
0x180030c31  mov     qword ptr [rsp+290h+var_270], r15
0x180030c36  test    rcx, rcx
0x180030c39  jz      short loc_180030C41
0x180030c3b  call    cs:__imp_SRCacheContext_Close
0x180030c41  mov     eax, ebx
0x180030c43  jmp     loc_180030BBB
0x180030c48  mov     edx, 10Fh
0x180030c4d  jmp     short loc_180030C01
0x180030c4f  mov     rcx, [rbp+198h]; this
0x180030c56  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030c5d  mov     r9d, ebx; char *
0x180030c60  mov     edx, 1B0h; void *
0x180030c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c6a  mov     edx, 110h
0x180030c6f  jmp     short loc_180030C01
0x180030c71  mov     ebx, 80670012h
0x180030c76  mov     edx, 10Ch; void *
0x180030c7b  mov     rcx, [rbp+198h]; this
0x180030c82  lea     r8, aOnecorePrivate_7; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030c89  mov     r9d, ebx; char *
0x180030c8c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030c91  jmp     short loc_180030C2C
0x180030c93  mov     rcx, [rbp+198h]; this
0x180030c9a  lea     r8, aOnecorePrivate_14; "onecore\\private\\base\\inc\\appmodel\\"...
0x180030ca1  mov     r9d, ebx; char *
0x180030ca4  mov     edx, 18Ch; void *
0x180030ca9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180030cae  mov     edx, 10Bh
0x180030cb3  jmp     short loc_180030C7B
```
