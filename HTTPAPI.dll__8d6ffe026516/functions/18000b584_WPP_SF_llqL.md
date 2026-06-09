# WPP_SF_llqL

- ea: `0x18000b584`
- end: `0x18000b5e1`
- name: `WPP_SF_llqL`
- size: `93`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180003980`
- `0x18000a3c0`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_llqL(__int16 a1, __int64 a2, ULONGLONG a3, int a4, ...)
{
  int v5; // [rsp+88h] [rbp+20h] BYREF
  __int64 v6; // [rsp+90h] [rbp+28h] BYREF
  va_list va; // [rsp+90h] [rbp+28h]
  __int64 v8; // [rsp+98h] [rbp+30h] BYREF
  va_list va1; // [rsp+98h] [rbp+30h]
  va_list va2; // [rsp+A0h] [rbp+38h] BYREF

  va_start(va2, a4);
  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v8 = va_arg(va2, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(a1, 0xAu, a3, &v5, 4, va, 4, va1, 8, va2, 4, 0);
}

```

## disassembly

```asm
0x18000b584  mov     r11, rsp
0x18000b587  mov     [r11+20h], r9d
0x18000b58b  sub     rsp, 68h
0x18000b58f  mov     qword ptr [r11-10h], 0
0x18000b597  lea     rax, [r11+38h]
0x18000b59b  mov     r10d, 0Ah
0x18000b5a1  movzx   ecx, cx
0x18000b5a4  lea     r9, [r11+20h]
0x18000b5a8  lea     edx, [r10-6]
0x18000b5ac  mov     [r11-18h], rdx
0x18000b5b0  mov     [r11-20h], rax
0x18000b5b4  lea     rax, [r11+30h]
0x18000b5b8  mov     qword ptr [r11-28h], 8
0x18000b5c0  mov     [r11-30h], rax
0x18000b5c4  lea     rax, [r11+28h]
0x18000b5c8  mov     [r11-38h], rdx
0x18000b5cc  mov     [r11-40h], rax
0x18000b5d0  mov     [r11-48h], rdx
0x18000b5d4  mov     edx, r10d
0x18000b5d7  call    FastWppTraceMessage
0x18000b5dc  add     rsp, 68h
0x18000b5e0  retn
```
