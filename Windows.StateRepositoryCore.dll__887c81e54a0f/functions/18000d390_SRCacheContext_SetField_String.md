# SRCacheContext_SetField_String

- ea: `0x18000d390`
- end: `0x18000d3c6`
- name: `SRCacheContext_SetField_String`
- size: `54`
- prototype: `__int64 __fastcall(SRCacheContext *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000940c`
- `0x18000c7f0`
- `0x18000d390`

## string_xrefs

- `0x18000d3a6`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_SetField_String(
        SRCacheContext *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = SRCacheContext::SetField(a1, a2, a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x25A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000d390  push    rbx; int
0x18000d392  sub     rsp, 20h
0x18000d396  call    ?SetField@SRCacheContext@@QEAAJPEBG0@Z; SRCacheContext::SetField(ushort const *,ushort const *)
0x18000d39b  mov     ebx, eax
0x18000d39d  test    eax, eax
0x18000d39f  jns     short loc_18000D3BE
0x18000d3a1  mov     rcx, [rsp+28h]; this
0x18000d3a6  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d3ad  mov     r9d, eax; char *
0x18000d3b0  mov     edx, 25Ah; void *
0x18000d3b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d3ba  mov     eax, ebx
0x18000d3bc  jmp     short loc_18000D3C0
0x18000d3be  xor     eax, eax
0x18000d3c0  add     rsp, 20h
0x18000d3c4  pop     rbx
0x18000d3c5  retn
```
