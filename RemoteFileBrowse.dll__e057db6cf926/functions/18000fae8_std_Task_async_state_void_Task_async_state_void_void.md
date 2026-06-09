# std::_Task_async_state<void>::~_Task_async_state<void>(void)

- ea: `0x18000fae8`
- end: `0x18000fb6b`
- name: `??1?$_Task_async_state@X@std@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x180010680`

## callees

- `0x18000fa18`
- `0x18000fae8`
- `0x18001242c`
- `0x180012c38`
- `0x180019010`

## pseudocode

```c
void __fastcall std::_Task_async_state<void>::~_Task_async_state<void>(_QWORD *a1)
{
  __int64 v2; // rdx
  volatile signed __int32 *v3; // rbx

  *a1 = &std::_Task_async_state<void>::`vftable';
  if ( !a1[34] )
    Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
  Concurrency::details::_Task_impl_base::_Wait();
  v3 = (volatile signed __int32 *)a1[35];
  if ( v3 )
  {
    if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>((__int64)a1, v2);
}

```

## disassembly

```asm
0x18000fae8  mov     [rsp+arg_0], rbx
0x18000faed  push    rdi
0x18000faee  sub     rsp, 20h
0x18000faf2  mov     rdi, rcx
0x18000faf5  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x18000fafc  mov     [rcx], rax
0x18000faff  mov     rcx, [rcx+110h]
0x18000fb06  test    rcx, rcx
0x18000fb09  jz      short loc_18000FB65
0x18000fb0b  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x18000fb10  mov     rbx, [rdi+118h]
0x18000fb17  test    rbx, rbx
0x18000fb1a  jz      short loc_18000FB53
0x18000fb1c  or      eax, 0FFFFFFFFh
0x18000fb1f  lock xadd [rbx+8], eax
0x18000fb24  cmp     eax, 1
0x18000fb27  jnz     short loc_18000FB53
0x18000fb29  mov     rax, [rbx]
0x18000fb2c  mov     rcx, rbx
0x18000fb2f  mov     rax, [rax]
0x18000fb32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb37  or      eax, 0FFFFFFFFh
0x18000fb3a  lock xadd [rbx+0Ch], eax
0x18000fb3f  cmp     eax, 1
0x18000fb42  jnz     short loc_18000FB53
0x18000fb44  mov     rax, [rbx]
0x18000fb47  mov     rcx, rbx
0x18000fb4a  mov     rax, [rax+8]
0x18000fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb53  mov     rcx, rdi
0x18000fb56  mov     rbx, [rsp+28h+arg_0]
0x18000fb5b  add     rsp, 20h
0x18000fb5f  pop     rdi
0x18000fb60  jmp     ??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ; std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)
0x18000fb65  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
```
