# StateRepository::Cache::Entity::ApplicationExtensionIndexIterator_NoThrow::Get(StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,bool &)

- ea: `0x180004eb0`
- end: `0x180004ff9`
- name: `?Get@ApplicationExtensionIndexIterator_NoThrow@Entity@Cache@StateRepository@@QEAAJW4CacheFlags@ApplicationExtension_NoThrow@234@AEAV6234@AEA_N@Z`
- size: `329`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180012b9c`

## callees

- `0x180004eb0`
- `0x180005000`
- `0x180007be0`
- `0x180007c78`
- `0x180018e80`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004fa1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004fd7`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004fa1`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180004fd7`

## string_xrefs

- `0x180004efc`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180004f14`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180004f84`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`
- `0x180004fb1`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Entity-ApplicationExtension.hpp`

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
0x180004eb0  mov     [rsp-18h+arg_10], rbx
0x180004eb5  mov     [rsp-18h+arg_18], rsi
0x180004eba  mov     [rsp-18h+arg_8], rdx
0x180004ebf  push    rbp
0x180004ec0  push    rdi
0x180004ec1  push    r14; int
0x180004ec3  mov     rbp, rsp
0x180004ec6  sub     rsp, 20h
0x180004eca  cmp     qword ptr [rcx], 0
0x180004ece  mov     rsi, r9
0x180004ed1  mov     r14, r8
0x180004ed4  mov     byte ptr [r9], 0
0x180004ed8  mov     rbx, rcx
0x180004edb  jz      loc_180004FE3
0x180004ee1  mov     edx, [rcx+8]; int
0x180004ee4  lea     r8, [rbp+arg_0]; __int64 *
0x180004ee8  and     [rbp+arg_0], 0
0x180004eed  call    ?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z; StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)
0x180004ef2  mov     edi, eax
0x180004ef4  test    eax, eax
0x180004ef6  jns     short loc_180004F2F
0x180004ef8  mov     rcx, [rbp+18h]; this
0x180004efc  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004f03  mov     r9d, eax; char *
0x180004f06  mov     edx, 294h; void *
0x180004f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f10  mov     rcx, [rbp+18h]; this
0x180004f14  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004f1b  mov     r9d, edi; char *
0x180004f1e  mov     edx, 2ACh; void *
0x180004f23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f28  mov     eax, edi
0x180004f2a  jmp     loc_180004FE5
0x180004f2f  mov     rdi, [rbp+arg_0]
0x180004f33  test    rdi, rdi
0x180004f36  jz      loc_180004FE3
0x180004f3c  mov     rcx, [rbx+10h]; struct StateRepository::Cache::Manager_NoThrow *
0x180004f40  lea     r8, [rbp+arg_8]; struct StateRepository::Cache::Context_NoThrow *
0x180004f44  and     [rbp+arg_8], 0
0x180004f49  mov     r9, rsi; bool *
0x180004f4c  mov     rdx, rdi; __int64
0x180004f4f  call    ?Open@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVManager_NoThrow@34@_JAEAVContext_NoThrow@34@AEA_N@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::Open(StateRepository::Cache::Manager_NoThrow &,__int64,StateRepository::Cache::Context_NoThrow &,bool &)
0x180004f54  mov     ebx, eax
0x180004f56  test    eax, eax
0x180004f58  jns     short loc_180004F61
0x180004f5a  mov     edx, 145h
0x180004f5f  jmp     short loc_180004F80
0x180004f61  cmp     byte ptr [rsi], 0
0x180004f64  jz      short loc_180004FC9
0x180004f66  mov     r9, rdi
0x180004f69  lea     rcx, [rbp+arg_8]
0x180004f6d  mov     rdx, r14
0x180004f70  call    ?ContextToObject@ApplicationExtension_NoThrow@Entity@Cache@StateRepository@@CAJAEAVContext_NoThrow@34@AEAV1234@W4CacheFlags@1234@_J@Z; StateRepository::Cache::Entity::ApplicationExtension_NoThrow::ContextToObject(StateRepository::Cache::Context_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow &,StateRepository::Cache::Entity::ApplicationExtension_NoThrow::CacheFlags,__int64)
0x180004f75  mov     ebx, eax
0x180004f77  test    eax, eax
0x180004f79  jns     short loc_180004FC9
0x180004f7b  mov     edx, 14Ah; void *
0x180004f80  mov     rcx, [rbp+18h]; this
0x180004f84  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004f8b  mov     r9d, eax; char *
0x180004f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004f93  mov     rcx, [rbp+arg_8]
0x180004f97  and     [rbp+arg_8], 0
0x180004f9c  test    rcx, rcx
0x180004f9f  jz      short loc_180004FAD
0x180004fa1  call    cs:__imp_SRCacheContext_Close
0x180004fa8  nop     dword ptr [rax+rax+00h]
0x180004fad  mov     rcx, [rbp+18h]; this
0x180004fb1  lea     r8, aOnecorePrivate_4; "onecore\\private\\base\\inc\\appmodel\\"...
0x180004fb8  mov     r9d, ebx; char *
0x180004fbb  mov     edx, 2B1h; void *
0x180004fc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180004fc5  mov     eax, ebx
0x180004fc7  jmp     short loc_180004FE5
0x180004fc9  mov     rcx, [rbp+arg_8]
0x180004fcd  and     [rbp+arg_8], 0
0x180004fd2  test    rcx, rcx
0x180004fd5  jz      short loc_180004FE3
0x180004fd7  call    cs:__imp_SRCacheContext_Close
0x180004fde  nop     dword ptr [rax+rax+00h]
0x180004fe3  xor     eax, eax
0x180004fe5  mov     rbx, [rsp+20h+arg_10]
0x180004fea  mov     rsi, [rsp+20h+arg_18]
0x180004fef  add     rsp, 20h
0x180004ff3  pop     r14
0x180004ff5  pop     rdi
0x180004ff6  pop     rbp
0x180004ff7  retn
```
