# __scrt_throw_std_bad_alloc(void)

- ea: `0x180001eb4`
- end: `0x180001ed4`
- name: `?__scrt_throw_std_bad_alloc@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180001cf8`

## callees

- `0x180001d80`
- `0x180001f68`

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
0x180001eb4  sub     rsp, 48h
0x180001eb8  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001ebd  call    ??0bad_alloc@std@@QEAA@XZ
0x180001ec2  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001ec9  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001ece  call    _CxxThrowException_0
```
