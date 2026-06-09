# _CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::dtor$2

- ea: `0x180010bbe`
- end: `0x180010bca`
- name: `_CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000361c`

## pseudocode

```c
__int64 __fastcall CSMBHelperClass::ReproduceFailureThreadExecutive_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(a2 + 48);
}

```

## disassembly

```asm
0x180010bbe  lea     rcx, [rdx+30h]
0x180010bc5  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
