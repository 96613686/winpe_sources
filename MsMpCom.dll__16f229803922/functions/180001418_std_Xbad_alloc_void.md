# std::_Xbad_alloc(void)

- ea: `0x180001418`
- end: `0x180001438`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000126c`
- `0x180008238`
- `0x180009b34`

## callees

- `0x1800012cc`
- `0x180001ccc`

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
0x180001418  sub     rsp, 48h
0x18000141c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001421  call    ??0bad_alloc@std@@QEAA@XZ
0x180001426  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000142d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001432  call    _CxxThrowException_0
```
