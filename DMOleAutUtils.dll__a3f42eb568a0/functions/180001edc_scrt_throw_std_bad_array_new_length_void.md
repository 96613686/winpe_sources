# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180001edc`
- end: `0x180001efc`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cf8`

## callees

- `0x180001dec`
- `0x180001f68`

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
0x180001edc  sub     rsp, 48h
0x180001ee0  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001ee5  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180001eea  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180001ef1  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001ef6  call    _CxxThrowException_0
```
