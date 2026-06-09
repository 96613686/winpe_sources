# StateRepository::Cache::Entity::Activation_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,StateRepository::Cache::Entity::Activation_NoThrow &,bool &)

- ea: `0x18002f4bc`
- end: `0x18002f594`
- name: `?Get@Activation_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004da98`

## callees

- `0x18002f4bc`
- `0x18002fd50`
- `0x180030914`
- `0x18004d320`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f546`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f583`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f546`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002f583`

## string_xrefs

- `0x18002f4d9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`
- `0x18002f524`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-Activation.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Activation_NoThrow::Get(
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
      (void *)0x137,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::Activation_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 314;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(&v16, a4, v10, a2);
    if ( v7 < 0 )
    {
      v11 = 319;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-Activation.hpp",
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
0x18002f4bc  mov     [rsp+arg_10], r8
0x18002f4c1  push    rbx
0x18002f4c2  push    rbp
0x18002f4c3  push    rsi
0x18002f4c4  push    rdi
0x18002f4c5  sub     rsp, 28h
0x18002f4c9  mov     rbp, r9
0x18002f4cc  mov     rdi, rdx
0x18002f4cf  test    rdx, rdx
0x18002f4d2  jnz     short loc_18002F4F9
0x18002f4d4  mov     rcx, [rsp+48h]; this
0x18002f4d9  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f4e0  mov     ebx, 80070057h
0x18002f4e5  mov     edx, 137h; void *
0x18002f4ea  mov     r9d, ebx; char *
0x18002f4ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f4f2  mov     eax, ebx
0x18002f4f4  jmp     loc_18002F58B
0x18002f4f9  mov     rsi, [rsp+48h+arg_20]
0x18002f4fe  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002f503  mov     r9, rsi; bool *
0x18002f506  mov     [rsp+48h+arg_10], 0
0x18002f50f  call    ?Open@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Activation_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002f514  mov     ebx, eax
0x18002f516  test    eax, eax
0x18002f518  jns     short loc_18002F54E
0x18002f51a  mov     edx, 13Ah; void *
0x18002f51f  mov     rcx, [rsp+48h]; this
0x18002f524  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002f52b  mov     r9d, ebx; char *
0x18002f52e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f533  mov     rcx, [rsp+48h+arg_10]
0x18002f538  mov     [rsp+48h+arg_10], 0
0x18002f541  test    rcx, rcx
0x18002f544  jz      short loc_18002F4F2
0x18002f546  call    cs:__imp_SRCacheContext_Close
0x18002f54c  jmp     short loc_18002F4F2
0x18002f54e  cmp     byte ptr [rsi], 0
0x18002f551  jz      short loc_18002F570
0x18002f553  mov     r9, rdi
0x18002f556  lea     rcx, [rsp+48h+arg_10]
0x18002f55b  mov     rdx, rbp
0x18002f55e  call    ?ContextToObject@Activation_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Activation_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow &,StateRepository::Cache::Entity::Activation_NoThrow::CacheFlags,__int64)
0x18002f563  mov     ebx, eax
0x18002f565  test    eax, eax
0x18002f567  jns     short loc_18002F570
0x18002f569  mov     edx, 13Fh
0x18002f56e  jmp     short loc_18002F51F
0x18002f570  mov     rcx, [rsp+48h+arg_10]
0x18002f575  mov     [rsp+48h+arg_10], 0
0x18002f57e  test    rcx, rcx
0x18002f581  jz      short loc_18002F589
0x18002f583  call    cs:__imp_SRCacheContext_Close
0x18002f589  xor     eax, eax
0x18002f58b  add     rsp, 28h
0x18002f58f  pop     rdi
0x18002f590  pop     rsi
0x18002f591  pop     rbp
0x18002f592  pop     rbx
0x18002f593  retn
```
