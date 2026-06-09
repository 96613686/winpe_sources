# WPP_SF_D

- ea: `0x14000ab98`
- end: `0x14000abcf`
- name: `WPP_SF_D`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x14000b250`
- `0x14000dc6c`
- `0x14000ee8c`
- `0x14000f70c`
- `0x1400100d8`
- `0x140011c60`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x14000abc4`
- `ADVAPI32!TraceMessage` at `0x14000abc4`

## pseudocode

```c
ULONG __fastcall WPP_SF_D(TRACEHANDLE a1, USHORT a2, const GUID *a3, int a4)
{
  int v5; // [rsp+68h] [rbp+20h] BYREF

  v5 = a4;
  return TraceMessage(a1, 0x2Bu, a3, a2, &v5, 4, 0);
}

```

## disassembly

```asm
0x14000ab98  mov     r11, rsp
0x14000ab9b  mov     [r11+20h], r9d
0x14000ab9f  sub     rsp, 48h
0x14000aba3  mov     qword ptr [r11-18h], 0
0x14000abab  lea     rax, [r11+20h]
0x14000abaf  movzx   r9d, dx; MessageNumber
0x14000abb3  mov     edx, 2Bh ; '+'; MessageFlags
0x14000abb8  mov     qword ptr [r11-20h], 4
0x14000abc0  mov     [r11-28h], rax
0x14000abc4  call    cs:__imp_TraceMessage
0x14000abca  add     rsp, 48h
0x14000abce  retn
```
