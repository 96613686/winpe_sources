# SRCacheContext_GetField_String

- ea: `0x18000ced0`
- end: `0x18000cf26`
- name: `SRCacheContext_GetField_String`
- size: `86`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000c698`
- `0x18000ced0`

## string_xrefs

- `0x18000ceed`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cf06`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_GetField_String(
        struct Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int Registry; // eax
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  Registry = SRCacheContext::ReadRegistry(a1, a2, a3);
  v4 = Registry;
  if ( Registry >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x8A,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)Registry);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x227,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)v4);
  return v4;
}

```

## disassembly

```asm
0x18000ced0  push    rbx; int
0x18000ced2  sub     rsp, 20h
0x18000ced6  mov     qword ptr [r8], 0
0x18000cedd  call    ?ReadRegistry@SRCacheContext@@CAJAEAVRegistryKey@Common@@PEBGPEAPEAG@Z; SRCacheContext::ReadRegistry(Common::RegistryKey &,ushort const *,ushort * *)
0x18000cee2  mov     ebx, eax
0x18000cee4  test    eax, eax
0x18000cee6  jns     short loc_18000CF1E
0x18000cee8  mov     rcx, [rsp+28h]; this
0x18000ceed  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cef4  mov     r9d, eax; char *
0x18000cef7  mov     edx, 8Ah; void *
0x18000cefc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf01  mov     rcx, [rsp+28h]; this
0x18000cf06  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cf0d  mov     r9d, ebx; char *
0x18000cf10  mov     edx, 227h; void *
0x18000cf15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf1a  mov     eax, ebx
0x18000cf1c  jmp     short loc_18000CF20
0x18000cf1e  xor     eax, eax
0x18000cf20  add     rsp, 20h
0x18000cf24  pop     rbx
0x18000cf25  retn
```
