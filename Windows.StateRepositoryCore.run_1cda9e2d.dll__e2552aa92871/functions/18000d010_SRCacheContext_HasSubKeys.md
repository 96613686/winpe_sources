# SRCacheContext_HasSubKeys

- ea: `0x18000d010`
- end: `0x18000d046`
- name: `SRCacheContext_HasSubKeys`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000d010`
- `0x18000d050`

## string_xrefs

- `0x18000d026`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_HasSubKeys(HKEY *a1, int *a2)
{
  int IsEmpty; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  IsEmpty = SRCacheContext_IsEmpty(a1, a2);
  v3 = IsEmpty;
  if ( IsEmpty >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x28B,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)IsEmpty,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000d010  push    rbx; int
0x18000d012  sub     rsp, 20h
0x18000d016  call    SRCacheContext_IsEmpty
0x18000d01b  mov     ebx, eax
0x18000d01d  test    eax, eax
0x18000d01f  jns     short loc_18000D03E
0x18000d021  mov     rcx, [rsp+28h]; this
0x18000d026  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d02d  mov     r9d, eax; char *
0x18000d030  mov     edx, 28Bh; void *
0x18000d035  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d03a  mov     eax, ebx
0x18000d03c  jmp     short loc_18000D040
0x18000d03e  xor     eax, eax
0x18000d040  add     rsp, 20h
0x18000d044  pop     rbx
0x18000d045  retn
```
