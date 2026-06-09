# std::_Xbad_alloc(void)

- ea: `0x140001368`
- end: `0x140001388`
- name: `?_Xbad_alloc@std@@YAXXZ`
- size: `32`
- prototype: `void __noreturn(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140001208`
- `0x140004410`

## callees

- `0x14000108c`
- `0x140001e9c`

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
0x140001368  sub     rsp, 48h
0x14000136c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x140001371  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x140001376  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x14000137d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140001382  call    _CxxThrowException_0
```
