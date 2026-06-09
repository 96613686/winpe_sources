# std::_Xbad_alloc(void)

- ea: `0x180001fa8`
- end: `0x180001fc8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x180001da8`
- `0x180006fec`
- `0x18000919c`
- `0x180009250`
- `0x18000a518`
- `0x18000a558`
- `0x18000a5b0`
- `0x18000a610`
- `0x18000a660`
- `0x18000a6a8`
- `0x18000ab4c`
- `0x18000cc97`
- `0x18000cfff`

## callees

- `0x180001e08`
- `0x18000274c`

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
0x180001fa8  sub     rsp, 48h
0x180001fac  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001fb1  call    ??0bad_alloc@std@@QEAA@XZ
0x180001fb6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001fbd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001fc2  call    _CxxThrowException_0
```
