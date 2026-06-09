# WPP_SF_Dd

- ea: `0x140004aa8`
- end: `0x140004aed`
- name: `WPP_SF_Dd`
- size: `69`
- prototype: `ULONG(TRACEHANDLE, USHORT, const GUID *, int, ...)`
- caller_count: `41`
- callee_count: `0`
- tags: ``

## callers

- `0x140003e38`
- `0x140005698`
- `0x140006e70`
- `0x140007f18`
- `0x14000bf3c`
- `0x14000d5f0`
- `0x14000de58`
- `0x14000ea7c`
- `0x14000f2e4`
- `0x1400100a0`
- `0x1400104f4`
- `0x140010d1c`
- `0x140012040`
- `0x1400127dc`
- `0x140015ff0`
- `0x14001742c`
- `0x1400188e8`
- `0x14001a270`
- `0x1400211a4`
- `0x14002dff4`
- `0x14002eef0`
- `0x140036390`
- `0x140038490`
- `0x140039de0`
- `0x14003a3d0`
- `0x14003ad70`
- `0x14003c7e8`
- `0x14003ca54`
- `0x14003cde0`
- `0x14003cfb4`
- `0x14003d2ec`
- `0x14003d800`
- `0x14003da18`
- `0x14003db78`
- `0x14003ddd4`
- `0x14003e49c`
- `0x14003e794`
- `0x14003e8ec`
- `0x14003e9d0`
- `0x14003eba8`
- `0x14003f4d8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140004ae2`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x140004ae2`

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
0x140004aa8  mov     r11, rsp
0x140004aab  mov     [r11+20h], r9d
0x140004aaf  sub     rsp, 58h
0x140004ab3  mov     qword ptr [r11-18h], 0
0x140004abb  lea     rax, [r11+28h]
0x140004abf  mov     r9d, 4
0x140004ac5  mov     [r11-20h], r9
0x140004ac9  mov     [r11-28h], rax
0x140004acd  lea     rax, [r11+20h]
0x140004ad1  mov     [r11-30h], r9
0x140004ad5  movzx   r9d, dx; MessageNumber
0x140004ad9  mov     edx, 2Bh ; '+'; MessageFlags
0x140004ade  mov     [r11-38h], rax
0x140004ae2  call    cs:__imp_TraceMessage
0x140004ae8  add     rsp, 58h
0x140004aec  retn
```
