# WPP_SF_dDD

- ea: `0x18000c250`
- end: `0x18000c2a5`
- name: `WPP_SF_dDD`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008b90`
- `0x1800097c4`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_dDD(__int64 a1, USHORT a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  __int64 v6; // [rsp+80h] [rbp+28h] BYREF
  va_list va; // [rsp+80h] [rbp+28h]
  va_list va1; // [rsp+88h] [rbp+30h] BYREF

  va_start(va1, a4);
  va_start(va, a4);
  v6 = va_arg(va1, _QWORD);
  v5 = a4;
  return FastWppTraceMessage(
           1050,
           a2,
           (ULONGLONG)WPP_9757c9c47725323be14918a4f6df94b6_Traceguids,
           &v5,
           4,
           va,
           4,
           va1,
           4,
           0);
}

```

## disassembly

```asm
0x18000c250  mov     r11, rsp
0x18000c253  mov     [r11+20h], r9d
0x18000c257  sub     rsp, 58h
0x18000c25b  mov     qword ptr [r11-10h], 0
0x18000c263  lea     rax, [r11+30h]
0x18000c267  mov     ecx, 4
0x18000c26c  movzx   edx, dx
0x18000c26f  mov     [r11-18h], rcx
0x18000c273  lea     r9, [r11+20h]
0x18000c277  mov     [r11-20h], rax
0x18000c27b  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x18000c282  mov     [r11-28h], rcx
0x18000c286  lea     rax, [r11+28h]
0x18000c28a  mov     [r11-30h], rax
0x18000c28e  mov     r10d, 41Ah
0x18000c294  mov     [r11-38h], rcx
0x18000c298  mov     ecx, r10d
0x18000c29b  call    FastWppTraceMessage
0x18000c2a0  add     rsp, 58h
0x18000c2a4  retn
```
