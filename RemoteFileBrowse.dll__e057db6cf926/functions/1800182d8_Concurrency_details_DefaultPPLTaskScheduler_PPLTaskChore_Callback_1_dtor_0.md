# _Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback_::_1_::dtor$0

- ea: `0x1800182d8`
- end: `0x1800182e4`
- name: `_Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x18000fce8`

## pseudocode

```c
void __fastcall Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore::_Callback_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>(
    (Concurrency::details **)(a2 + 48),
    (struct Concurrency::details::_Threadpool_chore *)a2);
}

```

## disassembly

```asm
0x1800182d8  lea     rcx, [rdx+30h]
0x1800182df  jmp     ??1?$unique_ptr@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@U?$default_delete@V_PPLTaskChore@_DefaultPPLTaskScheduler@details@Concurrency@@@std@@@std@@QEAA@XZ; std::unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>::~unique_ptr<Concurrency::details::_DefaultPPLTaskScheduler::_PPLTaskChore>(void)
```
