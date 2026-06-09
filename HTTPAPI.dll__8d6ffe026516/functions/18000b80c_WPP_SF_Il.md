# WPP_SF_Il

- ea: `0x18000b80c`
- end: `0x18000b854`
- name: `WPP_SF_Il`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180001a30`
- `0x180006dc0`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_Il(__int64 a1, USHORT a2, __int64 a3, ...)
{
  __int64 v4; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return FastWppTraceMessage(1050, a2, (ULONGLONG)WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x18000b80c  mov     r11, rsp
0x18000b80f  mov     [r11+20h], r9
0x18000b813  sub     rsp, 48h
0x18000b817  mov     qword ptr [r11-10h], 0
0x18000b81f  lea     rax, [r11+28h]
0x18000b823  mov     qword ptr [r11-18h], 4
0x18000b82b  lea     r9, [r11+20h]
0x18000b82f  mov     [r11-20h], rax
0x18000b833  lea     r8, WPP_e34116c8aa7b3cb90090504062d578ea_Traceguids
0x18000b83a  mov     ecx, 41Ah
0x18000b83f  movzx   edx, dx
0x18000b842  mov     qword ptr [r11-28h], 8
0x18000b84a  call    FastWppTraceMessage
0x18000b84f  add     rsp, 48h
0x18000b853  retn
```
