# bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV1(void)

- ea: `0x180019834`
- end: `0x1800198b3`
- name: `?SkipStructV1@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXXZ`
- size: `127`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000b9b0`
- `0x18000ba24`
- `0x18000bde8`

## callees

- `0x18000ba24`
- `0x18000ff68`
- `0x18001199c`
- `0x180017664`
- `0x1800176f4`
- `0x180019834`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall bond::CompactBinaryReader<bond::InputBuffer>::SkipStructV1(bond::InputBuffer *this)
{
  int v2; // eax
  char v3; // [rsp+38h] [rbp+10h] BYREF
  __int16 v4; // [rsp+40h] [rbp+18h]
  int v5; // [rsp+48h] [rbp+20h]

  bond::detail::RecursionGuard::RecursionGuard((bond::detail::RecursionGuard *)&v3);
  do
  {
    bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(this);
    v4 = 0;
    v5 = 0;
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
    v2 = v5;
    if ( !v5 )
      break;
    do
    {
      if ( v2 == 1 )
        break;
      bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(this, v2);
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
      v2 = v5;
    }
    while ( v5 );
  }
  while ( v2 );
  bond::detail::RecursionGuard::~RecursionGuard((bond::detail::RecursionGuard *)&v3);
}

```

## disassembly

```asm
0x180019834  push    rbx
0x180019836  sub     rsp, 20h
0x18001983a  mov     rbx, rcx
0x18001983d  lea     rcx, [rsp+28h+arg_8]; this
0x180019842  call    ??0RecursionGuard@detail@bond@@QEAA@XZ; bond::detail::RecursionGuard::RecursionGuard(void)
0x180019847  nop
0x180019848  xor     edx, edx
0x18001984a  mov     rcx, rbx; this
0x18001984d  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180019852  xor     eax, eax
0x180019854  mov     [rsp+28h+arg_10], ax
0x180019859  mov     [rsp+28h+arg_18], eax
0x18001985d  lea     r8, [rsp+28h+arg_10]
0x180019862  lea     rdx, [rsp+28h+arg_18]
0x180019867  mov     rcx, rbx; this
0x18001986a  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18001986f  mov     eax, [rsp+28h+arg_18]
0x180019873  test    eax, eax
0x180019875  jz      short loc_1800198A4
0x180019877  cmp     eax, 1
0x18001987a  jz      short loc_1800198A0
0x18001987c  mov     edx, eax
0x18001987e  mov     rcx, rbx; this
0x180019881  call    ??$SkipType@$$V@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::_bond_enumerators::BondDataType::BondDataType)
0x180019886  lea     r8, [rsp+28h+arg_10]
0x18001988b  lea     rdx, [rsp+28h+arg_18]
0x180019890  mov     rcx, rbx; this
0x180019893  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180019898  mov     eax, [rsp+28h+arg_18]
0x18001989c  test    eax, eax
0x18001989e  jnz     short loc_180019877
0x1800198a0  test    eax, eax
0x1800198a2  jnz     short loc_180019848
0x1800198a4  lea     rcx, [rsp+28h+arg_8]; this
0x1800198a9  add     rsp, 20h
0x1800198ad  pop     rbx
0x1800198ae  jmp     ??1RecursionGuard@detail@bond@@QEAA@XZ; bond::detail::RecursionGuard::~RecursionGuard(void)
```
