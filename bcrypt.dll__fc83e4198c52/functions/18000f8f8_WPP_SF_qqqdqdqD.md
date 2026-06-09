# WPP_SF_qqqdqdqD

- ea: `0x18000f8f8`
- end: `0x18000f9a0`
- name: `WPP_SF_qqqdqdqD`
- size: `168`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD)`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800049a0`
- `0x18000fb30`
- `0x1800101c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000f98b`
- `ntdll!EtwTraceMessage` at `0x18000f98b`

## pseudocode

```c
__int64 WPP_SF_qqqdqdqD(__int64 a1, unsigned __int16 a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+D8h] [rbp+20h] BYREF
  va_list va; // [rsp+D8h] [rbp+20h]
  __int64 v6; // [rsp+E0h] [rbp+28h] BYREF
  va_list va1; // [rsp+E0h] [rbp+28h]
  __int64 v8; // [rsp+E8h] [rbp+30h] BYREF
  va_list va2; // [rsp+E8h] [rbp+30h]
  va_list va3; // [rsp+F0h] [rbp+38h] BYREF

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
           8,
           va3);
}

```

## disassembly

```asm
0x18000f8f8  mov     r11, rsp
0x18000f8fb  mov     [r11+20h], r9
0x18000f8ff  sub     rsp, 0B8h
0x18000f906  mov     qword ptr [r11-18h], 0
0x18000f90e  lea     rax, [r11+58h]
0x18000f912  mov     r8d, 4
0x18000f918  mov     [r11-20h], r8
0x18000f91c  mov     [r11-28h], rax
0x18000f920  lea     rax, [r11+50h]
0x18000f924  lea     r9d, [r8+4]
0x18000f928  mov     [r11-30h], r9
0x18000f92c  mov     [r11-38h], rax
0x18000f930  lea     rax, [r11+48h]
0x18000f934  mov     [r11-40h], r8
0x18000f938  mov     [r11-48h], rax
0x18000f93c  lea     rax, [r11+40h]
0x18000f940  mov     [r11-50h], r9
0x18000f944  mov     [r11-58h], rax
0x18000f948  lea     rax, [r11+38h]
0x18000f94c  mov     [r11-60h], r8
0x18000f950  lea     r8, WPP_40a0629bf3fc38698bf40003e296882d_Traceguids
0x18000f957  mov     [r11-68h], rax
0x18000f95b  lea     rax, [r11+30h]
0x18000f95f  mov     [r11-70h], r9
0x18000f963  mov     [r11-78h], rax
0x18000f967  lea     rax, [r11+28h]
0x18000f96b  mov     [r11-80h], r9
0x18000f96f  mov     [rsp+0B8h+var_88], rax
0x18000f974  lea     rax, [r11+20h]
0x18000f978  mov     [rsp+0B8h+var_90], r9
0x18000f97d  movzx   r9d, dx
0x18000f981  mov     edx, 2Bh ; '+'
0x18000f986  mov     [rsp+0B8h+var_98], rax
0x18000f98b  call    cs:__imp_EtwTraceMessage
0x18000f992  nop     dword ptr [rax+rax+00h]
0x18000f997  add     rsp, 0B8h
0x18000f99e  retn
```
