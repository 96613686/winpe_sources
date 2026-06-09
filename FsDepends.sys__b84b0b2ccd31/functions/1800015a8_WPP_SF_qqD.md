# WPP_SF_qqD

- ea: `0x1800015a8`
- end: `0x180001603`
- name: `WPP_SF_qqD`
- size: `91`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001610`
- `0x18000b5f0`
- `0x18000c940`
- `0x18000cb40`
- `0x18000f2e8`
- `0x18000fc50`

## callees

- `0x180001fb0`

## pseudocode

```c
__int64 WPP_SF_qqD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  va_list va2; // [rsp+98h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           a3,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           va2,
           4,
           0);
}

```

## disassembly

```asm
0x1800015a8  mov     r11, rsp
0x1800015ab  mov     [r11+20h], r9
0x1800015af  sub     rsp, 68h
0x1800015b3  mov     rax, cs:pfnWppTraceMessage
0x1800015ba  lea     r9, [r11+30h]
0x1800015be  mov     qword ptr [r11-18h], 0
0x1800015c6  mov     r10d, 8
0x1800015cc  mov     qword ptr [r11-20h], 4
0x1800015d4  mov     [r11-28h], r9
0x1800015d8  lea     r9, [r11+28h]
0x1800015dc  mov     [r11-30h], r10
0x1800015e0  mov     [r11-38h], r9
0x1800015e4  lea     r9, [r11+20h]
0x1800015e8  mov     [r11-40h], r10
0x1800015ec  mov     [r11-48h], r9
0x1800015f0  movzx   r9d, dx
0x1800015f4  lea     edx, [r10+23h]
0x1800015f8  call    _guard_dispatch_icall
0x1800015fd  add     rsp, 68h
0x180001601  retn
```
