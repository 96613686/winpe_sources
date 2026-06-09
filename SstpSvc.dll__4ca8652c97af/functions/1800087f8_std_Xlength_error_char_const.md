# std::_Xlength_error(char const *)

- ea: `0x1800087f8`
- end: `0x18000881b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x180007e28`
- `0x18000805c`
- `0x1800118ec`
- `0x180011d2c`
- `0x180011e14`
- `0x180011fa4`
- `0x180012378`
- `0x1800123f4`
- `0x18001308c`
- `0x18001317c`

## callees

- `0x180008778`
- `0x180008fce`

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
0x1800087f8  sub     rsp, 48h
0x1800087fc  mov     rdx, rcx; char *
0x1800087ff  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180008804  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180008809  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180008810  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180008815  call    _CxxThrowException_0
```
