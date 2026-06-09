# std::_Xout_of_range(char const *)

- ea: `0x18000825c`
- end: `0x18000827f`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180007478`
- `0x180007528`
- `0x1800076b8`
- `0x180007f54`
- `0x18000b56c`
- `0x18000b870`
- `0x18000b914`
- `0x18000ed14`

## callees

- `0x180008184`
- `0x18000895c`

## pseudocode

```c
void __fastcall __noreturn std::_Xout_of_range(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::out_of_range *)pExceptionObject;
}

```

## disassembly

```asm
0x18000825c  sub     rsp, 48h
0x180008260  mov     rdx, rcx; char *
0x180008263  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008268  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x18000826d  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x180008274  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008279  call    _CxxThrowException_0
```
