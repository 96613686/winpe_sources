# WPP_SF_q

- ea: `0x18000ba20`
- end: `0x18000ba5e`
- name: `WPP_SF_q`
- size: `62`
- prototype: `ULONG(TRACEHANDLE, USHORT, __int64, ...)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a02c`
- `0x18000aa40`
- `0x18000ac68`
- `0x18000adf0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ba53`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000ba53`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, &WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids, a2, va, 8, 0);
}

```

## disassembly

```asm
0x18000ba20  mov     r11, rsp
0x18000ba23  mov     [r11+20h], r9
0x18000ba27  sub     rsp, 48h
0x18000ba2b  mov     qword ptr [r11-18h], 0
0x18000ba33  lea     rax, [r11+20h]
0x18000ba37  movzx   r9d, dx; MessageNumber
0x18000ba3b  lea     r8, WPP_4b7fc9b143d0368172f607d8a9267014_Traceguids; MessageGuid
0x18000ba42  mov     qword ptr [r11-20h], 8
0x18000ba4a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ba4f  mov     [r11-28h], rax
0x18000ba53  call    cs:__imp_TraceMessage
0x18000ba59  add     rsp, 48h
0x18000ba5d  retn
```
