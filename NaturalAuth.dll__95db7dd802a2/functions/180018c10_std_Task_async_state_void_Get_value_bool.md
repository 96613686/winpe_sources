# std::_Task_async_state<void>::_Get_value(bool)

- ea: `0x180018c10`
- end: `0x180018c75`
- name: `?_Get_value@?$_Task_async_state@X@std@@UEAAAEAH_N@Z`
- size: `101`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180005170`
- `0x1800121d8`
- `0x180018b20`
- `0x180018c10`
- `0x18001acd0`

## string_xrefs

- `0x180018c2c`: `This function cannot be called on a default constructed task`

## pseudocode

```c
__int64 __fastcall std::_Task_async_state<void>::_Get_value(__int64 a1, char a2)
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
  Concurrency::details::_Task_impl_base::_Wait();
  return std::_Associated_state<int>::_Get_value(a1, a2);
}

```

## disassembly

```asm
0x180018c10  mov     [rsp+arg_0], rbx
0x180018c15  push    rdi
0x180018c16  sub     rsp, 40h
0x180018c1a  mov     rbx, rcx
0x180018c1d  mov     dil, dl
0x180018c20  mov     rcx, [rcx+110h]
0x180018c27  test    rcx, rcx
0x180018c2a  jnz     short loc_180018C5B
0x180018c2c  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x180018c33  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180018c38  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180018c3d  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x180018c44  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x180018c4b  mov     [rsp+48h+pExceptionObject], rax
0x180018c50  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180018c55  call    _CxxThrowException_0
0x180018c5b  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x180018c60  mov     dl, dil
0x180018c63  mov     rcx, rbx
0x180018c66  mov     rbx, [rsp+48h+arg_0]
0x180018c6b  add     rsp, 40h
0x180018c6f  pop     rdi
0x180018c70  jmp     ?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z; std::_Associated_state<int>::_Get_value(bool)
```
