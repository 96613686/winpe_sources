# SRCacheManager_SetProperty_UInt32

- ea: `0x18000d9d0`
- end: `0x18000da38`
- name: `SRCacheManager_SetProperty_UInt32`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d9d0`
- `0x18000fdf0`

## string_xrefs

- `0x18000d9ff`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000da18`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_SetProperty_UInt32(__int64 a1, const unsigned __int16 *a2, int a3)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  v3 = Common::RegistryKey::SetValue((HKEY *)(a1 + 8), a2, (const BYTE *)&v7, 4u, 4u);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5F,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)(unsigned int)v3);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xCE,
    (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)v4);
  return v4;
}

```

## disassembly

```asm
0x18000d9d0  push    rbx
0x18000d9d2  sub     rsp, 30h
0x18000d9d6  mov     [rsp+38h+arg_10], r8d
0x18000d9db  mov     r9d, 4; unsigned int
0x18000d9e1  lea     r8, [rsp+38h+arg_10]; void *
0x18000d9e6  mov     [rsp+38h+var_18], r9d; int
0x18000d9eb  add     rcx, 8; this
0x18000d9ef  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000d9f4  mov     ebx, eax
0x18000d9f6  test    eax, eax
0x18000d9f8  jns     short loc_18000DA30
0x18000d9fa  mov     rcx, [rsp+38h]; this
0x18000d9ff  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000da06  mov     r9d, eax; char *
0x18000da09  mov     edx, 5Fh ; '_'; void *
0x18000da0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da13  mov     rcx, [rsp+38h]; this
0x18000da18  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000da1f  mov     r9d, ebx; char *
0x18000da22  mov     edx, 0CEh; void *
0x18000da27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da2c  mov     eax, ebx
0x18000da2e  jmp     short loc_18000DA32
0x18000da30  xor     eax, eax
0x18000da32  add     rsp, 30h
0x18000da36  pop     rbx
0x18000da37  retn
```
