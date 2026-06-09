# bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(ushort,bond::Metadata const &,bool const &)

- ea: `0x18000c8bc`
- end: `0x18000c8f3`
- name: `??$Field@_N@?$Serializer@V?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEB_N@Z`
- size: `55`
- prototype: `char __fastcall(_QWORD *, __int64, __int64, _BYTE *)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000cf70`
- `0x18000d0b0`
- `0x18000d3fc`
- `0x18000d570`
- `0x18000d808`
- `0x18000e4f0`
- `0x18000e6b4`
- `0x18000e94c`
- `0x18000eef4`
- `0x18000f0e4`
- `0x18000f46c`
- `0x18000f8d8`
- `0x18001bb58`
- `0x18001c764`

## callees

- `0x18000c8bc`
- `0x1800228d8`

## pseudocode

```c
char __fastcall bond::Serializer<bond::CompactBinaryWriter<bond::OutputCounter>>::Field<bool>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        _BYTE *a4)
{
  _DWORD **v4; // rcx

  if ( *(_DWORD *)(a3 + 80) || *a4 != (*(_QWORD *)(a3 + 88) != 0) )
  {
    bond::CompactBinaryWriter<bond::OutputCounter>::WriteFieldBegin(*a1, a2, (unsigned __int16)a2);
    ++**v4;
  }
  return 0;
}

```

## disassembly

```asm
0x18000c8bc  sub     rsp, 28h
0x18000c8c0  cmp     dword ptr [r8+50h], 0
0x18000c8c5  jnz     short loc_18000C8DB
0x18000c8c7  movzx   eax, byte ptr [r9]
0x18000c8cb  xor     r10d, r10d
0x18000c8ce  cmp     [r8+58h], r10
0x18000c8d2  setnz   r10b
0x18000c8d6  cmp     eax, r10d
0x18000c8d9  jz      short loc_18000C8EC
0x18000c8db  mov     rcx, [rcx]
0x18000c8de  movzx   r8d, dx
0x18000c8e2  call    ?WriteFieldBegin@?$CompactBinaryWriter@VOutputCounter@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@G@Z; bond::CompactBinaryWriter<bond::OutputCounter>::WriteFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType,ushort)
0x18000c8e7  mov     rcx, [rcx]
0x18000c8ea  inc     dword ptr [rcx]
0x18000c8ec  xor     al, al
0x18000c8ee  add     rsp, 28h
0x18000c8f2  retn
```
