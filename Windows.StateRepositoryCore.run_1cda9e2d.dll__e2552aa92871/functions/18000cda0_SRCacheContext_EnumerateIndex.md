# SRCacheContext_EnumerateIndex

- ea: `0x18000cda0`
- end: `0x18000cdd6`
- name: `SRCacheContext_EnumerateIndex`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000c2e8`
- `0x18000cda0`

## string_xrefs

- `0x18000cdb6`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_EnumerateIndex(HKEY *a1, DWORD a2, __int64 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = SRCacheContext::EnumerateIndex(a1, a2, a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x282,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000cda0  push    rbx; int
0x18000cda2  sub     rsp, 20h
0x18000cda6  call    ?EnumerateIndex@SRCacheContext@@QEAAJIPEA_J@Z; SRCacheContext::EnumerateIndex(uint,__int64 *)
0x18000cdab  mov     ebx, eax
0x18000cdad  test    eax, eax
0x18000cdaf  jns     short loc_18000CDCE
0x18000cdb1  mov     rcx, [rsp+28h]; this
0x18000cdb6  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cdbd  mov     r9d, eax; char *
0x18000cdc0  mov     edx, 282h; void *
0x18000cdc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cdca  mov     eax, ebx
0x18000cdcc  jmp     short loc_18000CDD0
0x18000cdce  xor     eax, eax
0x18000cdd0  add     rsp, 20h
0x18000cdd4  pop     rbx
0x18000cdd5  retn
```
