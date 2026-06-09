# StateRepository::Cache::Entity::Package_NoThrow::Get(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,StateRepository::Cache::Entity::Package_NoThrow &,bool &)

- ea: `0x1800199ac`
- end: `0x180019aa5`
- name: `?Get@Package_NoThrow@Entity@Cache@StateRepository@@SAJAEAVManager_NoThrow@34@_JW4CacheFlags@1234@AEAV1234@AEA_N@Z`
- size: `249`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180062a00`
- `0x180064c18`

## callees

- `0x1800199ac`
- `0x180019aac`
- `0x180019e3c`
- `0x18002c8d0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a6f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180019a6f`

## string_xrefs

- `0x180019a4d`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`
- `0x180019a7c`: `onecore\private\base\inc\appmodel\staterepository\cache\srcache-entity-package.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Entity::Package_NoThrow::Get(
        struct StateRepository::Cache::Manager_NoThrow *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        bool *a5)
{
  bool *v8; // rsi
  __int64 v9; // rdx
  int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // rdx
  int v16; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v18; // [rsp+48h] [rbp+10h] BYREF

  if ( !a2 )
  {
    v10 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x453,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
      (const char *)0x80070057LL,
      v16);
    return (unsigned int)v10;
  }
  v8 = a5;
  v18 = 0;
  v10 = StateRepository::Cache::Entity::Package_NoThrow::Open(
          a1,
          a2,
          (struct StateRepository::Cache::Context_NoThrow *)&v18,
          a5);
  if ( v10 < 0 )
  {
    v15 = 1110;
    goto LABEL_9;
  }
  if ( *v8 )
  {
    v10 = StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(&v18, a4, a3, a2);
    if ( v10 < 0 )
    {
      v15 = 1115;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\srcache-entity-package.hpp",
        (const char *)(unsigned int)v10,
        v16);
      v14 = v18;
      v18 = 0;
      if ( v14 )
        SRCacheContext_Close(v14, v13);
      return (unsigned int)v10;
    }
  }
  v11 = v18;
  v18 = 0;
  if ( v11 )
    SRCacheContext_Close(v11, v9);
  return 0;
}

```

## disassembly

```asm
0x1800199ac  mov     rax, rsp
0x1800199af  mov     [rax+8], rbx
0x1800199b3  mov     [rax+18h], rbp
0x1800199b7  push    rsi
0x1800199b8  push    rdi
0x1800199b9  push    r14; int
0x1800199bb  sub     rsp, 20h
0x1800199bf  mov     rbp, r9
0x1800199c2  mov     r14, r8
0x1800199c5  mov     rdi, rdx
0x1800199c8  test    rdx, rdx
0x1800199cb  jz      loc_180019A77
0x1800199d1  mov     rsi, [rsp+38h+arg_20]
0x1800199d6  lea     r8, [rax+10h]; struct StateRepository::Cache::Context_NoThrow *
0x1800199da  mov     r9, rsi; bool *
0x1800199dd  mov     qword ptr [rax+10h], 0
0x1800199e5  call    ?Open@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::Package_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x1800199ea  mov     ebx, eax
0x1800199ec  test    eax, eax
0x1800199ee  js      loc_180019A97
0x1800199f4  cmp     byte ptr [rsi], 0
0x1800199f7  jz      short loc_180019A16
0x1800199f9  mov     r9, rdi
0x1800199fc  lea     rcx, [rsp+38h+arg_8]
0x180019a01  mov     r8, r14
0x180019a04  mov     rdx, rbp
0x180019a07  call    ?ContextToObject@Package_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::Package_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow &,StateRepository::Cache::Entity::Package_NoThrow::CacheFlags,__int64)
0x180019a0c  mov     ebx, eax
0x180019a0e  test    eax, eax
0x180019a10  js      loc_180019A9E
0x180019a16  mov     rcx, [rsp+38h+arg_8]
0x180019a1b  mov     [rsp+38h+arg_8], 0
0x180019a24  test    rcx, rcx
0x180019a27  jz      short loc_180019A2F
0x180019a29  call    cs:__imp_SRCacheContext_Close
0x180019a2f  xor     eax, eax
0x180019a31  mov     rbx, [rsp+38h+arg_0]
0x180019a36  mov     rbp, [rsp+38h+arg_10]
0x180019a3b  add     rsp, 20h
0x180019a3f  pop     r14
0x180019a41  pop     rdi
0x180019a42  pop     rsi
0x180019a43  retn
0x180019a44  mov     eax, ebx
0x180019a46  jmp     short loc_180019A31
0x180019a48  mov     rcx, [rsp+38h]; this
0x180019a4d  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019a54  mov     r9d, ebx; char *
0x180019a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a5c  mov     rcx, [rsp+38h+arg_8]
0x180019a61  mov     [rsp+38h+arg_8], 0
0x180019a6a  test    rcx, rcx
0x180019a6d  jz      short loc_180019A44
0x180019a6f  call    cs:__imp_SRCacheContext_Close
0x180019a75  jmp     short loc_180019A44
0x180019a77  mov     rcx, [rsp+38h]; this
0x180019a7c  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019a83  mov     ebx, 80070057h
0x180019a88  mov     edx, 453h; void *
0x180019a8d  mov     r9d, ebx; char *
0x180019a90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019a95  jmp     short loc_180019A44
0x180019a97  mov     edx, 456h; void *
0x180019a9c  jmp     short loc_180019A48
0x180019a9e  mov     edx, 45Bh
0x180019aa3  jmp     short loc_180019A48
```
