# WPP_SF_DDD

- ea: `0x1400104c8`
- end: `0x140010527`
- name: `WPP_SF_DDD`
- size: `95`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x140004ed0`
- `0x140009cb0`
- `0x1400259cc`

## callees

- `0x140013990`

## pseudocode

```c
__int64 WPP_SF_DDD(__int64 a1, unsigned __int16 a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  va_list va1; // [rsp+98h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return ((__int64 (__fastcall *)(__int64, __int64, __int64 *, _QWORD, int *, __int64, __int64 *, __int64, char *, __int64, _QWORD))pfnWppTraceMessage)(
           a1,
           43,
           WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
           a2,
           &v5,
           4,
           (__int64 *)va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x1400104c8  mov     r11, rsp
0x1400104cb  mov     [r11+20h], r9d
0x1400104cf  sub     rsp, 68h
0x1400104d3  mov     rax, cs:pfnWppTraceMessage
0x1400104da  lea     r8, [r11+30h]
0x1400104de  mov     qword ptr [r11-18h], 0
0x1400104e6  mov     r9d, 4
0x1400104ec  mov     [r11-20h], r9
0x1400104f0  mov     [r11-28h], r8
0x1400104f4  lea     r8, [r11+28h]
0x1400104f8  mov     [r11-30h], r9
0x1400104fc  mov     [r11-38h], r8
0x140010500  lea     r8, [r11+20h]
0x140010504  mov     [r11-40h], r9
0x140010508  mov     [r11-48h], r8
0x14001050c  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140010513  movzx   r9d, dx
0x140010517  mov     edx, 2Bh ; '+'
0x14001051c  call    _guard_dispatch_icall
0x140010521  add     rsp, 68h
0x140010525  retn
```
