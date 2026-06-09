# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x140002e80`
- end: `0x140002ea0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x14000164c`
- `0x140002390`
- `0x140003f18`

## callees

- `0x1400022f8`
- `0x1400026bc`

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
0x140002e80  sub     rsp, 48h
0x140002e84  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140002e89  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x140002e8e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x140002e95  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140002e9a  call    _CxxThrowException_0
```
