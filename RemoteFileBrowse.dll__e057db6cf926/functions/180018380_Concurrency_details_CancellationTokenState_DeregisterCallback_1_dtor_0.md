# _Concurrency::details::_CancellationTokenState::_DeregisterCallback_::_1_::dtor$0

- ea: `0x180018380`
- end: `0x18001838c`
- name: `_Concurrency::details::_CancellationTokenState::_DeregisterCallback_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000fc90`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_CancellationTokenState::_DeregisterCallback_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  return std::lock_guard<std::mutex>::~lock_guard<std::mutex>(a2 + 96);
}

```

## disassembly

```asm
0x180018380  lea     rcx, [rdx+60h]
0x180018387  jmp     ??1?$lock_guard@Vmutex@std@@@std@@QEAA@XZ; std::lock_guard<std::mutex>::~lock_guard<std::mutex>(void)
```
