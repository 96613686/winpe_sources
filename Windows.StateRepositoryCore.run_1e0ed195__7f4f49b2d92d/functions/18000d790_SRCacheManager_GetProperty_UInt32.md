# SRCacheManager_GetProperty_UInt32

- ea: `0x18000d790`
- end: `0x18000d806`
- name: `SRCacheManager_GetProperty_UInt32`
- size: `118`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d4d0`
- `0x18000d790`

## string_xrefs

- `0x18000d7bb`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d7d4`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_GetProperty_UInt32(__int64 a1, __int64 a2, _DWORD *a3)
{
  int UInt32ValueIf; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v10; // [rsp+30h] [rbp+8h] BYREF

  v10 = 0;
  UInt32ValueIf = Common::RegistryKey::GetUInt32ValueIfExists<unsigned int>(a1 + 8, a2, a3, &v10);
  v5 = UInt32ValueIf;
  if ( UInt32ValueIf >= 0 )
  {
    if ( !v10 )
      *a3 = 0;
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)(unsigned int)UInt32ValueIf,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)v5,
      v8);
    return v5;
  }
}

```

## disassembly

```asm
0x18000d790  mov     [rsp+arg_8], rbx
0x18000d795  push    rdi; int
0x18000d796  sub     rsp, 20h
0x18000d79a  add     rcx, 8
0x18000d79e  mov     [rsp+28h+arg_0], 0
0x18000d7a3  lea     r9, [rsp+28h+arg_0]
0x18000d7a8  mov     rdi, r8
0x18000d7ab  call    ??$GetUInt32ValueIfExists@I@RegistryKey@Common@@QEAAJPEBGPEAIPEA_N@Z; Common::RegistryKey::GetUInt32ValueIfExists<uint>(ushort const *,uint *,bool *)
0x18000d7b0  mov     ebx, eax
0x18000d7b2  test    eax, eax
0x18000d7b4  jns     short loc_18000D7EC
0x18000d7b6  mov     rcx, [rsp+28h]; this
0x18000d7bb  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d7c2  mov     r9d, eax; char *
0x18000d7c5  mov     edx, 53h ; 'S'; void *
0x18000d7ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7cf  mov     rcx, [rsp+28h]; this
0x18000d7d4  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d7db  mov     r9d, ebx; char *
0x18000d7de  mov     edx, 0C4h; void *
0x18000d7e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7e8  mov     eax, ebx
0x18000d7ea  jmp     short loc_18000D7FB
0x18000d7ec  cmp     [rsp+28h+arg_0], 0
0x18000d7f1  jnz     short loc_18000D7F9
0x18000d7f3  mov     dword ptr [rdi], 0
0x18000d7f9  xor     eax, eax
0x18000d7fb  mov     rbx, [rsp+28h+arg_8]
0x18000d800  add     rsp, 20h
0x18000d804  pop     rdi
0x18000d805  retn
```
