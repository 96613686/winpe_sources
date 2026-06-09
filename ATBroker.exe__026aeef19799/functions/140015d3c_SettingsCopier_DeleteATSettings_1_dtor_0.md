# _SettingsCopier::DeleteATSettings_::_1_::dtor$0

- ea: `0x140015d3c`
- end: `0x140015d48`
- name: `_SettingsCopier::DeleteATSettings_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140003750`

## pseudocode

```c
__int64 __fastcall SettingsCopier::DeleteATSettings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::~CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((_QWORD *)(a2 + 48));
}

```

## disassembly

```asm
0x140015d3c  lea     rcx, [rdx+30h]
0x140015d43  jmp     ??1?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::~CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
```
