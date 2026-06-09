# Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(void)

- ea: `0x18001242c`
- end: `0x18001244c`
- name: `?_NoCallOnDefaultTask_ErrorImpl@_DefaultTaskHelper@details@Concurrency@@SAXXZ`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000fae8`
- `0x1800120d0`
- `0x180012c10`

## callees

- `0x180002de8`
- `0x18000f814`

## pseudocode

```c
void __fastcall __noreturn Concurrency::details::_DefaultTaskHelper::_NoCallOnDefaultTask_ErrorImpl(
        __int64 a1,
        const char *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  Concurrency::invalid_operation::invalid_operation((Concurrency::invalid_operation *)pExceptionObject, a2);
  throw (Concurrency::invalid_operation *)pExceptionObject;
}

```

## disassembly

```asm
0x18001242c  sub     rsp, 48h
0x180012430  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180012435  call    ??0invalid_operation@Concurrency@@QEAA@PEBD@Z
0x18001243a  lea     rdx, _TI2?AVinvalid_operation@Concurrency@@; pThrowInfo
0x180012441  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180012446  call    _CxxThrowException_0
```
