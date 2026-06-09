# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x1800078d8`
- end: `0x1800078f8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c24`
- `0x180007398`
- `0x1800074d8`
- `0x180010634`
- `0x180011028`

## callees

- `0x180002654`
- `0x18000768c`

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
0x1800078d8  sub     rsp, 48h
0x1800078dc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800078e1  call    ??0bad_array_new_length@std@@QEAA@XZ
0x1800078e6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x1800078ed  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800078f2  call    _CxxThrowException_0
```
