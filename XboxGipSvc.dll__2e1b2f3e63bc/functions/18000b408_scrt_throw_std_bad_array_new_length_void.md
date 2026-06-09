# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000b408`
- end: `0x18000b428`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x1800021fc`
- `0x180009508`
- `0x180009820`
- `0x180009a08`
- `0x18000e2c4`
- `0x18000e414`
- `0x18000e7f0`
- `0x180010d1c`

## callees

- `0x18000231a`
- `0x180009bd0`

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
0x18000b408  sub     rsp, 48h
0x18000b40c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000b411  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000b416  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000b41d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000b422  call    _CxxThrowException_0
```
