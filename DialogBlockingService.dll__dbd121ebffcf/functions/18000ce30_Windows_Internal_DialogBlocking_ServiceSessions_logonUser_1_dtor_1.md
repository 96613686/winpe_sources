# _Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$1

- ea: `0x18000ce30`
- end: `0x18000ce3c`
- name: `_Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x180009990`

## pseudocode

```c
__int64 __fastcall Windows::Internal::DialogBlocking::ServiceSessions::logonUser_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return std::unique_lock<std::mutex>::~unique_lock<std::mutex>(a2 + 32);
}

```

## disassembly

```asm
0x18000ce30  lea     rcx, [rdx+20h]
0x18000ce37  jmp     ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
```
