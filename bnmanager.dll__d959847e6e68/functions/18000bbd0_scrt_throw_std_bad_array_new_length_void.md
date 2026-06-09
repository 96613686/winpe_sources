# __scrt_throw_std_bad_array_new_length(void)

- ea: `0x18000bbd0`
- end: `0x18000bbf0`
- name: `?__scrt_throw_std_bad_array_new_length@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180001bc8`
- `0x1800025d0`
- `0x1800030a0`
- `0x18000322c`
- `0x180003be4`

## callees

- `0x1800022b4`
- `0x180004978`

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
0x18000bbd0  sub     rsp, 48h
0x18000bbd4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000bbd9  call    ??0bad_array_new_length@std@@QEAA@XZ
0x18000bbde  lea     rdx, _TI3?AVbad_array_new_length@std@@; pThrowInfo
0x18000bbe5  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000bbea  call    _CxxThrowException_0
```
