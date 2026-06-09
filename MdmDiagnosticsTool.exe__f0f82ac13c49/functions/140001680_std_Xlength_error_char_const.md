# std::_Xlength_error(char const *)

- ea: `0x140001680`
- end: `0x1400016a3`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140002d74`
- `0x140007018`
- `0x140007098`
- `0x1400072e0`
- `0x1400073dc`
- `0x14000749c`
- `0x14000758c`

## callees

- `0x140001584`
- `0x140001dbc`

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
0x140001680  sub     rsp, 48h
0x140001684  mov     rdx, rcx; char *
0x140001687  lea     rcx, [rsp+48h+pExceptionObject]; this
0x14000168c  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x140001691  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x140001698  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14000169d  call    _CxxThrowException_0
```
