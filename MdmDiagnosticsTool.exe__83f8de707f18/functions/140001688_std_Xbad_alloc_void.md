# std::_Xbad_alloc(void)

- ea: `0x140001688`
- end: `0x1400016a8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014e4`
- `0x140002dd0`
- `0x14000727c`
- `0x14000a2cc`

## callees

- `0x140001544`
- `0x140001dec`

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
0x140001688  sub     rsp, 48h
0x14000168c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001691  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001696  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000169d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400016a2  call    _CxxThrowException_0
```
