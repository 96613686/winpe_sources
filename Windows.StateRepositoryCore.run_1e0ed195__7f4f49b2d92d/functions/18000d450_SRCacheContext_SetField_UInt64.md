# SRCacheContext_SetField_UInt64

- ea: `0x18000d450`
- end: `0x18000d4c9`
- name: `SRCacheContext_SetField_UInt64`
- size: `121`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d450`
- `0x18000fdf0`

## string_xrefs

- `0x18000d495`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d4a9`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_SetField_UInt64(HKEY *a1, const unsigned __int16 *a2, __int64 a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v6; // [rsp+20h] [rbp-18h]
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v3 = -2147019873;
    v4 = 278;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v3,
      v6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v3,
      v7);
    return v3;
  }
  v9 = a3;
  v3 = Common::RegistryKey::SetValue(a1, a2, (const BYTE *)&v9, 8u, 0xBu);
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = 280;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d450  push    rbx
0x18000d452  sub     rsp, 30h
0x18000d456  cmp     qword ptr [rcx], 0
0x18000d45a  jnz     short loc_18000D468
0x18000d45c  mov     ebx, 8007139Fh
0x18000d461  mov     edx, 116h; unsigned __int16 *
0x18000d466  jmp     short loc_18000D490
0x18000d468  mov     [rsp+38h+arg_0], r8
0x18000d46d  mov     r9d, 8; unsigned int
0x18000d473  lea     r8, [rsp+38h+arg_0]; void *
0x18000d478  mov     [rsp+38h+var_18], 0Bh; int
0x18000d480  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000d485  mov     ebx, eax
0x18000d487  test    eax, eax
0x18000d489  jns     short loc_18000D4C1
0x18000d48b  mov     edx, 118h; void *
0x18000d490  mov     rcx, [rsp+38h]; this
0x18000d495  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d49c  mov     r9d, ebx; char *
0x18000d49f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4a4  mov     rcx, [rsp+38h]; this
0x18000d4a9  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d4b0  mov     r9d, ebx; char *
0x18000d4b3  mov     edx, 250h; void *
0x18000d4b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d4bd  mov     eax, ebx
0x18000d4bf  jmp     short loc_18000D4C3
0x18000d4c1  xor     eax, eax
0x18000d4c3  add     rsp, 30h
0x18000d4c7  pop     rbx
0x18000d4c8  retn
```
