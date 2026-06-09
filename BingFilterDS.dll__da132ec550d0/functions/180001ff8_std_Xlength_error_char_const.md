# std::_Xlength_error(char const *)

- ea: `0x180001ff8`
- end: `0x18000201b`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007170`
- `0x180008210`
- `0x18000ad10`

## callees

- `0x180001ed0`
- `0x18000274c`

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
0x180001ff8  sub     rsp, 48h
0x180001ffc  mov     rdx, rcx; char *
0x180001fff  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180002004  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180002009  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180002010  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180002015  call    _CxxThrowException_0
```
