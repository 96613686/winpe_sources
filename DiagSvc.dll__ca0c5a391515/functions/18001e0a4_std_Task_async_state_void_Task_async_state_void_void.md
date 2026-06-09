# std::_Task_async_state<void>::~_Task_async_state<void>(void)

- ea: `0x18001e0a4`
- end: `0x18001e118`
- name: `??1?$_Task_async_state@X@std@@UEAA@XZ`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x18001ea80`

## callees

- `0x18001dce0`
- `0x18001dff0`
- `0x18001e0a4`
- `0x18001e210`
- `0x1800244b0`
- `0x180026140`

## string_xrefs

- `0x18001e0ca`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::~_Task_async_state<void>(_QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  *a1 = &std::_Task_async_state<void>::`vftable';
  v2 = a1 + 34;
  if ( !a1[34] )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "This function cannot be called on a default constructed task");
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  Concurrency::details::_Task_impl_base::_Wait();
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(v2);
  return std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(a1);
}

```

## disassembly

```asm
0x18001e0a4  mov     [rsp+arg_0], rbx
0x18001e0a9  push    rdi
0x18001e0aa  sub     rsp, 40h
0x18001e0ae  mov     rbx, rcx
0x18001e0b1  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x18001e0b8  mov     [rcx], rax
0x18001e0bb  lea     rdi, [rcx+110h]
0x18001e0c2  mov     rcx, [rdi]
0x18001e0c5  test    rcx, rcx
0x18001e0c8  jnz     short loc_18001E0F9
0x18001e0ca  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x18001e0d1  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001e0d6  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18001e0db  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x18001e0e2  mov     [rsp+48h+pExceptionObject], rax
0x18001e0e7  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18001e0ee  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001e0f3  call    _CxxThrowException_0
0x18001e0f9  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x18001e0fe  mov     rcx, rdi
0x18001e101  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x18001e106  mov     rcx, rbx
0x18001e109  mov     rbx, [rsp+48h+arg_0]
0x18001e10e  add     rsp, 40h
0x18001e112  pop     rdi
0x18001e113  jmp     ??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ; std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)
```
