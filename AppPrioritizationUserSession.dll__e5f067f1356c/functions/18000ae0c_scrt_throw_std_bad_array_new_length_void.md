# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000ae0c`
- end: `0x18000ae2c`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180002b5c`
- `0x1800080c0`
- `0x1800081d0`
- `0x180008458`

## callees

- `0x1800032e0`
- `0x1800087dc`

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
0x18000ae0c  sub     rsp, 48h
0x18000ae10  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000ae15  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000ae1a  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000ae21  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000ae26  call    _CxxThrowException_0
```
