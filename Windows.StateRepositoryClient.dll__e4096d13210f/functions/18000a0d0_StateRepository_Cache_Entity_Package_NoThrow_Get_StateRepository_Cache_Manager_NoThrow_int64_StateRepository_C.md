# StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x18000a0d0`
- end: `0x18000a1bd`
- name: `?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b20c`
- `0x18001384c`
- `0x18001757c`

## callees

- `0x1800075e4`
- `0x180009938`
- `0x18000a0d0`
- `0x18000b6f0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a162`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a1a2`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a162`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000a1a2`

## string_xrefs

- `0x18000a0f5`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`
- `0x18000a140`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-Package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  int v8; // ebx
  bool *v10; // rsi
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v16; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v8 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x453,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v8;
  }
  v10 = a5;
  v16 = 0;
  v8 = StateRepository::Cache::Entity::Package_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v8 < 0 )
  {
    v11 = 1110;
    goto LABEL_6;
  }
  if ( *v10 )
  {
    v8 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           a3,
           a2);
    if ( v8 < 0 )
    {
      v11 = 1115;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-Package.hpp",
        (const char *)(unsigned int)v8,
        v14);
      v12 = v16;
      v16 = 0;
      if ( v12 )
        SRCacheContext_Close(v12);
      return (unsigned int)v8;
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
0x18000a0d0  mov     [rsp+arg_0], rbx
0x18000a0d5  mov     [rsp+arg_10], rbp
0x18000a0da  push    rsi
0x18000a0db  push    rdi
0x18000a0dc  push    r14; int
0x18000a0de  sub     rsp, 20h
0x18000a0e2  mov     rbp, r9
0x18000a0e5  mov     r14, r8
0x18000a0e8  mov     rdi, rdx
0x18000a0eb  test    rdx, rdx
0x18000a0ee  jnz     short loc_18000A115
0x18000a0f0  mov     rcx, [rsp+38h]; this
0x18000a0f5  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a0fc  mov     ebx, 80070057h
0x18000a101  mov     edx, 453h; void *
0x18000a106  mov     r9d, ebx; char *
0x18000a109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a10e  mov     eax, ebx
0x18000a110  jmp     loc_18000A1AA
0x18000a115  mov     rsi, [rsp+38h+arg_20]
0x18000a11a  lea     r8, [rsp+38h+arg_8]; struct StateRepository::Cache::Context_NoThrow *
0x18000a11f  mov     r9, rsi; bool *
0x18000a122  mov     [rsp+38h+arg_8], 0
0x18000a12b  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000a130  mov     ebx, eax
0x18000a132  test    eax, eax
0x18000a134  jns     short loc_18000A16A
0x18000a136  mov     edx, 456h; void *
0x18000a13b  mov     rcx, [rsp+38h]; this
0x18000a140  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\StateRepositor"...
0x18000a147  mov     r9d, ebx; char *
0x18000a14a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a14f  mov     rcx, [rsp+38h+arg_8]
0x18000a154  mov     [rsp+38h+arg_8], 0
0x18000a15d  test    rcx, rcx
0x18000a160  jz      short loc_18000A10E
0x18000a162  call    cs:__imp_SRCacheContext_Close
0x18000a168  jmp     short loc_18000A10E
0x18000a16a  cmp     byte ptr [rsi], 0
0x18000a16d  jz      short loc_18000A18F
0x18000a16f  mov     r9, rdi
0x18000a172  lea     rcx, [rsp+38h+arg_8]
0x18000a177  mov     r8, r14
0x18000a17a  mov     rdx, rbp
0x18000a17d  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x18000a182  mov     ebx, eax
0x18000a184  test    eax, eax
0x18000a186  jns     short loc_18000A18F
0x18000a188  mov     edx, 45Bh
0x18000a18d  jmp     short loc_18000A13B
0x18000a18f  mov     rcx, [rsp+38h+arg_8]
0x18000a194  mov     [rsp+38h+arg_8], 0
0x18000a19d  test    rcx, rcx
0x18000a1a0  jz      short loc_18000A1A8
0x18000a1a2  call    cs:__imp_SRCacheContext_Close
0x18000a1a8  xor     eax, eax
0x18000a1aa  mov     rbx, [rsp+38h+arg_0]
0x18000a1af  mov     rbp, [rsp+38h+arg_10]
0x18000a1b4  add     rsp, 20h
0x18000a1b8  pop     r14
0x18000a1ba  pop     rdi
0x18000a1bb  pop     rsi
0x18000a1bc  retn
```
