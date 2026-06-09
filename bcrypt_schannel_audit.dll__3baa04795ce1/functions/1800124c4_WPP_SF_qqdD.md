# WPP_SF_qqdD

- ea: `0x1800124c4`
- end: `0x180012535`
- name: `WPP_SF_qqdD`
- size: `113`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180005280`
- `0x180005470`
- `0x1800078e0`
- `0x18000a230`
- `0x18000c1e0`
- `0x18000cc10`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180012523`
- `ntdll!EtwTraceMessage` at `0x180012523`

## pseudocode

```c
__int64 WPP_SF_qqdD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va2; // [rsp+A8h] [rbp+30h]
  va_list va3; // [rsp+B0h] [rbp+38h] BYREF

  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  return EtwTraceMessage(
           a1,
           43,
           WPP_40a0629bf3fc38698bf40003e296882d_Traceguids,
           a2,
           (__int64 *)va,
           8,
           (__int64 *)va1,
           8,
           (__int64 *)va2,
           4,
           va3,
           4,
           0);
}

```

## disassembly

```asm
0x1800124c4  mov     r11, rsp
0x1800124c7  mov     [r11+20h], r9
0x1800124cb  sub     rsp, 78h
0x1800124cf  mov     qword ptr [r11-18h], 0
0x1800124d7  lea     rax, [r11+38h]
0x1800124db  mov     r8d, 4
0x1800124e1  movzx   r9d, dx
0x1800124e5  mov     [r11-20h], r8
0x1800124e9  mov     edx, 2Bh ; '+'
0x1800124ee  mov     [r11-28h], rax
0x1800124f2  lea     rax, [r11+30h]
0x1800124f6  mov     [r11-30h], r8
0x1800124fa  mov     r8d, 8
0x180012500  mov     [r11-38h], rax
0x180012504  lea     rax, [r11+28h]
0x180012508  mov     [r11-40h], r8
0x18001250c  mov     [r11-48h], rax
0x180012510  lea     rax, [r11+20h]
0x180012514  mov     [r11-50h], r8
0x180012518  lea     r8, WPP_40a0629bf3fc38698bf40003e296882d_Traceguids
0x18001251f  mov     [r11-58h], rax
0x180012523  call    cs:__imp_EtwTraceMessage
0x18001252a  nop     dword ptr [rax+rax+00h]
0x18001252f  add     rsp, 78h
0x180012533  retn
```
