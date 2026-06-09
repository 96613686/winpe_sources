# _ServiceMainImpl_::_1_::dtor$1

- ea: `0x180017910`
- end: `0x18001791c`
- name: `_ServiceMainImpl_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002b50`

## pseudocode

```c
void __fastcall ServiceMainImpl_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  ProcessRefCount::~ProcessRefCount((ProcessRefCount *)(a2 + 64));
}

```

## disassembly

```asm
0x180017910  lea     rcx, [rdx+40h]; this
0x180017917  jmp     ??1ProcessRefCount@@QEAA@XZ; ProcessRefCount::~ProcessRefCount(void)
```
