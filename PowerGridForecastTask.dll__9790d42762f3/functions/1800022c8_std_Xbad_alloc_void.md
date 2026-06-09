# std::_Xbad_alloc(void)

- ea: `0x1800022c8`
- end: `0x1800022e8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800020c4`
- `0x180005efc`
- `0x180005fe8`
- `0x18000bbe0`
- `0x18002fdc4`
- `0x180033d00`
- `0x180033f1c`
- `0x180035423`
- `0x180035f8b`
- `0x180036286`

## callees

- `0x180002184`
- `0x180026778`

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
0x1800022c8  sub     rsp, 48h
0x1800022cc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800022d1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800022d6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800022dd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800022e2  call    _CxxThrowException_0
```
