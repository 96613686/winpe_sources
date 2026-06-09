# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000e89c`
- end: `0x18000e8bc`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002324`
- `0x1800032ac`
- `0x180004428`
- `0x1800045b4`

## callees

- `0x180002e04`
- `0x180005154`

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
0x18000e89c  sub     rsp, 48h
0x18000e8a0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000e8a5  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000e8aa  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000e8b1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000e8b6  call    _CxxThrowException_0
```
