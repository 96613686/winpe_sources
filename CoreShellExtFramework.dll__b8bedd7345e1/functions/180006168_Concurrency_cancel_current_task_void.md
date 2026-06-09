# Concurrency::cancel_current_task(void)

- ea: `0x180006168`
- end: `0x180006188`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800060d4`

## callees

- `0x180004d6c`
- `0x18000619a`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180004D6C(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x180006168  sub     rsp, 48h
0x18000616c  lea     rcx, [rsp+48h+pExceptionObject]
0x180006171  call    sub_180004D6C
0x180006176  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000617d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180006182  call    _CxxThrowException
```
