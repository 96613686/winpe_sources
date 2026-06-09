# _Accommodation::Accommodation_::_1_::dtor$8

- ea: `0x140015fbc`
- end: `0x140015fcc`
- name: `_Accommodation::Accommodation_::_1_::dtor$8`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003750`

## pseudocode

```c
__int64 __fastcall Accommodation::Accommodation_::_1_::dtor_8(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(*(_QWORD *)(a2 + 48) + 72LL));
}

```

## disassembly

```asm
0x140015fbc  mov     rcx, [rdx+30h]
0x140015fc3  add     rcx, 48h ; 'H'
0x140015fc7  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
