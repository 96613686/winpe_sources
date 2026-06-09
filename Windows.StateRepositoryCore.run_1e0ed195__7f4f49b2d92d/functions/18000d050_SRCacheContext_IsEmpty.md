# SRCacheContext_IsEmpty

- ea: `0x18000d050`
- end: `0x18000d086`
- name: `SRCacheContext_IsEmpty`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d010`

## callees

- `0x18000940c`
- `0x18000c384`
- `0x18000d050`

## string_xrefs

- `0x18000d066`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_IsEmpty(HKEY *a1, int *a2)
{
  int IsEmpty; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  IsEmpty = SRCacheContext::IsEmpty(a1, a2);
  v3 = IsEmpty;
  if ( IsEmpty >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x294,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)IsEmpty,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000d050  push    rbx; int
0x18000d052  sub     rsp, 20h
0x18000d056  call    ?IsEmpty@SRCacheContext@@QEAAJPEAH@Z; SRCacheContext::IsEmpty(int *)
0x18000d05b  mov     ebx, eax
0x18000d05d  test    eax, eax
0x18000d05f  jns     short loc_18000D07E
0x18000d061  mov     rcx, [rsp+28h]; this
0x18000d066  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d06d  mov     r9d, eax; char *
0x18000d070  mov     edx, 294h; void *
0x18000d075  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d07a  mov     eax, ebx
0x18000d07c  jmp     short loc_18000D080
0x18000d07e  xor     eax, eax
0x18000d080  add     rsp, 20h
0x18000d084  pop     rbx
0x18000d085  retn
```
