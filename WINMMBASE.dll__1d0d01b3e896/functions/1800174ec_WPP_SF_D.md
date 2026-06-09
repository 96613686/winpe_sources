# WPP_SF_D

- ea: `0x1800174ec`
- end: `0x180017523`
- name: `WPP_SF_D`
- size: `55`
- prototype: ``
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180003c80`
- `0x18000a960`
- `0x180017b20`
- `0x180017d30`
- `0x1800187a0`
- `0x18001d190`
- `0x18001dc78`
- `0x18001e8c8`
- `0x18001eb28`
- `0x18001ebc0`
- `0x18001ee20`
- `0x18001f238`
- `0x18001f880`
- `0x18001fb58`
- `0x18001fe4c`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180017518`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180017518`

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
0x1800174ec  mov     r11, rsp
0x1800174ef  mov     [r11+20h], r9d
0x1800174f3  sub     rsp, 48h
0x1800174f7  mov     qword ptr [r11-18h], 0
0x1800174ff  lea     rax, [r11+20h]
0x180017503  movzx   r9d, dx; MessageNumber
0x180017507  mov     edx, 2Bh ; '+'; MessageFlags
0x18001750c  mov     qword ptr [r11-20h], 4
0x180017514  mov     [r11-28h], rax
0x180017518  call    cs:__imp_TraceMessage
0x18001751e  add     rsp, 48h
0x180017522  retn
```
