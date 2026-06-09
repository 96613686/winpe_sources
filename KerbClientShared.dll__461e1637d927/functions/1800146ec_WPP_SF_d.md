# WPP_SF_d

- ea: `0x1800146ec`
- end: `0x180014723`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `20`
- callee_count: `0`
- tags: ``

## callers

- `0x1800012e0`
- `0x1800016f0`
- `0x180001ea0`
- `0x180003730`
- `0x180007ce0`
- `0x180008a40`
- `0x180009c50`
- `0x180009d60`
- `0x180009fa0`
- `0x18000a1b0`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000b790`
- `0x18000c8c0`
- `0x18000e2a0`
- `0x180015010`
- `0x180015e10`
- `0x180016328`
- `0x1800171cc`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014718`
- `api-ms-win-eventing-classicprovider-l1-1-0!TraceMessage` at `0x180014718`

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
0x1800146ec  mov     r11, rsp
0x1800146ef  mov     [r11+20h], r9d
0x1800146f3  sub     rsp, 48h
0x1800146f7  mov     qword ptr [r11-18h], 0
0x1800146ff  lea     rax, [r11+20h]
0x180014703  movzx   r9d, dx; MessageNumber
0x180014707  mov     edx, 2Bh ; '+'; MessageFlags
0x18001470c  mov     qword ptr [r11-20h], 4
0x180014714  mov     [r11-28h], rax
0x180014718  call    cs:__imp_TraceMessage
0x18001471e  add     rsp, 48h
0x180014722  retn
```
