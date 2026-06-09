# SRCacheContext_GetField_MultiString

- ea: `0x18000ce50`
- end: `0x18000cec8`
- name: `SRCacheContext_GetField_MultiString`
- size: `120`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000c698`
- `0x18000ce50`

## string_xrefs

- `0x18000ce82`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000ce9b`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_GetField_MultiString(
        struct Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int16 *v10; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v10 = 0;
  v4 = SRCacheContext::ReadRegistry(a1, a2, &v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    *a3 = v10;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v4,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23C,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v5,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x18000ce50  mov     [rsp+arg_8], rbx
0x18000ce55  push    rdi; int
0x18000ce56  sub     rsp, 20h
0x18000ce5a  mov     rdi, r8
0x18000ce5d  mov     qword ptr [r8], 0
0x18000ce64  lea     r8, [rsp+28h+arg_0]; unsigned __int16 **
0x18000ce69  mov     [rsp+28h+arg_0], 0
0x18000ce72  call    ?ReadRegistry@SRCacheContext@@CAJAEAVRegistryKey@Common@@PEBGPEAPEAG@Z; SRCacheContext::ReadRegistry(Common::RegistryKey &,ushort const *,ushort * *)
0x18000ce77  mov     ebx, eax
0x18000ce79  test    eax, eax
0x18000ce7b  jns     short loc_18000CEB3
0x18000ce7d  mov     rcx, [rsp+28h]; this
0x18000ce82  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000ce89  mov     r9d, eax; char *
0x18000ce8c  mov     edx, 0A0h; void *
0x18000ce91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ce96  mov     rcx, [rsp+28h]; this
0x18000ce9b  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cea2  mov     r9d, ebx; char *
0x18000cea5  mov     edx, 23Ch; void *
0x18000ceaa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ceaf  mov     eax, ebx
0x18000ceb1  jmp     short loc_18000CEBD
0x18000ceb3  mov     rax, [rsp+28h+arg_0]
0x18000ceb8  mov     [rdi], rax
0x18000cebb  xor     eax, eax
0x18000cebd  mov     rbx, [rsp+28h+arg_8]
0x18000cec2  add     rsp, 20h
0x18000cec6  pop     rdi
0x18000cec7  retn
```
