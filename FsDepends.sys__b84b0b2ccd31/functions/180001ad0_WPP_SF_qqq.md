# WPP_SF_qqq

- ea: `0x180001ad0`
- end: `0x180001b27`
- name: `WPP_SF_qqq`
- size: `87`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180001610`
- `0x18000c8b0`
- `0x18000cb40`
- `0x18000ce60`
- `0x18000d1c0`
- `0x18000fc50`

## callees

- `0x180001fb0`

## pseudocode

```c
__int64 WPP_SF_qqq(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
           8,
           0);
}

```

## disassembly

```asm
0x180001ad0  mov     r11, rsp
0x180001ad3  mov     [r11+20h], r9
0x180001ad7  sub     rsp, 68h
0x180001adb  mov     rax, cs:pfnWppTraceMessage
0x180001ae2  lea     r9, [r11+30h]
0x180001ae6  mov     qword ptr [r11-18h], 0
0x180001aee  mov     r10d, 8
0x180001af4  mov     [r11-20h], r10
0x180001af8  mov     [r11-28h], r9
0x180001afc  lea     r9, [r11+28h]
0x180001b00  mov     [r11-30h], r10
0x180001b04  mov     [r11-38h], r9
0x180001b08  lea     r9, [r11+20h]
0x180001b0c  mov     [r11-40h], r10
0x180001b10  mov     [r11-48h], r9
0x180001b14  movzx   r9d, dx
0x180001b18  lea     edx, [r10+23h]
0x180001b1c  call    _guard_dispatch_icall
0x180001b21  add     rsp, 68h
0x180001b25  retn
```
