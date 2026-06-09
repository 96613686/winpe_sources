# StateRepository::Migration::Context::Close(StateRepository::Database &)

- ea: `0x18000ba20`
- end: `0x18000ba5a`
- name: `?Close@Context@Migration@StateRepository@@QEBAJAEAVDatabase@3@@Z`
- size: `58`
- prototype: `int(StateRepository::Migration::Context *__hidden this, struct StateRepository::Database *)`
- caller_count: `12`
- callee_count: `2`
- tags: ``

## callers

- `0x18000bb64`
- `0x18000c9b0`
- `0x18000d0a0`
- `0x18000e620`
- `0x18000ec40`
- `0x18000ed80`
- `0x180012e90`
- `0x180013750`
- `0x180013980`
- `0x180013c40`
- `0x180014350`
- `0x1800145e0`

## callees

- `0x18000a3c0`
- `0x18000ba20`

## import_xrefs

- `Windows.StateRepository!StateRepository_DataAccessLayer_DatabaseCache_Add` at `0x18000ba29`
- `Windows.StateRepository!StateRepository_DataAccessLayer_DatabaseCache_Add` at `0x18000ba29`

## pseudocode

```c
__int64 __fastcall StateRepository::Migration::Context::Close(
        StateRepository::Migration::Context *this,
        struct StateRepository::Database *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = StateRepository_DataAccessLayer_DatabaseCache_Add(a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x57,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\upgrade\\inc\\Context.hpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000ba20  push    rbx; int
0x18000ba22  sub     rsp, 20h
0x18000ba26  mov     rcx, rdx
0x18000ba29  call    cs:__imp_StateRepository_DataAccessLayer_DatabaseCache_Add
0x18000ba2f  mov     ebx, eax
0x18000ba31  test    eax, eax
0x18000ba33  jns     short loc_18000BA52
0x18000ba35  mov     rcx, [rsp+28h]; this
0x18000ba3a  lea     r8, aOnecoreBaseApp_47; "onecore\\base\\appmodel\\staterepositor"...
0x18000ba41  mov     r9d, eax; char *
0x18000ba44  mov     edx, 57h ; 'W'; void *
0x18000ba49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ba4e  mov     eax, ebx
0x18000ba50  jmp     short loc_18000BA54
0x18000ba52  xor     eax, eax
0x18000ba54  add     rsp, 20h
0x18000ba58  pop     rbx
0x18000ba59  retn
```
