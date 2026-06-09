# SRCacheContext_Delete

- ea: `0x18000cc50`
- end: `0x18000cc86`
- name: `SRCacheContext_Delete`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x18000940c`
- `0x18000c154`
- `0x18000cc50`

## string_xrefs

- `0x18000cc66`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_Delete(SRCacheContext *a1, const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = SRCacheContext::Delete(a1, a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x200,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000cc50  push    rbx; int
0x18000cc52  sub     rsp, 20h
0x18000cc56  call    ?Delete@SRCacheContext@@QEAAJPEBG@Z; SRCacheContext::Delete(ushort const *)
0x18000cc5b  mov     ebx, eax
0x18000cc5d  test    eax, eax
0x18000cc5f  jns     short loc_18000CC7E
0x18000cc61  mov     rcx, [rsp+28h]; this
0x18000cc66  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cc6d  mov     r9d, eax; char *
0x18000cc70  mov     edx, 200h; void *
0x18000cc75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc7a  mov     eax, ebx
0x18000cc7c  jmp     short loc_18000CC80
0x18000cc7e  xor     eax, eax
0x18000cc80  add     rsp, 20h
0x18000cc84  pop     rbx
0x18000cc85  retn
```
