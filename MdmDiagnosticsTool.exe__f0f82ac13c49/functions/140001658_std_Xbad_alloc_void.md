# std::_Xbad_alloc(void)

- ea: `0x140001658`
- end: `0x140001678`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014b4`
- `0x140002d4c`
- `0x140006e80`
- `0x140009c97`

## callees

- `0x140001514`
- `0x140001dbc`

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
0x140001658  sub     rsp, 48h
0x14000165c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001661  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001666  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000166d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001672  call    _CxxThrowException_0
```
