# WPP_SF_qI

- ea: `0x18000b85c`
- end: `0x18000b8a5`
- name: `WPP_SF_qI`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005770`
- `0x180006080`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_qI(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return FastWppTraceMessage(1050, a2, (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, va, 8, va1, 8, 0);
}

```

## disassembly

```asm
0x18000b85c  mov     r11, rsp
0x18000b85f  mov     [r11+20h], r9
0x18000b863  sub     rsp, 48h
0x18000b867  mov     ecx, 8
0x18000b86c  mov     qword ptr [r11-10h], 0
0x18000b874  mov     [r11-18h], rcx
0x18000b878  lea     rax, [r11+28h]
0x18000b87c  mov     [r11-20h], rax
0x18000b880  lea     r9, [r11+20h]
0x18000b884  mov     r10d, 41Ah
0x18000b88a  mov     [r11-28h], rcx
0x18000b88e  mov     ecx, r10d
0x18000b891  movzx   edx, dx
0x18000b894  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000b89b  call    FastWppTraceMessage
0x18000b8a0  add     rsp, 48h
0x18000b8a4  retn
```
