# std::_Xlength_error(char const *)

- ea: `0x1800015b8`
- end: `0x1800015db`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1800015a0`
- `0x180002974`
- `0x18000a438`
- `0x18000ab58`
- `0x18000ccb8`
- `0x18000ee54`
- `0x18000f7dc`

## callees

- `0x18000130c`
- `0x18000257c`

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
0x1800015b8  sub     rsp, 48h
0x1800015bc  mov     rdx, rcx; char *
0x1800015bf  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800015c4  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1800015c9  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x1800015d0  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800015d5  call    _CxxThrowException_0
```
