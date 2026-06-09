# WPP_SF_

- ea: `0x18000abe4`
- end: `0x18000ac0c`
- name: `WPP_SF_`
- size: `40`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `264`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ffc`
- `0x180004394`
- `0x180004c3c`
- `0x180004cb4`
- `0x180006308`
- `0x180008cc8`
- `0x180009ba0`
- `0x180009dd0`
- `0x18000a140`
- `0x18000a2c0`
- `0x18000a830`
- `0x18000aa00`
- `0x18000af98`
- `0x18000b250`
- `0x18000b3f0`
- `0x18000b470`
- `0x18000b4f0`
- `0x18000b710`
- `0x18000b960`
- `0x18000bab0`
- `0x18000bd30`
- `0x18000bf50`
- `0x18000c0d0`
- `0x18000c530`
- `0x18000c670`
- `0x18000c9a0`
- `0x18000cb20`
- `0x18000ceb0`
- `0x18000d130`
- `0x18000d560`
- `0x18000d680`
- `0x18000d900`
- `0x18000da10`
- `0x18000dd00`
- `0x18000deb0`
- `0x18000e040`
- `0x18000e170`
- `0x18000e400`
- `0x18000e550`
- `0x18000e830`
- `0x18000eb50`
- `0x18000ed50`
- `0x18000f060`
- `0x18000f220`
- `0x18000f3b0`
- `0x18000f540`
- `0x18000f6a0`
- `0x18000fa10`
- `0x18000fba0`
- `0x18000fd80`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000abfa`
- `ADVAPI32!TraceMessage` at `0x18000abfa`

## pseudocode

```c
ULONG __fastcall WPP_SF_(TRACEHANDLE a1, USHORT a2, const GUID *a3)
{
  return TraceMessage(a1, 0x2Bu, a3, a2, 0);
}

```

## disassembly

```asm
0x18000abe4  sub     rsp, 38h
0x18000abe8  movzx   r9d, dx; MessageNumber
0x18000abec  mov     edx, 2Bh ; '+'; MessageFlags
0x18000abf1  mov     [rsp+38h+var_18], 0
0x18000abfa  call    cs:__imp_TraceMessage
0x18000ac01  nop     dword ptr [rax+rax+00h]
0x18000ac06  add     rsp, 38h
0x18000ac0a  retn
```
