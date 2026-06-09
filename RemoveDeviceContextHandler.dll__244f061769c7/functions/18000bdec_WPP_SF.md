# WPP_SF_

- ea: `0x18000bdec`
- end: `0x18000be14`
- name: `WPP_SF_`
- size: `40`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180006fd8`
- `0x180007a10`
- `0x180007f80`
- `0x1800082c0`
- `0x1800085b0`
- `0x18000a2b0`
- `0x18000b5dc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000be09`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000be09`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2)
{
  return TraceMessage(a1, 0x2Bu, &WPP_1d6fff2cd8463d06a7f66ef5d4aaafbc_Traceguids, a2, 0);
}

```

## disassembly

```asm
0x18000bdec  sub     rsp, 38h
0x18000bdf0  movzx   r9d, dx; MessageNumber
0x18000bdf4  lea     r8, WPP_1d6fff2cd8463d06a7f66ef5d4aaafbc_Traceguids; MessageGuid
0x18000bdfb  mov     edx, 2Bh ; '+'; MessageFlags
0x18000be00  mov     [rsp+38h+var_18], 0
0x18000be09  call    cs:__imp_TraceMessage
0x18000be0f  add     rsp, 38h
0x18000be13  retn
```
