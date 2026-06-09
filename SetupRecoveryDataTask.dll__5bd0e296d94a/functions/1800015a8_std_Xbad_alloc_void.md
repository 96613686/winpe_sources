# std::_Xbad_alloc(void)

- ea: `0x1800015a8`
- end: `0x1800015c8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180001404`
- `0x18000aa14`
- `0x18000cb73`

## callees

- `0x180001464`
- `0x180001cec`

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
0x1800015a8  sub     rsp, 48h
0x1800015ac  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800015b1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800015b6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800015bd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800015c2  call    _CxxThrowException_0
```
