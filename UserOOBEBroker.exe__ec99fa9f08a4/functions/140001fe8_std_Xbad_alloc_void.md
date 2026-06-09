# std::_Xbad_alloc(void)

- ea: `0x140001fe8`
- end: `0x140002008`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001e40`
- `0x14000613c`
- `0x14000e6c7`

## callees

- `0x140001ea0`
- `0x14000263c`

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
0x140001fe8  sub     rsp, 48h
0x140001fec  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001ff1  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001ff6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x140001ffd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140002002  call    _CxxThrowException_0
```
