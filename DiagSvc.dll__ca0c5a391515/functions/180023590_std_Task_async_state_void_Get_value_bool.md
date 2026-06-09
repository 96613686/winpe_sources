# std::_Task_async_state<void>::_Get_value(bool)

- ea: `0x180023590`
- end: `0x1800235f5`
- name: `?_Get_value@?$_Task_async_state@X@std@@UEAAAEAH_N@Z`
- size: `101`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18001dce0`
- `0x1800234a0`
- `0x180023590`
- `0x1800244b0`
- `0x180026140`

## string_xrefs

- `0x1800235ac`: `This function cannot be called on a default constructed task`

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
    pExceptionObject[0] = &std::bad_alloc::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  Concurrency::details::_Task_impl_base::_Wait();
  return std::_Associated_state<int>::_Get_value(a1, a2);
}

```

## disassembly

```asm
0x180023590  mov     [rsp+arg_0], rbx
0x180023595  push    rdi
0x180023596  sub     rsp, 40h
0x18002359a  mov     rbx, rcx
0x18002359d  mov     dil, dl
0x1800235a0  mov     rcx, [rcx+110h]
0x1800235a7  test    rcx, rcx
0x1800235aa  jnz     short loc_1800235DB
0x1800235ac  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x1800235b3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800235b8  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x1800235bd  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800235c4  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x1800235cb  mov     [rsp+48h+pExceptionObject], rax
0x1800235d0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800235d5  call    _CxxThrowException_0
0x1800235db  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x1800235e0  mov     dl, dil
0x1800235e3  mov     rcx, rbx
0x1800235e6  mov     rbx, [rsp+48h+arg_0]
0x1800235eb  add     rsp, 40h
0x1800235ef  pop     rdi
0x1800235f0  jmp     ?_Get_value@?$_Associated_state@H@std@@UEAAAEAH_N@Z; std::_Associated_state<int>::_Get_value(bool)
```
