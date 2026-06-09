# WPP_SF_d

- ea: `0x14000bf20`
- end: `0x14000bf57`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `12`
- callee_count: `0`
- tags: ``

## callers

- `0x140006064`
- `0x140006b40`
- `0x140006eb0`
- `0x14000728c`
- `0x14000a4a0`
- `0x14000c7b0`
- `0x14000eb40`
- `0x14000ec34`
- `0x14000ed48`
- `0x14000ee64`
- `0x14000f45c`
- `0x140010684`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000bf4c`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x14000bf4c`

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
0x14000bf20  mov     r11, rsp
0x14000bf23  mov     [r11+20h], r9d
0x14000bf27  sub     rsp, 48h
0x14000bf2b  mov     qword ptr [r11-18h], 0
0x14000bf33  lea     rax, [r11+20h]
0x14000bf37  movzx   r9d, dx; MessageNumber
0x14000bf3b  mov     edx, 2Bh ; '+'; MessageFlags
0x14000bf40  mov     qword ptr [r11-20h], 4
0x14000bf48  mov     [r11-28h], rax
0x14000bf4c  call    cs:__imp_TraceMessage
0x14000bf52  add     rsp, 48h
0x14000bf56  retn
```
