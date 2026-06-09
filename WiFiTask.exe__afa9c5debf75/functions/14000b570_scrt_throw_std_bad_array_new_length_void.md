# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x14000b570`
- end: `0x14000b590`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1400016d0`
- `0x140002d70`
- `0x140002f18`
- `0x14000dfc4`
- `0x14000e694`
- `0x14000e908`

## callees

- `0x140002174`
- `0x140003314`

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
0x14000b570  sub     rsp, 48h
0x14000b574  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000b579  call    ??0bad_array_new_length@std@@QEAA@XZ; std::bad_array_new_length::bad_array_new_length(void)
0x14000b57e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x14000b585  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000b58a  call    _CxxThrowException_0
```
