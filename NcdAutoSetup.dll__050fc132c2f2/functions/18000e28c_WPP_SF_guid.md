# WPP_SF__guid_

- ea: `0x18000e28c`
- end: `0x18000e2c2`
- name: `WPP_SF__guid_`
- size: `54`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, __int64, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bb80`
- `0x18000bc10`
- `0x18000bde0`
- `0x18000be70`
- `0x18000d978`
- `0x18000dee0`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e2b7`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000e2b7`

## pseudocode

```c
ULONG __fastcall WPP_SF__guid_(TRACEHANDLE a1, USHORT a2, __int64 a3, __int64 a4)
{
  return TraceMessage(a1, 0x2Bu, &WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids, a2, a4, 16, 0);
}

```

## disassembly

```asm
0x18000e28c  sub     rsp, 48h
0x18000e290  mov     [rsp+48h+var_18], 0
0x18000e299  lea     r8, WPP_e12904a7fb053f955c1ac70c1ea20c99_Traceguids; MessageGuid
0x18000e2a0  mov     [rsp+48h+var_20], 10h
0x18000e2a9  mov     [rsp+48h+var_28], r9
0x18000e2ae  movzx   r9d, dx; MessageNumber
0x18000e2b2  mov     edx, 2Bh ; '+'; MessageFlags
0x18000e2b7  call    cs:__imp_TraceMessage
0x18000e2bd  add     rsp, 48h
0x18000e2c1  retn
```
