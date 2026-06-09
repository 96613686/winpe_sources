# WPP_SF_d

- ea: `0x18000b6f4`
- end: `0x18000b72b`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `24`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003520`
- `0x180003710`
- `0x180003800`
- `0x180005720`
- `0x180005910`
- `0x180005c20`
- `0x180005e30`
- `0x180006000`
- `0x180006340`
- `0x180006810`
- `0x1800069e0`
- `0x180007df0`
- `0x180008930`
- `0x180008ce0`
- `0x18000c0b0`
- `0x18000c580`
- `0x18000da00`
- `0x18000dc90`
- `0x18000e1e8`
- `0x18000e6a0`
- `0x18000e960`
- `0x18000eac4`
- `0x18000eda0`
- `0x18000f160`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x18000b720`
- `ntdll!EtwTraceMessage` at `0x18000b720`

## pseudocode

```c
__int64 __fastcall WPP_SF_d(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x18000b6f4  mov     r11, rsp
0x18000b6f7  mov     [r11+20h], r9d
0x18000b6fb  sub     rsp, 48h
0x18000b6ff  mov     qword ptr [r11-18h], 0
0x18000b707  lea     rax, [r11+20h]
0x18000b70b  movzx   r9d, dx
0x18000b70f  mov     edx, 2Bh ; '+'
0x18000b714  mov     qword ptr [r11-20h], 4
0x18000b71c  mov     [r11-28h], rax
0x18000b720  call    cs:__imp_EtwTraceMessage
0x18000b726  add     rsp, 48h
0x18000b72a  retn
```
