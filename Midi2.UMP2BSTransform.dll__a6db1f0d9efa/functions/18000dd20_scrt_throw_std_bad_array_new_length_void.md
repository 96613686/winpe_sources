# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000dd20`
- end: `0x18000dd40`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001f40`
- `0x18000a4f0`
- `0x18000a65c`
- `0x18000e1ec`

## callees

- `0x180002964`
- `0x18000a824`

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
0x18000dd20  sub     rsp, 48h
0x18000dd24  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000dd29  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000dd2e  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000dd35  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000dd3a  call    _CxxThrowException_0
```
