# StateRepository::Cache::Entity::Application_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,StateRepository::Cache::Entity::Application_NoThrow &,bool &)

- ea: `0x18002f3dc`
- end: `0x18002f4b4`
- name: `?Get@Application_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004e168`

## callees

- `0x18002f3dc`
- `0x18002fb0c`
- `0x180030914`
- `0x18004d5e0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f4a3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f466`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f4a3`

## string_xrefs

- `0x18002f3f9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`
- `0x18002f444`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Application.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Application_NoThrow::Get(
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
      (void *)0x153,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
    v7 = StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(&v16, a4, v10, a2);
    if ( v7 < 0 )
    {
      v11 = 347;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Application.hpp",
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
0x18002f3dc  mov     [rsp+arg_10], r8
0x18002f3e1  push    rbx
0x18002f3e2  push    rbp
0x18002f3e3  push    rsi
0x18002f3e4  push    rdi
0x18002f3e5  sub     rsp, 28h
0x18002f3e9  mov     rbp, r9
0x18002f3ec  mov     rdi, rdx
0x18002f3ef  test    rdx, rdx
0x18002f3f2  jnz     short loc_18002F419
0x18002f3f4  mov     rcx, [rsp+48h]; this
0x18002f3f9  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f400  mov     ebx, 80070057h
0x18002f405  mov     edx, 153h; void *
0x18002f40a  mov     r9d, ebx; char *
0x18002f40d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f412  mov     eax, ebx
0x18002f414  jmp     loc_18002F4AB
0x18002f419  mov     rsi, [rsp+48h+arg_20]
0x18002f41e  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002f423  mov     r9, rsi; bool *
0x18002f426  mov     [rsp+48h+arg_10], 0
0x18002f42f  call    ?Open@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Application_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002f434  mov     ebx, eax
0x18002f436  test    eax, eax
0x18002f438  jns     short loc_18002F46E
0x18002f43a  mov     edx, 156h; void *
0x18002f43f  mov     rcx, [rsp+48h]; this
0x18002f444  lea     r8, aOnecorePrivate_1; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f44b  mov     r9d, ebx; char *
0x18002f44e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f453  mov     rcx, [rsp+48h+arg_10]
0x18002f458  mov     [rsp+48h+arg_10], 0
0x18002f461  test    rcx, rcx
0x18002f464  jz      short loc_18002F412
0x18002f466  call    cs:__imp_SRCacheContext_Close
0x18002f46c  jmp     short loc_18002F412
0x18002f46e  cmp     byte ptr [rsi], 0
0x18002f471  jz      short loc_18002F490
0x18002f473  mov     r9, rdi
0x18002f476  lea     rcx, [rsp+48h+arg_10]
0x18002f47b  mov     rdx, rbp
0x18002f47e  call    ?ContextToObject@Application_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Application_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow &,StateRepository::Cache::Entity::Application_NoThrow::CacheFlags,__int64)
0x18002f483  mov     ebx, eax
0x18002f485  test    eax, eax
0x18002f487  jns     short loc_18002F490
0x18002f489  mov     edx, 15Bh
0x18002f48e  jmp     short loc_18002F43F
0x18002f490  mov     rcx, [rsp+48h+arg_10]
0x18002f495  mov     [rsp+48h+arg_10], 0
0x18002f49e  test    rcx, rcx
0x18002f4a1  jz      short loc_18002F4A9
0x18002f4a3  call    cs:__imp_SRCacheContext_Close
0x18002f4a9  xor     eax, eax
0x18002f4ab  add     rsp, 28h
0x18002f4af  pop     rdi
0x18002f4b0  pop     rsi
0x18002f4b1  pop     rbp
0x18002f4b2  pop     rbx
0x18002f4b3  retn
```
