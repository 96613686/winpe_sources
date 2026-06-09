# _CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$1

- ea: `0x14004061f`
- end: `0x14004062b`
- name: `_CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140002aac`

## pseudocode

```c
void __fastcall CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CCoInit::~CCoInit((CCoInit *)(a2 + 136));
}

```

## disassembly

```asm
0x14004061f  lea     rcx, [rdx+88h]; this
0x140040626  jmp     ??1CCoInit@@QEAA@XZ; CCoInit::~CCoInit(void)
```
