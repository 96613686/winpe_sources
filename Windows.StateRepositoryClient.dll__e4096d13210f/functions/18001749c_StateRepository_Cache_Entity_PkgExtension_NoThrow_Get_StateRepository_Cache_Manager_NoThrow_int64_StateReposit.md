# StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PkgExtension_NoThrow &,bool &)

- ea: `0x18001749c`
- end: `0x180017574`
- name: `?Get@PkgExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800173d4`

## callees

- `0x1800075e4`
- `0x180016f78`
- `0x18001749c`
- `0x180017a00`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017563`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017526`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180017563`

## string_xrefs

- `0x1800174b9`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`
- `0x180017504`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PkgExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PkgExtension_NoThrow::Get(
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
      (void *)0xD9,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 220;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 225;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PkgExtension.hpp",
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
0x18001749c  mov     [rsp+arg_10], r8
0x1800174a1  push    rbx
0x1800174a2  push    rbp
0x1800174a3  push    rsi
0x1800174a4  push    rdi
0x1800174a5  sub     rsp, 28h
0x1800174a9  mov     rbp, r9
0x1800174ac  mov     rdi, rdx
0x1800174af  test    rdx, rdx
0x1800174b2  jnz     short loc_1800174D9
0x1800174b4  mov     rcx, [rsp+48h]; this
0x1800174b9  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x1800174c0  mov     ebx, 80070057h
0x1800174c5  mov     edx, 0D9h; void *
0x1800174ca  mov     r9d, ebx; char *
0x1800174cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174d2  mov     eax, ebx
0x1800174d4  jmp     loc_18001756B
0x1800174d9  mov     rsi, [rsp+48h+arg_20]
0x1800174de  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x1800174e3  mov     r9, rsi; bool *
0x1800174e6  mov     [rsp+48h+arg_10], 0
0x1800174ef  call    ?Open@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800174f4  mov     ebx, eax
0x1800174f6  test    eax, eax
0x1800174f8  jns     short loc_18001752E
0x1800174fa  mov     edx, 0DCh; void *
0x1800174ff  mov     rcx, [rsp+48h]; this
0x180017504  lea     r8, aOnecoreBaseApp_34; "onecore\\base\\appmodel\\StateRepositor"...
0x18001750b  mov     r9d, ebx; char *
0x18001750e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017513  mov     rcx, [rsp+48h+arg_10]
0x180017518  mov     [rsp+48h+arg_10], 0
0x180017521  test    rcx, rcx
0x180017524  jz      short loc_1800174D2
0x180017526  call    cs:__imp_SRCacheContext_Close
0x18001752c  jmp     short loc_1800174D2
0x18001752e  cmp     byte ptr [rsi], 0
0x180017531  jz      short loc_180017550
0x180017533  mov     r9, rdi
0x180017536  lea     rcx, [rsp+48h+arg_10]
0x18001753b  mov     rdx, rbp
0x18001753e  call    ?ContextToObject@PkgExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PkgExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow &,StateRepository::Cache::Entity::PkgExtension_NoThrow::CacheFlags,__int64)
0x180017543  mov     ebx, eax
0x180017545  test    eax, eax
0x180017547  jns     short loc_180017550
0x180017549  mov     edx, 0E1h
0x18001754e  jmp     short loc_1800174FF
0x180017550  mov     rcx, [rsp+48h+arg_10]
0x180017555  mov     [rsp+48h+arg_10], 0
0x18001755e  test    rcx, rcx
0x180017561  jz      short loc_180017569
0x180017563  call    cs:__imp_SRCacheContext_Close
0x180017569  xor     eax, eax
0x18001756b  add     rsp, 28h
0x18001756f  pop     rdi
0x180017570  pop     rsi
0x180017571  pop     rbp
0x180017572  pop     rbx
0x180017573  retn
```
