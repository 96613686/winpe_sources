# StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageExtension_NoThrow &,bool &)

- ea: `0x1800172f4`
- end: `0x1800173cc`
- name: `?Get@PackageExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x18001757c`

## callees

- `0x1800075e4`
- `0x180016da0`
- `0x1800172f4`
- `0x180017764`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001737e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800173bb`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001737e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800173bb`

## string_xrefs

- `0x180017311`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`
- `0x18001735c`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageExtension_NoThrow::Get(
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
      (void *)0x113,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 278;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::PackageExtension_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 283;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageExtension.hpp",
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
0x1800172f4  mov     [rsp+arg_10], r8
0x1800172f9  push    rbx
0x1800172fa  push    rbp
0x1800172fb  push    rsi
0x1800172fc  push    rdi
0x1800172fd  sub     rsp, 28h
0x180017301  mov     rbp, r9
0x180017304  mov     rdi, rdx
0x180017307  test    rdx, rdx
0x18001730a  jnz     short loc_180017331
0x18001730c  mov     rcx, [rsp+48h]; this
0x180017311  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x180017318  mov     ebx, 80070057h
0x18001731d  mov     edx, 113h; void *
0x180017322  mov     r9d, ebx; char *
0x180017325  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001732a  mov     eax, ebx
0x18001732c  jmp     loc_1800173C3
0x180017331  mov     rsi, [rsp+48h+arg_20]
0x180017336  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18001733b  mov     r9, rsi; bool *
0x18001733e  mov     [rsp+48h+arg_10], 0
0x180017347  call    ?Open@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18001734c  mov     ebx, eax
0x18001734e  test    eax, eax
0x180017350  jns     short loc_180017386
0x180017352  mov     edx, 116h; void *
0x180017357  mov     rcx, [rsp+48h]; this
0x18001735c  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\StateRepositor"...
0x180017363  mov     r9d, ebx; char *
0x180017366  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001736b  mov     rcx, [rsp+48h+arg_10]
0x180017370  mov     [rsp+48h+arg_10], 0
0x180017379  test    rcx, rcx
0x18001737c  jz      short loc_18001732A
0x18001737e  call    cs:__imp_SRCacheContext_Close
0x180017384  jmp     short loc_18001732A
0x180017386  cmp     byte ptr [rsi], 0
0x180017389  jz      short loc_1800173A8
0x18001738b  mov     r9, rdi
0x18001738e  lea     rcx, [rsp+48h+arg_10]
0x180017393  mov     rdx, rbp
0x180017396  call    ?ContextToObject@PackageExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow &,StateRepository::Cache::Entity::PackageExtension_NoThrow::CacheFlags,__int64)
0x18001739b  mov     ebx, eax
0x18001739d  test    eax, eax
0x18001739f  jns     short loc_1800173A8
0x1800173a1  mov     edx, 11Bh
0x1800173a6  jmp     short loc_180017357
0x1800173a8  mov     rcx, [rsp+48h+arg_10]
0x1800173ad  mov     [rsp+48h+arg_10], 0
0x1800173b6  test    rcx, rcx
0x1800173b9  jz      short loc_1800173C1
0x1800173bb  call    cs:__imp_SRCacheContext_Close
0x1800173c1  xor     eax, eax
0x1800173c3  add     rsp, 28h
0x1800173c7  pop     rdi
0x1800173c8  pop     rsi
0x1800173c9  pop     rbp
0x1800173ca  pop     rbx
0x1800173cb  retn
```
