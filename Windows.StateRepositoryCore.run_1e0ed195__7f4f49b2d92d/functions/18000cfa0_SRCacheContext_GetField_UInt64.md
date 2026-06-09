# SRCacheContext_GetField_UInt64

- ea: `0x18000cfa0`
- end: `0x18000d008`
- name: `SRCacheContext_GetField_UInt64`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000cfa0`
- `0x18000fc2c`

## string_xrefs

- `0x18000cfd4`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cfe8`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_GetField_UInt64(
        Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  unsigned int UInt64Value; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  if ( !*(_QWORD *)a1 )
  {
    UInt64Value = -2147019873;
    v4 = 126;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)UInt64Value,
      v6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)UInt64Value,
      v7);
    return UInt64Value;
  }
  UInt64Value = Common::RegistryKey::GetUInt64Value(a1, a2, a3);
  if ( (UInt64Value & 0x80000000) != 0 )
  {
    v4 = 128;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cfa0  push    rbx; int
0x18000cfa2  sub     rsp, 20h
0x18000cfa6  mov     qword ptr [r8], 0
0x18000cfad  cmp     qword ptr [rcx], 0
0x18000cfb1  jnz     short loc_18000CFBF
0x18000cfb3  mov     ebx, 8007139Fh
0x18000cfb8  mov     edx, 7Eh ; '~'; unsigned __int16 *
0x18000cfbd  jmp     short loc_18000CFCF
0x18000cfbf  call    ?GetUInt64Value@RegistryKey@Common@@QEAAJPEBGPEA_K@Z; Common::RegistryKey::GetUInt64Value(ushort const *,unsigned __int64 *)
0x18000cfc4  mov     ebx, eax
0x18000cfc6  test    eax, eax
0x18000cfc8  jns     short loc_18000D000
0x18000cfca  mov     edx, 80h; void *
0x18000cfcf  mov     rcx, [rsp+28h]; this
0x18000cfd4  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cfdb  mov     r9d, ebx; char *
0x18000cfde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cfe3  mov     rcx, [rsp+28h]; this
0x18000cfe8  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cfef  mov     r9d, ebx; char *
0x18000cff2  mov     edx, 21Dh; void *
0x18000cff7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cffc  mov     eax, ebx
0x18000cffe  jmp     short loc_18000D002
0x18000d000  xor     eax, eax
0x18000d002  add     rsp, 20h
0x18000d006  pop     rbx
0x18000d007  retn
```
