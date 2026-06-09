# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000d9c8`
- end: `0x14000d9e8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b9c`
- `0x14000cc78`
- `0x14000ce04`
- `0x14000cf98`
- `0x14000de3c`

## callees

- `0x140002050`
- `0x14000d580`

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
0x14000d9c8  sub     rsp, 48h
0x14000d9cc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000d9d1  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000d9d6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000d9dd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000d9e2  call    _CxxThrowException_0
```
