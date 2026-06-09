# std::_Xbad_alloc(void)

- ea: `0x1800021c8`
- end: `0x1800021e8`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `28`
- callee_count: `2`
- tags: ``

## callers

- `0x180001fc4`
- `0x180006e08`
- `0x18000cba4`
- `0x18000cbe4`
- `0x18000cc24`
- `0x18000cc78`
- `0x18000ccc4`
- `0x18000cfbc`
- `0x18000d208`
- `0x18000ffd0`
- `0x180010024`
- `0x18001134c`
- `0x18001398c`
- `0x1800140d4`
- `0x180014a00`
- `0x18001e088`
- `0x18001e914`
- `0x180020110`
- `0x180021db0`
- `0x180021e00`
- `0x180021e50`
- `0x180021ea0`
- `0x1800225bc`
- `0x180022ac4`
- `0x18002a8a0`
- `0x18002ab2c`
- `0x18002c3e7`
- `0x18002c9c4`

## callees

- `0x180002024`
- `0x18000294c`

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
0x1800021c8  sub     rsp, 48h
0x1800021cc  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800021d1  call    ??0bad_alloc@std@@QEAA@XZ
0x1800021d6  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800021dd  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800021e2  call    _CxxThrowException_0
```
