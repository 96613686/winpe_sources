# _ShareConnectTest::GenerateRepairInfo_::_1_::dtor$0

- ea: `0x180010d84`
- end: `0x180010d90`
- name: `_ShareConnectTest::GenerateRepairInfo_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000af74`

## pseudocode

```c
void __fastcall ShareConnectTest::GenerateRepairInfo_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  NetShareEnumerator::~NetShareEnumerator((NetShareEnumerator *)(a2 + 192));
}

```

## disassembly

```asm
0x180010d84  lea     rcx, [rdx+0C0h]; this
0x180010d8b  jmp     ??1NetShareEnumerator@@QEAA@XZ; NetShareEnumerator::~NetShareEnumerator(void)
```
