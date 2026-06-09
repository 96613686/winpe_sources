# std::_Task_async_state<void>::_Get_value(bool)

- ea: `0x1800120d0`
- end: `0x18001210c`
- name: `?_Get_value@?$_Task_async_state@X@std@@UEAAAEAH_N@Z`
- size: `60`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180011f90`
- `0x1800120d0`
- `0x18001242c`
- `0x180012c38`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Task_async_state<void>::_Get_value(__int64 a1, char a2)
{
  __int64 v4; // rdx

  if ( !*(_QWORD *)(a1 + 272) )
    Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl();
  Concurrency::details::_Task_impl_base::_Wait();
  LOBYTE(v4) = a2;
  return std::_Associated_state<int>::_Get_value(a1, v4);
}

```

## disassembly

```asm
0x1800120d0  mov     [rsp+arg_0], rbx
0x1800120d5  push    rdi
0x1800120d6  sub     rsp, 20h
0x1800120da  mov     rbx, rcx
0x1800120dd  mov     dil, dl
0x1800120e0  mov     rcx, [rcx+110h]
0x1800120e7  test    rcx, rcx
0x1800120ea  jz      short loc_180012106
0x1800120ec  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800120f1  mov     dl, dil
0x1800120f4  mov     rcx, rbx
0x1800120f7  mov     rbx, [rsp+28h+arg_0]
0x1800120fc  add     rsp, 20h
0x180012100  pop     rdi
0x180012101  jmp     ?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z; std::_Associated_state<int>::_Get_value(bool)
0x180012106  call    ?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ; Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
```
