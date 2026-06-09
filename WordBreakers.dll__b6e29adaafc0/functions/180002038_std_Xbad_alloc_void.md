# std::_Xbad_alloc(void)

- ea: `0x180002038`
- end: `0x180002058`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180001e88`
- `0x18000656c`
- `0x1800065a4`
- `0x180006754`
- `0x1800069ac`
- `0x18000bb6a`

## callees

- `0x180001ee8`
- `0x18000278c`

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
0x180002038  sub     rsp, 48h
0x18000203c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002041  call    ??0bad_alloc@std@@QEAA@XZ
0x180002046  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000204d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002052  call    _CxxThrowException_0
```
