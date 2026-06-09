# std::_Xlength_error(char const *)

- ea: `0x1800015c8`
- end: `0x1800015eb`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(char *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800015b0`
- `0x18000a394`

## callees

- `0x180001320`
- `0x18000255c`

## pseudocode

```c
void __fastcall __noreturn std::_Xlength_error(char *a1)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  std::length_error::length_error((std::length_error *)pExceptionObject, a1);
  throw (std::length_error *)pExceptionObject;
}

```

## disassembly

```asm
0x1800015c8  sub     rsp, 48h
0x1800015cc  mov     rdx, rcx; char *
0x1800015cf  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800015d4  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800015d9  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800015e0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800015e5  call    _CxxThrowException_0
```
