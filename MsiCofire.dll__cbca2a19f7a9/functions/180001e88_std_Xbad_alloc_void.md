# std::_Xbad_alloc(void)

- ea: `0x180001e88`
- end: `0x180001ea8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180001b48`
- `0x180001d28`
- `0x180006d14`
- `0x1800073c7`

## callees

- `0x180001ba8`
- `0x18000255c`

## pseudocode

```c
void __noreturn std::_Xbad_alloc(void)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
  throw (std::bad_alloc *)pExceptionObject;
}

```

## disassembly

```asm
0x180001e88  sub     rsp, 48h
0x180001e8c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001e91  call    ??0bad_alloc@std@@QEAA@XZ
0x180001e96  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001e9d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001ea2  call    _CxxThrowException_0
```
