# _ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$25

- ea: `0x18000e8a8`
- end: `0x18000e8b4`
- name: `_ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$25`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x180003400`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor_25(__int64 a1, __int64 a2)
{
  return ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::~CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>(*(_QWORD *)(a2 + 88));
}

```

## disassembly

```asm
0x18000e8a8  mov     rcx, [rdx+58h]
0x18000e8af  jmp     ??1?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEAA@XZ; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::~CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>(void)
```
