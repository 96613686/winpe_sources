# s_NgcCtnrEnumDeleteNode$dtor$1

- ea: `0x18001ef3f`
- end: `0x18001ef4b`
- name: `s_NgcCtnrEnumDeleteNode$dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000cc60`

## pseudocode

```c
void __fastcall s_NgcCtnrEnumDeleteNode_dtor_1(__int64 a1, __int64 a2)
{
  ScopedTaskCounter::~ScopedTaskCounter((ScopedTaskCounter *)(a2 + 104));
}

```

## disassembly

```asm
0x18001ef3f  lea     rcx, [rdx+68h]; this
0x18001ef46  jmp     ??1ScopedTaskCounter@@QEAA@XZ; ScopedTaskCounter::~ScopedTaskCounter(void)
```
