# std::_Xlength_error(char const *)

- ea: `0x180011b84`
- end: `0x180011ba7`
- name: `?_Xlength_error@std@@YAXPEBD@Z`
- size: `35`
- prototype: `void __fastcall __noreturn(const char *)`
- caller_count: `36`
- callee_count: `2`
- tags: ``

## callers

- `0x180001c08`
- `0x180002af4`
- `0x1800030b0`
- `0x180003940`
- `0x180003d44`
- `0x180004668`
- `0x1800046f8`
- `0x180004920`
- `0x180004c88`
- `0x180004d80`
- `0x180005000`
- `0x180005140`
- `0x180005780`
- `0x180009288`
- `0x180009350`
- `0x18000951c`
- `0x18000a3ec`
- `0x18000a468`
- `0x18000a560`
- `0x18000a5dc`
- `0x18000c34c`
- `0x18000e498`
- `0x180016db8`
- `0x18001a4c0`
- `0x18001aad4`
- `0x18001b598`
- `0x18001b654`
- `0x18001b7bc`
- `0x18001f10c`
- `0x18001f258`
- `0x180020f8c`
- `0x18002101c`
- `0x18002121c`
- `0x18002136c`
- `0x180021ea4`
- `0x18002201c`

## callees

- `0x180011adc`
- `0x180013294`

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
0x180011b84  sub     rsp, 48h
0x180011b88  mov     rdx, rcx; char *
0x180011b8b  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180011b90  call    ??0length_error@std@@QEAA@PEBD@Z; std::length_error::length_error(char const *)
0x180011b95  lea     rdx, _TI3?AVlength_error@std@@; pThrowInfo
0x180011b9c  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180011ba1  call    _CxxThrowException_0
```
