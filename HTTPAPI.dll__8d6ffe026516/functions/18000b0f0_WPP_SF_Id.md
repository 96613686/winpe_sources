# WPP_SF_Id

- ea: `0x18000b0f0`
- end: `0x18000b131`
- name: `WPP_SF_Id`
- size: `65`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d20`
- `0x180002820`
- `0x180004f80`
- `0x180005050`
- `0x180005c70`
- `0x180005fe0`
- `0x180006150`
- `0x180006230`
- `0x1800068e0`
- `0x1800069c0`
- `0x180008480`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_Id(__int64 a1, USHORT a2, ULONGLONG a3, ...)
{
  __int64 v4; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+68h] [rbp+20h]
  va_list va1; // [rsp+70h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v4 = va_arg(va1, _QWORD);
  return FastWppTraceMessage(1050, a2, a3, va, 8, va1, 4, 0);
}

```

## disassembly

```asm
0x18000b0f0  mov     r11, rsp
0x18000b0f3  mov     [r11+20h], r9
0x18000b0f7  sub     rsp, 48h
0x18000b0fb  mov     qword ptr [r11-10h], 0
0x18000b103  lea     rax, [r11+28h]
0x18000b107  mov     qword ptr [r11-18h], 4
0x18000b10f  lea     r9, [r11+20h]
0x18000b113  mov     [r11-20h], rax
0x18000b117  mov     ecx, 41Ah
0x18000b11c  movzx   edx, dx
0x18000b11f  mov     qword ptr [r11-28h], 8
0x18000b127  call    FastWppTraceMessage
0x18000b12c  add     rsp, 48h
0x18000b130  retn
```
