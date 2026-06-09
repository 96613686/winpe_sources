# WPP_SF_qD

- ea: `0x1800010fc`
- end: `0x18000114a`
- name: `WPP_SF_qD`
- size: `78`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001610`
- `0x1800084f4`
- `0x18000aecc`
- `0x18000b1d4`
- `0x18000d1c0`
- `0x18000fc50`
- `0x180010e40`
- `0x1800110c0`
- `0x18001127c`

## callees

- `0x180001fb0`

## pseudocode

```c
__int64 WPP_SF_qD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  va_list va1; // [rsp+80h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1800010fc  mov     r11, rsp
0x1800010ff  mov     [r11+20h], r9
0x180001103  sub     rsp, 58h
0x180001107  mov     rax, cs:pfnWppTraceMessage
0x18000110e  lea     r9, [r11+28h]
0x180001112  mov     qword ptr [r11-18h], 0
0x18000111a  mov     qword ptr [r11-20h], 4
0x180001122  mov     [r11-28h], r9
0x180001126  lea     r9, [r11+20h]
0x18000112a  mov     qword ptr [r11-30h], 8
0x180001132  mov     [r11-38h], r9
0x180001136  movzx   r9d, dx
0x18000113a  mov     edx, 2Bh ; '+'
0x18000113f  call    _guard_dispatch_icall
0x180001144  add     rsp, 58h
0x180001148  retn
```
