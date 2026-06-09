# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180007d74`
- end: `0x180007d94`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001650`
- `0x18000852c`
- `0x18000a9e0`

## callees

- `0x1800020dc`
- `0x180003bdc`

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
0x180007d74  sub     rsp, 48h
0x180007d78  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180007d7d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180007d82  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180007d89  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180007d8e  call    _CxxThrowException_0
```
