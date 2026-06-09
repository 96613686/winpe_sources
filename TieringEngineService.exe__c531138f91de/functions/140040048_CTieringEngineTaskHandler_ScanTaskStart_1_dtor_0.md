# _CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$0

- ea: `0x140040048`
- end: `0x140040054`
- name: `_CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x140005420`

## pseudocode

```c
void __fastcall CTieringEngineTaskHandler::ScanTaskStart_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CHResultImp::~CHResultImp((CHResultImp *)(a2 + 56));
}

```

## disassembly

```asm
0x140040048  lea     rcx, [rdx+38h]; this
0x14004004f  jmp     ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
```
