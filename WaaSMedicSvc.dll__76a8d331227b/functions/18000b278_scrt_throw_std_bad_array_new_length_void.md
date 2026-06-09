# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000b278`
- end: `0x18000b298`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000260c`
- `0x1800077d8`
- `0x180007850`
- `0x180007c4c`
- `0x180007fc0`
- `0x180008134`
- `0x1800083ac`
- `0x180008514`

## callees

- `0x180002f94`
- `0x180008a68`

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
0x18000b278  sub     rsp, 48h
0x18000b27c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000b281  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000b286  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000b28d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b292  call    _CxxThrowException_0
```
