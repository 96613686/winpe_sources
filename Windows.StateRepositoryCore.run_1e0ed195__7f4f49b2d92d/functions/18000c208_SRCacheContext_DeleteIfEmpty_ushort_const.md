# SRCacheContext::DeleteIfEmpty(ushort const *)

- ea: `0x18000c208`
- end: `0x18000c23c`
- name: `?DeleteIfEmpty@SRCacheContext@@QEAAJPEBG@Z`
- size: `52`
- prototype: `__int64 __fastcall(SRCacheContext *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000cd20`

## callees

- `0x18000940c`
- `0x18000c208`

## string_xrefs

- `0x18000c217`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext::DeleteIfEmpty(SRCacheContext *this, const unsigned __int16 *a2)
{
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_QWORD *)this )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x65,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)0x80070057LL,
    v3);
  return 2147942487LL;
}

```

## disassembly

```asm
0x18000c208  sub     rsp, 28h
0x18000c20c  cmp     qword ptr [rcx], 0
0x18000c210  jnz     short loc_18000C235
0x18000c212  mov     rcx, [rsp+28h]; this
0x18000c217  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000c21e  mov     r9d, 80070057h; char *
0x18000c224  mov     edx, 65h ; 'e'; void *
0x18000c229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000c22e  mov     eax, 80070057h
0x18000c233  jmp     short loc_18000C237
0x18000c235  xor     eax, eax
0x18000c237  add     rsp, 28h
0x18000c23b  retn
```
