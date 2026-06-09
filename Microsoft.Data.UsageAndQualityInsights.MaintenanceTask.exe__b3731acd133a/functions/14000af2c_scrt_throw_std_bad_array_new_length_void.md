# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000af2c`
- end: `0x14000af4c`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400019c8`
- `0x1400094c0`
- `0x1400095cc`
- `0x140009760`

## callees

- `0x14000224c`
- `0x140009e3c`

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
0x14000af2c  sub     rsp, 48h
0x14000af30  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000af35  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000af3a  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000af41  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000af46  call    _CxxThrowException_0
```
