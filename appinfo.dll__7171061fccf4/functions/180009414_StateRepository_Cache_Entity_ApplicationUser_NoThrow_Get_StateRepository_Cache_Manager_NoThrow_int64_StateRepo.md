# StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::ApplicationUser_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationUser_NoThrow &,bool &)

- ea: `0x180009414`
- end: `0x180009536`
- name: `?Get@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `290`
- prototype: `__int64 __fastcall(struct StateRepository::Cache::Manager_NoThrow *, __int64, __int64, __int64 *, bool *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005220`

## callees

- `0x18000720c`
- `0x180008f10`
- `0x180009414`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800094c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x1800094c1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800094a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000951b`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800094a4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000951b`

## string_xrefs

- `0x1800094d1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`
- `0x18000943d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x180009484`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`
- `0x1800094e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationUser.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationUser_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        bool *a5)
{
  unsigned int v7; // ebx
  bool *v9; // r14
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rcx
  int Field_UInt32; // eax
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v17; // [rsp+50h] [rbp+30h] BYREF

  v17 = a3;
  if ( !a2 )
  {
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
      (const char *)0x80070057LL,
      savedregs);
    return v7;
  }
  v9 = a5;
  v17 = 0;
  v7 = StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(
         a1,
         a2,
         (struct StateRepository::Cache::Context_NoThrow *)&v17,
         a5);
  if ( (v7 & 0x80000000) != 0 )
  {
    v10 = 274;
    goto LABEL_6;
  }
  v12 = v17;
  if ( *v9 )
  {
    Field_UInt32 = SRCacheContext_GetField_UInt32(v17, L"Application", a4 + 3);
    v7 = Field_UInt32;
    if ( Field_UInt32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x221,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
        (const char *)(unsigned int)Field_UInt32,
        savedregs);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45D,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v7,
        savedregsa);
      v10 = 279;
LABEL_6:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationUser.hpp",
        (const char *)v7,
        savedregs);
      v11 = v17;
      v17 = 0;
      if ( v11 )
        SRCacheContext_Close();
      return v7;
    }
    v12 = v17;
    *a4 = a2;
  }
  v17 = 0;
  if ( v12 )
    SRCacheContext_Close();
  return 0;
}

```

## disassembly

```asm
0x180009414  mov     [rsp-18h+arg_0], rbx
0x180009419  mov     [rsp-18h+arg_8], rsi
0x18000941e  mov     [rsp-18h+arg_10], r8
0x180009423  push    rbp
0x180009424  push    rdi
0x180009425  push    r14; int
0x180009427  mov     rbp, rsp
0x18000942a  sub     rsp, 20h
0x18000942e  mov     rsi, r9
0x180009431  mov     rdi, rdx
0x180009434  test    rdx, rdx
0x180009437  jnz     short loc_18000945D
0x180009439  mov     rcx, [rbp+18h]; this
0x18000943d  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x180009444  mov     ebx, 80070057h
0x180009449  mov     edx, 10Fh; void *
0x18000944e  mov     r9d, ebx; char *
0x180009451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009456  mov     eax, ebx
0x180009458  jmp     loc_180009523
0x18000945d  mov     r14, [rbp+arg_20]
0x180009461  lea     r8, [rbp+arg_10]; struct StateRepository::Cache::Context_NoThrow *
0x180009465  mov     r9, r14; bool *
0x180009468  mov     [rbp+arg_10], 0
0x180009470  call    ?Open@ApplicationUser_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationUser_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180009475  mov     ebx, eax
0x180009477  test    eax, eax
0x180009479  jns     short loc_1800094AC
0x18000947b  mov     edx, 112h; void *
0x180009480  mov     rcx, [rbp+18h]; this
0x180009484  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000948b  mov     r9d, ebx; char *
0x18000948e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009493  mov     rcx, [rbp+arg_10]
0x180009497  mov     [rbp+arg_10], 0
0x18000949f  test    rcx, rcx
0x1800094a2  jz      short loc_180009456
0x1800094a4  call    cs:__imp_SRCacheContext_Close
0x1800094aa  jmp     short loc_180009456
0x1800094ac  cmp     byte ptr [r14], 0
0x1800094b0  mov     rcx, [rbp+arg_10]
0x1800094b4  jz      short loc_18000950E
0x1800094b6  lea     r8, [rsi+18h]
0x1800094ba  lea     rdx, aApplication; "Application"
0x1800094c1  call    cs:__imp_SRCacheContext_GetField_UInt32
0x1800094c7  mov     ebx, eax
0x1800094c9  test    eax, eax
0x1800094cb  jns     short loc_180009507
0x1800094cd  mov     rcx, [rbp+18h]; this
0x1800094d1  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800094d8  mov     r9d, eax; char *
0x1800094db  mov     edx, 221h; void *
0x1800094e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094e5  mov     rcx, [rbp+18h]; this
0x1800094e9  lea     r8, aOnecorePrivate_8; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800094f0  mov     r9d, ebx; char *
0x1800094f3  mov     edx, 45Dh; void *
0x1800094f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800094fd  mov     edx, 117h
0x180009502  jmp     loc_180009480
0x180009507  mov     rcx, [rbp+arg_10]
0x18000950b  mov     [rsi], rdi
0x18000950e  mov     [rbp+arg_10], 0
0x180009516  test    rcx, rcx
0x180009519  jz      short loc_180009521
0x18000951b  call    cs:__imp_SRCacheContext_Close
0x180009521  xor     eax, eax
0x180009523  mov     rbx, [rsp+20h+arg_0]
0x180009528  mov     rsi, [rsp+20h+arg_8]
0x18000952d  add     rsp, 20h
0x180009531  pop     r14
0x180009533  pop     rdi
0x180009534  pop     rbp
0x180009535  retn
```
