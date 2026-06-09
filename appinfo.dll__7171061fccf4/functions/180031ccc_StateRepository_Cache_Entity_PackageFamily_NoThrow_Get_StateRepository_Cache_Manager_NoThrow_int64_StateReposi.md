# StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)

- ea: `0x180031ccc`
- end: `0x180031da4`
- name: `?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180036898`

## callees

- `0x18000720c`
- `0x1800197fc`
- `0x18001e0b0`
- `0x180031ccc`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031d56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031d93`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031d56`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180031d93`

## string_xrefs

- `0x180031ce9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x180031d34`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  const WCHAR *v10; // r8
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
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 175;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 180;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
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
0x180031ccc  mov     [rsp+arg_10], r8
0x180031cd1  push    rbx
0x180031cd2  push    rbp
0x180031cd3  push    rsi
0x180031cd4  push    rdi
0x180031cd5  sub     rsp, 28h
0x180031cd9  mov     rbp, r9
0x180031cdc  mov     rdi, rdx
0x180031cdf  test    rdx, rdx
0x180031ce2  jnz     short loc_180031D09
0x180031ce4  mov     rcx, [rsp+48h]; this
0x180031ce9  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031cf0  mov     ebx, 80070057h
0x180031cf5  mov     edx, 0ACh; void *
0x180031cfa  mov     r9d, ebx; char *
0x180031cfd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d02  mov     eax, ebx
0x180031d04  jmp     loc_180031D9B
0x180031d09  mov     rsi, [rsp+48h+arg_20]
0x180031d0e  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180031d13  mov     r9, rsi; bool *
0x180031d16  mov     [rsp+48h+arg_10], 0
0x180031d1f  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180031d24  mov     ebx, eax
0x180031d26  test    eax, eax
0x180031d28  jns     short loc_180031D5E
0x180031d2a  mov     edx, 0AFh; void *
0x180031d2f  mov     rcx, [rsp+48h]; this
0x180031d34  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x180031d3b  mov     r9d, ebx; char *
0x180031d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031d43  mov     rcx, [rsp+48h+arg_10]
0x180031d48  mov     [rsp+48h+arg_10], 0
0x180031d51  test    rcx, rcx
0x180031d54  jz      short loc_180031D02
0x180031d56  call    cs:__imp_SRCacheContext_Close
0x180031d5c  jmp     short loc_180031D02
0x180031d5e  cmp     byte ptr [rsi], 0
0x180031d61  jz      short loc_180031D80
0x180031d63  mov     r9, rdi
0x180031d66  lea     rcx, [rsp+48h+arg_10]
0x180031d6b  mov     rdx, rbp
0x180031d6e  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x180031d73  mov     ebx, eax
0x180031d75  test    eax, eax
0x180031d77  jns     short loc_180031D80
0x180031d79  mov     edx, 0B4h
0x180031d7e  jmp     short loc_180031D2F
0x180031d80  mov     rcx, [rsp+48h+arg_10]
0x180031d85  mov     [rsp+48h+arg_10], 0
0x180031d8e  test    rcx, rcx
0x180031d91  jz      short loc_180031D99
0x180031d93  call    cs:__imp_SRCacheContext_Close
0x180031d99  xor     eax, eax
0x180031d9b  add     rsp, 28h
0x180031d9f  pop     rdi
0x180031da0  pop     rsi
0x180031da1  pop     rbp
0x180031da2  pop     rbx
0x180031da3  retn
```
