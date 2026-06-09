# _Accommodation::Accommodation_::_1_::dtor$3

- ea: `0x140015f4e`
- end: `0x140015f5e`
- name: `_Accommodation::Accommodation_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003750`

## pseudocode

```c
__int64 __fastcall Accommodation::Accommodation_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL));
}

```

## disassembly

```asm
0x140015f4e  mov     rcx, [rdx+30h]
0x140015f55  add     rcx, 18h
0x140015f59  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
