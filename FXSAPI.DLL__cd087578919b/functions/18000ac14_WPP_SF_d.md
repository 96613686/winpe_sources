# WPP_SF_d

- ea: `0x18000ac14`
- end: `0x18000ac52`
- name: `WPP_SF_d`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `215`
- callee_count: `0`
- tags: ``

## callers

- `0x180003ffc`
- `0x180004394`
- `0x180006308`
- `0x180008cc8`
- `0x180009ba0`
- `0x180009dd0`
- `0x18000a140`
- `0x18000a2c0`
- `0x18000a830`
- `0x18000aa00`
- `0x18000af98`
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
- `0x18000fee0`
- `0x1800102a0`
- `0x180010480`
- `0x180010650`
- `0x180010720`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000ac40`
- `ADVAPI32!TraceMessage` at `0x18000ac40`

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
0x18000ac14  mov     r11, rsp
0x18000ac17  mov     [r11+20h], r9d
0x18000ac1b  sub     rsp, 48h
0x18000ac1f  mov     qword ptr [r11-18h], 0
0x18000ac27  lea     rax, [r11+20h]
0x18000ac2b  movzx   r9d, dx; MessageNumber
0x18000ac2f  mov     edx, 2Bh ; '+'; MessageFlags
0x18000ac34  mov     qword ptr [r11-20h], 4
0x18000ac3c  mov     [r11-28h], rax
0x18000ac40  call    cs:__imp_TraceMessage
0x18000ac47  nop     dword ptr [rax+rax+00h]
0x18000ac4c  add     rsp, 48h
0x18000ac50  retn
```
