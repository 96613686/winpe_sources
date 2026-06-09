# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x1800046a4`
- end: `0x1800047ec`
- name: `?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `328`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, bool *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18000a938`

## callees

- `0x1800046a4`
- `0x1800047f4`
- `0x18000720c`
- `0x180007780`
- `0x18001b3a4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000479e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800047d1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x18000479e`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x1800047d1`

## string_xrefs

- `0x1800046f3`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18000470b`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x18000477e`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x1800047a8`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        bool *a4)
{
  bool v4; // zf
  int v8; // edx
  int v9; // eax
  unsigned int v10; // edi
  __int64 v12; // rdi
  struct StateRepository::Cache::Manager_NoThrow *v13; // rcx
  int v14; // eax
  __int64 v15; // r8
  unsigned int v16; // ebx
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int savedregs; // [rsp+20h] [rbp+0h]
  int savedregsb; // [rsp+20h] [rbp+0h]
  int savedregsa; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  __int64 v24; // [rsp+40h] [rbp+20h] BYREF
  __int64 v25; // [rsp+48h] [rbp+28h] BYREF

  v25 = a2;
  v4 = *(_QWORD *)a1 == 0;
  *a4 = 0;
  if ( v4 )
    return 0;
  v8 = *(_DWORD *)(a1 + 8);
  v24 = 0;
  v9 = StateRepository::Cache::Context_NoThrow::EnumerateData((StateRepository::Cache::Context_NoThrow *)a1, v8, &v24);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x294,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)(unsigned int)v9,
      savedregs);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
      (const char *)v10,
      savedregsb);
    return v10;
  }
  v12 = v24;
  if ( !v24 )
    return 0;
  v13 = *(struct StateRepository::Cache::Manager_NoThrow **)(a1 + 16);
  v25 = 0;
  v14 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(
          v13,
          v24,
          (struct StateRepository::Cache::Context_NoThrow *)&v25,
          a4);
  v16 = v14;
  if ( v14 >= 0 )
  {
    if ( *a4 )
    {
      v14 = StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(&v25, a3, v15, v12);
      v16 = v14;
      if ( v14 < 0 )
      {
        v17 = 330;
        goto LABEL_10;
      }
    }
    v19 = v25;
    v25 = 0;
    if ( v19 )
      SRCacheContext_Close(v19);
    return 0;
  }
  v17 = 325;
LABEL_10:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v17,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)(unsigned int)v14,
    savedregs);
  v18 = v25;
  v25 = 0;
  if ( v18 )
    SRCacheContext_Close(v18);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2B1,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Entity-ApplicationExtension.hpp",
    (const char *)v16,
    savedregsa);
  return v16;
}

```

## disassembly

```asm
0x1800046a4  mov     [rsp-18h+arg_10], rbx
0x1800046a9  mov     [rsp-18h+arg_18], rsi
0x1800046ae  mov     [rsp-18h+arg_8], rdx
0x1800046b3  push    rbp
0x1800046b4  push    rdi
0x1800046b5  push    r14; int
0x1800046b7  mov     rbp, rsp
0x1800046ba  sub     rsp, 20h
0x1800046be  cmp     qword ptr [rcx], 0
0x1800046c2  mov     rsi, r9
0x1800046c5  mov     r14, r8
0x1800046c8  mov     byte ptr [r9], 0
0x1800046cc  mov     rbx, rcx
0x1800046cf  jz      loc_1800047D7
0x1800046d5  mov     edx, [rcx+8]; int
0x1800046d8  lea     r8, [rbp+arg_0]; __int64 *
0x1800046dc  mov     [rbp+arg_0], 0
0x1800046e4  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x1800046e9  mov     edi, eax
0x1800046eb  test    eax, eax
0x1800046ed  jns     short loc_180004726
0x1800046ef  mov     rcx, [rbp+18h]; this
0x1800046f3  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800046fa  mov     r9d, eax; char *
0x1800046fd  mov     edx, 294h; void *
0x180004702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004707  mov     rcx, [rbp+18h]; this
0x18000470b  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004712  mov     r9d, edi; char *
0x180004715  mov     edx, 2ACh; void *
0x18000471a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000471f  mov     eax, edi
0x180004721  jmp     loc_1800047D9
0x180004726  mov     rdi, [rbp+arg_0]
0x18000472a  test    rdi, rdi
0x18000472d  jz      loc_1800047D7
0x180004733  mov     rcx, [rbx+10h]; struct StateRepository::Cache::Manager_NoThrow *
0x180004737  lea     r8, [rbp+arg_8]; struct StateRepository::Cache::Context_NoThrow *
0x18000473b  mov     r9, rsi; bool *
0x18000473e  mov     [rbp+arg_8], 0
0x180004746  mov     rdx, rdi; __int64
0x180004749  call    ?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x18000474e  mov     ebx, eax
0x180004750  test    eax, eax
0x180004752  jns     short loc_18000475B
0x180004754  mov     edx, 145h
0x180004759  jmp     short loc_18000477A
0x18000475b  cmp     byte ptr [rsi], 0
0x18000475e  jz      short loc_1800047C0
0x180004760  mov     r9, rdi
0x180004763  lea     rcx, [rbp+arg_8]
0x180004767  mov     rdx, r14
0x18000476a  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x18000476f  mov     ebx, eax
0x180004771  test    eax, eax
0x180004773  jns     short loc_1800047C0
0x180004775  mov     edx, 14Ah; void *
0x18000477a  mov     rcx, [rbp+18h]; this
0x18000477e  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004785  mov     r9d, eax; char *
0x180004788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000478d  mov     rcx, [rbp+arg_8]
0x180004791  mov     [rbp+arg_8], 0
0x180004799  test    rcx, rcx
0x18000479c  jz      short loc_1800047A4
0x18000479e  call    cs:__imp_SRCacheContext_Close
0x1800047a4  mov     rcx, [rbp+18h]; this
0x1800047a8  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800047af  mov     r9d, ebx; char *
0x1800047b2  mov     edx, 2B1h; void *
0x1800047b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800047bc  mov     eax, ebx
0x1800047be  jmp     short loc_1800047D9
0x1800047c0  mov     rcx, [rbp+arg_8]
0x1800047c4  mov     [rbp+arg_8], 0
0x1800047cc  test    rcx, rcx
0x1800047cf  jz      short loc_1800047D7
0x1800047d1  call    cs:__imp_SRCacheContext_Close
0x1800047d7  xor     eax, eax
0x1800047d9  mov     rbx, [rsp+20h+arg_10]
0x1800047de  mov     rsi, [rsp+20h+arg_18]
0x1800047e3  add     rsp, 20h
0x1800047e7  pop     r14
0x1800047e9  pop     rdi
0x1800047ea  pop     rbp
0x1800047eb  retn
```
