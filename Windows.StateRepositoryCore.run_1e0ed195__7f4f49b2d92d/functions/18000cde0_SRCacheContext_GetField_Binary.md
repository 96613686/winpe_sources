# SRCacheContext_GetField_Binary

- ea: `0x18000cde0`
- end: `0x18000ce3d`
- name: `SRCacheContext_GetField_Binary`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000c52c`
- `0x18000cde0`

## string_xrefs

- `0x18000ce04`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000ce1d`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_GetField_Binary(
        struct Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  int Registry; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  *a4 = 0;
  Registry = SRCacheContext::ReadRegistry(a1, a2, a3, a4);
  v5 = Registry;
  if ( Registry >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x95,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)(unsigned int)Registry,
    v7);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x232,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
    (const char *)v5,
    v8);
  return v5;
}

```

## disassembly

```asm
0x18000cde0  push    rbx; int
0x18000cde2  sub     rsp, 20h
0x18000cde6  mov     dword ptr [r8], 0
0x18000cded  mov     qword ptr [r9], 0
0x18000cdf4  call    ?ReadRegistry@SRCacheContext@@CAJAEAVRegistryKey@Common@@PEBGAEAIPEAPEAE@Z; SRCacheContext::ReadRegistry(Common::RegistryKey &,ushort const *,uint &,uchar * *)
0x18000cdf9  mov     ebx, eax
0x18000cdfb  test    eax, eax
0x18000cdfd  jns     short loc_18000CE35
0x18000cdff  mov     rcx, [rsp+28h]; this
0x18000ce04  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000ce0b  mov     r9d, eax; char *
0x18000ce0e  mov     edx, 95h; void *
0x18000ce13  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce18  mov     rcx, [rsp+28h]; this
0x18000ce1d  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000ce24  mov     r9d, ebx; char *
0x18000ce27  mov     edx, 232h; void *
0x18000ce2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce31  mov     eax, ebx
0x18000ce33  jmp     short loc_18000CE37
0x18000ce35  xor     eax, eax
0x18000ce37  add     rsp, 20h
0x18000ce3b  pop     rbx
0x18000ce3c  retn
```
