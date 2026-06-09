# SRCacheManager_GetProperty_UInt64

- ea: `0x18000d810`
- end: `0x18000d88f`
- name: `SRCacheManager_GetProperty_UInt64`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000940c`
- `0x18000d810`
- `0x18000fc2c`

## string_xrefs

- `0x18000d855`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`
- `0x18000d86e`: `onecore\base\appmodel\staterepository\core\lib\srcachemanager.cpp`

## pseudocode

```c
__int64 __fastcall SRCacheManager_GetProperty_UInt64(__int64 a1, const unsigned __int16 *a2, unsigned __int64 *a3)
{
  int UInt64Value; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  UInt64Value = Common::RegistryKey::GetUInt64Value((Common::RegistryKey *)(a1 + 8), a2, a3);
  v5 = UInt64Value;
  if ( UInt64Value <= -2147024895 || (unsigned int)(UInt64Value + 2147024892) <= 0x7FF8FFFB )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x68,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)(unsigned int)UInt64Value,
      v7);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachemanager.cpp",
      (const char *)v5,
      v8);
    return v5;
  }
  else
  {
    if ( UInt64Value < 0 )
      *a3 = 0;
    return 0;
  }
}

```

## disassembly

```asm
0x18000d810  mov     [rsp+arg_0], rbx
0x18000d815  push    rdi; int
0x18000d816  sub     rsp, 20h
0x18000d81a  add     rcx, 8; this
0x18000d81e  mov     rdi, r8
0x18000d821  call    ?GetUInt64Value@RegistryKey@Common@@QEAAJPEBGPEA_K@Z; Common::RegistryKey::GetUInt64Value(ushort const *,unsigned __int64 *)
0x18000d826  mov     ebx, eax
0x18000d828  cmp     eax, 80070001h
0x18000d82d  jle     short loc_18000D850
0x18000d82f  lea     ecx, [rax+7FF8FFFCh]
0x18000d835  cmp     ecx, 7FF8FFFBh
0x18000d83b  jbe     short loc_18000D850
0x18000d83d  shr     ebx, 1Fh
0x18000d840  xor     bl, 1
0x18000d843  jnz     short loc_18000D84C
0x18000d845  mov     qword ptr [rdi], 0
0x18000d84c  xor     eax, eax
0x18000d84e  jmp     short loc_18000D884
0x18000d850  mov     rcx, [rsp+28h]; this
0x18000d855  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d85c  mov     r9d, ebx; char *
0x18000d85f  mov     edx, 68h ; 'h'; void *
0x18000d864  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d869  mov     rcx, [rsp+28h]; this
0x18000d86e  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\staterepositor"...
0x18000d875  mov     r9d, ebx; char *
0x18000d878  mov     edx, 0D8h; void *
0x18000d87d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d882  mov     eax, ebx
0x18000d884  mov     rbx, [rsp+28h+arg_0]
0x18000d889  add     rsp, 20h
0x18000d88d  pop     rdi
0x18000d88e  retn
```
