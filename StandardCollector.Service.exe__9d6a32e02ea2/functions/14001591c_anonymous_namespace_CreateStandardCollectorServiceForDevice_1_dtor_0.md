# __anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor$0

- ea: `0x14001591c`
- end: `0x140015928`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000463c`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForDevice_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  DiagHubCommon::AutoCriticalSection::~AutoCriticalSection((LPCRITICAL_SECTION *)(a2 + 96));
}

```

## disassembly

```asm
0x14001591c  lea     rcx, [rdx+60h]; this
0x140015923  jmp     ??1AutoCriticalSection@DiagHubCommon@@QEAA@XZ; DiagHubCommon::AutoCriticalSection::~AutoCriticalSection(void)
```
