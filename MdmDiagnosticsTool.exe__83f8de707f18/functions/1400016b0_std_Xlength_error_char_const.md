# std::_Xlength_error(char const *)

- ea: `0x1400016b0`
- end: `0x1400016d3`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002df8`
- `0x140007414`
- `0x140007494`
- `0x1400076f4`
- `0x1400077f0`
- `0x1400078b0`
- `0x1400079a0`

## callees

- `0x1400015b4`
- `0x140001dec`

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
0x1400016b0  sub     rsp, 48h
0x1400016b4  mov     rdx, rcx; char *
0x1400016b7  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400016bc  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1400016c1  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1400016c8  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400016cd  call    _CxxThrowException_0
```
