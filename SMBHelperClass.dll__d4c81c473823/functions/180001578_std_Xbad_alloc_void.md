# std::_Xbad_alloc(void)

- ea: `0x180001578`
- end: `0x180001598`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x18000123c`
- `0x180001418`
- `0x18000a394`
- `0x18000aa18`
- `0x18000cc24`
- `0x18000d66c`
- `0x18000d6ac`
- `0x18000f494`
- `0x18000f4d4`
- `0x18000fd43`

## callees

- `0x18000129c`
- `0x18000257c`

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
0x180001578  sub     rsp, 48h
0x18000157c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180001581  call    ??0bad_alloc@std@@QEAA@XZ
0x180001586  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000158d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180001592  call    _CxxThrowException_0
```
