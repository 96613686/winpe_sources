# SRCacheContext_DeleteIfEmpty

- ea: `0x18000cd20`
- end: `0x18000cd56`
- name: `SRCacheContext_DeleteIfEmpty`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000c208`
- `0x18000cd20`

## string_xrefs

- `0x18000cd36`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_DeleteIfEmpty(SRCacheContext *a1, const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = SRCacheContext::DeleteIfEmpty(a1, a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x209,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000cd20  push    rbx; int
0x18000cd22  sub     rsp, 20h
0x18000cd26  call    ?DeleteIfEmpty@SRCacheContext@@QEAAJPEBG@Z; SRCacheContext::DeleteIfEmpty(ushort const *)
0x18000cd2b  mov     ebx, eax
0x18000cd2d  test    eax, eax
0x18000cd2f  jns     short loc_18000CD4E
0x18000cd31  mov     rcx, [rsp+28h]; this
0x18000cd36  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cd3d  mov     r9d, eax; char *
0x18000cd40  mov     edx, 209h; void *
0x18000cd45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd4a  mov     eax, ebx
0x18000cd4c  jmp     short loc_18000CD50
0x18000cd4e  xor     eax, eax
0x18000cd50  add     rsp, 20h
0x18000cd54  pop     rbx
0x18000cd55  retn
```
