# std::_Xbad_alloc(void)

- ea: `0x180001a68`
- end: `0x180001a88`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001730`
- `0x180001908`
- `0x18000ab00`

## callees

- `0x180001790`
- `0x1800026ec`

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
0x180001a68  sub     rsp, 48h
0x180001a6c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001a71  call    ??0bad_alloc@std@@QEAA@XZ
0x180001a76  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x180001a7d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001a82  call    _CxxThrowException_0
```
