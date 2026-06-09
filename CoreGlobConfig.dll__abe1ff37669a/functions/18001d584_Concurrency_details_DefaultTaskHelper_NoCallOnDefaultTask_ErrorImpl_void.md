# Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)

- ea: `0x18001d584`
- end: `0x18001d5b7`
- name: `?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ`
- size: `51`
- prototype: `void __noreturn(void)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000ee28`
- `0x18001279c`

## callees

- `0x180003318`
- `0x180010784`

## string_xrefs

- `0x18001d588`: `This function cannot be called on a default constructed task`

## pseudocode

```c
void __noreturn Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)
{
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  std::exception::exception(
    (std::exception *)pExceptionObject,
    "This function cannot be called on a default constructed task");
  pExceptionObject[0] = &Concurrency::invalid_operation::`vftable';
  throw (Concurrency::invalid_operation *)pExceptionObject;
}

```

## disassembly

```asm
0x18001d584  sub     rsp, 48h
0x18001d588  lea     rdx, aThisFunctionCa; "This function cannot be called on a def"...
0x18001d58f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001d594  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x18001d599  lea     rax, ??_7invalid_operation@Concurrency@@6B@; const Concurrency::invalid_operation::`vftable'
0x18001d5a0  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x18001d5a7  mov     [rsp+48h+pExceptionObject], rax
0x18001d5ac  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001d5b1  call    _CxxThrowException_0
```
