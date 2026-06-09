# SRCacheContext_SetField_Binary

- ea: `0x18000d280`
- end: `0x18000d2ff`
- name: `SRCacheContext_SetField_Binary`
- size: `127`
- prototype: `__int64 __fastcall(Common::RegistryKey *this, const unsigned __int16 *, unsigned int, const void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d280`
- `0x18000fdf0`

## string_xrefs

- `0x18000d2cb`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d2df`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_SetField_Binary(
        Common::RegistryKey *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const void *a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v7; // [rsp+20h] [rbp-18h]
  unsigned int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*(_QWORD *)this )
  {
    v4 = -2147019873;
    v5 = 300;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v4,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x139,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v4,
      v8);
    return v4;
  }
  v4 = Common::RegistryKey::SetValue(this, a2, a4, a3, a4 != 0 ? 3 : 0);
  if ( (v4 & 0x80000000) != 0 )
  {
    v5 = 302;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d280  push    rbx
0x18000d282  sub     rsp, 30h
0x18000d286  cmp     qword ptr [rcx], 0
0x18000d28a  mov     r11, r9
0x18000d28d  mov     r10, rcx
0x18000d290  jnz     short loc_18000D29E
0x18000d292  mov     ebx, 8007139Fh
0x18000d297  mov     edx, 12Ch; unsigned __int16 *
0x18000d29c  jmp     short loc_18000D2C6
0x18000d29e  mov     rax, r11
0x18000d2a1  mov     r9d, r8d; unsigned int
0x18000d2a4  neg     rax
0x18000d2a7  mov     r8, r11; void *
0x18000d2aa  sbb     ecx, ecx
0x18000d2ac  and     ecx, 3
0x18000d2af  mov     [rsp+38h+var_18], ecx; int
0x18000d2b3  mov     rcx, r10; this
0x18000d2b6  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000d2bb  mov     ebx, eax
0x18000d2bd  test    eax, eax
0x18000d2bf  jns     short loc_18000D2F7
0x18000d2c1  mov     edx, 12Eh; void *
0x18000d2c6  mov     rcx, [rsp+38h]; this
0x18000d2cb  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d2d2  mov     r9d, ebx; char *
0x18000d2d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d2da  mov     rcx, [rsp+38h]; this
0x18000d2df  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d2e6  mov     r9d, ebx; char *
0x18000d2e9  mov     edx, 139h; void *
0x18000d2ee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d2f3  mov     eax, ebx
0x18000d2f5  jmp     short loc_18000D2F9
0x18000d2f7  xor     eax, eax
0x18000d2f9  add     rsp, 30h
0x18000d2fd  pop     rbx
0x18000d2fe  retn
```
