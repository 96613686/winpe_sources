# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000d918`
- end: `0x14000d938`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x14000892c`
- `0x14000d698`
- `0x14000eb3c`
- `0x14000f43c`
- `0x140011740`
- `0x140012c4c`

## callees

- `0x1400090f8`
- `0x14000d844`

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
0x14000d918  sub     rsp, 48h
0x14000d91c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000d921  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000d926  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000d92d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000d932  call    _CxxThrowException_0
```
