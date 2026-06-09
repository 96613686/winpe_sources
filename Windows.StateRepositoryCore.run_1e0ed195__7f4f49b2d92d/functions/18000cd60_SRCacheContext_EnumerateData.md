# SRCacheContext_EnumerateData

- ea: `0x18000cd60`
- end: `0x18000cd96`
- name: `SRCacheContext_EnumerateData`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000c244`
- `0x18000cd60`

## string_xrefs

- `0x18000cd76`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_EnumerateData(SRCacheContext *a1, unsigned int a2, __int64 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = SRCacheContext::EnumerateData(a1, a2, a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x278,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000cd60  push    rbx; int
0x18000cd62  sub     rsp, 20h
0x18000cd66  call    ?EnumerateData@SRCacheContext@@QEAAJIPEA_J@Z; SRCacheContext::EnumerateData(uint,__int64 *)
0x18000cd6b  mov     ebx, eax
0x18000cd6d  test    eax, eax
0x18000cd6f  jns     short loc_18000CD8E
0x18000cd71  mov     rcx, [rsp+28h]; this
0x18000cd76  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cd7d  mov     r9d, eax; char *
0x18000cd80  mov     edx, 278h; void *
0x18000cd85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cd8a  mov     eax, ebx
0x18000cd8c  jmp     short loc_18000CD90
0x18000cd8e  xor     eax, eax
0x18000cd90  add     rsp, 20h
0x18000cd94  pop     rbx
0x18000cd95  retn
```
