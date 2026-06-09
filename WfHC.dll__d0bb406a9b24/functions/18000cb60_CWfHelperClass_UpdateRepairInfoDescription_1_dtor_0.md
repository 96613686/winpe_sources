# _CWfHelperClass::UpdateRepairInfoDescription_::_1_::dtor$0

- ea: `0x18000cb60`
- end: `0x18000cb6c`
- name: `_CWfHelperClass::UpdateRepairInfoDescription_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a928`

## pseudocode

```c
void __fastcall CWfHelperClass::UpdateRepairInfoDescription_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DiagnosisTextBuilder::~DiagnosisTextBuilder((DiagnosisTextBuilder *)(a2 + 56));
}

```

## disassembly

```asm
0x18000cb60  lea     rcx, [rdx+38h]; this
0x18000cb67  jmp     ??1DiagnosisTextBuilder@@QEAA@XZ; DiagnosisTextBuilder::~DiagnosisTextBuilder(void)
```
