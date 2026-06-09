# std::_Task_async_state<void>::_Wait(void)

- ea: `0x180024460`
- end: `0x1800244a8`
- name: `?_Wait@?$_Task_async_state@X@std@@UEAAXXZ`
- size: `72`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001dce0`
- `0x180024460`
- `0x1800244b0`
- `0x180026140`

## string_xrefs

- `0x180024470`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::_Wait(__int64 a1)
{
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( !*(_QWORD *)(a1 + 272) )
  {
    std::exception::exception(
      (std::exception *)pExceptionObject,
      "This function cannot be called on a default constructed task");
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  return Concurrency::details::_Task_impl_base::_Wait();
}

```

## disassembly

```asm
0x180024460  sub     rsp, 48h
0x180024464  mov     rcx, [rcx+110h]
0x18002446b  test    rcx, rcx
0x18002446e  jnz     short loc_18002449F
0x180024470  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x180024477  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18002447c  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180024481  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x180024488  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18002448f  mov     [rsp+48h+pExceptionObject], rax
0x180024494  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180024499  call    _CxxThrowException_0
0x18002449f  add     rsp, 48h
0x1800244a3  jmp     ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
```
