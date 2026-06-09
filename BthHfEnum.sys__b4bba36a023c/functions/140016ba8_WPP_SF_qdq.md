# WPP_SF_qdq

- ea: `0x140016ba8`
- end: `0x140016c0b`
- name: `WPP_SF_qdq`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x140016320`
- `0x140016520`
- `0x14002d400`
- `0x14002de78`

## callees

- `0x14001ae00`

## pseudocode

```c
__int64 WPP_SF_qdq(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
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
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, __int64 *, __int64, __int64 *, __int64, char *, __int64, _QWORD))WPP_MAIN_CB.Queue.Wcb.DeviceObject)(
           a1,
           43,
           WPP_4de776f173d133e87e80f57736d58590_Traceguids,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           4,
           va2,
           8,
           0);
}

```

## disassembly

```asm
0x140016ba8  mov     r11, rsp
0x140016bab  mov     [r11+20h], r9
0x140016baf  sub     rsp, 68h
0x140016bb3  mov     rax, qword ptr cs:WPP_MAIN_CB.Queue+30h
0x140016bba  lea     r8, [r11+30h]
0x140016bbe  mov     qword ptr [r11-18h], 0
0x140016bc6  mov     r9d, 8
0x140016bcc  mov     [r11-20h], r9
0x140016bd0  mov     [r11-28h], r8
0x140016bd4  lea     r8, [r11+28h]
0x140016bd8  mov     qword ptr [r11-30h], 4
0x140016be0  mov     [r11-38h], r8
0x140016be4  lea     r8, [r11+20h]
0x140016be8  mov     [r11-40h], r9
0x140016bec  mov     [r11-48h], r8
0x140016bf0  lea     r8, WPP_4de776f173d133e87e80f57736d58590_Traceguids
0x140016bf7  movzx   r9d, dx
0x140016bfb  mov     edx, 2Bh ; '+'
0x140016c00  call    _guard_dispatch_icall
0x140016c05  add     rsp, 68h
0x140016c09  retn
```
