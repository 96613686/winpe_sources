# std::_Xout_of_range(char const *)

- ea: `0x1400016ac`
- end: `0x1400016cf`
- name: `?_Xout_of_range@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x1400072e0`
- `0x14000749c`
- `0x140007650`
- `0x1400077e4`
- `0x140007b20`
- `0x140007bc4`
- `0x140007c00`

## callees

- `0x140001584`
- `0x140001dbc`

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
0x1400016ac  sub     rsp, 48h
0x1400016b0  mov     rdx, rcx; char *
0x1400016b3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1400016b8  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x1400016bd  lea     rdx, _TI3?AVout_of_range@std@@; pThrowInfo
0x1400016c4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1400016c9  call    _CxxThrowException_0
```
