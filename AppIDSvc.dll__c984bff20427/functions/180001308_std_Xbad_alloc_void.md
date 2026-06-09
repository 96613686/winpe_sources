# std::_Xbad_alloc(void)

- ea: `0x180001308`
- end: `0x180001328`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800011c8`
- `0x180005b7c`
- `0x1800078c8`
- `0x1800079c8`
- `0x180007ae4`
- `0x18000c88f`
- `0x18000c90c`

## callees

- `0x180001ba8`
- `0x180006018`

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
0x180001308  sub     rsp, 48h
0x18000130c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001311  call    ??0bad_alloc@std@@QEAA@XZ
0x180001316  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000131d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001322  call    _CxxThrowException_0
```
