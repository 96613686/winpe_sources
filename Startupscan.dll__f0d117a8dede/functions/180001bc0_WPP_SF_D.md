# WPP_SF_D

- ea: `0x180001bc0`
- end: `0x180001bf7`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(__int64, unsigned __int16, __int64, int)`
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001940`
- `0x1800019a0`
- `0x180001a00`
- `0x180001a60`
- `0x180002c64`
- `0x180003164`
- `0x180003478`
- `0x180003610`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180001bec`
- `ntdll!EtwTraceMessage` at `0x180001bec`

## pseudocode

```c
__int64 __fastcall WPP_SF_D(__int64 a1, unsigned __int16 a2, __int64 a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return EtwTraceMessage(a1, 43, a3, a2, &v5);
}

```

## disassembly

```asm
0x180001bc0  mov     r11, rsp
0x180001bc3  mov     [r11+20h], r9d
0x180001bc7  sub     rsp, 48h
0x180001bcb  mov     qword ptr [r11-18h], 0
0x180001bd3  lea     rax, [r11+20h]
0x180001bd7  movzx   r9d, dx
0x180001bdb  mov     edx, 2Bh ; '+'
0x180001be0  mov     qword ptr [r11-20h], 4
0x180001be8  mov     [r11-28h], rax
0x180001bec  call    cs:__imp_EtwTraceMessage
0x180001bf2  add     rsp, 48h
0x180001bf6  retn
```
