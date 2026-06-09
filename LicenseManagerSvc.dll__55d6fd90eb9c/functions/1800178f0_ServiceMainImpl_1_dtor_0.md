# _ServiceMainImpl_::_1_::dtor$0

- ea: `0x1800178f0`
- end: `0x1800178fc`
- name: `_ServiceMainImpl_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180002b44`

## pseudocode

```c
void __fastcall ServiceMainImpl_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  ServiceContext::~ServiceContext((ServiceContext *)(a2 + 64));
}

```

## disassembly

```asm
0x1800178f0  lea     rcx, [rdx+40h]; this
0x1800178f7  jmp     ??1ServiceContext@@QEAA@XZ; ServiceContext::~ServiceContext(void)
```
