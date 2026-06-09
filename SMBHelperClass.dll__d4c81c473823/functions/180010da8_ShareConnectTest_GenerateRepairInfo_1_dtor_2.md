# _ShareConnectTest::GenerateRepairInfo_::_1_::dtor$2

- ea: `0x180010da8`
- end: `0x180010db4`
- name: `_ShareConnectTest::GenerateRepairInfo_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a98c`

## pseudocode

```c
void __fastcall ShareConnectTest::GenerateRepairInfo_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  StringEnumerationMatcher::~StringEnumerationMatcher((StringEnumerationMatcher *)(a2 + 80));
}

```

## disassembly

```asm
0x180010da8  lea     rcx, [rdx+50h]; this
0x180010daf  jmp     ??1StringEnumerationMatcher@@QEAA@XZ; StringEnumerationMatcher::~StringEnumerationMatcher(void)
```
