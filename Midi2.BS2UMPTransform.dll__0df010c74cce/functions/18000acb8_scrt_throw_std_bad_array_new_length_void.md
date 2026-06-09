# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000acb8`
- end: `0x18000acd8`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001eb0`
- `0x18000a328`
- `0x18000a4b8`
- `0x18000a5c0`

## callees

- `0x1800028d4`
- `0x18000a788`

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
0x18000acb8  sub     rsp, 48h
0x18000acbc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000acc1  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000acc6  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000accd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000acd2  call    _CxxThrowException_0
```
