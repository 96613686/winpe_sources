# WPP_SF_dd

- ea: `0x180009bd0`
- end: `0x180009c15`
- name: `WPP_SF_dd`
- size: `69`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, int, ...)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180008420`
- `0x1800091a0`
- `0x18000c1a4`
- `0x18000c660`
- `0x18000cab0`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180009c0a`
- `ADVAPI32!TraceMessage` at `0x180009c0a`

## pseudocode

```c
ULONG WPP_SF_dd(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4, ...)
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
0x180009bd0  mov     r11, rsp
0x180009bd3  mov     [r11+20h], r9d
0x180009bd7  sub     rsp, 58h
0x180009bdb  mov     qword ptr [r11-18h], 0
0x180009be3  lea     rax, [r11+28h]
0x180009be7  mov     r9d, 4
0x180009bed  mov     [r11-20h], r9
0x180009bf1  mov     [r11-28h], rax
0x180009bf5  lea     rax, [r11+20h]
0x180009bf9  mov     [r11-30h], r9
0x180009bfd  movzx   r9d, dx; MessageNumber
0x180009c01  mov     edx, 2Bh ; '+'; MessageFlags
0x180009c06  mov     [r11-38h], rax
0x180009c0a  call    cs:__imp_TraceMessage
0x180009c10  add     rsp, 58h
0x180009c14  retn
```
