# __scrt_throw_std_bad_alloc(void)

- ea: `0x180001e54`
- end: `0x180001e74`
- name: `?__scrt_throw_std_bad_alloc@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800019cc`

## callees

- `0x180001d20`
- `0x180001ff0`

## pseudocode

```c
void __noreturn __scrt_throw_std_bad_alloc(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180001e54  sub     rsp, 48h
0x180001e58  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001e5d  call    ??0bad_alloc@std@@QEAA@XZ
0x180001e62  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001e69  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001e6e  call    _CxxThrowException_0
```
