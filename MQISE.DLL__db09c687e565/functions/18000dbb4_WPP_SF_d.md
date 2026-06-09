# WPP_SF_d

- ea: `0x18000dbb4`
- end: `0x18000dbeb`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180004f68`
- `0x180005528`
- `0x180005fb8`
- `0x180006570`
- `0x180006b94`
- `0x1800071c4`
- `0x1800080dc`
- `0x18000a3fc`
- `0x18000d1e0`
- `0x18000d3e0`
- `0x18000e884`
- `0x18000f0c8`
- `0x18000f170`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000dbe0`
- `ADVAPI32!TraceMessage` at `0x18000dbe0`

## pseudocode

```c
ULONG __fastcall WPP_SF_d(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x18000dbb4  mov     r11, rsp
0x18000dbb7  mov     [r11+20h], r9d
0x18000dbbb  sub     rsp, 48h
0x18000dbbf  mov     qword ptr [r11-18h], 0
0x18000dbc7  lea     rax, [r11+20h]
0x18000dbcb  movzx   r9d, dx; MessageNumber
0x18000dbcf  mov     edx, 2Bh ; '+'; MessageFlags
0x18000dbd4  mov     qword ptr [r11-20h], 4
0x18000dbdc  mov     [r11-28h], rax
0x18000dbe0  call    cs:__imp_TraceMessage
0x18000dbe6  add     rsp, 48h
0x18000dbea  retn
```
