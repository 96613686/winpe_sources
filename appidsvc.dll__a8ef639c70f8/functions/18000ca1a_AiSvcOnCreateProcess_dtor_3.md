# AiSvcOnCreateProcess$dtor$3

- ea: `0x18000ca1a`
- end: `0x18000ca26`
- name: `AiSvcOnCreateProcess$dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180006378`

## pseudocode

```c
void __fastcall AiSvcOnCreateProcess_dtor_3(__int64 a1, __int64 a2)
{
  SrwLock::~SrwLock((SrwLock *)(a2 + 160));
}

```

## disassembly

```asm
0x18000ca1a  lea     rcx, [rdx+0A0h]; this
0x18000ca21  jmp     ??1SrwLock@@QEAA@XZ; SrwLock::~SrwLock(void)
```
