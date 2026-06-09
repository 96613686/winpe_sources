# __scrt_throw_std_bad_alloc(void)

- ea: `0x140001d84`
- end: `0x140001da4`
- name: `?__scrt_throw_std_bad_alloc@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000192c`

## callees

- `0x140001c54`
- `0x140001fbc`

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
0x140001d84  sub     rsp, 48h
0x140001d88  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001d8d  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001d92  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140001d99  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001d9e  call    _CxxThrowException_0
```
