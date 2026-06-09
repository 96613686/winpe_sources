# StateRepository::Cache::Entity::PackageUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUser_NoThrow &,bool &)

- ea: `0x180012fd0`
- end: `0x1800130a8`
- name: `?Get@PackageUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, _QWORD *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180013658`

## callees

- `0x1800075e4`
- `0x1800128e8`
- `0x180012fd0`
- `0x18001424c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001305a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013097`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001305a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013097`

## string_xrefs

- `0x180012fed`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`
- `0x180013038`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUser_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  __int64 v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v16; // [rsp+60h] [rbp+18h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCA,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageUser_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 205;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PackageUser_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 210;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUser.hpp",
        (const char *)(unsigned int)v7,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v7;
    }
  }
  v13 = v16;
  v16 = 0;
  if ( v13 )
    SRCacheContext_Close(v13);
  return 0;
}

```

## disassembly

```asm
0x180012fd0  mov     [rsp+arg_10], r8
0x180012fd5  push    rbx
0x180012fd6  push    rbp
0x180012fd7  push    rsi
0x180012fd8  push    rdi
0x180012fd9  sub     rsp, 28h
0x180012fdd  mov     rbp, r9
0x180012fe0  mov     rdi, rdx
0x180012fe3  test    rdx, rdx
0x180012fe6  jnz     short loc_18001300D
0x180012fe8  mov     rcx, [rsp+48h]; this
0x180012fed  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x180012ff4  mov     ebx, 80070057h
0x180012ff9  mov     edx, 0CAh; void *
0x180012ffe  mov     r9d, ebx; char *
0x180013001  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013006  mov     eax, ebx
0x180013008  jmp     loc_18001309F
0x18001300d  mov     rsi, [rsp+48h+arg_20]
0x180013012  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180013017  mov     r9, rsi; bool *
0x18001301a  mov     [rsp+48h+arg_10], 0
0x180013023  call    ?Open@PackageUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180013028  mov     ebx, eax
0x18001302a  test    eax, eax
0x18001302c  jns     short loc_180013062
0x18001302e  mov     edx, 0CDh; void *
0x180013033  mov     rcx, [rsp+48h]; this
0x180013038  lea     r8, aOnecoreBaseApp_27; "onecore\\base\\appmodel\\StateRepositor"...
0x18001303f  mov     r9d, ebx; char *
0x180013042  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013047  mov     rcx, [rsp+48h+arg_10]
0x18001304c  mov     [rsp+48h+arg_10], 0
0x180013055  test    rcx, rcx
0x180013058  jz      short loc_180013006
0x18001305a  call    cs:__imp_SRCacheContext_Close
0x180013060  jmp     short loc_180013006
0x180013062  cmp     byte ptr [rsi], 0
0x180013065  jz      short loc_180013084
0x180013067  mov     r9, rdi
0x18001306a  lea     rcx, [rsp+48h+arg_10]
0x18001306f  mov     rdx, rbp
0x180013072  call    ?ContextToObject@PackageUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageUser_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageUser_NoThrow &,StateRepository::Cache::Entity::PackageUser_NoThrow::CacheFlags,__int64)
0x180013077  mov     ebx, eax
0x180013079  test    eax, eax
0x18001307b  jns     short loc_180013084
0x18001307d  mov     edx, 0D2h
0x180013082  jmp     short loc_180013033
0x180013084  mov     rcx, [rsp+48h+arg_10]
0x180013089  mov     [rsp+48h+arg_10], 0
0x180013092  test    rcx, rcx
0x180013095  jz      short loc_18001309D
0x180013097  call    cs:__imp_SRCacheContext_Close
0x18001309d  xor     eax, eax
0x18001309f  add     rsp, 28h
0x1800130a3  pop     rdi
0x1800130a4  pop     rsi
0x1800130a5  pop     rbp
0x1800130a6  pop     rbx
0x1800130a7  retn
```
