# _SettingsCopier::DeleteATSettings_::_1_::dtor$2

- ea: `0x140015d18`
- end: `0x140015d24`
- name: `_SettingsCopier::DeleteATSettings_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003750`

## pseudocode

```c
__int64 __fastcall SettingsCopier::DeleteATSettings_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 56));
}

```

## disassembly

```asm
0x140015d18  lea     rcx, [rdx+38h]
0x140015d1f  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
