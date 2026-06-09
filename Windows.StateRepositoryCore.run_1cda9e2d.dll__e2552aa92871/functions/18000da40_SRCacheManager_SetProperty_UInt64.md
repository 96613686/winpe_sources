# SRCacheManager_SetProperty_UInt64

- ea: `0x18000da40`
- end: `0x18000daab`
- name: `SRCacheManager_SetProperty_UInt64`
- size: `107`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000da40`
- `0x18000fdf0`

## string_xrefs

- `0x18000da72`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000da8b`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_SetProperty_UInt64(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  unsigned int v6; // [rsp+20h] [rbp-18h]
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  v9 = a3;
  v3 = Common::RegistryKey::SetValue((HKEY *)(a1 + 8), a2, (const BYTE *)&v9, 8u, 0xBu);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)(unsigned int)v3,
    v6);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE2,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
    (const char *)v4,
    v7);
  return v4;
}

```

## disassembly

```asm
0x18000da40  push    rbx
0x18000da42  sub     rsp, 30h
0x18000da46  mov     [rsp+38h+arg_0], r8
0x18000da4b  add     rcx, 8; this
0x18000da4f  lea     r8, [rsp+38h+arg_0]; void *
0x18000da54  mov     [rsp+38h+var_18], 0Bh; int
0x18000da5c  mov     r9d, 8; unsigned int
0x18000da62  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000da67  mov     ebx, eax
0x18000da69  test    eax, eax
0x18000da6b  jns     short loc_18000DAA3
0x18000da6d  mov     rcx, [rsp+38h]; this
0x18000da72  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000da79  mov     r9d, eax; char *
0x18000da7c  mov     edx, 74h ; 't'; void *
0x18000da81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da86  mov     rcx, [rsp+38h]; this
0x18000da8b  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000da92  mov     r9d, ebx; char *
0x18000da95  mov     edx, 0E2h; void *
0x18000da9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da9f  mov     eax, ebx
0x18000daa1  jmp     short loc_18000DAA5
0x18000daa3  xor     eax, eax
0x18000daa5  add     rsp, 30h
0x18000daa9  pop     rbx
0x18000daaa  retn
```
