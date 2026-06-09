# std::_Task_async_state<void>::_Wait(void)

- ea: `0x180012c10`
- end: `0x180012c2f`
- name: `?_Wait@?$_Task_async_state@X@std@@UEAAXXZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64, const char *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18001242c`
- `0x180012c10`
- `0x180012c38`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Task_async_state<void>::_Wait(__int64 a1, const char *a2)
{
  if ( !*(_QWORD *)(a1 + 272) )
    Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(0, a2);
  return Concurrency::details::_Task_impl_base::_Wait();
}

```

## disassembly

```asm
0x180012c10  sub     rsp, 28h
0x180012c14  mov     rcx, [rcx+110h]
0x180012c1b  test    rcx, rcx
0x180012c1e  jz      short loc_180012C29
0x180012c20  add     rsp, 28h
0x180012c24  jmp     ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x180012c29  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
```
