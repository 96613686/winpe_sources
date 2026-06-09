# Concurrency::cancel_current_task(void)

- ea: `0x18001aa50`
- end: `0x18001aa70`
- name: `?cancel_current_task@Concurrency@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001a760`
- `0x18001aa70`
- `0x180060f80`
- `0x180078abc`

## callees

- `0x18001a950`
- `0x18007c4ee`

## pseudocode

```c
void __noreturn Concurrency::cancel_current_task(void)
{
  _QWORD pExceptionObject[5]; // [rsp+20h] [rbp-28h] BYREF

  sub_18001A950(pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x18001aa50  sub     rsp, 48h
0x18001aa54  lea     rcx, [rsp+48h+pExceptionObject]
0x18001aa59  call    sub_18001A950
0x18001aa5e  lea     rdx, __TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18001aa65  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001aa6a  call    _CxxThrowException
```
