# SiGetFirmwareSystemPartition

- ea: `0x1400135b0`
- end: `0x1400135b8`
- name: `SiGetFirmwareSystemPartition`
- size: `8`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140013484`

## pseudocode

```c
__int64 __fastcall SiGetFirmwareSystemPartition(__int64 a1, __int64 a2, __int64 a3)
{
  return SiGetFirmwareSystemDevice(a1, a2, a3, a2);
}

```

## disassembly

```asm
0x1400135b0  mov     r9, rdx
0x1400135b3  jmp     SiGetFirmwareSystemDevice
```
