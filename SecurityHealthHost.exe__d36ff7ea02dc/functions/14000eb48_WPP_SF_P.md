# WPP_SF_P

- ea: `0x14000eb48`
- end: `0x14000eb7f`
- name: `WPP_SF_P`
- size: `55`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x14000ded8`
- `0x14000df84`
- `0x14000e16c`
- `0x14000e6b4`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000eb74`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000eb74`

## pseudocode

```c
ULONG WPP_SF_P(TRACEHANDLE a1, USHORT a2, const GUID *a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, a3, a2, va, 8, 0);
}

```

## disassembly

```asm
0x14000eb48  mov     r11, rsp
0x14000eb4b  mov     [r11+20h], r9
0x14000eb4f  sub     rsp, 48h
0x14000eb53  mov     qword ptr [r11-18h], 0
0x14000eb5b  lea     rax, [r11+20h]
0x14000eb5f  movzx   r9d, dx; MessageNumber
0x14000eb63  mov     edx, 2Bh ; '+'; MessageFlags
0x14000eb68  mov     qword ptr [r11-20h], 8
0x14000eb70  mov     [r11-28h], rax
0x14000eb74  call    cs:__imp_TraceMessage
0x14000eb7a  add     rsp, 48h
0x14000eb7e  retn
```
