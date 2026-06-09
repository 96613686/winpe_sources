# StateRepository::Cache::Entity::AppExtension_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::AppExtension_NoThrow &,bool &)

- ea: `0x180012d30`
- end: `0x180012e08`
- name: `?Get@AppExtension_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180012c68`

## callees

- `0x1800075e4`
- `0x180012448`
- `0x180012d30`
- `0x180013a78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012dba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012df7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012dba`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180012df7`

## string_xrefs

- `0x180012d4d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`
- `0x180012d98`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-AppExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::AppExtension_NoThrow::Get(
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
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::AppExtension_NoThrow::Open(
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
    v7 = StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(
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
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-AppExtension.hpp",
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
0x180012d30  mov     [rsp+arg_10], r8
0x180012d35  push    rbx
0x180012d36  push    rbp
0x180012d37  push    rsi
0x180012d38  push    rdi
0x180012d39  sub     rsp, 28h
0x180012d3d  mov     rbp, r9
0x180012d40  mov     rdi, rdx
0x180012d43  test    rdx, rdx
0x180012d46  jnz     short loc_180012D6D
0x180012d48  mov     rcx, [rsp+48h]; this
0x180012d4d  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012d54  mov     ebx, 80070057h
0x180012d59  mov     edx, 0D9h; void *
0x180012d5e  mov     r9d, ebx; char *
0x180012d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012d66  mov     eax, ebx
0x180012d68  jmp     loc_180012DFF
0x180012d6d  mov     rsi, [rsp+48h+arg_20]
0x180012d72  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180012d77  mov     r9, rsi; bool *
0x180012d7a  mov     [rsp+48h+arg_10], 0
0x180012d83  call    ?Open@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180012d88  mov     ebx, eax
0x180012d8a  test    eax, eax
0x180012d8c  jns     short loc_180012DC2
0x180012d8e  mov     edx, 0DCh; void *
0x180012d93  mov     rcx, [rsp+48h]; this
0x180012d98  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\StateRepositor"...
0x180012d9f  mov     r9d, ebx; char *
0x180012da2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012da7  mov     rcx, [rsp+48h+arg_10]
0x180012dac  mov     [rsp+48h+arg_10], 0
0x180012db5  test    rcx, rcx
0x180012db8  jz      short loc_180012D66
0x180012dba  call    cs:__imp_SRCacheContext_Close
0x180012dc0  jmp     short loc_180012D66
0x180012dc2  cmp     byte ptr [rsi], 0
0x180012dc5  jz      short loc_180012DE4
0x180012dc7  mov     r9, rdi
0x180012dca  lea     rcx, [rsp+48h+arg_10]
0x180012dcf  mov     rdx, rbp
0x180012dd2  call    ?ContextToObject@AppExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::AppExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow &,StateRepository::Cache::Entity::AppExtension_NoThrow::CacheFlags,__int64)
0x180012dd7  mov     ebx, eax
0x180012dd9  test    eax, eax
0x180012ddb  jns     short loc_180012DE4
0x180012ddd  mov     edx, 0E1h
0x180012de2  jmp     short loc_180012D93
0x180012de4  mov     rcx, [rsp+48h+arg_10]
0x180012de9  mov     [rsp+48h+arg_10], 0
0x180012df2  test    rcx, rcx
0x180012df5  jz      short loc_180012DFD
0x180012df7  call    cs:__imp_SRCacheContext_Close
0x180012dfd  xor     eax, eax
0x180012dff  add     rsp, 28h
0x180012e03  pop     rdi
0x180012e04  pop     rsi
0x180012e05  pop     rbp
0x180012e06  pop     rbx
0x180012e07  retn
```
