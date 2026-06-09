# StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags,StateRepository::Cache::Entity::PackageMachineStatus_NoThrow &,bool &)

- ea: `0x180014cd8`
- end: `0x180014dde`
- name: `?Get@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `262`
- prototype: `static int __high(struct StateRepository::Cache::Manager_NoThrow *, __int64, enum StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::CacheFlags, struct StateRepository::Cache::Entity::PackageMachineStatus_NoThrow *, bool *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800155dc`

## callees

- `0x1800075e4`
- `0x18000b0b0`
- `0x180014cd8`
- `0x1800158b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014d68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014dc3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014d68`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180014dc3`

## string_xrefs

- `0x180014d01`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x180014d48`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`
- `0x180014d94`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-PackageMachineStatus.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Get(
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
      (void *)0xAF,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
      (const char *)0x80070057LL,
      savedregs);
    return v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = 178;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    Field = StateRepository::Cache::Context_NoThrow::GetField(
              (StateRepository::Cache::Context_NoThrow *)&v16,
              L"Status",
              (unsigned int *)(a4 + 24));
    v7 = Field;
    if ( Field < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B5,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
        (const char *)(unsigned int)Field,
        savedregs);
      v10 = 183;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-PackageMachineStatus.hpp",
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
0x180014cd8  mov     [rsp-18h+arg_0], rbx
0x180014cdd  mov     [rsp-18h+arg_8], rsi
0x180014ce2  mov     [rsp-18h+arg_10], r8
0x180014ce7  push    rbp
0x180014ce8  push    rdi
0x180014ce9  push    r14; int
0x180014ceb  mov     rbp, rsp
0x180014cee  sub     rsp, 20h
0x180014cf2  mov     rsi, r9
0x180014cf5  mov     rdi, rdx
0x180014cf8  test    rdx, rdx
0x180014cfb  jnz     short loc_180014D21
0x180014cfd  mov     rcx, [rbp+18h]; this
0x180014d01  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180014d08  mov     ebx, 80070057h
0x180014d0d  mov     edx, 0AFh; void *
0x180014d12  mov     r9d, ebx; char *
0x180014d15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d1a  mov     eax, ebx
0x180014d1c  jmp     loc_180014DCB
0x180014d21  mov     r14, [rbp+arg_20]
0x180014d25  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180014d29  mov     r9, r14; bool *
0x180014d2c  mov     [rbp+arg_10], 0
0x180014d34  call    ?Open@PackageMachineStatus_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::PackageMachineStatus_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180014d39  mov     ebx, eax
0x180014d3b  test    eax, eax
0x180014d3d  jns     short loc_180014D70
0x180014d3f  mov     edx, 0B2h; void *
0x180014d44  mov     rcx, [rbp+18h]; this
0x180014d48  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180014d4f  mov     r9d, ebx; char *
0x180014d52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014d57  mov     rcx, [rbp+arg_10]
0x180014d5b  mov     [rbp+arg_10], 0
0x180014d63  test    rcx, rcx
0x180014d66  jz      short loc_180014D1A
0x180014d68  call    cs:__imp_SRCacheContext_Close
0x180014d6e  jmp     short loc_180014D1A
0x180014d70  cmp     byte ptr [r14], 0
0x180014d74  jz      short loc_180014DB2
0x180014d76  lea     r8, [rsi+18h]; unsigned int *
0x180014d7a  lea     rdx, aStatus; "Status"
0x180014d81  lea     rcx, [rbp+arg_10]; this
0x180014d85  call    ?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z; StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)
0x180014d8a  mov     ebx, eax
0x180014d8c  test    eax, eax
0x180014d8e  jns     short loc_180014DAF
0x180014d90  mov     rcx, [rbp+18h]; this
0x180014d94  lea     r8, aOnecoreBaseApp_10; "onecore\\base\\appmodel\\StateRepositor"...
0x180014d9b  mov     r9d, eax; char *
0x180014d9e  mov     edx, 2B5h; void *
0x180014da3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014da8  mov     edx, 0B7h
0x180014dad  jmp     short loc_180014D44
0x180014daf  mov     [rsi], rdi
0x180014db2  mov     rcx, [rbp+arg_10]
0x180014db6  mov     [rbp+arg_10], 0
0x180014dbe  test    rcx, rcx
0x180014dc1  jz      short loc_180014DC9
0x180014dc3  call    cs:__imp_SRCacheContext_Close
0x180014dc9  xor     eax, eax
0x180014dcb  mov     rbx, [rsp+20h+arg_0]
0x180014dd0  mov     rsi, [rsp+20h+arg_8]
0x180014dd5  add     rsp, 20h
0x180014dd9  pop     r14
0x180014ddb  pop     rdi
0x180014ddc  pop     rbp
0x180014ddd  retn
```
