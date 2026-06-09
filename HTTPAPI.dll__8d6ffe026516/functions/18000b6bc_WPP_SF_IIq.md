# WPP_SF_IIq

- ea: `0x18000b6bc`
- end: `0x18000b711`
- name: `WPP_SF_IIq`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e50`
- `0x180005f00`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_IIq(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+78h] [rbp+20h]
  __int64 v6; // [rsp+80h] [rbp+28h] BYREF
  va_list va1; // [rsp+80h] [rbp+28h]
  va_list va2; // [rsp+88h] [rbp+30h] BYREF

  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids,
           va,
           8,
           va1,
           8,
           va2,
           8,
           0);
}

```

## disassembly

```asm
0x18000b6bc  mov     r11, rsp
0x18000b6bf  mov     [r11+20h], r9
0x18000b6c3  sub     rsp, 58h
0x18000b6c7  mov     qword ptr [r11-10h], 0
0x18000b6cf  lea     rax, [r11+30h]
0x18000b6d3  mov     ecx, 8
0x18000b6d8  movzx   edx, dx
0x18000b6db  mov     [r11-18h], rcx
0x18000b6df  lea     r9, [r11+20h]
0x18000b6e3  mov     [r11-20h], rax
0x18000b6e7  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000b6ee  mov     [r11-28h], rcx
0x18000b6f2  lea     rax, [r11+28h]
0x18000b6f6  mov     [r11-30h], rax
0x18000b6fa  mov     r10d, 41Ah
0x18000b700  mov     [r11-38h], rcx
0x18000b704  mov     ecx, r10d
0x18000b707  call    FastWppTraceMessage
0x18000b70c  add     rsp, 58h
0x18000b710  retn
```
