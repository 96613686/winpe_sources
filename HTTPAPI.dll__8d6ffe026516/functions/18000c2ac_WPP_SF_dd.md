# WPP_SF_dd

- ea: `0x18000c2ac`
- end: `0x18000c2f5`
- name: `WPP_SF_dd`
- size: `73`
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
ULONG WPP_SF_dd(__int64 a1, USHORT a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return FastWppTraceMessage(1050, a2, (ULONGLONG)WPP_9757c9c47725323be14918a4f6df94b6_Traceguids, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x18000c2ac  mov     r11, rsp
0x18000c2af  mov     [r11+20h], r9d
0x18000c2b3  sub     rsp, 48h
0x18000c2b7  mov     ecx, 4
0x18000c2bc  mov     qword ptr [r11-10h], 0
0x18000c2c4  mov     [r11-18h], rcx
0x18000c2c8  lea     rax, [r11+28h]
0x18000c2cc  mov     [r11-20h], rax
0x18000c2d0  lea     r9, [r11+20h]
0x18000c2d4  mov     r10d, 41Ah
0x18000c2da  mov     [r11-28h], rcx
0x18000c2de  mov     ecx, r10d
0x18000c2e1  movzx   edx, dx
0x18000c2e4  lea     r8, WPP_9757c9c47725323be14918a4f6df94b6_Traceguids
0x18000c2eb  call    FastWppTraceMessage
0x18000c2f0  add     rsp, 48h
0x18000c2f4  retn
```
