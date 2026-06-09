# SRCacheContext_SetField_UInt32

- ea: `0x18000d3d0`
- end: `0x18000d446`
- name: `SRCacheContext_SetField_UInt32`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d3d0`
- `0x18000fdf0`

## string_xrefs

- `0x18000d412`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d426`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_SetField_UInt32(HKEY *a1, const unsigned __int16 *a2, int a3)
{
  unsigned int v3; // ebx
  __int64 v4; // rdx
  unsigned int v6; // [rsp+20h] [rbp-18h]
  unsigned int v7; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v9; // [rsp+40h] [rbp+8h] BYREF

  if ( !*a1 )
  {
    v3 = -2147019873;
    v4 = 268;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v3,
      v6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x246,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v3,
      v7);
    return v3;
  }
  v9 = a3;
  v3 = Common::RegistryKey::SetValue(a1, a2, (const BYTE *)&v9, 4u, 4u);
  if ( (v3 & 0x80000000) != 0 )
  {
    v4 = 270;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d3d0  push    rbx
0x18000d3d2  sub     rsp, 30h
0x18000d3d6  cmp     qword ptr [rcx], 0
0x18000d3da  jnz     short loc_18000D3E8
0x18000d3dc  mov     ebx, 8007139Fh
0x18000d3e1  mov     edx, 10Ch; unsigned __int16 *
0x18000d3e6  jmp     short loc_18000D40D
0x18000d3e8  mov     [rsp+38h+arg_0], r8d
0x18000d3ed  mov     r9d, 4; unsigned int
0x18000d3f3  lea     r8, [rsp+38h+arg_0]; void *
0x18000d3f8  mov     [rsp+38h+var_18], r9d; int
0x18000d3fd  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000d402  mov     ebx, eax
0x18000d404  test    eax, eax
0x18000d406  jns     short loc_18000D43E
0x18000d408  mov     edx, 10Eh; void *
0x18000d40d  mov     rcx, [rsp+38h]; this
0x18000d412  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d419  mov     r9d, ebx; char *
0x18000d41c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d421  mov     rcx, [rsp+38h]; this
0x18000d426  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d42d  mov     r9d, ebx; char *
0x18000d430  mov     edx, 246h; void *
0x18000d435  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d43a  mov     eax, ebx
0x18000d43c  jmp     short loc_18000D440
0x18000d43e  xor     eax, eax
0x18000d440  add     rsp, 30h
0x18000d444  pop     rbx
0x18000d445  retn
```
