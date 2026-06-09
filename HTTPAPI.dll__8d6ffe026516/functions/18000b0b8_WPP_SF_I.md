# WPP_SF_I

- ea: `0x18000b0b8`
- end: `0x18000b0e9`
- name: `WPP_SF_I`
- size: `49`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x180001130`
- `0x180001490`
- `0x1800015d0`
- `0x180003bc0`
- `0x180004c00`
- `0x180005290`
- `0x180005520`
- `0x1800055b0`
- `0x180005660`
- `0x1800056e0`
- `0x180005810`
- `0x1800058b0`
- `0x180005ab0`
- `0x180005c70`
- `0x180006d10`
- `0x180009280`

## callees

- `0x1800072e0`

## pseudocode

```c
ULONG WPP_SF_I(__int64 a1, USHORT a2, ULONGLONG a3, ...)
{
  va_list va; // [rsp+58h] [rbp+20h] BYREF

  va_start(va, a3);
  return FastWppTraceMessage(1050, a2, a3, va, 8, 0);
}

```

## disassembly

```asm
0x18000b0b8  mov     rax, rsp
0x18000b0bb  mov     [rax+20h], r9
0x18000b0bf  sub     rsp, 38h
0x18000b0c3  mov     qword ptr [rax-10h], 0
0x18000b0cb  lea     r9, [rax+20h]
0x18000b0cf  mov     ecx, 41Ah
0x18000b0d4  movzx   edx, dx
0x18000b0d7  mov     qword ptr [rax-18h], 8
0x18000b0df  call    FastWppTraceMessage
0x18000b0e4  add     rsp, 38h
0x18000b0e8  retn
```
