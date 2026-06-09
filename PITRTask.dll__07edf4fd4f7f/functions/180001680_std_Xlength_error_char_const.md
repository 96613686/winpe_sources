# std::_Xlength_error(char const *)

- ea: `0x180001680`
- end: `0x1800016a3`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ba60`
- `0x18000ba78`
- `0x18000cf1c`

## callees

- `0x180001584`
- `0x180001dcc`

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
0x180001680  sub     rsp, 48h
0x180001684  mov     rdx, rcx; char *
0x180001687  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000168c  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180001691  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180001698  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000169d  call    _CxxThrowException_0
```
