# _Accommodation::Accommodation_::_1_::dtor$0

- ea: `0x140015cbe`
- end: `0x140015cca`
- name: `_Accommodation::Accommodation_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140003750`

## pseudocode

```c
__int64 __fastcall Accommodation::Accommodation_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(*(_QWORD **)(a2 + 48));
}

```

## disassembly

```asm
0x140015cbe  mov     rcx, [rdx+30h]
0x140015cc5  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
