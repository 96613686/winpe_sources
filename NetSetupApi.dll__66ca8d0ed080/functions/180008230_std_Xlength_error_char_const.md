# std::_Xlength_error(char const *)

- ea: `0x180008230`
- end: `0x180008253`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180007528`
- `0x1800076b8`
- `0x18000b3f8`
- `0x18000eacc`
- `0x18000ec00`
- `0x180010f18`

## callees

- `0x180008184`
- `0x18000895c`

## pseudocode

```c
void __fastcall __noreturn std::_Xlength_error(const char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180008230  sub     rsp, 48h
0x180008234  mov     rdx, rcx; char *
0x180008237  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000823c  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180008241  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180008248  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000824d  call    _CxxThrowException_0
```
