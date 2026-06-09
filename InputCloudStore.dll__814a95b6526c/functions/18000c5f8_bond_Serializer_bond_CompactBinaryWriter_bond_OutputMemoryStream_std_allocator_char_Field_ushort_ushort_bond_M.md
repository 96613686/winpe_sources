# bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<ushort>(ushort,bond::Metadata const &,ushort const &)

- ea: `0x18000c5f8`
- end: `0x18000c643`
- name: `??$Field@G@?$Serializer@V?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@@bond@@QEBA_NGAEBUMetadata@1@AEBG@Z`
- size: `75`
- prototype: `char __fastcall(_QWORD *, unsigned __int16, __int64, _WORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ce80`
- `0x18000d66c`
- `0x18000e638`
- `0x18000f02c`

## callees

- `0x18000c5f8`
- `0x180011c40`
- `0x180022850`

## pseudocode

```c
char __fastcall bond::Serializer<bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>>::Field<unsigned short>(
        _QWORD *a1,
        unsigned __int16 a2,
        __int64 a3,
        _WORD *a4)
{
  _QWORD *v5; // rbx

  if ( *(_DWORD *)(a3 + 80) || *a4 != *(_WORD *)(a3 + 88) )
  {
    v5 = (_QWORD *)*a1;
    bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(*a1, 4, a2);
    bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<unsigned short>(*v5, (unsigned __int16)*a4);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c5f8  mov     [rsp+arg_0], rbx
0x18000c5fd  push    rdi
0x18000c5fe  sub     rsp, 20h
0x18000c602  cmp     dword ptr [r8+50h], 0
0x18000c607  mov     rdi, r9
0x18000c60a  jnz     short loc_18000C617
0x18000c60c  movzx   eax, word ptr [r8+58h]
0x18000c611  cmp     [r9], ax
0x18000c615  jz      short loc_18000C636
0x18000c617  mov     rbx, [rcx]
0x18000c61a  movzx   r8d, dx
0x18000c61e  mov     rcx, rbx
0x18000c621  mov     edx, 4
0x18000c626  call    ?WriteFieldBegin@?$CompactBinaryWriter@V?$OutputMemoryStream@V?$allocator@D@std@@@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@G@Z; bond::CompactBinaryWriter<bond::OutputMemoryStream<std::allocator<char>>>::WriteFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType,ushort)
0x18000c62b  movzx   edx, word ptr [rdi]
0x18000c62e  mov     rcx, [rbx]
0x18000c631  call    ??$WriteVariableUnsigned@G@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXG@Z; bond::OutputMemoryStream<std::allocator<char>>::WriteVariableUnsigned<ushort>(ushort)
0x18000c636  mov     rbx, [rsp+28h+arg_0]
0x18000c63b  xor     al, al
0x18000c63d  add     rsp, 20h
0x18000c641  pop     rdi
0x18000c642  retn
```
