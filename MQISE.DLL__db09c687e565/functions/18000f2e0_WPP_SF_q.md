# WPP_SF_q

- ea: `0x18000f2e0`
- end: `0x18000f31e`
- name: `WPP_SF_q`
- size: `62`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180002df0`
- `0x180003938`
- `0x180007988`
- `0x18000f214`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x18000f313`
- `ADVAPI32!TraceMessage` at `0x18000f313`

## pseudocode

```c
ULONG WPP_SF_q(TRACEHANDLE a1, USHORT a2, __int64 a3, ...)
{
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  return TraceMessage(a1, 0x2Bu, &WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids, a2, va, 8, 0);
}

```

## disassembly

```asm
0x18000f2e0  mov     r11, rsp
0x18000f2e3  mov     [r11+20h], r9
0x18000f2e7  sub     rsp, 48h
0x18000f2eb  mov     qword ptr [r11-18h], 0
0x18000f2f3  lea     rax, [r11+20h]
0x18000f2f7  movzx   r9d, dx; MessageNumber
0x18000f2fb  lea     r8, WPP_8d0ecbf9bd643f4a4a65022ade2d0c19_Traceguids; MessageGuid
0x18000f302  mov     qword ptr [r11-20h], 8
0x18000f30a  mov     edx, 2Bh ; '+'; MessageFlags
0x18000f30f  mov     [r11-28h], rax
0x18000f313  call    cs:__imp_TraceMessage
0x18000f319  add     rsp, 48h
0x18000f31d  retn
```
