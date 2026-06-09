# WPP_SF_

- ea: `0x18000dfd4`
- end: `0x18000dff5`
- name: `WPP_SF_`
- size: `33`
- prototype: ``
- caller_count: `14`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017c0`
- `0x180002a70`
- `0x1800031b0`
- `0x180003980`
- `0x180003b60`
- `0x180003cd0`
- `0x180003ed0`
- `0x180004620`
- `0x180004c50`
- `0x180005dc0`
- `0x1800060b0`
- `0x1800069d0`
- `0x18000e360`
- `0x180011b04`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000dfea`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x18000dfea`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x18000dfd4  sub     rsp, 38h
0x18000dfd8  movzx   r9d, dx; MessageNumber
0x18000dfdc  mov     edx, 2Bh ; '+'; MessageFlags
0x18000dfe1  mov     [rsp+38h+var_18], 0
0x18000dfea  call    cs:__imp_TraceMessage
0x18000dff0  add     rsp, 38h
0x18000dff4  retn
```
