# StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x18002f2fc`
- end: `0x18002f3d4`
- name: `?Get@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18004e0a0`

## callees

- `0x18002f2fc`
- `0x18002f5dc`
- `0x180030914`
- `0x18004d3a4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f386`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f3c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f386`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f3c3`

## string_xrefs

- `0x18002f319`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18002f364`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
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
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
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
0x18002f2fc  mov     [rsp+arg_10], r8
0x18002f301  push    rbx
0x18002f302  push    rbp
0x18002f303  push    rsi
0x18002f304  push    rdi
0x18002f305  sub     rsp, 28h
0x18002f309  mov     rbp, r9
0x18002f30c  mov     rdi, rdx
0x18002f30f  test    rdx, rdx
0x18002f312  jnz     short loc_18002F339
0x18002f314  mov     rcx, [rsp+48h]; this
0x18002f319  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f320  mov     ebx, 80070057h
0x18002f325  mov     edx, 142h; void *
0x18002f32a  mov     r9d, ebx; char *
0x18002f32d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f332  mov     eax, ebx
0x18002f334  jmp     loc_18002F3CB
0x18002f339  mov     rsi, [rsp+48h+arg_20]
0x18002f33e  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002f343  mov     r9, rsi; bool *
0x18002f346  mov     [rsp+48h+arg_10], 0
0x18002f34f  call    ?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002f354  mov     ebx, eax
0x18002f356  test    eax, eax
0x18002f358  jns     short loc_18002F38E
0x18002f35a  mov     edx, 145h; void *
0x18002f35f  mov     rcx, [rsp+48h]; this
0x18002f364  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f36b  mov     r9d, ebx; char *
0x18002f36e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f373  mov     rcx, [rsp+48h+arg_10]
0x18002f378  mov     [rsp+48h+arg_10], 0
0x18002f381  test    rcx, rcx
0x18002f384  jz      short loc_18002F332
0x18002f386  call    cs:__imp_SRCacheContext_Close
0x18002f38c  jmp     short loc_18002F332
0x18002f38e  cmp     byte ptr [rsi], 0
0x18002f391  jz      short loc_18002F3B0
0x18002f393  mov     r9, rdi
0x18002f396  lea     rcx, [rsp+48h+arg_10]
0x18002f39b  mov     rdx, rbp
0x18002f39e  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x18002f3a3  mov     ebx, eax
0x18002f3a5  test    eax, eax
0x18002f3a7  jns     short loc_18002F3B0
0x18002f3a9  mov     edx, 14Ah
0x18002f3ae  jmp     short loc_18002F35F
0x18002f3b0  mov     rcx, [rsp+48h+arg_10]
0x18002f3b5  mov     [rsp+48h+arg_10], 0
0x18002f3be  test    rcx, rcx
0x18002f3c1  jz      short loc_18002F3C9
0x18002f3c3  call    cs:__imp_SRCacheContext_Close
0x18002f3c9  xor     eax, eax
0x18002f3cb  add     rsp, 28h
0x18002f3cf  pop     rdi
0x18002f3d0  pop     rsi
0x18002f3d1  pop     rbp
0x18002f3d2  pop     rbx
0x18002f3d3  retn
```
