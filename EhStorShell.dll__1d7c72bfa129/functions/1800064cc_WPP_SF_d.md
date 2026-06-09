# WPP_SF_d

- ea: `0x1800064cc`
- end: `0x180006503`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180001890`
- `0x180001b20`
- `0x180002610`
- `0x180002c60`
- `0x180003340`
- `0x180003670`
- `0x180003a98`
- `0x180004260`
- `0x1800048e0`
- `0x180005dc0`
- `0x180006890`
- `0x1800095c0`
- `0x1800097a0`
- `0x180009b6c`
- `0x180009f00`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x1800064f8`
- `ADVAPI32!TraceMessage` at `0x1800064f8`

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
0x1800064cc  mov     r11, rsp
0x1800064cf  mov     [r11+20h], r9d
0x1800064d3  sub     rsp, 48h
0x1800064d7  mov     qword ptr [r11-18h], 0
0x1800064df  lea     rax, [r11+20h]
0x1800064e3  movzx   r9d, dx; MessageNumber
0x1800064e7  mov     edx, 2Bh ; '+'; MessageFlags
0x1800064ec  mov     qword ptr [r11-20h], 4
0x1800064f4  mov     [r11-28h], rax
0x1800064f8  call    cs:__imp_TraceMessage
0x1800064fe  add     rsp, 48h
0x180006502  retn
```
