# WPP_SF_Lq

- ea: `0x18000be64`
- end: `0x18000beac`
- name: `WPP_SF_Lq`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033b0`
- `0x180003ad0`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_Lq(__int64 a1, USHORT a2, __int64 a3, int a4, ...)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return FastWppTraceMessage(1050, a2, (ULONGLONG)WPP_d1f5b049c58935796a293ebb03e09278_Traceguids, &v5, 4, va, 8, 0);
}

```

## disassembly

```asm
0x18000be64  mov     r11, rsp
0x18000be67  mov     [r11+20h], r9d
0x18000be6b  sub     rsp, 48h
0x18000be6f  mov     qword ptr [r11-10h], 0
0x18000be77  lea     rax, [r11+28h]
0x18000be7b  mov     qword ptr [r11-18h], 8
0x18000be83  lea     r9, [r11+20h]
0x18000be87  mov     [r11-20h], rax
0x18000be8b  lea     r8, WPP_d1f5b049c58935796a293ebb03e09278_Traceguids
0x18000be92  mov     ecx, 41Ah
0x18000be97  movzx   edx, dx
0x18000be9a  mov     qword ptr [r11-28h], 4
0x18000bea2  call    FastWppTraceMessage
0x18000bea7  add     rsp, 48h
0x18000beab  retn
```
