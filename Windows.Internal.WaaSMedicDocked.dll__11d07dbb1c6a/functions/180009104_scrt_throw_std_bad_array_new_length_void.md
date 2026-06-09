# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180009104`
- end: `0x180009124`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000197c`
- `0x180005db8`
- `0x18000a65c`

## callees

- `0x180001fea`
- `0x180005f94`

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
0x180009104  sub     rsp, 48h
0x180009108  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000910d  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180009112  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180009119  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000911e  call    _CxxThrowException_0
```
