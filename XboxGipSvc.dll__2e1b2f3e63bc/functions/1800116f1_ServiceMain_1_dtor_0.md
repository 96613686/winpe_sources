# _ServiceMain_::_1_::dtor$0

- ea: `0x1800116f1`
- end: `0x1800116fd`
- name: `_ServiceMain_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800045e4`

## pseudocode

```c
void __fastcall ServiceMain_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  GipMgmtSvc::~GipMgmtSvc((GipMgmtSvc *)(a2 + 272));
}

```

## disassembly

```asm
0x1800116f1  lea     rcx, [rdx+110h]; this
0x1800116f8  jmp     ??1GipMgmtSvc@@QEAA@XZ; GipMgmtSvc::~GipMgmtSvc(void)
```
