# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x180009c28`
- end: `0x180009c48`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800045c8`
- `0x18000698c`
- `0x180006a90`
- `0x180006e68`

## callees

- `0x1800046bf`
- `0x1800071dc`

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
0x180009c28  sub     rsp, 48h
0x180009c2c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009c31  call    ??0bad_array_new_length@std@@QEAA@XZ
0x180009c36  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x180009c3d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009c42  call    _CxxThrowException_0
```
