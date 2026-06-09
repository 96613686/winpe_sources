# StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageUserStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageUserStatus_NoThrow &,bool &)

- ea: `0x180014de4`
- end: `0x180014eea`
- name: `?Get@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `262`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180015534`

## callees

- `0x1800075e4`
- `0x18000b0b0`
- `0x180014de4`
- `0x180015b4c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014e74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014ecf`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014e74`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014ecf`

## string_xrefs

- `0x180014e0d`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x180014e54`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`
- `0x180014ea0`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageUserStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  unsigned int v7; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  int Field; // eax
  __int64 v13; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v16; // [rsp+50h] [rbp+30h] BYREF

  v16 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
      (const char *)0x80070057LL,
      savedregs);
    return v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = 203;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    Field = StateRepository::Cache::Context_NoThrow::GetField(
              (StateRepository::Cache::Context_NoThrow *)&v16,
              L"Status",
              (unsigned int *)(a4 + 32));
    v7 = Field;
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x305,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
        (const char *)(unsigned int)Field,
        savedregs);
      v10 = 208;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageUserStatus.hpp",
        (const char *)v7,
        savedregs);
      v11 = v16;
      v16 = 0;
      if ( v11 )
        SRCacheContext_Close(v11);
      return v7;
    }
    *(_QWORD *)a4 = a2;
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
0x180014de4  mov     [rsp-18h+arg_0], rbx
0x180014de9  mov     [rsp-18h+arg_8], rsi
0x180014dee  mov     [rsp-18h+arg_10], r8
0x180014df3  push    rbp
0x180014df4  push    rdi
0x180014df5  push    r14; int
0x180014df7  mov     rbp, rsp
0x180014dfa  sub     rsp, 20h
0x180014dfe  mov     rsi, r9
0x180014e01  mov     rdi, rdx
0x180014e04  test    rdx, rdx
0x180014e07  jnz     short loc_180014E2D
0x180014e09  mov     rcx, [rbp+18h]; this
0x180014e0d  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180014e14  mov     ebx, 80070057h
0x180014e19  mov     edx, 0C8h; void *
0x180014e1e  mov     r9d, ebx; char *
0x180014e21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e26  mov     eax, ebx
0x180014e28  jmp     loc_180014ED7
0x180014e2d  mov     r14, [rbp+arg_20]
0x180014e31  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180014e35  mov     r9, r14; bool *
0x180014e38  mov     [rbp+arg_10], 0
0x180014e40  call    ?Open@PackageUserStatus_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageUserStatus_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180014e45  mov     ebx, eax
0x180014e47  test    eax, eax
0x180014e49  jns     short loc_180014E7C
0x180014e4b  mov     edx, 0CBh; void *
0x180014e50  mov     rcx, [rbp+18h]; this
0x180014e54  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180014e5b  mov     r9d, ebx; char *
0x180014e5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014e63  mov     rcx, [rbp+arg_10]
0x180014e67  mov     [rbp+arg_10], 0
0x180014e6f  test    rcx, rcx
0x180014e72  jz      short loc_180014E26
0x180014e74  call    cs:__imp_SRCacheContext_Close
0x180014e7a  jmp     short loc_180014E26
0x180014e7c  cmp     byte ptr [r14], 0
0x180014e80  jz      short loc_180014EBE
0x180014e82  lea     r8, [rsi+20h]; unsigned int *
0x180014e86  lea     rdx, aStatus; "Status"
0x180014e8d  lea     rcx, [rbp+arg_10]; this
0x180014e91  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180014e96  mov     ebx, eax
0x180014e98  test    eax, eax
0x180014e9a  jns     short loc_180014EBB
0x180014e9c  mov     rcx, [rbp+18h]; this
0x180014ea0  lea     r8, aOnecoreBaseApp_18; "onecore\\base\\appmodel\\StateRepositor"...
0x180014ea7  mov     r9d, eax; char *
0x180014eaa  mov     edx, 305h; void *
0x180014eaf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014eb4  mov     edx, 0D0h
0x180014eb9  jmp     short loc_180014E50
0x180014ebb  mov     [rsi], rdi
0x180014ebe  mov     rcx, [rbp+arg_10]
0x180014ec2  mov     [rbp+arg_10], 0
0x180014eca  test    rcx, rcx
0x180014ecd  jz      short loc_180014ED5
0x180014ecf  call    cs:__imp_SRCacheContext_Close
0x180014ed5  xor     eax, eax
0x180014ed7  mov     rbx, [rsp+20h+arg_0]
0x180014edc  mov     rsi, [rsp+20h+arg_8]
0x180014ee1  add     rsp, 20h
0x180014ee5  pop     r14
0x180014ee7  pop     rdi
0x180014ee8  pop     rbp
0x180014ee9  retn
```
