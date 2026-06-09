# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x180012e10`
- end: `0x180012ee8`
- name: `?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001384c`

## callees

- `0x1800075e4`
- `0x180012638`
- `0x180012e10`
- `0x180013d14`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012e9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012ed7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012e9a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012ed7`

## string_xrefs

- `0x180012e2d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`
- `0x180012e78`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(
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
      (void *)0x142,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 325;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(&v16, a4, v10, a2);
    if ( v7 < 0 )
    {
      v11 = 330;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-ApplicationExtension.hpp",
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
0x180012e10  mov     [rsp+arg_10], r8
0x180012e15  push    rbx
0x180012e16  push    rbp
0x180012e17  push    rsi
0x180012e18  push    rdi
0x180012e19  sub     rsp, 28h
0x180012e1d  mov     rbp, r9
0x180012e20  mov     rdi, rdx
0x180012e23  test    rdx, rdx
0x180012e26  jnz     short loc_180012E4D
0x180012e28  mov     rcx, [rsp+48h]; this
0x180012e2d  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180012e34  mov     ebx, 80070057h
0x180012e39  mov     edx, 142h; void *
0x180012e3e  mov     r9d, ebx; char *
0x180012e41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e46  mov     eax, ebx
0x180012e48  jmp     loc_180012EDF
0x180012e4d  mov     rsi, [rsp+48h+arg_20]
0x180012e52  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180012e57  mov     r9, rsi; bool *
0x180012e5a  mov     [rsp+48h+arg_10], 0
0x180012e63  call    ?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180012e68  mov     ebx, eax
0x180012e6a  test    eax, eax
0x180012e6c  jns     short loc_180012EA2
0x180012e6e  mov     edx, 145h; void *
0x180012e73  mov     rcx, [rsp+48h]; this
0x180012e78  lea     r8, aOnecoreBaseApp_25; "onecore\\base\\appmodel\\StateRepositor"...
0x180012e7f  mov     r9d, ebx; char *
0x180012e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012e87  mov     rcx, [rsp+48h+arg_10]
0x180012e8c  mov     [rsp+48h+arg_10], 0
0x180012e95  test    rcx, rcx
0x180012e98  jz      short loc_180012E46
0x180012e9a  call    cs:__imp_SRCacheContext_Close
0x180012ea0  jmp     short loc_180012E46
0x180012ea2  cmp     byte ptr [rsi], 0
0x180012ea5  jz      short loc_180012EC4
0x180012ea7  mov     r9, rdi
0x180012eaa  lea     rcx, [rsp+48h+arg_10]
0x180012eaf  mov     rdx, rbp
0x180012eb2  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x180012eb7  mov     ebx, eax
0x180012eb9  test    eax, eax
0x180012ebb  jns     short loc_180012EC4
0x180012ebd  mov     edx, 14Ah
0x180012ec2  jmp     short loc_180012E73
0x180012ec4  mov     rcx, [rsp+48h+arg_10]
0x180012ec9  mov     [rsp+48h+arg_10], 0
0x180012ed2  test    rcx, rcx
0x180012ed5  jz      short loc_180012EDD
0x180012ed7  call    cs:__imp_SRCacheContext_Close
0x180012edd  xor     eax, eax
0x180012edf  add     rsp, 28h
0x180012ee3  pop     rdi
0x180012ee4  pop     rsi
0x180012ee5  pop     rbp
0x180012ee6  pop     rbx
0x180012ee7  retn
```
