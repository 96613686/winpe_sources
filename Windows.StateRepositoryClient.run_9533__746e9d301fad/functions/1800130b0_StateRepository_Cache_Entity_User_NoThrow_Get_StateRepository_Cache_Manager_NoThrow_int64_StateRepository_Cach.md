# StateRepository::Cache::Entity::User_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,StateRepository::Cache::Entity::User_NoThrow &,bool &)

- ea: `0x1800130b0`
- end: `0x180013188`
- name: `?Get@User_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001370c`

## callees

- `0x1800075e4`
- `0x18001297c`
- `0x1800130b0`
- `0x1800144e8`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001313a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013177`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18001313a`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180013177`

## string_xrefs

- `0x1800130cd`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`
- `0x180013118`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Entity-User.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::User_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
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
      (void *)0x98,
      (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
      (const char *)0x80070057LL,
      v14);
    return (unsigned int)v7;
  }
  v9 = a5;
  v16 = 0;
  v7 = StateRepository::Cache::Entity::User_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v16,
         a5);
  if ( v7 < 0 )
  {
    v11 = 155;
    goto LABEL_6;
  }
  if ( *v9 )
  {
    v7 = StateRepository::Cache::Entity::User_NoThrow::ContextToObject(
           (StateRepository::Cache::Context_NoThrow *)&v16,
           a4,
           v10,
           a2);
    if ( v7 < 0 )
    {
      v11 = 160;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Entity-User.hpp",
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
0x1800130b0  mov     [rsp+arg_10], r8
0x1800130b5  push    rbx
0x1800130b6  push    rbp
0x1800130b7  push    rsi
0x1800130b8  push    rdi
0x1800130b9  sub     rsp, 28h
0x1800130bd  mov     rbp, r9
0x1800130c0  mov     rdi, rdx
0x1800130c3  test    rdx, rdx
0x1800130c6  jnz     short loc_1800130ED
0x1800130c8  mov     rcx, [rsp+48h]; this
0x1800130cd  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x1800130d4  mov     ebx, 80070057h
0x1800130d9  mov     edx, 98h; void *
0x1800130de  mov     r9d, ebx; char *
0x1800130e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800130e6  mov     eax, ebx
0x1800130e8  jmp     loc_18001317F
0x1800130ed  mov     rsi, [rsp+48h+arg_20]
0x1800130f2  lea     r8, [rsp+48h+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x1800130f7  mov     r9, rsi; bool *
0x1800130fa  mov     [rsp+48h+arg_10], 0
0x180013103  call    ?Open@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::User_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180013108  mov     ebx, eax
0x18001310a  test    eax, eax
0x18001310c  jns     short loc_180013142
0x18001310e  mov     edx, 9Bh; void *
0x180013113  mov     rcx, [rsp+48h]; this
0x180013118  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\StateRepositor"...
0x18001311f  mov     r9d, ebx; char *
0x180013122  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013127  mov     rcx, [rsp+48h+arg_10]
0x18001312c  mov     [rsp+48h+arg_10], 0
0x180013135  test    rcx, rcx
0x180013138  jz      short loc_1800130E6
0x18001313a  call    cs:__imp_SRCacheContext_Close
0x180013140  jmp     short loc_1800130E6
0x180013142  cmp     byte ptr [rsi], 0
0x180013145  jz      short loc_180013164
0x180013147  mov     r9, rdi
0x18001314a  lea     rcx, [rsp+48h+arg_10]
0x18001314f  mov     rdx, rbp
0x180013152  call    ?ContextToObject@User_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::User_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::User_NoThrow &,StateRepository::Cache::Entity::User_NoThrow::CacheFlags,__int64)
0x180013157  mov     ebx, eax
0x180013159  test    eax, eax
0x18001315b  jns     short loc_180013164
0x18001315d  mov     edx, 0A0h
0x180013162  jmp     short loc_180013113
0x180013164  mov     rcx, [rsp+48h+arg_10]
0x180013169  mov     [rsp+48h+arg_10], 0
0x180013172  test    rcx, rcx
0x180013175  jz      short loc_18001317D
0x180013177  call    cs:__imp_SRCacheContext_Close
0x18001317d  xor     eax, eax
0x18001317f  add     rsp, 28h
0x180013183  pop     rdi
0x180013184  pop     rsi
0x180013185  pop     rbp
0x180013186  pop     rbx
0x180013187  retn
```
