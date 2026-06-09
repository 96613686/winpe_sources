# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180011d50`
- end: `0x180011d70`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18000214c`
- `0x18000e4b4`
- `0x18000e5a4`
- `0x18000e7a8`
- `0x18000ed18`

## callees

- `0x180002a34`
- `0x18000f0b8`

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
0x180011d50  sub     rsp, 48h
0x180011d54  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011d59  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180011d5e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180011d65  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011d6a  call    _CxxThrowException_0
```
