# Concurrency::cancel_current_task(void)

- ea: `0x180011458`
- end: `0x180011478`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010ea8`

## callees

- `0x180011410`
- `0x18002c810`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180011410(pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180011458  sub     rsp, 48h
0x18001145c  lea     rcx, [rsp+48h+pExceptionObject]
0x180011461  call    sub_180011410
0x180011466  lea     rdx, __TI2?AVbad_alloc@std@@; pThrowInfo
0x18001146d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011472  call    _CxxThrowException
```
