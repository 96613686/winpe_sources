# SRCacheContext_SetField_MultiString

- ea: `0x18000d310`
- end: `0x18000d37c`
- name: `SRCacheContext_SetField_MultiString`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d310`
- `0x18000fdf0`

## string_xrefs

- `0x18000d348`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000d35c`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_SetField_MultiString(HKEY *a1, const unsigned __int16 *a2, const BYTE *a3, int a4)
{
  unsigned int v4; // ebx
  __int64 v5; // rdx
  unsigned int v7; // [rsp+20h] [rbp-18h]
  unsigned int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !*a1 )
  {
    v4 = -2147019873;
    v5 = 322;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v4,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x265,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)v4,
      v8);
    return v4;
  }
  v4 = Common::RegistryKey::SetValue(a1, a2, a3, 2 * a4, 7u);
  if ( (v4 & 0x80000000) != 0 )
  {
    v5 = 324;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000d310  push    rbx
0x18000d312  sub     rsp, 30h
0x18000d316  cmp     qword ptr [rcx], 0
0x18000d31a  jnz     short loc_18000D328
0x18000d31c  mov     ebx, 8007139Fh
0x18000d321  mov     edx, 142h; unsigned __int16 *
0x18000d326  jmp     short loc_18000D343
0x18000d328  add     r9d, r9d; unsigned int
0x18000d32b  mov     [rsp+38h+var_18], 7; int
0x18000d333  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x18000d338  mov     ebx, eax
0x18000d33a  test    eax, eax
0x18000d33c  jns     short loc_18000D374
0x18000d33e  mov     edx, 144h; void *
0x18000d343  mov     rcx, [rsp+38h]; this
0x18000d348  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d34f  mov     r9d, ebx; char *
0x18000d352  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d357  mov     rcx, [rsp+38h]; this
0x18000d35c  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000d363  mov     r9d, ebx; char *
0x18000d366  mov     edx, 265h; void *
0x18000d36b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d370  mov     eax, ebx
0x18000d372  jmp     short loc_18000D376
0x18000d374  xor     eax, eax
0x18000d376  add     rsp, 30h
0x18000d37a  pop     rbx
0x18000d37b  retn
```
