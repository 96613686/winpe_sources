# _DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$2

- ea: `0x18000ccd8`
- end: `0x18000cce4`
- name: `_DiagnosisTextBuilderImpl::GetXML_::_1_::dtor$2`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000a850`

## pseudocode

```c
__int64 __fastcall DiagnosisTextBuilderImpl::GetXML_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 128));
}

```

## disassembly

```asm
0x18000ccd8  lea     rcx, [rdx+80h]
0x18000ccdf  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
