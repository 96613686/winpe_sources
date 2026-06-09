# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x140005fd4`
- end: `0x140005ff4`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000174c`
- `0x14000593c`

## callees

- `0x140001f42`
- `0x140005b78`

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
0x140005fd4  sub     rsp, 48h
0x140005fd8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140005fdd  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x140005fe2  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x140005fe9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140005fee  call    _CxxThrowException_0
```
