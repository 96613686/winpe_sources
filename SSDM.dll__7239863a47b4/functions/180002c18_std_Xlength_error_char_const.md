# std::_Xlength_error(char const *)

- ea: `0x180002c18`
- end: `0x180002c3b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180007564`
- `0x18000757c`
- `0x18000c334`
- `0x18000cfd8`

## callees

- `0x180002b40`
- `0x180002ebc`

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
0x180002c18  sub     rsp, 48h
0x180002c1c  mov     rdx, rcx; char *
0x180002c1f  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002c24  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180002c29  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180002c30  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002c35  call    _CxxThrowException_0
```
