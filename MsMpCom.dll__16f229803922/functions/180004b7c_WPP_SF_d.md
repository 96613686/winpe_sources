# WPP_SF_d

- ea: `0x180004b7c`
- end: `0x180004bb3`
- name: `WPP_SF_d`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003380`
- `0x180005010`
- `0x180005530`
- `0x1800057f4`
- `0x180006e04`
- `0x180007c10`
- `0x180008bd4`
- `0x180008e98`

## import_xrefs

- `ADVAPI32!TraceMessage` at `0x180004ba8`
- `ADVAPI32!TraceMessage` at `0x180004ba8`

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
0x180004b7c  mov     r11, rsp
0x180004b7f  mov     [r11+20h], r9d
0x180004b83  sub     rsp, 48h
0x180004b87  mov     qword ptr [r11-18h], 0
0x180004b8f  lea     rax, [r11+20h]
0x180004b93  movzx   r9d, dx; MessageNumber
0x180004b97  mov     edx, 2Bh ; '+'; MessageFlags
0x180004b9c  mov     qword ptr [r11-20h], 4
0x180004ba4  mov     [r11-28h], rax
0x180004ba8  call    cs:__imp_TraceMessage
0x180004bae  add     rsp, 48h
0x180004bb2  retn
```
