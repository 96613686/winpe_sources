# Concurrency::cancel_current_task(void)

- ea: `0x180011478`
- end: `0x180011498`
- name: `?cancel_current_task@Concurrency@@YAXXZ_0`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010ea8`

## callees

- `0x180011434`
- `0x18002c810`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  sub_180011434(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x180011478  sub     rsp, 48h
0x18001147c  lea     rcx, [rsp+48h+pExceptionObject]
0x180011481  call    sub_180011434
0x180011486  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18001148d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011492  call    _CxxThrowException
```
