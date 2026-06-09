# WPP_SF_c

- ea: `0x180010ed4`
- end: `0x180010f0b`
- name: `WPP_SF_c`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, char)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eadc`
- `0x18000f968`
- `0x1800111f4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180010f00`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180010f00`

## pseudocode

```c
ULONG __fastcall WPP_SF_c(TRACEHANDLE a1, USHORT a2, const GUID *a3, char a4)
{
  char v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 1, 0);
}

```

## disassembly

```asm
0x180010ed4  mov     r11, rsp
0x180010ed7  mov     [r11+20h], r9b
0x180010edb  sub     rsp, 48h
0x180010edf  mov     qword ptr [r11-18h], 0
0x180010ee7  lea     rax, [r11+20h]
0x180010eeb  movzx   r9d, dx; MessageNumber
0x180010eef  mov     edx, 2Bh ; '+'; MessageFlags
0x180010ef4  mov     qword ptr [r11-20h], 1
0x180010efc  mov     [r11-28h], rax
0x180010f00  call    cs:__imp_TraceMessage
0x180010f06  add     rsp, 48h
0x180010f0a  retn
```
