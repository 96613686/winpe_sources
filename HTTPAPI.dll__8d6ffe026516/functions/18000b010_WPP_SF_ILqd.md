# WPP_SF_ILqd

- ea: `0x18000b010`
- end: `0x18000b078`
- name: `WPP_SF_ILqd`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001330`
- `0x180002610`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_ILqd(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+88h] [rbp+20h] BYREF
  va_list va; // [rsp+88h] [rbp+20h]
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va1; // [rsp+90h] [rbp+28h]
  __int64 v8; // [rsp+98h] [rbp+30h] BYREF
  va_list va2; // [rsp+98h] [rbp+30h]
  va_list va3; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids,
           va,
           8,
           va1,
           4,
           va2,
           8,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x18000b010  mov     r11, rsp
0x18000b013  mov     [r11+20h], r9
0x18000b017  sub     rsp, 68h
0x18000b01b  mov     qword ptr [r11-10h], 0
0x18000b023  lea     rax, [r11+38h]
0x18000b027  mov     qword ptr [r11-18h], 4
0x18000b02f  lea     r9, [r11+20h]
0x18000b033  mov     [r11-20h], rax
0x18000b037  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000b03e  mov     qword ptr [r11-28h], 8
0x18000b046  lea     rax, [r11+30h]
0x18000b04a  mov     [r11-30h], rax
0x18000b04e  mov     ecx, 41Ah
0x18000b053  mov     qword ptr [r11-38h], 4
0x18000b05b  lea     rax, [r11+28h]
0x18000b05f  mov     [r11-40h], rax
0x18000b063  movzx   edx, dx
0x18000b066  mov     qword ptr [r11-48h], 8
0x18000b06e  call    FastWppTraceMessage
0x18000b073  add     rsp, 68h
0x18000b077  retn
```
