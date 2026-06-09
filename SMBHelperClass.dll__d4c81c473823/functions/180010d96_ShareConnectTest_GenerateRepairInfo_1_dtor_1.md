# _ShareConnectTest::GenerateRepairInfo_::_1_::dtor$1

- ea: `0x180010d96`
- end: `0x180010da2`
- name: `_ShareConnectTest::GenerateRepairInfo_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000a670`

## pseudocode

```c
void __fastcall ShareConnectTest::GenerateRepairInfo_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  EditDistance::~EditDistance((EditDistance *)(a2 + 160));
}

```

## disassembly

```asm
0x180010d96  lea     rcx, [rdx+0A0h]; this
0x180010d9d  jmp     ??1EditDistance@@QEAA@XZ; EditDistance::~EditDistance(void)
```
