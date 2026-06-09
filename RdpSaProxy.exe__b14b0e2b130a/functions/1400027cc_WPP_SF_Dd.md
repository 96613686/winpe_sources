# WPP_SF_Dd

- ea: `0x1400027cc`
- end: `0x140002811`
- name: `WPP_SF_Dd`
- size: `69`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, int, ...)`
- caller_count: `16`
- callee_count: `0`
- tags: ``

## callers

- `0x140002578`
- `0x140002944`
- `0x140002f60`
- `0x1400032f0`
- `0x1400035d8`
- `0x1400039e0`
- `0x140003c20`
- `0x140003d90`
- `0x140003ef4`
- `0x140004240`
- `0x140004370`
- `0x140004590`
- `0x140004750`
- `0x14000499c`
- `0x140004c0c`
- `0x140005058`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x140002806`
- `ADVAPI32!TraceMessage` at `0x140002806`

## pseudocode

```c
ULONG WPP_SF_Dd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
{
  int v5; // [rsp+78h] [rbp+20h] BYREF
  va_list va; // [rsp+80h] [rbp+28h] BYREF

  va_start(va, a4);
  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, va, 4, 0);
}

```

## disassembly

```asm
0x1400027cc  mov     r11, rsp
0x1400027cf  mov     [r11+20h], r9d
0x1400027d3  sub     rsp, 58h
0x1400027d7  mov     qword ptr [r11-18h], 0
0x1400027df  lea     rax, [r11+28h]
0x1400027e3  mov     r9d, 4
0x1400027e9  mov     [r11-20h], r9
0x1400027ed  mov     [r11-28h], rax
0x1400027f1  lea     rax, [r11+20h]
0x1400027f5  mov     [r11-30h], r9
0x1400027f9  movzx   r9d, dx; MessageNumber
0x1400027fd  mov     edx, 2Bh ; '+'; MessageFlags
0x140002802  mov     [r11-38h], rax
0x140002806  call    cs:__imp_TraceMessage
0x14000280c  add     rsp, 58h
0x140002810  retn
```
