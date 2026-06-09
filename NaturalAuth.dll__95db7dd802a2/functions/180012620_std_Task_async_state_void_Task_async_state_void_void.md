# std::_Task_async_state<void>::~_Task_async_state<void>(void)

- ea: `0x180012620`
- end: `0x180012694`
- name: `??1?$_Task_async_state@X@std@@UEAA@XZ`
- size: `116`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180013880`

## callees

- `0x180005170`
- `0x1800121d8`
- `0x180012598`
- `0x180012620`
- `0x180012ab4`
- `0x18001acd0`

## string_xrefs

- `0x180012646`: `This function cannot be called on a default constructed task`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
    pExceptionObject[0] = &std::logic_error::`vftable';
    throw (Concurrency::invalid_operation *)pExceptionObject;
  }
  Concurrency::details::_Task_impl_base::_Wait();
  std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(v2);
  return std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(a1);
}

```

## disassembly

```asm
0x180012620  mov     [rsp+arg_0], rbx
0x180012625  push    rdi
0x180012626  sub     rsp, 40h
0x18001262a  mov     rbx, rcx
0x18001262d  lea     rax, ??_7?$_Task_async_state@X@std@@6B@; const std::_Task_async_state<void>::`vftable'
0x180012634  mov     [rcx], rax
0x180012637  lea     rdi, [rcx+110h]
0x18001263e  mov     rcx, [rdi]
0x180012641  test    rcx, rcx
0x180012644  jnz     short loc_180012675
0x180012646  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x18001264d  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180012652  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180012657  lea     rax, ??_7logic_error@std@@6B@; const std::logic_error::`vftable'
0x18001265e  mov     [rsp+48h+pExceptionObject], rax
0x180012663  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18001266a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001266f  call    _CxxThrowException_0
0x180012675  call    ?_Wait@_Task_impl_base@details@Concurrency@@QEAA?AW4task_group_status@3@XZ; Concurrency::details::_Task_impl_base::_Wait(void)
0x18001267a  mov     rcx, rdi
0x18001267d  call    ??1?$shared_ptr@U_ExceptionHolder@details@Concurrency@@@std@@QEAA@XZ; std::shared_ptr<Concurrency::details::_ExceptionHolder>::~shared_ptr<Concurrency::details::_ExceptionHolder>(void)
0x180012682  mov     rcx, rbx
0x180012685  mov     rbx, [rsp+48h+arg_0]
0x18001268a  add     rsp, 40h
0x18001268e  pop     rdi
0x18001268f  jmp     ??1?$_Packaged_state@$$A6AXXZ@std@@UEAA@XZ; std::_Packaged_state<void (void)>::~_Packaged_state<void (void)>(void)
```
