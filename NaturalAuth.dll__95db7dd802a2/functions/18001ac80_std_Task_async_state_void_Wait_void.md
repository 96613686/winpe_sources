# std::_Task_async_state<void>::_Wait(void)

- ea: `0x18001ac80`
- end: `0x18001acc8`
- name: `?_Wait@?$_Task_async_state@X@std@@UEAAXXZ`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180005170`
- `0x1800121d8`
- `0x18001ac80`
- `0x18001acd0`

## string_xrefs

- `0x18001ac90`: `This function cannot be called on a default constructed task`

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
    pExceptionObject[0] = &std::logic_error::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  return Concurrency::details::_Task_impl_base::_Wait();
}

```

## disassembly

```asm
0x18001ac80  sub     rsp, 48h
0x18001ac84  mov     rcx, [rcx+110h]
0x18001ac8b  test    rcx, rcx
0x18001ac8e  jnz     short loc_18001ACBF
0x18001ac90  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x18001ac97  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001ac9c  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18001aca1  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18001aca8  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18001acaf  mov     [rsp+48h+pExceptionObject], rax
0x18001acb4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001acb9  call    _CxxThrowException_0
0x18001acbf  add     rsp, 48h
0x18001acc3  jmp     ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
```
