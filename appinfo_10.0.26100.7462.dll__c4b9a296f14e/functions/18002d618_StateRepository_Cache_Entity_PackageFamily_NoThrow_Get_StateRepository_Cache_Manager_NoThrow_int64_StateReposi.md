# StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageFamily_NoThrow &,bool &)

- ea: `0x18002d618`
- end: `0x18002d70b`
- name: `?Get@PackageFamily_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `243`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800337f8`

## callees

- `0x180007c78`
- `0x18002c8e8`
- `0x18002d618`
- `0x180035568`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d6a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d6e7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d6a7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18002d6e7`

## string_xrefs

- `0x18002d640`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`
- `0x18002d688`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-PackageFamily.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageFamily_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        unsigned __int64 a2,
        __int64 a3,
        _QWORD *a4,
        bool *a5)
{
  int v7; // ebx
  bool *v9; // rsi
  const WCHAR *v10; // r8
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v16; // [rsp+40h] [rbp+18h] BYREF

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
0x18002d618  mov     rax, rsp
0x18002d61b  mov     [rax+8], rbx
0x18002d61f  mov     [rax+10h], rbp
0x18002d623  mov     [rax+20h], rsi
0x18002d627  mov     [rax+18h], r8
0x18002d62b  push    rdi; int
0x18002d62c  sub     rsp, 20h
0x18002d630  mov     rbp, r9
0x18002d633  mov     rdi, rdx
0x18002d636  test    rdx, rdx
0x18002d639  jnz     short loc_18002D660
0x18002d63b  mov     rcx, [rsp+28h]; this
0x18002d640  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d647  mov     ebx, 80070057h
0x18002d64c  mov     edx, 0ACh; void *
0x18002d651  mov     r9d, ebx; char *
0x18002d654  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d659  mov     eax, ebx
0x18002d65b  jmp     loc_18002D6F5
0x18002d660  mov     rsi, [rsp+28h+arg_20]
0x18002d665  lea     r8, [rsp+28h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x18002d66a  and     [rsp+28h+arg_10], 0
0x18002d670  mov     r9, rsi; bool *
0x18002d673  call    ?Open@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18002d678  mov     ebx, eax
0x18002d67a  test    eax, eax
0x18002d67c  jns     short loc_18002D6B5
0x18002d67e  mov     edx, 0AFh; void *
0x18002d683  mov     rcx, [rsp+28h]; this
0x18002d688  lea     r8, aOnecorePrivate_2; "onecore\\private\\base\\inc\\appmodel\\"...
0x18002d68f  mov     r9d, ebx; char *
0x18002d692  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d697  mov     rcx, [rsp+28h+arg_10]
0x18002d69c  and     [rsp+28h+arg_10], 0
0x18002d6a2  test    rcx, rcx
0x18002d6a5  jz      short loc_18002D659
0x18002d6a7  call    cs:__imp_SRCacheContext_Close
0x18002d6ae  nop     dword ptr [rax+rax+00h]
0x18002d6b3  jmp     short loc_18002D659
0x18002d6b5  cmp     byte ptr [rsi], 0
0x18002d6b8  jz      short loc_18002D6D7
0x18002d6ba  mov     r9, rdi
0x18002d6bd  lea     rcx, [rsp+28h+arg_10]
0x18002d6c2  mov     rdx, rbp
0x18002d6c5  call    ?ContextToObject@PackageFamily_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::PackageFamily_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow &,StateRepository::Cache::Entity::PackageFamily_NoThrow::CacheFlags,__int64)
0x18002d6ca  mov     ebx, eax
0x18002d6cc  test    eax, eax
0x18002d6ce  jns     short loc_18002D6D7
0x18002d6d0  mov     edx, 0B4h
0x18002d6d5  jmp     short loc_18002D683
0x18002d6d7  mov     rcx, [rsp+28h+arg_10]
0x18002d6dc  and     [rsp+28h+arg_10], 0
0x18002d6e2  test    rcx, rcx
0x18002d6e5  jz      short loc_18002D6F3
0x18002d6e7  call    cs:__imp_SRCacheContext_Close
0x18002d6ee  nop     dword ptr [rax+rax+00h]
0x18002d6f3  xor     eax, eax
0x18002d6f5  mov     rbx, [rsp+28h+arg_0]
0x18002d6fa  mov     rbp, [rsp+28h+arg_8]
0x18002d6ff  mov     rsi, [rsp+28h+arg_18]
0x18002d704  add     rsp, 20h
0x18002d708  pop     rdi
0x18002d709  retn
```
