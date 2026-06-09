# StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x180012ef0`
- end: `0x180012fc8`
- name: `?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001384c`

## callees

- `0x1800075e4`
- `0x18001284c`
- `0x180012ef0`
- `0x180013fb0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012fb7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012f7a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012fb7`

## string_xrefs

- `0x180012f0d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Application.hpp`
- `0x180012f58`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
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
      (void *)0x153,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Application.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::Application_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 342;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 347;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Application.hpp",
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
0x180012ef0  mov     [rsp+arg_10], r8
0x180012ef5  push    rbx
0x180012ef6  push    rbp
0x180012ef7  push    rsi
0x180012ef8  push    rdi
0x180012ef9  sub     rsp, 28h
0x180012efd  mov     rbp, r9
0x180012f00  mov     rdi, rdx
0x180012f03  test    rdx, rdx
0x180012f06  jnz     short loc_180012F2D
0x180012f08  mov     rcx, [rsp+48h]; this
0x180012f0d  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\StateRepositor"...
0x180012f14  mov     ebx, 80070057h
0x180012f19  mov     edx, 153h; void *
0x180012f1e  mov     r9d, ebx; char *
0x180012f21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f26  mov     eax, ebx
0x180012f28  jmp     loc_180012FBF
0x180012f2d  mov     rsi, [rsp+48h+arg_20]
0x180012f32  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180012f37  mov     r9, rsi; bool *
0x180012f3a  mov     [rsp+48h+arg_10], 0
0x180012f43  call    ?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180012f48  mov     ebx, eax
0x180012f4a  test    eax, eax
0x180012f4c  jns     short loc_180012F82
0x180012f4e  mov     edx, 156h; void *
0x180012f53  mov     rcx, [rsp+48h]; this
0x180012f58  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\StateRepositor"...
0x180012f5f  mov     r9d, ebx; char *
0x180012f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012f67  mov     rcx, [rsp+48h+arg_10]
0x180012f6c  mov     [rsp+48h+arg_10], 0
0x180012f75  test    rcx, rcx
0x180012f78  jz      short loc_180012F26
0x180012f7a  call    cs:__imp_SRCacheContext_Close
0x180012f80  jmp     short loc_180012F26
0x180012f82  cmp     byte ptr [rsi], 0
0x180012f85  jz      short loc_180012FA4
0x180012f87  mov     r9, rdi
0x180012f8a  lea     rcx, [rsp+48h+arg_10]
0x180012f8f  mov     rdx, rbp
0x180012f92  call    ?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)
0x180012f97  mov     ebx, eax
0x180012f99  test    eax, eax
0x180012f9b  jns     short loc_180012FA4
0x180012f9d  mov     edx, 15Bh
0x180012fa2  jmp     short loc_180012F53
0x180012fa4  mov     rcx, [rsp+48h+arg_10]
0x180012fa9  mov     [rsp+48h+arg_10], 0
0x180012fb2  test    rcx, rcx
0x180012fb5  jz      short loc_180012FBD
0x180012fb7  call    cs:__imp_SRCacheContext_Close
0x180012fbd  xor     eax, eax
0x180012fbf  add     rsp, 28h
0x180012fc3  pop     rdi
0x180012fc4  pop     rsi
0x180012fc5  pop     rbp
0x180012fc6  pop     rbx
0x180012fc7  retn
```
