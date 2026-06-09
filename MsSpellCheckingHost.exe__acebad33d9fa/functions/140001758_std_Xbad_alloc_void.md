# std::_Xbad_alloc(void)

- ea: `0x140001758`
- end: `0x140001778`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400014fc`
- `0x140006314`
- `0x14000e94c`
- `0x14000e98c`
- `0x14000e9e0`
- `0x14000ea28`
- `0x1400119d0`
- `0x140011a20`
- `0x1400120e3`
- `0x14001235b`

## callees

- `0x1400015bc`
- `0x1400020ac`

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
0x140001758  sub     rsp, 48h
0x14000175c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001761  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001766  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000176d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001772  call    _CxxThrowException_0
```
