# WPP_SF_qILqL

- ea: `0x18000b9e4`
- end: `0x18000ba55`
- name: `WPP_SF_qILqL`
- size: `113`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800064c0`
- `0x1800065d0`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_qILqL(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v6; // [rsp+A0h] [rbp+28h] BYREF
  va_list va1; // [rsp+A0h] [rbp+28h]
  __int64 v8; // [rsp+A8h] [rbp+30h] BYREF
  va_list va2; // [rsp+A8h] [rbp+30h]
  __int64 v10; // [rsp+B0h] [rbp+38h] BYREF
  va_list va3; // [rsp+B0h] [rbp+38h]
  va_list va4; // [rsp+B8h] [rbp+40h] BYREF

  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v6 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v8 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v10 = va_arg(va4, _QWORD);
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids,
           va,
           8,
           va1,
           8,
           va2,
           4,
           va3,
           8,
           va4,
           4,
           0);
}

```

## disassembly

```asm
0x18000b9e4  mov     r11, rsp
0x18000b9e7  mov     [r11+20h], r9
0x18000b9eb  sub     rsp, 78h
0x18000b9ef  mov     qword ptr [r11-10h], 0
0x18000b9f7  lea     rax, [r11+40h]
0x18000b9fb  mov     ecx, 4
0x18000ba00  movzx   edx, dx
0x18000ba03  mov     [r11-18h], rcx
0x18000ba07  lea     r9, [r11+20h]
0x18000ba0b  mov     [r11-20h], rax
0x18000ba0f  mov     r10d, 41Ah
0x18000ba15  lea     rax, [r11+38h]
0x18000ba19  lea     r8d, [rcx+4]
0x18000ba1d  mov     [r11-28h], r8
0x18000ba21  mov     [r11-30h], rax
0x18000ba25  lea     rax, [r11+30h]
0x18000ba29  mov     [r11-38h], rcx
0x18000ba2d  mov     ecx, r10d
0x18000ba30  mov     [r11-40h], rax
0x18000ba34  lea     rax, [r11+28h]
0x18000ba38  mov     [r11-48h], r8
0x18000ba3c  mov     [r11-50h], rax
0x18000ba40  mov     [r11-58h], r8
0x18000ba44  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000ba4b  call    FastWppTraceMessage
0x18000ba50  add     rsp, 78h
0x18000ba54  retn
```
