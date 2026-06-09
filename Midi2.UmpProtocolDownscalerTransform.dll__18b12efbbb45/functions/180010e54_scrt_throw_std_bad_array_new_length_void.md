# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180010e54`
- end: `0x180010e74`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ec0`
- `0x18000b238`
- `0x18000b344`
- `0x18000b4d4`
- `0x18000b5dc`
- `0x18000b770`
- `0x18000c450`
- `0x18000c62c`

## callees

- `0x180003a50`
- `0x18000c7f8`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_array_new_length(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_array_new_length::bad_array_new_length((std::bad_array_new_length *)pExceptionObject);
  throw (std::bad_array_new_length *)pExceptionObject;
}

```

## disassembly

```asm
0x180010e54  sub     rsp, 48h
0x180010e58  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180010e5d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180010e62  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180010e69  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010e6e  call    _CxxThrowException_0
```
