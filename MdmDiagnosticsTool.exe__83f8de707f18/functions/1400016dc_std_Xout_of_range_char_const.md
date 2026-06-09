# std::_Xout_of_range(char const *)

- ea: `0x1400016dc`
- end: `0x1400016ff`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400076f4`
- `0x1400078b0`
- `0x140007a68`
- `0x140007bfc`
- `0x140007f50`
- `0x140007ff4`
- `0x140008034`

## callees

- `0x1400015b4`
- `0x140001dec`

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
0x1400016dc  sub     rsp, 48h
0x1400016e0  mov     rdx, rcx; char *
0x1400016e3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400016e8  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1400016ed  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1400016f4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400016f9  call    _CxxThrowException_0
```
