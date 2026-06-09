# std::_Xbad_alloc(void)

- ea: `0x140001e78`
- end: `0x140001e98`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001b44`
- `0x140001d18`
- `0x140005836`

## callees

- `0x140001ba4`
- `0x1400024fc`

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
0x140001e78  sub     rsp, 48h
0x140001e7c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001e81  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001e86  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140001e8d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001e92  call    _CxxThrowException_0
```
