# WPP_SF_

- ea: `0x14000bef0`
- end: `0x14000bf18`
- name: `WPP_SF_`
- size: `40`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x1400048e0`
- `0x1400066e4`
- `0x140006eb0`
- `0x14000728c`
- `0x140007ce0`
- `0x14000a628`
- `0x14000a6b4`
- `0x14000c7b0`
- `0x140010ecf`
- `0x14001109c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000bf0d`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000bf0d`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2)
{
  return TraceMessage(a1, 0x2Bu, &WPP_b0092361ee8d34528df1964c4db39788_Traceguids, a2, 0);
}

```

## disassembly

```asm
0x14000bef0  sub     rsp, 38h
0x14000bef4  movzx   r9d, dx; MessageNumber
0x14000bef8  lea     r8, WPP_b0092361ee8d34528df1964c4db39788_Traceguids; MessageGuid
0x14000beff  mov     edx, 2Bh ; '+'; MessageFlags
0x14000bf04  mov     [rsp+38h+var_18], 0
0x14000bf0d  call    cs:__imp_TraceMessage
0x14000bf13  add     rsp, 38h
0x14000bf17  retn
```
