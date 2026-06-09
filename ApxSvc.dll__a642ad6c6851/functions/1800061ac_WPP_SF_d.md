# WPP_SF_d

- ea: `0x1800061ac`
- end: `0x1800061e3`
- name: `WPP_SF_d`
- size: `55`
- prototype: `ULONG __fastcall(TRACEHANDLE, USHORT, const GUID *, int)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180005bc4`
- `0x1800063c8`
- `0x180006554`
- `0x180006740`
- `0x180006c94`
- `0x180007660`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800061d8`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x1800061d8`

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
0x1800061ac  mov     r11, rsp
0x1800061af  mov     [r11+20h], r9d
0x1800061b3  sub     rsp, 48h
0x1800061b7  mov     qword ptr [r11-18h], 0
0x1800061bf  lea     rax, [r11+20h]
0x1800061c3  movzx   r9d, dx; MessageNumber
0x1800061c7  mov     edx, 2Bh ; '+'; MessageFlags
0x1800061cc  mov     qword ptr [r11-20h], 4
0x1800061d4  mov     [r11-28h], rax
0x1800061d8  call    cs:__imp_TraceMessage
0x1800061de  add     rsp, 48h
0x1800061e2  retn
```
