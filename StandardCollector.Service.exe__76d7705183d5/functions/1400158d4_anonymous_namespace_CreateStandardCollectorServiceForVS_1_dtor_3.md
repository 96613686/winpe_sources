# __anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$3

- ea: `0x1400158d4`
- end: `0x1400158e0`
- name: `__anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x14000463c`

## pseudocode

```c
void __fastcall _anonymous_namespace_::CreateStandardCollectorServiceForVS_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  DiagHubCommon::AutoCriticalSection::~AutoCriticalSection((LPCRITICAL_SECTION *)(a2 + 88));
}

```

## disassembly

```asm
0x1400158d4  lea     rcx, [rdx+58h]; this
0x1400158db  jmp     ??1AutoCriticalSection@DiagHubCommon@@QEAA@XZ
```
