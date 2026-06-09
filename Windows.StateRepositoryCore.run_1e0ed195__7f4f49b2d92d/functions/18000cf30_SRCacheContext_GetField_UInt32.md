# SRCacheContext_GetField_UInt32

- ea: `0x18000cf30`
- end: `0x18000cf98`
- name: `SRCacheContext_GetField_UInt32`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000cf30`
- `0x18000fbe8`

## string_xrefs

- `0x18000cf64`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`
- `0x18000cf78`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheContext_GetField_UInt32(
        Common::RegistryKey *a1,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  unsigned int UInt32Value; // ebx
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a3 = 0;
  if ( !*(_QWORD *)a1 )
  {
    UInt32Value = -2147019873;
    v4 = 114;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)UInt32Value,
      v6);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)UInt32Value,
      v7);
    return UInt32Value;
  }
  UInt32Value = Common::RegistryKey::GetUInt32Value(a1, a2, a3);
  if ( (UInt32Value & 0x80000000) != 0 )
  {
    v4 = 116;
    goto LABEL_5;
  }
  return 0;
}

```

## disassembly

```asm
0x18000cf30  push    rbx; int
0x18000cf32  sub     rsp, 20h
0x18000cf36  mov     dword ptr [r8], 0
0x18000cf3d  cmp     qword ptr [rcx], 0
0x18000cf41  jnz     short loc_18000CF4F
0x18000cf43  mov     ebx, 8007139Fh
0x18000cf48  mov     edx, 72h ; 'r'; unsigned __int16 *
0x18000cf4d  jmp     short loc_18000CF5F
0x18000cf4f  call    ?GetUInt32Value@RegistryKey@Common@@QEAAJPEBGPEAI@Z; Common::RegistryKey::GetUInt32Value(ushort const *,uint *)
0x18000cf54  mov     ebx, eax
0x18000cf56  test    eax, eax
0x18000cf58  jns     short loc_18000CF90
0x18000cf5a  mov     edx, 74h ; 't'; void *
0x18000cf5f  mov     rcx, [rsp+28h]; this
0x18000cf64  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cf6b  mov     r9d, ebx; char *
0x18000cf6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf73  mov     rcx, [rsp+28h]; this
0x18000cf78  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000cf7f  mov     r9d, ebx; char *
0x18000cf82  mov     edx, 213h; void *
0x18000cf87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cf8c  mov     eax, ebx
0x18000cf8e  jmp     short loc_18000CF92
0x18000cf90  xor     eax, eax
0x18000cf92  add     rsp, 20h
0x18000cf96  pop     rbx
0x18000cf97  retn
```
