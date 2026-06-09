# Concurrency::cancel_current_task(void)

- ea: `0x180006140`
- end: `0x180006160`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800060d4`

## callees

- `0x180006118`
- `0x18000619a`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180006118(pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180006140  sub     rsp, 48h
0x180006144  lea     rcx, [rsp+48h+pExceptionObject]
0x180006149  call    sub_180006118
0x18000614e  lea     rdx, __TI2?AVbad_alloc@std@@; pThrowInfo
0x180006155  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000615a  call    _CxxThrowException
```
