# _ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$24

- ea: `0x18000e88c`
- end: `0x18000e89c`
- name: `_ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor$24`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callees

- `0x18000343c`

## pseudocode

```c
void __fastcall ATL::CAtlModule::UpdateRegistryFromResource_::_1_::dtor_24(__int64 a1, __int64 a2)
{
  ATL::CExpansionVector::~CExpansionVector((ATL::CExpansionVector *)(a2 + 56));
}

```

## disassembly

```asm
0x18000e88c  lea     rcx, [rdx+30h]
0x18000e893  add     rcx, 8; this
0x18000e897  jmp     ??1CExpansionVector@ATL@@QEAA@XZ; ATL::CExpansionVector::~CExpansionVector(void)
```
