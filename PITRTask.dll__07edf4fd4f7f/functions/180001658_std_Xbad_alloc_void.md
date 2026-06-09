# std::_Xbad_alloc(void)

- ea: `0x180001658`
- end: `0x180001678`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x1800014b4`
- `0x18000b634`
- `0x18000b72c`
- `0x18000b89c`
- `0x18000ea00`
- `0x18000ea40`
- `0x18000eb08`
- `0x180010d09`
- `0x180010d81`

## callees

- `0x180001514`
- `0x180001dcc`

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
0x180001658  sub     rsp, 48h
0x18000165c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001661  call    ??0bad_alloc@std@@QEAA@XZ
0x180001666  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000166d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001672  call    _CxxThrowException_0
```
