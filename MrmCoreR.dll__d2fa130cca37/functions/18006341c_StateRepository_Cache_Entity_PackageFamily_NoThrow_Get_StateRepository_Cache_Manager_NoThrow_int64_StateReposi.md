# StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)

- ea: `0x18006341c`
- end: `0x1800634f7`
- name: `?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180062a00`

## callees

- `0x18002c8d0`
- `0x18006341c`
- `0x180063500`
- `0x180063928`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800634e1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180063487`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800634e1`

## string_xrefs

- `0x18006349d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x1800634bf`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  bool *v7; // rsi
  __int64 v8; // rdx
  int v9; // ebx
  const WCHAR *v10; // r8
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v18; // [rsp+60h] [rbp+18h] BYREF

  v18 = a3;
  if ( !a2 )
  {
    v9 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
      (const char *)0x80070057LL,
      v16);
    return (unsigned int)v9;
  }
  v7 = a5;
  v18 = 0;
  v9 = StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v18,
         a5);
  if ( v9 < 0 )
  {
    v15 = 175;
    goto LABEL_10;
  }
  if ( *v7 )
  {
    v9 = StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v18,
           a4,
           v10,
           a2);
    if ( v9 < 0 )
    {
      v15 = 180;
LABEL_10:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-PackageFamily.hpp",
        (const char *)(unsigned int)v9,
        v16);
      v14 = v18;
      v18 = 0;
      if ( v14 )
        SRCacheContext_Close(v14, v13);
      return (unsigned int)v9;
    }
  }
  v11 = v18;
  v18 = 0;
  if ( v11 )
    SRCacheContext_Close(v11, v8);
  return 0;
}

```

## disassembly

```asm
0x18006341c  mov     [rsp+arg_10], r8
0x180063421  push    rbx
0x180063422  push    rbp
0x180063423  push    rsi
0x180063424  push    rdi
0x180063425  sub     rsp, 28h
0x180063429  mov     rbp, r9
0x18006342c  mov     rdi, rdx
0x18006342f  test    rdx, rdx
0x180063432  jz      short loc_180063498
0x180063434  mov     rsi, [rsp+48h+arg_20]
0x180063439  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18006343e  mov     r9, rsi; bool *
0x180063441  mov     [rsp+48h+arg_10], 0
0x18006344a  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18006344f  mov     ebx, eax
0x180063451  test    eax, eax
0x180063453  js      loc_1800634E9
0x180063459  cmp     byte ptr [rsi], 0
0x18006345c  jz      short loc_180063474
0x18006345e  mov     r9, rdi
0x180063461  lea     rcx, [rsp+48h+arg_10]
0x180063466  mov     rdx, rbp
0x180063469  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x18006346e  mov     ebx, eax
0x180063470  test    eax, eax
0x180063472  js      short loc_1800634F0
0x180063474  mov     rcx, [rsp+48h+arg_10]
0x180063479  mov     [rsp+48h+arg_10], 0
0x180063482  test    rcx, rcx
0x180063485  jz      short loc_18006348D
0x180063487  call    cs:__imp_SRCacheContext_Close
0x18006348d  xor     eax, eax
0x18006348f  add     rsp, 28h
0x180063493  pop     rdi
0x180063494  pop     rsi
0x180063495  pop     rbp
0x180063496  pop     rbx
0x180063497  retn
0x180063498  mov     rcx, [rsp+48h]; this
0x18006349d  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800634a4  mov     ebx, 80070057h
0x1800634a9  mov     edx, 0ACh; void *
0x1800634ae  mov     r9d, ebx; char *
0x1800634b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800634b6  mov     eax, ebx
0x1800634b8  jmp     short loc_18006348F
0x1800634ba  mov     rcx, [rsp+48h]; this
0x1800634bf  lea     r8, aOnecorePrivate_5; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800634c6  mov     r9d, ebx; char *
0x1800634c9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800634ce  mov     rcx, [rsp+48h+arg_10]
0x1800634d3  mov     [rsp+48h+arg_10], 0
0x1800634dc  test    rcx, rcx
0x1800634df  jz      short loc_1800634B6
0x1800634e1  call    cs:__imp_SRCacheContext_Close
0x1800634e7  jmp     short loc_1800634B6
0x1800634e9  mov     edx, 0AFh; void *
0x1800634ee  jmp     short loc_1800634BA
0x1800634f0  mov     edx, 0B4h
0x1800634f5  jmp     short loc_1800634BA
```
