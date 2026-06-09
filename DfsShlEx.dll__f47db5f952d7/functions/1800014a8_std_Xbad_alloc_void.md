# std::_Xbad_alloc(void)

- ea: `0x1800014a8`
- end: `0x1800014c8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001164`
- `0x180001348`
- `0x18000aae3`

## callees

- `0x1800011d0`
- `0x1800024ec`

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
0x1800014a8  sub     rsp, 48h
0x1800014ac  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800014b1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800014b6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800014bd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800014c2  call    _CxxThrowException_0
```
