# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000c968`
- end: `0x18000c988`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000200c`
- `0x18000acc0`
- `0x18000c33c`
- `0x18000ca20`
- `0x18000cb50`
- `0x18000cc68`

## callees

- `0x1800021a0`
- `0x18000c4b8`

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
0x18000c968  sub     rsp, 48h
0x18000c96c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000c971  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000c976  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000c97d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000c982  call    _CxxThrowException_0
```
