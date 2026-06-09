# __anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor$1

- ea: `0x140015928`
- end: `0x140015934`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x140006364`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  DiagHubCommon::ModulePath::~ModulePath(a2 + 136);
}

```

## disassembly

```asm
0x140015928  lea     rcx, [rdx+88h]; this
0x14001592f  jmp     ??1ModulePath@DiagHubCommon@@QEAA@XZ; DiagHubCommon::ModulePath::~ModulePath(void)
```
