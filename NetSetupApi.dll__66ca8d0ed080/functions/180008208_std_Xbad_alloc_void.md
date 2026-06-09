# std::_Xbad_alloc(void)

- ea: `0x180008208`
- end: `0x180008228`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800069e0`
- `0x1800092b0`
- `0x18000eb78`
- `0x180010f18`
- `0x18001291c`

## callees

- `0x180008030`
- `0x18000895c`

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
0x180008208  sub     rsp, 48h
0x18000820c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008211  call    ??0bad_alloc@std@@QEAA@XZ
0x180008216  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000821d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008222  call    _CxxThrowException_0
```
