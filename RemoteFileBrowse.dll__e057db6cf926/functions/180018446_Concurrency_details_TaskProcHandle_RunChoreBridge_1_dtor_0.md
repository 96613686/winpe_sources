# _Concurrency::details::_TaskProcHandle::_RunChoreBridge_::_1_::dtor$0

- ea: `0x180018446`
- end: `0x180018452`
- name: `_Concurrency::details::_TaskProcHandle::_RunChoreBridge_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fcc0`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_TaskProcHandle::_RunChoreBridge_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return std::unique_ptr<Concurrency::details::_TaskProcHandle>::~unique_ptr<Concurrency::details::_TaskProcHandle>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 48));
}

```

## disassembly

```asm
0x180018446  lea     rcx, [rdx+30h]
0x18001844d  jmp     ??1?$unique_ptr@U_TaskProcHandle@details@Concurrency@@U?$default_delete@U_TaskProcHandle@details@Concurrency@@@std@@@std@@QEAA@XZ; std::unique_ptr<Concurrency::details::_TaskProcHandle>::~unique_ptr<Concurrency::details::_TaskProcHandle>(void)
```
